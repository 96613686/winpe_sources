# CSchedule::SetTargetComputer(ushort const *)

- ea: `0x180029ef0`
- end: `0x18002a4ca`
- name: `?SetTargetComputer@CSchedule@@UEAAJPEBG@Z`
- size: `1498`
- prototype: `__int64 __fastcall(CSchedule *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180003320`
- `0x1800040c0`
- `0x180007948`
- `0x180007988`
- `0x1800089f8`
- `0x180028854`
- `0x180029ef0`
- `0x18002cc94`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18002a183`
- `msvcrt!_wcsnicmp` at `0x18002a1ac`
- `msvcrt!_wcsnicmp` at `0x18002a183`
- `msvcrt!_wcsnicmp` at `0x18002a1ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029f78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029f78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a099`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a15e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a20c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a272`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a280`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a2d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a099`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a15e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a20c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a272`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a280`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a2d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a111`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a25b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a111`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a25b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a082`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a1f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a082`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a1f5`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180029fbc`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180029fbc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180029f68`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180029f68`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180029fec`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002a005`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180029fec`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002a005`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18002a04f`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18002a04f`

## string_xrefs

- `0x18002a07b`: `SOFTWARE\Microsoft\SchedulingAgent`
- `0x18002a0f0`: `TasksFolder`
- `0x18002a127`: `%SystemRoot%\Tasks`

## pseudocode

```c
signed int __fastcall CSchedule::SetTargetComputer(CSchedule *this, const unsigned __int16 *a2)
{
  unsigned __int64 v2; // r13
  BOOL v5; // r15d
  signed int result; // eax
  bool v7; // cc
  LSTATUS v8; // ebx
  unsigned __int64 v9; // rcx
  DWORD v10; // eax
  __int64 v11; // rax
  __int64 v12; // rcx
  DWORD v13; // eax
  __int64 v14; // rax
  unsigned __int64 v15; // r12
  _WORD *v16; // rax
  void *v17; // r14
  __int64 v18; // rax
  unsigned __int16 *v19; // rbx
  void *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  DWORD nSize; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v26; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR String2; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v29; // [rsp+52h] [rbp-AEh]
  wchar_t Buffer[264]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 Data[264]; // [rsp+470h] [rbp+370h] BYREF

  v2 = 0;
  nSize = 0;
  v5 = 1;
  if ( a2 )
  {
    memset_0(Buffer, 0, 0x202u);
    nSize = 257;
    if ( !GetComputerNameW(Buffer, &nSize)
      || (memset_0(&String2, 0, 0x202u),
          nSize = 257,
          !GetComputerNameExW(ComputerNamePhysicalDnsFullyQualified, &String2, &nSize)) )
    {
      result = GetLastError();
      v7 = result <= 0;
      goto LABEL_4;
    }
    if ( !*a2 || !a2[1] )
      return -2147418113;
    if ( lstrcmpiW(a2 + 2, Buffer) )
      v5 = lstrcmpiW(a2 + 2, &String2) == 0;
  }
  memset_0(&String2, 0, 0x20Au);
  if ( v5 )
  {
    v14 = -1;
    do
      ++v14;
    while ( g_TasksFolderInfo[v14] );
    v13 = v14 + 1;
    goto LABEL_48;
  }
  phkResult = 0;
  hKey = 0;
  result = RegConnectRegistryW(a2, HKEY_LOCAL_MACHINE, &phkResult);
  v7 = result <= 0;
  if ( result )
  {
LABEL_4:
    if ( !v7 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v8 = RegOpenKeyExW(phkResult, L"SOFTWARE\\Microsoft\\SchedulingAgent", 0, 0x20019u, &hKey);
  if ( !v8 )
  {
    memset_0(Buffer, 0, 0x20Au);
    cbData = 520;
    if ( RegQueryValueExW(hKey, L"TasksFolder", 0, 0, (LPBYTE)Buffer, &cbData) )
    {
      StringCchCopyW(Buffer, 0x105u, L"%SystemRoot%\\Tasks");
    }
    else
    {
      v9 = cbData & 0xFFFFFFFE;
      if ( v9 >= 0x20A )
        _report_rangecheckfailure();
      *(wchar_t *)((char *)Buffer + v9) = 0;
    }
    RegCloseKey(hKey);
    nSize = 12;
    if ( _wcsnicmp(Buffer, L"%SystemRoot%", 0xCu) && (nSize = 8, _wcsnicmp(Buffer, L"%WinDir%", 8u)) )
    {
      v10 = 0;
      nSize = 0;
    }
    else
    {
      v10 = nSize;
    }
    if ( v10 )
    {
      v26 = 0;
      v8 = RegOpenKeyExW(phkResult, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion", 0, 0xF003Fu, &v26);
      if ( v8 )
      {
LABEL_30:
        RegCloseKey(phkResult);
        goto LABEL_16;
      }
      memset_0(Data, 0, 0x20Au);
      cbData = 522;
      v8 = RegQueryValueExW(v26, L"SystemRoot", 0, 0, (LPBYTE)Data, &cbData);
      if ( v8 )
      {
        RegCloseKey(v26);
        goto LABEL_30;
      }
      RegCloseKey(v26);
      StringCchCopyW(&String2, 0x105u, Data);
      StringCchCatW(&String2, 0x105u, &Buffer[nSize]);
    }
    else
    {
      StringCchCopyW(&String2, 0x105u, Buffer);
    }
    RegCloseKey(phkResult);
    if ( (unsigned __int16)(String2 - 65) > 0x19u && (unsigned __int16)(String2 - 97) > 0x19u || v29 != 58 )
      return -2147024735;
    v11 = -1;
    do
      ++v11;
    while ( *(&String2 + v11) );
    v12 = -1;
    do
      ++v12;
    while ( a2[v12] );
    v13 = v12 + v11 + 2;
LABEL_48:
    nSize = v13;
    v15 = v13;
    v16 = operator new(saturated_mul(v13, 2u));
    v17 = v16;
    if ( !v16 )
      return -2147024882;
    *v16 = 0;
    if ( v5 )
    {
      v19 = 0;
    }
    else
    {
      v18 = -1;
      do
        ++v18;
      while ( a2[v18] );
      v2 = v18 + 1;
      v19 = (unsigned __int16 *)operator new(saturated_mul(v18 + 1, 2u));
      if ( !v19 )
      {
        operator delete(v17);
        return -2147024882;
      }
      *v19 = 0;
    }
    v20 = (void *)*((_QWORD *)this + 7);
    if ( v20 )
      operator delete(v20);
    v21 = (void *)*((_QWORD *)this + 8);
    if ( v21 )
      operator delete(v21);
    if ( v5 )
    {
      *((_QWORD *)this + 8) = v17;
      *((_QWORD *)this + 7) = 0;
      StringCchCopyW((unsigned __int16 *)v17, v15, g_TasksFolderInfo);
      v8 = FolderAccessCheckOnThreadToken(*((LPCWSTR *)this + 8), 1u);
      if ( v8 < 0 )
      {
        operator delete(*((void **)this + 7));
        v22 = (void *)*((_QWORD *)this + 8);
        *((_QWORD *)this + 7) = 0;
        operator delete(v22);
        *((_QWORD *)this + 8) = 0;
        CSchedule::Init(this);
        return v8;
      }
    }
    else
    {
      *((_QWORD *)this + 7) = v19;
      StringCchCopyW(v19, v2, a2);
      *((_QWORD *)this + 8) = v17;
      v29 = 36;
      StringCchCopyW((unsigned __int16 *)v17, v15, a2);
      StringCchCatW(*((unsigned __int16 **)this + 8), v15, L"\\");
      StringCchCatW(*((unsigned __int16 **)this + 8), v15, &String2);
    }
    return 0;
  }
  RegCloseKey(phkResult);
  if ( v8 != 1010 && v8 != 2 )
  {
LABEL_16:
    if ( v8 > 0 )
      return (unsigned __int16)v8 | 0x80070000;
    return v8;
  }
  return -2147216628;
}

```

## disassembly

```asm
0x180029ef0  mov     [rsp-8+arg_10], rbx
0x180029ef5  push    rbp
0x180029ef6  push    rsi
0x180029ef7  push    rdi
0x180029ef8  push    r12
0x180029efa  push    r13
0x180029efc  push    r14
0x180029efe  push    r15
0x180029f00  lea     rbp, [rsp-590h]
0x180029f08  sub     rsp, 690h
0x180029f0f  mov     rax, cs:__security_cookie
0x180029f16  xor     rax, rsp
0x180029f19  mov     [rbp+5C0h+var_40], rax
0x180029f20  xor     r13d, r13d
0x180029f23  mov     rsi, rdx
0x180029f26  mov     [rsp+6C0h+nSize], r13d
0x180029f2b  mov     rdi, rcx
0x180029f2e  lea     r15d, [r13+1]
0x180029f32  test    rdx, rdx
0x180029f35  jz      loc_18002A018
0x180029f3b  mov     ebx, 202h
0x180029f40  lea     rcx, [rbp+5C0h+Buffer]; void *
0x180029f47  mov     r8d, ebx; Size
0x180029f4a  xor     edx, edx; Val
0x180029f4c  call    memset_0
0x180029f51  mov     r14d, 101h
0x180029f57  lea     rdx, [rsp+6C0h+nSize]; nSize
0x180029f5c  lea     rcx, [rbp+5C0h+Buffer]; lpBuffer
0x180029f63  mov     [rsp+6C0h+nSize], r14d
0x180029f68  call    cs:__imp_GetComputerNameW
0x180029f6f  nop     dword ptr [rax+rax+00h]
0x180029f74  test    eax, eax
0x180029f76  jnz     short loc_180029F99
0x180029f78  call    cs:__imp_GetLastError
0x180029f7f  nop     dword ptr [rax+rax+00h]
0x180029f84  test    eax, eax
0x180029f86  jle     loc_18002A49F
0x180029f8c  movzx   eax, ax
0x180029f8f  or      eax, 80070000h
0x180029f94  jmp     loc_18002A49F
0x180029f99  mov     r8, rbx; Size
0x180029f9c  lea     rcx, [rsp+6C0h+String2]; void *
0x180029fa1  xor     edx, edx; Val
0x180029fa3  call    memset_0
0x180029fa8  lea     r8, [rsp+6C0h+nSize]; nSize
0x180029fad  mov     [rsp+6C0h+nSize], r14d
0x180029fb2  lea     rdx, [rsp+6C0h+String2]; lpBuffer
0x180029fb7  mov     ecx, 7; NameType
0x180029fbc  call    cs:__imp_GetComputerNameExW
0x180029fc3  nop     dword ptr [rax+rax+00h]
0x180029fc8  test    eax, eax
0x180029fca  jz      short loc_180029F78
0x180029fcc  cmp     [rsi], r13w
0x180029fd0  jz      loc_18002A49A
0x180029fd6  cmp     [rsi+2], r13w
0x180029fdb  jz      loc_18002A49A
0x180029fe1  lea     rdx, [rbp+5C0h+Buffer]; lpString2
0x180029fe8  lea     rcx, [rsi+4]; lpString1
0x180029fec  call    cs:__imp_lstrcmpiW
0x180029ff3  nop     dword ptr [rax+rax+00h]
0x180029ff8  test    eax, eax
0x180029ffa  jz      short loc_18002A018
0x180029ffc  lea     rdx, [rsp+6C0h+String2]; lpString2
0x18002a001  lea     rcx, [rsi+4]; lpString1
0x18002a005  call    cs:__imp_lstrcmpiW
0x18002a00c  nop     dword ptr [rax+rax+00h]
0x18002a011  test    eax, eax
0x18002a013  jz      short loc_18002A018
0x18002a015  mov     r15d, r13d
0x18002a018  mov     r14d, 20Ah
0x18002a01e  lea     rcx, [rsp+6C0h+String2]; void *
0x18002a023  mov     r8d, r14d; Size
0x18002a026  xor     edx, edx; Val
0x18002a028  call    memset_0
0x18002a02d  test    r15d, r15d
0x18002a030  jnz     loc_18002A33E
0x18002a036  lea     r8, [rsp+6C0h+phkResult]; phkResult
0x18002a03b  mov     [rsp+6C0h+phkResult], r13
0x18002a040  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18002a047  mov     [rsp+6C0h+hKey], r13
0x18002a04c  mov     rcx, rsi; lpMachineName
0x18002a04f  call    cs:__imp_RegConnectRegistryW
0x18002a056  nop     dword ptr [rax+rax+00h]
0x18002a05b  test    eax, eax
0x18002a05d  jnz     loc_180029F86
0x18002a063  mov     rcx, [rsp+6C0h+phkResult]; hKey
0x18002a068  lea     rax, [rsp+6C0h+hKey]
0x18002a06d  mov     r9d, 20019h; samDesired
0x18002a073  mov     [rsp+6C0h+var_6A0], rax; phkResult
0x18002a078  xor     r8d, r8d; ulOptions
0x18002a07b  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\SchedulingAgent"
0x18002a082  call    cs:__imp_RegOpenKeyExW
0x18002a089  nop     dword ptr [rax+rax+00h]
0x18002a08e  mov     ebx, eax
0x18002a090  test    eax, eax
0x18002a092  jz      short loc_18002A0D0
0x18002a094  mov     rcx, [rsp+6C0h+phkResult]; hKey
0x18002a099  call    cs:__imp_RegCloseKey
0x18002a0a0  nop     dword ptr [rax+rax+00h]
0x18002a0a5  cmp     ebx, 3F2h
0x18002a0ab  jz      short loc_18002A0C6
0x18002a0ad  cmp     ebx, 2
0x18002a0b0  jz      short loc_18002A0C6
0x18002a0b2  test    ebx, ebx
0x18002a0b4  jle     short loc_18002A0BF
0x18002a0b6  movzx   ebx, bx
0x18002a0b9  or      ebx, 80070000h
0x18002a0bf  mov     eax, ebx
0x18002a0c1  jmp     loc_18002A49F
0x18002a0c6  mov     eax, 8004130Ch
0x18002a0cb  jmp     loc_18002A49F
0x18002a0d0  mov     r8, r14; Size
0x18002a0d3  lea     rcx, [rbp+5C0h+Buffer]; void *
0x18002a0da  xor     edx, edx; Val
0x18002a0dc  call    memset_0
0x18002a0e1  mov     rcx, [rsp+6C0h+hKey]; hKey
0x18002a0e6  lea     rax, [rsp+6C0h+cbData]
0x18002a0eb  mov     [rsp+6C0h+lpcbData], rax; lpcbData
0x18002a0f0  lea     rdx, aTasksfolder; "TasksFolder"
0x18002a0f7  lea     rax, [rbp+5C0h+Buffer]
0x18002a0fe  mov     [rsp+6C0h+cbData], 208h
0x18002a106  xor     r9d, r9d; lpType
0x18002a109  mov     [rsp+6C0h+var_6A0], rax; lpData
0x18002a10e  xor     r8d, r8d; lpReserved
0x18002a111  call    cs:__imp_RegQueryValueExW
0x18002a118  nop     dword ptr [rax+rax+00h]
0x18002a11d  mov     r12d, 105h
0x18002a123  test    eax, eax
0x18002a125  jz      short loc_18002A13F
0x18002a127  lea     r8, aSystemrootTask; "%SystemRoot%\\Tasks"
0x18002a12e  mov     edx, r12d; unsigned __int64
0x18002a131  lea     rcx, [rbp+5C0h+Buffer]; unsigned __int16 *
0x18002a138  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a13d  jmp     short loc_18002A159
0x18002a13f  mov     ecx, [rsp+6C0h+cbData]
0x18002a143  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18002a147  cmp     rcx, r14
0x18002a14a  jnb     loc_18002A338
0x18002a150  mov     [rbp+rcx+5C0h+Buffer], r13w
0x18002a159  mov     rcx, [rsp+6C0h+hKey]; hKey
0x18002a15e  call    cs:__imp_RegCloseKey
0x18002a165  nop     dword ptr [rax+rax+00h]
0x18002a16a  mov     r8d, 0Ch; MaxCount
0x18002a170  lea     rdx, aSystemroot_0; "%SystemRoot%"
0x18002a177  lea     rcx, [rbp+5C0h+Buffer]; String1
0x18002a17e  mov     [rsp+6C0h+nSize], r8d
0x18002a183  call    cs:__imp__wcsnicmp
0x18002a18a  nop     dword ptr [rax+rax+00h]
0x18002a18f  test    eax, eax
0x18002a191  jz      short loc_18002A1C5
0x18002a193  mov     r8d, 8; MaxCount
0x18002a199  lea     rdx, aWindir; "%WinDir%"
0x18002a1a0  lea     rcx, [rbp+5C0h+Buffer]; String1
0x18002a1a7  mov     [rsp+6C0h+nSize], r8d
0x18002a1ac  call    cs:__imp__wcsnicmp
0x18002a1b3  nop     dword ptr [rax+rax+00h]
0x18002a1b8  test    eax, eax
0x18002a1ba  jz      short loc_18002A1C5
0x18002a1bc  mov     eax, r13d
0x18002a1bf  mov     [rsp+6C0h+nSize], eax
0x18002a1c3  jmp     short loc_18002A1C9
0x18002a1c5  mov     eax, [rsp+6C0h+nSize]
0x18002a1c9  test    eax, eax
0x18002a1cb  jz      loc_18002A2BF
0x18002a1d1  mov     rcx, [rsp+6C0h+phkResult]; hKey
0x18002a1d6  lea     rax, [rsp+6C0h+var_680]
0x18002a1db  mov     r9d, 0F003Fh; samDesired
0x18002a1e1  mov     [rsp+6C0h+var_6A0], rax; phkResult
0x18002a1e6  xor     r8d, r8d; ulOptions
0x18002a1e9  mov     [rsp+6C0h+var_680], r13
0x18002a1ee  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002a1f5  call    cs:__imp_RegOpenKeyExW
0x18002a1fc  nop     dword ptr [rax+rax+00h]
0x18002a201  mov     ebx, eax
0x18002a203  test    eax, eax
0x18002a205  jz      short loc_18002A21D
0x18002a207  mov     rcx, [rsp+6C0h+phkResult]; hKey
0x18002a20c  call    cs:__imp_RegCloseKey
0x18002a213  nop     dword ptr [rax+rax+00h]
0x18002a218  jmp     loc_18002A0B2
0x18002a21d  mov     r8, r14; Size
0x18002a220  lea     rcx, [rbp+5C0h+Data]; void *
0x18002a227  xor     edx, edx; Val
0x18002a229  call    memset_0
0x18002a22e  mov     rcx, [rsp+6C0h+var_680]; hKey
0x18002a233  lea     rax, [rsp+6C0h+cbData]
0x18002a238  mov     [rsp+6C0h+lpcbData], rax; lpcbData
0x18002a23d  lea     rdx, aSystemroot; "SystemRoot"
0x18002a244  lea     rax, [rbp+5C0h+Data]
0x18002a24b  mov     [rsp+6C0h+cbData], r14d
0x18002a250  xor     r9d, r9d; lpType
0x18002a253  mov     [rsp+6C0h+var_6A0], rax; lpData
0x18002a258  xor     r8d, r8d; lpReserved
0x18002a25b  call    cs:__imp_RegQueryValueExW
0x18002a262  nop     dword ptr [rax+rax+00h]
0x18002a267  mov     rcx, [rsp+6C0h+var_680]; hKey
0x18002a26c  mov     ebx, eax
0x18002a26e  test    eax, eax
0x18002a270  jz      short loc_18002A280
0x18002a272  call    cs:__imp_RegCloseKey
0x18002a279  nop     dword ptr [rax+rax+00h]
0x18002a27e  jmp     short loc_18002A207
0x18002a280  call    cs:__imp_RegCloseKey
0x18002a287  nop     dword ptr [rax+rax+00h]
0x18002a28c  lea     r8, [rbp+5C0h+Data]; unsigned __int16 *
0x18002a293  mov     rdx, r12; unsigned __int64
0x18002a296  lea     rcx, [rsp+6C0h+String2]; unsigned __int16 *
0x18002a29b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a2a0  mov     r10d, [rsp+6C0h+nSize]
0x18002a2a5  lea     r8, [rbp+5C0h+Buffer]
0x18002a2ac  mov     rdx, r12; unsigned __int64
0x18002a2af  lea     rcx, [rsp+6C0h+String2]; unsigned __int16 *
0x18002a2b4  lea     r8, [r8+r10*2]; unsigned __int16 *
0x18002a2b8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a2bd  jmp     short loc_18002A2D3
0x18002a2bf  lea     r8, [rbp+5C0h+Buffer]; unsigned __int16 *
0x18002a2c6  mov     rdx, r12; unsigned __int64
0x18002a2c9  lea     rcx, [rsp+6C0h+String2]; unsigned __int16 *
0x18002a2ce  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a2d3  mov     rcx, [rsp+6C0h+phkResult]; hKey
0x18002a2d8  call    cs:__imp_RegCloseKey
0x18002a2df  nop     dword ptr [rax+rax+00h]
0x18002a2e4  movzx   ecx, [rsp+6C0h+String2]
0x18002a2e9  lea     eax, [rcx-41h]
0x18002a2ec  cmp     ax, 19h
0x18002a2f0  jbe     short loc_18002A2FC
0x18002a2f2  sub     cx, 61h ; 'a'
0x18002a2f6  cmp     cx, 19h
0x18002a2fa  ja      short loc_18002A32E
0x18002a2fc  cmp     [rsp+6C0h+var_66E], 3Ah ; ':'
0x18002a302  jnz     short loc_18002A32E
0x18002a304  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002a308  lea     rcx, [rsp+6C0h+String2]
0x18002a30d  mov     rax, rbx
0x18002a310  inc     rax
0x18002a313  cmp     [rcx+rax*2], r13w
0x18002a318  jnz     short loc_18002A310
0x18002a31a  mov     rcx, rbx
0x18002a31d  inc     rcx
0x18002a320  cmp     [rsi+rcx*2], r13w
0x18002a325  jnz     short loc_18002A31D
0x18002a327  add     eax, 2
0x18002a32a  add     eax, ecx
0x18002a32c  jmp     short loc_18002A358
0x18002a32e  mov     eax, 800700A1h
0x18002a333  jmp     loc_18002A49F
0x18002a338  call    __report_rangecheckfailure
0x18002a33e  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; _TasksFolderInfo g_TasksFolderInfo
0x18002a345  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002a349  mov     rax, rbx
0x18002a34c  inc     rax
0x18002a34f  cmp     [rcx+rax*2], r13w
0x18002a354  jnz     short loc_18002A34C
0x18002a356  inc     eax
0x18002a358  mov     [rsp+6C0h+nSize], eax
0x18002a35c  mov     r12d, eax
0x18002a35f  mov     eax, 2
0x18002a364  mul     r12
0x18002a367  cmovb   rax, rbx
0x18002a36b  mov     rcx, rax; Size
0x18002a36e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a373  mov     r14, rax
0x18002a376  test    rax, rax
0x18002a379  jnz     short loc_18002A385
0x18002a37b  mov     eax, 8007000Eh
0x18002a380  jmp     loc_18002A49F
0x18002a385  mov     [rax], r13w
0x18002a389  test    r15d, r15d
0x18002a38c  jnz     short loc_18002A3CC
0x18002a38e  mov     rax, rbx
0x18002a391  inc     rax
0x18002a394  cmp     [rsi+rax*2], r13w
0x18002a399  jnz     short loc_18002A391
0x18002a39b  lea     r13, [rax+1]
0x18002a39f  mov     eax, 2
0x18002a3a4  mul     r13
0x18002a3a7  cmovb   rax, rbx
0x18002a3ab  mov     rcx, rax; Size
0x18002a3ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a3b3  mov     rbx, rax
0x18002a3b6  test    rax, rax
0x18002a3b9  jnz     short loc_18002A3C5
0x18002a3bb  mov     rcx, r14; Block
0x18002a3be  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002a3c3  jmp     short loc_18002A37B
0x18002a3c5  xor     eax, eax
0x18002a3c7  mov     [rbx], ax
0x18002a3ca  jmp     short loc_18002A3CE
0x18002a3cc  xor     ebx, ebx
0x18002a3ce  mov     rcx, [rdi+38h]; Block
0x18002a3d2  test    rcx, rcx
0x18002a3d5  jz      short loc_18002A3DC
0x18002a3d7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002a3dc  mov     rcx, [rdi+40h]; Block
0x18002a3e0  test    rcx, rcx
0x18002a3e3  jz      short loc_18002A3EA
0x18002a3e5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002a3ea  test    r15d, r15d
0x18002a3ed  jz      short loc_18002A444
0x18002a3ef  mov     [rdi+40h], r14
  ... truncated ...
```
