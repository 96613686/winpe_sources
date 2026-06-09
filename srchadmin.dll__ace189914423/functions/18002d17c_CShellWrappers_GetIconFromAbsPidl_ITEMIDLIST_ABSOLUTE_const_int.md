# CShellWrappers::GetIconFromAbsPidl(_ITEMIDLIST_ABSOLUTE const *,int *)

- ea: `0x18002d17c`
- end: `0x18002d2cb`
- name: `?GetIconFromAbsPidl@CShellWrappers@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAH@Z`
- size: `335`
- prototype: `int(CShellWrappers *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001681c`
- `0x180024950`

## callees

- `0x1800038ac`
- `0x180005cc0`
- `0x18002d17c`
- `0x180032010`

## import_xrefs

- `SHELL32!SHBindToParent` at `0x18002d1d3`
- `SHELL32!SHBindToParent` at `0x18002d1d3`
- `SHELL32!__imp_Shell_GetCachedImageIndex` at `0x18002d28a`
- `SHELL32!__imp_Shell_GetCachedImageIndex` at `0x18002d28a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CShellWrappers::GetIconFromAbsPidl(CShellWrappers *this, const ITEMIDLIST *a2, int *a3)
{
  HRESULT v5; // edi
  int CachedImageIndex; // eax
  int v8; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v9; // [rsp+48h] [rbp-B8h] BYREF
  void *ppv; // [rsp+50h] [rbp-B0h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pwszIconPath[264]; // [rsp+60h] [rbp-A0h] BYREF

  ppv = 0;
  ppidlLast = 0;
  v5 = SHBindToParent(a2, &GUID_000214e6_0000_0000_c000_000000000046, &ppv, &ppidlLast);
  if ( v5 >= 0 )
  {
    v9 = 0;
    v5 = (*(__int64 (__fastcall **)(void *, _QWORD, __int64, LPCITEMIDLIST *, GUID *, _QWORD, __int64 *))(*(_QWORD *)ppv + 80LL))(
           ppv,
           0,
           1,
           &ppidlLast,
           &GUID_000214fa_0000_0000_c000_000000000046,
           0,
           &v9);
    if ( v5 < 0 )
      goto LABEL_9;
    v8 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, WCHAR *, __int64, int *, int *))(*(_QWORD *)v9 + 24LL))(
           v9,
           0,
           pwszIconPath,
           260,
           a3,
           &v8);
    if ( v5 < 0 )
      goto LABEL_9;
    if ( (v8 & 8) != 0 )
    {
      if ( pwszIconPath[0] == 42 )
      {
LABEL_9:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
        goto LABEL_10;
      }
      CachedImageIndex = *((_DWORD *)this + 5);
    }
    else
    {
      CachedImageIndex = Shell_GetCachedImageIndex(pwszIconPath, *a3, 0);
    }
    *a3 = CachedImageIndex;
    goto LABEL_9;
  }
LABEL_10:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002d17c  mov     [rsp-8+arg_0], rbx
0x18002d181  push    rbp
0x18002d182  push    rsi
0x18002d183  push    rdi
0x18002d184  lea     rbp, [rsp-180h]
0x18002d18c  sub     rsp, 280h
0x18002d193  mov     rax, cs:__security_cookie
0x18002d19a  xor     rax, rsp
0x18002d19d  mov     [rbp+190h+var_20], rax
0x18002d1a4  mov     rbx, r8
0x18002d1a7  mov     rax, rdx
0x18002d1aa  mov     rsi, rcx
0x18002d1ad  mov     [rsp+290h+ppv], 0
0x18002d1b6  mov     [rsp+290h+ppidlLast], 0
0x18002d1bf  lea     r9, [rsp+290h+ppidlLast]; ppidlLast
0x18002d1c4  lea     r8, [rsp+290h+ppv]; ppv
0x18002d1c9  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18002d1d0  mov     rcx, rax; pidl
0x18002d1d3  call    cs:__imp_SHBindToParent
0x18002d1d9  mov     edi, eax
0x18002d1db  test    eax, eax
0x18002d1dd  js      loc_18002D29D
0x18002d1e3  mov     [rsp+290h+var_248], 0
0x18002d1ec  mov     rcx, [rsp+290h+ppv]
0x18002d1f1  mov     rax, [rcx]
0x18002d1f4  lea     rdx, [rsp+290h+var_248]
0x18002d1f9  mov     [rsp+290h+var_260], rdx
0x18002d1fe  mov     [rsp+290h+var_268], 0
0x18002d207  lea     rdx, _GUID_000214fa_0000_0000_c000_000000000046
0x18002d20e  mov     [rsp+290h+var_270], rdx
0x18002d213  lea     r9, [rsp+290h+ppidlLast]
0x18002d218  xor     edx, edx
0x18002d21a  lea     r8d, [rdx+1]
0x18002d21e  mov     rax, [rax+50h]
0x18002d222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d227  mov     edi, eax
0x18002d229  test    eax, eax
0x18002d22b  js      short loc_18002D292
0x18002d22d  mov     [rsp+290h+var_250], 0
0x18002d235  mov     rcx, [rsp+290h+var_248]
0x18002d23a  mov     rax, [rcx]
0x18002d23d  lea     rdx, [rsp+290h+var_250]
0x18002d242  mov     [rsp+290h+var_268], rdx
0x18002d247  mov     [rsp+290h+var_270], rbx
0x18002d24c  mov     r9d, 104h
0x18002d252  lea     r8, [rsp+290h+pwszIconPath]
0x18002d257  xor     edx, edx
0x18002d259  mov     rax, [rax+18h]
0x18002d25d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d262  mov     edi, eax
0x18002d264  test    eax, eax
0x18002d266  js      short loc_18002D292
0x18002d268  test    byte ptr [rsp+290h+var_250], 8
0x18002d26d  jz      short loc_18002D280
0x18002d26f  mov     eax, 2Ah ; '*'
0x18002d274  cmp     ax, [rsp+290h+pwszIconPath]
0x18002d279  jz      short loc_18002D292
0x18002d27b  mov     eax, [rsi+14h]
0x18002d27e  jmp     short loc_18002D290
0x18002d280  xor     r8d, r8d; uIconFlags
0x18002d283  mov     edx, [rbx]; iIconIndex
0x18002d285  lea     rcx, [rsp+290h+pwszIconPath]; pwszIconPath
0x18002d28a  call    cs:__imp_Shell_GetCachedImageIndex
0x18002d290  mov     [rbx], eax
0x18002d292  lea     rcx, [rsp+290h+var_248]
0x18002d297  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002d29c  nop
0x18002d29d  lea     rcx, [rsp+290h+ppv]
0x18002d2a2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002d2a7  mov     eax, edi
0x18002d2a9  mov     rcx, [rbp+190h+var_20]
0x18002d2b0  xor     rcx, rsp; StackCookie
0x18002d2b3  call    __security_check_cookie
0x18002d2b8  mov     rbx, [rsp+290h+arg_0]
0x18002d2c0  add     rsp, 280h
0x18002d2c7  pop     rdi
0x18002d2c8  pop     rsi
0x18002d2c9  pop     rbp
0x18002d2ca  retn
```
