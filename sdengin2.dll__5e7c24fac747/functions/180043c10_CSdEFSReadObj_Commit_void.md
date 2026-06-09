# CSdEFSReadObj::Commit(void)

- ea: `0x180043c10`
- end: `0x180043e92`
- name: `?Commit@CSdEFSReadObj@@UEAAJXZ`
- size: `642`
- prototype: `__int64 __fastcall(PVOID pvCallbackContext)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180043c10`
- `0x180046744`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x18008f660`
- `0x1800c9830`
- `0x1800cb010`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x180043df5`
- `ntdll!NtSetInformationFile` at `0x180043df5`
- `KERNEL32!DeleteFileW` at `0x180043e47`
- `KERNEL32!DeleteFileW` at `0x180043e47`
- `KERNEL32!CreateFileW` at `0x180043cf9`
- `KERNEL32!CreateFileW` at `0x180043cf9`
- `KERNEL32!CloseHandle` at `0x180043e32`
- `KERNEL32!CloseHandle` at `0x180043e5d`
- `KERNEL32!CloseHandle` at `0x180043e32`
- `KERNEL32!CloseHandle` at `0x180043e5d`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180043d84`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180043d84`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180043d49`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180043d49`

## string_xrefs

- `0x180043c47`: `CSdEFSReadObj::Commit`

## pseudocode

```c
__int64 __fastcall CSdEFSReadObj::Commit(PVOID pvCallbackContext)
{
  __int64 FileW; // rbx
  __int16 v3; // ax
  __int64 v4; // rcx
  void *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // esi
  WINBOOL bDaclPresent; // [rsp+40h] [rbp-49h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+44h] [rbp-45h] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-41h] BYREF
  __int16 v14; // [rsp+4Ch] [rbp-3Dh]
  __int16 v15; // [rsp+4Eh] [rbp-3Bh]
  PACL pDacl; // [rsp+80h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-1h] BYREF
  _BYTE FileInformation[36]; // [rsp+98h] [rbp+Fh] BYREF
  int v19; // [rsp+BCh] [rbp+33h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "CSdEFSReadObj::Commit", 1296, 1);
  FileW = -1;
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  IoStatusBlock = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v19 = 0;
  LastFailureAsHRESULT = CSdEFSReadObj::_CopyFromTemporary(pvCallbackContext);
  v3 = 1316;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_2;
  v14 = 1316;
  if ( !*((_QWORD *)pvCallbackContext + 22) && !*((_DWORD *)pvCallbackContext + 34) )
  {
    LastFailureAsHRESULT = 0;
    v3 = 1323;
    goto LABEL_17;
  }
  (*(void (__fastcall **)(PVOID))(*(_QWORD *)pvCallbackContext + 72LL))(pvCallbackContext);
  FileW = (__int64)CreateFileW(
                     *((LPCWSTR *)pvCallbackContext + 7),
                     0x40100u,
                     *((_DWORD *)pvCallbackContext + 18),
                     0,
                     3u,
                     *((_DWORD *)pvCallbackContext + 19),
                     0);
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v4);
    v3 = 1337;
    goto LABEL_2;
  }
  LastFailureAsHRESULT = 0;
  v14 = 1337;
  v5 = (void *)*((_QWORD *)pvCallbackContext + 22);
  if ( v5 )
  {
    if ( !GetSecurityDescriptorDacl(v5, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v6);
      v3 = 1349;
      goto LABEL_2;
    }
    LastFailureAsHRESULT = 0;
    v14 = 1349;
    if ( bDaclPresent )
    {
      if ( !SetKernelObjectSecurity((HANDLE)FileW, 4u, *((PSECURITY_DESCRIPTOR *)pvCallbackContext + 22)) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7);
        v3 = 1352;
        goto LABEL_2;
      }
      LastFailureAsHRESULT = 0;
      v14 = 1352;
    }
  }
  if ( !*((_DWORD *)pvCallbackContext + 34) )
    goto LABEL_18;
  *(_QWORD *)FileInformation = *((_QWORD *)pvCallbackContext + 18);
  *(_QWORD *)&FileInformation[8] = *((_QWORD *)pvCallbackContext + 19);
  *(_QWORD *)&FileInformation[16] = *((_QWORD *)pvCallbackContext + 20);
  *(_DWORD *)&FileInformation[32] = *((_DWORD *)pvCallbackContext + 42);
  v8 = NtSetInformationFile((HANDLE)FileW, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
  LastFailureAsHRESULT = HRESULTFromNTSTATUS(v8);
  v3 = 1365;
  if ( LastFailureAsHRESULT < 0 )
  {
LABEL_2:
    v15 = v3;
    goto LABEL_18;
  }
LABEL_17:
  v14 = v3;
LABEL_18:
  (*(void (__fastcall **)(PVOID))(*(_QWORD *)pvCallbackContext + 72LL))(pvCallbackContext);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle((HANDLE)FileW);
    FileW = -1;
  }
  v9 = LastFailureAsHRESULT;
  if ( LastFailureAsHRESULT < 0 )
  {
    DeleteFileW(*((LPCWSTR *)pvCallbackContext + 7));
    v9 = LastFailureAsHRESULT;
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v9;
}

```

## disassembly

```asm
0x180043c10  mov     [rsp-8+arg_8], rbx
0x180043c15  mov     [rsp-8+arg_10], rsi
0x180043c1a  push    rbp
0x180043c1b  push    rdi
0x180043c1c  push    r14
0x180043c1e  lea     rbp, [rsp-47h]
0x180043c23  sub     rsp, 0D0h
0x180043c2a  mov     rax, cs:__security_cookie
0x180043c31  xor     rax, rsp
0x180043c34  mov     [rbp+57h+var_20], rax
0x180043c38  mov     rdi, rcx
0x180043c3b  mov     r9d, 1; unsigned __int16
0x180043c41  mov     r8d, 510h; unsigned __int16
0x180043c47  lea     rdx, aCsdefsreadobjC_2; "CSdEFSReadObj::Commit"
0x180043c4e  lea     rcx, [rbp+57h+var_98]; this
0x180043c52  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180043c57  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180043c5b  xor     r14d, r14d
0x180043c5e  mov     [rbp+57h+pDacl], r14
0x180043c62  mov     [rbp+57h+bDaclPresent], r14d
0x180043c66  mov     [rbp+57h+bDaclDefaulted], r14d
0x180043c6a  xorps   xmm0, xmm0
0x180043c6d  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180043c71  mov     dword ptr [rbp+57h+FileInformation], r14d
0x180043c75  xorps   xmm1, xmm1
0x180043c78  xor     eax, eax
0x180043c7a  movups  xmmword ptr [rbp+57h+FileInformation+4], xmm1
0x180043c7e  movups  [rbp+57h+var_34], xmm1
0x180043c82  mov     [rbp+57h+var_24], eax
0x180043c85  mov     rcx, rdi; pvCallbackContext
0x180043c88  call    ?_CopyFromTemporary@CSdEFSReadObj@@AEAAJXZ; CSdEFSReadObj::_CopyFromTemporary(void)
0x180043c8d  mov     [rbp+57h+var_98], eax
0x180043c90  test    eax, eax
0x180043c92  mov     eax, 524h
0x180043c97  jns     short loc_180043CA2
0x180043c99  mov     [rbp+57h+var_92], ax
0x180043c9d  jmp     loc_180043E16
0x180043ca2  mov     [rbp+57h+var_94], ax
0x180043ca6  cmp     [rdi+0B0h], r14
0x180043cad  jnz     short loc_180043CC6
0x180043caf  cmp     [rdi+88h], r14d
0x180043cb6  jnz     short loc_180043CC6
0x180043cb8  mov     [rbp+57h+var_98], r14d
0x180043cbc  mov     eax, 52Bh
0x180043cc1  jmp     loc_180043E12
0x180043cc6  mov     rax, [rdi]
0x180043cc9  mov     rcx, rdi
0x180043ccc  mov     rax, [rax+48h]
0x180043cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043cd5  mov     [rsp+0E0h+hTemplateFile], r14; hTemplateFile
0x180043cda  mov     eax, [rdi+4Ch]
0x180043cdd  mov     [rsp+0E0h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180043ce1  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x180043ce9  xor     r9d, r9d; lpSecurityAttributes
0x180043cec  mov     r8d, [rdi+48h]; dwShareMode
0x180043cf0  mov     edx, 40100h; dwDesiredAccess
0x180043cf5  mov     rcx, [rdi+38h]; lpFileName
0x180043cf9  call    cs:__imp_CreateFileW
0x180043cff  mov     rbx, rax
0x180043d02  inc     rax
0x180043d05  test    rax, 0FFFFFFFFFFFFFFFEh
0x180043d0b  jnz     short loc_180043D1F
0x180043d0d  call    GetLastFailureAsHRESULT
0x180043d12  mov     [rbp+57h+var_98], eax
0x180043d15  mov     eax, 539h
0x180043d1a  jmp     loc_180043C99
0x180043d1f  mov     [rbp+57h+var_98], r14d
0x180043d23  mov     eax, 539h
0x180043d28  mov     [rbp+57h+var_94], ax
0x180043d2c  mov     rcx, [rdi+0B0h]; pSecurityDescriptor
0x180043d33  mov     esi, 4
0x180043d38  test    rcx, rcx
0x180043d3b  jz      short loc_180043DAD
0x180043d3d  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180043d41  lea     r8, [rbp+57h+pDacl]; pDacl
0x180043d45  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180043d49  call    cs:__imp_GetSecurityDescriptorDacl
0x180043d4f  test    eax, eax
0x180043d51  jnz     short loc_180043D65
0x180043d53  call    GetLastFailureAsHRESULT
0x180043d58  mov     [rbp+57h+var_98], eax
0x180043d5b  mov     eax, 545h
0x180043d60  jmp     loc_180043C99
0x180043d65  mov     [rbp+57h+var_98], r14d
0x180043d69  mov     eax, 545h
0x180043d6e  mov     [rbp+57h+var_94], ax
0x180043d72  cmp     [rbp+57h+bDaclPresent], r14d
0x180043d76  jz      short loc_180043DAD
0x180043d78  mov     r8, [rdi+0B0h]; SecurityDescriptor
0x180043d7f  mov     edx, esi; SecurityInformation
0x180043d81  mov     rcx, rbx; Handle
0x180043d84  call    cs:__imp_SetKernelObjectSecurity
0x180043d8a  test    eax, eax
0x180043d8c  jnz     short loc_180043DA0
0x180043d8e  call    GetLastFailureAsHRESULT
0x180043d93  mov     [rbp+57h+var_98], eax
0x180043d96  mov     eax, 548h
0x180043d9b  jmp     loc_180043C99
0x180043da0  mov     [rbp+57h+var_98], r14d
0x180043da4  mov     eax, 548h
0x180043da9  mov     [rbp+57h+var_94], ax
0x180043dad  cmp     [rdi+88h], r14d
0x180043db4  jz      short loc_180043E16
0x180043db6  mov     rax, [rdi+90h]
0x180043dbd  mov     [rbp+57h+FileInformation], rax
0x180043dc1  mov     rax, [rdi+98h]
0x180043dc8  mov     [rbp+57h+var_40], rax
0x180043dcc  mov     rax, [rdi+0A0h]
0x180043dd3  mov     [rbp+1Fh], rax
0x180043dd7  mov     eax, [rdi+0A8h]
0x180043ddd  mov     dword ptr [rbp+57h+var_34+0Ch], eax
0x180043de0  mov     [rsp+0E0h+dwCreationDisposition], esi; FileInformationClass
0x180043de4  mov     r9d, 28h ; '('; Length
0x180043dea  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x180043dee  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180043df2  mov     rcx, rbx; FileHandle
0x180043df5  call    cs:__imp_NtSetInformationFile
0x180043dfb  mov     ecx, eax
0x180043dfd  call    HRESULTFromNTSTATUS
0x180043e02  mov     [rbp+57h+var_98], eax
0x180043e05  test    eax, eax
0x180043e07  mov     eax, 555h
0x180043e0c  js      loc_180043C99
0x180043e12  mov     [rbp+57h+var_94], ax
0x180043e16  mov     rax, [rdi]
0x180043e19  mov     rcx, rdi
0x180043e1c  mov     rax, [rax+48h]
0x180043e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e25  lea     rax, [rbx-1]
0x180043e29  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180043e2d  ja      short loc_180043E3C
0x180043e2f  mov     rcx, rbx; hObject
0x180043e32  call    cs:__imp_CloseHandle
0x180043e38  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180043e3c  mov     esi, [rbp+57h+var_98]
0x180043e3f  test    esi, esi
0x180043e41  jns     short loc_180043E50
0x180043e43  mov     rcx, [rdi+38h]; lpFileName
0x180043e47  call    cs:__imp_DeleteFileW
0x180043e4d  mov     esi, [rbp+57h+var_98]
0x180043e50  lea     rcx, [rbx-1]
0x180043e54  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180043e58  ja      short loc_180043E63
0x180043e5a  mov     rcx, rbx; hObject
0x180043e5d  call    cs:__imp_CloseHandle
0x180043e63  lea     rcx, [rbp+57h+var_98]; this
0x180043e67  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180043e6c  mov     eax, esi
0x180043e6e  mov     rcx, [rbp+57h+var_20]
0x180043e72  xor     rcx, rsp; StackCookie
0x180043e75  call    __security_check_cookie
0x180043e7a  lea     r11, [rsp+0E0h+var_10]
0x180043e82  mov     rbx, [r11+28h]
0x180043e86  mov     rsi, [r11+30h]
0x180043e8a  mov     rsp, r11
0x180043e8d  pop     r14
0x180043e8f  pop     rdi
0x180043e90  pop     rbp
0x180043e91  retn
```
