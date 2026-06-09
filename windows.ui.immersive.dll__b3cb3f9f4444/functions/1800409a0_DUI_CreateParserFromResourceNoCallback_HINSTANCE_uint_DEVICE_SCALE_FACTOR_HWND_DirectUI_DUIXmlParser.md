# _DUI_CreateParserFromResourceNoCallback(HINSTANCE__ *,uint,DEVICE_SCALE_FACTOR,HWND__ *,DirectUI::DUIXmlParser * *)

- ea: `0x1800409a0`
- end: `0x180040a63`
- name: `?_DUI_CreateParserFromResourceNoCallback@@YAJPEAUHINSTANCE__@@IW4DEVICE_SCALE_FACTOR@@PEAUHWND__@@PEAPEAVDUIXmlParser@DirectUI@@@Z`
- size: `195`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, enum DEVICE_SCALE_FACTOR, HWND, struct DirectUI::DUIXmlParser **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180040968`

## callees

- `0x1800409a0`

## import_xrefs

- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJPEBGPEAUHINSTANCE__@@1@Z` at `0x180040a22`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJPEBGPEAUHINSTANCE__@@1@Z` at `0x180040a22`
- `DUI70!?SetRootWindowForTheming@DUIXmlParser@DirectUI@@QEAAXPEAUHWND__@@@Z` at `0x180040a01`
- `DUI70!?SetRootWindowForTheming@DUIXmlParser@DirectUI@@QEAAXPEAUHWND__@@@Z` at `0x180040a01`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x1800409e4`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x1800409e4`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180040a49`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180040a49`

## pseudocode

```c
__int64 __fastcall _DUI_CreateParserFromResourceNoCallback(
        HINSTANCE a1,
        unsigned __int16 a2,
        enum DEVICE_SCALE_FACTOR a3,
        HWND a4,
        struct DirectUI::DUIXmlParser **a5)
{
  struct DirectUI::DUIXmlParser **v5; // rdi
  int v9; // ebx

  v5 = a5;
  a5 = 0;
  *v5 = 0;
  v9 = DirectUI::DUIXmlParser::Create(
         (struct DirectUI::DUIXmlParser **)&a5,
         0,
         0,
         (void (*)(const unsigned __int16 *, const unsigned __int16 *, int, void *))CSafeElementPtrBase<UIBridgeWindow>::OnListenedPropertyChanged,
         0);
  if ( v9 >= 0 )
  {
    DirectUI::DUIXmlParser::SetRootWindowForTheming((DirectUI::DUIXmlParser *)a5, a4);
    v9 = DirectUI::DUIXmlParser::SetXMLFromResource(
           (DirectUI::DUIXmlParser *)a5,
           (const unsigned __int16 *)a2,
           a1,
           &_ImageBase);
    if ( v9 < 0 )
      DirectUI::DUIXmlParser::Destroy((DirectUI::DUIXmlParser *)a5);
    else
      *v5 = (struct DirectUI::DUIXmlParser *)a5;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800409a0  mov     rax, rsp
0x1800409a3  push    rbx
0x1800409a4  push    rbp
0x1800409a5  push    rsi
0x1800409a6  push    rdi
0x1800409a7  push    r14
0x1800409a9  sub     rsp, 30h
0x1800409ad  mov     rdi, [rsp+58h+arg_20]
0x1800409b5  mov     rsi, r9
0x1800409b8  mov     ebp, edx
0x1800409ba  lea     r9, ?OnListenedPropertyChanged@?$CSafeElementPtrBase@VUIBridgeWindow@@@@MEAAXPEAVElement@DirectUI@@PEBUPropertyInfo@3@HPEAVValue@3@2@Z; CSafeElementPtrBase<UIBridgeWindow>::OnListenedPropertyChanged(DirectUI::Element *,DirectUI::PropertyInfo const *,int,DirectUI::Value *,DirectUI::Value *)
0x1800409c1  mov     r14, rcx
0x1800409c4  mov     qword ptr [rax+28h], 0
0x1800409cc  xor     r8d, r8d
0x1800409cf  mov     qword ptr [rax-38h], 0
0x1800409d7  xor     edx, edx
0x1800409d9  mov     qword ptr [rdi], 0
0x1800409e0  lea     rcx, [rax+28h]
0x1800409e4  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x1800409eb  nop     dword ptr [rax+rax+00h]
0x1800409f0  mov     ebx, eax
0x1800409f2  test    eax, eax
0x1800409f4  js      short loc_180040A55
0x1800409f6  mov     rcx, [rsp+58h+arg_20]
0x1800409fe  mov     rdx, rsi
0x180040a01  call    cs:__imp_?SetRootWindowForTheming@DUIXmlParser@DirectUI@@QEAAXPEAUHWND__@@@Z; DirectUI::DUIXmlParser::SetRootWindowForTheming(HWND__ *)
0x180040a08  nop     dword ptr [rax+rax+00h]
0x180040a0d  mov     rcx, [rsp+58h+arg_20]
0x180040a15  lea     r9, __ImageBase
0x180040a1c  movzx   edx, bp
0x180040a1f  mov     r8, r14
0x180040a22  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJPEBGPEAUHINSTANCE__@@1@Z; DirectUI::DUIXmlParser::SetXMLFromResource(ushort const *,HINSTANCE__ *,HINSTANCE__ *)
0x180040a29  nop     dword ptr [rax+rax+00h]
0x180040a2e  mov     ebx, eax
0x180040a30  test    eax, eax
0x180040a32  js      short loc_180040A41
0x180040a34  mov     rax, [rsp+58h+arg_20]
0x180040a3c  mov     [rdi], rax
0x180040a3f  jmp     short loc_180040A55
0x180040a41  mov     rcx, [rsp+58h+arg_20]
0x180040a49  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x180040a50  nop     dword ptr [rax+rax+00h]
0x180040a55  mov     eax, ebx
0x180040a57  add     rsp, 30h
0x180040a5b  pop     r14
0x180040a5d  pop     rdi
0x180040a5e  pop     rsi
0x180040a5f  pop     rbp
0x180040a60  pop     rbx
0x180040a61  retn
```
