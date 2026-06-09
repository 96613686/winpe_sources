# CNtSecurityDescriptor::SetDacl(CNtAcl *)

- ea: `0x180023a60`
- end: `0x180023b11`
- name: `?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(CNtSecurityDescriptor *__hidden this, struct CNtAcl *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003d310`
- `0x18003f730`

## callees

- `0x180009fd0`
- `0x18001d19c`
- `0x180023a60`
- `0x180023b18`
- `0x180023b40`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023ae7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023ae7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023afd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023afd`

## string_xrefs

- `0x180023af6`: `SetSecurityDescriptorDacl`

## pseudocode

```c
__int64 __fastcall CNtSecurityDescriptor::SetDacl(CNtSecurityDescriptor *this, struct CNtAcl *a2)
{
  struct SNtAbsoluteSD *AbsoluteCopy; // rax
  void **v5; // rdi
  __int64 v6; // rbp
  FARPROC ProcAddress; // rax
  __int64 v8; // rsi
  unsigned int v9; // edx
  unsigned int v10; // ebx
  unsigned int v11; // edx
  DWORD SecurityDll; // eax

  if ( *((_DWORD *)this + 2) )
    return 0;
  if ( !*(_QWORD *)this )
    return 0;
  AbsoluteCopy = CNtSecurityDescriptor::GetAbsoluteCopy(this);
  v5 = (void **)AbsoluteCopy;
  if ( !AbsoluteCopy )
    return 0;
  v6 = *(_QWORD *)AbsoluteCopy;
  ProcAddress = (FARPROC)qword_180070318;
  v8 = *(_QWORD *)a2;
  if ( qword_180070318 )
    goto LABEL_5;
  SecurityDll = DLpLoadSecurityDll();
  if ( SecurityDll )
  {
    SetLastError(SecurityDll);
  }
  else
  {
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "SetSecurityDescriptorDacl");
    qword_180070318 = (__int64)ProcAddress;
    if ( ProcAddress )
    {
LABEL_5:
      if ( ((unsigned int (__fastcall *)(__int64, __int64, __int64))ProcAddress)(v6, 1, v8) )
      {
        v10 = CNtSecurityDescriptor::SetFromAbsoluteCopy((void **)this, v5);
        SNtAbsoluteSD::`scalar deleting destructor'((SNtAbsoluteSD *)v5, v11);
        return v10;
      }
    }
  }
  SNtAbsoluteSD::`scalar deleting destructor'((SNtAbsoluteSD *)v5, v9);
  return 0;
}

```

## disassembly

```asm
0x180023a60  push    rbx
0x180023a62  push    rbp
0x180023a63  push    rsi
0x180023a64  push    rdi
0x180023a65  sub     rsp, 38h
0x180023a69  cmp     dword ptr [rcx+8], 0
0x180023a6d  mov     rsi, rdx
0x180023a70  mov     rbx, rcx
0x180023a73  jnz     short loc_180023AD8
0x180023a75  cmp     qword ptr [rcx], 0
0x180023a79  jz      short loc_180023AD8
0x180023a7b  call    ?GetAbsoluteCopy@CNtSecurityDescriptor@@QEAAPEAUSNtAbsoluteSD@@XZ; CNtSecurityDescriptor::GetAbsoluteCopy(void)
0x180023a80  mov     rdi, rax
0x180023a83  test    rax, rax
0x180023a86  jz      short loc_180023AD8
0x180023a88  mov     rbp, [rax]
0x180023a8b  mov     rax, cs:qword_180070318
0x180023a92  mov     rsi, [rsi]
0x180023a95  test    rax, rax
0x180023a98  jz      short loc_180023ADC
0x180023a9a  xor     r9d, r9d
0x180023a9d  mov     r8, rsi
0x180023aa0  mov     rcx, rbp
0x180023aa3  lea     edx, [r9+1]
0x180023aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023aac  test    eax, eax
0x180023aae  jz      short loc_180023AD0
0x180023ab0  mov     rdx, rdi; struct SNtAbsoluteSD *
0x180023ab3  mov     rcx, rbx; this
0x180023ab6  call    ?SetFromAbsoluteCopy@CNtSecurityDescriptor@@QEAAHPEAUSNtAbsoluteSD@@@Z; CNtSecurityDescriptor::SetFromAbsoluteCopy(SNtAbsoluteSD *)
0x180023abb  mov     rcx, rdi; this
0x180023abe  mov     ebx, eax
0x180023ac0  call    ??_GSNtAbsoluteSD@@QEAAPEAXI@Z; SNtAbsoluteSD::`scalar deleting destructor'(uint)
0x180023ac5  mov     eax, ebx
0x180023ac7  add     rsp, 38h
0x180023acb  pop     rdi
0x180023acc  pop     rsi
0x180023acd  pop     rbp
0x180023ace  pop     rbx
0x180023acf  retn
0x180023ad0  mov     rcx, rdi; this
0x180023ad3  call    ??_GSNtAbsoluteSD@@QEAAPEAXI@Z; SNtAbsoluteSD::`scalar deleting destructor'(uint)
0x180023ad8  xor     eax, eax
0x180023ada  jmp     short loc_180023AC7
0x180023adc  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x180023ae1  test    eax, eax
0x180023ae3  jz      short loc_180023AEF
0x180023ae5  mov     ecx, eax; dwErrCode
0x180023ae7  call    cs:__imp_SetLastError
0x180023aed  jmp     short loc_180023AD0
0x180023aef  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180023af6  lea     rdx, aSetsecuritydes_3; "SetSecurityDescriptorDacl"
0x180023afd  call    cs:__imp_GetProcAddress
0x180023b03  mov     cs:qword_180070318, rax
0x180023b0a  test    rax, rax
0x180023b0d  jz      short loc_180023AD0
0x180023b0f  jmp     short loc_180023A9A
```
