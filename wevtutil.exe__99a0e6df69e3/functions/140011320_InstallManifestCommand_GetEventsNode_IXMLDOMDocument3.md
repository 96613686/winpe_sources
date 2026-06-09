# InstallManifestCommand::GetEventsNode(IXMLDOMDocument3 *)

- ea: `0x140011320`
- end: `0x140011449`
- name: `?GetEventsNode@InstallManifestCommand@@AEAA?AU?$com_ptr@UIXMLDOMElement@@@winrt@@PEAUIXMLDOMDocument3@@@Z`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140001ce0`

## callees

- `0x140010450`
- `0x140011320`
- `0x14001145c`
- `0x140022cec`
- `0x140031810`

## string_xrefs

- `0x140011354`: `/ns:instrumentationManifest/ns:instrumentation/ns:events`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall InstallManifestCommand::GetEventsNode(__int64 a1, _QWORD *a2, __int64 a3)
{
  const wchar_t *Src; // rax
  const char *v8; // [rsp+20h] [rbp-68h]
  const wchar_t *v9; // [rsp+40h] [rbp-48h] BYREF
  __int64 v10; // [rsp+48h] [rbp-40h]
  _BYTE pExceptionObject[48]; // [rsp+50h] [rbp-38h] BYREF

  *a2 = 0;
  v9 = L"/ns:instrumentationManifest/ns:instrumentation/ns:events";
  v10 = 56;
  if ( (unsigned int)XmlTryGetElement(a3, &v9, a2) )
  {
    v9 = L"/*[local-name() = 'assembly']/*[local-name() = 'instrumentation']/ns:events";
    v10 = 75;
    if ( (unsigned int)XmlTryGetElement(a3, &v9, a2) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids, 1168);
      }
      Src = (const wchar_t *)(a1 + 40);
      if ( *(_QWORD *)(a1 + 64) > 7u )
        Src = *(const wchar_t **)Src;
      EvtException::EvtException((EvtException *)pExceptionObject, 0x490u, 0, 0, v8, 61, 0x22u, Src);
      throw (EvtException *)pExceptionObject;
    }
  }
  return a2;
}

```

## disassembly

```asm
0x140011320  mov     r11, rsp
0x140011323  mov     [r11+8], rbx
0x140011327  mov     [r11+18h], rsi
0x14001132b  mov     [r11+10h], rdx
0x14001132f  push    rdi
0x140011330  sub     rsp, 80h
0x140011337  mov     rdi, r8
0x14001133a  mov     rbx, rdx
0x14001133d  mov     rsi, rcx
0x140011340  mov     eax, 1
0x140011345  mov     [r11+20h], eax
0x140011349  mov     qword ptr [rdx], 0
0x140011350  mov     [r11+20h], eax
0x140011354  lea     rax, aNsInstrumentat; "/ns:instrumentationManifest/ns:instrume"...
0x14001135b  mov     [r11-48h], rax
0x14001135f  mov     qword ptr [r11-40h], 38h ; '8'
0x140011367  mov     r8, rdx
0x14001136a  lea     rdx, [r11-48h]
0x14001136e  mov     rcx, rdi
0x140011371  call    ?XmlTryGetElement@@YAJPEAUIXMLDOMNode@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAU?$com_ptr@UIXMLDOMElement@@@winrt@@@Z; XmlTryGetElement(IXMLDOMNode *,std::wstring_view,winrt::com_ptr<IXMLDOMElement> &)
0x140011376  test    eax, eax
0x140011378  jz      loc_140011431
0x14001137e  lea     rax, aLocalNameAssem; "/*[local-name() = 'assembly']/*[local-n"...
0x140011385  mov     [rsp+88h+var_48], rax
0x14001138a  mov     [rsp+88h+var_40], 4Bh ; 'K'
0x140011393  mov     r8, rbx
0x140011396  lea     rdx, [rsp+88h+var_48]
0x14001139b  mov     rcx, rdi
0x14001139e  call    ?XmlTryGetElement@@YAJPEAUIXMLDOMNode@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAU?$com_ptr@UIXMLDOMElement@@@winrt@@@Z; XmlTryGetElement(IXMLDOMNode *,std::wstring_view,winrt::com_ptr<IXMLDOMElement> &)
0x1400113a3  test    eax, eax
0x1400113a5  jz      loc_140011431
0x1400113ab  lea     rax, WPP_GLOBAL_Control
0x1400113b2  mov     ebx, 490h
0x1400113b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400113be  cmp     rcx, rax
0x1400113c1  jz      short loc_1400113EA
0x1400113c3  test    dword ptr [rcx+1Ch], 400000h
0x1400113ca  jz      short loc_1400113EA
0x1400113cc  cmp     byte ptr [rcx+19h], 2
0x1400113d0  jb      short loc_1400113EA
0x1400113d2  mov     edx, 0Ah
0x1400113d7  mov     r9d, ebx
0x1400113da  lea     r8, WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids
0x1400113e1  mov     rcx, [rcx+10h]
0x1400113e5  call    WPP_SF_d
0x1400113ea  lea     rax, [rsi+28h]
0x1400113ee  cmp     qword ptr [rax+18h], 7
0x1400113f3  jbe     short loc_1400113F8
0x1400113f5  mov     rax, [rax]
0x1400113f8  mov     [rsp+88h+Src], rax; Src
0x1400113fd  mov     [rsp+88h+var_58], 22h ; '"'; unsigned int
0x140011405  mov     [rsp+88h+var_60], 3Dh ; '='; int
0x14001140d  xor     r9d, r9d; unsigned int
0x140011410  xor     r8d, r8d; unsigned int
0x140011413  mov     edx, ebx; unsigned int
0x140011415  lea     rcx, [rsp+88h+pExceptionObject]; this
0x14001141a  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001141f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140011426  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x14001142b  call    _CxxThrowException_0
0x140011431  mov     rax, rbx
0x140011434  lea     r11, [rsp+88h+var_8]
0x14001143c  mov     rbx, [r11+10h]
0x140011440  mov     rsi, [r11+20h]
0x140011444  mov     rsp, r11
0x140011447  pop     rdi
0x140011448  retn
```
