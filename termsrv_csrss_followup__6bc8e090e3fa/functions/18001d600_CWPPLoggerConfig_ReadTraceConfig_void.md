# CWPPLoggerConfig::ReadTraceConfig(void)

- ea: `0x18001d600`
- end: `0x18001da55`
- name: `?ReadTraceConfig@CWPPLoggerConfig@@QEAAJXZ`
- size: `1109`
- prototype: `__int64 __fastcall(CWPPLoggerConfig *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800be0e0`
- `0x1800be384`

## callees

- `0x180006214`
- `0x18001d600`
- `0x18002b82c`
- `0x180033f60`
- `0x180034e64`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d7ab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d7ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001da2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001da2d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d680`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d680`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d8e6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d9f7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d8e6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d9f7`

## string_xrefs

- `0x18001d6f2`: `RegOpenKeyEx failed`
- `0x18001d80e`: `Setting log file size from registry entry DebugMaxFileSize`

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
    if ( (unsigned int)dword_18012E170 > 2 )
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
      UserData.Ptr = (ULONGLONG)off_18012E178;
      v28 = 20;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_18012E178;
      v7 = word_18011ABB2;
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
          if ( (unsigned int)dword_18012E170 > 5 )
          {
            v16 = *(_QWORD *)this;
            *(_QWORD *)&v21.Id = *((unsigned int *)this + 13);
            *(_QWORD *)&EventDescriptor.Id = "Setting log file size from registry entry DebugMaxFileSize";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
              v9,
              (unsigned int)&byte_18011ACAF,
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
    if ( (unsigned int)dword_18012E170 > 5 )
    {
      v28 = 67;
      v27 = "Ignoring DebugMaxFileSize, it has be greater than 0, using default";
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_18012E178;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_18012E178;
      v24 = byte_18011ACFB;
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
    if ( (unsigned int)dword_18012E170 > 5 )
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
        v12 = &qword_1800DDBD8;
        v14 = 2;
      }
      v32 = v14;
      p_EventDescriptor = &v21;
      v31 = v12;
      v29 = &EventDescriptor;
      v27 = "Using Default log file size";
      *(_DWORD *)&v21.Level = 5;
      UserData.Ptr = (ULONGLONG)off_18012E178;
      v33 = 0;
      v30 = 8;
      v28 = 28;
      *(_DWORD *)&v21.Id = 184549376;
      v21.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_18012E178;
      v7 = (__int16 *)byte_18011AC79;
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
0x18001d600  mov     r11, rsp
0x18001d603  push    rbp
0x18001d604  push    rsi
0x18001d605  lea     rbp, [r11-208h]
0x18001d60c  sub     rsp, 2F8h
0x18001d613  mov     rax, cs:__security_cookie
0x18001d61a  xor     rax, rsp
0x18001d61d  mov     [rbp+200h+var_20], rax
0x18001d624  mov     [r11+10h], rbx
0x18001d628  xor     edx, edx; Val
0x18001d62a  mov     [r11+18h], rdi
0x18001d62e  mov     rbx, rcx
0x18001d631  mov     [r11+20h], r14
0x18001d635  lea     rcx, [rbp+200h+var_230]; void *
0x18001d639  mov     [r11-18h], r15
0x18001d63d  mov     r8d, 208h; Size
0x18001d643  xor     r15d, r15d
0x18001d646  mov     [rsp+300h+hKey], r15
0x18001d64b  call    memset_0
0x18001d650  lea     rax, [rsp+300h+hKey]
0x18001d655  mov     [rsp+300h+cbData], r15d
0x18001d65a  mov     r9d, 20019h; samDesired
0x18001d660  mov     [rsp+300h+phkResult], rax; phkResult
0x18001d665  xor     r8d, r8d; ulOptions
0x18001d668  mov     [rsp+300h+Type], r15d
0x18001d66d  lea     rdx, aSystemCurrentc_8; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x18001d674  mov     [rsp+300h+Data], r15d
0x18001d679  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d680  call    cs:__imp_RegOpenKeyExW
0x18001d687  nop     dword ptr [rax+rax+00h]
0x18001d68c  mov     esi, eax
0x18001d68e  test    eax, eax
0x18001d690  jz      loc_18001D755
0x18001d696  jle     short loc_18001D6A1
0x18001d698  movzx   esi, ax
0x18001d69b  or      esi, 80070000h
0x18001d6a1  mov     eax, cs:dword_18012E170
0x18001d6a7  cmp     eax, 2
0x18001d6aa  jbe     loc_18001DA03
0x18001d6b0  mov     dword ptr [rsp+300h+var_298.Id], esi
0x18001d6b4  lea     rcx, [rbp+200h+var_230]
0x18001d6b8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001d6bf  nop
0x18001d6c0  cmp     [rcx+rax*2+2], r15w
0x18001d6c6  lea     rax, [rax+1]
0x18001d6ca  jnz     short loc_18001D6C0
0x18001d6cc  lea     eax, ds:2[rax*2]
0x18001d6d3  mov     [rbp+200h+var_234], r15d
0x18001d6d7  mov     [rbp+200h+var_238], eax
0x18001d6da  lea     rcx, [rbp+200h+var_230]
0x18001d6de  lea     rax, [rsp+300h+var_298]
0x18001d6e3  mov     [rbp+200h+var_240], rcx
0x18001d6e7  mov     [rbp+200h+var_250], rax
0x18001d6eb  lea     rdi, _TraceLoggingMetadataEnd
0x18001d6f2  lea     rax, aRegopenkeyexFa_0; "RegOpenKeyEx failed"
0x18001d6f9  mov     [rbp+200h+var_248], 4
0x18001d701  mov     [rbp+200h+var_260], rax
0x18001d705  lea     r14, _TraceLoggingMetadata
0x18001d70c  movzx   eax, cs:word_18011ABA8
0x18001d713  lea     rdx, [rsp+300h+EventDescriptor]
0x18001d718  mov     dword ptr [rsp+300h+EventDescriptor.Level], eax
0x18001d71c  mov     rax, cs:off_18012E178
0x18001d723  mov     [rbp+200h+UserData.Ptr], rax
0x18001d727  mov     [rbp+200h+var_258], 14h
0x18001d72f  mov     dword ptr [rsp+300h+EventDescriptor.Id], 0B000000h
0x18001d737  mov     [rsp+300h+EventDescriptor.Keyword], r15
0x18001d73c  movzx   eax, word ptr [rax]
0x18001d73f  mov     [rbp+200h+UserData.Size], eax
0x18001d742  lea     rax, word_18011ABB2
0x18001d749  mov     [rbp+200h+var_268], 1Ch
0x18001d750  jmp     loc_18001D9BC
0x18001d755  mov     esi, r15d
0x18001d758  mov     edi, r15d
0x18001d75b  cmp     [rbx+8], r15d
0x18001d75f  jbe     short loc_18001D77B
0x18001d761  mov     eax, edi
0x18001d763  lea     rcx, [rax+rax*4]
0x18001d767  mov     rax, [rbx+10h]
0x18001d76b  lea     rcx, [rax+rcx*8]; this
0x18001d76f  call    ?ReadTraceConfig@CWPPLoggerGuidConfig@@QEAAJXZ; CWPPLoggerGuidConfig::ReadTraceConfig(void)
0x18001d774  inc     edi
0x18001d776  cmp     edi, [rbx+8]
0x18001d779  jb      short loc_18001D761
0x18001d77b  mov     rcx, [rsp+300h+hKey]; hKey
0x18001d780  lea     rax, [rsp+300h+cbData]
0x18001d785  mov     [rsp+300h+lpcbData], rax; lpcbData
0x18001d78a  lea     r9, [rsp+300h+Type]; lpType
0x18001d78f  lea     rax, [rsp+300h+Data]
0x18001d794  mov     [rsp+300h+cbData], 4
0x18001d79c  xor     r8d, r8d; lpReserved
0x18001d79f  mov     [rsp+300h+phkResult], rax; lpData
0x18001d7a4  lea     rdx, aDebugmaxfilesi; "DebugMaxFileSize"
0x18001d7ab  call    cs:__imp_RegQueryValueExW
0x18001d7b2  nop     dword ptr [rax+rax+00h]
0x18001d7b7  lea     rdi, _TraceLoggingMetadataEnd
0x18001d7be  lea     r14, _TraceLoggingMetadata
0x18001d7c5  test    eax, eax
0x18001d7c7  jnz     loc_18001D8F2
0x18001d7cd  cmp     [rsp+300h+Type], 4
0x18001d7d2  mov     eax, [rsp+300h+Data]
0x18001d7d6  jnz     short loc_18001D842
0x18001d7d8  test    eax, eax
0x18001d7da  jz      short loc_18001D84A
0x18001d7dc  cmp     [rbx+34h], eax
0x18001d7df  jz      loc_18001DA03
0x18001d7e5  mov     [rbx+34h], eax
0x18001d7e8  mov     eax, cs:dword_18012E170
0x18001d7ee  cmp     eax, 5
0x18001d7f1  jbe     loc_18001DA03
0x18001d7f7  mov     rax, [rbx]
0x18001d7fa  lea     rdx, byte_18011ACAF
0x18001d801  mov     qword ptr [rsp+300h+var_2C0], rax
0x18001d806  mov     eax, [rbx+34h]
0x18001d809  mov     qword ptr [rsp+300h+var_298.Id], rax
0x18001d80e  lea     rax, aSettingLogFile; "Setting log file size from registry ent"...
0x18001d815  mov     qword ptr [rsp+300h+EventDescriptor.Id], rax
0x18001d81a  lea     rax, [rsp+300h+var_2C0]
0x18001d81f  mov     [rsp+30h], rax
0x18001d824  lea     rax, [rsp+300h+var_298]
0x18001d829  mov     [rsp+300h+lpcbData], rax
0x18001d82e  lea     rax, [rsp+300h+EventDescriptor]
0x18001d833  mov     [rsp+300h+phkResult], rax
0x18001d838  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18001d83d  jmp     loc_18001DA03
0x18001d842  test    eax, eax
0x18001d844  jnz     loc_18001D8F2
0x18001d84a  mov     eax, cs:dword_18012E170
0x18001d850  cmp     eax, 5
0x18001d853  jbe     loc_18001D8F2
0x18001d859  lea     rax, aIgnoringDebugm; "Ignoring DebugMaxFileSize, it has be gr"...
0x18001d860  mov     [rbp+200h+var_258], 43h ; 'C'
0x18001d868  mov     [rbp+200h+var_260], rax
0x18001d86c  lea     rdx, [rsp+300h+EventDescriptor]; EventDescriptor
0x18001d871  movzx   eax, cs:word_18011ACF1
0x18001d878  xor     r9d, r9d; RelatedActivityId
0x18001d87b  mov     dword ptr [rsp+300h+EventDescriptor.Level], eax
0x18001d87f  xor     r8d, r8d; ActivityId
0x18001d882  mov     rax, cs:off_18012E178
0x18001d889  mov     [rbp+200h+UserData.Ptr], rax
0x18001d88d  mov     dword ptr [rsp+300h+EventDescriptor.Id], 0B000000h
0x18001d895  mov     [rsp+300h+EventDescriptor.Keyword], r15
0x18001d89a  movzx   eax, word ptr [rax]
0x18001d89d  mov     [rbp+200h+UserData.Size], eax
0x18001d8a0  lea     rax, byte_18011ACFB
0x18001d8a7  mov     [rbp+200h+var_270], rax
0x18001d8ab  mov     rax, rdi
0x18001d8ae  sub     eax, r14d
0x18001d8b1  mov     dword ptr [rbp+200h+UserData.0Ch], 2
0x18001d8b8  mov     [rbp+200h+var_268], 10h
0x18001d8bf  mov     [rbp+200h+var_264], 1
0x18001d8c6  mov     [rsp+300h+var_2C0], eax
0x18001d8ca  mov     eax, [rsp+300h+var_2C0]
0x18001d8ce  mov     rcx, cs:RegHandle; RegHandle
0x18001d8d5  lea     rax, [rbp+200h+UserData]
0x18001d8d9  mov     [rsp+300h+lpcbData], rax; UserData
0x18001d8de  mov     dword ptr [rsp+300h+phkResult], 3; UserDataCount
0x18001d8e6  call    cs:__imp_EventWriteTransfer
0x18001d8ed  nop     dword ptr [rax+rax+00h]
0x18001d8f2  cmp     dword ptr [rbx+34h], 800h
0x18001d8f9  jz      loc_18001DA03
0x18001d8ff  mov     dword ptr [rbx+34h], 800h
0x18001d906  mov     eax, cs:dword_18012E170
0x18001d90c  cmp     eax, 5
0x18001d90f  jbe     loc_18001DA03
0x18001d915  mov     rcx, [rbx]
0x18001d918  mov     eax, [rbx+34h]
0x18001d91b  mov     qword ptr [rsp+300h+EventDescriptor.Id], rax
0x18001d920  test    rcx, rcx
0x18001d923  jz      short loc_18001D945
0x18001d925  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001d92c  nop     dword ptr [rax+00h]
0x18001d930  cmp     [rcx+rax*2+2], r15w
0x18001d936  lea     rax, [rax+1]
0x18001d93a  jnz     short loc_18001D930
0x18001d93c  lea     eax, ds:2[rax*2]
0x18001d943  jmp     short loc_18001D951
0x18001d945  lea     rcx, qword_1800DDBD8
0x18001d94c  mov     eax, 2
0x18001d951  mov     [rbp+200h+var_238], eax
0x18001d954  lea     rdx, [rsp+300h+var_298]; EventDescriptor
0x18001d959  lea     rax, [rsp+300h+EventDescriptor]
0x18001d95e  mov     [rbp+200h+var_240], rcx
0x18001d962  mov     [rbp+200h+var_250], rax
0x18001d966  lea     rax, aUsingDefaultLo; "Using Default log file size"
0x18001d96d  mov     [rbp+200h+var_260], rax
0x18001d971  movzx   eax, cs:word_18011AC6F
0x18001d978  mov     dword ptr [rsp+300h+var_298.Level], eax
0x18001d97c  mov     rax, cs:off_18012E178
0x18001d983  mov     [rbp+200h+UserData.Ptr], rax
0x18001d987  mov     [rbp+200h+var_234], r15d
0x18001d98b  mov     [rbp+200h+var_248], 8
0x18001d993  mov     [rbp+200h+var_258], 1Ch
0x18001d99b  mov     dword ptr [rsp+300h+var_298.Id], 0B000000h
0x18001d9a3  mov     [rsp+300h+var_298.Keyword], r15
0x18001d9a8  movzx   eax, word ptr [rax]
0x18001d9ab  mov     [rbp+200h+UserData.Size], eax
0x18001d9ae  lea     rax, byte_18011AC79
0x18001d9b5  mov     [rbp+200h+var_268], 35h ; '5'
0x18001d9bc  mov     [rbp+200h+var_270], rax
0x18001d9c0  sub     edi, r14d
0x18001d9c3  mov     dword ptr [rbp+200h+UserData.0Ch], 2
0x18001d9ca  xor     r9d, r9d; RelatedActivityId
0x18001d9cd  mov     [rbp+200h+var_264], 1
0x18001d9d4  xor     r8d, r8d; ActivityId
0x18001d9d7  mov     [rsp+300h+var_2C0], edi
0x18001d9db  mov     eax, [rsp+300h+var_2C0]
0x18001d9df  mov     rcx, cs:RegHandle; RegHandle
0x18001d9e6  lea     rax, [rbp+200h+UserData]
0x18001d9ea  mov     [rsp+300h+lpcbData], rax; UserData
0x18001d9ef  mov     dword ptr [rsp+300h+phkResult], 5; UserDataCount
0x18001d9f7  call    cs:__imp_EventWriteTransfer
0x18001d9fe  nop     dword ptr [rax+rax+00h]
0x18001da03  mov     rcx, [rsp+300h+hKey]; hKey
0x18001da08  mov     r15, [rsp+2F0h]
0x18001da10  mov     r14, [rsp+300h+arg_18]
0x18001da18  mov     rdi, [rsp+300h+arg_10]
0x18001da20  mov     rbx, [rsp+300h+arg_8]
0x18001da28  test    rcx, rcx
0x18001da2b  jz      short loc_18001DA39
0x18001da2d  call    cs:__imp_RegCloseKey
0x18001da34  nop     dword ptr [rax+rax+00h]
0x18001da39  mov     eax, esi
0x18001da3b  mov     rcx, [rbp+200h+var_20]
0x18001da42  xor     rcx, rsp; StackCookie
0x18001da45  call    __security_check_cookie
0x18001da4a  add     rsp, 2F8h
0x18001da51  pop     rsi
0x18001da52  pop     rbp
0x18001da53  retn
```
