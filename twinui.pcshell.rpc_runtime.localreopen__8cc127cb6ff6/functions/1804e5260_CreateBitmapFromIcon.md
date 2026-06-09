# CreateBitmapFromIcon

- ea: `0x1804e5260`
- end: `0x1804e54ff`
- name: `CreateBitmapFromIcon`
- size: `671`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180149274`

## callees

- `0x1801ea518`
- `0x1801ef12c`
- `0x180356360`
- `0x180356edc`
- `0x18036522c`
- `0x1804e4b64`
- `0x1804e5260`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFillRectClr` at `0x1804e52f8`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFillRectClr` at `0x1804e52f8`
- `SHELL32!__imp_SHGetImageList` at `0x1804e53d5`
- `SHELL32!__imp_SHGetImageList` at `0x1804e53d5`
- `GDI32!DeleteObject` at `0x1804e54cc`
- `GDI32!DeleteObject` at `0x1804e54cc`
- `GDI32!CreateCompatibleDC` at `0x1804e52bc`
- `GDI32!CreateCompatibleDC` at `0x1804e52bc`
- `GDI32!SelectObject` at `0x1804e52d5`
- `GDI32!SelectObject` at `0x1804e54a2`
- `GDI32!SelectObject` at `0x1804e52d5`
- `GDI32!SelectObject` at `0x1804e54a2`
- `GDI32!DeleteDC` at `0x1804e54be`
- `GDI32!DeleteDC` at `0x1804e54be`

## string_xrefs

- `0x1804e5337`: `ImageList_ReplaceIcon`

## pseudocode

```c
__int64 __fastcall CreateBitmapFromIcon(HDC a1, __int64 a2, void **a3, const struct tagSIZE *a4, _QWORD *a5)
{
  HRESULT v7; // ebx
  HDC CompatibleDC; // rax
  HDC v9; // rsi
  HGDIOBJ v10; // rax
  void *v11; // r13
  int v12; // r9d
  struct _IMAGELIST *v13; // r14
  __int64 (__fastcall *v14)(struct _IMAGELIST *, __int64, HDC); // rax
  int v15; // r15d
  __int64 (__fastcall *v16)(struct _IMAGELIST *, GUID *, void **); // rax
  void *v17; // rcx
  HGDIOBJ v18; // rax
  int v20; // [rsp+20h] [rbp-81h]
  void *ppvObj; // [rsp+30h] [rbp-71h] BYREF
  HGDIOBJ h; // [rsp+38h] [rbp-69h] BYREF
  __int64 v23; // [rsp+40h] [rbp-61h] BYREF
  _BYTE v24[8]; // [rsp+48h] [rbp-59h] BYREF
  int v25; // [rsp+50h] [rbp-51h]
  HDC v26; // [rsp+58h] [rbp-49h]
  LONG v27; // [rsp+68h] [rbp-39h]
  LONG v28; // [rsp+6Ch] [rbp-35h]
  int v29; // [rsp+78h] [rbp-29h]
  int v30; // [rsp+7Ch] [rbp-25h]
  int v31; // [rsp+80h] [rbp-21h]
  __int64 v32; // [rsp+A0h] [rbp-1h] BYREF
  LONG cx; // [rsp+A8h] [rbp+7h]
  LONG cy; // [rsp+ACh] [rbp+Bh]

  h = 0;
  *a5 = 0;
  v7 = Create32BitHBITMAP(a1, a4, a3, (HBITMAP *)&h);
  if ( v7 < 0 )
    return (unsigned int)v7;
  v7 = -2147467259;
  CompatibleDC = CreateCompatibleDC(0);
  v9 = CompatibleDC;
  if ( !CompatibleDC )
  {
LABEL_27:
    DeleteObject(h);
    *a5 = 0;
    return (unsigned int)v7;
  }
  v10 = SelectObject(CompatibleDC, h);
  cx = a4->cx;
  v11 = v10;
  cy = a4->cy;
  v32 = 0;
  SHFillRectClr(v9, &v32, 0xFFFFFFFFLL);
  ppvObj = 0;
  if ( a1 )
  {
    v7 = -2147024882;
    v13 = ImageList_Create(a4->cx, a4->cy, 0x21u, v12, v20);
    if ( !v13 )
      goto LABEL_21;
    v14 = (__int64 (__fastcall *)(struct _IMAGELIST *, __int64, HDC))qword_1808D5238;
    if ( qword_1808D5238 == -1 )
    {
      GetProcFromComCtl32(&qword_1808D5238, "ImageList_ReplaceIcon");
      v14 = (__int64 (__fastcall *)(struct _IMAGELIST *, __int64, HDC))qword_1808D5238;
    }
    if ( v14 )
    {
      v15 = v14(v13, 0xFFFFFFFFLL, a1);
      if ( v15 != -1 )
      {
        v16 = (__int64 (__fastcall *)(struct _IMAGELIST *, GUID *, void **))qword_1808D5228;
        if ( qword_1808D5228 == -1 )
        {
          GetProcFromComCtl32(&qword_1808D5228, "HIMAGELIST_QueryInterface");
          v16 = (__int64 (__fastcall *)(struct _IMAGELIST *, GUID *, void **))qword_1808D5228;
        }
        if ( v16 )
          v7 = v16(v13, &GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1, &ppvObj);
        else
          v7 = -2147467259;
      }
    }
    else
    {
      v15 = -1;
    }
    ImageList_Destroy(v13);
  }
  else
  {
    v7 = SHGetImageList(-1, &GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1, &ppvObj);
    if ( v7 < 0 )
      goto LABEL_21;
    v7 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)ppvObj + 256LL))(
           ppvObj,
           (unsigned int)a4->cx,
           (unsigned int)a4->cy);
    if ( v7 < 0 )
      goto LABEL_21;
    v15 = 0;
    v7 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)ppvObj + 296LL))(ppvObj, 0, 0);
  }
  if ( v7 >= 0 )
  {
    v23 = 88;
    memset_0(v24, 0, 0x50u);
    v27 = a4->cx;
    v28 = a4->cy;
    v29 = -16777216;
    v30 = -16777216;
    v25 = v15 & 0xFFFFFF;
    v26 = v9;
    v31 = 327681;
    v7 = (*(__int64 (__fastcall **)(void *, __int64 *))(*(_QWORD *)ppvObj + 64LL))(ppvObj, &v23);
  }
LABEL_21:
  v17 = ppvObj;
  ppvObj = 0;
  if ( v17 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 16LL))(v17);
  v18 = SelectObject(v9, v11);
  *a5 = v18;
  if ( v7 >= 0 && !v18 )
    v7 = -2147467259;
  DeleteDC(v9);
  if ( v7 < 0 )
    goto LABEL_27;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1804e5260  mov     [rsp-8+arg_8], rbx
0x1804e5265  push    rbp
0x1804e5266  push    rsi
0x1804e5267  push    rdi
0x1804e5268  push    r12
0x1804e526a  push    r13
0x1804e526c  push    r14
0x1804e526e  push    r15
0x1804e5270  lea     rbp, [rsp-1Fh]
0x1804e5275  sub     rsp, 0C0h
0x1804e527c  mov     rax, cs:__security_cookie
0x1804e5283  xor     rax, rsp
0x1804e5286  mov     [rbp+4Fh+var_40], rax
0x1804e528a  mov     r12, [rbp+4Fh+arg_20]
0x1804e528e  mov     rdi, r9
0x1804e5291  xor     r14d, r14d
0x1804e5294  lea     r9, [rbp+4Fh+h]; HBITMAP *
0x1804e5298  mov     rdx, rdi; struct tagSIZE *
0x1804e529b  mov     [rbp+4Fh+h], r14
0x1804e529f  mov     r15, rcx
0x1804e52a2  mov     [r12], r14
0x1804e52a6  call    ?Create32BitHBITMAP@@YAJPEAUHDC__@@PEBUtagSIZE@@PEAPEAXPEAPEAUHBITMAP__@@@Z; Create32BitHBITMAP(HDC__ *,tagSIZE const *,void * *,HBITMAP__ * *)
0x1804e52ab  mov     ebx, eax
0x1804e52ad  test    eax, eax
0x1804e52af  js      loc_1804E54D6
0x1804e52b5  xor     ecx, ecx; hdc
0x1804e52b7  mov     ebx, 80004005h
0x1804e52bc  call    cs:__imp_CreateCompatibleDC
0x1804e52c2  mov     rsi, rax
0x1804e52c5  test    rax, rax
0x1804e52c8  jz      loc_1804E54C8
0x1804e52ce  mov     rdx, [rbp+4Fh+h]; h
0x1804e52d2  mov     rcx, rax; hdc
0x1804e52d5  call    cs:__imp_SelectObject
0x1804e52db  mov     ecx, [rdi]
0x1804e52dd  lea     rdx, [rbp+4Fh+var_50]
0x1804e52e1  mov     [rbp+4Fh+var_48], ecx
0x1804e52e4  or      r8d, 0FFFFFFFFh
0x1804e52e8  mov     ecx, [rdi+4]
0x1804e52eb  mov     r13, rax
0x1804e52ee  mov     [rbp+4Fh+var_44], ecx
0x1804e52f1  mov     rcx, rsi
0x1804e52f4  mov     [rbp+4Fh+var_50], r14
0x1804e52f8  call    cs:__imp_SHFillRectClr
0x1804e52fe  mov     [rbp+4Fh+ppvObj], r14
0x1804e5302  test    r15, r15
0x1804e5305  jz      loc_1804E53C7
0x1804e530b  mov     edx, [rdi+4]; cy
0x1804e530e  lea     r8d, [r14+21h]; flags
0x1804e5312  mov     ecx, [rdi]; cx
0x1804e5314  mov     ebx, 8007000Eh
0x1804e5319  call    ImageList_Create
0x1804e531e  mov     r14, rax
0x1804e5321  test    rax, rax
0x1804e5324  jz      loc_1804E5480
0x1804e532a  mov     rax, cs:qword_1808D5238
0x1804e5331  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1804e5335  jnz     short loc_1804E5351
0x1804e5337  lea     rdx, aImagelistRepla; "ImageList_ReplaceIcon"
0x1804e533e  lea     rcx, qword_1808D5238
0x1804e5345  call    _GetProcFromComCtl32
0x1804e534a  mov     rax, cs:qword_1808D5238
0x1804e5351  test    rax, rax
0x1804e5354  jz      short loc_1804E53B6
0x1804e5356  mov     r8, r15
0x1804e5359  or      edx, 0FFFFFFFFh
0x1804e535c  mov     rcx, r14
0x1804e535f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e5364  mov     r15d, eax
0x1804e5367  cmp     eax, 0FFFFFFFFh
0x1804e536a  jz      short loc_1804E53BA
0x1804e536c  mov     rax, cs:qword_1808D5228
0x1804e5373  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1804e5377  jnz     short loc_1804E5393
0x1804e5379  lea     rdx, aHimagelistQuer; "HIMAGELIST_QueryInterface"
0x1804e5380  lea     rcx, qword_1808D5228
0x1804e5387  call    _GetProcFromComCtl32
0x1804e538c  mov     rax, cs:qword_1808D5228
0x1804e5393  test    rax, rax
0x1804e5396  jz      short loc_1804E53AF
0x1804e5398  lea     r8, [rbp+4Fh+ppvObj]
0x1804e539c  mov     rcx, r14
0x1804e539f  lea     rdx, _GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1
0x1804e53a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e53ab  mov     ebx, eax
0x1804e53ad  jmp     short loc_1804E53BA
0x1804e53af  mov     ebx, 80004005h
0x1804e53b4  jmp     short loc_1804E53BA
0x1804e53b6  or      r15d, 0FFFFFFFFh
0x1804e53ba  mov     rcx, r14; himl
0x1804e53bd  call    ImageList_Destroy
0x1804e53c2  xor     r14d, r14d
0x1804e53c5  jmp     short loc_1804E5421
0x1804e53c7  lea     r8, [rbp+4Fh+ppvObj]; ppvObj
0x1804e53cb  or      ecx, 0FFFFFFFFh; iImageList
0x1804e53ce  lea     rdx, _GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1; riid
0x1804e53d5  call    cs:__imp_SHGetImageList
0x1804e53db  mov     ebx, eax
0x1804e53dd  test    eax, eax
0x1804e53df  js      loc_1804E5483
0x1804e53e5  mov     rcx, [rbp+4Fh+ppvObj]
0x1804e53e9  mov     r8d, [rdi+4]
0x1804e53ed  mov     edx, [rdi]
0x1804e53ef  mov     rax, [rcx]
0x1804e53f2  mov     rax, [rax+100h]
0x1804e53f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e53fe  mov     ebx, eax
0x1804e5400  test    eax, eax
0x1804e5402  js      short loc_1804E5483
0x1804e5404  mov     rcx, [rbp+4Fh+ppvObj]
0x1804e5408  xor     r8d, r8d
0x1804e540b  xor     edx, edx
0x1804e540d  mov     r15d, r14d
0x1804e5410  mov     rax, [rcx]
0x1804e5413  mov     rax, [rax+128h]
0x1804e541a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e541f  mov     ebx, eax
0x1804e5421  test    ebx, ebx
0x1804e5423  js      short loc_1804E5483
0x1804e5425  xor     edx, edx; Val
0x1804e5427  mov     [rbp+4Fh+var_B0], 58h ; 'X'
0x1804e542f  lea     rcx, [rbp+4Fh+var_A8]; void *
0x1804e5433  lea     r8d, [rdx+50h]; Size
0x1804e5437  call    memset_0
0x1804e543c  mov     eax, [rdi]
0x1804e543e  lea     rdx, [rbp+4Fh+var_B0]
0x1804e5442  mov     rcx, [rbp+4Fh+ppvObj]
0x1804e5446  and     r15d, 0FFFFFFh
0x1804e544d  mov     [rbp+4Fh+var_88], eax
0x1804e5450  mov     eax, [rdi+4]
0x1804e5453  mov     [rbp+4Fh+var_84], eax
0x1804e5456  mov     eax, 0FF000000h
0x1804e545b  mov     [rbp+4Fh+var_78], eax
0x1804e545e  mov     [rbp+4Fh+var_74], eax
0x1804e5461  mov     [rbp+4Fh+var_A0], r15d
0x1804e5465  mov     [rbp+4Fh+var_98], rsi
0x1804e5469  mov     [rbp+4Fh+var_70], 50001h
0x1804e5470  mov     rax, [rcx]
0x1804e5473  mov     rax, [rax+40h]
0x1804e5477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e547c  mov     ebx, eax
0x1804e547e  jmp     short loc_1804E5483
0x1804e5480  xor     r14d, r14d
0x1804e5483  mov     rcx, [rbp+4Fh+ppvObj]
0x1804e5487  mov     [rbp+4Fh+ppvObj], r14
0x1804e548b  test    rcx, rcx
0x1804e548e  jz      short loc_1804E549C
0x1804e5490  mov     rax, [rcx]
0x1804e5493  mov     rax, [rax+10h]
0x1804e5497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e549c  mov     rdx, r13; h
0x1804e549f  mov     rcx, rsi; hdc
0x1804e54a2  call    cs:__imp_SelectObject
0x1804e54a8  mov     [r12], rax
0x1804e54ac  test    ebx, ebx
0x1804e54ae  js      short loc_1804E54BB
0x1804e54b0  test    rax, rax
0x1804e54b3  mov     eax, 80004005h
0x1804e54b8  cmovz   ebx, eax
0x1804e54bb  mov     rcx, rsi; hdc
0x1804e54be  call    cs:__imp_DeleteDC
0x1804e54c4  test    ebx, ebx
0x1804e54c6  jns     short loc_1804E54D6
0x1804e54c8  mov     rcx, [rbp+4Fh+h]; ho
0x1804e54cc  call    cs:__imp_DeleteObject
0x1804e54d2  mov     [r12], r14
0x1804e54d6  mov     eax, ebx
0x1804e54d8  mov     rcx, [rbp+4Fh+var_40]
0x1804e54dc  xor     rcx, rsp; StackCookie
0x1804e54df  call    __security_check_cookie
0x1804e54e4  mov     rbx, [rsp+0F0h+arg_8]
0x1804e54ec  add     rsp, 0C0h
0x1804e54f3  pop     r15
0x1804e54f5  pop     r14
0x1804e54f7  pop     r13
0x1804e54f9  pop     r12
0x1804e54fb  pop     rdi
0x1804e54fc  pop     rsi
0x1804e54fd  pop     rbp
0x1804e54fe  retn
```
