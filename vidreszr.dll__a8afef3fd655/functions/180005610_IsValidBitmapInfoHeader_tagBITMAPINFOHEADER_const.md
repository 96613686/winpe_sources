# IsValidBitmapInfoHeader(tagBITMAPINFOHEADER const *)

- ea: `0x180005610`
- end: `0x1800057c3`
- name: `?IsValidBitmapInfoHeader@@YAHPEBUtagBITMAPINFOHEADER@@@Z`
- size: `435`
- prototype: `_BOOL8 __fastcall(const struct tagBITMAPINFOHEADER *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008680`
- `0x1800089b0`

## callees

- `0x180005610`

## pseudocode

```c
_BOOL8 __fastcall IsValidBitmapInfoHeader(const struct tagBITMAPINFOHEADER *a1)
{
  LONG biHeight; // edx
  LONG v3; // r9d
  LONG biWidth; // ecx
  DWORD biCompression; // eax
  int v6; // ecx
  int v7; // eax
  int biBitCount; // edx
  signed int v10; // eax

  if ( !a1 )
    return 0;
  biHeight = a1->biHeight;
  v3 = -biHeight;
  if ( biHeight > 0 )
    v3 = a1->biHeight;
  if ( a1->biSize != 40 )
    return 0;
  if ( a1->biPlanes != 1 )
    return 0;
  biWidth = a1->biWidth;
  if ( biWidth <= 0 || v3 <= 0 )
    return 0;
  biCompression = a1->biCompression;
  if ( biCompression > 0x32315659 )
  {
    if ( biCompression > 0x56555941 )
    {
      if ( biCompression == 1448433993 )
        goto LABEL_23;
      if ( biCompression != 1498831189 )
        return 1;
    }
    else
    {
      if ( biCompression == 1448433985 )
        goto LABEL_15;
      if ( biCompression != 844715353 )
      {
        if ( biCompression != 909193814 )
        {
          if ( biCompression != 1431918169 )
            return 1;
          goto LABEL_42;
        }
        if ( (biWidth & 1) != 0 )
          return 0;
LABEL_15:
        if ( biHeight <= 0 || a1->biBitCount != 32 )
          return 0;
        v6 = 32 * biWidth;
        goto LABEL_46;
      }
    }
LABEL_42:
    if ( (biWidth & 1) != 0 || biHeight <= 0 || a1->biBitCount != 16 )
      return 0;
    v6 = 16 * biWidth;
LABEL_46:
    v7 = v6 + 31;
    goto LABEL_47;
  }
  if ( biCompression == 842094169 )
    goto LABEL_23;
  if ( biCompression > 0x30323449 )
  {
    if ( biCompression == 825316942 )
    {
      if ( (biWidth & 3) != 0 || biHeight <= 0 || a1->biBitCount != 12 )
        return 0;
      v10 = 12 * biWidth;
      return a1->biSizeImage == v3 * (v10 / 8);
    }
    if ( biCompression != 842094158 )
      return 1;
LABEL_23:
    if ( (biWidth & 1) == 0 && (v3 & 1) == 0 && biHeight > 0 && a1->biBitCount == 12 )
      return a1->biSizeImage == v3 * (12 * biWidth / 8);
    return 0;
  }
  switch ( biCompression )
  {
    case 0x30323449u:
      goto LABEL_23;
    case 0u:
      biBitCount = a1->biBitCount;
      if ( (((_WORD)biBitCount - 8) & 0xFFE7) != 0 )
        return 0;
      v7 = biWidth * biBitCount + 31;
      goto LABEL_47;
    case 3u:
      v7 = biWidth * a1->biBitCount + 31;
LABEL_47:
      v10 = v7 & 0xFFFFFFE1;
      return a1->biSizeImage == v3 * (v10 / 8);
    case 0x30313456u:
      goto LABEL_15;
  }
  return 1;
}

```

## disassembly

```asm
0x180005610  mov     r8, rcx
0x180005613  test    rcx, rcx
0x180005616  jz      loc_180005779
0x18000561c  mov     edx, [rcx+8]
0x18000561f  mov     r9d, edx
0x180005622  neg     r9d
0x180005625  cmovs   r9d, edx
0x180005629  cmp     dword ptr [rcx], 28h ; '('
0x18000562c  jnz     loc_180005779
0x180005632  mov     r11d, 1
0x180005638  cmp     r11w, [rcx+0Ch]
0x18000563d  jnz     loc_180005779
0x180005643  mov     ecx, [rcx+4]
0x180005646  test    ecx, ecx
0x180005648  jle     loc_180005779
0x18000564e  test    r9d, r9d
0x180005651  jle     loc_180005779
0x180005657  mov     eax, [r8+10h]
0x18000565b  cmp     eax, 32315659h
0x180005660  ja      loc_18000574A
0x180005666  jz      loc_1800056F0
0x18000566c  cmp     eax, 30323449h
0x180005671  ja      short loc_1800056DE
0x180005673  jz      short loc_1800056F0
0x180005675  test    eax, eax
0x180005677  jz      short loc_1800056B9
0x180005679  cmp     eax, 3
0x18000567c  jz      short loc_1800056A9
0x18000567e  cmp     eax, 30313456h
0x180005683  jnz     loc_1800057BF
0x180005689  test    edx, edx
0x18000568b  jle     loc_180005779
0x180005691  mov     eax, 20h ; ' '
0x180005696  cmp     ax, [r8+0Eh]
0x18000569b  jnz     loc_180005779
0x1800056a1  shl     ecx, 5
0x1800056a4  jmp     loc_1800057A6
0x1800056a9  movzx   eax, word ptr [r8+0Eh]
0x1800056ae  imul    eax, ecx
0x1800056b1  add     eax, 1Fh
0x1800056b4  jmp     loc_1800057A9
0x1800056b9  movzx   edx, word ptr [r8+0Eh]
0x1800056be  mov     r10d, 0FFE7h
0x1800056c4  lea     eax, [rdx-8]
0x1800056c7  test    r10w, ax
0x1800056cb  jnz     loc_180005779
0x1800056d1  mov     eax, edx
0x1800056d3  imul    eax, ecx
0x1800056d6  add     eax, 1Fh
0x1800056d9  jmp     loc_1800057A9
0x1800056de  cmp     eax, 3131564Eh
0x1800056e3  jz      short loc_18000572D
0x1800056e5  cmp     eax, 3231564Eh
0x1800056ea  jnz     loc_1800057BF
0x1800056f0  test    r11b, cl
0x1800056f3  jnz     loc_180005779
0x1800056f9  test    r11b, r9b
0x1800056fc  jnz     short loc_180005779
0x1800056fe  test    edx, edx
0x180005700  jle     short loc_180005779
0x180005702  mov     eax, 0Ch
0x180005707  cmp     ax, [r8+0Eh]
0x18000570c  jnz     short loc_180005779
0x18000570e  lea     eax, [rcx+rcx*2]
0x180005711  xor     ecx, ecx
0x180005713  shl     eax, 2
0x180005716  cdq
0x180005717  and     edx, 7
0x18000571a  add     eax, edx
0x18000571c  sar     eax, 3
0x18000571f  imul    eax, r9d
0x180005723  cmp     [r8+14h], eax
0x180005727  setz    cl
0x18000572a  mov     eax, ecx
0x18000572c  retn
0x18000572d  test    cl, 3
0x180005730  jnz     short loc_180005779
0x180005732  test    edx, edx
0x180005734  jle     short loc_180005779
0x180005736  mov     eax, 0Ch
0x18000573b  cmp     ax, [r8+0Eh]
0x180005740  jnz     short loc_180005779
0x180005742  lea     eax, [rcx+rcx*2]
0x180005745  shl     eax, 2
0x180005748  jmp     short loc_1800057AC
0x18000574a  cmp     eax, 56555941h
0x18000574f  ja      short loc_18000577C
0x180005751  jz      loc_180005689
0x180005757  cmp     eax, 32595559h
0x18000575c  jz      short loc_18000578E
0x18000575e  cmp     eax, 36313256h
0x180005763  jz      short loc_180005770
0x180005765  cmp     eax, 55595659h
0x18000576a  jz      short loc_18000578E
0x18000576c  mov     eax, r11d
0x18000576f  retn
0x180005770  test    r11b, cl
0x180005773  jz      loc_180005689
0x180005779  xor     eax, eax
0x18000577b  retn
0x18000577c  cmp     eax, 56555949h
0x180005781  jz      loc_1800056F0
0x180005787  cmp     eax, 59565955h
0x18000578c  jnz     short loc_1800057BF
0x18000578e  test    r11b, cl
0x180005791  jnz     short loc_180005779
0x180005793  test    edx, edx
0x180005795  jle     short loc_180005779
0x180005797  mov     eax, 10h
0x18000579c  cmp     ax, [r8+0Eh]
0x1800057a1  jnz     short loc_180005779
0x1800057a3  shl     ecx, 4
0x1800057a6  lea     eax, [rcx+1Fh]
0x1800057a9  and     eax, 0FFFFFFE1h
0x1800057ac  cdq
0x1800057ad  and     edx, 7
0x1800057b0  add     eax, edx
0x1800057b2  sar     eax, 3
0x1800057b5  imul    eax, r9d
0x1800057b9  cmp     [r8+14h], eax
0x1800057bd  jnz     short loc_180005779
0x1800057bf  mov     eax, r11d
0x1800057c2  retn
```
