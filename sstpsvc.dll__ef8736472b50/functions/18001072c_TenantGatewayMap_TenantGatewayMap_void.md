# TenantGatewayMap::TenantGatewayMap(void)

- ea: `0x18001072c`
- end: `0x18001086e`
- name: `??0TenantGatewayMap@@AEAA@XZ`
- size: `322`
- prototype: `TenantGatewayMap *__fastcall(PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180008404`

## callees

- `0x1800080dc`
- `0x1800089dc`
- `0x180008b90`
- `0x18001058c`
- `0x18001072c`
- `0x180011de8`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800107f9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800107f9`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180010831`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180010831`

## string_xrefs

- `0x1800107b3`: `TenantGatewayMap::TenantGatewayMap: GetXmlFilePath failed with error %d`
- `0x180010861`: `TenantGatewayMap::TenantGatewayMap: FATAL ERROR. Failed to open the xml file with error %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
WCHAR *__fastcall TenantGatewayMap::TenantGatewayMap(WCHAR *SRWLock)
{
  unsigned int XmlFilePath; // eax
  __int64 v3; // r8
  const wchar_t *v4; // rdx
  unsigned int v6; // eax
  LPCWSTR lpFileName[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v8; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v9[2044]; // [rsp+34h] [rbp-CCh] BYREF

  lpFileName[1] = SRWLock;
  std::tr1::unordered_map<std::wstring,std::vector<std::wstring>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::unordered_map<std::wstring,std::vector<std::wstring>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>(SRWLock + 4);
  lpFileName[0] = 0;
  *((_QWORD *)SRWLock + 12) = 0;
  v8 = 0;
  memset_0(v9, 0, sizeof(v9));
  XmlFilePath = GetXmlFilePath((unsigned __int16 **)lpFileName);
  v3 = XmlFilePath;
  if ( XmlFilePath )
  {
    if ( (byte_18002E903 & 8) == 0 )
      goto LABEL_6;
    v4 = L"TenantGatewayMap::TenantGatewayMap: GetXmlFilePath failed with error %d";
  }
  else
  {
    InitializeSRWLock((PSRWLOCK)SRWLock);
    v6 = FileStream::OpenFile(lpFileName[0], (struct IStream **)SRWLock + 12);
    v3 = v6;
    if ( !v6 )
      goto LABEL_6;
    *((_QWORD *)SRWLock + 12) = 0;
    if ( (byte_18002E903 & 8) == 0 )
      goto LABEL_6;
    v4 = L"TenantGatewayMap::TenantGatewayMap: FATAL ERROR. Failed to open the xml file with error %d";
  }
  LOWORD(v8) = 0;
  FormatRRASErrorString(&v8, v4, v3);
  if ( (byte_18002E903 & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v8);
LABEL_6:
  if ( lpFileName[0] )
    operator delete[]((void *)lpFileName[0]);
  return SRWLock;
}

```

## disassembly

```asm
0x18001072c  mov     [rsp-8+arg_8], rbx
0x180010731  mov     [rsp-8+arg_10], rsi
0x180010736  push    rbp
0x180010737  lea     rbp, [rsp-740h]
0x18001073f  sub     rsp, 840h
0x180010746  mov     rax, cs:__security_cookie
0x18001074d  xor     rax, rsp
0x180010750  mov     [rbp+740h+var_10], rax
0x180010757  mov     rbx, rcx
0x18001075a  mov     [rsp+840h+var_818], rcx
0x18001075f  add     rcx, 8
0x180010763  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@tr1@std@@QEAA@XZ; std::tr1::unordered_map<std::wstring,std::vector<std::wstring>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::unordered_map<std::wstring,std::vector<std::wstring>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>(void)
0x180010768  nop
0x180010769  mov     [rsp+840h+lpFileName], 0
0x180010772  lea     rsi, [rbx+60h]
0x180010776  mov     qword ptr [rsi], 0
0x18001077d  xor     eax, eax
0x18001077f  mov     [rsp+840h+var_810], eax
0x180010783  xor     edx, edx; Val
0x180010785  mov     r8d, 7FCh; Size
0x18001078b  lea     rcx, [rsp+840h+var_80C]; void *
0x180010790  call    memset_0
0x180010795  lea     rcx, [rsp+840h+lpFileName]; unsigned __int16 **
0x18001079a  call    ?GetXmlFilePath@@YAKPEAPEAG@Z; GetXmlFilePath(ushort * *)
0x18001079f  mov     r8d, eax
0x1800107a2  test    eax, eax
0x1800107a4  jz      loc_18001082E
0x1800107aa  test    cs:byte_18002E903, 8
0x1800107b1  jz      short loc_1800107EC
0x1800107b3  lea     rdx, aTenantgatewaym_5; "TenantGatewayMap::TenantGatewayMap: Get"...
0x1800107ba  xor     eax, eax
0x1800107bc  mov     word ptr [rsp+840h+var_810], ax
0x1800107c1  lea     rcx, [rsp+840h+var_810]
0x1800107c6  call    FormatRRASErrorString
0x1800107cb  test    cs:byte_18002E903, 8
0x1800107d2  jz      short loc_1800107EC
0x1800107d4  lea     r8, [rsp+840h+var_810]
0x1800107d9  lea     rdx, RasSSTPSvcTraceError
0x1800107e0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800107e7  call    McTemplateU0z_EventWriteTransfer
0x1800107ec  cmp     [rsp+840h+lpFileName], 0
0x1800107f2  jz      short loc_180010806
0x1800107f4  mov     rcx, [rsp+840h+lpFileName]
0x1800107f9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180010800  nop     dword ptr [rax+rax+00h]
0x180010805  nop
0x180010806  mov     rax, rbx
0x180010809  mov     rcx, [rbp+740h+var_10]
0x180010810  xor     rcx, rsp; StackCookie
0x180010813  call    __security_check_cookie
0x180010818  lea     r11, [rsp+840h+var_s0]
0x180010820  mov     rbx, [r11+18h]
0x180010824  mov     rsi, [r11+20h]
0x180010828  mov     rsp, r11
0x18001082b  pop     rbp
0x18001082c  retn
0x18001082e  mov     rcx, rbx; SRWLock
0x180010831  call    cs:__imp_InitializeSRWLock
0x180010838  nop     dword ptr [rax+rax+00h]
0x18001083d  mov     rdx, rsi; struct IStream **
0x180010840  mov     rcx, [rsp+840h+lpFileName]; lpFileName
0x180010845  call    ?OpenFile@FileStream@@SAJPEBGPEAPEAUIStream@@@Z; FileStream::OpenFile(ushort const *,IStream * *)
0x18001084a  mov     r8d, eax
0x18001084d  test    eax, eax
0x18001084f  jz      short loc_1800107EC
0x180010851  mov     qword ptr [rsi], 0
0x180010858  test    cs:byte_18002E903, 8
0x18001085f  jz      short loc_1800107EC
0x180010861  lea     rdx, aTenantgatewaym_3; "TenantGatewayMap::TenantGatewayMap: FAT"...
0x180010868  jmp     loc_1800107BA
```
