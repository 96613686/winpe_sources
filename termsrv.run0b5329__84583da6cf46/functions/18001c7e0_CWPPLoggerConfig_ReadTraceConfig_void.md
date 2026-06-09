# CWPPLoggerConfig::ReadTraceConfig(void)

- ea: `0x18001c7e0`
- end: `0x18001cc18`
- name: `?ReadTraceConfig@CWPPLoggerConfig@@QEAAJXZ`
- size: `1080`
- prototype: `__int64 __fastcall(CWPPLoggerConfig *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800b78dc`
- `0x1800b7b78`

## callees

- `0x1800061b8`
- `0x18001c7e0`
- `0x18002a19c`
- `0x1800321f0`
- `0x1800330c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c98b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c98b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cbf7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cbf7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c860`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c860`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001cac0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001cbc7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001cac0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001cbc7`

## string_xrefs

- `0x18001c8d2`: `RegOpenKeyEx failed`
- `0x18001c9e8`: `Setting log file size from registry entry DebugMaxFileSize`

## pseudocode

```c
__int64 __fastcall CWPPLoggerConfig::ReadTraceConfig(CWPPLoggerConfig *this)
{
  LSTATUS v2; // eax
  unsigned int v3; // esi
  __int64 v4; // rax
  bool v5; // zf
  EVENT_DESCRIPTOR *p_EventDescriptor; // rdx
  __int16 *v7; // rax
  unsigned int i; // edi
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  const unsigned __int16 *v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  __int64 v16; // [rsp+48h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-B8h] BYREF
  int Data; // [rsp+54h] [rbp-B4h] BYREF
  DWORD Type[2]; // [rsp+58h] [rbp-B0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-A8h] BYREF
  EVENT_DESCRIPTOR v21; // [rsp+70h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+88h] [rbp-80h] BYREF
  char *v24; // [rsp+98h] [rbp-70h]
  int v25; // [rsp+A0h] [rbp-68h]
  int v26; // [rsp+A4h] [rbp-64h]
  const char *v27; // [rsp+A8h] [rbp-60h]
  __int64 v28; // [rsp+B0h] [rbp-58h]
  EVENT_DESCRIPTOR *v29; // [rsp+B8h] [rbp-50h]
  __int64 v30; // [rsp+C0h] [rbp-48h]
  const unsigned __int16 *v31; // [rsp+C8h] [rbp-40h]
  int v32; // [rsp+D0h] [rbp-38h]
  int v33; // [rsp+D4h] [rbp-34h]
  _WORD v34[264]; // [rsp+D8h] [rbp-30h] BYREF

  hKey = 0;
  memset_0(v34, 0, 0x208u);
  cbData = 0;
  Type[0] = 0;
  Data = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    if ( (unsigned int)dword_180128170 > 2 )
    {
      *(_DWORD *)&v21.Id = v3;
      v4 = -1;
      do
        v5 = v34[++v4] == 0;
      while ( !v5 );
      v33 = 0;
      v32 = 2 * v4 + 2;
      v31 = v34;
      v29 = &v21;
      v30 = 4;
      v27 = "RegOpenKeyEx failed";
      p_EventDescriptor = &EventDescriptor;
      *(_DWORD *)&EventDescriptor.Level = 2;
      UserData.Ptr = (ULONGLONG)off_180128178;
      v28 = 20;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_180128178;
      v7 = word_180114B32;
      v25 = 28;
LABEL_27:
      v24 = (char *)v7;
      UserData.Reserved = 2;
      v26 = 1;
      LODWORD(v16) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, p_EventDescriptor, 0, 0, 5u, &UserData);
      goto LABEL_28;
    }
    goto LABEL_28;
  }
  v3 = 0;
  for ( i = 0; i < *((_DWORD *)this + 2); ++i )
    CWPPLoggerGuidConfig::ReadTraceConfig((CWPPLoggerGuidConfig *)(*((_QWORD *)this + 2) + 40LL * i));
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"DebugMaxFileSize", 0, Type, (LPBYTE)&Data, &cbData) )
  {
    if ( Type[0] == 4 )
    {
      if ( Data )
      {
        if ( *((_DWORD *)this + 13) != Data )
        {
          *((_DWORD *)this + 13) = Data;
          if ( (unsigned int)dword_180128170 > 5 )
          {
            v16 = *(_QWORD *)this;
            *(_QWORD *)&v21.Id = *((unsigned int *)this + 13);
            *(_QWORD *)&EventDescriptor.Id = "Setting log file size from registry entry DebugMaxFileSize";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
              v9,
              (unsigned int)&byte_180114C2F,
              v10,
              v11,
              (__int64)&EventDescriptor,
              (__int64)&v21,
              (__int64)&v16);
          }
        }
        goto LABEL_28;
      }
    }
    else if ( Data )
    {
      goto LABEL_19;
    }
    if ( (unsigned int)dword_180128170 > 5 )
    {
      v28 = 67;
      v27 = "Ignoring DebugMaxFileSize, it has be greater than 0, using default";
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_180128178;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_180128178;
      v24 = byte_180114C7B;
      UserData.Reserved = 2;
      v25 = 16;
      v26 = 1;
      LODWORD(v16) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
  }
LABEL_19:
  if ( *((_DWORD *)this + 13) != 2048 )
  {
    *((_DWORD *)this + 13) = 2048;
    if ( (unsigned int)dword_180128170 > 5 )
    {
      v12 = *(const unsigned __int16 **)this;
      *(_QWORD *)&EventDescriptor.Id = *((unsigned int *)this + 13);
      if ( v12 )
      {
        v13 = -1;
        do
          v5 = v12[++v13] == 0;
        while ( !v5 );
        v14 = 2 * v13 + 2;
      }
      else
      {
        v12 = &qword_1800D7B88;
        v14 = 2;
      }
      v32 = v14;
      p_EventDescriptor = &v21;
      v31 = v12;
      v29 = &EventDescriptor;
      v27 = "Using Default log file size";
      *(_DWORD *)&v21.Level = 5;
      UserData.Ptr = (ULONGLONG)off_180128178;
      v33 = 0;
      v30 = 8;
      v28 = 28;
      *(_DWORD *)&v21.Id = 184549376;
      v21.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_180128178;
      v7 = (__int16 *)byte_180114BF9;
      v25 = 53;
      goto LABEL_27;
    }
  }
LABEL_28:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18001c7e0  mov     r11, rsp
0x18001c7e3  push    rbp
0x18001c7e4  push    rsi
0x18001c7e5  lea     rbp, [r11-208h]
0x18001c7ec  sub     rsp, 2F8h
0x18001c7f3  mov     rax, cs:__security_cookie
0x18001c7fa  xor     rax, rsp
0x18001c7fd  mov     [rbp+200h+var_20], rax
0x18001c804  mov     [r11+10h], rbx
0x18001c808  xor     edx, edx; Val
0x18001c80a  mov     [r11+18h], rdi
0x18001c80e  mov     rbx, rcx
0x18001c811  mov     [r11+20h], r14
0x18001c815  lea     rcx, [rbp+200h+var_230]; void *
0x18001c819  mov     [r11-18h], r15
0x18001c81d  mov     r8d, 208h; Size
0x18001c823  xor     r15d, r15d
0x18001c826  mov     [rsp+300h+hKey], r15
0x18001c82b  call    memset_0
0x18001c830  lea     rax, [rsp+300h+hKey]
0x18001c835  mov     [rsp+300h+cbData], r15d
0x18001c83a  mov     r9d, 20019h; samDesired
0x18001c840  mov     [rsp+300h+phkResult], rax; phkResult
0x18001c845  xor     r8d, r8d; ulOptions
0x18001c848  mov     [rsp+300h+Type], r15d
0x18001c84d  lea     rdx, aSystemCurrentc_8; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x18001c854  mov     [rsp+300h+Data], r15d
0x18001c859  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c860  call    cs:__imp_RegOpenKeyExW
0x18001c866  mov     esi, eax
0x18001c868  test    eax, eax
0x18001c86a  jz      loc_18001C935
0x18001c870  jle     short loc_18001C87B
0x18001c872  movzx   esi, ax
0x18001c875  or      esi, 80070000h
0x18001c87b  mov     eax, cs:dword_180128170
0x18001c881  cmp     eax, 2
0x18001c884  jbe     loc_18001CBCD
0x18001c88a  mov     dword ptr [rsp+300h+var_298.Id], esi
0x18001c88e  lea     rcx, [rbp+200h+var_230]
0x18001c892  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001c899  nop     dword ptr [rax+00000000h]
0x18001c8a0  cmp     [rcx+rax*2+2], r15w
0x18001c8a6  lea     rax, [rax+1]
0x18001c8aa  jnz     short loc_18001C8A0
0x18001c8ac  lea     eax, ds:2[rax*2]
0x18001c8b3  mov     [rbp+200h+var_234], r15d
0x18001c8b7  mov     [rbp+200h+var_238], eax
0x18001c8ba  lea     rcx, [rbp+200h+var_230]
0x18001c8be  lea     rax, [rsp+300h+var_298]
0x18001c8c3  mov     [rbp+200h+var_240], rcx
0x18001c8c7  mov     [rbp+200h+var_250], rax
0x18001c8cb  lea     rdi, _TraceLoggingMetadataEnd
0x18001c8d2  lea     rax, aRegopenkeyexFa_0; "RegOpenKeyEx failed"
0x18001c8d9  mov     [rbp+200h+var_248], 4
0x18001c8e1  mov     [rbp+200h+var_260], rax
0x18001c8e5  lea     r14, _TraceLoggingMetadata
0x18001c8ec  movzx   eax, cs:word_180114B28
0x18001c8f3  lea     rdx, [rsp+300h+EventDescriptor]
0x18001c8f8  mov     dword ptr [rsp+300h+EventDescriptor.Level], eax
0x18001c8fc  mov     rax, cs:off_180128178
0x18001c903  mov     [rbp+200h+UserData.Ptr], rax
0x18001c907  mov     [rbp+200h+var_258], 14h
0x18001c90f  mov     dword ptr [rsp+300h+EventDescriptor.Id], 0B000000h
0x18001c917  mov     [rsp+300h+EventDescriptor.Keyword], r15
0x18001c91c  movzx   eax, word ptr [rax]
0x18001c91f  mov     [rbp+200h+UserData.Size], eax
0x18001c922  lea     rax, word_180114B32
0x18001c929  mov     [rbp+200h+var_268], 1Ch
0x18001c930  jmp     loc_18001CB8C
0x18001c935  mov     esi, r15d
0x18001c938  mov     edi, r15d
0x18001c93b  cmp     [rbx+8], r15d
0x18001c93f  jbe     short loc_18001C95B
0x18001c941  mov     eax, edi
0x18001c943  lea     rcx, [rax+rax*4]
0x18001c947  mov     rax, [rbx+10h]
0x18001c94b  lea     rcx, [rax+rcx*8]; this
0x18001c94f  call    ?ReadTraceConfig@CWPPLoggerGuidConfig@@QEAAJXZ; CWPPLoggerGuidConfig::ReadTraceConfig(void)
0x18001c954  inc     edi
0x18001c956  cmp     edi, [rbx+8]
0x18001c959  jb      short loc_18001C941
0x18001c95b  mov     rcx, [rsp+300h+hKey]; hKey
0x18001c960  lea     rax, [rsp+300h+cbData]
0x18001c965  mov     [rsp+300h+lpcbData], rax; lpcbData
0x18001c96a  lea     r9, [rsp+300h+Type]; lpType
0x18001c96f  lea     rax, [rsp+300h+Data]
0x18001c974  mov     [rsp+300h+cbData], 4
0x18001c97c  xor     r8d, r8d; lpReserved
0x18001c97f  mov     [rsp+300h+phkResult], rax; lpData
0x18001c984  lea     rdx, aDebugmaxfilesi; "DebugMaxFileSize"
0x18001c98b  call    cs:__imp_RegQueryValueExW
0x18001c991  lea     rdi, _TraceLoggingMetadataEnd
0x18001c998  lea     r14, _TraceLoggingMetadata
0x18001c99f  test    eax, eax
0x18001c9a1  jnz     loc_18001CAC6
0x18001c9a7  cmp     [rsp+300h+Type], 4
0x18001c9ac  mov     eax, [rsp+300h+Data]
0x18001c9b0  jnz     short loc_18001CA1C
0x18001c9b2  test    eax, eax
0x18001c9b4  jz      short loc_18001CA24
0x18001c9b6  cmp     [rbx+34h], eax
0x18001c9b9  jz      loc_18001CBCD
0x18001c9bf  mov     [rbx+34h], eax
0x18001c9c2  mov     eax, cs:dword_180128170
0x18001c9c8  cmp     eax, 5
0x18001c9cb  jbe     loc_18001CBCD
0x18001c9d1  mov     rax, [rbx]
0x18001c9d4  lea     rdx, byte_180114C2F
0x18001c9db  mov     qword ptr [rsp+300h+var_2C0], rax
0x18001c9e0  mov     eax, [rbx+34h]
0x18001c9e3  mov     qword ptr [rsp+300h+var_298.Id], rax
0x18001c9e8  lea     rax, aSettingLogFile; "Setting log file size from registry ent"...
0x18001c9ef  mov     qword ptr [rsp+300h+EventDescriptor.Id], rax
0x18001c9f4  lea     rax, [rsp+300h+var_2C0]
0x18001c9f9  mov     [rsp+30h], rax
0x18001c9fe  lea     rax, [rsp+300h+var_298]
0x18001ca03  mov     [rsp+300h+lpcbData], rax
0x18001ca08  lea     rax, [rsp+300h+EventDescriptor]
0x18001ca0d  mov     [rsp+300h+phkResult], rax
0x18001ca12  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18001ca17  jmp     loc_18001CBCD
0x18001ca1c  test    eax, eax
0x18001ca1e  jnz     loc_18001CAC6
0x18001ca24  mov     eax, cs:dword_180128170
0x18001ca2a  cmp     eax, 5
0x18001ca2d  jbe     loc_18001CAC6
0x18001ca33  lea     rax, aIgnoringDebugm; "Ignoring DebugMaxFileSize, it has be gr"...
0x18001ca3a  mov     [rbp+200h+var_258], 43h ; 'C'
0x18001ca42  mov     [rbp+200h+var_260], rax
0x18001ca46  lea     rdx, [rsp+300h+EventDescriptor]; EventDescriptor
0x18001ca4b  movzx   eax, cs:word_180114C71
0x18001ca52  xor     r9d, r9d; RelatedActivityId
0x18001ca55  mov     dword ptr [rsp+300h+EventDescriptor.Level], eax
0x18001ca59  xor     r8d, r8d; ActivityId
0x18001ca5c  mov     rax, cs:off_180128178
0x18001ca63  mov     [rbp+200h+UserData.Ptr], rax
0x18001ca67  mov     dword ptr [rsp+300h+EventDescriptor.Id], 0B000000h
0x18001ca6f  mov     [rsp+300h+EventDescriptor.Keyword], r15
0x18001ca74  movzx   eax, word ptr [rax]
0x18001ca77  mov     [rbp+200h+UserData.Size], eax
0x18001ca7a  lea     rax, byte_180114C7B
0x18001ca81  mov     [rbp+200h+var_270], rax
0x18001ca85  mov     rax, rdi
0x18001ca88  sub     eax, r14d
0x18001ca8b  mov     dword ptr [rbp+200h+UserData.0Ch], 2
0x18001ca92  mov     [rbp+200h+var_268], 10h
0x18001ca99  mov     [rbp+200h+var_264], 1
0x18001caa0  mov     [rsp+300h+var_2C0], eax
0x18001caa4  mov     eax, [rsp+300h+var_2C0]
0x18001caa8  mov     rcx, cs:RegHandle; RegHandle
0x18001caaf  lea     rax, [rbp+200h+UserData]
0x18001cab3  mov     [rsp+300h+lpcbData], rax; UserData
0x18001cab8  mov     dword ptr [rsp+300h+phkResult], 3; UserDataCount
0x18001cac0  call    cs:__imp_EventWriteTransfer
0x18001cac6  cmp     dword ptr [rbx+34h], 800h
0x18001cacd  jz      loc_18001CBCD
0x18001cad3  mov     dword ptr [rbx+34h], 800h
0x18001cada  mov     eax, cs:dword_180128170
0x18001cae0  cmp     eax, 5
0x18001cae3  jbe     loc_18001CBCD
0x18001cae9  mov     rcx, [rbx]
0x18001caec  mov     eax, [rbx+34h]
0x18001caef  mov     qword ptr [rsp+300h+EventDescriptor.Id], rax
0x18001caf4  test    rcx, rcx
0x18001caf7  jz      short loc_18001CB15
0x18001caf9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001cb00  cmp     [rcx+rax*2+2], r15w
0x18001cb06  lea     rax, [rax+1]
0x18001cb0a  jnz     short loc_18001CB00
0x18001cb0c  lea     eax, ds:2[rax*2]
0x18001cb13  jmp     short loc_18001CB21
0x18001cb15  lea     rcx, qword_1800D7B88
0x18001cb1c  mov     eax, 2
0x18001cb21  mov     [rbp+200h+var_238], eax
0x18001cb24  lea     rdx, [rsp+300h+var_298]; EventDescriptor
0x18001cb29  lea     rax, [rsp+300h+EventDescriptor]
0x18001cb2e  mov     [rbp+200h+var_240], rcx
0x18001cb32  mov     [rbp+200h+var_250], rax
0x18001cb36  lea     rax, aUsingDefaultLo; "Using Default log file size"
0x18001cb3d  mov     [rbp+200h+var_260], rax
0x18001cb41  movzx   eax, cs:word_180114BEF
0x18001cb48  mov     dword ptr [rsp+300h+var_298.Level], eax
0x18001cb4c  mov     rax, cs:off_180128178
0x18001cb53  mov     [rbp+200h+UserData.Ptr], rax
0x18001cb57  mov     [rbp+200h+var_234], r15d
0x18001cb5b  mov     [rbp+200h+var_248], 8
0x18001cb63  mov     [rbp+200h+var_258], 1Ch
0x18001cb6b  mov     dword ptr [rsp+300h+var_298.Id], 0B000000h
0x18001cb73  mov     [rsp+300h+var_298.Keyword], r15
0x18001cb78  movzx   eax, word ptr [rax]
0x18001cb7b  mov     [rbp+200h+UserData.Size], eax
0x18001cb7e  lea     rax, byte_180114BF9
0x18001cb85  mov     [rbp+200h+var_268], 35h ; '5'
0x18001cb8c  mov     [rbp+200h+var_270], rax
0x18001cb90  sub     edi, r14d
0x18001cb93  mov     dword ptr [rbp+200h+UserData.0Ch], 2
0x18001cb9a  xor     r9d, r9d; RelatedActivityId
0x18001cb9d  mov     [rbp+200h+var_264], 1
0x18001cba4  xor     r8d, r8d; ActivityId
0x18001cba7  mov     [rsp+300h+var_2C0], edi
0x18001cbab  mov     eax, [rsp+300h+var_2C0]
0x18001cbaf  mov     rcx, cs:RegHandle; RegHandle
0x18001cbb6  lea     rax, [rbp+200h+UserData]
0x18001cbba  mov     [rsp+300h+lpcbData], rax; UserData
0x18001cbbf  mov     dword ptr [rsp+300h+phkResult], 5; UserDataCount
0x18001cbc7  call    cs:__imp_EventWriteTransfer
0x18001cbcd  mov     rcx, [rsp+300h+hKey]; hKey
0x18001cbd2  mov     r15, [rsp+2F0h]
0x18001cbda  mov     r14, [rsp+300h+arg_18]
0x18001cbe2  mov     rdi, [rsp+300h+arg_10]
0x18001cbea  mov     rbx, [rsp+300h+arg_8]
0x18001cbf2  test    rcx, rcx
0x18001cbf5  jz      short loc_18001CBFD
0x18001cbf7  call    cs:__imp_RegCloseKey
0x18001cbfd  mov     eax, esi
0x18001cbff  mov     rcx, [rbp+200h+var_20]
0x18001cc06  xor     rcx, rsp; StackCookie
0x18001cc09  call    __security_check_cookie
0x18001cc0e  add     rsp, 2F8h
0x18001cc15  pop     rsi
0x18001cc16  pop     rbp
0x18001cc17  retn
```
