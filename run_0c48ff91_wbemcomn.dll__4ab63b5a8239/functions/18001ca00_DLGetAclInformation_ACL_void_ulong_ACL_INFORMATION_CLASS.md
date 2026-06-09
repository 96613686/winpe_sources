# DLGetAclInformation(_ACL *,void *,ulong,_ACL_INFORMATION_CLASS)

- ea: `0x18001ca00`
- end: `0x18001ca81`
- name: `?DLGetAclInformation@@YAHPEAU_ACL@@PEAXKW4_ACL_INFORMATION_CLASS@@@Z`
- size: `129`
- prototype: `__int64 __fastcall(struct _ACL *, void *, unsigned int, enum _ACL_INFORMATION_CLASS)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001c6f0`

## callees

- `0x18001ca00`
- `0x18001d19c`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ca57`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ca57`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ca6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ca6d`

## string_xrefs

- `0x18001ca66`: `GetAclInformation`

## pseudocode

```c
__int64 __fastcall DLGetAclInformation(struct _ACL *a1, void *a2, __int64 a3, enum _ACL_INFORMATION_CLASS a4)
{
  FARPROC ProcAddress; // rax
  unsigned int v7; // ebx
  DWORD SecurityDll; // eax

  ProcAddress = (FARPROC)qword_1800703A0;
  if ( !qword_1800703A0 )
  {
    v7 = 0;
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      return v7;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "GetAclInformation");
    qword_1800703A0 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return v7;
  }
  return ((unsigned int (__fastcall *)(struct _ACL *, void *, __int64))ProcAddress)(a1, a2, 12);
}

```

## disassembly

```asm
0x18001ca00  mov     [rsp+arg_0], rbx
0x18001ca05  mov     [rsp+arg_8], rsi
0x18001ca0a  push    rdi
0x18001ca0b  sub     rsp, 30h
0x18001ca0f  mov     rax, cs:qword_1800703A0
0x18001ca16  mov     rdi, rdx
0x18001ca19  mov     rsi, rcx
0x18001ca1c  test    rax, rax
0x18001ca1f  jz      short loc_18001CA4A
0x18001ca21  mov     r9d, 2
0x18001ca27  mov     rdx, rdi
0x18001ca2a  mov     rcx, rsi
0x18001ca2d  lea     r8d, [r9+0Ah]
0x18001ca31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca36  mov     ebx, eax
0x18001ca38  mov     rsi, [rsp+38h+arg_8]
0x18001ca3d  mov     eax, ebx
0x18001ca3f  mov     rbx, [rsp+38h+arg_0]
0x18001ca44  add     rsp, 30h
0x18001ca48  pop     rdi
0x18001ca49  retn
0x18001ca4a  xor     ebx, ebx
0x18001ca4c  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001ca51  test    eax, eax
0x18001ca53  jz      short loc_18001CA5F
0x18001ca55  mov     ecx, eax; dwErrCode
0x18001ca57  call    cs:__imp_SetLastError
0x18001ca5d  jmp     short loc_18001CA38
0x18001ca5f  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001ca66  lea     rdx, aGetaclinformat; "GetAclInformation"
0x18001ca6d  call    cs:__imp_GetProcAddress
0x18001ca73  mov     cs:qword_1800703A0, rax
0x18001ca7a  test    rax, rax
0x18001ca7d  jz      short loc_18001CA38
0x18001ca7f  jmp     short loc_18001CA21
```
