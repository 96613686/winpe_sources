# RDSHTelemetryLogging::GetSessDirActive(ulong *)

- ea: `0x1800924ac`
- end: `0x1800926c0`
- name: `?GetSessDirActive@RDSHTelemetryLogging@@CAJPEAK@Z`
- size: `532`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800926c8`

## callees

- `0x1800016a8`
- `0x1800924ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800925a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800925a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800926a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800926a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800924f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800924f7`

## string_xrefs

- `0x180092537`: `RegOpenKeyEx REG_CONTROL_TSERVER failed`
- `0x1800925a2`: `SessionDirectoryActive`

## pseudocode

```c
__int64 __fastcall RDSHTelemetryLogging::GetSessDirActive(unsigned int *a1)
{
  LSTATUS v2; // eax
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  signed int v6; // ebx
  __int16 *v7; // rdx
  const char **v8; // rax
  LSTATUS v9; // eax
  unsigned int v10; // eax
  const char **v12; // [rsp+38h] [rbp-38h]
  signed int v13; // [rsp+40h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-28h] BYREF
  const char *v15; // [rsp+50h] [rbp-20h] BYREF
  const char *v16; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v17[2]; // [rsp+60h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+98h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp+30h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+38h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey);
  v6 = v2;
  if ( v2 > 0 )
    v6 = (unsigned __int16)v2 | 0x80070000;
  if ( v6 < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_21;
    v15 = "GetSessDirActive";
    v7 = &word_1801172E6;
    v16 = "RegOpenKeyEx REG_CONTROL_TSERVER failed";
    v17[0] = "Warning HResult failed";
    v12 = &v15;
    v8 = (const char **)v17;
    goto LABEL_6;
  }
  cbData = 4;
  v9 = RegQueryValueExW(hKey, L"SessionDirectoryActive", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( v9 == 2 )
  {
    v10 = 0;
    Data = 0;
    goto LABEL_19;
  }
  if ( v9 > 0 )
    v6 = (unsigned __int16)v9 | 0x80070000;
  else
    v6 = v9;
  if ( v6 < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_21;
    v17[0] = "GetSessDirActive";
    v7 = word_1801172A2;
    v16 = "RegQueryValueEx REG_TS_SESSDIRACTIVE failed";
    v15 = "Warning HResult failed";
    v12 = (const char **)v17;
    v8 = &v15;
    goto LABEL_6;
  }
  if ( Type != 4 )
  {
    v6 = -2147024809;
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_21;
    v17[0] = "GetSessDirActive";
    v7 = &word_18011725E;
    v16 = "REG_TS_SESSDIRACTIVE not REG_DWORD";
    v15 = "Warning HResult failed";
    v12 = (const char **)v17;
    v8 = &v15;
LABEL_6:
    v13 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v3,
      (_DWORD)v7,
      v4,
      v5,
      (__int64)v8,
      (__int64)&v16,
      (__int64)&v13,
      (__int64)v12);
    goto LABEL_21;
  }
  v10 = Data;
LABEL_19:
  if ( a1 )
    *a1 = v10;
LABEL_21:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800924ac  push    rbp
0x1800924ae  push    rbx
0x1800924af  push    rdi
0x1800924b0  mov     rbp, rsp
0x1800924b3  sub     rsp, 70h
0x1800924b7  mov     rdi, rcx
0x1800924ba  mov     [rbp+hKey], 0
0x1800924c2  lea     rax, [rbp+hKey]
0x1800924c6  mov     [rbp+Type], 0
0x1800924cd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800924d4  mov     [rsp+70h+phkResult], rax; phkResult
0x1800924d9  mov     r9d, 20019h; samDesired
0x1800924df  mov     [rbp+cbData], 0
0x1800924e6  xor     r8d, r8d; ulOptions
0x1800924e9  mov     [rbp+Data], 0
0x1800924f0  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x1800924f7  call    cs:__imp_RegOpenKeyExW
0x1800924fe  nop     dword ptr [rax+rax+00h]
0x180092503  mov     ebx, eax
0x180092505  test    eax, eax
0x180092507  jle     short loc_180092512
0x180092509  movzx   ebx, ax
0x18009250c  or      ebx, 80070000h
0x180092512  test    ebx, ebx
0x180092514  jns     short loc_18009257E
0x180092516  mov     eax, cs:dword_18012E170
0x18009251c  cmp     eax, 3
0x18009251f  jbe     loc_1800926A0
0x180092525  lea     rax, aGetsessdiracti; "GetSessDirActive"
0x18009252c  mov     [rbp+var_20], rax
0x180092530  lea     rdx, word_1801172E6
0x180092537  lea     rax, aRegopenkeyexRe_0; "RegOpenKeyEx REG_CONTROL_TSERVER failed"
0x18009253e  mov     [rbp+var_18], rax
0x180092542  lea     rax, aWarningHresult; "Warning HResult failed"
0x180092549  mov     [rbp+var_10], rax
0x18009254d  lea     rax, [rbp+var_20]
0x180092551  mov     [rsp+70h+var_38], rax
0x180092556  lea     rax, [rbp+var_30]
0x18009255a  mov     [rsp+70h+var_40], rax
0x18009255f  lea     rax, [rbp+var_18]
0x180092563  mov     [rsp+70h+lpcbData], rax
0x180092568  lea     rax, [rbp+var_10]
0x18009256c  mov     [rbp+var_30], ebx
0x18009256f  mov     [rsp+70h+phkResult], rax
0x180092574  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180092579  jmp     loc_1800926A0
0x18009257e  mov     rcx, [rbp+hKey]; hKey
0x180092582  lea     rax, [rbp+cbData]
0x180092586  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18009258b  lea     r9, [rbp+Type]; lpType
0x18009258f  lea     rax, [rbp+Data]
0x180092593  mov     [rbp+cbData], 4
0x18009259a  xor     r8d, r8d; lpReserved
0x18009259d  mov     [rsp+70h+phkResult], rax; lpData
0x1800925a2  lea     rdx, aSessiondirecto_3; "SessionDirectoryActive"
0x1800925a9  call    cs:__imp_RegQueryValueExW
0x1800925b0  nop     dword ptr [rax+rax+00h]
0x1800925b5  cmp     eax, 2
0x1800925b8  jnz     short loc_1800925C4
0x1800925ba  xor     eax, eax
0x1800925bc  mov     [rbp+Data], eax
0x1800925bf  jmp     loc_180092699
0x1800925c4  test    eax, eax
0x1800925c6  jg      short loc_1800925CC
0x1800925c8  mov     ebx, eax
0x1800925ca  jmp     short loc_1800925D5
0x1800925cc  movzx   ebx, ax
0x1800925cf  or      ebx, 80070000h
0x1800925d5  test    ebx, ebx
0x1800925d7  jns     short loc_180092634
0x1800925d9  mov     eax, cs:dword_18012E170
0x1800925df  cmp     eax, 3
0x1800925e2  jbe     loc_1800926A0
0x1800925e8  lea     rax, aGetsessdiracti; "GetSessDirActive"
0x1800925ef  mov     [rbp+var_10], rax
0x1800925f3  lea     rdx, word_1801172A2
0x1800925fa  lea     rax, aRegqueryvaluee_7; "RegQueryValueEx REG_TS_SESSDIRACTIVE fa"...
0x180092601  mov     [rbp+var_18], rax
0x180092605  lea     rax, aWarningHresult; "Warning HResult failed"
0x18009260c  mov     [rbp+var_20], rax
0x180092610  lea     rax, [rbp+var_10]
0x180092614  mov     [rsp+70h+var_38], rax
0x180092619  lea     rax, [rbp+var_30]
0x18009261d  mov     [rsp+70h+var_40], rax
0x180092622  lea     rax, [rbp+var_18]
0x180092626  mov     [rsp+70h+lpcbData], rax
0x18009262b  lea     rax, [rbp+var_20]
0x18009262f  jmp     loc_18009256C
0x180092634  cmp     [rbp+Type], 4
0x180092638  jz      short loc_180092696
0x18009263a  mov     eax, cs:dword_18012E170
0x180092640  mov     ebx, 80070057h
0x180092645  cmp     eax, 3
0x180092648  jbe     short loc_1800926A0
0x18009264a  lea     rax, aGetsessdiracti; "GetSessDirActive"
0x180092651  mov     [rbp+var_10], rax
0x180092655  lea     rdx, word_18011725E
0x18009265c  lea     rax, aRegTsSessdirac; "REG_TS_SESSDIRACTIVE not REG_DWORD"
0x180092663  mov     [rbp+var_18], rax
0x180092667  lea     rax, aWarningHresult; "Warning HResult failed"
0x18009266e  mov     [rbp+var_20], rax
0x180092672  lea     rax, [rbp+var_10]
0x180092676  mov     [rsp+70h+var_38], rax
0x18009267b  lea     rax, [rbp+var_30]
0x18009267f  mov     [rsp+70h+var_40], rax
0x180092684  lea     rax, [rbp+var_18]
0x180092688  mov     [rsp+70h+lpcbData], rax
0x18009268d  lea     rax, [rbp+var_20]
0x180092691  jmp     loc_18009256C
0x180092696  mov     eax, [rbp+Data]
0x180092699  test    rdi, rdi
0x18009269c  jz      short loc_1800926A0
0x18009269e  mov     [rdi], eax
0x1800926a0  mov     rcx, [rbp+hKey]; hKey
0x1800926a4  test    rcx, rcx
0x1800926a7  jz      short loc_1800926B5
0x1800926a9  call    cs:__imp_RegCloseKey
0x1800926b0  nop     dword ptr [rax+rax+00h]
0x1800926b5  mov     eax, ebx
0x1800926b7  add     rsp, 70h
0x1800926bb  pop     rdi
0x1800926bc  pop     rbx
0x1800926bd  pop     rbp
0x1800926be  retn
```
