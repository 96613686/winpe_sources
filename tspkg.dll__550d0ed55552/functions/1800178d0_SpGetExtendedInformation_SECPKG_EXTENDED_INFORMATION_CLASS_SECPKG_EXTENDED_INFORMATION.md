# SpGetExtendedInformation(_SECPKG_EXTENDED_INFORMATION_CLASS,_SECPKG_EXTENDED_INFORMATION * *)

- ea: `0x1800178d0`
- end: `0x180017959`
- name: `?SpGetExtendedInformation@@YAJW4_SECPKG_EXTENDED_INFORMATION_CLASS@@PEAPEAU_SECPKG_EXTENDED_INFORMATION@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(enum _SECPKG_EXTENDED_INFORMATION_CLASS, struct _SECPKG_EXTENDED_INFORMATION **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800178d0`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001792f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001792f`

## string_xrefs

- `0x180017926`: `%SystemRoot%\SysWOW64\TsPkg.DLL`

## pseudocode

```c
__int64 __fastcall SpGetExtendedInformation(
        enum _SECPKG_EXTENDED_INFORMATION_CLASS a1,
        struct _SECPKG_EXTENDED_INFORMATION **a2)
{
  __int64 v4; // rax
  struct _SECPKG_EXTENDED_INFORMATION *v5; // rbx
  unsigned int v6; // edi
  unsigned __int16 v7; // ax

  if ( a1 != SecpkgWowClientDll )
    return 3221225475LL;
  v4 = ((__int64 (__fastcall *)(__int64))TSGlobalLsaFunctions->AllocateLsaHeap)(576);
  v5 = (struct _SECPKG_EXTENDED_INFORMATION *)v4;
  if ( v4 )
  {
    *(_DWORD *)v4 = 4;
    *(_QWORD *)(v4 + 16) = v4 + 56;
    v6 = 0;
    v7 = 2 * ExpandEnvironmentStringsW(L"%SystemRoot%\\SysWOW64\\TsPkg.DLL", (LPWSTR)(v4 + 56), 0x104u);
    v5->Info.WowClientDll.WowClientDllPath.Length = v7;
    v5->Info.WowClientDll.WowClientDllPath.MaximumLength = v7 + 2;
    *a2 = v5;
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v6;
}

```

## disassembly

```asm
0x1800178d0  mov     [rsp+arg_0], rbx
0x1800178d5  mov     [rsp+arg_8], rsi
0x1800178da  push    rdi
0x1800178db  sub     rsp, 20h
0x1800178df  mov     rsi, rdx
0x1800178e2  cmp     ecx, 4
0x1800178e5  jz      short loc_1800178EE
0x1800178e7  mov     eax, 0C0000003h
0x1800178ec  jmp     short loc_180017949
0x1800178ee  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x1800178f5  mov     ecx, 240h
0x1800178fa  mov     rax, [rax+28h]
0x1800178fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017903  mov     rbx, rax
0x180017906  test    rax, rax
0x180017909  jnz     short loc_180017912
0x18001790b  mov     edi, 0C000009Ah
0x180017910  jmp     short loc_180017947
0x180017912  lea     rdx, [rax+38h]; lpDst
0x180017916  mov     dword ptr [rax], 4
0x18001791c  mov     r8d, 104h; nSize
0x180017922  mov     [rax+10h], rdx
0x180017926  lea     rcx, Src; "%SystemRoot%\\SysWOW64\\TsPkg.DLL"
0x18001792d  xor     edi, edi
0x18001792f  call    cs:__imp_ExpandEnvironmentStringsW
0x180017935  add     ax, ax
0x180017938  mov     [rbx+8], ax
0x18001793c  add     ax, 2
0x180017940  mov     [rbx+0Ah], ax
0x180017944  mov     [rsi], rbx
0x180017947  mov     eax, edi
0x180017949  mov     rbx, [rsp+28h+arg_0]
0x18001794e  mov     rsi, [rsp+28h+arg_8]
0x180017953  add     rsp, 20h
0x180017957  pop     rdi
0x180017958  retn
```
