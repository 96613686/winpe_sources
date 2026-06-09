# CIASMigrationHelper::FindUnsupportedPropertiesInXML(ushort const *,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,ushort * *)

- ea: `0x18004cdf4`
- end: `0x18004ceed`
- name: `?FindUnsupportedPropertiesInXML@CIASMigrationHelper@@SAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@1PEAPEAG@Z`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180047a60`

## callees

- `0x18002cd00`
- `0x180042a80`
- `0x18004cdf4`
- `0x18004f2cc`
- `0x180053188`
- `0x1800540cc`
- `0x180054130`

## string_xrefs

- `0x18004ce62`: `SearchForUnsupportedPropertiesInXML() failed: %!hresult!`

## pseudocode

```c
__int64 __fastcall CIASMigrationHelper::FindUnsupportedPropertiesInXML(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 **a4)
{
  const unsigned __int16 *v7; // rcx
  int v8; // ebx
  int v9; // edx

  std::list<CPolicyErrorInfo>::clear(qword_180079038);
  std::list<CPolicyErrorInfo>::clear(qword_180079058);
  std::list<_bstr_t>::clear(&qword_180076580);
  v8 = CIASMigrationHelper::SearchForUnsupportedPropertiesInXML(a2, a3);
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
    {
      return (unsigned int)v8;
    }
    WppDbgPrint("SearchForUnsupportedPropertiesInXML() failed: %!hresult!");
    v9 = 14;
LABEL_6:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      (unsigned int)WPP_35f0385197fd35cdb48f774109abba17_Traceguids,
      (unsigned int)"NPSDS",
      v8);
    return (unsigned int)v8;
  }
  v8 = CIasMigErrorHelper::BuildUnsupportedPropertiesDesc(v7, a4);
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
    {
      return (unsigned int)v8;
    }
    WppDbgPrint("BuildUnsupportedPropertiesDesc() failed: %!hresult!");
    v9 = 15;
    goto LABEL_6;
  }
  return 0;
}

```

## disassembly

```asm
0x18004cdf4  mov     [rsp+arg_0], rbx
0x18004cdf9  mov     [rsp+arg_8], rsi
0x18004cdfe  push    rdi
0x18004cdff  sub     rsp, 30h
0x18004ce03  lea     rcx, qword_180079038
0x18004ce0a  mov     rsi, r9
0x18004ce0d  mov     rbx, r8
0x18004ce10  mov     rdi, rdx
0x18004ce13  call    ?clear@?$list@VCPolicyErrorInfo@@V?$allocator@VCPolicyErrorInfo@@@std@@@std@@QEAAXXZ; std::list<CPolicyErrorInfo>::clear(void)
0x18004ce18  lea     rcx, qword_180079058
0x18004ce1f  call    ?clear@?$list@VCPolicyErrorInfo@@V?$allocator@VCPolicyErrorInfo@@@std@@@std@@QEAAXXZ; std::list<CPolicyErrorInfo>::clear(void)
0x18004ce24  lea     rcx, qword_180076580
0x18004ce2b  call    ?clear@?$list@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@QEAAXXZ; std::list<_bstr_t>::clear(void)
0x18004ce30  mov     rdx, rbx
0x18004ce33  mov     rcx, rdi
0x18004ce36  call    ?SearchForUnsupportedPropertiesInXML@CIASMigrationHelper@@KAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@0@Z; CIASMigrationHelper::SearchForUnsupportedPropertiesInXML(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)
0x18004ce3b  mov     ebx, eax
0x18004ce3d  test    eax, eax
0x18004ce3f  jns     short loc_18004CE99
0x18004ce41  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ce48  lea     rdx, WPP_GLOBAL_Control
0x18004ce4f  cmp     rcx, rdx
0x18004ce52  jz      short loc_18004CE95
0x18004ce54  cmp     byte ptr [rcx+19h], 2
0x18004ce58  jb      short loc_18004CE95
0x18004ce5a  test    byte ptr [rcx+1Ch], 10h
0x18004ce5e  jz      short loc_18004CE95
0x18004ce60  mov     edx, eax
0x18004ce62  lea     rcx, aSearchforunsup; "SearchForUnsupportedPropertiesInXML() f"...
0x18004ce69  call    WppDbgPrint
0x18004ce6e  mov     edx, 0Eh
0x18004ce73  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ce7a  lea     r9, aNpsds; "NPSDS"
0x18004ce81  lea     r8, WPP_35f0385197fd35cdb48f774109abba17_Traceguids
0x18004ce88  mov     [rsp+38h+var_18], ebx
0x18004ce8c  mov     rcx, [rcx+10h]
0x18004ce90  call    WPP_SF_sd
0x18004ce95  mov     eax, ebx
0x18004ce97  jmp     short loc_18004CEDD
0x18004ce99  mov     rdx, rsi; unsigned __int16 **
0x18004ce9c  call    ?BuildUnsupportedPropertiesDesc@CIasMigErrorHelper@@SAJPEBGPEAPEAG@Z; CIasMigErrorHelper::BuildUnsupportedPropertiesDesc(ushort const *,ushort * *)
0x18004cea1  mov     ebx, eax
0x18004cea3  test    eax, eax
0x18004cea5  jns     short loc_18004CEDB
0x18004cea7  mov     rax, cs:WPP_GLOBAL_Control
0x18004ceae  lea     rdx, WPP_GLOBAL_Control
0x18004ceb5  cmp     rax, rdx
0x18004ceb8  jz      short loc_18004CE95
0x18004ceba  cmp     byte ptr [rax+19h], 2
0x18004cebe  jb      short loc_18004CE95
0x18004cec0  test    byte ptr [rax+1Ch], 10h
0x18004cec4  jz      short loc_18004CE95
0x18004cec6  mov     edx, ebx
0x18004cec8  lea     rcx, aBuildunsupport; "BuildUnsupportedPropertiesDesc() failed"...
0x18004cecf  call    WppDbgPrint
0x18004ced4  mov     edx, 0Fh
0x18004ced9  jmp     short loc_18004CE73
0x18004cedb  xor     eax, eax
0x18004cedd  mov     rbx, [rsp+38h+arg_0]
0x18004cee2  mov     rsi, [rsp+38h+arg_8]
0x18004cee7  add     rsp, 30h
0x18004ceeb  pop     rdi
0x18004ceec  retn
```
