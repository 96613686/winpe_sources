# CSchedule::SetTargetComputer(ushort const *)

- ea: `0x180028620`
- end: `0x180028b8d`
- name: `?SetTargetComputer@CSchedule@@UEAAJPEBG@Z`
- size: `1389`
- prototype: `__int64 __fastcall(CSchedule *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800031a0`
- `0x180003ef0`
- `0x180007488`
- `0x1800074c8`
- `0x180008538`
- `0x180027044`
- `0x180028620`
- `0x18002b0d0`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180028877`
- `msvcrt!_wcsnicmp` at `0x18002889a`
- `msvcrt!_wcsnicmp` at `0x180028877`
- `msvcrt!_wcsnicmp` at `0x18002889a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800286a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800286a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002879f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028858`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800288ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028948`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028950`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800289a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002879f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028858`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800288ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028948`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028950`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800289a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028811`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028937`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028811`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028937`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002878e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800288dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002878e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800288dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800286e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800286e0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180028698`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180028698`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002870a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002871d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002870a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002871d`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x180028761`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x180028761`

## string_xrefs

- `0x180028787`: `SOFTWARE\Microsoft\SchedulingAgent`
- `0x1800287f0`: `TasksFolder`
- `0x180028821`: `%SystemRoot%\Tasks`

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
0x180028620  mov     [rsp-8+arg_10], rbx
0x180028625  push    rbp
0x180028626  push    rsi
0x180028627  push    rdi
0x180028628  push    r12
0x18002862a  push    r13
0x18002862c  push    r14
0x18002862e  push    r15
0x180028630  lea     rbp, [rsp-590h]
0x180028638  sub     rsp, 690h
0x18002863f  mov     rax, cs:__security_cookie
0x180028646  xor     rax, rsp
0x180028649  mov     [rbp+5C0h+var_40], rax
0x180028650  xor     r13d, r13d
0x180028653  mov     rsi, rdx
0x180028656  mov     [rsp+6C0h+nSize], r13d
0x18002865b  mov     rdi, rcx
0x18002865e  lea     r15d, [r13+1]
0x180028662  test    rdx, rdx
0x180028665  jz      loc_18002872A
0x18002866b  mov     ebx, 202h
0x180028670  lea     rcx, [rbp+5C0h+Buffer]; void *
0x180028677  mov     r8d, ebx; Size
0x18002867a  xor     edx, edx; Val
0x18002867c  call    memset_0
0x180028681  mov     r14d, 101h
0x180028687  lea     rdx, [rsp+6C0h+nSize]; nSize
0x18002868c  lea     rcx, [rbp+5C0h+Buffer]; lpBuffer
0x180028693  mov     [rsp+6C0h+nSize], r14d
0x180028698  call    cs:__imp_GetComputerNameW
0x18002869e  test    eax, eax
0x1800286a0  jnz     short loc_1800286BD
0x1800286a2  call    cs:__imp_GetLastError
0x1800286a8  test    eax, eax
0x1800286aa  jle     loc_180028B63
0x1800286b0  movzx   eax, ax
0x1800286b3  or      eax, 80070000h
0x1800286b8  jmp     loc_180028B63
0x1800286bd  mov     r8, rbx; Size
0x1800286c0  lea     rcx, [rsp+6C0h+String2]; void *
0x1800286c5  xor     edx, edx; Val
0x1800286c7  call    memset_0
0x1800286cc  lea     r8, [rsp+6C0h+nSize]; nSize
0x1800286d1  mov     [rsp+6C0h+nSize], r14d
0x1800286d6  lea     rdx, [rsp+6C0h+String2]; lpBuffer
0x1800286db  mov     ecx, 7; NameType
0x1800286e0  call    cs:__imp_GetComputerNameExW
0x1800286e6  test    eax, eax
0x1800286e8  jz      short loc_1800286A2
0x1800286ea  cmp     [rsi], r13w
0x1800286ee  jz      loc_180028B5E
0x1800286f4  cmp     [rsi+2], r13w
0x1800286f9  jz      loc_180028B5E
0x1800286ff  lea     rdx, [rbp+5C0h+Buffer]; lpString2
0x180028706  lea     rcx, [rsi+4]; lpString1
0x18002870a  call    cs:__imp_lstrcmpiW
0x180028710  test    eax, eax
0x180028712  jz      short loc_18002872A
0x180028714  lea     rdx, [rsp+6C0h+String2]; lpString2
0x180028719  lea     rcx, [rsi+4]; lpString1
0x18002871d  call    cs:__imp_lstrcmpiW
0x180028723  test    eax, eax
0x180028725  jz      short loc_18002872A
0x180028727  mov     r15d, r13d
0x18002872a  mov     r14d, 20Ah
0x180028730  lea     rcx, [rsp+6C0h+String2]; void *
0x180028735  mov     r8d, r14d; Size
0x180028738  xor     edx, edx; Val
0x18002873a  call    memset_0
0x18002873f  test    r15d, r15d
0x180028742  jnz     loc_180028A02
0x180028748  lea     r8, [rsp+6C0h+phkResult]; phkResult
0x18002874d  mov     [rsp+6C0h+phkResult], r13
0x180028752  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180028759  mov     [rsp+6C0h+hKey], r13
0x18002875e  mov     rcx, rsi; lpMachineName
0x180028761  call    cs:__imp_RegConnectRegistryW
0x180028767  test    eax, eax
0x180028769  jnz     loc_1800286AA
0x18002876f  mov     rcx, [rsp+6C0h+phkResult]; hKey
0x180028774  lea     rax, [rsp+6C0h+hKey]
0x180028779  mov     r9d, 20019h; samDesired
0x18002877f  mov     [rsp+6C0h+var_6A0], rax; phkResult
0x180028784  xor     r8d, r8d; ulOptions
0x180028787  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\SchedulingAgent"
0x18002878e  call    cs:__imp_RegOpenKeyExW
0x180028794  mov     ebx, eax
0x180028796  test    eax, eax
0x180028798  jz      short loc_1800287D0
0x18002879a  mov     rcx, [rsp+6C0h+phkResult]; hKey
0x18002879f  call    cs:__imp_RegCloseKey
0x1800287a5  cmp     ebx, 3F2h
0x1800287ab  jz      short loc_1800287C6
0x1800287ad  cmp     ebx, 2
0x1800287b0  jz      short loc_1800287C6
0x1800287b2  test    ebx, ebx
0x1800287b4  jle     short loc_1800287BF
0x1800287b6  movzx   ebx, bx
0x1800287b9  or      ebx, 80070000h
0x1800287bf  mov     eax, ebx
0x1800287c1  jmp     loc_180028B63
0x1800287c6  mov     eax, 8004130Ch
0x1800287cb  jmp     loc_180028B63
0x1800287d0  mov     r8, r14; Size
0x1800287d3  lea     rcx, [rbp+5C0h+Buffer]; void *
0x1800287da  xor     edx, edx; Val
0x1800287dc  call    memset_0
0x1800287e1  mov     rcx, [rsp+6C0h+hKey]; hKey
0x1800287e6  lea     rax, [rsp+6C0h+cbData]
0x1800287eb  mov     [rsp+6C0h+lpcbData], rax; lpcbData
0x1800287f0  lea     rdx, aTasksfolder; "TasksFolder"
0x1800287f7  lea     rax, [rbp+5C0h+Buffer]
0x1800287fe  mov     [rsp+6C0h+cbData], 208h
0x180028806  xor     r9d, r9d; lpType
0x180028809  mov     [rsp+6C0h+var_6A0], rax; lpData
0x18002880e  xor     r8d, r8d; lpReserved
0x180028811  call    cs:__imp_RegQueryValueExW
0x180028817  mov     r12d, 105h
0x18002881d  test    eax, eax
0x18002881f  jz      short loc_180028839
0x180028821  lea     r8, aSystemrootTask; "%SystemRoot%\\Tasks"
0x180028828  mov     edx, r12d; unsigned __int64
0x18002882b  lea     rcx, [rbp+5C0h+Buffer]; unsigned __int16 *
0x180028832  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180028837  jmp     short loc_180028853
0x180028839  mov     ecx, [rsp+6C0h+cbData]
0x18002883d  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180028841  cmp     rcx, r14
0x180028844  jnb     loc_1800289FC
0x18002884a  mov     [rbp+rcx+5C0h+Buffer], r13w
0x180028853  mov     rcx, [rsp+6C0h+hKey]; hKey
0x180028858  call    cs:__imp_RegCloseKey
0x18002885e  mov     r8d, 0Ch; MaxCount
0x180028864  lea     rdx, aSystemroot_0; "%SystemRoot%"
0x18002886b  lea     rcx, [rbp+5C0h+Buffer]; String1
0x180028872  mov     [rsp+6C0h+nSize], r8d
0x180028877  call    cs:__imp__wcsnicmp
0x18002887d  test    eax, eax
0x18002887f  jz      short loc_1800288AD
0x180028881  mov     r8d, 8; MaxCount
0x180028887  lea     rdx, aWindir; "%WinDir%"
0x18002888e  lea     rcx, [rbp+5C0h+Buffer]; String1
0x180028895  mov     [rsp+6C0h+nSize], r8d
0x18002889a  call    cs:__imp__wcsnicmp
0x1800288a0  test    eax, eax
0x1800288a2  jz      short loc_1800288AD
0x1800288a4  mov     eax, r13d
0x1800288a7  mov     [rsp+6C0h+nSize], eax
0x1800288ab  jmp     short loc_1800288B1
0x1800288ad  mov     eax, [rsp+6C0h+nSize]
0x1800288b1  test    eax, eax
0x1800288b3  jz      loc_180028989
0x1800288b9  mov     rcx, [rsp+6C0h+phkResult]; hKey
0x1800288be  lea     rax, [rsp+6C0h+var_680]
0x1800288c3  mov     r9d, 0F003Fh; samDesired
0x1800288c9  mov     [rsp+6C0h+var_6A0], rax; phkResult
0x1800288ce  xor     r8d, r8d; ulOptions
0x1800288d1  mov     [rsp+6C0h+var_680], r13
0x1800288d6  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800288dd  call    cs:__imp_RegOpenKeyExW
0x1800288e3  mov     ebx, eax
0x1800288e5  test    eax, eax
0x1800288e7  jz      short loc_1800288F9
0x1800288e9  mov     rcx, [rsp+6C0h+phkResult]; hKey
0x1800288ee  call    cs:__imp_RegCloseKey
0x1800288f4  jmp     loc_1800287B2
0x1800288f9  mov     r8, r14; Size
0x1800288fc  lea     rcx, [rbp+5C0h+Data]; void *
0x180028903  xor     edx, edx; Val
0x180028905  call    memset_0
0x18002890a  mov     rcx, [rsp+6C0h+var_680]; hKey
0x18002890f  lea     rax, [rsp+6C0h+cbData]
0x180028914  mov     [rsp+6C0h+lpcbData], rax; lpcbData
0x180028919  lea     rdx, aSystemroot; "SystemRoot"
0x180028920  lea     rax, [rbp+5C0h+Data]
0x180028927  mov     [rsp+6C0h+cbData], r14d
0x18002892c  xor     r9d, r9d; lpType
0x18002892f  mov     [rsp+6C0h+var_6A0], rax; lpData
0x180028934  xor     r8d, r8d; lpReserved
0x180028937  call    cs:__imp_RegQueryValueExW
0x18002893d  mov     rcx, [rsp+6C0h+var_680]; hKey
0x180028942  mov     ebx, eax
0x180028944  test    eax, eax
0x180028946  jz      short loc_180028950
0x180028948  call    cs:__imp_RegCloseKey
0x18002894e  jmp     short loc_1800288E9
0x180028950  call    cs:__imp_RegCloseKey
0x180028956  lea     r8, [rbp+5C0h+Data]; unsigned __int16 *
0x18002895d  mov     rdx, r12; unsigned __int64
0x180028960  lea     rcx, [rsp+6C0h+String2]; unsigned __int16 *
0x180028965  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002896a  mov     r10d, [rsp+6C0h+nSize]
0x18002896f  lea     r8, [rbp+5C0h+Buffer]
0x180028976  mov     rdx, r12; unsigned __int64
0x180028979  lea     rcx, [rsp+6C0h+String2]; unsigned __int16 *
0x18002897e  lea     r8, [r8+r10*2]; unsigned __int16 *
0x180028982  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180028987  jmp     short loc_18002899D
0x180028989  lea     r8, [rbp+5C0h+Buffer]; unsigned __int16 *
0x180028990  mov     rdx, r12; unsigned __int64
0x180028993  lea     rcx, [rsp+6C0h+String2]; unsigned __int16 *
0x180028998  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002899d  mov     rcx, [rsp+6C0h+phkResult]; hKey
0x1800289a2  call    cs:__imp_RegCloseKey
0x1800289a8  movzx   ecx, [rsp+6C0h+String2]
0x1800289ad  lea     eax, [rcx-41h]
0x1800289b0  cmp     ax, 19h
0x1800289b4  jbe     short loc_1800289C0
0x1800289b6  sub     cx, 61h ; 'a'
0x1800289ba  cmp     cx, 19h
0x1800289be  ja      short loc_1800289F2
0x1800289c0  cmp     [rsp+6C0h+var_66E], 3Ah ; ':'
0x1800289c6  jnz     short loc_1800289F2
0x1800289c8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800289cc  lea     rcx, [rsp+6C0h+String2]
0x1800289d1  mov     rax, rbx
0x1800289d4  inc     rax
0x1800289d7  cmp     [rcx+rax*2], r13w
0x1800289dc  jnz     short loc_1800289D4
0x1800289de  mov     rcx, rbx
0x1800289e1  inc     rcx
0x1800289e4  cmp     [rsi+rcx*2], r13w
0x1800289e9  jnz     short loc_1800289E1
0x1800289eb  add     eax, 2
0x1800289ee  add     eax, ecx
0x1800289f0  jmp     short loc_180028A1C
0x1800289f2  mov     eax, 800700A1h
0x1800289f7  jmp     loc_180028B63
0x1800289fc  call    __report_rangecheckfailure
0x180028a02  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; _TasksFolderInfo g_TasksFolderInfo
0x180028a09  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180028a0d  mov     rax, rbx
0x180028a10  inc     rax
0x180028a13  cmp     [rcx+rax*2], r13w
0x180028a18  jnz     short loc_180028A10
0x180028a1a  inc     eax
0x180028a1c  mov     [rsp+6C0h+nSize], eax
0x180028a20  mov     r12d, eax
0x180028a23  mov     eax, 2
0x180028a28  mul     r12
0x180028a2b  cmovb   rax, rbx
0x180028a2f  mov     rcx, rax; Size
0x180028a32  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028a37  mov     r14, rax
0x180028a3a  test    rax, rax
0x180028a3d  jnz     short loc_180028A49
0x180028a3f  mov     eax, 8007000Eh
0x180028a44  jmp     loc_180028B63
0x180028a49  mov     [rax], r13w
0x180028a4d  test    r15d, r15d
0x180028a50  jnz     short loc_180028A90
0x180028a52  mov     rax, rbx
0x180028a55  inc     rax
0x180028a58  cmp     [rsi+rax*2], r13w
0x180028a5d  jnz     short loc_180028A55
0x180028a5f  lea     r13, [rax+1]
0x180028a63  mov     eax, 2
0x180028a68  mul     r13
0x180028a6b  cmovb   rax, rbx
0x180028a6f  mov     rcx, rax; Size
0x180028a72  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028a77  mov     rbx, rax
0x180028a7a  test    rax, rax
0x180028a7d  jnz     short loc_180028A89
0x180028a7f  mov     rcx, r14; Block
0x180028a82  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180028a87  jmp     short loc_180028A3F
0x180028a89  xor     eax, eax
0x180028a8b  mov     [rbx], ax
0x180028a8e  jmp     short loc_180028A92
0x180028a90  xor     ebx, ebx
0x180028a92  mov     rcx, [rdi+38h]; Block
0x180028a96  test    rcx, rcx
0x180028a99  jz      short loc_180028AA0
0x180028a9b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180028aa0  mov     rcx, [rdi+40h]; Block
0x180028aa4  test    rcx, rcx
0x180028aa7  jz      short loc_180028AAE
0x180028aa9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180028aae  test    r15d, r15d
0x180028ab1  jz      short loc_180028B08
0x180028ab3  mov     [rdi+40h], r14
0x180028ab7  xor     esi, esi
0x180028ab9  mov     [rdi+38h], rsi
0x180028abd  mov     rdx, r12; unsigned __int64
0x180028ac0  mov     r8, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; unsigned __int16 *
0x180028ac7  mov     rcx, r14; unsigned __int16 *
0x180028aca  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180028acf  mov     rcx, [rdi+40h]; lpFileName
0x180028ad3  lea     edx, [rsi+1]; DesiredAccess
0x180028ad6  call    ?FolderAccessCheckOnThreadToken@@YAJPEBGK@Z; FolderAccessCheckOnThreadToken(ushort const *,ulong)
0x180028adb  mov     ebx, eax
0x180028add  test    eax, eax
0x180028adf  jns     short loc_180028B5A
0x180028ae1  mov     rcx, [rdi+38h]; Block
0x180028ae5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180028aea  mov     rcx, [rdi+40h]; Block
0x180028aee  mov     [rdi+38h], rsi
0x180028af2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180028af7  mov     rcx, rdi; this
  ... truncated ...
```
