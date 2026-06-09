# DLIsValidSid(void *)

- ea: `0x18001c4fc`
- end: `0x18001c563`
- name: `?DLIsValidSid@@YAHPEAX@Z`
- size: `103`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `11`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001bb20`
- `0x18001c2d0`
- `0x18001c4d0`
- `0x180023160`
- `0x18003aac0`
- `0x18003cef0`
- `0x18003d030`
- `0x18003d1d0`
- `0x18003e520`
- `0x18003e5a0`
- `0x18003e600`

## callees

- `0x18001c4fc`
- `0x18001d19c`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c55b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c55b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c545`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c545`

## string_xrefs

- `0x18001c53e`: `IsValidSid`

## pseudocode

```c
__int64 __fastcall DLIsValidSid(void *a1)
{
  FARPROC ProcAddress; // rax
  unsigned int v3; // ebx
  DWORD SecurityDll; // eax

  ProcAddress = (FARPROC)qword_1800702F8;
  if ( !qword_1800702F8 )
  {
    v3 = 0;
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      return v3;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "IsValidSid");
    qword_1800702F8 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return v3;
  }
  return ((unsigned int (__fastcall *)(void *))ProcAddress)(a1);
}

```

## disassembly

```asm
0x18001c4fc  mov     [rsp+arg_0], rbx
0x18001c501  push    rdi
0x18001c502  sub     rsp, 20h
0x18001c506  mov     rax, cs:qword_1800702F8
0x18001c50d  mov     rdi, rcx
0x18001c510  test    rax, rax
0x18001c513  jz      short loc_18001C52C
0x18001c515  mov     rcx, rdi
0x18001c518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c51d  mov     ebx, eax
0x18001c51f  mov     eax, ebx
0x18001c521  mov     rbx, [rsp+28h+arg_0]
0x18001c526  add     rsp, 20h
0x18001c52a  pop     rdi
0x18001c52b  retn
0x18001c52c  xor     ebx, ebx
0x18001c52e  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001c533  test    eax, eax
0x18001c535  jnz     short loc_18001C559
0x18001c537  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001c53e  lea     rdx, aIsvalidsid; "IsValidSid"
0x18001c545  call    cs:__imp_GetProcAddress
0x18001c54b  mov     cs:qword_1800702F8, rax
0x18001c552  test    rax, rax
0x18001c555  jnz     short loc_18001C515
0x18001c557  jmp     short loc_18001C51F
0x18001c559  mov     ecx, eax; dwErrCode
0x18001c55b  call    cs:__imp_SetLastError
0x18001c561  jmp     short loc_18001C51F
```
