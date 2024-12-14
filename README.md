# convert-size-variants-based-on-country

    Variant Option Name should be 'Size' and values should be this format:
    
    Size:
    UK 3 | EU 36 | US 2
    UK 4 | EU 37 | US 3
    UK 5 | EU 38 | US 4


    Minified Version
    
    document.addEventListener('DOMContentLoaded',()=>{const a=document.querySelectorAll('.variant-wrapper fieldset.variant-input-wrap[name="Size"] .variant-input label');if(a){const b=document.createElement('div');b.className='size-selector';a.forEach(a=>a.dataset.originalSizes=a.innerText);['UK','EU','US'].forEach(c=>{const d=document.createElement('span');Object.assign(d.style,{cursor:'pointer',color:'#000',padding:'2px 15px',margin:'0 4px 12px',fontSize:'13px',display:'inline-block',backgroundColor:'#f8f8f8',boxShadow:'0 0 0 1px #e8e8e1'});d.textContent=c;d.setAttribute('value',c);if(c==='UK'){Object.assign(d.style,{backgroundColor:'#000',color:'#fff'});d.setAttribute('selected','true')}d.addEventListener('click',()=>e(c,d));b.appendChild(d)});document.querySelector('fieldset.variant-input-wrap').prepend(b);const e=(c,d)=>{document.querySelectorAll('.size-selector span').forEach(e=>{Object.assign(e.style,{backgroundColor:'#f8f8f8',boxShadow:'0 0 0 1px #e8e8e1',color:'#000'});e.removeAttribute('selected')});Object.assign(d.style,{backgroundColor:'#000',boxShadow:'0 0 0 2px #000',color:'#fff'});d.setAttribute('selected','true');a.forEach(a=>{const b=a.dataset.originalSizes.match(/UK (\d+) \| EU (\d+) \| US (\d+)/);if(b){const e=b[['UK','EU','US'].indexOf(c)+1];a.innerText=e}else{console.error('Size format does not match expected pattern [UK 3 | EU 36 | US 2]',a)}})};e('UK',document.querySelector('.size-selector span[value="UK"]'))}});
