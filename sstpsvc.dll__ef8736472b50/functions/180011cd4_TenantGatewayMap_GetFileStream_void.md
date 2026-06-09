# TenantGatewayMap::GetFileStream(void)

- ea: `0x180011cd4`
- end: `0x180011de0`
- name: `?GetFileStream@TenantGatewayMap@@QEAAPEAUIStream@@XZ`
- size: `268`
- prototype: `struct IStream *__fastcall(TenantGatewayMap *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180014484`
- `0x180014900`
- `0x180015500`

## callees

- `0x1800080dc`
- `0x1800089dc`
- `0x180008b90`
- `0x180011cd4`
- `0x180011de8`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180011d7e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180011d7e`

## string_xrefs

- `0x180011d3d`: `TenantGatewayMap::GetFileStream: GetXmlFilePath failed with error %d`
- `0x180011dd4`: `TenantGatewayMap::GetFileStream: FATAL ERROR. Failed to open the xml file with error %d`

## pseudocode

```c
struct IStream *__fastcall TenantGatewayMap::GetFileStream(TenantGatewayMap *this)
{
  unsigned int XmlFilePath; // eax
  WCHAR *v3; // rbx
  __int64 v4; // r8
  const wchar_t *v5; // rdx
  unsigned int v7; // eax
  LPCWSTR lpFileName; // [rsp+20h] [rbp-828h] BYREF
  int v9; // [rsp+30h] [rbp-818h] BYREF
  _BYTE v10[2044]; // [rsp+34h] [rbp-814h] BYREF

  lpFileName = 0;
  v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  if ( *((_QWORD *)this + 12) )
    return (struct IStream *)*((_QWORD *)this + 12);
  XmlFilePath = GetXmlFilePath((unsigned __int16 **)&lpFileName);
  v3 = (WCHAR *)lpFileName;
  v4 = XmlFilePath;
  if ( XmlFilePath )
  {
    if ( (byte_18002E903 & 8) != 0 )
    {
      v5 = L"TenantGatewayMap::GetFileStream: GetXmlFilePath failed with error %d";
      goto LABEL_5;
    }
  }
  else
  {
    v7 = FileStream::OpenFile(lpFileName, (struct IStream **)this + 12);
    v4 = v7;
    if ( v7 )
    {
      *((_QWORD *)this + 12) = 0;
      if ( (byte_18002E903 & 8) != 0 )
      {
        v5 = L"TenantGatewayMap::GetFileStream: FATAL ERROR. Failed to open the xml file with error %d";
LABEL_5:
        LOWORD(v9) = 0;
        FormatRRASErrorString(&v9, v5, v4);
        if ( (byte_18002E903 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v9);
      }
    }
  }
  if ( v3 )
    operator delete[](v3);
  return (struct IStream *)*((_QWORD *)this + 12);
}

```

## disassembly

```asm
0x180011cd4  mov     [rsp+arg_8], rbx
0x180011cd9  push    rdi
0x180011cda  sub     rsp, 840h
0x180011ce1  mov     rax, cs:__security_cookie
0x180011ce8  xor     rax, rsp
0x180011ceb  mov     [rsp+848h+var_18], rax
0x180011cf3  mov     rdi, rcx
0x180011cf6  mov     [rsp+848h+lpFileName], 0
0x180011cff  xor     eax, eax
0x180011d01  lea     rcx, [rsp+848h+var_814]; void *
0x180011d06  xor     edx, edx; Val
0x180011d08  mov     [rsp+848h+var_818], eax
0x180011d0c  mov     r8d, 7FCh; Size
0x180011d12  call    memset_0
0x180011d17  cmp     qword ptr [rdi+60h], 0
0x180011d1c  jnz     short loc_180011D8A
0x180011d1e  lea     rcx, [rsp+848h+lpFileName]; unsigned __int16 **
0x180011d23  call    ?GetXmlFilePath@@YAKPEAPEAG@Z; GetXmlFilePath(ushort * *)
0x180011d28  mov     rbx, [rsp+848h+lpFileName]
0x180011d2d  mov     r8d, eax
0x180011d30  test    eax, eax
0x180011d32  jz      short loc_180011DB0
0x180011d34  test    cs:byte_18002E903, 8
0x180011d3b  jz      short loc_180011D76
0x180011d3d  lea     rdx, aTenantgatewaym_2; "TenantGatewayMap::GetFileStream: GetXml"...
0x180011d44  xor     eax, eax
0x180011d46  lea     rcx, [rsp+848h+var_818]
0x180011d4b  mov     word ptr [rsp+848h+var_818], ax
0x180011d50  call    FormatRRASErrorString
0x180011d55  test    cs:byte_18002E903, 8
0x180011d5c  jz      short loc_180011D76
0x180011d5e  lea     r8, [rsp+848h+var_818]
0x180011d63  lea     rdx, RasSSTPSvcTraceError
0x180011d6a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180011d71  call    McTemplateU0z_EventWriteTransfer
0x180011d76  test    rbx, rbx
0x180011d79  jz      short loc_180011D8A
0x180011d7b  mov     rcx, rbx
0x180011d7e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180011d85  nop     dword ptr [rax+rax+00h]
0x180011d8a  mov     rax, [rdi+60h]
0x180011d8e  mov     rcx, [rsp+848h+var_18]
0x180011d96  xor     rcx, rsp; StackCookie
0x180011d99  call    __security_check_cookie
0x180011d9e  mov     rbx, [rsp+848h+arg_8]
0x180011da6  add     rsp, 840h
0x180011dad  pop     rdi
0x180011dae  retn
0x180011db0  lea     rdx, [rdi+60h]; struct IStream **
0x180011db4  mov     rcx, rbx; lpFileName
0x180011db7  call    ?OpenFile@FileStream@@SAJPEBGPEAPEAUIStream@@@Z; FileStream::OpenFile(ushort const *,IStream * *)
0x180011dbc  mov     r8d, eax
0x180011dbf  test    eax, eax
0x180011dc1  jz      short loc_180011D76
0x180011dc3  mov     qword ptr [rdi+60h], 0
0x180011dcb  test    cs:byte_18002E903, 8
0x180011dd2  jz      short loc_180011D76
0x180011dd4  lea     rdx, aTenantgatewaym_4; "TenantGatewayMap::GetFileStream: FATAL "...
0x180011ddb  jmp     loc_180011D44
```
