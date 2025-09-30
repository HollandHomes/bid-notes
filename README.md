<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Project & Bid Notes Form</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap');
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f3f4f6;
            color: #1f2937;
        }
        input[type="text"], input[type="date"], textarea, input[type="tel"], input[type="email"] {
            border: 1px solid #d1d5db;
            border-radius: 0.375rem;
            padding: 0.5rem 0.75rem;
            width: 100%;
            background-color: #fff;
        }
        h1, h2, h3 {
            color: #111827;
        }
        .container {
            max-width: 5xl;
            margin: 2rem auto;
            background-color: #ffffff;
            padding: 2.5rem;
            border-radius: 0.75rem;
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
        }
        /* New print-specific styles */
        .print-view {
            display: none;
        }
        @media print {
            .container {
                box-shadow: none;
                padding: 0;
            }
            .no-print {
                display: none;
            }
            .print-view {
                display: block;
                /* Preserve white-space/line breaks from the textarea */
                white-space: pre-wrap; 
                word-wrap: break-word;
                font-family: 'Inter', sans-serif;
                font-size: 0.875rem; /* text-sm */
            }
            .page-break {
                page-break-after: always;
            }
        }
    </style>
</head>
<body class="p-6">

    <div class="container">
        <header class="text-center mb-10">
            <h1 class="text-3xl font-bold">Holland Family Home Services, Inc.</h1>
            <p class="text-xl font-bold mt-2">Project & Bid Notes Form</p>
            <p class="text-gray-600 mt-2">Use this form to gather your thoughts and details for a project. Save it as a PDF for your records.</p>
        </header>

        <section class="mb-8">
            <h2 class="text-2xl font-semibold mb-4 text-center">General Information</h2>
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                <div>
                    <label for="client-name" class="block text-sm font-medium text-gray-700 mb-1">Client Name</label>
                    <input type="text" id="client-name" name="client-name" placeholder="John Doe">
                </div>
                <div>
                    <label for="client-phone" class="block text-sm font-medium text-gray-700 mb-1">Client Phone Number</label>
                    <input type="tel" id="client-phone" name="client-phone" placeholder="555-555-5555">
                </div>
                <div>
                    <label for="client-email" class="block text-sm font-medium text-gray-700 mb-1">Client Email Address</label>
                    <input type="email" id="client-email" name="client-email" placeholder="john.doe@example.com">
                </div>
                <div>
                    <label for="project-name" class="block text-sm font-medium text-gray-700 mb-1">Project Name</label>
                    <input type="text" id="project-name" name="project-name" placeholder="Kitchen Remodel">
                </div>
                <div>
                    <label for="project-address" class="block text-sm font-medium text-gray-700 mb-1">Project Address</label>
                    <input type="text" id="project-address" name="project-address" placeholder="1234 Main St, Anytown, USA">
                </div>
                <div>
                    <label for="date-of-issue" class="block text-sm font-medium text-gray-700 mb-1">Date of Visit/Notes</label>
                    <input type="date" id="date-of-issue" name="date-of-issue">
                </div>
            </div>
        </section>

        <hr class="my-8 border-gray-300">

        <section class="mb-8">
            <h2 class="text-2xl font-semibold mb-4 text-center">Project Objective & Overall Scope</h2>
            <p class="text-gray-600 mb-4">Provide a high-level summary of the client's goals and the project's overall scope.</p>
            <textarea name="overall-scope" rows="5" placeholder="Example: The client wants to fully renovate their master bathroom to a modern aesthetic. This includes converting the tub to a walk-in shower, replacing the toilet, and updating the sink and fixtures." class="no-print"></textarea>
            <div class="print-view font-mono bg-white p-2 border mt-1" id="overall-scope-print"></div>
        </section>

        <hr class="my-8 border-gray-300">

        <section class="mb-8">
            <h2 class="text-2xl font-semibold mb-6 text-center">Exclusions & Notes</h2>
            <p class="text-gray-600 mb-4">List anything that is explicitly not included in the bid, or any other important notes to remember about the project.</p>
            <textarea name="exclusions-notes" rows="5" placeholder="Example: Exclusions: Any structural changes to the home's framing. Notes: Client mentioned they may want to upgrade to a smart thermostat in the future." class="no-print"></textarea>
            <div class="print-view font-mono bg-white p-2 border mt-1" id="exclusions-notes-print"></div>
        </section>

        <hr class="my-8 border-gray-300">

        <section class="mb-8">
            <h2 class="text-2xl font-semibold mb-6 text-center">Customer Needs & Site Notes</h2>
            <p class="text-gray-600 mb-4">Record details about the client's style preferences, any challenges with the site, or other important observations.</p>
            <textarea name="customer-notes" rows="5" placeholder="Example: Client prefers a minimalist, modern aesthetic with matte black fixtures. Access to the back yard is limited due to a narrow gate." class="no-print"></textarea>
            <div class="print-view font-mono bg-white p-2 border mt-1" id="customer-notes-print"></div>
        </section>

        <hr class="my-8 border-gray-300">

        <section class="mb-8">
            <h2 class="text-2xl font-semibold mb-6 text-center">Project & Bid Details</h2>
            <p class="text-gray-600 mb-4">Break down the project into specific line items with titles, detailed scope, and estimated costs. </p>

            <div id="project-container" class="space-y-6">
                <div class="project-field-group p-4 border rounded-lg bg-gray-50">
                    <h3 class="text-lg font-bold mb-3 text-indigo-700">Project 1</h3>
                    <div class="space-y-3">
                        <div>
                            <label for="project1-title" class="block text-sm font-medium text-gray-700 mb-1">Title</label>
                            <input type="text" id="project1-title" name="project1-title" placeholder="e.g., Tub-to-Walk-in Shower Conversion">
                        </div>
                        <div>
                            <label for="project1-scope" class="block text-sm font-medium text-gray-700 mb-1">Scope Details</label>
                            <textarea id="project1-scope" name="project1-scope" rows="5" placeholder="e.g., Demolition of existing tub, installation of a new shower pan and surround, new fixtures, and plumbing adjustments." class="no-print"></textarea>
                            <div class="print-view font-mono bg-white p-2 border mt-1" id="project1-scope-print"></div>
                        </div>
                        <div class="grid grid-cols-2 sm:grid-cols-4 gap-3">
                            <div>
                                <label for="project1-hours" class="block text-sm font-medium text-gray-700 mb-1">Est. Hours</label>
                                <input type="text" id="project1-hours" name="project1-hours" placeholder="e.g., 20">
                            </div>
                            <div>
                                <label for="project1-labor-cost" class="block text-sm font-medium text-gray-700 mb-1">Est. Labor Cost ($)</label>
                                <input type="text" id="project1-labor-cost" name="project1-labor-cost" placeholder="e.g., 1500 (numbers only)">
                            </div>
                            <div>
                                <label for="project1-materials-cost" class="block text-sm font-medium text-gray-700 mb-1">Est. Materials Cost ($)</label>
                                <input type="text" id="project1-materials-cost" name="project1-materials-cost" placeholder="e.g., 2500 (numbers only)">
                            </div>
                            <div>
                                <label for="project1-price" class="block text-sm font-medium text-gray-700 mb-1">Final Price ($)</label>
                                <input type="text" id="project1-price" name="project1-price" placeholder="e.g., 4155.77 (numbers only)">
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="mt-8 text-center no-print">
                <button onclick="addProjectField()" class="px-6 py-3 bg-indigo-600 text-white font-semibold rounded-lg shadow-md hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">
                    Add Another Project
                </button>
            </div>
        </section>

        <hr class="my-8 border-gray-300">

        <section class="mb-8">
            <h2 class="text-2xl font-semibold mb-4 text-center">Next Steps Checklist (Internal)</h2>
            <p class="text-gray-600 mb-4">A simple checklist to track your workflow for this project.</p>
            <div class="space-y-2">
                <div class="flex items-center space-x-2">
                    <input type="checkbox" id="next-step-1" name="next-step-1" class="h-4 w-4 rounded text-indigo-600 focus:ring-indigo-500">
                    <label for="next-step-1" class="text-sm font-medium text-gray-700">Finalize bid details</label>
                </div>
                <div class="flex items-center space-x-2">
                    <input type="checkbox" id="next-step-2" name="next-step-2" class="h-4 w-4 rounded text-indigo-600 focus:ring-indigo-500">
                    <label for="next-step-2" class="text-sm font-medium text-gray-700">Send to client</label>
                </div>
                <div class="flex items-center space-x-2">
                    <input type="checkbox" id="next-step-3" name="next-step-3" class="h-4 w-4 rounded text-indigo-600 focus:ring-indigo-500">
                    <label for="next-step-3" class="text-sm font-medium text-gray-700">Follow up in 3 days</label>
                </div>
                <div class="flex items-center space-x-2">
                    <input type="checkbox" id="next-step-4" name="next-step-4" class="h-4 w-4 rounded text-indigo-600 focus:ring-indigo-500">
                    <label for="next-step-4" class="text-sm font-medium text-gray-700">Order materials</label>
                </div>
                <div class="flex items-center space-x-2">
                    <input type="checkbox" id="next-step-5" name="next-step-5" class="h-4 w-4 rounded text-indigo-600 focus:ring-indigo-500">
                    <label for="next-step-5" class="text-sm font-medium text-gray-700">Schedule work</label>
                </div>
            </div>
        </section>

        <hr class="my-8 border-gray-300">

        <div class="mt-8">
            <div class="text-center mb-6">
                <button onclick="window.print()" class="no-print px-6 py-3 bg-indigo-600 text-white font-semibold rounded-lg shadow-md hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">
                    Save as PDF
                </button>
            </div>

            <div class="no-print bg-gray-100 p-6 rounded-lg">
                <p class="font-bold text-gray-700 mb-2">How to Save Your Proposal as a PDF:</p>

                <p class="font-semibold text-gray-700">For Desktop/Laptop Users:</p>
                <ol class="list-decimal list-inside mt-1 text-sm text-gray-600 space-y-1">
                    <li>Click the **Save as PDF** button above.</li>
                    <li>In the print dialog that appears, select **"Save as PDF"** or **"Microsoft Print to PDF"** from the printer destination menu.</li>
                    <li>Click **"Save"** or **"Print"** to download the completed form.</li>
                    <li>Email the saved PDF to **TheHollandSeven@gmail.com**.</li>
                </ol>

                <p class="font-semibold text-gray-700 mt-4">For Android or iPhone Users:</p>
                <ol class="list-decimal list-inside mt-1 text-sm text-gray-600 space-y-1">
                    <li>Click the **Save as PDF** button above.</li>
                    <li>In the print dialog, tap the dropdown menu to select a different printer or save option.</li>
                    <li>Choose **"Save as PDF"** from the list of options.</li>
                    <li>Save the file to your device.</li>
                    <li>Email the saved PDF to **TheHollandSeven@gmail.com**.</li>
                </ol>
            </div>
        </div>
    </div>
    <script>
        let projectCounter = 1;

        function resizeTextareas() {
            const textareas = document.querySelectorAll('textarea.no-print');
            textareas.forEach(textarea => {
                function resize() {
                    textarea.style.height = 'auto';
                    textarea.style.height = textarea.scrollHeight + 'px';
                    const printViewDiv = document.getElementById(textarea.name + '-print');
                    if (printViewDiv) {
                        // Crucial: Update the hidden print-view div with the textarea's content
                        printViewDiv.textContent = textarea.value;
                    }
                }
                textarea.removeEventListener('input', resize);
                textarea.addEventListener('input', resize);
                resize();
            });
        }

        function addProjectField() {
            projectCounter++;
            const projectContainer = document.getElementById('project-container');
            const newProjectDiv = document.createElement('div');
            // Added styling for separation and background color
            newProjectDiv.classList.add('project-field-group', 'p-4', 'border', 'rounded-lg', 'bg-gray-50', 'mt-6');

            const newProjectHTML = `
                <h3 class="text-lg font-bold mb-3 text-indigo-700">Project ${projectCounter}</h3>
                <div class="space-y-3">
                    <div>
                        <label for="project${projectCounter}-title" class="block text-sm font-medium text-gray-700 mb-1">Title</label>
                        <input type="text" id="project${projectCounter}-title" name="project${projectCounter}-title" placeholder="Title">
                    </div>
                    <div>
                        <label for="project${projectCounter}-scope" class="block text-sm font-medium text-gray-700 mb-1">Scope Details</label>
                        <textarea id="project${projectCounter}-scope" name="project${projectCounter}-scope" rows="5" placeholder="Scope" class="no-print"></textarea>
                        <div class="print-view font-mono bg-white p-2 border mt-1" id="project${projectCounter}-scope-print"></div>
                    </div>
                    <div class="grid grid-cols-2 sm:grid-cols-4 gap-3">
                        <div>
                            <label for="project${projectCounter}-hours" class="block text-sm font-medium text-gray-700 mb-1">Est. Hours</label>
                            <input type="text" id="project${projectCounter}-hours" name="project${projectCounter}-hours" placeholder="Estimated Hours">
                        </div>
                        <div>
                            <label for="project${projectCounter}-labor-cost" class="block text-sm font-medium text-gray-700 mb-1">Est. Labor Cost ($)</label>
                            <input type="text" id="project${projectCounter}-labor-cost" name="project${projectCounter}-labor-cost" placeholder="Estimated Labor Cost">
                        </div>
                        <div>
                            <label for="project${projectCounter}-materials-cost" class="block text-sm font-medium text-gray-700 mb-1">Est. Materials Cost ($)</label>
                            <input type="text" id="project${projectCounter}-materials-cost" name="project${projectCounter}-materials-cost" placeholder="Estimated Materials Cost">
                        </div>
                        <div>
                            <label for="project${projectCounter}-price" class="block text-sm font-medium text-gray-700 mb-1">Final Price ($)</label>
                            <input type="text" id="project${projectCounter}-price" name="project${projectCounter}-price" placeholder="Price (numbers only)">
                        </div>
                    </div>
                </div>
            `;
            newProjectDiv.innerHTML = newProjectHTML;
            projectContainer.appendChild(newProjectDiv);

            // Re-run the resize logic for all textareas, including the new one
            resizeTextareas();
        }

        document.addEventListener('DOMContentLoaded', () => {
            resizeTextareas();
        });
    </script>
</body>
</html>
