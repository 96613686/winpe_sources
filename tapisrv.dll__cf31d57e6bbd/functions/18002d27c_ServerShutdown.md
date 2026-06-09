# ServerShutdown

- ea: `0x18002d27c`
- end: `0x18002d561`
- name: `ServerShutdown`
- size: `741`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004fcc`
- `0x180020db4`
- `0x18002e9b0`

## callees

- `0x180001600`
- `0x18002ba10`
- `0x18002c8d4`
- `0x18002d27c`
- `0x18003d234`
- `0x180040010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d49d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d49d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d464`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d493`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d464`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d493`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d42c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d42c`
- `KERNEL32!DeleteCriticalSection` at `0x18002d329`
- `KERNEL32!DeleteCriticalSection` at `0x18002d329`
- `KERNEL32!FreeLibrary` at `0x18002d30c`
- `KERNEL32!FreeLibrary` at `0x18002d30c`
- `KERNEL32!CloseHandle` at `0x18002d31f`
- `KERNEL32!CloseHandle` at `0x18002d31f`
- `KERNEL32!Sleep` at `0x18002d2db`
- `KERNEL32!Sleep` at `0x18002d2db`

## pseudocode

```c
__int64 ServerShutdown()
{
  int v0; // ebx
  unsigned int i; // ecx
  unsigned int *v2; // rdi
  unsigned int *v3; // rbx
  unsigned int v4; // edi
  _QWORD *v5; // rbx
  unsigned int v6; // edi
  _QWORD *v7; // rbx
  LPVOID *v8; // rdi
  LPVOID *v9; // rbx
  BYTE Data[8]; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-40h] BYREF
  WCHAR ValueName[8]; // [rsp+40h] [rbp-38h] BYREF
  WCHAR v14[8]; // [rsp+50h] [rbp-28h] BYREF

  v0 = 200;
  gbQueueSPEvents = 0;
  do
  {
    if ( gbSPEventHandlerThreadExit )
      break;
    for ( i = 0; i < gdwNumSPEventHandlerThreads; ++i )
    {
      if ( *((LPVOID *)aSPEventHandlerThreadInfo + 8 * (unsigned __int64)i) != (char *)aSPEventHandlerThreadInfo
                                                                             + 64 * (unsigned __int64)i )
        break;
    }
    if ( i == gdwNumSPEventHandlerThreads )
      break;
    Sleep(0x64u);
    --v0;
  }
  while ( v0 );
  v2 = (unsigned int *)qword_180051910;
  if ( qword_180051910 )
  {
    do
    {
      v3 = (unsigned int *)*((_QWORD *)v2 + 6);
      (*((void (__fastcall **)(_QWORD, _QWORD))v2 + 124))(v2[7], v2[8]);
      FreeLibrary(*((HMODULE *)v2 + 2));
      MyCloseMutex(*((_QWORD *)v2 + 1));
      CloseHandle(*((HANDLE *)v2 + 10));
      DeleteCriticalSection((LPCRITICAL_SECTION)(v2 + 22));
      ServerFree(*((LPVOID *)v2 + 8));
      ServerFree(v2);
      v2 = v3;
    }
    while ( v3 );
  }
  qword_180051910 = 0;
  while ( 1 )
  {
    v5 = qword_180051920;
    if ( !qword_180051920 )
      break;
    v4 = 0;
    if ( *((_DWORD *)qword_180051920 + 1) )
    {
      do
      {
        if ( !LODWORD(v5[5 * v4 + 6]) )
          MyCloseMutex(v5[5 * v4 + 4]);
        ++v4;
      }
      while ( v4 < *((_DWORD *)v5 + 1) );
    }
    qword_180051920 = (LPVOID)v5[1];
    ServerFree(v5);
  }
  while ( 1 )
  {
    v7 = qword_180051930;
    if ( !qword_180051930 )
      break;
    v6 = 0;
    if ( *((_DWORD *)qword_180051930 + 1) )
    {
      do
      {
        if ( !LODWORD(v7[5 * v6 + 6]) )
          MyCloseMutex(v7[5 * v6 + 4]);
        ++v6;
      }
      while ( v6 < *((_DWORD *)v7 + 1) );
    }
    qword_180051930 = (LPVOID)v7[1];
    ServerFree(v7);
  }
  wcscpy(ValueName, L"Perf1");
  wcscpy(v14, L"Perf2");
  hKey = 0;
  *(_DWORD *)Data = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony",
          0,
          0xF003Fu,
          &hKey) )
  {
    *(_DWORD *)Data = dword_18005191C + 1346720326;
    RegSetValueExW(hKey, ValueName, 0, 4u, Data, 4u);
    *(_DWORD *)Data = dword_18005192C + 1346720326;
    RegSetValueExW(hKey, v14, 0, 4u, Data, 4u);
    RegCloseKey(hKey);
  }
  dword_180051900 &= ~1u;
  v8 = (LPVOID *)qword_180051998;
  if ( qword_180051998 )
  {
    do
    {
      ServerFree(v8[1]);
      ServerFree(v8[3]);
      v9 = (LPVOID *)v8[5];
      ServerFree(v8);
      v8 = v9;
    }
    while ( v9 );
  }
  qword_180051998 = 0;
  if ( gpLineInfoList )
  {
    ServerFree(gpLineInfoList);
    gpLineInfoList = 0;
    gftLineLastWrite = 0;
  }
  if ( gpPhoneInfoList )
  {
    ServerFree(gpPhoneInfoList);
    gpPhoneInfoList = 0;
    gftPhoneLastWrite = 0;
  }
  if ( gpLineDevFlags )
  {
    ServerFree(gpLineDevFlags);
    gpLineDevFlags = 0;
    gdwNumFlags = 0;
  }
  gbLockMMCWrite = 0;
  OnProxySCPShutdown();
  return 0;
}

```

## disassembly

```asm
0x18002d27c  push    rbp
0x18002d27e  push    rbx
0x18002d27f  push    rsi
0x18002d280  push    rdi
0x18002d281  mov     rbp, rsp
0x18002d284  sub     rsp, 78h
0x18002d288  mov     rax, cs:__security_cookie
0x18002d28f  xor     rax, rsp
0x18002d292  mov     [rbp+var_18], rax
0x18002d296  xor     esi, esi
0x18002d298  mov     ebx, 0C8h
0x18002d29d  mov     cs:gbQueueSPEvents, esi
0x18002d2a3  cmp     cs:gbSPEventHandlerThreadExit, esi
0x18002d2a9  jnz     short loc_18002D2E6
0x18002d2ab  mov     edx, cs:gdwNumSPEventHandlerThreads
0x18002d2b1  mov     ecx, esi
0x18002d2b3  test    edx, edx
0x18002d2b5  jz      short loc_18002D2D2
0x18002d2b7  mov     r8, cs:aSPEventHandlerThreadInfo
0x18002d2be  mov     eax, ecx
0x18002d2c0  shl     rax, 6
0x18002d2c4  add     rax, r8
0x18002d2c7  cmp     [rax], rax
0x18002d2ca  jnz     short loc_18002D2D2
0x18002d2cc  inc     ecx
0x18002d2ce  cmp     ecx, edx
0x18002d2d0  jb      short loc_18002D2BE
0x18002d2d2  cmp     ecx, edx
0x18002d2d4  jz      short loc_18002D2E6
0x18002d2d6  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18002d2db  call    cs:__imp_Sleep
0x18002d2e1  add     ebx, 0FFFFFFFFh
0x18002d2e4  jnz     short loc_18002D2A3
0x18002d2e6  mov     rdi, cs:qword_180051910
0x18002d2ed  test    rdi, rdi
0x18002d2f0  jz      short loc_18002D348
0x18002d2f2  mov     edx, [rdi+20h]
0x18002d2f5  mov     ecx, [rdi+1Ch]
0x18002d2f8  mov     rax, [rdi+3E0h]
0x18002d2ff  mov     rbx, [rdi+30h]
0x18002d303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d308  mov     rcx, [rdi+10h]; hLibModule
0x18002d30c  call    cs:__imp_FreeLibrary
0x18002d312  mov     rcx, [rdi+8]
0x18002d316  call    MyCloseMutex
0x18002d31b  mov     rcx, [rdi+50h]; hObject
0x18002d31f  call    cs:__imp_CloseHandle
0x18002d325  lea     rcx, [rdi+58h]; lpCriticalSection
0x18002d329  call    cs:__imp_DeleteCriticalSection
0x18002d32f  mov     rcx, [rdi+40h]; lpMem
0x18002d333  call    ServerFree
0x18002d338  mov     rcx, rdi; lpMem
0x18002d33b  call    ServerFree
0x18002d340  mov     rdi, rbx
0x18002d343  test    rbx, rbx
0x18002d346  jnz     short loc_18002D2F2
0x18002d348  mov     cs:qword_180051910, rsi
0x18002d34f  jmp     short loc_18002D388
0x18002d351  mov     edi, esi
0x18002d353  cmp     [rbx+4], esi
0x18002d356  jbe     short loc_18002D375
0x18002d358  mov     eax, edi
0x18002d35a  lea     rcx, [rax+rax*4]
0x18002d35e  cmp     [rbx+rcx*8+30h], esi
0x18002d362  jnz     short loc_18002D36E
0x18002d364  mov     rcx, [rbx+rcx*8+20h]
0x18002d369  call    MyCloseMutex
0x18002d36e  inc     edi
0x18002d370  cmp     edi, [rbx+4]
0x18002d373  jb      short loc_18002D358
0x18002d375  mov     rax, [rbx+8]
0x18002d379  mov     rcx, rbx; lpMem
0x18002d37c  mov     cs:qword_180051920, rax
0x18002d383  call    ServerFree
0x18002d388  mov     rbx, cs:qword_180051920
0x18002d38f  test    rbx, rbx
0x18002d392  jnz     short loc_18002D351
0x18002d394  jmp     short loc_18002D3CD
0x18002d396  mov     edi, esi
0x18002d398  cmp     [rbx+4], esi
0x18002d39b  jbe     short loc_18002D3BA
0x18002d39d  mov     eax, edi
0x18002d39f  lea     rcx, [rax+rax*4]
0x18002d3a3  cmp     [rbx+rcx*8+30h], esi
0x18002d3a7  jnz     short loc_18002D3B3
0x18002d3a9  mov     rcx, [rbx+rcx*8+20h]
0x18002d3ae  call    MyCloseMutex
0x18002d3b3  inc     edi
0x18002d3b5  cmp     edi, [rbx+4]
0x18002d3b8  jb      short loc_18002D39D
0x18002d3ba  mov     rax, [rbx+8]
0x18002d3be  mov     rcx, rbx; lpMem
0x18002d3c1  mov     cs:qword_180051930, rax
0x18002d3c8  call    ServerFree
0x18002d3cd  mov     rbx, cs:qword_180051930
0x18002d3d4  test    rbx, rbx
0x18002d3d7  jnz     short loc_18002D396
0x18002d3d9  mov     eax, dword ptr cs:aPerf1+8; "1"
0x18002d3df  lea     rdx, gszRegKeyTelephony; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002d3e6  movsd   xmm0, qword ptr cs:aPerf1; "Perf1"
0x18002d3ee  mov     r9d, 0F003Fh; samDesired
0x18002d3f4  mov     [rbp+var_30], eax
0x18002d3f7  xor     r8d, r8d; ulOptions
0x18002d3fa  mov     eax, dword ptr cs:aPerf2+8; "2"
0x18002d400  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d407  mov     [rbp+var_20], eax
0x18002d40a  lea     rax, [rbp+hKey]
0x18002d40e  movsd   qword ptr [rbp+ValueName], xmm0
0x18002d413  movsd   xmm0, qword ptr cs:aPerf2; "Perf2"
0x18002d41b  mov     [rsp+78h+phkResult], rax; phkResult
0x18002d420  movsd   qword ptr [rbp+var_28], xmm0
0x18002d425  mov     [rbp+hKey], rsi
0x18002d429  mov     dword ptr [rbp+Data], esi
0x18002d42c  call    cs:__imp_RegOpenKeyExW
0x18002d432  test    eax, eax
0x18002d434  jnz     short loc_18002D4A3
0x18002d436  mov     eax, cs:dword_18005191C
0x18002d43c  lea     rdx, [rbp+ValueName]; lpValueName
0x18002d440  mov     rcx, [rbp+hKey]; hKey
0x18002d444  add     eax, 50455246h
0x18002d449  mov     dword ptr [rbp+Data], eax
0x18002d44c  mov     ebx, 4
0x18002d451  lea     rax, [rbp+Data]
0x18002d455  mov     [rsp+78h+cbData], ebx; cbData
0x18002d459  mov     r9d, ebx; dwType
0x18002d45c  mov     [rsp+78h+phkResult], rax; lpData
0x18002d461  xor     r8d, r8d; Reserved
0x18002d464  call    cs:__imp_RegSetValueExW
0x18002d46a  mov     eax, cs:dword_18005192C
0x18002d470  lea     rdx, [rbp+var_28]; lpValueName
0x18002d474  mov     rcx, [rbp+hKey]; hKey
0x18002d478  add     eax, 50455246h
0x18002d47d  mov     dword ptr [rbp+Data], eax
0x18002d480  mov     r9d, ebx; dwType
0x18002d483  lea     rax, [rbp+Data]
0x18002d487  mov     [rsp+78h+cbData], ebx; cbData
0x18002d48b  xor     r8d, r8d; Reserved
0x18002d48e  mov     [rsp+78h+phkResult], rax; lpData
0x18002d493  call    cs:__imp_RegSetValueExW
0x18002d499  mov     rcx, [rbp+hKey]; hKey
0x18002d49d  call    cs:__imp_RegCloseKey
0x18002d4a3  and     cs:dword_180051900, 0FFFFFFFEh
0x18002d4aa  mov     rdi, cs:qword_180051998
0x18002d4b1  test    rdi, rdi
0x18002d4b4  jz      short loc_18002D4DC
0x18002d4b6  mov     rcx, [rdi+8]; lpMem
0x18002d4ba  call    ServerFree
0x18002d4bf  mov     rcx, [rdi+18h]; lpMem
0x18002d4c3  call    ServerFree
0x18002d4c8  mov     rbx, [rdi+28h]
0x18002d4cc  mov     rcx, rdi; lpMem
0x18002d4cf  call    ServerFree
0x18002d4d4  mov     rdi, rbx
0x18002d4d7  test    rbx, rbx
0x18002d4da  jnz     short loc_18002D4B6
0x18002d4dc  mov     rcx, cs:gpLineInfoList; lpMem
0x18002d4e3  mov     cs:qword_180051998, rsi
0x18002d4ea  test    rcx, rcx
0x18002d4ed  jz      short loc_18002D502
0x18002d4ef  call    ServerFree
0x18002d4f4  mov     cs:gpLineInfoList, rsi
0x18002d4fb  mov     cs:gftLineLastWrite, rsi
0x18002d502  mov     rcx, cs:gpPhoneInfoList; lpMem
0x18002d509  test    rcx, rcx
0x18002d50c  jz      short loc_18002D521
0x18002d50e  call    ServerFree
0x18002d513  mov     cs:gpPhoneInfoList, rsi
0x18002d51a  mov     cs:gftPhoneLastWrite, rsi
0x18002d521  mov     rcx, cs:gpLineDevFlags; lpMem
0x18002d528  test    rcx, rcx
0x18002d52b  jz      short loc_18002D53F
0x18002d52d  call    ServerFree
0x18002d532  mov     cs:gpLineDevFlags, rsi
0x18002d539  mov     cs:gdwNumFlags, esi
0x18002d53f  mov     cs:gbLockMMCWrite, esi
0x18002d545  call    OnProxySCPShutdown
0x18002d54a  xor     eax, eax
0x18002d54c  mov     rcx, [rbp+var_18]
0x18002d550  xor     rcx, rsp; StackCookie
0x18002d553  call    __security_check_cookie
0x18002d558  add     rsp, 78h
0x18002d55c  pop     rdi
0x18002d55d  pop     rsi
0x18002d55e  pop     rbx
0x18002d55f  pop     rbp
0x18002d560  retn
```
