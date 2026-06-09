# CWMResizeDMO::getVIH(_AMMediaType const *,tagVIDEOINFOHEADER *,tagVIDEOINFOHEADER * *)

- ea: `0x180009170`
- end: `0x1800092f3`
- name: `?getVIH@CWMResizeDMO@@AEAAJPEBU_AMMediaType@@PEAUtagVIDEOINFOHEADER@@PEAPEAU3@@Z`
- size: `387`
- prototype: `__int64 __fastcall(CWMResizeDMO *this, const struct _AMMediaType *, struct tagVIDEOINFOHEADER *, struct tagVIDEOINFOHEADER **)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004bd0`
- `0x180007e90`
- `0x180008680`
- `0x1800089b0`

## callees

- `0x180003950`
- `0x180009170`
- `0x180015905`

## pseudocode

```c
__int64 __fastcall CWMResizeDMO::getVIH(
        CWMResizeDMO *this,
        const struct _AMMediaType *a2,
        struct tagVIDEOINFOHEADER *a3,
        struct tagVIDEOINFOHEADER **a4)
{
  __int64 result; // rax
  DWORD biClrUsed; // eax

  if ( !a2 || !a3 || !a4 )
    return 2147500035LL;
  if ( *(_QWORD *)&FORMAT_MFVideoFormat.Data1 == *(_QWORD *)&a2->formattype.Data1
    && *(_QWORD *)FORMAT_MFVideoFormat.Data4 == *(_QWORD *)a2->formattype.Data4 )
  {
    ConvertMFVideoFormatToVIH3(a3, (struct _MFVIDEOFORMAT *)a2->pbFormat);
    result = 0;
    *a4 = a3;
    return result;
  }
  if ( *(_QWORD *)&FORMAT_VideoInfo2.Data1 == *(_QWORD *)&a2->formattype.Data1
    && *(_QWORD *)FORMAT_VideoInfo2.Data4 == *(_QWORD *)a2->formattype.Data4 )
  {
    *a3 = *(struct tagVIDEOINFOHEADER *)a2->pbFormat;
    a3->bmiHeader = *(BITMAPINFOHEADER *)(a2->pbFormat + 72);
  }
  else
  {
    if ( *(_QWORD *)&FORMAT_VideoInfo.Data1 != *(_QWORD *)&a2->formattype.Data1
      || *(_QWORD *)FORMAT_VideoInfo.Data4 != *(_QWORD *)a2->formattype.Data4 )
    {
      return 2147500037LL;
    }
    *a3 = *(struct tagVIDEOINFOHEADER *)a2->pbFormat;
  }
  if ( !a3->bmiHeader.biCompression )
  {
    biClrUsed = a3->bmiHeader.biClrUsed;
    if ( biClrUsed )
      memcpy_0(&a3[1], a2->pbFormat + 112, 4LL * biClrUsed);
  }
  *a4 = a3;
  return 0;
}

```

## disassembly

```asm
0x180009170  mov     [rsp+arg_0], rbx
0x180009175  push    rdi
0x180009176  sub     rsp, 20h
0x18000917a  mov     rdi, r9
0x18000917d  mov     rbx, r8
0x180009180  test    rdx, rdx
0x180009183  jz      loc_1800092E3
0x180009189  test    rbx, rbx
0x18000918c  jz      loc_1800092E3
0x180009192  test    r9, r9
0x180009195  jz      loc_1800092E3
0x18000919b  mov     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x1800091a2  cmp     rax, [rdx+2Ch]
0x1800091a6  jnz     short loc_1800091D1
0x1800091a8  mov     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x1800091af  cmp     rax, [rdx+34h]
0x1800091b3  jnz     short loc_1800091D1
0x1800091b5  mov     rdx, [rdx+50h]; struct _MFVIDEOFORMAT *
0x1800091b9  mov     rcx, rbx; struct tagVIDEOINFOHEADER *
0x1800091bc  call    ?ConvertMFVideoFormatToVIH3@@YAJPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z; ConvertMFVideoFormatToVIH3(tagVIDEOINFOHEADER *,_MFVIDEOFORMAT *)
0x1800091c1  xor     eax, eax
0x1800091c3  mov     [rdi], rbx
0x1800091c6  mov     rbx, [rsp+28h+arg_0]
0x1800091cb  add     rsp, 20h
0x1800091cf  pop     rdi
0x1800091d0  retn
0x1800091d1  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x1800091d8  cmp     rax, [rdx+2Ch]
0x1800091dc  jnz     short loc_180009248
0x1800091de  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x1800091e5  cmp     rax, [rdx+34h]
0x1800091e9  jnz     short loc_180009248
0x1800091eb  mov     rax, [rdx+50h]
0x1800091ef  movups  xmm0, xmmword ptr [rax]
0x1800091f2  movups  xmmword ptr [r8], xmm0
0x1800091f6  movups  xmm1, xmmword ptr [rax+10h]
0x1800091fa  movups  xmmword ptr [r8+10h], xmm1
0x1800091ff  movups  xmm0, xmmword ptr [rax+20h]
0x180009203  movups  xmmword ptr [r8+20h], xmm0
0x180009208  movups  xmm1, xmmword ptr [rax+30h]
0x18000920c  movups  xmmword ptr [r8+30h], xmm1
0x180009211  movups  xmm0, xmmword ptr [rax+40h]
0x180009215  movups  xmmword ptr [r8+40h], xmm0
0x18000921a  movsd   xmm1, qword ptr [rax+50h]
0x18000921f  movsd   qword ptr [r8+50h], xmm1
0x180009225  mov     rax, [rdx+50h]
0x180009229  movups  xmm0, xmmword ptr [rax+48h]
0x18000922d  movups  xmmword ptr [r8+30h], xmm0
0x180009232  movups  xmm1, xmmword ptr [rax+58h]
0x180009236  movups  xmmword ptr [r8+40h], xmm1
0x18000923b  movsd   xmm0, qword ptr [rax+68h]
0x180009240  movsd   qword ptr [r8+50h], xmm0
0x180009246  jmp     short loc_18000929C
0x180009248  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x18000924f  cmp     rax, [rdx+2Ch]
0x180009253  jnz     short loc_1800092D3
0x180009255  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x18000925c  cmp     rax, [rdx+34h]
0x180009260  jnz     short loc_1800092D3
0x180009262  mov     rax, [rdx+50h]
0x180009266  movups  xmm0, xmmword ptr [rax]
0x180009269  movups  xmmword ptr [r8], xmm0
0x18000926d  movups  xmm1, xmmword ptr [rax+10h]
0x180009271  movups  xmmword ptr [r8+10h], xmm1
0x180009276  movups  xmm0, xmmword ptr [rax+20h]
0x18000927a  movups  xmmword ptr [r8+20h], xmm0
0x18000927f  movups  xmm1, xmmword ptr [rax+30h]
0x180009283  movups  xmmword ptr [r8+30h], xmm1
0x180009288  movups  xmm0, xmmword ptr [rax+40h]
0x18000928c  movups  xmmword ptr [r8+40h], xmm0
0x180009291  movsd   xmm1, qword ptr [rax+50h]
0x180009296  movsd   qword ptr [r8+50h], xmm1
0x18000929c  cmp     dword ptr [r8+40h], 0
0x1800092a1  jnz     short loc_1800092C3
0x1800092a3  mov     eax, [r8+50h]
0x1800092a7  test    eax, eax
0x1800092a9  jz      short loc_1800092C3
0x1800092ab  mov     rdx, [rdx+50h]
0x1800092af  lea     rcx, [rbx+58h]; void *
0x1800092b3  mov     r8d, eax
0x1800092b6  add     rdx, 70h ; 'p'; Src
0x1800092ba  shl     r8, 2; Size
0x1800092be  call    memcpy_0
0x1800092c3  mov     [rdi], rbx
0x1800092c6  xor     eax, eax
0x1800092c8  mov     rbx, [rsp+28h+arg_0]
0x1800092cd  add     rsp, 20h
0x1800092d1  pop     rdi
0x1800092d2  retn
0x1800092d3  mov     eax, 80004005h
0x1800092d8  mov     rbx, [rsp+28h+arg_0]
0x1800092dd  add     rsp, 20h
0x1800092e1  pop     rdi
0x1800092e2  retn
0x1800092e3  mov     rbx, [rsp+28h+arg_0]
0x1800092e8  mov     eax, 80004003h
0x1800092ed  add     rsp, 20h
0x1800092f1  pop     rdi
0x1800092f2  retn
```
