# DUI_CreateParserWithCallbackFromResource(HINSTANCE__ *,uint,DEVICE_SCALE_FACTOR,HWND__ *,DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *)

- ea: `0x180032ea4`
- end: `0x180032f89`
- name: `?DUI_CreateParserWithCallbackFromResource@@YAJPEAUHINSTANCE__@@IW4DEVICE_SCALE_FACTOR@@PEAUHWND__@@PEAPEAVDUIXmlParser@DirectUI@@P6APEAVValue@5@PEBGPEAX@Z5@Z`
- size: `229`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, enum DEVICE_SCALE_FACTOR, HWND, struct DirectUI::DUIXmlParser **, struct DirectUI::Value *(*)(const unsigned __int16 *, void *), void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180040968`

## callees

- `0x180032ea4`
- `0x1800474ac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180032f4c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180032f4c`
- `DUI70!?SetXMLFromResourceWithTheme@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@00@Z` at `0x180032f36`
- `DUI70!?SetXMLFromResourceWithTheme@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@00@Z` at `0x180032f36`
- `DUI70!?SetRootWindowForTheming@DUIXmlParser@DirectUI@@QEAAXPEAUHWND__@@@Z` at `0x180032f12`
- `DUI70!?SetRootWindowForTheming@DUIXmlParser@DirectUI@@QEAAXPEAUHWND__@@@Z` at `0x180032f12`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x180032efa`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x180032efa`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180032f64`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180032f64`

## pseudocode

```c
__int64 __fastcall DUI_CreateParserWithCallbackFromResource(
        unsigned __int16 **a1,
        unsigned int a2,
        enum DEVICE_SCALE_FACTOR a3,
        HWND a4,
        struct DirectUI::DUIXmlParser **a5)
{
  HINSTANCE ShellStyleHInstance; // rax
  HMODULE v9; // rsi
  HINSTANCE v10; // rbp
  int v11; // edi

  *a5 = 0;
  ShellStyleHInstance = GetShellStyleHInstance(a1);
  v9 = (HMODULE)a1;
  if ( ShellStyleHInstance )
    v9 = ShellStyleHInstance;
  v10 = ShellStyleHInstance;
  v11 = DirectUI::DUIXmlParser::Create(
          a5,
          (struct DirectUI::Value *(*)(const unsigned __int16 *, void *))DUI_ShellStyleSheet_GetSheetCB,
          0,
          (void (*)(const unsigned __int16 *, const unsigned __int16 *, int, void *))CSafeElementPtrBase<UIBridgeWindow>::OnListenedPropertyChanged,
          0);
  if ( v11 >= 0 )
  {
    DirectUI::DUIXmlParser::SetRootWindowForTheming(*a5, a4);
    v11 = DirectUI::DUIXmlParser::SetXMLFromResourceWithTheme(*a5, a2, (HINSTANCE)a1, v9, &_ImageBase);
  }
  if ( v10 )
    FreeLibrary(v9);
  if ( v11 < 0 && *a5 )
  {
    DirectUI::DUIXmlParser::Destroy(*a5);
    *a5 = 0;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180032ea4  push    rbx
0x180032ea6  push    rbp
0x180032ea7  push    rsi
0x180032ea8  push    rdi
0x180032ea9  push    r12
0x180032eab  push    r14
0x180032ead  push    r15
0x180032eaf  sub     rsp, 30h
0x180032eb3  mov     rbx, [rsp+68h+arg_20]
0x180032ebb  mov     r15, r9
0x180032ebe  mov     r12d, edx
0x180032ec1  mov     r14, rcx
0x180032ec4  mov     qword ptr [rbx], 0
0x180032ecb  call    ?GetShellStyleHInstance@@YAPEAUHINSTANCE__@@PEAPEAG@Z; GetShellStyleHInstance(ushort * *)
0x180032ed0  test    rax, rax
0x180032ed3  mov     [rsp+68h+var_48], 0
0x180032edc  mov     rsi, r14
0x180032edf  lea     r9, ?OnListenedPropertyChanged@?$CSafeElementPtrBase@VUIBridgeWindow@@@@MEAAXPEAVElement@DirectUI@@PEBUPropertyInfo@3@HPEAVValue@3@2@Z; CSafeElementPtrBase<UIBridgeWindow>::OnListenedPropertyChanged(DirectUI::Element *,DirectUI::PropertyInfo const *,int,DirectUI::Value *,DirectUI::Value *)
0x180032ee6  cmovnz  rsi, rax
0x180032eea  lea     rdx, ?DUI_ShellStyleSheet_GetSheetCB@@YAPEAVValue@DirectUI@@PEBGPEAX@Z; DUI_ShellStyleSheet_GetSheetCB(ushort const *,void *)
0x180032ef1  xor     r8d, r8d
0x180032ef4  mov     rcx, rbx
0x180032ef7  mov     rbp, rax
0x180032efa  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x180032f01  nop     dword ptr [rax+rax+00h]
0x180032f06  mov     edi, eax
0x180032f08  test    eax, eax
0x180032f0a  js      short loc_180032F44
0x180032f0c  mov     rcx, [rbx]
0x180032f0f  mov     rdx, r15
0x180032f12  call    cs:__imp_?SetRootWindowForTheming@DUIXmlParser@DirectUI@@QEAAXPEAUHWND__@@@Z; DirectUI::DUIXmlParser::SetRootWindowForTheming(HWND__ *)
0x180032f19  nop     dword ptr [rax+rax+00h]
0x180032f1e  mov     rcx, [rbx]
0x180032f21  lea     rax, __ImageBase
0x180032f28  mov     r9, rsi
0x180032f2b  mov     [rsp+68h+var_48], rax
0x180032f30  mov     r8, r14
0x180032f33  mov     edx, r12d
0x180032f36  call    cs:__imp_?SetXMLFromResourceWithTheme@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@00@Z; DirectUI::DUIXmlParser::SetXMLFromResourceWithTheme(uint,HINSTANCE__ *,HINSTANCE__ *,HINSTANCE__ *)
0x180032f3d  nop     dword ptr [rax+rax+00h]
0x180032f42  mov     edi, eax
0x180032f44  test    rbp, rbp
0x180032f47  jz      short loc_180032F58
0x180032f49  mov     rcx, rsi; hLibModule
0x180032f4c  call    cs:__imp_FreeLibrary
0x180032f53  nop     dword ptr [rax+rax+00h]
0x180032f58  test    edi, edi
0x180032f5a  jns     short loc_180032F77
0x180032f5c  mov     rcx, [rbx]
0x180032f5f  test    rcx, rcx
0x180032f62  jz      short loc_180032F77
0x180032f64  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x180032f6b  nop     dword ptr [rax+rax+00h]
0x180032f70  mov     qword ptr [rbx], 0
0x180032f77  mov     eax, edi
0x180032f79  add     rsp, 30h
0x180032f7d  pop     r15
0x180032f7f  pop     r14
0x180032f81  pop     r12
0x180032f83  pop     rdi
0x180032f84  pop     rsi
0x180032f85  pop     rbp
0x180032f86  pop     rbx
0x180032f87  retn
```
