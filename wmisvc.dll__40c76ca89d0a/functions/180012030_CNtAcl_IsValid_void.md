# CNtAcl::IsValid(void)

- ea: `0x180012030`
- end: `0x180012096`
- name: `?IsValid@CNtAcl@@QEAAHXZ`
- size: `102`
- prototype: `_BOOL8 __fastcall(CNtAcl *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180012030`
- `0x180017008`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012071`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012071`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012055`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012055`

## string_xrefs

- `0x18001206a`: `IsValidAcl`

## pseudocode

```c
_BOOL8 __fastcall CNtAcl::IsValid(CNtAcl *this)
{
  __int64 v1; // rbx
  FARPROC ProcAddress; // rax
  DWORD SecurityDll; // eax

  v1 = *(_QWORD *)this;
  if ( !*(_QWORD *)this )
    return 0;
  ProcAddress = (FARPROC)qword_180032D48;
  if ( !qword_180032D48 )
  {
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      return 0;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "IsValidAcl");
    qword_180032D48 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return 0;
  }
  return ((unsigned int (__fastcall *)(__int64))ProcAddress)(v1) != 0;
}

```

## disassembly

```asm
0x180012030  push    rbx
0x180012032  sub     rsp, 20h
0x180012036  mov     rbx, [rcx]
0x180012039  test    rbx, rbx
0x18001203c  jz      short loc_18001205B
0x18001203e  mov     rax, cs:qword_180032D48
0x180012045  test    rax, rax
0x180012048  jnz     short loc_180012083
0x18001204a  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001204f  test    eax, eax
0x180012051  jz      short loc_180012063
0x180012053  mov     ecx, eax; dwErrCode
0x180012055  call    cs:__imp_SetLastError
0x18001205b  xor     eax, eax
0x18001205d  add     rsp, 20h
0x180012061  pop     rbx
0x180012062  retn
0x180012063  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001206a  lea     rdx, aIsvalidacl; "IsValidAcl"
0x180012071  call    cs:__imp_GetProcAddress
0x180012077  mov     cs:qword_180032D48, rax
0x18001207e  test    rax, rax
0x180012081  jz      short loc_18001205B
0x180012083  mov     rcx, rbx
0x180012086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001208b  test    eax, eax
0x18001208d  jz      short loc_18001205B
0x18001208f  mov     eax, 1
0x180012094  jmp     short loc_18001205D
```
