# CWPPLoggerConfig::ReadTraceConfig(void)

- ea: `0x18001e494`
- end: `0x18001e6f1`
- name: `?ReadTraceConfig@CWPPLoggerConfig@@QEAAJXZ`
- size: `605`
- prototype: `__int64 __fastcall(CWPPLoggerConfig *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001e23c`
- `0x18001e6f8`

## callees

- `0x180001008`
- `0x1800016dc`
- `0x180001878`
- `0x180013970`
- `0x18001a280`
- `0x18001ad5c`
- `0x18001e494`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e510`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e510`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e5d0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e5d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e6ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e6ce`

## string_xrefs

- `0x18001e54b`: `RegOpenKeyEx failed`
- `0x18001e61f`: `Setting log file size from registry entry DebugMaxFileSize`

## pseudocode

```c
__int64 __fastcall CWPPLoggerConfig::ReadTraceConfig(CWPPLoggerConfig *this)
{
  LSTATUS v2; // eax
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  unsigned int v6; // edi
  __int64 i; // rsi
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  char *v11; // rdx
  const char *v12; // rax
  const char *v14; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  const char *v18; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE *v19; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v21[528]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  memset_0(v21, 0, 0x208u);
  cbData = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey);
  v6 = v2;
  if ( !v2 )
  {
    v6 = 0;
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 2); i = (unsigned int)(i + 1) )
      CWPPLoggerGuidConfig::ReadTraceConfig((CWPPLoggerGuidConfig *)(*((_QWORD *)this + 2) + 40 * i));
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"DebugMaxFileSize", 0, &Type, Data, &cbData) )
      goto LABEL_17;
    if ( Type == 4 )
    {
      if ( *(_DWORD *)Data )
      {
        if ( *((_DWORD *)this + 13) == *(_DWORD *)Data )
          goto LABEL_21;
        *((_DWORD *)this + 13) = *(_DWORD *)Data;
        if ( (unsigned int)dword_180084170 <= 5 )
          goto LABEL_21;
        v11 = (char *)&unk_180078C60;
        v14 = *(const char **)this;
        v19 = (_BYTE *)*((unsigned int *)this + 13);
        v12 = "Setting log file size from registry entry DebugMaxFileSize";
        goto LABEL_20;
      }
    }
    else if ( *(_DWORD *)Data )
    {
LABEL_17:
      if ( *((_DWORD *)this + 13) == 2048 )
        goto LABEL_21;
      *((_DWORD *)this + 13) = 2048;
      if ( (unsigned int)dword_180084170 <= 5 )
        goto LABEL_21;
      v11 = &byte_180078C1F;
      v14 = *(const char **)this;
      v19 = (_BYTE *)*((unsigned int *)this + 13);
      v12 = "Using Default log file size";
LABEL_20:
      v18 = v12;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        v8,
        (_DWORD)v11,
        v9,
        v10,
        (__int64)&v18,
        (__int64)&v19,
        (__int64)&v14);
      goto LABEL_21;
    }
    if ( (unsigned int)dword_180084170 > 5 )
    {
      v14 = "Ignoring DebugMaxFileSize, it has be greater than 0, using default";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_180084170,
        (unsigned int)byte_180078CA1,
        0,
        0,
        (__int64)&v14);
    }
    goto LABEL_17;
  }
  if ( v2 > 0 )
    v6 = (unsigned __int16)v2 | 0x80070000;
  if ( (unsigned int)dword_180084170 > 2 )
  {
    LODWORD(v18) = v6;
    v19 = v21;
    v14 = "RegOpenKeyEx failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v3,
      (unsigned int)qword_180078B58,
      v4,
      v5,
      (__int64)&v14,
      (__int64)&v18,
      (__int64)&v19);
  }
LABEL_21:
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x18001e494  push    rbp
0x18001e496  push    rbx
0x18001e497  push    rsi
0x18001e498  push    rdi
0x18001e499  lea     rbp, [rsp-198h]
0x18001e4a1  sub     rsp, 298h
0x18001e4a8  mov     rax, cs:__security_cookie
0x18001e4af  xor     rax, rsp
0x18001e4b2  mov     [rbp+1B0h+var_30], rax
0x18001e4b9  mov     rbx, rcx
0x18001e4bc  mov     [rsp+2B0h+hKey], 0
0x18001e4c5  lea     rcx, [rsp+2B0h+var_240]; void *
0x18001e4ca  xor     edx, edx; Val
0x18001e4cc  mov     r8d, 208h; Size
0x18001e4d2  call    memset_0
0x18001e4d7  lea     rax, [rsp+2B0h+hKey]
0x18001e4dc  mov     [rsp+2B0h+cbData], 0
0x18001e4e4  mov     r9d, 20019h; samDesired
0x18001e4ea  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18001e4ef  xor     r8d, r8d; ulOptions
0x18001e4f2  mov     [rsp+2B0h+Type], 0
0x18001e4fa  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x18001e501  mov     dword ptr [rsp+2B0h+Data], 0
0x18001e509  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e510  call    cs:__imp_RegOpenKeyExW
0x18001e516  mov     edi, eax
0x18001e518  test    eax, eax
0x18001e51a  jz      short loc_18001E57F
0x18001e51c  jle     short loc_18001E527
0x18001e51e  movzx   edi, ax
0x18001e521  or      edi, 80070000h
0x18001e527  mov     eax, cs:dword_180084170
0x18001e52d  cmp     eax, 2
0x18001e530  jbe     loc_18001E6C4
0x18001e536  lea     rax, [rsp+2B0h+var_240]
0x18001e53b  mov     dword ptr [rsp+2B0h+var_258], edi
0x18001e53f  mov     [rsp+2B0h+var_250], rax
0x18001e544  lea     rdx, qword_180078B58
0x18001e54b  lea     rax, aRegopenkeyexFa_3; "RegOpenKeyEx failed"
0x18001e552  mov     [rsp+2B0h+var_270], rax
0x18001e557  lea     rax, [rsp+2B0h+var_250]
0x18001e55c  mov     [rsp+2B0h+var_280], rax
0x18001e561  lea     rax, [rsp+2B0h+var_258]
0x18001e566  mov     [rsp+2B0h+lpcbData], rax
0x18001e56b  lea     rax, [rsp+2B0h+var_270]
0x18001e570  mov     [rsp+2B0h+phkResult], rax
0x18001e575  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18001e57a  jmp     loc_18001E6C4
0x18001e57f  xor     edi, edi
0x18001e581  xor     esi, esi
0x18001e583  cmp     [rbx+8], esi
0x18001e586  jbe     short loc_18001E5A0
0x18001e588  mov     rax, [rbx+10h]
0x18001e58c  lea     rcx, [rsi+rsi*4]
0x18001e590  lea     rcx, [rax+rcx*8]; this
0x18001e594  call    ?ReadTraceConfig@CWPPLoggerGuidConfig@@QEAAJXZ; CWPPLoggerGuidConfig::ReadTraceConfig(void)
0x18001e599  inc     esi
0x18001e59b  cmp     esi, [rbx+8]
0x18001e59e  jb      short loc_18001E588
0x18001e5a0  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18001e5a5  lea     rax, [rsp+2B0h+cbData]
0x18001e5aa  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x18001e5af  lea     r9, [rsp+2B0h+Type]; lpType
0x18001e5b4  lea     rax, [rsp+2B0h+Data]
0x18001e5b9  mov     [rsp+2B0h+cbData], 4
0x18001e5c1  xor     r8d, r8d; lpReserved
0x18001e5c4  mov     [rsp+2B0h+phkResult], rax; lpData
0x18001e5c9  lea     rdx, aDebugmaxfilesi; "DebugMaxFileSize"
0x18001e5d0  call    cs:__imp_RegQueryValueExW
0x18001e5d6  test    eax, eax
0x18001e5d8  jnz     loc_18001E666
0x18001e5de  cmp     [rsp+2B0h+Type], 4
0x18001e5e3  mov     eax, dword ptr [rsp+2B0h+Data]
0x18001e5e7  jnz     short loc_18001E628
0x18001e5e9  test    eax, eax
0x18001e5eb  jz      short loc_18001E62C
0x18001e5ed  cmp     [rbx+34h], eax
0x18001e5f0  jz      loc_18001E6C4
0x18001e5f6  mov     [rbx+34h], eax
0x18001e5f9  mov     eax, cs:dword_180084170
0x18001e5ff  cmp     eax, 5
0x18001e602  jbe     loc_18001E6C4
0x18001e608  mov     rax, [rbx]
0x18001e60b  lea     rdx, unk_180078C60
0x18001e612  mov     [rsp+2B0h+var_270], rax
0x18001e617  mov     eax, [rbx+34h]
0x18001e61a  mov     [rsp+2B0h+var_250], rax
0x18001e61f  lea     rax, aSettingLogFile; "Setting log file size from registry ent"...
0x18001e626  jmp     short loc_18001E69C
0x18001e628  test    eax, eax
0x18001e62a  jnz     short loc_18001E666
0x18001e62c  mov     eax, cs:dword_180084170
0x18001e632  cmp     eax, 5
0x18001e635  jbe     short loc_18001E666
0x18001e637  lea     rax, aIgnoringDebugm; "Ignoring DebugMaxFileSize, it has be gr"...
0x18001e63e  xor     r9d, r9d
0x18001e641  mov     [rsp+2B0h+var_270], rax
0x18001e646  lea     rdx, byte_180078CA1
0x18001e64d  lea     rax, [rsp+2B0h+var_270]
0x18001e652  xor     r8d, r8d
0x18001e655  lea     rcx, dword_180084170
0x18001e65c  mov     [rsp+2B0h+phkResult], rax
0x18001e661  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18001e666  mov     eax, 800h
0x18001e66b  cmp     [rbx+34h], eax
0x18001e66e  jz      short loc_18001E6C4
0x18001e670  mov     [rbx+34h], eax
0x18001e673  mov     eax, cs:dword_180084170
0x18001e679  cmp     eax, 5
0x18001e67c  jbe     short loc_18001E6C4
0x18001e67e  mov     rax, [rbx]
0x18001e681  lea     rdx, byte_180078C1F
0x18001e688  mov     [rsp+2B0h+var_270], rax
0x18001e68d  mov     eax, [rbx+34h]
0x18001e690  mov     [rsp+2B0h+var_250], rax
0x18001e695  lea     rax, aUsingDefaultLo; "Using Default log file size"
0x18001e69c  mov     [rsp+2B0h+var_258], rax
0x18001e6a1  lea     rax, [rsp+2B0h+var_270]
0x18001e6a6  mov     [rsp+2B0h+var_280], rax
0x18001e6ab  lea     rax, [rsp+2B0h+var_250]
0x18001e6b0  mov     [rsp+2B0h+lpcbData], rax
0x18001e6b5  lea     rax, [rsp+2B0h+var_258]
0x18001e6ba  mov     [rsp+2B0h+phkResult], rax
0x18001e6bf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18001e6c4  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18001e6c9  test    rcx, rcx
0x18001e6cc  jz      short loc_18001E6D4
0x18001e6ce  call    cs:__imp_RegCloseKey
0x18001e6d4  mov     eax, edi
0x18001e6d6  mov     rcx, [rbp+1B0h+var_30]
0x18001e6dd  xor     rcx, rsp; StackCookie
0x18001e6e0  call    __security_check_cookie
0x18001e6e5  add     rsp, 298h
0x18001e6ec  pop     rdi
0x18001e6ed  pop     rsi
0x18001e6ee  pop     rbx
0x18001e6ef  pop     rbp
0x18001e6f0  retn
```
