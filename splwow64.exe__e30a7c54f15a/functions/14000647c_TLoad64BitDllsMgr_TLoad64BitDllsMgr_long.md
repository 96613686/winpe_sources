# TLoad64BitDllsMgr::TLoad64BitDllsMgr(long *)

- ea: `0x14000647c`
- end: `0x140006617`
- name: `??0TLoad64BitDllsMgr@@QEAA@PEAJ@Z`
- size: `411`
- prototype: `TLoad64BitDllsMgr *__fastcall(TLoad64BitDllsMgr *__hidden this, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x14000cca0`

## callees

- `0x14000647c`
- `0x14000f190`

## import_xrefs

- `ADVAPI32!RegOpenKeyW` at `0x140006538`
- `ADVAPI32!RegOpenKeyW` at `0x140006538`
- `ADVAPI32!RegQueryValueExW` at `0x140006568`
- `ADVAPI32!RegQueryValueExW` at `0x1400065a8`
- `ADVAPI32!RegQueryValueExW` at `0x140006568`
- `ADVAPI32!RegQueryValueExW` at `0x1400065a8`
- `ADVAPI32!RegCloseKey` at `0x1400065c6`
- `ADVAPI32!RegCloseKey` at `0x1400065c6`
- `KERNEL32!InitializeCriticalSection` at `0x1400065d8`
- `KERNEL32!InitializeCriticalSection` at `0x1400065d8`
- `KERNEL32!GetCurrentProcessId` at `0x1400065cc`
- `KERNEL32!GetCurrentProcessId` at `0x1400065cc`
- `KERNEL32!GetTickCount64` at `0x1400065de`
- `KERNEL32!GetTickCount64` at `0x1400065de`
- `KERNEL32!ProcessIdToSessionId` at `0x1400065ee`
- `KERNEL32!ProcessIdToSessionId` at `0x1400065ee`

## string_xrefs

- `0x14000648e`: `TLoad64BitDllsMgr`

## pseudocode

```c
TLoad64BitDllsMgr *__fastcall TLoad64BitDllsMgr::TLoad64BitDllsMgr(TLoad64BitDllsMgr *this, int *a2)
{
  const char *v2; // r9
  char *v5; // rcx
  __int64 v6; // rax
  __int64 v7; // r8
  char *v8; // rax
  __int64 v9; // rcx
  DWORD CurrentProcessId; // ebx
  int Data; // [rsp+50h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+28h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp+30h] BYREF

  v2 = "TLoad64BitDllsMgr";
  v5 = (char *)this + 24;
  v6 = 2147483646;
  v7 = 32;
  *(_OWORD *)v5 = 0;
  *((_OWORD *)v5 + 1) = 0;
  do
  {
    if ( !v6 )
      break;
    if ( !*v2 )
      break;
    *v5++ = *v2++;
    --v6;
    --v7;
  }
  while ( v7 );
  phkResult = 0;
  v8 = v5 - 1;
  if ( v7 )
    v8 = v5;
  cbData = 4;
  *v8 = 0;
  *(_QWORD *)this = &TLoad64BitDllsMgr::`vftable'{for `TRefCntMgr'};
  *((_QWORD *)this + 2) = &TLoad64BitDllsMgr::`vftable'{for `TPrinterDriver'};
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 8) = 120000;
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 15) = 0;
  *((_DWORD *)this + 18) = 0;
  if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Print", &phkResult) )
  {
    Data = 0;
    if ( RegQueryValueExW(phkResult, L"SplWOW64TimeOutSeconds", 0, 0, (LPBYTE)&Data, &cbData) )
    {
      Data = 0;
      cbData = 4;
      if ( RegQueryValueExW(phkResult, L"SplWOW64TimeOut", 0, 0, (LPBYTE)&Data, &cbData) )
        goto LABEL_13;
      v9 = (unsigned int)(60000 * Data);
    }
    else
    {
      v9 = (unsigned int)(1000 * Data);
    }
    *((_QWORD *)this + 8) = v9;
  }
LABEL_13:
  if ( phkResult )
    RegCloseKey(phkResult);
  CurrentProcessId = GetCurrentProcessId();
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  *((_QWORD *)this + 10) = GetTickCount64();
  ProcessIdToSessionId(CurrentProcessId, (DWORD *)this + 14);
  TRefCntMgr::AddRef(this);
  if ( a2 )
    *a2 = 0;
  return this;
}

```

## disassembly

```asm
0x14000647c  mov     [rsp-18h+arg_18], rbx
0x140006481  push    rbp
0x140006482  push    rsi
0x140006483  push    rdi
0x140006484  mov     rbp, rsp
0x140006487  sub     rsp, 30h
0x14000648b  xorps   xmm0, xmm0
0x14000648e  lea     r9, aTload64bitdlls_11; "TLoad64BitDllsMgr"
0x140006495  mov     rdi, rcx
0x140006498  mov     rsi, rdx
0x14000649b  add     rcx, 18h
0x14000649f  mov     eax, 7FFFFFFEh
0x1400064a4  mov     r8d, 20h ; ' '
0x1400064aa  movups  xmmword ptr [rcx], xmm0
0x1400064ad  movups  xmmword ptr [rcx+10h], xmm0
0x1400064b1  test    rax, rax
0x1400064b4  jz      short loc_1400064CE
0x1400064b6  mov     dl, [r9]
0x1400064b9  test    dl, dl
0x1400064bb  jz      short loc_1400064CE
0x1400064bd  mov     [rcx], dl
0x1400064bf  inc     r9
0x1400064c2  inc     rcx
0x1400064c5  dec     rax
0x1400064c8  sub     r8, 1
0x1400064cc  jnz     short loc_1400064B1
0x1400064ce  test    r8, r8
0x1400064d1  mov     [rbp+phkResult], 0
0x1400064d9  lea     rax, [rcx-1]
0x1400064dd  mov     ebx, 4
0x1400064e2  cmovnz  rax, rcx
0x1400064e6  mov     [rbp+cbData], ebx
0x1400064e9  lea     r8, [rbp+phkResult]; phkResult
0x1400064ed  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400064f4  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Pri"...
0x1400064fb  mov     byte ptr [rax], 0
0x1400064fe  lea     rax, ??_7TLoad64BitDllsMgr@@6BTRefCntMgr@@@; const TLoad64BitDllsMgr::`vftable'{for `TRefCntMgr'}
0x140006505  mov     [rdi], rax
0x140006508  lea     rax, ??_7TLoad64BitDllsMgr@@6BTPrinterDriver@@@; const TLoad64BitDllsMgr::`vftable'{for `TPrinterDriver'}
0x14000650f  mov     [rdi+10h], rax
0x140006513  mov     qword ptr [rdi+50h], 0
0x14000651b  mov     qword ptr [rdi+40h], 1D4C0h
0x140006523  mov     dword ptr [rdi+8], 0
0x14000652a  mov     dword ptr [rdi+3Ch], 0
0x140006531  mov     dword ptr [rdi+48h], 0
0x140006538  call    cs:__imp_RegOpenKeyW
0x14000653e  test    eax, eax
0x140006540  jnz     short loc_1400065BD
0x140006542  mov     rcx, [rbp+phkResult]; hKey
0x140006546  lea     rdx, ValueName; "SplWOW64TimeOutSeconds"
0x14000654d  mov     [rbp+Data], eax
0x140006550  xor     r9d, r9d; lpType
0x140006553  lea     rax, [rbp+cbData]
0x140006557  xor     r8d, r8d; lpReserved
0x14000655a  mov     [rsp+30h+lpcbData], rax; lpcbData
0x14000655f  lea     rax, [rbp+Data]
0x140006563  mov     [rsp+30h+lpData], rax; lpData
0x140006568  call    cs:__imp_RegQueryValueExW
0x14000656e  test    eax, eax
0x140006570  jnz     short loc_14000657B
0x140006572  imul    ecx, [rbp+Data], 3E8h
0x140006579  jmp     short loc_1400065B9
0x14000657b  mov     rcx, [rbp+phkResult]; hKey
0x14000657f  lea     rax, [rbp+cbData]
0x140006583  mov     [rsp+30h+lpcbData], rax; lpcbData
0x140006588  lea     rdx, aSplwow64timeou; "SplWOW64TimeOut"
0x14000658f  lea     rax, [rbp+Data]
0x140006593  mov     [rbp+Data], 0
0x14000659a  xor     r9d, r9d; lpType
0x14000659d  mov     [rsp+30h+lpData], rax; lpData
0x1400065a2  xor     r8d, r8d; lpReserved
0x1400065a5  mov     [rbp+cbData], ebx
0x1400065a8  call    cs:__imp_RegQueryValueExW
0x1400065ae  test    eax, eax
0x1400065b0  jnz     short loc_1400065BD
0x1400065b2  imul    ecx, [rbp+Data], 0EA60h
0x1400065b9  mov     [rdi+40h], rcx
0x1400065bd  mov     rcx, [rbp+phkResult]; hKey
0x1400065c1  test    rcx, rcx
0x1400065c4  jz      short loc_1400065CC
0x1400065c6  call    cs:__imp_RegCloseKey
0x1400065cc  call    cs:__imp_GetCurrentProcessId
0x1400065d2  lea     rcx, [rdi+58h]; lpCriticalSection
0x1400065d6  mov     ebx, eax
0x1400065d8  call    cs:__imp_InitializeCriticalSection
0x1400065de  call    cs:__imp_GetTickCount64
0x1400065e4  lea     rdx, [rdi+38h]; pSessionId
0x1400065e8  mov     ecx, ebx; dwProcessId
0x1400065ea  mov     [rdi+50h], rax
0x1400065ee  call    cs:__imp_ProcessIdToSessionId
0x1400065f4  mov     rcx, rdi; this
0x1400065f7  call    ?AddRef@TRefCntMgr@@UEAAKXZ; TRefCntMgr::AddRef(void)
0x1400065fc  test    rsi, rsi
0x1400065ff  jz      short loc_140006607
0x140006601  mov     dword ptr [rsi], 0
0x140006607  mov     rbx, [rsp+30h+arg_18]
0x14000660c  mov     rax, rdi
0x14000660f  add     rsp, 30h
0x140006613  pop     rdi
0x140006614  pop     rsi
0x140006615  pop     rbp
0x140006616  retn
```
