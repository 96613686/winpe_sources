# TenantGatewayMap::DeleteSstpProxyRules(void)

- ea: `0x180011a14`
- end: `0x180011b53`
- name: `?DeleteSstpProxyRules@TenantGatewayMap@@QEAAKXZ`
- size: `319`
- prototype: `unsigned int __fastcall(TenantGatewayMap *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800158c0`

## callees

- `0x1800080dc`
- `0x180008514`
- `0x1800089dc`
- `0x180008b90`
- `0x180011a14`
- `0x18001d1da`
- `0x18001d210`
- `0x18001e010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180011b24`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180011b24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ac0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ac0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180011ab0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180011ab0`

## string_xrefs

- `0x180011a9a`: `TenantGatewayMap::DeleteSstpProxyRules: GetXmlFilePath failed with error %d`
- `0x180011add`: `TenantGatewayMap::DeleteSstpProxyRules: FATAL ERROR. DeleteFile method failed with error %d`

## pseudocode

```c
__int64 __fastcall TenantGatewayMap::DeleteSstpProxyRules(TenantGatewayMap *this)
{
  unsigned int XmlFilePath; // eax
  DWORD LastError; // ebx
  LPCWSTR lpFileName; // [rsp+20h] [rbp-E0h] BYREF
  int v6; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v7[2044]; // [rsp+34h] [rbp-CCh] BYREF

  lpFileName = 0;
  v6 = 0;
  memset_0(v7, 0, sizeof(v7));
  std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::clear((char *)this + 8);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 12) + 16LL))(*((_QWORD *)this + 12));
  *((_QWORD *)this + 12) = 0;
  XmlFilePath = GetXmlFilePath((unsigned __int16 **)&lpFileName);
  LastError = XmlFilePath;
  if ( XmlFilePath )
  {
    if ( (byte_18002E903 & 8) == 0 )
      goto LABEL_10;
    LOWORD(v6) = 0;
    FormatRRASErrorString(
      &v6,
      L"TenantGatewayMap::DeleteSstpProxyRules: GetXmlFilePath failed with error %d",
      XmlFilePath);
  }
  else
  {
    if ( DeleteFileW(lpFileName) )
      goto LABEL_10;
    LastError = GetLastError();
    if ( !LastError || (byte_18002E903 & 8) == 0 )
      goto LABEL_10;
    LOWORD(v6) = 0;
    FormatRRASErrorString(
      &v6,
      L"TenantGatewayMap::DeleteSstpProxyRules: FATAL ERROR. DeleteFile method failed with error %d",
      LastError);
  }
  if ( (byte_18002E903 & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v6);
LABEL_10:
  if ( lpFileName )
    operator delete[]((void *)lpFileName);
  return LastError;
}

```

## disassembly

```asm
0x180011a14  mov     [rsp-8+arg_8], rbx
0x180011a19  push    rbp
0x180011a1a  lea     rbp, [rsp-740h]
0x180011a22  sub     rsp, 840h
0x180011a29  mov     rax, cs:__security_cookie
0x180011a30  xor     rax, rsp
0x180011a33  mov     [rbp+740h+var_10], rax
0x180011a3a  mov     rbx, rcx
0x180011a3d  mov     [rsp+840h+lpFileName], 0
0x180011a46  xor     eax, eax
0x180011a48  lea     rcx, [rsp+840h+var_80C]; void *
0x180011a4d  xor     edx, edx; Val
0x180011a4f  mov     [rsp+840h+var_810], eax
0x180011a53  mov     r8d, 7FCh; Size
0x180011a59  call    memset_0
0x180011a5e  lea     rcx, [rbx+8]
0x180011a62  call    ?clear@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAAXXZ; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::clear(void)
0x180011a67  mov     rcx, [rbx+60h]
0x180011a6b  mov     rax, [rcx]
0x180011a6e  mov     rax, [rax+10h]
0x180011a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a77  lea     rcx, [rsp+840h+lpFileName]; unsigned __int16 **
0x180011a7c  mov     qword ptr [rbx+60h], 0
0x180011a84  call    ?GetXmlFilePath@@YAKPEAPEAG@Z; GetXmlFilePath(ushort * *)
0x180011a89  mov     ebx, eax
0x180011a8b  test    eax, eax
0x180011a8d  jz      short loc_180011AAB
0x180011a8f  test    cs:byte_18002E903, 8
0x180011a96  jz      short loc_180011B17
0x180011a98  xor     ecx, ecx
0x180011a9a  lea     rdx, aTenantgatewaym_0; "TenantGatewayMap::DeleteSstpProxyRules:"...
0x180011aa1  mov     word ptr [rsp+840h+var_810], cx
0x180011aa6  mov     r8d, eax
0x180011aa9  jmp     short loc_180011AEC
0x180011aab  mov     rcx, [rsp+840h+lpFileName]; lpFileName
0x180011ab0  call    cs:__imp_DeleteFileW
0x180011ab7  nop     dword ptr [rax+rax+00h]
0x180011abc  test    eax, eax
0x180011abe  jnz     short loc_180011B17
0x180011ac0  call    cs:__imp_GetLastError
0x180011ac7  nop     dword ptr [rax+rax+00h]
0x180011acc  mov     ebx, eax
0x180011ace  test    eax, eax
0x180011ad0  jz      short loc_180011B17
0x180011ad2  test    cs:byte_18002E903, 8
0x180011ad9  jz      short loc_180011B17
0x180011adb  xor     eax, eax
0x180011add  lea     rdx, aTenantgatewaym_1; "TenantGatewayMap::DeleteSstpProxyRules:"...
0x180011ae4  mov     word ptr [rsp+840h+var_810], ax
0x180011ae9  mov     r8d, ebx
0x180011aec  lea     rcx, [rsp+840h+var_810]
0x180011af1  call    FormatRRASErrorString
0x180011af6  test    cs:byte_18002E903, 8
0x180011afd  jz      short loc_180011B17
0x180011aff  lea     r8, [rsp+840h+var_810]
0x180011b04  lea     rdx, RasSSTPSvcTraceError
0x180011b0b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180011b12  call    McTemplateU0z_EventWriteTransfer
0x180011b17  cmp     [rsp+840h+lpFileName], 0
0x180011b1d  jz      short loc_180011B30
0x180011b1f  mov     rcx, [rsp+840h+lpFileName]
0x180011b24  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180011b2b  nop     dword ptr [rax+rax+00h]
0x180011b30  mov     eax, ebx
0x180011b32  mov     rcx, [rbp+740h+var_10]
0x180011b39  xor     rcx, rsp; StackCookie
0x180011b3c  call    __security_check_cookie
0x180011b41  mov     rbx, [rsp+840h+arg_8]
0x180011b49  add     rsp, 840h
0x180011b50  pop     rbp
0x180011b51  retn
```
