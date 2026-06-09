# CDlpManager::SetThreadPriority(WINDLP_PRIORITY)

- ea: `0x180075cf0`
- end: `0x180076186`
- name: `?SetThreadPriority@CDlpManager@@UEAAJW4WINDLP_PRIORITY@@@Z`
- size: `1174`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x18004541c`

## callees

- `0x180001be8`
- `0x180001f30`
- `0x1800097ec`
- `0x18000aba4`
- `0x180012f5c`
- `0x1800140dc`
- `0x18001fd60`
- `0x180075cf0`
- `0x18007ec9a`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180075f23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180075f23`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180075f2e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180075f2e`
- `ntdll!RtlGetVersion` at `0x180075e5a`
- `ntdll!RtlGetVersion` at `0x180075e5a`
- `ntdll!NtSetInformationThread` at `0x180076034`
- `ntdll!NtSetInformationThread` at `0x1800760b1`
- `ntdll!NtSetInformationThread` at `0x180076034`
- `ntdll!NtSetInformationThread` at `0x1800760b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075f38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075f38`

## string_xrefs

- `0x180075da9`: `CDlpManager::SetThreadPriority`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDlpManager::SetThreadPriority(__int64 a1, int a2)
{
  int v4; // edi
  __int64 v5; // rax
  __int64 v6; // rcx
  int v7; // eax
  NTSTATUS Version; // eax
  int v9; // edi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  NTSTATUS v12; // eax
  NTSTATUS v13; // eax
  char *v14; // rbx
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+28h] [rbp-D8h]
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  int ThreadInformation; // [rsp+34h] [rbp-CCh] BYREF
  int v20; // [rsp+38h] [rbp-C8h] BYREF
  int v21; // [rsp+3Ch] [rbp-C4h] BYREF
  int v22; // [rsp+40h] [rbp-C0h] BYREF
  void *v23; // [rsp+48h] [rbp-B8h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(&VersionInformation, 0, 0x11Cu);
  v21 = 0;
  v20 = 0;
  ThreadInformation = 0;
  v23 = 0;
  v22 = 14;
  if ( (unsigned int)(a2 - 1) > 4 )
  {
    v4 = -2147024809;
    if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80) )
      goto LABEL_54;
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80);
    v6 = 0;
    if ( !v5 )
      goto LABEL_7;
    v17 = -2147024809;
    v16 = 1950;
    goto LABEL_5;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a1 + 192LL))(a1, &v21);
  v18 = v4;
  if ( v4 >= 0 )
  {
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
    VersionInformation.dwOSVersionInfoSize = 284;
    Version = RtlGetVersion(&VersionInformation);
    if ( !SErrorConverter::C_NtStatus2HR(Version, &v18) )
    {
      if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80) )
      {
        v4 = v18;
        v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80);
        v6 = 0;
        if ( v4 >= 0 || !v5 )
          goto LABEL_7;
        v17 = v4;
        v16 = 1960;
        goto LABEL_5;
      }
LABEL_53:
      v4 = v18;
      goto LABEL_54;
    }
    v9 = 0;
    ThreadInformation = 2;
    v20 = 5;
    switch ( a2 )
    {
      case 2:
        v9 = -2;
        ThreadInformation = 0;
        v20 = 1;
        break;
      case 3:
        v9 = 2;
LABEL_22:
        ThreadInformation = 3;
        break;
      case 4:
        v9 = -1;
        ThreadInformation = 1;
        v20 = 3;
        break;
      case 5:
        v9 = 1;
        goto LABEL_22;
      default:
        break;
    }
    CurrentThread = GetCurrentThread();
    if ( !SetThreadPriority(CurrentThread, v9) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v4 = -2147467259;
      }
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80) )
        goto LABEL_54;
      v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80);
      v6 = 0;
      if ( v4 >= 0 || !v5 )
        goto LABEL_7;
      v17 = v4;
      v16 = 2006;
LABEL_5:
      v7 = CDlpLogT<CEmptyType>::DlpLogFormat(
             v5,
             4u,
             (__int64)L"%s(%d): Result = 0x%X",
             L"CDlpManager::SetThreadPriority",
             v16,
             v17);
      v6 = (unsigned int)v7;
      if ( v7 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
      goto LABEL_7;
    }
    if ( VersionInformation.dwMajorVersion >= 6 )
    {
      if ( ((a2 - 3) & 0xFFFFFFFD) == 0 )
      {
        v4 = CAutoRevertApplyPrivilegesT<CEmptyType>::Enable(&v23, (__int64)&v22, 1u);
        v18 = v4;
        if ( v4 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80) )
            goto LABEL_54;
          v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80);
          v6 = 0;
          if ( !v5 )
            goto LABEL_7;
          v17 = v4;
          v16 = 2017;
          goto LABEL_5;
        }
      }
      v12 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadIoPriority, &ThreadInformation, 4u);
      if ( !SErrorConverter::C_NtStatus2HR(v12, &v18) )
      {
        if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80) )
        {
          v4 = v18;
          v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80);
          v6 = 0;
          if ( v4 >= 0 || !v5 )
            goto LABEL_7;
          v17 = v4;
          v16 = 2025;
          goto LABEL_5;
        }
        goto LABEL_53;
      }
      v13 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPagePriority, &v20, 4u);
      if ( !SErrorConverter::C_NtStatus2HR(v13, &v18) )
      {
        if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80) )
        {
          v4 = v18;
          v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80);
          v6 = 0;
          if ( v4 >= 0 || !v5 )
            goto LABEL_7;
          v17 = v4;
          v16 = 2032;
          goto LABEL_5;
        }
        goto LABEL_53;
      }
    }
    if ( !*(_DWORD *)(a1 + 852) )
      *(_DWORD *)(a1 + 852) = v21;
    goto LABEL_53;
  }
  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80) )
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 80) + 16LL))(a1 + 80);
    v6 = 0;
    if ( v5 )
    {
      v17 = v4;
      v16 = 1954;
      goto LABEL_5;
    }
LABEL_7:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  }
LABEL_54:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
  if ( v23 )
  {
    v14 = (char *)v23 - 8;
    `eh vector destructor iterator'(
      v23,
      8u,
      *((_QWORD *)v23 - 1),
      (void (*)(void *))CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState::~CPrivilegeState);
    operator delete(v14);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180075cf0  mov     [rsp-8+arg_8], rbx
0x180075cf5  mov     [rsp-8+arg_10], rsi
0x180075cfa  push    rbp
0x180075cfb  push    rdi
0x180075cfc  push    r13
0x180075cfe  lea     rbp, [rsp-80h]
0x180075d03  sub     rsp, 180h
0x180075d0a  mov     rax, cs:__security_cookie
0x180075d11  xor     rax, rsp
0x180075d14  mov     [rbp+90h+var_20], rax
0x180075d18  mov     esi, edx
0x180075d1a  mov     rbx, rcx
0x180075d1d  xor     edx, edx; Val
0x180075d1f  mov     r8d, 11Ch; Size
0x180075d25  lea     rcx, [rsp+190h+VersionInformation]; void *
0x180075d2a  call    memset_0
0x180075d2f  mov     [rsp+190h+var_154], 0
0x180075d37  mov     [rsp+190h+var_158], 0
0x180075d3f  mov     [rsp+190h+ThreadInformation], 0
0x180075d47  mov     [rsp+190h+var_148], 0
0x180075d50  mov     [rsp+190h+var_150], 0Eh
0x180075d58  lea     eax, [rsi-1]
0x180075d5b  mov     r13d, 4
0x180075d61  cmp     eax, r13d
0x180075d64  jbe     short loc_180075DD7
0x180075d66  mov     edi, 80070057h
0x180075d6b  mov     rax, [rbx+50h]
0x180075d6f  lea     rcx, [rbx+50h]
0x180075d73  mov     rax, [rax+10h]
0x180075d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075d7c  test    rax, rax
0x180075d7f  jz      loc_18007612D
0x180075d85  mov     rax, [rbx+50h]
0x180075d89  lea     rcx, [rbx+50h]
0x180075d8d  mov     rax, [rax+10h]
0x180075d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075d96  xor     ecx, ecx
0x180075d98  test    rax, rax
0x180075d9b  jz      short loc_180075DCD
0x180075d9d  mov     [rsp+190h+var_168], edi
0x180075da1  mov     [rsp+190h+var_170], 79Eh
0x180075da9  lea     r9, aCdlpmanagerSet_3; "CDlpManager::SetThreadPriority"
0x180075db0  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180075db7  mov     edx, r13d
0x180075dba  mov     rcx, rax
0x180075dbd  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180075dc2  test    eax, eax
0x180075dc4  mov     ecx, eax
0x180075dc6  jns     short loc_180075DCD
0x180075dc8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180075dcd  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180075dd2  jmp     loc_18007612D
0x180075dd7  mov     rax, [rbx]
0x180075dda  lea     rdx, [rsp+190h+var_154]
0x180075ddf  mov     rcx, rbx
0x180075de2  mov     rax, [rax+0C0h]
0x180075de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075dee  mov     edi, eax
0x180075df0  mov     [rsp+190h+var_160], eax
0x180075df4  test    eax, eax
0x180075df6  jns     short loc_180075E3B
0x180075df8  mov     rax, [rbx+50h]
0x180075dfc  lea     rcx, [rbx+50h]
0x180075e00  mov     rax, [rax+10h]
0x180075e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075e09  test    rax, rax
0x180075e0c  jz      loc_18007612D
0x180075e12  mov     rax, [rbx+50h]
0x180075e16  lea     rcx, [rbx+50h]
0x180075e1a  mov     rax, [rax+10h]
0x180075e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075e23  xor     ecx, ecx
0x180075e25  test    rax, rax
0x180075e28  jz      short loc_180075DCD
0x180075e2a  mov     [rsp+190h+var_168], edi
0x180075e2e  mov     [rsp+190h+var_170], 7A2h
0x180075e36  jmp     loc_180075DA9
0x180075e3b  xor     edx, edx; Val
0x180075e3d  mov     r8d, 118h; Size
0x180075e43  lea     rcx, [rsp+190h+VersionInformation.dwMajorVersion]; void *
0x180075e48  call    memset_0
0x180075e4d  mov     [rsp+190h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180075e55  lea     rcx, [rsp+190h+VersionInformation]; lpVersionInformation
0x180075e5a  call    cs:__imp_RtlGetVersion
0x180075e60  mov     ecx, eax; int
0x180075e62  lea     rdx, [rsp+190h+var_160]; int *
0x180075e67  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x180075e6c  test    eax, eax
0x180075e6e  jnz     short loc_180075EC3
0x180075e70  mov     rax, [rbx+50h]
0x180075e74  lea     rcx, [rbx+50h]
0x180075e78  mov     rax, [rax+10h]
0x180075e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075e81  test    rax, rax
0x180075e84  jz      loc_180076129
0x180075e8a  mov     edi, [rsp+190h+var_160]
0x180075e8e  mov     rax, [rbx+50h]
0x180075e92  lea     rcx, [rbx+50h]
0x180075e96  mov     rax, [rax+10h]
0x180075e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075e9f  xor     ecx, ecx
0x180075ea1  test    edi, edi
0x180075ea3  jns     loc_180075DCD
0x180075ea9  test    rax, rax
0x180075eac  jz      loc_180075DCD
0x180075eb2  mov     [rsp+190h+var_168], edi
0x180075eb6  mov     [rsp+190h+var_170], 7A8h
0x180075ebe  jmp     loc_180075DA9
0x180075ec3  xor     edi, edi
0x180075ec5  lea     edx, [rdi+2]
0x180075ec8  mov     [rsp+190h+ThreadInformation], edx
0x180075ecc  mov     [rsp+190h+var_158], 5
0x180075ed4  mov     ecx, esi
0x180075ed6  sub     ecx, edx
0x180075ed8  jz      short loc_180075F0E
0x180075eda  sub     ecx, 1
0x180075edd  jz      short loc_180075F0A
0x180075edf  sub     ecx, 1
0x180075ee2  jz      short loc_180075EF5
0x180075ee4  cmp     ecx, 1
0x180075ee7  jnz     short loc_180075F23
0x180075ee9  mov     edi, ecx
0x180075eeb  mov     [rsp+190h+ThreadInformation], 3
0x180075ef3  jmp     short loc_180075F23
0x180075ef5  or      edi, 0FFFFFFFFh
0x180075ef8  mov     [rsp+190h+ThreadInformation], 1
0x180075f00  mov     [rsp+190h+var_158], 3
0x180075f08  jmp     short loc_180075F23
0x180075f0a  mov     edi, edx
0x180075f0c  jmp     short loc_180075EEB
0x180075f0e  mov     edi, 0FFFFFFFEh
0x180075f13  mov     [rsp+190h+ThreadInformation], 0
0x180075f1b  mov     [rsp+190h+var_158], 1
0x180075f23  call    cs:__imp_GetCurrentThread
0x180075f29  mov     rcx, rax; hThread
0x180075f2c  mov     edx, edi; nPriority
0x180075f2e  call    cs:__imp_SetThreadPriority
0x180075f34  test    eax, eax
0x180075f36  jnz     short loc_180075FA5
0x180075f38  call    cs:__imp_GetLastError
0x180075f3e  mov     edi, eax
0x180075f40  test    eax, eax
0x180075f42  jnz     short loc_180075F4B
0x180075f44  mov     edi, 80004005h
0x180075f49  jmp     short loc_180075F56
0x180075f4b  jle     short loc_180075F56
0x180075f4d  movzx   edi, ax
0x180075f50  or      edi, 80070000h
0x180075f56  mov     rax, [rbx+50h]
0x180075f5a  lea     rcx, [rbx+50h]
0x180075f5e  mov     rax, [rax+10h]
0x180075f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075f67  test    rax, rax
0x180075f6a  jz      loc_18007612D
0x180075f70  mov     rax, [rbx+50h]
0x180075f74  lea     rcx, [rbx+50h]
0x180075f78  mov     rax, [rax+10h]
0x180075f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075f81  xor     ecx, ecx
0x180075f83  test    edi, edi
0x180075f85  jns     loc_180075DCD
0x180075f8b  test    rax, rax
0x180075f8e  jz      loc_180075DCD
0x180075f94  mov     [rsp+190h+var_168], edi
0x180075f98  mov     [rsp+190h+var_170], 7D6h
0x180075fa0  jmp     loc_180075DA9
0x180075fa5  cmp     [rsp+190h+VersionInformation.dwMajorVersion], 6
0x180075faa  jb      loc_180076116
0x180075fb0  lea     eax, [rsi-3]
0x180075fb3  test    eax, 0FFFFFFFDh
0x180075fb8  jnz     short loc_180076020
0x180075fba  mov     r8d, 1
0x180075fc0  lea     rdx, [rsp+190h+var_150]
0x180075fc5  lea     rcx, [rsp+190h+var_148]
0x180075fca  call    ?Enable@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAAJPEBKK@Z; CAutoRevertApplyPrivilegesT<CEmptyType>::Enable(ulong const *,ulong)
0x180075fcf  mov     edi, eax
0x180075fd1  mov     [rsp+190h+var_160], eax
0x180075fd5  test    eax, eax
0x180075fd7  jns     short loc_180076020
0x180075fd9  mov     rax, [rbx+50h]
0x180075fdd  lea     rcx, [rbx+50h]
0x180075fe1  mov     rax, [rax+10h]
0x180075fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075fea  test    rax, rax
0x180075fed  jz      loc_18007612D
0x180075ff3  mov     rax, [rbx+50h]
0x180075ff7  lea     rcx, [rbx+50h]
0x180075ffb  mov     rax, [rax+10h]
0x180075fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076004  xor     ecx, ecx
0x180076006  test    rax, rax
0x180076009  jz      loc_180075DCD
0x18007600f  mov     [rsp+190h+var_168], edi
0x180076013  mov     [rsp+190h+var_170], 7E1h
0x18007601b  jmp     loc_180075DA9
0x180076020  mov     r9d, r13d; ThreadInformationLength
0x180076023  lea     r8, [rsp+190h+ThreadInformation]; ThreadInformation
0x180076028  mov     edx, 16h; ThreadInformationClass
0x18007602d  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180076034  call    cs:__imp_NtSetInformationThread
0x18007603a  mov     ecx, eax; int
0x18007603c  lea     rdx, [rsp+190h+var_160]; int *
0x180076041  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x180076046  test    eax, eax
0x180076048  jnz     short loc_18007609D
0x18007604a  mov     rax, [rbx+50h]
0x18007604e  lea     rcx, [rbx+50h]
0x180076052  mov     rax, [rax+10h]
0x180076056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007605b  test    rax, rax
0x18007605e  jz      loc_180076129
0x180076064  mov     edi, [rsp+190h+var_160]
0x180076068  mov     rax, [rbx+50h]
0x18007606c  lea     rcx, [rbx+50h]
0x180076070  mov     rax, [rax+10h]
0x180076074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076079  xor     ecx, ecx
0x18007607b  test    edi, edi
0x18007607d  jns     loc_180075DCD
0x180076083  test    rax, rax
0x180076086  jz      loc_180075DCD
0x18007608c  mov     [rsp+190h+var_168], edi
0x180076090  mov     [rsp+190h+var_170], 7E9h
0x180076098  jmp     loc_180075DA9
0x18007609d  mov     r9d, r13d; ThreadInformationLength
0x1800760a0  lea     r8, [rsp+190h+var_158]; ThreadInformation
0x1800760a5  mov     edx, 18h; ThreadInformationClass
0x1800760aa  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800760b1  call    cs:__imp_NtSetInformationThread
0x1800760b7  mov     ecx, eax; int
0x1800760b9  lea     rdx, [rsp+190h+var_160]; int *
0x1800760be  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x1800760c3  test    eax, eax
0x1800760c5  jnz     short loc_180076116
0x1800760c7  mov     rax, [rbx+50h]
0x1800760cb  lea     rcx, [rbx+50h]
0x1800760cf  mov     rax, [rax+10h]
0x1800760d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800760d8  test    rax, rax
0x1800760db  jz      short loc_180076129
0x1800760dd  mov     edi, [rsp+190h+var_160]
0x1800760e1  mov     rax, [rbx+50h]
0x1800760e5  lea     rcx, [rbx+50h]
0x1800760e9  mov     rax, [rax+10h]
0x1800760ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800760f2  xor     ecx, ecx
0x1800760f4  test    edi, edi
0x1800760f6  jns     loc_180075DCD
0x1800760fc  test    rax, rax
0x1800760ff  jz      loc_180075DCD
0x180076105  mov     [rsp+190h+var_168], edi
0x180076109  mov     [rsp+190h+var_170], 7F0h
0x180076111  jmp     loc_180075DA9
0x180076116  cmp     dword ptr [rbx+354h], 0
0x18007611d  jnz     short loc_180076129
0x18007611f  mov     eax, [rsp+190h+var_154]
0x180076123  mov     [rbx+354h], eax
0x180076129  mov     edi, [rsp+190h+var_160]
0x18007612d  mov     ecx, edi
0x18007612f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180076134  nop
0x180076135  mov     rcx, [rsp+190h+var_148]; void *
0x18007613a  test    rcx, rcx
0x18007613d  jz      short loc_180076160
0x18007613f  lea     rbx, [rcx-8]
0x180076143  lea     r9, ??1CPrivilegeState@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAA@XZ; void (*)(void *)
0x18007614a  mov     r8, [rbx]; unsigned __int64
0x18007614d  mov     edx, 8; unsigned __int64
0x180076152  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180076157  mov     rcx, rbx; Block
0x18007615a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007615f  nop
0x180076160  mov     eax, edi
0x180076162  mov     rcx, [rbp+90h+var_20]
0x180076166  xor     rcx, rsp; StackCookie
0x180076169  call    __security_check_cookie
0x18007616e  lea     r11, [rsp+190h+var_10]
0x180076176  mov     rbx, [r11+28h]
0x18007617a  mov     rsi, [r11+30h]
0x18007617e  mov     rsp, r11
0x180076181  pop     r13
0x180076183  pop     rdi
0x180076184  pop     rbp
0x180076185  retn
```
