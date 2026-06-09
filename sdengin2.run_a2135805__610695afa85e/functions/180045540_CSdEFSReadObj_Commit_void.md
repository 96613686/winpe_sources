# CSdEFSReadObj::Commit(void)

- ea: `0x180045540`
- end: `0x1800457ed`
- name: `?Commit@CSdEFSReadObj@@UEAAJXZ`
- size: `685`
- prototype: `__int64 __fastcall(PVOID pvCallbackContext)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180045540`
- `0x18004825c`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x180093698`
- `0x1800cf5c0`
- `0x1800d1010`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x180045737`
- `ntdll!NtSetInformationFile` at `0x180045737`
- `KERNEL32!DeleteFileW` at `0x180045795`
- `KERNEL32!DeleteFileW` at `0x180045795`
- `KERNEL32!CreateFileW` at `0x180045629`
- `KERNEL32!CreateFileW` at `0x180045629`
- `KERNEL32!CloseHandle` at `0x18004577a`
- `KERNEL32!CloseHandle` at `0x1800457b1`
- `KERNEL32!CloseHandle` at `0x18004577a`
- `KERNEL32!CloseHandle` at `0x1800457b1`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x1800456c0`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x1800456c0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004567f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004567f`

## string_xrefs

- `0x180045577`: `CSdEFSReadObj::Commit`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "CSdEFSReadObj::Commit", 0x510u, 1u);
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
0x180045540  mov     [rsp-8+arg_8], rbx
0x180045545  mov     [rsp-8+arg_10], rsi
0x18004554a  push    rbp
0x18004554b  push    rdi
0x18004554c  push    r14
0x18004554e  lea     rbp, [rsp-47h]
0x180045553  sub     rsp, 0D0h
0x18004555a  mov     rax, cs:__security_cookie
0x180045561  xor     rax, rsp
0x180045564  mov     [rbp+57h+var_20], rax
0x180045568  mov     rdi, rcx
0x18004556b  mov     r9d, 1; unsigned __int16
0x180045571  mov     r8d, 510h; unsigned __int16
0x180045577  lea     rdx, aCsdefsreadobjC_2; "CSdEFSReadObj::Commit"
0x18004557e  lea     rcx, [rbp+57h+var_98]; this
0x180045582  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180045587  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004558b  xor     r14d, r14d
0x18004558e  mov     [rbp+57h+pDacl], r14
0x180045592  mov     [rbp+57h+bDaclPresent], r14d
0x180045596  mov     [rbp+57h+bDaclDefaulted], r14d
0x18004559a  xorps   xmm0, xmm0
0x18004559d  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800455a1  mov     dword ptr [rbp+57h+FileInformation], r14d
0x1800455a5  xorps   xmm1, xmm1
0x1800455a8  xor     eax, eax
0x1800455aa  movups  xmmword ptr [rbp+57h+FileInformation+4], xmm1
0x1800455ae  movups  [rbp+57h+var_34], xmm1
0x1800455b2  mov     [rbp+57h+var_24], eax
0x1800455b5  mov     rcx, rdi; pvCallbackContext
0x1800455b8  call    ?_CopyFromTemporary@CSdEFSReadObj@@AEAAJXZ; CSdEFSReadObj::_CopyFromTemporary(void)
0x1800455bd  mov     [rbp+57h+var_98], eax
0x1800455c0  test    eax, eax
0x1800455c2  mov     eax, 524h
0x1800455c7  jns     short loc_1800455D2
0x1800455c9  mov     [rbp+57h+var_92], ax
0x1800455cd  jmp     loc_18004575E
0x1800455d2  mov     [rbp+57h+var_94], ax
0x1800455d6  cmp     [rdi+0B0h], r14
0x1800455dd  jnz     short loc_1800455F6
0x1800455df  cmp     [rdi+88h], r14d
0x1800455e6  jnz     short loc_1800455F6
0x1800455e8  mov     [rbp+57h+var_98], r14d
0x1800455ec  mov     eax, 52Bh
0x1800455f1  jmp     loc_18004575A
0x1800455f6  mov     rax, [rdi]
0x1800455f9  mov     rcx, rdi
0x1800455fc  mov     rax, [rax+48h]
0x180045600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045605  mov     [rsp+0E0h+hTemplateFile], r14; hTemplateFile
0x18004560a  mov     eax, [rdi+4Ch]
0x18004560d  mov     [rsp+0E0h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180045611  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x180045619  xor     r9d, r9d; lpSecurityAttributes
0x18004561c  mov     r8d, [rdi+48h]; dwShareMode
0x180045620  mov     edx, 40100h; dwDesiredAccess
0x180045625  mov     rcx, [rdi+38h]; lpFileName
0x180045629  call    cs:__imp_CreateFileW
0x180045630  nop     dword ptr [rax+rax+00h]
0x180045635  mov     rbx, rax
0x180045638  inc     rax
0x18004563b  test    rax, 0FFFFFFFFFFFFFFFEh
0x180045641  jnz     short loc_180045655
0x180045643  call    GetLastFailureAsHRESULT
0x180045648  mov     [rbp+57h+var_98], eax
0x18004564b  mov     eax, 539h
0x180045650  jmp     loc_1800455C9
0x180045655  mov     [rbp+57h+var_98], r14d
0x180045659  mov     eax, 539h
0x18004565e  mov     [rbp+57h+var_94], ax
0x180045662  mov     rcx, [rdi+0B0h]; pSecurityDescriptor
0x180045669  mov     esi, 4
0x18004566e  test    rcx, rcx
0x180045671  jz      short loc_1800456EF
0x180045673  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180045677  lea     r8, [rbp+57h+pDacl]; pDacl
0x18004567b  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x18004567f  call    cs:__imp_GetSecurityDescriptorDacl
0x180045686  nop     dword ptr [rax+rax+00h]
0x18004568b  test    eax, eax
0x18004568d  jnz     short loc_1800456A1
0x18004568f  call    GetLastFailureAsHRESULT
0x180045694  mov     [rbp+57h+var_98], eax
0x180045697  mov     eax, 545h
0x18004569c  jmp     loc_1800455C9
0x1800456a1  mov     [rbp+57h+var_98], r14d
0x1800456a5  mov     eax, 545h
0x1800456aa  mov     [rbp+57h+var_94], ax
0x1800456ae  cmp     [rbp+57h+bDaclPresent], r14d
0x1800456b2  jz      short loc_1800456EF
0x1800456b4  mov     r8, [rdi+0B0h]; SecurityDescriptor
0x1800456bb  mov     edx, esi; SecurityInformation
0x1800456bd  mov     rcx, rbx; Handle
0x1800456c0  call    cs:__imp_SetKernelObjectSecurity
0x1800456c7  nop     dword ptr [rax+rax+00h]
0x1800456cc  test    eax, eax
0x1800456ce  jnz     short loc_1800456E2
0x1800456d0  call    GetLastFailureAsHRESULT
0x1800456d5  mov     [rbp+57h+var_98], eax
0x1800456d8  mov     eax, 548h
0x1800456dd  jmp     loc_1800455C9
0x1800456e2  mov     [rbp+57h+var_98], r14d
0x1800456e6  mov     eax, 548h
0x1800456eb  mov     [rbp+57h+var_94], ax
0x1800456ef  cmp     [rdi+88h], r14d
0x1800456f6  jz      short loc_18004575E
0x1800456f8  mov     rax, [rdi+90h]
0x1800456ff  mov     [rbp+57h+FileInformation], rax
0x180045703  mov     rax, [rdi+98h]
0x18004570a  mov     [rbp+57h+var_40], rax
0x18004570e  mov     rax, [rdi+0A0h]
0x180045715  mov     [rbp+1Fh], rax
0x180045719  mov     eax, [rdi+0A8h]
0x18004571f  mov     dword ptr [rbp+57h+var_34+0Ch], eax
0x180045722  mov     [rsp+0E0h+dwCreationDisposition], esi; FileInformationClass
0x180045726  mov     r9d, 28h ; '('; Length
0x18004572c  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x180045730  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180045734  mov     rcx, rbx; FileHandle
0x180045737  call    cs:__imp_NtSetInformationFile
0x18004573e  nop     dword ptr [rax+rax+00h]
0x180045743  mov     ecx, eax
0x180045745  call    HRESULTFromNTSTATUS
0x18004574a  mov     [rbp+57h+var_98], eax
0x18004574d  test    eax, eax
0x18004574f  mov     eax, 555h
0x180045754  js      loc_1800455C9
0x18004575a  mov     [rbp+57h+var_94], ax
0x18004575e  mov     rax, [rdi]
0x180045761  mov     rcx, rdi
0x180045764  mov     rax, [rax+48h]
0x180045768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004576d  lea     rax, [rbx-1]
0x180045771  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180045775  ja      short loc_18004578A
0x180045777  mov     rcx, rbx; hObject
0x18004577a  call    cs:__imp_CloseHandle
0x180045781  nop     dword ptr [rax+rax+00h]
0x180045786  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004578a  mov     esi, [rbp+57h+var_98]
0x18004578d  test    esi, esi
0x18004578f  jns     short loc_1800457A4
0x180045791  mov     rcx, [rdi+38h]; lpFileName
0x180045795  call    cs:__imp_DeleteFileW
0x18004579c  nop     dword ptr [rax+rax+00h]
0x1800457a1  mov     esi, [rbp+57h+var_98]
0x1800457a4  lea     rcx, [rbx-1]
0x1800457a8  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800457ac  ja      short loc_1800457BD
0x1800457ae  mov     rcx, rbx; hObject
0x1800457b1  call    cs:__imp_CloseHandle
0x1800457b8  nop     dword ptr [rax+rax+00h]
0x1800457bd  lea     rcx, [rbp+57h+var_98]; this
0x1800457c1  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800457c6  mov     eax, esi
0x1800457c8  mov     rcx, [rbp+57h+var_20]
0x1800457cc  xor     rcx, rsp; StackCookie
0x1800457cf  call    __security_check_cookie
0x1800457d4  lea     r11, [rsp+0E0h+var_10]
0x1800457dc  mov     rbx, [r11+28h]
0x1800457e0  mov     rsi, [r11+30h]
0x1800457e4  mov     rsp, r11
0x1800457e7  pop     r14
0x1800457e9  pop     rdi
0x1800457ea  pop     rbp
0x1800457eb  retn
```
