# AlphaFillRegion(HDC__ *,ulong,HRGN__ *,tagRECT *)

- ea: `0x180003394`
- end: `0x1800035ee`
- name: `?AlphaFillRegion@@YAXPEAUHDC__@@KPEAUHRGN__@@PEAUtagRECT@@@Z`
- size: `602`
- prototype: `void __fastcall(HDC hdcDest, unsigned int, HRGN, struct tagRECT *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180057ea4`
- `0x1800581bc`

## callees

- `0x180003394`
- `0x180003690`
- `0x180004d70`
- `0x180031704`
- `0x1800358c0`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180003471`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18000348c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800034a2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180003471`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18000348c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800034a2`
- `GDI32!DeleteObject` at `0x1800035c8`
- `GDI32!DeleteObject` at `0x1800035c8`
- `GDI32!GetRegionData` at `0x1800034b3`
- `GDI32!GetRegionData` at `0x1800034e1`
- `GDI32!GetRegionData` at `0x1800034b3`
- `GDI32!GetRegionData` at `0x1800034e1`
- `GDI32!CreateDIBSection` at `0x180003436`
- `GDI32!CreateDIBSection` at `0x180003436`
- `USER32!ReleaseDC` at `0x180003449`
- `USER32!ReleaseDC` at `0x180003449`
- `USER32!GetDC` at `0x18000340c`
- `USER32!GetDC` at `0x18000340c`

## pseudocode

```c
void __fastcall AlphaFillRegion(HDC hdcDest, unsigned int a2, HRGN a3, struct tagRECT *a4)
{
  LONG v6; // eax
  HDC v8; // r14
  HDC DC; // rbx
  HBITMAP v10; // rsi
  unsigned int v11; // r13d
  DWORD RegionData; // eax
  DWORD v13; // r15d
  struct _RGNDATA *v14; // rax
  struct _RGNDATA *v15; // rbx
  char *v16; // rcx
  int v17; // r9d
  char v18; // r15
  char v19; // r12
  char v20; // r14
  int v21; // ecx
  int v22; // r11d
  int v23; // r10d
  unsigned int i; // r8d
  __int64 dwSize; // rcx
  unsigned int *v26; // rdx
  int v27; // edx
  void *ppvBits; // [rsp+30h] [rbp-49h] BYREF
  int v29; // [rsp+38h] [rbp-41h]
  int v30; // [rsp+3Ch] [rbp-3Dh]
  int v31; // [rsp+40h] [rbp-39h]
  HDC v32; // [rsp+48h] [rbp-31h]
  BITMAPINFO pbmi; // [rsp+50h] [rbp-29h] BYREF

  pbmi.bmiHeader.biWidth = a4->right - a4->left;
  v6 = a4->bottom - a4->top;
  v32 = hdcDest;
  v8 = hdcDest;
  ppvBits = 0;
  pbmi.bmiHeader.biSize = 40;
  pbmi.bmiHeader.biHeight = v6;
  *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
  if ( hdcDest )
  {
    DC = hdcDest;
  }
  else
  {
    DC = GetDC(0);
    if ( !DC )
      return;
  }
  v10 = CreateDIBSection(DC, &pbmi, 0, &ppvBits, 0, 0);
  if ( v8 != DC )
    ReleaseDC(0, DC);
  if ( v10 )
  {
    v11 = HIBYTE(a2);
    v29 = MulDiv(BYTE2(a2), HIBYTE(a2), 255);
    v30 = MulDiv(BYTE1(a2), HIBYTE(a2), 255);
    v31 = MulDiv((unsigned __int8)a2, HIBYTE(a2), 255);
    RegionData = GetRegionData(a3, 0, 0);
    v13 = RegionData;
    if ( RegionData )
    {
      v14 = (struct _RGNDATA *)operator new(RegionData);
      v15 = v14;
      if ( v14 )
      {
        GetRegionData(a3, v13, v14);
        if ( (a4->right - a4->left) * (a4->bottom - a4->top) > 0 )
        {
          v16 = (char *)ppvBits;
          v17 = 0;
          v18 = v29;
          v19 = v30;
          v20 = v31;
          do
          {
            v16[3] = 0;
            v21 = a4->right - a4->left;
            v22 = v17 % v21 + a4->left + 1;
            v23 = v17 / v21 + a4->top;
            for ( i = 0; i < v15->rdh.nCount; ++i )
            {
              dwSize = v15->rdh.dwSize;
              v26 = &v15->rdh.dwSize + 4 * i;
              if ( v22 >= *(int *)((char *)v26 + dwSize)
                && v22 < *(int *)((char *)v26 + dwSize + 8)
                && v23 >= *(int *)((char *)v26 + dwSize + 4)
                && v23 < *(int *)((char *)v26 + dwSize + 12) )
              {
                *(_BYTE *)ppvBits = v20;
                *((_BYTE *)ppvBits + 1) = v19;
                *((_BYTE *)ppvBits + 2) = v18;
                *((_BYTE *)ppvBits + 3) = v11;
                break;
              }
            }
            ++v17;
            v16 = (char *)ppvBits + 4;
            v27 = (a4->right - a4->left) * (a4->bottom - a4->top);
            ppvBits = (char *)ppvBits + 4;
          }
          while ( v17 < v27 );
          v8 = v32;
        }
        operator delete(v15);
      }
      AlphaDrawImage(v8, v10, a4);
    }
    DeleteObject(v10);
  }
}

```

## disassembly

```asm
0x180003394  push    rbp
0x180003396  push    rbx
0x180003397  push    rsi
0x180003398  push    rdi
0x180003399  push    r12
0x18000339b  push    r13
0x18000339d  push    r14
0x18000339f  push    r15
0x1800033a1  lea     rbp, [rsp-1Fh]
0x1800033a6  sub     rsp, 98h
0x1800033ad  mov     rax, cs:__security_cookie
0x1800033b4  xor     rax, rsp
0x1800033b7  mov     [rbp+57h+var_50], rax
0x1800033bb  mov     eax, [r9+8]
0x1800033bf  xor     r13d, r13d
0x1800033c2  sub     eax, [r9]
0x1800033c5  xorps   xmm0, xmm0
0x1800033c8  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x1800033cb  mov     rdi, r9
0x1800033ce  mov     eax, [r9+0Ch]
0x1800033d2  mov     r12, r8
0x1800033d5  sub     eax, [r9+4]
0x1800033d9  mov     r15d, edx
0x1800033dc  mov     [rbp+57h+var_88], rcx
0x1800033e0  mov     r14, rcx
0x1800033e3  mov     [rbp+57h+ppvBits], r13
0x1800033e7  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], r13
0x1800033eb  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x1800033f2  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x1800033f5  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x1800033fd  movdqu  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x180003402  test    rcx, rcx
0x180003405  jz      short loc_18000340C
0x180003407  mov     rbx, rcx
0x18000340a  jmp     short loc_18000341E
0x18000340c  call    cs:__imp_GetDC
0x180003412  mov     rbx, rax
0x180003415  test    rax, rax
0x180003418  jz      loc_1800035CE
0x18000341e  mov     [rsp+0D0h+offset], r13d; offset
0x180003423  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x180003427  xor     r8d, r8d; usage
0x18000342a  mov     [rsp+0D0h+hSection], r13; hSection
0x18000342f  lea     rdx, [rbp+57h+pbmi]; pbmi
0x180003433  mov     rcx, rbx; hdc
0x180003436  call    cs:__imp_CreateDIBSection
0x18000343c  mov     rsi, rax
0x18000343f  cmp     r14, rbx
0x180003442  jz      short loc_18000344F
0x180003444  mov     rdx, rbx; hDC
0x180003447  xor     ecx, ecx; hWnd
0x180003449  call    cs:__imp_ReleaseDC
0x18000344f  test    rsi, rsi
0x180003452  jz      loc_1800035CE
0x180003458  mov     eax, r15d
0x18000345b  mov     r13d, r15d
0x18000345e  shr     eax, 10h
0x180003461  mov     r8d, 0FFh; nDenominator
0x180003467  shr     r13d, 18h
0x18000346b  movzx   ecx, al; nNumber
0x18000346e  mov     edx, r13d; nNumerator
0x180003471  call    cs:__imp_MulDiv
0x180003477  mov     ecx, r15d
0x18000347a  mov     r8d, 0FFh; nDenominator
0x180003480  mov     edx, r13d; nNumerator
0x180003483  mov     [rbp+57h+var_98], eax
0x180003486  shr     ecx, 8
0x180003489  movzx   ecx, cl; nNumber
0x18000348c  call    cs:__imp_MulDiv
0x180003492  movzx   ecx, r15b; nNumber
0x180003496  mov     r8d, 0FFh; nDenominator
0x18000349c  mov     edx, r13d; nNumerator
0x18000349f  mov     [rbp+57h+var_94], eax
0x1800034a2  call    cs:__imp_MulDiv
0x1800034a8  xor     r8d, r8d; lpRgnData
0x1800034ab  xor     edx, edx; nCount
0x1800034ad  mov     rcx, r12; hrgn
0x1800034b0  mov     [rbp+57h+var_90], eax
0x1800034b3  call    cs:__imp_GetRegionData
0x1800034b9  mov     r15d, eax
0x1800034bc  test    eax, eax
0x1800034be  jz      loc_1800035C5
0x1800034c4  mov     ecx, r15d; unsigned __int64
0x1800034c7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800034cc  mov     rbx, rax
0x1800034cf  test    rax, rax
0x1800034d2  jz      loc_1800035B7
0x1800034d8  mov     r8, rax; lpRgnData
0x1800034db  mov     edx, r15d; nCount
0x1800034de  mov     rcx, r12; hrgn
0x1800034e1  call    cs:__imp_GetRegionData
0x1800034e7  mov     edx, [rdi+0Ch]
0x1800034ea  sub     edx, [rdi+4]
0x1800034ed  mov     ecx, [rdi+8]
0x1800034f0  sub     ecx, [rdi]
0x1800034f2  imul    edx, ecx
0x1800034f5  test    edx, edx
0x1800034f7  jle     loc_1800035AF
0x1800034fd  mov     rcx, [rbp+57h+ppvBits]
0x180003501  xor     r9d, r9d
0x180003504  mov     r15d, [rbp+57h+var_98]
0x180003508  mov     r12d, [rbp+57h+var_94]
0x18000350c  mov     r14d, [rbp+57h+var_90]
0x180003510  mov     byte ptr [rcx+3], 0
0x180003514  mov     eax, r9d
0x180003517  mov     r8d, [rdi]
0x18000351a  cdq
0x18000351b  mov     ecx, [rdi+8]
0x18000351e  mov     r10d, [rdi+4]
0x180003522  sub     ecx, r8d
0x180003525  idiv    ecx
0x180003527  lea     r11d, [r8+1]
0x18000352b  add     r11d, edx
0x18000352e  add     r10d, eax
0x180003531  xor     r8d, r8d
0x180003534  cmp     r8d, [rbx+8]
0x180003538  jnb     short loc_180003585
0x18000353a  mov     ecx, [rbx]
0x18000353c  mov     edx, r8d
0x18000353f  shl     rdx, 4
0x180003543  add     rdx, rbx
0x180003546  cmp     r11d, [rcx+rdx]
0x18000354a  jl      short loc_180003561
0x18000354c  cmp     r11d, [rcx+rdx+8]
0x180003551  jge     short loc_180003561
0x180003553  cmp     r10d, [rcx+rdx+4]
0x180003558  jl      short loc_180003561
0x18000355a  cmp     r10d, [rcx+rdx+0Ch]
0x18000355f  jl      short loc_180003566
0x180003561  inc     r8d
0x180003564  jmp     short loc_180003534
0x180003566  mov     rax, [rbp+57h+ppvBits]
0x18000356a  mov     [rax], r14b
0x18000356d  mov     rax, [rbp+57h+ppvBits]
0x180003571  mov     [rax+1], r12b
0x180003575  mov     rax, [rbp+57h+ppvBits]
0x180003579  mov     [rax+2], r15b
0x18000357d  mov     rax, [rbp+57h+ppvBits]
0x180003581  mov     [rax+3], r13b
0x180003585  mov     rcx, [rbp+57h+ppvBits]
0x180003589  inc     r9d
0x18000358c  mov     edx, [rdi+0Ch]
0x18000358f  add     rcx, 4
0x180003593  sub     edx, [rdi+4]
0x180003596  mov     eax, [rdi+8]
0x180003599  sub     eax, [rdi]
0x18000359b  imul    edx, eax
0x18000359e  mov     [rbp+57h+ppvBits], rcx
0x1800035a2  cmp     r9d, edx
0x1800035a5  jl      loc_180003510
0x1800035ab  mov     r14, [rbp+57h+var_88]
0x1800035af  mov     rcx, rbx; lpMem
0x1800035b2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800035b7  mov     r8, rdi; struct tagRECT *
0x1800035ba  mov     rdx, rsi; h
0x1800035bd  mov     rcx, r14; hdcDest
0x1800035c0  call    ?AlphaDrawImage@@YAHPEAUHDC__@@PEAUHBITMAP__@@PEAUtagRECT@@@Z; AlphaDrawImage(HDC__ *,HBITMAP__ *,tagRECT *)
0x1800035c5  mov     rcx, rsi; ho
0x1800035c8  call    cs:__imp_DeleteObject
0x1800035ce  mov     rcx, [rbp+57h+var_50]
0x1800035d2  xor     rcx, rsp; StackCookie
0x1800035d5  call    __security_check_cookie
0x1800035da  add     rsp, 98h
0x1800035e1  pop     r15
0x1800035e3  pop     r14
0x1800035e5  pop     r13
0x1800035e7  pop     r12
0x1800035e9  pop     rdi
0x1800035ea  pop     rsi
0x1800035eb  pop     rbx
0x1800035ec  pop     rbp
0x1800035ed  retn
```
