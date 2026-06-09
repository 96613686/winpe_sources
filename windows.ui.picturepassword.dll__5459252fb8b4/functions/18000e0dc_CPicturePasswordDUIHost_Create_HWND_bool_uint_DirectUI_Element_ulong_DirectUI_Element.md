# CPicturePasswordDUIHost::Create(HWND__ *,bool,uint,DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x18000e0dc`
- end: `0x18000e1fe`
- name: `?Create@CPicturePasswordDUIHost@@SAJPEAUHWND__@@_NIPEAVElement@DirectUI@@PEAKPEAPEAV34@@Z`
- size: `290`
- prototype: `__int64 __fastcall(HWND, unsigned __int64, __int64, struct DirectUI::Element *, unsigned int *, struct DirectUI::Element **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010fd0`

## callees

- `0x18000cd18`
- `0x18000e0dc`
- `0x18000e9cc`
- `0x18000eafc`
- `0x180014938`

## import_xrefs

- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x18000e157`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x18000e157`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18000e175`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18000e175`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18000e1ad`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18000e1ad`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000e1e5`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000e1e5`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x18000e1da`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RemovePropW` at `0x18000e1da`

## string_xrefs

- `0x18000e1d3`: `ImmersiveComponentOwnedWindow`

## pseudocode

```c
__int64 __fastcall CPicturePasswordDUIHost::Create(
        HWND a1,
        unsigned __int64 a2,
        __int64 a3,
        struct DirectUI::Element *a4,
        unsigned int *a5,
        struct DirectUI::Element **a6)
{
  struct DirectUI::Element **v6; // r14
  CPicturePasswordDUIHost *v8; // rax
  CPicturePasswordDUIHost *v9; // rdi
  bool v10; // r8
  unsigned int v11; // r9d
  int v12; // ebx
  bool v13; // r8
  DirectUI::DUIXmlParser **v14; // rsi
  DirectUI::DUIXmlParser *v15; // rcx
  struct DirectUI::Element *v17; // [rsp+20h] [rbp-38h]
  struct DirectUI::Element *v18; // [rsp+78h] [rbp+20h] BYREF

  v18 = a4;
  v6 = a6;
  *a6 = 0;
  v8 = (CPicturePasswordDUIHost *)DirectUI::HAllocAndZero((DirectUI *)0x430, a2);
  v9 = v8;
  if ( v8 )
  {
    CPicturePasswordDUIHost::CPicturePasswordDUIHost(v8);
    v12 = CPicturePasswordDUIHost::Initialize(v9, a1, v10, v11, v17, a5);
    if ( v12 < 0
      || (v14 = (DirectUI::DUIXmlParser **)((char *)v9 + 712),
          v12 = DirectUI::DUIXmlParser::Create((struct DirectUI::DUIXmlParser **)v9 + 89, 0, 0, 0, 0),
          v12 < 0)
      || (v12 = DirectUI::DUIXmlParser::SetXMLFromResource(*v14, 0x445Eu, &_ImageBase, &_ImageBase), v12 < 0)
      || (v15 = *v14, v18 = 0, v12 = DirectUI::DUIXmlParser::CreateElement(v15, L"main", v9, 0, 0, &v18), v12 < 0) )
    {
      CPicturePasswordGestureHelper::Unregister((CPicturePasswordDUIHost *)((char *)v9 + 472), 1, v13);
      RemovePropW(*((HWND *)v9 + 109), L"ImmersiveComponentOwnedWindow");
      DirectUI::Element::Destroy(v9, 1);
    }
    else
    {
      *v6 = v9;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000e0dc  mov     [rsp+arg_18], r9
0x18000e0e1  push    rbx
0x18000e0e2  push    rsi
0x18000e0e3  push    rdi
0x18000e0e4  push    r14
0x18000e0e6  sub     rsp, 38h
0x18000e0ea  mov     r14, [rsp+58h+arg_28]
0x18000e0f2  mov     rbx, rcx
0x18000e0f5  mov     ecx, 430h; this
0x18000e0fa  mov     qword ptr [r14], 0
0x18000e101  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000e106  mov     rdi, rax
0x18000e109  test    rax, rax
0x18000e10c  jz      loc_18000E1ED
0x18000e112  mov     rcx, rax; this
0x18000e115  call    ??0CPicturePasswordDUIHost@@QEAA@XZ; CPicturePasswordDUIHost::CPicturePasswordDUIHost(void)
0x18000e11a  mov     rdx, [rsp+58h+arg_20]
0x18000e122  mov     rcx, rdi; this
0x18000e125  mov     [rsp+58h+var_30], rdx; unsigned int *
0x18000e12a  mov     rdx, rbx; HWND
0x18000e12d  call    ?Initialize@CPicturePasswordDUIHost@@QEAAJPEAUHWND__@@_NIPEAVElement@DirectUI@@PEAK@Z; CPicturePasswordDUIHost::Initialize(HWND__ *,bool,uint,DirectUI::Element *,ulong *)
0x18000e132  mov     ebx, eax
0x18000e134  test    eax, eax
0x18000e136  js      loc_18000E1BE
0x18000e13c  lea     rsi, [rdi+2C8h]
0x18000e143  mov     [rsp+58h+var_38], 0
0x18000e14c  mov     rcx, rsi
0x18000e14f  xor     r9d, r9d
0x18000e152  xor     r8d, r8d
0x18000e155  xor     edx, edx
0x18000e157  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x18000e15d  mov     ebx, eax
0x18000e15f  test    eax, eax
0x18000e161  js      short loc_18000E1BE
0x18000e163  mov     rcx, [rsi]
0x18000e166  lea     r8, __ImageBase
0x18000e16d  mov     r9, r8
0x18000e170  mov     edx, 445Eh
0x18000e175  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x18000e17b  mov     ebx, eax
0x18000e17d  test    eax, eax
0x18000e17f  js      short loc_18000E1BE
0x18000e181  mov     rcx, [rsi]
0x18000e184  lea     rax, [rsp+58h+arg_18]
0x18000e189  mov     [rsp+58h+var_30], rax
0x18000e18e  lea     rdx, aMain; "main"
0x18000e195  xor     r9d, r9d
0x18000e198  mov     [rsp+58h+var_38], 0
0x18000e1a1  mov     r8, rdi
0x18000e1a4  mov     [rsp+58h+arg_18], 0
0x18000e1ad  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18000e1b3  mov     ebx, eax
0x18000e1b5  test    eax, eax
0x18000e1b7  js      short loc_18000E1BE
0x18000e1b9  mov     [r14], rdi
0x18000e1bc  jmp     short loc_18000E1F2
0x18000e1be  lea     rcx, [rdi+1D8h]; this
0x18000e1c5  mov     dl, 1; bool
0x18000e1c7  call    ?Unregister@CPicturePasswordGestureHelper@@QEAAX_N0@Z; CPicturePasswordGestureHelper::Unregister(bool,bool)
0x18000e1cc  mov     rcx, [rdi+368h]; hWnd
0x18000e1d3  lea     rdx, String; "ImmersiveComponentOwnedWindow"
0x18000e1da  call    cs:__imp_RemovePropW
0x18000e1e0  mov     dl, 1
0x18000e1e2  mov     rcx, rdi
0x18000e1e5  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18000e1eb  jmp     short loc_18000E1F2
0x18000e1ed  mov     ebx, 8007000Eh
0x18000e1f2  mov     eax, ebx
0x18000e1f4  add     rsp, 38h
0x18000e1f8  pop     r14
0x18000e1fa  pop     rdi
0x18000e1fb  pop     rsi
0x18000e1fc  pop     rbx
0x18000e1fd  retn
```
