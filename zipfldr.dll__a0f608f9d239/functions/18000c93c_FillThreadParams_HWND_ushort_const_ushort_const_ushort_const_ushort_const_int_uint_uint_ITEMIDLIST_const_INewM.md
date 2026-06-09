# FillThreadParams(HWND__ *,ushort const *,ushort const *,ushort const *,ushort const *,int,uint,uint,_ITEMIDLIST const *,INewMenuClient *,THREADPARAMS * *)

- ea: `0x18000c93c`
- end: `0x18000ca8d`
- name: `?FillThreadParams@@YAJPEAUHWND__@@PEBG111HIIPEFBU_ITEMIDLIST@@PEAUINewMenuClient@@PEAPEAUTHREADPARAMS@@@Z`
- size: `337`
- prototype: `int(HWND, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, unsigned int, unsigned int, const struct _ITEMIDLIST *, struct INewMenuClient *, struct THREADPARAMS **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002bf78`

## callees

- `0x18000c25c`
- `0x18000c93c`
- `0x18000d7e0`
- `0x18000f698`
- `0x180011860`
- `0x1800390fd`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x18000c9d8`
- `SHLWAPI!SHStrDupW` at `0x18000c9d8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c96e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c96e`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18000ca5e`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18000ca5e`

## pseudocode

```c
__int64 __fastcall FillThreadParams(
        HWND a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *Src,
        int a6,
        unsigned int a7,
        unsigned int a8,
        const struct _ITEMIDLIST *a9,
        IUnknown *pUnk,
        struct THREADPARAMS **a11)
{
  wchar_t *v15; // rax
  size_t *v16; // r8
  wchar_t *v17; // rdi
  size_t *v18; // r8
  __int64 v19; // rcx
  HRESULT v20; // ebx
  size_t v22; // [rsp+20h] [rbp-48h]
  size_t v23; // [rsp+20h] [rbp-48h]

  *a11 = 0;
  v15 = (wchar_t *)LocalAlloc(0x40u, 0x440u);
  v17 = v15;
  if ( !v15 )
    return (unsigned int)-2147024882;
  *((_DWORD *)v15 + 267) = a8;
  *((_DWORD *)v15 + 266) = a6;
  *(_QWORD *)v15 = a1;
  StringCopyWorkerW(v15 + 4, 0x104u, v16, a2, v22);
  StringCopyWorkerW(v17 + 264, 0x104u, v18, a3, v23);
  if ( a4 )
  {
    v20 = SHStrDupW(a4, (LPWSTR *)v17 + 131);
    if ( v20 < 0 )
      goto LABEL_14;
  }
  else
  {
    *((_QWORD *)v17 + 131) = 0;
  }
  v20 = _AllocArray<unsigned short,CTLocalAllocPolicy>(v19, 64, a7, v17 + 528);
  if ( v20 < 0 )
    goto LABEL_14;
  memcpy_0(*((void **)v17 + 132), Src, 2LL * a7);
  if ( a9 )
  {
    v20 = SHILClone(a9, (struct _ITEMIDLIST **)v17 + 134);
    if ( v20 < 0 )
      goto LABEL_14;
  }
  if ( pUnk )
  {
    v20 = CoMarshalInterThreadInterfaceInStream(&IID_INewMenuClient, pUnk, (LPSTREAM *)v17 + 135);
    if ( v20 >= 0 )
      goto LABEL_11;
LABEL_14:
    FreeThreadParams((struct THREADPARAMS *)v17);
    return (unsigned int)v20;
  }
  v20 = 0;
LABEL_11:
  *a11 = (struct THREADPARAMS *)v17;
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x18000c93c  push    rbx
0x18000c93e  push    rbp
0x18000c93f  push    rsi
0x18000c940  push    rdi
0x18000c941  push    r14
0x18000c943  push    r15
0x18000c945  sub     rsp, 38h
0x18000c949  mov     r15, [rsp+68h+arg_50]
0x18000c951  mov     rbp, rdx
0x18000c954  mov     r14, rcx
0x18000c957  mov     edx, 440h; uBytes
0x18000c95c  mov     ecx, 40h ; '@'; uFlags
0x18000c961  mov     rbx, r9
0x18000c964  mov     rsi, r8
0x18000c967  mov     qword ptr [r15], 0
0x18000c96e  call    cs:__imp_LocalAlloc
0x18000c974  mov     rdi, rax
0x18000c977  test    rax, rax
0x18000c97a  jz      loc_18000CA7C
0x18000c980  mov     ecx, [rsp+68h+arg_38]
0x18000c987  mov     r9, rbp; pszSrc
0x18000c98a  mov     [rax+42Ch], ecx
0x18000c990  mov     ebp, 104h
0x18000c995  mov     ecx, [rsp+68h+arg_28]
0x18000c99c  mov     edx, ebp; cchDest
0x18000c99e  mov     [rax+428h], ecx
0x18000c9a4  lea     rcx, [rax+8]; pszDest
0x18000c9a8  mov     [rax], r14
0x18000c9ab  call    StringCopyWorkerW
0x18000c9b0  lea     rcx, [rdi+210h]; pszDest
0x18000c9b7  mov     r9, rsi; pszSrc
0x18000c9ba  mov     edx, ebp; cchDest
0x18000c9bc  call    StringCopyWorkerW
0x18000c9c1  lea     rax, [rdi+418h]
0x18000c9c8  test    rbx, rbx
0x18000c9cb  jnz     short loc_18000C9D2
0x18000c9cd  mov     [rax], rbx
0x18000c9d0  jmp     short loc_18000C9E8
0x18000c9d2  mov     rdx, rax; ppwsz
0x18000c9d5  mov     rcx, rbx; psz
0x18000c9d8  call    cs:__imp_SHStrDupW
0x18000c9de  mov     ebx, eax
0x18000c9e0  test    eax, eax
0x18000c9e2  js      loc_18000CA83
0x18000c9e8  mov     esi, [rsp+68h+arg_30]
0x18000c9ef  lea     r14, [rdi+420h]
0x18000c9f6  mov     r9, r14
0x18000c9f9  mov     r8d, esi
0x18000c9fc  mov     edx, 40h ; '@'
0x18000ca01  call    ??$_AllocArray@GVCTLocalAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTLocalAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x18000ca06  mov     ebx, eax
0x18000ca08  test    eax, eax
0x18000ca0a  js      short loc_18000CA83
0x18000ca0c  mov     rdx, [rsp+68h+Src]; Src
0x18000ca14  lea     r8, [rsi+rsi]; Size
0x18000ca18  mov     rcx, [r14]; void *
0x18000ca1b  call    memcpy_0
0x18000ca20  mov     rcx, [rsp+68h+arg_40]; struct _ITEMIDLIST *
0x18000ca28  test    rcx, rcx
0x18000ca2b  jz      short loc_18000CA3F
0x18000ca2d  lea     rdx, [rdi+430h]; struct _ITEMIDLIST **
0x18000ca34  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST@@PEAPEFAU1@@Z; SHILClone(_ITEMIDLIST const *,_ITEMIDLIST * *)
0x18000ca39  mov     ebx, eax
0x18000ca3b  test    eax, eax
0x18000ca3d  js      short loc_18000CA83
0x18000ca3f  mov     rdx, [rsp+68h+pUnk]; pUnk
0x18000ca47  test    rdx, rdx
0x18000ca4a  jnz     short loc_18000CA50
0x18000ca4c  xor     ebx, ebx
0x18000ca4e  jmp     short loc_18000CA6A
0x18000ca50  lea     r8, [rdi+438h]; ppStm
0x18000ca57  lea     rcx, IID_INewMenuClient; riid
0x18000ca5e  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x18000ca64  mov     ebx, eax
0x18000ca66  test    eax, eax
0x18000ca68  js      short loc_18000CA83
0x18000ca6a  mov     [r15], rdi
0x18000ca6d  mov     eax, ebx
0x18000ca6f  add     rsp, 38h
0x18000ca73  pop     r15
0x18000ca75  pop     r14
0x18000ca77  pop     rdi
0x18000ca78  pop     rsi
0x18000ca79  pop     rbp
0x18000ca7a  pop     rbx
0x18000ca7b  retn
0x18000ca7c  mov     ebx, 8007000Eh
0x18000ca81  jmp     short loc_18000CA6D
0x18000ca83  mov     rcx, rdi; struct THREADPARAMS *
0x18000ca86  call    ?FreeThreadParams@@YAXPEAUTHREADPARAMS@@@Z; FreeThreadParams(THREADPARAMS *)
0x18000ca8b  jmp     short loc_18000CA6D
```
