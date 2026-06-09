# _CreateScopeItemForLocation(IShellItem *,ILocationDescription *,IShellItem * *)

- ea: `0x18003f898`
- end: `0x18003f9b0`
- name: `?_CreateScopeItemForLocation@@YAJPEAUIShellItem@@PEAUILocationDescription@@PEAPEAU1@@Z`
- size: `280`
- prototype: `int(struct IShellItem *, struct ILocationDescription *, struct IShellItem **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003f34c`

## callees

- `0x18003e660`
- `0x18003f898`
- `0x180057010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18003f8cc`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18003f8cc`
- `SHELL32!SHCreateItemFromParsingName` at `0x18003f972`
- `SHELL32!SHCreateItemFromParsingName` at `0x18003f972`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f984`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f984`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003f937`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003f937`

## string_xrefs

- `0x18003f91e`: `LibraryDescriptionParsingPath`

## pseudocode

```c
__int64 __fastcall _CreateScopeItemForLocation(
        struct IShellItem *a1,
        struct ILocationDescription *a2,
        struct IShellItem **a3)
{
  HRESULT v5; // ebx
  const unsigned __int16 *v6; // rcx
  PROPVARIANT pvar[4]; // [rsp+20h] [rbp-20h] BYREF
  void *ppv; // [rsp+68h] [rbp+28h] BYREF
  PCWSTR pszPath; // [rsp+70h] [rbp+30h] BYREF

  *a3 = 0;
  ppv = 0;
  v5 = PSCreateMemoryPropertyStore(&GUID_71604b0f_97b0_4764_8577_2f13e98a1422, &ppv);
  if ( v5 >= 0 )
  {
    memset(pvar, 0, 24);
    LOWORD(pvar[0]) = 31;
    v5 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, PROPVARIANT *))a1->lpVtbl->GetDisplayName)(
           a1,
           2147844096LL,
           &pvar[1]);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(void *, const wchar_t *, PROPVARIANT *))(*(_QWORD *)ppv + 32LL))(
             ppv,
             L"LibraryDescriptionParsingPath",
             pvar);
      PropVariantClear(pvar);
      if ( v5 >= 0 )
      {
        pszPath = 0;
        v5 = SHGetParsingNameFromPropertyStore(v6, (struct INamedPropertyStore *)ppv, (unsigned __int16 **)&pszPath);
        if ( v5 >= 0 )
        {
          v5 = SHCreateItemFromParsingName(pszPath, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)a3);
          CoTaskMemFree((LPVOID)pszPath);
        }
      }
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003f898  mov     [rsp-18h+arg_0], rbx
0x18003f89d  mov     [rsp-18h+ppv], rdx
0x18003f8a2  push    rbp
0x18003f8a3  push    rsi
0x18003f8a4  push    rdi
0x18003f8a5  mov     rbp, rsp
0x18003f8a8  sub     rsp, 40h
0x18003f8ac  mov     rsi, rcx
0x18003f8af  mov     qword ptr [r8], 0
0x18003f8b6  lea     rcx, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422; riid
0x18003f8bd  mov     [rbp+ppv], 0
0x18003f8c5  lea     rdx, [rbp+ppv]; ppv
0x18003f8c9  mov     rdi, r8
0x18003f8cc  call    cs:__imp_PSCreateMemoryPropertyStore
0x18003f8d3  nop     dword ptr [rax+rax+00h]
0x18003f8d8  mov     ebx, eax
0x18003f8da  test    eax, eax
0x18003f8dc  js      loc_18003F9A0
0x18003f8e2  xor     eax, eax
0x18003f8e4  lea     r8, [rbp+var_18]
0x18003f8e8  mov     [rbp+var_10], rax
0x18003f8ec  xorps   xmm0, xmm0
0x18003f8ef  mov     eax, 1Fh
0x18003f8f4  mov     edx, 80058000h
0x18003f8f9  movups  xmmword ptr [rbp-20h], xmm0
0x18003f8fd  mov     word ptr [rbp+pvar], ax
0x18003f901  mov     rcx, rsi
0x18003f904  mov     rax, [rsi]
0x18003f907  mov     rax, [rax+28h]
0x18003f90b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f910  mov     ebx, eax
0x18003f912  test    eax, eax
0x18003f914  js      short loc_18003F990
0x18003f916  mov     rcx, [rbp+ppv]
0x18003f91a  lea     r8, [rbp+pvar]
0x18003f91e  lea     rdx, aLibrarydescrip; "LibraryDescriptionParsingPath"
0x18003f925  mov     rax, [rcx]
0x18003f928  mov     rax, [rax+20h]
0x18003f92c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f931  lea     rcx, [rbp+pvar]; pvar
0x18003f935  mov     ebx, eax
0x18003f937  call    cs:__imp_PropVariantClear
0x18003f93e  nop     dword ptr [rax+rax+00h]
0x18003f943  test    ebx, ebx
0x18003f945  js      short loc_18003F990
0x18003f947  mov     rdx, [rbp+ppv]; struct INamedPropertyStore *
0x18003f94b  lea     r8, [rbp+pszPath]; unsigned __int16 **
0x18003f94f  mov     [rbp+pszPath], 0
0x18003f957  call    ?SHGetParsingNameFromPropertyStore@@YAJPEBGPEAUINamedPropertyStore@@PEAPEAG@Z; SHGetParsingNameFromPropertyStore(ushort const *,INamedPropertyStore *,ushort * *)
0x18003f95c  mov     ebx, eax
0x18003f95e  test    eax, eax
0x18003f960  js      short loc_18003F990
0x18003f962  mov     rcx, [rbp+pszPath]; pszPath
0x18003f966  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18003f96d  mov     r9, rdi; ppv
0x18003f970  xor     edx, edx; pbc
0x18003f972  call    cs:__imp_SHCreateItemFromParsingName
0x18003f979  nop     dword ptr [rax+rax+00h]
0x18003f97e  mov     rcx, [rbp+pszPath]; pv
0x18003f982  mov     ebx, eax
0x18003f984  call    cs:__imp_CoTaskMemFree
0x18003f98b  nop     dword ptr [rax+rax+00h]
0x18003f990  mov     rcx, [rbp+ppv]
0x18003f994  mov     rax, [rcx]
0x18003f997  mov     rax, [rax+10h]
0x18003f99b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f9a0  mov     eax, ebx
0x18003f9a2  mov     rbx, [rsp+40h+arg_0]
0x18003f9a7  add     rsp, 40h
0x18003f9ab  pop     rdi
0x18003f9ac  pop     rsi
0x18003f9ad  pop     rbp
0x18003f9ae  retn
```
