# CUser::TracePwdExpiryNotfn(CUser::PwdExpNotfnState,ulong,ushort *)

- ea: `0x14002d9a4`
- end: `0x14002dd73`
- name: `?TracePwdExpiryNotfn@CUser@@AEAAXW4PwdExpNotfnState@1@KPEAG@Z`
- size: `975`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14002d59c`

## callees

- `0x140001340`
- `0x140006970`
- `0x14000d4e0`
- `0x14002d9a4`
- `0x140039638`
- `0x14003d7d8`
- `0x140044800`
- `0x14004eb98`
- `0x140053720`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002dc24`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002dc73`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002dca7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002dcec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002dd1d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002dc24`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002dc73`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002dca7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002dcec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002dd1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002dd2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002dd2c`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x14002d9f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x14002d9f1`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x14002dbd8`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x14002dbd8`
- `ntdll!NtOpenThreadToken` at `0x14002db88`
- `ntdll!NtOpenThreadToken` at `0x14002db88`
- `ntdll!NtClose` at `0x14002dd45`
- `ntdll!NtClose` at `0x14002dd45`

## pseudocode

```c
unsigned int __fastcall CUser::TracePwdExpiryNotfn(CUser *a1, int a2, int a3, const BYTE *a4)
{
  int v8; // r9d
  __int16 *v9; // rdx
  int v10; // ecx
  int v11; // r9d
  unsigned int result; // eax
  int v13; // r14d
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  CUser *v19; // rcx
  HKEY phkResult; // [rsp+50h] [rbp-59h] BYREF
  __int64 v21; // [rsp+58h] [rbp-51h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-49h] BYREF
  const BYTE *v23; // [rsp+68h] [rbp-41h] BYREF
  __int128 v24; // [rsp+70h] [rbp-39h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+80h] [rbp-29h] BYREF
  __int128 v26; // [rsp+90h] [rbp-19h] BYREF
  unsigned __int16 Data[28]; // [rsp+A0h] [rbp-9h] BYREF

  SystemTime = 0;
  TokenHandle = 0;
  phkResult = 0;
  GetLocalTime(&SystemTime);
  StringCchPrintfW(
    Data,
    0x19u,
    L"%02d::%02d::%02d, %04d/%02d/%02d",
    SystemTime.wHour,
    SystemTime.wMinute,
    SystemTime.wSecond,
    SystemTime.wYear,
    SystemTime.wMonth,
    SystemTime.wDay);
  if ( (unsigned int)(a2 - 1) <= 1 )
  {
    v26 = 0;
    WLGetTSActivityId(&v26);
    if ( (unsigned int)dword_1400CF778 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400CF778, 0x400000000000LL) )
    {
      LODWORD(v21) = a3;
      v23 = a4;
      *(_QWORD *)&v24 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)byte_1400BD41D,
        (unsigned int)&v26,
        v11,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v21);
    }
  }
  else if ( a2 )
  {
    if ( a2 == 3 )
    {
      v24 = 0;
      WLGetTSActivityId(&v24);
      if ( (unsigned int)dword_1400CF778 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_1400CF778, 0x400000000000LL) )
        {
          v9 = &word_1400BD3E6;
          goto LABEL_6;
        }
      }
    }
  }
  else
  {
    v24 = 0;
    WLGetTSActivityId(&v24);
    if ( (unsigned int)dword_1400CF778 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400CF778, 0x400000000000LL) )
    {
      v9 = (__int16 *)byte_1400BD3AD;
LABEL_6:
      v21 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        (unsigned int)&dword_1400CF778,
        (_DWORD)v9,
        (unsigned int)&v24,
        v8,
        (__int64)&v21);
    }
  }
  result = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  if ( result == -1073741700 )
  {
    if ( !*((_QWORD *)a1 + 17) )
      return result;
    result = CUser::ImpersonateUser(a1, 0);
    if ( result )
      return result;
    v13 = 1;
  }
  else
  {
    v13 = 0;
    if ( !TokenHandle )
      return result;
  }
  result = RegCreateKeyW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\Winlogon\\PasswordExpiryNotification",
             &phkResult);
  if ( result )
    goto LABEL_36;
  v14 = -1;
  if ( a2 )
  {
    if ( a2 != 2 )
      goto LABEL_30;
  }
  else
  {
    v15 = -1;
    do
      ++v15;
    while ( Data[v15] );
    RegSetValueExW(phkResult, L"ShownTime", 0, 1u, (const BYTE *)Data, 2 * v15 + 2);
    a4 = &pPassword;
    Data[0] = 0;
  }
  v16 = -1;
  do
    ++v16;
  while ( Data[v16] );
  RegSetValueExW(phkResult, L"NotShownErrorTime", 0, 1u, (const BYTE *)Data, 2 * v16 + 2);
  v17 = -1;
  do
    ++v17;
  while ( *(_WORD *)&a4[2 * v17] );
  result = RegSetValueExW(phkResult, L"NotShownErrorReason", 0, 1u, a4, 2 * v17 + 2);
  if ( !a2 )
    goto LABEL_31;
LABEL_30:
  if ( a2 == 1 )
  {
LABEL_31:
    v18 = -1;
    do
      ++v18;
    while ( Data[v18] );
    RegSetValueExW(phkResult, L"NotShownTime", 0, 1u, (const BYTE *)Data, 2 * v18 + 2);
    do
      ++v14;
    while ( *(_WORD *)&a4[2 * v14] );
    result = RegSetValueExW(phkResult, L"NotShownReason", 0, 1u, a4, 2 * v14 + 2);
  }
LABEL_36:
  v19 = (CUser *)phkResult;
  if ( phkResult )
    result = RegCloseKey(phkResult);
  if ( v13 )
    result = CUser::StopImpersonating(v19);
  if ( TokenHandle )
    return NtClose(TokenHandle);
  return result;
}

```

## disassembly

```asm
0x14002d9a4  mov     [rsp-8+arg_8], rbx
0x14002d9a9  mov     [rsp-8+arg_10], rsi
0x14002d9ae  push    rbp
0x14002d9af  push    rdi
0x14002d9b0  push    r12
0x14002d9b2  push    r14
0x14002d9b4  push    r15
0x14002d9b6  lea     rbp, [rsp-37h]
0x14002d9bb  sub     rsp, 0E0h
0x14002d9c2  mov     rax, cs:__security_cookie
0x14002d9c9  xor     rax, rsp
0x14002d9cc  mov     [rbp+57h+var_28], rax
0x14002d9d0  mov     rbx, rcx
0x14002d9d3  xorps   xmm0, xmm0
0x14002d9d6  xor     r15d, r15d
0x14002d9d9  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x14002d9dd  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x14002d9e1  mov     [rbp+57h+TokenHandle], r15
0x14002d9e5  mov     rsi, r9
0x14002d9e8  mov     [rbp+57h+phkResult], r15
0x14002d9ec  mov     r14d, r8d
0x14002d9ef  mov     edi, edx
0x14002d9f1  call    cs:__imp_GetLocalTime
0x14002d9f7  movzx   ecx, [rbp+57h+SystemTime.wMonth]
0x14002d9fb  movzx   edx, [rbp+57h+SystemTime.wYear]
0x14002d9ff  movzx   r8d, [rbp+57h+SystemTime.wSecond]
0x14002da04  movzx   eax, [rbp+57h+SystemTime.wDay]
0x14002da08  movzx   r10d, [rbp+57h+SystemTime.wMinute]
0x14002da0d  movzx   r9d, [rbp+57h+SystemTime.wHour]
0x14002da12  mov     [rsp+100h+var_C0], eax
0x14002da16  mov     [rsp+100h+var_C8], ecx
0x14002da1a  lea     rcx, [rbp+57h+Data]; unsigned __int16 *
0x14002da1e  mov     dword ptr [rsp+100h+var_D0], edx
0x14002da22  lea     edx, [r15+19h]; unsigned __int64
0x14002da26  mov     [rsp+100h+cbData], r8d
0x14002da2b  lea     r8, a02d02d02d04d02; "%02d::%02d::%02d, %04d/%02d/%02d"
0x14002da32  mov     dword ptr [rsp+100h+lpData], r10d
0x14002da37  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002da3c  lea     eax, [rdi-1]
0x14002da3f  lea     r12d, [r15+1]
0x14002da43  cmp     eax, r12d
0x14002da46  jbe     loc_14002DB05
0x14002da4c  test    edi, edi
0x14002da4e  jnz     short loc_14002DABA
0x14002da50  xorps   xmm0, xmm0
0x14002da53  lea     rcx, [rbp+57h+var_90]
0x14002da57  movups  [rbp+57h+var_90], xmm0
0x14002da5b  call    WLGetTSActivityId
0x14002da60  mov     eax, cs:dword_1400CF778
0x14002da66  cmp     eax, 5
0x14002da69  jbe     loc_14002DB75
0x14002da6f  mov     rdx, 400000000000h
0x14002da79  lea     rcx, dword_1400CF778
0x14002da80  call    _tlgKeywordOn
0x14002da85  test    al, al
0x14002da87  jz      loc_14002DB75
0x14002da8d  lea     rdx, byte_1400BD3AD
0x14002da94  lea     rax, [rbp+57h+var_A8]
0x14002da98  mov     [rsp+100h+lpData], rax
0x14002da9d  lea     r8, [rbp+57h+var_90]
0x14002daa1  lea     rcx, dword_1400CF778
0x14002daa8  mov     [rbp+57h+var_A8], 1000000h
0x14002dab0  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x14002dab5  jmp     loc_14002DB75
0x14002daba  cmp     edi, 3
0x14002dabd  jnz     loc_14002DB75
0x14002dac3  xorps   xmm0, xmm0
0x14002dac6  lea     rcx, [rbp+57h+var_90]
0x14002daca  movups  [rbp+57h+var_90], xmm0
0x14002dace  call    WLGetTSActivityId
0x14002dad3  mov     eax, cs:dword_1400CF778
0x14002dad9  cmp     eax, 5
0x14002dadc  jbe     loc_14002DB75
0x14002dae2  mov     rdx, 400000000000h
0x14002daec  lea     rcx, dword_1400CF778
0x14002daf3  call    _tlgKeywordOn
0x14002daf8  test    al, al
0x14002dafa  jz      short loc_14002DB75
0x14002dafc  lea     rdx, word_1400BD3E6
0x14002db03  jmp     short loc_14002DA94
0x14002db05  xorps   xmm0, xmm0
0x14002db08  lea     rcx, [rbp+57h+var_70]
0x14002db0c  movups  [rbp+57h+var_70], xmm0
0x14002db10  call    WLGetTSActivityId
0x14002db15  mov     eax, cs:dword_1400CF778
0x14002db1b  cmp     eax, 5
0x14002db1e  jbe     short loc_14002DB75
0x14002db20  mov     rdx, 400000000000h
0x14002db2a  lea     rcx, dword_1400CF778
0x14002db31  call    _tlgKeywordOn
0x14002db36  test    al, al
0x14002db38  jz      short loc_14002DB75
0x14002db3a  lea     rax, [rbp+57h+var_A8]
0x14002db3e  mov     dword ptr [rbp+57h+var_A8], r14d
0x14002db42  mov     [rsp+100h+var_D0], rax
0x14002db47  lea     r8, [rbp+57h+var_70]
0x14002db4b  lea     rax, [rbp+57h+var_98]
0x14002db4f  mov     [rbp+57h+var_98], rsi
0x14002db53  mov     qword ptr [rsp+100h+cbData], rax
0x14002db58  lea     rdx, byte_1400BD41D
0x14002db5f  lea     rax, [rbp+57h+var_90]
0x14002db63  mov     qword ptr [rbp+57h+var_90], 1000000h
0x14002db6b  mov     [rsp+100h+lpData], rax
0x14002db70  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x14002db75  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x14002db79  mov     r8b, r12b; OpenAsSelf
0x14002db7c  mov     edx, 8; DesiredAccess
0x14002db81  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14002db88  call    cs:__imp_NtOpenThreadToken
0x14002db8e  cmp     eax, 0C000007Ch
0x14002db93  jnz     short loc_14002DBB9
0x14002db95  cmp     [rbx+88h], r15
0x14002db9c  jz      loc_14002DD4B
0x14002dba2  xor     edx, edx; int
0x14002dba4  mov     rcx, rbx; this
0x14002dba7  call    ?ImpersonateUser@CUser@@QEAAKH@Z; CUser::ImpersonateUser(int)
0x14002dbac  test    eax, eax
0x14002dbae  jnz     loc_14002DD4B
0x14002dbb4  mov     r14d, r12d
0x14002dbb7  jmp     short loc_14002DBC6
0x14002dbb9  mov     r14d, r15d
0x14002dbbc  cmp     [rbp+57h+TokenHandle], r15
0x14002dbc0  jz      loc_14002DD4B
0x14002dbc6  lea     r8, [rbp+57h+phkResult]; phkResult
0x14002dbca  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14002dbd1  lea     rdx, aSoftwareMicros_26; "Software\\Microsoft\\Windows\\Winlogon"...
0x14002dbd8  call    cs:__imp_RegCreateKeyW
0x14002dbde  test    eax, eax
0x14002dbe0  jnz     loc_14002DD23
0x14002dbe6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14002dbea  test    edi, edi
0x14002dbec  jnz     short loc_14002DC38
0x14002dbee  lea     rcx, [rbp+57h+Data]
0x14002dbf2  mov     rax, rbx
0x14002dbf5  inc     rax
0x14002dbf8  cmp     [rcx+rax*2], r15w
0x14002dbfd  jnz     short loc_14002DBF5
0x14002dbff  mov     rcx, [rbp+57h+phkResult]; hKey
0x14002dc03  lea     eax, ds:2[rax*2]
0x14002dc0a  mov     [rsp+100h+cbData], eax; cbData
0x14002dc0e  lea     rdx, aShowntime; "ShownTime"
0x14002dc15  lea     rax, [rbp+57h+Data]
0x14002dc19  mov     r9d, r12d; dwType
0x14002dc1c  xor     r8d, r8d; Reserved
0x14002dc1f  mov     [rsp+100h+lpData], rax; lpData
0x14002dc24  call    cs:__imp_RegSetValueExW
0x14002dc2a  lea     rsi, pPassword
0x14002dc31  mov     [rbp+57h+Data], r15w
0x14002dc36  jmp     short loc_14002DC3D
0x14002dc38  cmp     edi, 2
0x14002dc3b  jnz     short loc_14002DCB1
0x14002dc3d  lea     rcx, [rbp+57h+Data]
0x14002dc41  mov     rax, rbx
0x14002dc44  inc     rax
0x14002dc47  cmp     [rcx+rax*2], r15w
0x14002dc4c  jnz     short loc_14002DC44
0x14002dc4e  mov     rcx, [rbp+57h+phkResult]; hKey
0x14002dc52  lea     eax, ds:2[rax*2]
0x14002dc59  mov     [rsp+100h+cbData], eax; cbData
0x14002dc5d  lea     rdx, aNotshownerrort; "NotShownErrorTime"
0x14002dc64  lea     rax, [rbp+57h+Data]
0x14002dc68  mov     r9d, r12d; dwType
0x14002dc6b  xor     r8d, r8d; Reserved
0x14002dc6e  mov     [rsp+100h+lpData], rax; lpData
0x14002dc73  call    cs:__imp_RegSetValueExW
0x14002dc79  mov     rax, rbx
0x14002dc7c  inc     rax
0x14002dc7f  cmp     [rsi+rax*2], r15w
0x14002dc84  jnz     short loc_14002DC7C
0x14002dc86  mov     rcx, [rbp+57h+phkResult]; hKey
0x14002dc8a  lea     eax, ds:2[rax*2]
0x14002dc91  mov     [rsp+100h+cbData], eax; cbData
0x14002dc95  lea     rdx, aNotshownerrorr; "NotShownErrorReason"
0x14002dc9c  mov     r9d, r12d; dwType
0x14002dc9f  mov     [rsp+100h+lpData], rsi; lpData
0x14002dca4  xor     r8d, r8d; Reserved
0x14002dca7  call    cs:__imp_RegSetValueExW
0x14002dcad  test    edi, edi
0x14002dcaf  jz      short loc_14002DCB6
0x14002dcb1  cmp     edi, r12d
0x14002dcb4  jnz     short loc_14002DD23
0x14002dcb6  lea     rcx, [rbp+57h+Data]
0x14002dcba  mov     rax, rbx
0x14002dcbd  inc     rax
0x14002dcc0  cmp     [rcx+rax*2], r15w
0x14002dcc5  jnz     short loc_14002DCBD
0x14002dcc7  mov     rcx, [rbp+57h+phkResult]; hKey
0x14002dccb  lea     eax, ds:2[rax*2]
0x14002dcd2  mov     [rsp+100h+cbData], eax; cbData
0x14002dcd6  lea     rdx, aNotshowntime; "NotShownTime"
0x14002dcdd  lea     rax, [rbp+57h+Data]
0x14002dce1  mov     r9d, r12d; dwType
0x14002dce4  xor     r8d, r8d; Reserved
0x14002dce7  mov     [rsp+100h+lpData], rax; lpData
0x14002dcec  call    cs:__imp_RegSetValueExW
0x14002dcf2  inc     rbx
0x14002dcf5  cmp     [rsi+rbx*2], r15w
0x14002dcfa  jnz     short loc_14002DCF2
0x14002dcfc  mov     rcx, [rbp+57h+phkResult]; hKey
0x14002dd00  lea     eax, ds:2[rbx*2]
0x14002dd07  mov     [rsp+100h+cbData], eax; cbData
0x14002dd0b  lea     rdx, aNotshownreason; "NotShownReason"
0x14002dd12  mov     r9d, r12d; dwType
0x14002dd15  mov     [rsp+100h+lpData], rsi; lpData
0x14002dd1a  xor     r8d, r8d; Reserved
0x14002dd1d  call    cs:__imp_RegSetValueExW
0x14002dd23  mov     rcx, [rbp+57h+phkResult]; hKey
0x14002dd27  test    rcx, rcx
0x14002dd2a  jz      short loc_14002DD32
0x14002dd2c  call    cs:__imp_RegCloseKey
0x14002dd32  test    r14d, r14d
0x14002dd35  jz      short loc_14002DD3C
0x14002dd37  call    ?StopImpersonating@CUser@@QEAAKXZ; CUser::StopImpersonating(void)
0x14002dd3c  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x14002dd40  test    rcx, rcx
0x14002dd43  jz      short loc_14002DD4B
0x14002dd45  call    cs:__imp_NtClose
0x14002dd4b  mov     rcx, [rbp+57h+var_28]
0x14002dd4f  xor     rcx, rsp; StackCookie
0x14002dd52  call    __security_check_cookie
0x14002dd57  lea     r11, [rsp+100h+var_20]
0x14002dd5f  mov     rbx, [r11+38h]
0x14002dd63  mov     rsi, [r11+40h]
0x14002dd67  mov     rsp, r11
0x14002dd6a  pop     r15
0x14002dd6c  pop     r14
0x14002dd6e  pop     r12
0x14002dd70  pop     rdi
0x14002dd71  pop     rbp
0x14002dd72  retn
```
