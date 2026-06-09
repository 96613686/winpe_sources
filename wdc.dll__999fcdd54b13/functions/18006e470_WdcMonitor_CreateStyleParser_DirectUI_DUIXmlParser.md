# WdcMonitor::CreateStyleParser(DirectUI::DUIXmlParser * *)

- ea: `0x18006e470`
- end: `0x18006e517`
- name: `?CreateStyleParser@WdcMonitor@@UEAAJPEAPEAVDUIXmlParser@DirectUI@@@Z`
- size: `167`
- prototype: `__int64 __fastcall(WdcMonitor *__hidden this, struct DirectUI::DUIXmlParser **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000b854`
- `0x18006e470`

## import_xrefs

- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x18006e49f`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x18006e49f`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18006e4c3`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18006e4c3`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18006e4fa`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18006e4fa`

## string_xrefs

- `0x18006e4dd`: `WdcMonitor::CreateStyleParser`

## pseudocode

```c
__int64 __fastcall WdcMonitor::CreateStyleParser(WdcMonitor *this, struct DirectUI::DUIXmlParser **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v6; // [rsp+20h] [rbp-18h]
  struct DirectUI::DUIXmlParser *v7; // [rsp+50h] [rbp+18h] BYREF

  v7 = 0;
  v3 = DirectUI::DUIXmlParser::Create(
         &v7,
         0,
         0,
         (void (*)(const unsigned __int16 *, const unsigned __int16 *, int, void *))WdcPE,
         0);
  v4 = v3;
  if ( v3 >= 0
    && (v3 = DirectUI::DUIXmlParser::SetXMLFromResource(v7, 0x7530u, g_hInstance, (HINSTANCE)&_ImageBase),
        v4 = v3,
        v3 >= 0) )
  {
    *a2 = v7;
  }
  else
  {
    LODWORD(v6) = v3;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\monitor.cpp",
      "WdcMonitor::CreateStyleParser",
      0,
      L"FAILURE: 0x%08x",
      v6);
    if ( v7 )
      DirectUI::DUIXmlParser::Destroy(v7);
  }
  return v4;
}

```

## disassembly

```asm
0x18006e470  mov     rax, rsp
0x18006e473  mov     [rax+8], rbx
0x18006e477  push    rdi
0x18006e478  sub     rsp, 30h
0x18006e47c  mov     rdi, rdx
0x18006e47f  mov     qword ptr [rax+18h], 0
0x18006e487  xor     edx, edx
0x18006e489  mov     qword ptr [rax-18h], 0
0x18006e491  lea     r9, ?WdcPE@@YAXPEBG0HPEAX@Z; WdcPE(ushort const *,ushort const *,int,void *)
0x18006e498  xor     r8d, r8d
0x18006e49b  lea     rcx, [rax+18h]
0x18006e49f  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x18006e4a5  mov     ebx, eax
0x18006e4a7  test    eax, eax
0x18006e4a9  js      short loc_18006E4CF
0x18006e4ab  mov     r8, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x18006e4b2  lea     r9, __ImageBase
0x18006e4b9  mov     rcx, [rsp+38h+arg_10]
0x18006e4be  mov     edx, 7530h
0x18006e4c3  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x18006e4c9  mov     ebx, eax
0x18006e4cb  test    eax, eax
0x18006e4cd  jns     short loc_18006E502
0x18006e4cf  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18006e4d6  mov     dword ptr [rsp+38h+var_18], eax
0x18006e4da  xor     r8d, r8d; int
0x18006e4dd  lea     rdx, aWdcmonitorCrea_0; "WdcMonitor::CreateStyleParser"
0x18006e4e4  lea     rcx, aBaseDiagnosisP_4; "base\\diagnosis\\pdui\\perfmon\\mon\\mo"...
0x18006e4eb  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18006e4f0  mov     rcx, [rsp+38h+arg_10]
0x18006e4f5  test    rcx, rcx
0x18006e4f8  jz      short loc_18006E50A
0x18006e4fa  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x18006e500  jmp     short loc_18006E50A
0x18006e502  mov     rax, [rsp+38h+arg_10]
0x18006e507  mov     [rdi], rax
0x18006e50a  mov     eax, ebx
0x18006e50c  mov     rbx, [rsp+38h+arg_0]
0x18006e511  add     rsp, 30h
0x18006e515  pop     rdi
0x18006e516  retn
```
