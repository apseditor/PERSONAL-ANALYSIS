<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>✨ Color Analysis Studio - AI-Powered Personal Color & Style Analysis</title>
    <script crossorigin src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/lucide@latest"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen', 'Ubuntu', 'Cantarell', sans-serif;
        }
        
        .serif-heading {
            font-family: Georgia, 'Times New Roman', serif;
        }
        
        .color-swatch {
            transition: transform 0.3s ease;
        }
        
        .color-swatch:hover {
            transform: scale(1.05);
        }
        
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(10px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .fade-in {
            animation: fadeIn 0.5s ease forwards;
        }
        
        .gradient-bg {
            background: linear-gradient(135deg, #faf9f7 0%, #ffffff 50%, #f0ebe5 100%);
        }
        
        @media (prefers-reduced-motion: reduce) {
            * {
                animation-duration: 0.01ms !important;
                animation-iteration-count: 1 !important;
                transition-duration: 0.01ms !important;
            }
        }
    </style>
</head>
<body class="gradient-bg">
    <div id="root"></div>

    <script type="text/babel">
        const { useState, useRef } = React;
        const { Upload, X, Loader, Download } = lucide;

        function ColorAnalysisApp() {
            const [selectedImage, setSelectedImage] = useState(null);
            const [preview, setPreview] = useState(null);
            const [loading, setLoading] = useState(false);
            const [analysis, setAnalysis] = useState(null);
            const [error, setError] = useState(null);
            const fileInputRef = useRef(null);

            const handleImageUpload = (e) => {
                const file = e.target.files?.[0];
                if (file) {
                    setError(null);
                    setSelectedImage(file);
                    const reader = new FileReader();
                    reader.onload = (e) => setPreview(e.target?.result);
                    reader.readAsDataURL(file);
                }
            };

            const analyzeImage = async () => {
                if (!selectedImage) return;
                
                setLoading(true);
                setError(null);

                try {
                    const reader = new FileReader();
                    reader.onload = async (e) => {
                        const base64Image = e.target?.result?.split(',')[1];
                        
                        try {
                            const response = await fetch('https://api.anthropic.com/v1/messages', {
                                method: 'POST',
                                headers: {
                                    'Content-Type': 'application/json',
                                },
                                body: JSON.stringify({
                                    model: 'claude-sonnet-4-6',
                                    max_tokens: 2000,
                                    messages: [
                                        {
                                            role: 'user',
                                            content: [
                                                {
                                                    type: 'image',
                                                    source: {
                                                        type: 'base64',
                                                        media_type: 'image/jpeg',
                                                        data: base64Image,
                                                    },
                                                },
                                                {
                                                    type: 'text',
                                                    text: `Analyze this portrait and provide a comprehensive personal color analysis and styling guide. Return ONLY valid JSON (no markdown, no code blocks) with this exact structure:
{
  "colorPalette": {
    "season": "string (e.g., 'Warm Autumn')",
    "undertone": "string (e.g., 'Warm/Golden')",
    "contrast": "string (e.g., 'Medium')",
    "colors": [
      {"name": "string", "hex": "#XXXXXX", "usage": "string description"}
    ]
  },
  "recommendations": {
    "bodyType": {
      "type": "string",
      "flattering_silhouettes": ["string"],
      "fabrics_to_wear": ["string"],
      "cuts_to_avoid": ["string"]
    },
    "hairstyle": {
      "recommended": ["string"],
      "colors_to_consider": ["string"],
      "avoid": ["string"]
    },
    "makeup": {
      "foundation_tone": "string",
      "eyeshadow_colors": ["string"],
      "lip_colors": ["string"],
      "blush_tone": "string"
    },
    "dress_code": {
      "casual": ["string"],
      "professional": ["string"],
      "evening": ["string"]
    }
  },
  "personalInsights": {
    "key_strength": "string",
    "styling_tip": "string",
    "color_combinations": ["string"]
  }
}`
                                                }
                                            ],
                                        },
                                    ],
                                }),
                            });

                            if (!response.ok) {
                                const errorData = await response.json();
                                throw new Error(errorData.error?.message || 'API request failed');
                            }

                            const data = await response.json();
                            const textContent = data.content[0].text;
                            
                            const analysisData = JSON.parse(textContent);
                            setAnalysis(analysisData);
                        } catch (err) {
                            setError(err.message || 'Failed to analyze image. Please ensure you have set up your Anthropic API key.');
                        } finally {
                            setLoading(false);
                        }
                    };
                    reader.readAsDataURL(selectedImage);
                } catch (err) {
                    setError('Error processing image. Please try again.');
                    setLoading(false);
                }
            };

            const downloadReport = () => {
                if (!analysis) return;
                
                const reportHTML = `
<!DOCTYPE html>
<html>
<head>
  <title>Color Analysis Report</title>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body { 
      font-family: Georgia, serif; 
      max-width: 900px; 
      margin: 0 auto; 
      padding: 40px 20px; 
      background: linear-gradient(135deg, #faf9f7 0%, #f0ebe5 100%);
      color: #1a2332;
      line-height: 1.6;
    }
    h1 { 
      text-align: center;
      font-size: 2.5em;
      margin-bottom: 40px;
      color: #1a2332;
      border-bottom: 3px solid #d4a574;
      padding-bottom: 20px;
    }
    h2 { 
      color: #1a2332; 
      border-bottom: 2px solid #d4a574; 
      padding-bottom: 12px;
      margin-top: 30px;
      margin-bottom: 20px;
      font-size: 1.8em;
    }
    h3 { 
      color: #1a2332; 
      margin-top: 20px;
      margin-bottom: 15px;
      font-size: 1.3em;
    }
    .section { 
      background: white; 
      padding: 30px; 
      margin: 25px 0; 
      border-radius: 12px; 
      box-shadow: 0 4px 15px rgba(0,0,0,0.08);
      border: 1px solid #e0dbd6;
    }
    .color-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 20px;
      margin: 20px 0;
    }
    .color-item {
      text-align: center;
    }
    .color-swatch { 
      width: 100%;
      aspect-ratio: 1;
      border-radius: 8px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.15);
      margin-bottom: 12px;
      border: 2px solid #fff;
    }
    .color-name {
      font-weight: bold;
      color: #1a2332;
      margin-bottom: 5px;
    }
    .color-code {
      font-family: 'Courier New', monospace;
      color: #a89ba8;
      font-size: 0.9em;
    }
    ul { 
      list-style: none; 
      padding-left: 0;
      margin: 15px 0;
    }
    li { 
      padding: 10px 0;
      border-bottom: 1px solid #f0ebe5;
    }
    li:last-child {
      border-bottom: none;
    }
    li:before { 
      content: "✓ "; 
      color: #d4a574; 
      font-weight: bold; 
      margin-right: 10px;
    }
    .info-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 20px;
      margin: 20px 0;
    }
    .info-box {
      background: #faf9f7;
      padding: 20px;
      border-radius: 8px;
      border-left: 4px solid #d4a574;
    }
    .info-label {
      color: #a89ba8;
      font-size: 0.85em;
      text-transform: uppercase;
      letter-spacing: 1px;
      margin-bottom: 8px;
    }
    .info-value {
      color: #1a2332;
      font-weight: 500;
      font-size: 1.1em;
    }
    .insights {
      background: linear-gradient(135deg, #faf9f7 0%, #ffffff 100%);
      border: 2px solid #d4a574;
    }
    @media print {
      body { background: white; }
      .section { box-shadow: none; }
    }
  </style>
</head>
<body>
  <h1>✨ Your Personal Color Analysis Report</h1>
  
  <div class="section">
    <h2>Color Season: ${analysis.colorPalette.season}</h2>
    <div class="info-grid">
      <div class="info-box">
        <div class="info-label">Undertone</div>
        <div class="info-value">${analysis.colorPalette.undertone}</div>
      </div>
      <div class="info-box">
        <div class="info-label">Contrast Level</div>
        <div class="info-value">${analysis.colorPalette.contrast}</div>
      </div>
    </div>
    <h3>Your Color Palette</h3>
    <div class="color-grid">
      ${analysis.colorPalette.colors.map(color => \`
        <div class="color-item">
          <div class="color-swatch" style="background-color: \${color.hex};"></div>
          <div class="color-name">\${color.name}</div>
          <div class="color-code">\${color.hex}</div>
          <p style="font-size: 0.85em; color: #a89ba8; margin-top: 8px;">\${color.usage}</p>
        </div>
      \`).join('')}
    </div>
  </div>

  <div class="section">
    <h2>Body Type & Silhouettes</h2>
    <div class="info-box" style="margin-bottom: 20px;">
      <div class="info-label">Body Type</div>
      <div class="info-value">${analysis.recommendations.bodyType.type}</div>
    </div>
    <h3>Flattering Silhouettes</h3>
    <ul>${analysis.recommendations.bodyType.flattering_silhouettes.map(s => \`<li>\${s}</li>\`).join('')}</ul>
    <h3>Recommended Fabrics</h3>
    <ul>${analysis.recommendations.bodyType.fabrics_to_wear.map(f => \`<li>\${f}</li>\`).join('')}</ul>
    <h3>Cuts to Avoid</h3>
    <ul>${analysis.recommendations.bodyType.cuts_to_avoid.map(c => \`<li>\${c}</li>\`).join('')}</ul>
  </div>

  <div class="section">
    <h2>Hairstyle Recommendations</h2>
    <h3>Recommended Styles</h3>
    <ul>${analysis.recommendations.hairstyle.recommended.map(h => \`<li>\${h}</li>\`).join('')}</ul>
    <h3>Hair Colors to Consider</h3>
    <ul>${analysis.recommendations.hairstyle.colors_to_consider.map(c => \`<li>\${c}</li>\`).join('')}</ul>
    <h3>Styles to Avoid</h3>
    <ul>${analysis.recommendations.hairstyle.avoid.map(a => \`<li>\${a}</li>\`).join('')}</ul>
  </div>

  <div class="section">
    <h2>Makeup Recommendations</h2>
    <div class="info-grid">
      <div class="info-box">
        <div class="info-label">Foundation Tone</div>
        <div class="info-value">${analysis.recommendations.makeup.foundation_tone}</div>
      </div>
      <div class="info-box">
        <div class="info-label">Blush Tone</div>
        <div class="info-value">${analysis.recommendations.makeup.blush_tone}</div>
      </div>
    </div>
    <h3>Eyeshadow Colors</h3>
    <ul>${analysis.recommendations.makeup.eyeshadow_colors.map(e => \`<li>\${e}</li>\`).join('')}</ul>
    <h3>Lip Colors</h3>
    <ul>${analysis.recommendations.makeup.lip_colors.map(l => \`<li>\${l}</li>\`).join('')}</ul>
  </div>

  <div class="section">
    <h2>Dress Code Guide</h2>
    <h3>Casual Wear</h3>
    <ul>${analysis.recommendations.dress_code.casual.map(c => \`<li>\${c}</li>\`).join('')}</ul>
    <h3>Professional Wear</h3>
    <ul>${analysis.recommendations.dress_code.professional.map(p => \`<li>\${p}</li>\`).join('')}</ul>
    <h3>Evening Wear</h3>
    <ul>${analysis.recommendations.dress_code.evening.map(e => \`<li>\${e}</li>\`).join('')}</ul>
  </div>

  <div class="section insights">
    <h2>✨ Personal Styling Insights</h2>
    <div class="info-box">
      <div class="info-label">Key Strength</div>
      <div class="info-value">${analysis.personalInsights.key_strength}</div>
    </div>
    <div style="margin-top: 20px;">
      <div class="info-label">Styling Tip</div>
      <p style="color: #1a2332; margin-top: 10px;">${analysis.personalInsights.styling_tip}</p>
    </div>
    <h3>Color Combinations That Work</h3>
    <ul>${analysis.personalInsights.color_combinations.map(cc => \`<li>\${cc}</li>\`).join('')}</ul>
  </div>
</body>
</html>
                `;

                const blob = new Blob([reportHTML], { type: 'text/html' });
                const url = URL.createObjectURL(blob);
                const a = document.createElement('a');
                a.href = url;
                a.download = 'color-analysis-report.html';
                a.click();
                URL.revokeObjectURL(url);
            };

            if (!analysis) {
                return (
                    <div className="min-h-screen gradient-bg">
                        {/* Header */}
                        <header className="border-b border-[#e0dbd6] bg-white/80 backdrop-blur-sm sticky top-0 z-50">
                            <div className="max-w-6xl mx-auto px-4 sm:px-6 py-6">
                                <h1 className="text-3xl sm:text-4xl serif-heading text-[#1a2332] tracking-tight">
                                    ✨ Color Analysis Studio
                                </h1>
                                <p className="text-[#a89ba8] mt-1 text-sm sm:text-base">
                                    Discover your perfect color palette & personal style
                                </p>
                            </div>
                        </header>

                        {/* Main Content */}
                        <main className="max-w-6xl mx-auto px-4 sm:px-6 py-12">
                            {/* Upload Section */}
                            <div className="bg-white rounded-lg shadow-lg border border-[#e0dbd6] overflow-hidden mb-8">
                                <div className="p-8 sm:p-12">
                                    <div
                                        onClick={() => fileInputRef.current?.click()}
                                        className="relative border-2 border-dashed border-[#d4a574] rounded-lg p-12 sm:p-16 text-center cursor-pointer transition-all hover:border-[#c49565] hover:bg-[#faf9f7]"
                                    >
                                        <input
                                            ref={fileInputRef}
                                            type="file"
                                            accept="image/*"
                                            onChange={handleImageUpload}
                                            className="hidden"
                                        />
                                        
                                        {preview ? (
                                            <div className="space-y-4">
                                                <img src={preview} alt="Preview" className="h-64 w-64 object-cover mx-auto rounded-lg shadow-md" />
                                                <button
                                                    onClick={(e) => {
                                                        e.stopPropagation();
                                                        setPreview(null);
                                                        setSelectedImage(null);
                                                    }}
                                                    className="inline-flex items-center gap-2 px-4 py-2 bg-red-50 text-red-600 rounded-lg hover:bg-red-100 transition-colors"
                                                >
                                                    ✕ Remove Image
                                                </button>
                                            </div>
                                        ) : (
                                            <div className="space-y-4">
                                                <div className="inline-block p-4 bg-[#faf9f7] rounded-lg mb-4">
                                                    <span style={{ fontSize: '40px' }}>📸</span>
                                                </div>
                                                <h3 className="text-xl sm:text-2xl serif-heading text-[#1a2332]">
                                                    Upload Your Portrait
                                                </h3>
                                                <p className="text-[#a89ba8] text-sm sm:text-base">
                                                    Choose a clear, well-lit headshot for the most accurate analysis
                                                </p>
                                                <p className="text-xs text-[#a89ba8] mt-2">
                                                    JPG, PNG or WebP • Max 10MB
                                                </p>
                                            </div>
                                        )}
                                    </div>
                                </div>

                                {/* Action Button */}
                                {selectedImage && !loading && (
                                    <div className="px-8 sm:px-12 pb-8">
                                        <button
                                            onClick={analyzeImage}
                                            disabled={loading}
                                            className="w-full bg-[#1a2332] text-white py-3 sm:py-4 rounded-lg font-semibold hover:bg-[#2a3442] transition-colors disabled:opacity-50"
                                        >
                                            Analyze My Colors
                                        </button>
                                    </div>
                                )}

                                {/* Loading State */}
                                {loading && (
                                    <div className="px-8 sm:px-12 pb-8">
                                        <div className="flex items-center justify-center gap-3 py-8">
                                            <span style={{ fontSize: '24px', animation: 'spin 2s linear infinite' }}>⏳</span>
                                            <p className="text-[#a89ba8] font-medium">
                                                Analyzing your color palette...
                                            </p>
                                        </div>
                                    </div>
                                )}

                                {/* Error State */}
                                {error && (
                                    <div className="px-8 sm:px-12 pb-8 bg-red-50 border-t border-red-200">
                                        <p className="text-red-600 font-medium">⚠️ Error: {error}</p>
                                        <p className="text-red-500 text-sm mt-2">
                                            Please try again with a different image
                                        </p>
                                    </div>
                                )}
                            </div>

                            {/* Info Section */}
                            <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
                                {[
                                    {
                                        title: "Color Palette",
                                        description: "Discover your seasonal color classification and undertone"
                                    },
                                    {
                                        title: "Style Guide",
                                        description: "Get personalized recommendations for body type and silhouettes"
                                    },
                                    {
                                        title: "Complete Analysis",
                                        description: "Hair, makeup, and outfit recommendations tailored to you"
                                    }
                                ].map((item, idx) => (
                                    <div key={idx} className="bg-white rounded-lg p-6 border border-[#e0dbd6]">
                                        <h3 className="serif-heading text-lg text-[#1a2332] mb-2">{item.title}</h3>
                                        <p className="text-[#a89ba8] text-sm">{item.description}</p>
                                    </div>
                                ))}
                            </div>
                        </main>

                        {/* Footer */}
                        <footer className="border-t border-[#e0dbd6] bg-white/50 py-8 mt-12">
                            <div className="max-w-6xl mx-auto px-4 sm:px-6 text-center text-[#a89ba8] text-sm">
                                <p>✨ Personal Color Analysis Studio powered by AI</p>
                                <p className="mt-2">Upload a clear, well-lit headshot for the most accurate analysis</p>
                            </div>
                        </footer>
                    </div>
                );
            }

            // Results View
            return (
                <div className="min-h-screen gradient-bg">
                    {/* Header */}
                    <header className="border-b border-[#e0dbd6] bg-white/80 backdrop-blur-sm sticky top-0 z-50">
                        <div className="max-w-6xl mx-auto px-4 sm:px-6 py-6">
                            <button
                                onClick={() => setAnalysis(null)}
                                className="text-[#d4a574] hover:text-[#c49565] font-medium text-sm mb-2"
                            >
                                ← Start New Analysis
                            </button>
                            <h1 className="text-3xl sm:text-4xl serif-heading text-[#1a2332]">Your Color Analysis</h1>
                            <p className="text-[#a89ba8] mt-1">Personalized recommendations based on your unique features</p>
                        </div>
                    </header>

                    <main className="max-w-6xl mx-auto px-4 sm:px-6 py-12">
                        {/* Color Palette Section */}
                        <div className="bg-white rounded-lg shadow-lg border border-[#e0dbd6] p-8 mb-8">
                            <h2 className="text-3xl serif-heading text-[#1a2332] mb-6">
                                {analysis.colorPalette.season}
                            </h2>
                            
                            <div className="grid grid-cols-2 sm:grid-cols-4 gap-4 text-sm mb-8">
                                <div>
                                    <p className="text-[#a89ba8] text-xs uppercase tracking-wide mb-1">Undertone</p>
                                    <p className="text-[#1a2332] font-medium">{analysis.colorPalette.undertone}</p>
                                </div>
                                <div>
                                    <p className="text-[#a89ba8] text-xs uppercase tracking-wide mb-1">Contrast</p>
                                    <p className="text-[#1a2332] font-medium">{analysis.colorPalette.contrast}</p>
                                </div>
                            </div>

                            {/* Color Swatches */}
                            <h3 className="font-semibold text-[#1a2332] mb-6 text-lg">Your Color Palette</h3>
                            <div className="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-4 gap-4">
                                {analysis.colorPalette.colors.map((color, idx) => (
                                    <div key={idx} className="group cursor-pointer">
                                        <div
                                            className="w-full aspect-square rounded-lg shadow-md mb-3 transition-transform group-hover:scale-105 border-2 border-white color-swatch"
                                            style={{ backgroundColor: color.hex }}
                                            title={color.name}
                                        />
                                        <p className="font-medium text-[#1a2332] text-sm">{color.name}</p>
                                        <p className="text-xs text-[#a89ba8] font-mono mt-1">{color.hex}</p>
                                        <p className="text-xs text-[#a89ba8] mt-2">{color.usage}</p>
                                    </div>
                                ))}
                            </div>
                        </div>

                        {/* Body Type Section */}
                        <div className="bg-white rounded-lg shadow-lg border border-[#e0dbd6] p-8 mb-8">
                            <h2 className="text-2xl serif-heading text-[#1a2332] mb-6">
                                Body Type & Silhouettes
                            </h2>
                            <p className="text-sm text-[#a89ba8] uppercase tracking-wide mb-2">Your Type</p>
                            <p className="text-xl text-[#1a2332] font-medium mb-6">{analysis.recommendations.bodyType.type}</p>

                            <div className="grid grid-cols-1 md:grid-cols-2 gap-8">
                                <div>
                                    <h4 className="font-semibold text-[#1a2332] mb-4">Flattering Silhouettes</h4>
                                    <ul className="space-y-2">
                                        {analysis.recommendations.bodyType.flattering_silhouettes.map((item, idx) => (
                                            <li key={idx} className="flex gap-3">
                                                <span className="text-[#d4a574] font-bold">→</span>
                                                <span className="text-[#1a2332]">{item}</span>
                                            </li>
                                        ))}
                                    </ul>
                                </div>
                                <div>
                                    <h4 className="font-semibold text-[#1a2332] mb-4">Recommended Fabrics</h4>
                                    <ul className="space-y-2">
                                        {analysis.recommendations.bodyType.fabrics_to_wear.map((item, idx) => (
                                            <li key={idx} className="flex gap-3">
                                                <span className="text-[#d4a574] font-bold">→</span>
                                                <span className="text-[#1a2332]">{item}</span>
                                            </li>
                                        ))}
                                    </ul>
                                </div>
                            </div>
                        </div>

                        {/* Hairstyle Section */}
                        <div className="bg-white rounded-lg shadow-lg border border-[#e0dbd6] p-8 mb-8">
                            <h2 className="text-2xl serif-heading text-[#1a2332] mb-6">
                                Hairstyle Recommendations
                            </h2>
                            <div className="grid grid-cols-1 md:grid-cols-2 gap-8">
                                <div>
                                    <h4 className="font-semibold text-[#1a2332] mb-4">Recommended Styles</h4>
                                    <ul className="space-y-2">
                                        {analysis.recommendations.hairstyle.recommended.map((item, idx) => (
                                            <li key={idx} className="flex gap-3">
                                                <span className="text-[#d4a574] font-bold">→</span>
                                                <span className="text-[#1a2332]">{item}</span>
                                            </li>
                                        ))}
                                    </ul>
                                </div>
                                <div>
                                    <h4 className="font-semibold text-[#1a2332] mb-4">Hair Colors to Consider</h4>
                                    <ul className="space-y-2">
                                        {analysis.recommendations.hairstyle.colors_to_consider.map((item, idx) => (
                                            <li key={idx} className="flex gap-3">
                                                <span className="text-[#d4a574] font-bold">→</span>
                                                <span className="text-[#1a2332]">{item}</span>
                                            </li>
                                        ))}
                                    </ul>
                                </div>
                            </div>
                        </div>

                        {/* Makeup Section */}
                        <div className="bg-white rounded-lg shadow-lg border border-[#e0dbd6] p-8 mb-8">
                            <h2 className="text-2xl serif-heading text-[#1a2332] mb-6">
                                Makeup Recommendations
                            </h2>
                            <div className="grid grid-cols-1 md:grid-cols-2 gap-8">
                                <div>
                                    <div className="mb-6">
                                        <p className="text-sm text-[#a89ba8] uppercase tracking-wide mb-2">Foundation Tone</p>
                                        <p className="text-lg text-[#1a2332] font-medium">{analysis.recommendations.makeup.foundation_tone}</p>
                                    </div>
                                    <div>
                                        <p className="text-sm text-[#a89ba8] uppercase tracking-wide mb-2">Blush Tone</p>
                                        <p className="text-lg text-[#1a2332] font-medium">{analysis.recommendations.makeup.blush_tone}</p>
                                    </div>
                                </div>
                                <div>
                                    <div className="mb-6">
                                        <h4 className="font-semibold text-[#1a2332] mb-3">Eyeshadow Colors</h4>
                                        <ul className="space-y-2">
                                            {analysis.recommendations.makeup.eyeshadow_colors.map((item, idx) => (
                                                <li key={idx} className="flex gap-3">
                                                    <span className="text-[#d4a574] font-bold">→</span>
                                                    <span className="text-[#1a2332]">{item}</span>
                                                </li>
                                            ))}
                                        </ul>
                                    </div>
                                    <div>
                                        <h4 className="font-semibold text-[#1a2332] mb-3">Lip Colors</h4>
                                        <ul className="space-y-2">
                                            {analysis.recommendations.makeup.lip_colors.map((item, idx) => (
                                                <li key={idx} className="flex gap-3">
                                                    <span className="text-[#d4a574] font-bold">→</span>
                                                    <span className="text-[#1a2332]">{item}</span>
                                                </li>
                                            ))}
                                        </ul>
                                    </div>
                                </div>
                            </div>
                        </div>

                        {/* Dress Code Section */}
                        <div className="bg-white rounded-lg shadow-lg border border-[#e0dbd6] p-8 mb-8">
                            <h2 className="text-2xl serif-heading text-[#1a2332] mb-6">
                                Dress Code Guide
                            </h2>
                            <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
                                {[
                                    { label: 'Casual', key: 'casual' },
                                    { label: 'Professional', key: 'professional' },
                                    { label: 'Evening', key: 'evening' }
                                ].map((category) => (
                                    <div key={category.key}>
                                        <h4 className="font-semibold text-[#1a2332] mb-4">{category.label}</h4>
                                        <ul className="space-y-2">
                                            {analysis.recommendations.dress_code[category.key].map((item, idx) => (
                                                <li key={idx} className="flex gap-3">
                                                    <span className="text-[#d4a574] font-bold">→</span>
                                                    <span className="text-[#1a2332] text-sm">{item}</span>
                                                </li>
                                            ))}
                                        </ul>
                                    </div>
                                ))}
                            </div>
                        </div>

                        {/* Personal Insights */}
                        <div className="bg-gradient-to-br from-[#faf9f7] to-white rounded-lg shadow-lg border border-[#e0dbd6] p-8 mb-12">
                            <h2 className="text-2xl serif-heading text-[#1a2332] mb-6">
                                ✨ Personal Styling Insights
                            </h2>
                            <div className="space-y-6">
                                <div className="bg-white rounded-lg p-6 border border-[#d4a574]/30">
                                    <p className="text-sm text-[#a89ba8] uppercase tracking-wide mb-2">Key Strength</p>
                                    <p className="text-lg text-[#1a2332] font-medium">{analysis.personalInsights.key_strength}</p>
                                </div>
                                <div className="bg-white rounded-lg p-6 border border-[#d4a574]/30">
                                    <p className="text-sm text-[#a89ba8] uppercase tracking-wide mb-2">Styling Tip</p>
                                    <p className="text-lg text-[#1a2332]">{analysis.personalInsights.styling_tip}</p>
                                </div>
                                <div className="bg-white rounded-lg p-6 border border-[#d4a574]/30">
                                    <p className="text-sm text-[#a89ba8] uppercase tracking-wide mb-3">Color Combinations</p>
                                    <ul className="space-y-2">
                                        {analysis.personalInsights.color_combinations.map((combo, idx) => (
                                            <li key={idx} className="flex gap-3">
                                                <span className="text-[#d4a574] font-bold">→</span>
                                                <span className="text-[#1a2332]">{combo}</span>
                                            </li>
                                        ))}
                                    </ul>
                                </div>
                            </div>
                        </div>

                        {/* Action Buttons */}
                        <div className="flex flex-col sm:flex-row gap-4 mb-12">
                            <button
                                onClick={downloadReport}
                                className="flex items-center justify-center gap-2 px-6 py-3 bg-[#1a2332] text-white rounded-lg hover:bg-[#2a3442] transition-colors font-medium flex-1"
                            >
                                📥 Download Report
                            </button>
                            <button
                                onClick={() => setAnalysis(null)}
                                className="flex items-center justify-center gap-2 px-6 py-3 border-2 border-[#d4a574] text-[#1a2332] rounded-lg hover:bg-[#faf9f7] transition-colors font-medium flex-1"
                            >
                                📸 Analyze Another Photo
                            </button>
                        </div>
                    </main>

                    {/* Footer */}
                    <footer className="border-t border-[#e0dbd6] bg-white/50 py-8">
                        <div className="max-w-6xl mx-auto px-4 sm:px-6 text-center text-[#a89ba8] text-sm">
                            <p>✨ Personal Color Analysis Studio powered by AI</p>
                            <p className="mt-2">Your personalized style guide created with advanced AI analysis</p>
                        </div>
                    </footer>
                </div>
            );
        }

        ReactDOM.render(<ColorAnalysisApp />, document.getElementById('root'));
    </script>
</body>
</html>