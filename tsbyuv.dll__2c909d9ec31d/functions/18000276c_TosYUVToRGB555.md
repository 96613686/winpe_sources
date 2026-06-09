# TosYUVToRGB555

- ea: `0x18000276c`
- end: `0x180002837`
- name: `TosYUVToRGB555`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000263c`

## callees

- `0x18000276c`

## pseudocode

```c
__int16 __fastcall TosYUVToRGB555(int a1, int a2, int a3)
{
  int v3; // r10d
  int v4; // eax
  char v5; // r9
  int v6; // eax
  char v7; // cl
  int v8; // eax

  v3 = 1192 * a1;
  v4 = (1192 * a1 + 1635 * a3 - 228361) / 1024;
  v5 = v4;
  if ( v4 > 255 )
  {
    v5 = -1;
  }
  else if ( v4 < 0 )
  {
    v5 = 0;
  }
  v6 = (-402 * a2 - 833 * a3 + v3 + 138908) / 1024;
  v7 = v6;
  if ( v6 > 255 )
  {
    v7 = -1;
  }
  else if ( v6 < 0 )
  {
    v7 = 0;
  }
  v8 = (v3 + 2067 * a2 - 283629) / 1024;
  if ( v8 > 255 )
  {
    v8 = 255;
  }
  else if ( v8 < 0 )
  {
    v8 = 0;
  }
  return (4 * (v7 & 0xF8 | (32 * (v5 & 0xF8)))) | (v8 >> 3) & 0x1F;
}

```

## disassembly

```asm
0x18000276c  mov     [rsp+arg_0], rbx
0x180002771  imul    eax, r8d, 663h
0x180002778  mov     r11d, edx
0x18000277b  imul    r10d, ecx, 4A8h
0x180002782  mov     ebx, 0FFh
0x180002787  add     eax, 0FFFC83F7h
0x18000278c  add     eax, r10d
0x18000278f  cdq
0x180002790  and     edx, 3FFh
0x180002796  add     eax, edx
0x180002798  sar     eax, 0Ah
0x18000279b  mov     r9d, eax
0x18000279e  cmp     eax, ebx
0x1800027a0  jg      short loc_1800027AB
0x1800027a2  test    eax, eax
0x1800027a4  jns     short loc_1800027AE
0x1800027a6  xor     r9d, r9d
0x1800027a9  jmp     short loc_1800027AE
0x1800027ab  mov     r9d, ebx
0x1800027ae  imul    eax, r8d, 341h
0x1800027b5  imul    ecx, r11d, 0FFFFFE6Eh
0x1800027bc  sub     ecx, eax
0x1800027be  lea     eax, [r10+21E9Ch]
0x1800027c5  add     eax, ecx
0x1800027c7  cdq
0x1800027c8  and     edx, 3FFh
0x1800027ce  add     eax, edx
0x1800027d0  sar     eax, 0Ah
0x1800027d3  mov     ecx, eax
0x1800027d5  cmp     eax, ebx
0x1800027d7  jg      short loc_1800027E1
0x1800027d9  test    eax, eax
0x1800027db  jns     short loc_1800027E3
0x1800027dd  xor     ecx, ecx
0x1800027df  jmp     short loc_1800027E3
0x1800027e1  mov     ecx, ebx
0x1800027e3  imul    eax, r11d, 813h
0x1800027ea  add     eax, 0FFFBAC13h
0x1800027ef  add     eax, r10d
0x1800027f2  cdq
0x1800027f3  and     edx, 3FFh
0x1800027f9  add     eax, edx
0x1800027fb  sar     eax, 0Ah
0x1800027fe  cmp     eax, ebx
0x180002800  jg      short loc_18000280A
0x180002802  test    eax, eax
0x180002804  jns     short loc_18000280C
0x180002806  xor     eax, eax
0x180002808  jmp     short loc_18000280C
0x18000280a  mov     eax, ebx
0x18000280c  mov     rbx, [rsp+arg_0]
0x180002811  mov     edx, 0F8h
0x180002816  and     r9w, dx
0x18000281a  sar     eax, 3
0x18000281d  shl     r9w, 5
0x180002822  and     cx, dx
0x180002825  or      r9w, cx
0x180002829  and     ax, 1Fh
0x18000282d  shl     r9w, 2
0x180002832  or      ax, r9w
0x180002836  retn
```
