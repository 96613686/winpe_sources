# TenantGatewayMap::DeleteSstpProxyRules(void)

- ea: `0x180010b84`
- end: `0x180010cb0`
- name: `?DeleteSstpProxyRules@TenantGatewayMap@@QEAAKXZ`
- size: `300`
- prototype: `unsigned int __fastcall(TenantGatewayMap *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180014840`

## callees

- `0x180007944`
- `0x180007d34`
- `0x18000827c`
- `0x180008360`
- `0x180010b84`
- `0x18001bcba`
- `0x18001bcf0`
- `0x18001d010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180010c88`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180010c88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c2a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180010c20`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180010c20`

## string_xrefs

- `0x180010c0a`: `TenantGatewayMap::DeleteSstpProxyRules: GetXmlFilePath failed with error %d`
- `0x180010c41`: `TenantGatewayMap::DeleteSstpProxyRules: FATAL ERROR. DeleteFile method failed with error %d`

## pseudocode

```c
__int64 __fastcall TenantGatewayMap::DeleteSstpProxyRules(TenantGatewayMap *this)
{
  DWORD XmlFilePath; // eax
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
    if ( (byte_18002D803 & 8) == 0 )
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
    if ( !LastError || (byte_18002D803 & 8) == 0 )
      goto LABEL_10;
    LOWORD(v6) = 0;
    FormatRRASErrorString(
      &v6,
      L"TenantGatewayMap::DeleteSstpProxyRules: FATAL ERROR. DeleteFile method failed with error %d",
      LastError);
  }
  if ( (byte_18002D803 & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v6);
LABEL_10:
  if ( lpFileName )
    operator delete[]((void *)lpFileName);
  return LastError;
}

```

## disassembly

```asm
0x180010b84  mov     [rsp-8+arg_8], rbx
0x180010b89  push    rbp
0x180010b8a  lea     rbp, [rsp-740h]
0x180010b92  sub     rsp, 840h
0x180010b99  mov     rax, cs:__security_cookie
0x180010ba0  xor     rax, rsp
0x180010ba3  mov     [rbp+740h+var_10], rax
0x180010baa  mov     rbx, rcx
0x180010bad  mov     [rsp+840h+lpFileName], 0
0x180010bb6  xor     eax, eax
0x180010bb8  lea     rcx, [rsp+840h+var_80C]; void *
0x180010bbd  xor     edx, edx; Val
0x180010bbf  mov     [rsp+840h+var_810], eax
0x180010bc3  mov     r8d, 7FCh; Size
0x180010bc9  call    memset_0
0x180010bce  lea     rcx, [rbx+8]
0x180010bd2  call    ?clear@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAAXXZ; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::clear(void)
0x180010bd7  mov     rcx, [rbx+60h]
0x180010bdb  mov     rax, [rcx]
0x180010bde  mov     rax, [rax+10h]
0x180010be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010be7  lea     rcx, [rsp+840h+lpFileName]; unsigned __int16 **
0x180010bec  mov     qword ptr [rbx+60h], 0
0x180010bf4  call    ?GetXmlFilePath@@YAKPEAPEAG@Z; GetXmlFilePath(ushort * *)
0x180010bf9  mov     ebx, eax
0x180010bfb  test    eax, eax
0x180010bfd  jz      short loc_180010C1B
0x180010bff  test    cs:byte_18002D803, 8
0x180010c06  jz      short loc_180010C7B
0x180010c08  xor     ecx, ecx
0x180010c0a  lea     rdx, aTenantgatewaym_0; "TenantGatewayMap::DeleteSstpProxyRules:"...
0x180010c11  mov     word ptr [rsp+840h+var_810], cx
0x180010c16  mov     r8d, eax
0x180010c19  jmp     short loc_180010C50
0x180010c1b  mov     rcx, [rsp+840h+lpFileName]; lpFileName
0x180010c20  call    cs:__imp_DeleteFileW
0x180010c26  test    eax, eax
0x180010c28  jnz     short loc_180010C7B
0x180010c2a  call    cs:__imp_GetLastError
0x180010c30  mov     ebx, eax
0x180010c32  test    eax, eax
0x180010c34  jz      short loc_180010C7B
0x180010c36  test    cs:byte_18002D803, 8
0x180010c3d  jz      short loc_180010C7B
0x180010c3f  xor     eax, eax
0x180010c41  lea     rdx, aTenantgatewaym_1; "TenantGatewayMap::DeleteSstpProxyRules:"...
0x180010c48  mov     word ptr [rsp+840h+var_810], ax
0x180010c4d  mov     r8d, ebx
0x180010c50  lea     rcx, [rsp+840h+var_810]
0x180010c55  call    FormatRRASErrorString
0x180010c5a  test    cs:byte_18002D803, 8
0x180010c61  jz      short loc_180010C7B
0x180010c63  lea     r8, [rsp+840h+var_810]
0x180010c68  lea     rdx, RasSSTPSvcTraceError
0x180010c6f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180010c76  call    McTemplateU0z_EventWriteTransfer
0x180010c7b  cmp     [rsp+840h+lpFileName], 0
0x180010c81  jz      short loc_180010C8E
0x180010c83  mov     rcx, [rsp+840h+lpFileName]
0x180010c88  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180010c8e  mov     eax, ebx
0x180010c90  mov     rcx, [rbp+740h+var_10]
0x180010c97  xor     rcx, rsp; StackCookie
0x180010c9a  call    __security_check_cookie
0x180010c9f  mov     rbx, [rsp+840h+arg_8]
0x180010ca7  add     rsp, 840h
0x180010cae  pop     rbp
0x180010caf  retn
```
