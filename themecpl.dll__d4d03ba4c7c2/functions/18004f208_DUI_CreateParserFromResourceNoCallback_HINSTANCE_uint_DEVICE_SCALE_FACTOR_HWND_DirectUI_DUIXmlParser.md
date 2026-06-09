# _DUI_CreateParserFromResourceNoCallback(HINSTANCE__ *,uint,DEVICE_SCALE_FACTOR,HWND__ *,DirectUI::DUIXmlParser * *)

- ea: `0x18004f208`
- end: `0x18004f2c4`
- name: `?_DUI_CreateParserFromResourceNoCallback@@YAJPEAUHINSTANCE__@@IW4DEVICE_SCALE_FACTOR@@PEAUHWND__@@PEAPEAVDUIXmlParser@DirectUI@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, enum DEVICE_SCALE_FACTOR, HWND, struct DirectUI::DUIXmlParser **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800214d8`

## callees

- `0x18004f208`

## import_xrefs

- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x18004f24b`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x18004f24b`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18004f2a5`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18004f2a5`
- `DUI70!?SetRootWindowForTheming@DUIXmlParser@DirectUI@@QEAAXPEAUHWND__@@@Z` at `0x18004f264`
- `DUI70!?SetRootWindowForTheming@DUIXmlParser@DirectUI@@QEAAXPEAUHWND__@@@Z` at `0x18004f264`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJPEBGPEAUHINSTANCE__@@1@Z` at `0x18004f284`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJPEBGPEAUHINSTANCE__@@1@Z` at `0x18004f284`

## pseudocode

```c
__int64 __fastcall _DUI_CreateParserFromResourceNoCallback(
        HINSTANCE a1,
        __int64 a2,
        enum DEVICE_SCALE_FACTOR a3,
        HWND a4,
        struct DirectUI::DUIXmlParser **a5)
{
  struct DirectUI::DUIXmlParser **v5; // rdi
  int v7; // ebx
  struct DirectUI::DUIXmlParser *v9; // [rsp+58h] [rbp+20h] BYREF

  v5 = a5;
  v9 = 0;
  *a5 = 0;
  v7 = DirectUI::DUIXmlParser::Create(
         &v9,
         0,
         0,
         (void (*)(const unsigned __int16 *, const unsigned __int16 *, int, void *))CGlassColorCplPage::PerformInitTasks,
         0);
  if ( v7 >= 0 )
  {
    DirectUI::DUIXmlParser::SetRootWindowForTheming(v9, 0);
    v7 = DirectUI::DUIXmlParser::SetXMLFromResource(v9, (const unsigned __int16 *)0x3E9, a1, &_ImageBase);
    if ( v7 < 0 )
      DirectUI::DUIXmlParser::Destroy(v9);
    else
      *v5 = v9;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004f208  mov     rax, rsp
0x18004f20b  mov     [rax+8], rbx
0x18004f20f  mov     [rax+10h], rsi
0x18004f213  mov     [rax+20h], r9
0x18004f217  push    rdi
0x18004f218  sub     rsp, 30h
0x18004f21c  mov     rdi, [rsp+38h+arg_20]
0x18004f221  lea     r9, ?PerformInitTasks@CGlassColorCplPage@@UEAAXXZ; CGlassColorCplPage::PerformInitTasks(void)
0x18004f228  mov     rsi, rcx
0x18004f22b  mov     qword ptr [rax+20h], 0
0x18004f233  xor     r8d, r8d
0x18004f236  mov     qword ptr [rax-18h], 0
0x18004f23e  xor     edx, edx
0x18004f240  lea     rcx, [rax+20h]
0x18004f244  mov     qword ptr [rdi], 0
0x18004f24b  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x18004f252  nop     dword ptr [rax+rax+00h]
0x18004f257  mov     ebx, eax
0x18004f259  test    eax, eax
0x18004f25b  js      short loc_18004F2B1
0x18004f25d  mov     rcx, [rsp+38h+arg_18]
0x18004f262  xor     edx, edx
0x18004f264  call    cs:__imp_?SetRootWindowForTheming@DUIXmlParser@DirectUI@@QEAAXPEAUHWND__@@@Z; DirectUI::DUIXmlParser::SetRootWindowForTheming(HWND__ *)
0x18004f26b  nop     dword ptr [rax+rax+00h]
0x18004f270  mov     rcx, [rsp+38h+arg_18]
0x18004f275  lea     r9, __ImageBase
0x18004f27c  mov     r8, rsi
0x18004f27f  mov     edx, 3E9h
0x18004f284  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJPEBGPEAUHINSTANCE__@@1@Z; DirectUI::DUIXmlParser::SetXMLFromResource(ushort const *,HINSTANCE__ *,HINSTANCE__ *)
0x18004f28b  nop     dword ptr [rax+rax+00h]
0x18004f290  mov     ebx, eax
0x18004f292  test    eax, eax
0x18004f294  js      short loc_18004F2A0
0x18004f296  mov     rax, [rsp+38h+arg_18]
0x18004f29b  mov     [rdi], rax
0x18004f29e  jmp     short loc_18004F2B1
0x18004f2a0  mov     rcx, [rsp+38h+arg_18]
0x18004f2a5  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x18004f2ac  nop     dword ptr [rax+rax+00h]
0x18004f2b1  mov     rsi, [rsp+38h+arg_8]
0x18004f2b6  mov     eax, ebx
0x18004f2b8  mov     rbx, [rsp+38h+arg_0]
0x18004f2bd  add     rsp, 30h
0x18004f2c1  pop     rdi
0x18004f2c2  retn
```
