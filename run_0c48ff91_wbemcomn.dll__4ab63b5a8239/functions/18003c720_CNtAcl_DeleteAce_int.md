# CNtAcl::DeleteAce(int)

- ea: `0x18003c720`
- end: `0x18003c79c`
- name: `?DeleteAce@CNtAcl@@QEAAHH@Z`
- size: `124`
- prototype: `__int64 __fastcall(CNtAcl *__hidden this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001d19c`
- `0x18003c720`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c756`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c756`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c76c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c76c`

## string_xrefs

- `0x18003c765`: `DeleteAce`

## pseudocode

```c
__int64 __fastcall CNtAcl::DeleteAce(CNtAcl *this, unsigned int a2)
{
  __int64 v2; // rdi
  FARPROC ProcAddress; // rax
  unsigned int v6; // ebx
  DWORD SecurityDll; // eax

  v2 = *(_QWORD *)this;
  if ( !*(_QWORD *)this )
    return 0;
  ProcAddress = (FARPROC)qword_180070358;
  if ( qword_180070358 )
    return ((unsigned int (__fastcall *)(__int64, _QWORD))ProcAddress)(v2, a2);
  v6 = 0;
  SecurityDll = DLpLoadSecurityDll();
  if ( !SecurityDll )
  {
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "DeleteAce");
    qword_180070358 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return v6;
    return ((unsigned int (__fastcall *)(__int64, _QWORD))ProcAddress)(v2, a2);
  }
  SetLastError(SecurityDll);
  return v6;
}

```

## disassembly

```asm
0x18003c720  mov     [rsp+arg_0], rbx
0x18003c725  mov     [rsp+arg_8], rsi
0x18003c72a  push    rdi
0x18003c72b  sub     rsp, 20h
0x18003c72f  mov     rdi, [rcx]
0x18003c732  mov     esi, edx
0x18003c734  test    rdi, rdi
0x18003c737  jnz     short loc_18003C73D
0x18003c739  xor     eax, eax
0x18003c73b  jmp     short loc_18003C78C
0x18003c73d  mov     rax, cs:qword_180070358
0x18003c744  test    rax, rax
0x18003c747  jnz     short loc_18003C77E
0x18003c749  xor     ebx, ebx
0x18003c74b  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18003c750  test    eax, eax
0x18003c752  jz      short loc_18003C75E
0x18003c754  mov     ecx, eax; dwErrCode
0x18003c756  call    cs:__imp_SetLastError
0x18003c75c  jmp     short loc_18003C78A
0x18003c75e  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18003c765  lea     rdx, aDeleteace; "DeleteAce"
0x18003c76c  call    cs:__imp_GetProcAddress
0x18003c772  mov     cs:qword_180070358, rax
0x18003c779  test    rax, rax
0x18003c77c  jz      short loc_18003C78A
0x18003c77e  mov     edx, esi
0x18003c780  mov     rcx, rdi
0x18003c783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c788  mov     ebx, eax
0x18003c78a  mov     eax, ebx
0x18003c78c  mov     rbx, [rsp+28h+arg_0]
0x18003c791  mov     rsi, [rsp+28h+arg_8]
0x18003c796  add     rsp, 20h
0x18003c79a  pop     rdi
0x18003c79b  retn
```
