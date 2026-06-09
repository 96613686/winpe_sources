# DLAdjustTokenPrivileges(void *,int,_TOKEN_PRIVILEGES *,ulong,_TOKEN_PRIVILEGES *,ulong *)

- ea: `0x180025634`
- end: `0x1800256b8`
- name: `?DLAdjustTokenPrivileges@@YAHPEAXHPEAU_TOKEN_PRIVILEGES@@K1PEAK@Z`
- size: `132`
- prototype: `__int64 __fastcall(void *, int, struct _TOKEN_PRIVILEGES *, unsigned int, struct _TOKEN_PRIVILEGES *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180034850`

## callees

- `0x18001d19c`
- `0x180025634`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002568e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002568e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800256a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800256a4`

## string_xrefs

- `0x18002569d`: `AdjustTokenPrivileges`

## pseudocode

```c
__int64 __fastcall DLAdjustTokenPrivileges(void *a1, __int64 a2, struct _TOKEN_PRIVILEGES *a3, unsigned int a4)
{
  FARPROC ProcAddress; // rax
  unsigned int v8; // ebx
  DWORD SecurityDll; // eax

  ProcAddress = (FARPROC)qword_180070380;
  if ( !qword_180070380 )
  {
    v8 = 0;
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      return v8;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "AdjustTokenPrivileges");
    qword_180070380 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return v8;
  }
  return ((unsigned int (__fastcall *)(void *, _QWORD, struct _TOKEN_PRIVILEGES *, _QWORD, _QWORD, _QWORD))ProcAddress)(
           a1,
           0,
           a3,
           a4,
           0,
           0);
}

```

## disassembly

```asm
0x180025634  push    rbx
0x180025636  push    rbp
0x180025637  push    rsi
0x180025638  push    rdi
0x180025639  sub     rsp, 48h
0x18002563d  mov     rax, cs:qword_180070380
0x180025644  mov     edi, r9d
0x180025647  mov     rsi, r8
0x18002564a  mov     rbp, rcx
0x18002564d  test    rax, rax
0x180025650  jz      short loc_180025681
0x180025652  mov     [rsp+68h+var_40], 0
0x18002565b  mov     r9d, edi
0x18002565e  mov     r8, rsi
0x180025661  mov     [rsp+68h+var_48], 0
0x18002566a  xor     edx, edx
0x18002566c  mov     rcx, rbp
0x18002566f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025674  mov     ebx, eax
0x180025676  mov     eax, ebx
0x180025678  add     rsp, 48h
0x18002567c  pop     rdi
0x18002567d  pop     rsi
0x18002567e  pop     rbp
0x18002567f  pop     rbx
0x180025680  retn
0x180025681  xor     ebx, ebx
0x180025683  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x180025688  test    eax, eax
0x18002568a  jz      short loc_180025696
0x18002568c  mov     ecx, eax; dwErrCode
0x18002568e  call    cs:__imp_SetLastError
0x180025694  jmp     short loc_180025676
0x180025696  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18002569d  lea     rdx, aAdjusttokenpri; "AdjustTokenPrivileges"
0x1800256a4  call    cs:__imp_GetProcAddress
0x1800256aa  mov     cs:qword_180070380, rax
0x1800256b1  test    rax, rax
0x1800256b4  jz      short loc_180025676
0x1800256b6  jmp     short loc_180025652
```
