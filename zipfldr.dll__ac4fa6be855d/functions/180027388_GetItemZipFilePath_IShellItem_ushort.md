# _GetItemZipFilePath(IShellItem *,ushort * *)

- ea: `0x180027388`
- end: `0x180027448`
- name: `?_GetItemZipFilePath@@YAJPEAUIShellItem@@PEAPEAG@Z`
- size: `192`
- prototype: `__int64 __fastcall(struct IShellItem *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800272f8`
- `0x180040630`

## callees

- `0x180027388`
- `0x180036f50`
- `0x180071010`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x1800273fa`
- `SHLWAPI!PathFindExtensionW` at `0x1800273fa`
- `SHLWAPI!__imp_StrCmpICW` at `0x18002740a`
- `SHLWAPI!__imp_StrCmpICW` at `0x18002740a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002741c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002741c`

## pseudocode

```c
__int64 __fastcall _GetItemZipFilePath(struct IShellItem *a1, LPCWSTR *a2)
{
  struct IShellItemVtbl *lpVtbl; // rax
  int v5; // edi
  const WCHAR *ExtensionW; // rax
  int v8; // [rsp+20h] [rbp-18h] BYREF

  *a2 = 0;
  lpVtbl = a1->lpVtbl;
  v8 = 0;
  v5 = -2147467259;
  if ( !((unsigned int (__fastcall *)(struct IShellItem *, __int64, int *))lpVtbl->GetAttributes)(a1, 0x400000, &v8) )
  {
    v5 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, LPCWSTR *))a1->lpVtbl->GetDisplayName)(
           a1,
           2147844096LL,
           a2);
    if ( v5 >= 0 )
    {
      ExtensionW = PathFindExtensionW(*a2);
      if ( StrCmpICW(ExtensionW, L".zip") )
      {
        v5 = -2147467259;
        CoTaskMemFree((LPVOID)*a2);
        *a2 = 0;
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180027388  mov     [rsp+arg_10], rbx
0x18002738d  mov     [rsp+arg_18], rsi
0x180027392  push    rdi
0x180027393  sub     rsp, 30h
0x180027397  mov     rax, cs:__security_cookie
0x18002739e  xor     rax, rsp
0x1800273a1  mov     [rsp+38h+var_10], rax
0x1800273a6  mov     qword ptr [rdx], 0
0x1800273ad  lea     r8, [rsp+38h+var_18]
0x1800273b2  mov     rax, [rcx]
0x1800273b5  mov     rbx, rdx
0x1800273b8  mov     edx, 400000h
0x1800273bd  mov     [rsp+38h+var_18], 0
0x1800273c5  mov     rsi, rcx
0x1800273c8  mov     edi, 80004005h
0x1800273cd  mov     rax, [rax+30h]
0x1800273d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273d6  test    eax, eax
0x1800273d8  jnz     short loc_180027429
0x1800273da  mov     rax, [rsi]
0x1800273dd  mov     r8, rbx
0x1800273e0  mov     edx, 80058000h
0x1800273e5  mov     rcx, rsi
0x1800273e8  mov     rax, [rax+28h]
0x1800273ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273f1  mov     edi, eax
0x1800273f3  test    eax, eax
0x1800273f5  js      short loc_180027429
0x1800273f7  mov     rcx, [rbx]; pszPath
0x1800273fa  call    cs:__imp_PathFindExtensionW
0x180027400  mov     rcx, rax; pszStr1
0x180027403  lea     rdx, aZip; ".zip"
0x18002740a  call    cs:__imp_StrCmpICW
0x180027410  test    eax, eax
0x180027412  jz      short loc_180027429
0x180027414  mov     rcx, [rbx]; pv
0x180027417  mov     edi, 80004005h
0x18002741c  call    cs:__imp_CoTaskMemFree
0x180027422  mov     qword ptr [rbx], 0
0x180027429  mov     eax, edi
0x18002742b  mov     rcx, [rsp+38h+var_10]
0x180027430  xor     rcx, rsp; StackCookie
0x180027433  call    __security_check_cookie
0x180027438  mov     rbx, [rsp+38h+arg_10]
0x18002743d  mov     rsi, [rsp+38h+arg_18]
0x180027442  add     rsp, 30h
0x180027446  pop     rdi
0x180027447  retn
```
