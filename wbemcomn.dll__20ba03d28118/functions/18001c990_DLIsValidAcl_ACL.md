# DLIsValidAcl(_ACL *)

- ea: `0x18001c990`
- end: `0x18001c9f7`
- name: `?DLIsValidAcl@@YAHPEAU_ACL@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(struct _ACL *)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001b490`
- `0x18001b7d0`
- `0x18001c6f0`
- `0x18001c790`
- `0x18001c900`
- `0x18001d360`
- `0x18003e4e0`

## callees

- `0x18001c990`
- `0x18001d19c`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c9cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c9cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c9e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c9e3`

## string_xrefs

- `0x18001c9dc`: `IsValidAcl`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DLIsValidAcl(struct _ACL *a1)
{
  FARPROC ProcAddress; // rax
  unsigned int v3; // ebx
  DWORD SecurityDll; // eax

  ProcAddress = (FARPROC)qword_180070308;
  if ( !qword_180070308 )
  {
    v3 = 0;
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      return v3;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "IsValidAcl");
    qword_180070308 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return v3;
  }
  return ((unsigned int (__fastcall *)(struct _ACL *))ProcAddress)(a1);
}

```

## disassembly

```asm
0x18001c990  mov     [rsp+arg_0], rbx
0x18001c995  push    rdi
0x18001c996  sub     rsp, 20h
0x18001c99a  mov     rax, cs:qword_180070308
0x18001c9a1  mov     rdi, rcx
0x18001c9a4  test    rax, rax
0x18001c9a7  jz      short loc_18001C9C0
0x18001c9a9  mov     rcx, rdi
0x18001c9ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9b1  mov     ebx, eax
0x18001c9b3  mov     eax, ebx
0x18001c9b5  mov     rbx, [rsp+28h+arg_0]
0x18001c9ba  add     rsp, 20h
0x18001c9be  pop     rdi
0x18001c9bf  retn
0x18001c9c0  xor     ebx, ebx
0x18001c9c2  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001c9c7  test    eax, eax
0x18001c9c9  jz      short loc_18001C9D5
0x18001c9cb  mov     ecx, eax; dwErrCode
0x18001c9cd  call    cs:__imp_SetLastError
0x18001c9d3  jmp     short loc_18001C9B3
0x18001c9d5  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001c9dc  lea     rdx, aIsvalidacl; "IsValidAcl"
0x18001c9e3  call    cs:__imp_GetProcAddress
0x18001c9e9  mov     cs:qword_180070308, rax
0x18001c9f0  test    rax, rax
0x18001c9f3  jz      short loc_18001C9B3
0x18001c9f5  jmp     short loc_18001C9A9
```
