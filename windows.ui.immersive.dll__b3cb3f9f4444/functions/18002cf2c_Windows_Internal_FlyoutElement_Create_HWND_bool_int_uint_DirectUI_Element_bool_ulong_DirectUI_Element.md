# Windows::Internal::FlyoutElement::Create(HWND__ *,bool,int,uint,DirectUI::Element *,bool,ulong *,DirectUI::Element * *)

- ea: `0x18002cf2c`
- end: `0x18002d0c9`
- name: `?Create@FlyoutElement@Internal@Windows@@SAJPEAUHWND__@@_NHIPEAVElement@DirectUI@@1PEAKPEAPEAV56@@Z`
- size: `413`
- prototype: `__int64 __fastcall(HWND, bool, int, unsigned int, struct DirectUI::Element *, bool, unsigned int *, struct DirectUI::Element **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180047c3c`

## callees

- `0x18002cf2c`
- `0x18003eec4`
- `0x18003ef34`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002cfe8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002cfe8`
- `DUI70!??0TouchHWNDElement@DirectUI@@QEAA@XZ` at `0x18002cf6a`
- `DUI70!??0TouchHWNDElement@DirectUI@@QEAA@XZ` at `0x18002cf6a`
- `DUI70!?Initialize@TouchHWNDElement@DirectUI@@QEAAJPEAUHWND__@@_NIPEAVElement@2@PEAK@Z` at `0x18002cfb2`
- `DUI70!?Initialize@TouchHWNDElement@DirectUI@@QEAAJPEAUHWND__@@_NIPEAVElement@2@PEAK@Z` at `0x18002cfb2`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18002d018`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18002d018`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18002d05c`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18002d05c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18002d087`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18002d087`
- `DUI70!StrToID` at `0x18002d075`
- `DUI70!StrToID` at `0x18002d075`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18002d0af`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18002d0af`

## pseudocode

```c
__int64 __fastcall Windows::Internal::FlyoutElement::Create(
        HWND a1,
        unsigned __int64 a2,
        unsigned int a3,
        __int64 a4,
        struct DirectUI::Element *a5,
        bool a6,
        unsigned int *a7,
        struct DirectUI::Element **a8)
{
  struct DirectUI::Element **v8; // r14
  int Element; // ebx
  DirectUI::TouchHWNDElement *v12; // rax
  DirectUI::TouchHWNDElement *v13; // rdi
  DirectUI::DUIXmlParser **Value; // rax
  DirectUI::DUIXmlParser *v15; // rsi
  unsigned __int16 v16; // ax
  struct DirectUI::Element *Descendent; // rax

  v8 = a8;
  Element = -2147024882;
  *a8 = 0;
  v12 = (DirectUI::TouchHWNDElement *)DirectUI::AccHAllocAndZero((DirectUI *)0x1B0, a2);
  v13 = v12;
  if ( v12 )
  {
    DirectUI::TouchHWNDElement::TouchHWNDElement(v12);
    *(_QWORD *)v13 = &Windows::Internal::FlyoutElement::`vftable';
    *((_BYTE *)v13 + 424) = a6;
    Element = DirectUI::TouchHWNDElement::Initialize(v13, a1, 1, 0x18u, 0, a7);
    if ( Element < 0 )
      goto LABEL_10;
    Element = -2147024882;
    a8 = 0;
    if ( dwTlsIndex == -1 )
      goto LABEL_10;
    Value = (DirectUI::DUIXmlParser **)TlsGetValue(dwTlsIndex);
    if ( !Value )
      goto LABEL_10;
    v15 = *Value;
    if ( *Value
      && (Element = DirectUI::DUIXmlParser::SetXMLFromResource(*Value, a3, &_ImageBase, &_ImageBase), Element >= 0)
      && (a8 = 0,
          Element = DirectUI::DUIXmlParser::CreateElement(v15, L"main", v13, 0, 0, (struct DirectUI::Element **)&a8),
          Element >= 0)
      && (v16 = StrToID(L"ButtonBar"),
          Descendent = DirectUI::Element::FindDescendent(v13, v16),
          Element = Windows::Internal::ButtonBarLayout::CreateAndAttachButtonBarLayout(Descendent),
          Element >= 0) )
    {
      *v8 = v13;
    }
    else
    {
LABEL_10:
      DirectUI::Element::Destroy(v13, 0);
    }
  }
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x18002cf2c  push    rbx
0x18002cf2e  push    rbp
0x18002cf2f  push    rsi
0x18002cf30  push    rdi
0x18002cf31  push    r14
0x18002cf33  sub     rsp, 30h
0x18002cf37  mov     r14, [rsp+58h+arg_38]
0x18002cf3f  mov     rsi, rcx
0x18002cf42  mov     ecx, 1B0h; this
0x18002cf47  mov     ebp, r8d
0x18002cf4a  mov     ebx, 8007000Eh
0x18002cf4f  mov     qword ptr [r14], 0
0x18002cf56  call    ?AccHAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::AccHAllocAndZero(unsigned __int64)
0x18002cf5b  mov     rdi, rax
0x18002cf5e  test    rax, rax
0x18002cf61  jz      loc_18002D0BB
0x18002cf67  mov     rcx, rax
0x18002cf6a  call    cs:__imp_??0TouchHWNDElement@DirectUI@@QEAA@XZ; DirectUI::TouchHWNDElement::TouchHWNDElement(void)
0x18002cf71  nop     dword ptr [rax+rax+00h]
0x18002cf76  lea     rax, ??_7FlyoutElement@Internal@Windows@@6B@; const Windows::Internal::FlyoutElement::`vftable'
0x18002cf7d  mov     r9d, 18h
0x18002cf83  mov     [rdi], rax
0x18002cf86  mov     r8b, 1
0x18002cf89  mov     al, [rsp+58h+arg_28]
0x18002cf90  mov     rdx, rsi
0x18002cf93  mov     [rdi+1A8h], al
0x18002cf99  mov     rcx, rdi
0x18002cf9c  mov     rax, [rsp+58h+arg_30]
0x18002cfa4  mov     [rsp+58h+var_30], rax
0x18002cfa9  mov     [rsp+58h+var_38], 0
0x18002cfb2  call    cs:__imp_?Initialize@TouchHWNDElement@DirectUI@@QEAAJPEAUHWND__@@_NIPEAVElement@2@PEAK@Z; DirectUI::TouchHWNDElement::Initialize(HWND__ *,bool,uint,DirectUI::Element *,ulong *)
0x18002cfb9  nop     dword ptr [rax+rax+00h]
0x18002cfbe  mov     ebx, eax
0x18002cfc0  test    eax, eax
0x18002cfc2  js      loc_18002D0AA
0x18002cfc8  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18002cfce  mov     ebx, 8007000Eh
0x18002cfd3  mov     [rsp+58h+arg_38], 0
0x18002cfdf  cmp     ecx, 0FFFFFFFFh
0x18002cfe2  jz      loc_18002D0A6
0x18002cfe8  call    cs:__imp_TlsGetValue
0x18002cfef  nop     dword ptr [rax+rax+00h]
0x18002cff4  test    rax, rax
0x18002cff7  jz      loc_18002D0A6
0x18002cffd  mov     rsi, [rax]
0x18002d000  test    rsi, rsi
0x18002d003  jz      loc_18002D0A6
0x18002d009  lea     r8, __ImageBase
0x18002d010  mov     edx, ebp
0x18002d012  mov     r9, r8
0x18002d015  mov     rcx, rsi
0x18002d018  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x18002d01f  nop     dword ptr [rax+rax+00h]
0x18002d024  mov     ebx, eax
0x18002d026  test    eax, eax
0x18002d028  js      short loc_18002D0A6
0x18002d02a  lea     rax, [rsp+58h+arg_38]
0x18002d032  mov     [rsp+58h+arg_38], 0
0x18002d03e  mov     [rsp+58h+var_30], rax
0x18002d043  lea     rdx, aMain; "main"
0x18002d04a  xor     r9d, r9d
0x18002d04d  mov     [rsp+58h+var_38], 0
0x18002d056  mov     r8, rdi
0x18002d059  mov     rcx, rsi
0x18002d05c  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18002d063  nop     dword ptr [rax+rax+00h]
0x18002d068  mov     ebx, eax
0x18002d06a  test    eax, eax
0x18002d06c  js      short loc_18002D0A6
0x18002d06e  lea     rcx, aButtonbar; "ButtonBar"
0x18002d075  call    cs:__imp_StrToID
0x18002d07c  nop     dword ptr [rax+rax+00h]
0x18002d081  movzx   edx, ax
0x18002d084  mov     rcx, rdi
0x18002d087  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18002d08e  nop     dword ptr [rax+rax+00h]
0x18002d093  mov     rcx, rax; struct DirectUI::Element *
0x18002d096  call    ?CreateAndAttachButtonBarLayout@ButtonBarLayout@Internal@Windows@@SAJPEAVElement@DirectUI@@@Z; Windows::Internal::ButtonBarLayout::CreateAndAttachButtonBarLayout(DirectUI::Element *)
0x18002d09b  mov     ebx, eax
0x18002d09d  test    eax, eax
0x18002d09f  js      short loc_18002D0AA
0x18002d0a1  mov     [r14], rdi
0x18002d0a4  jmp     short loc_18002D0BB
0x18002d0a6  test    ebx, ebx
0x18002d0a8  jns     short loc_18002D0BB
0x18002d0aa  xor     edx, edx
0x18002d0ac  mov     rcx, rdi
0x18002d0af  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18002d0b6  nop     dword ptr [rax+rax+00h]
0x18002d0bb  mov     eax, ebx
0x18002d0bd  add     rsp, 30h
0x18002d0c1  pop     r14
0x18002d0c3  pop     rdi
0x18002d0c4  pop     rsi
0x18002d0c5  pop     rbp
0x18002d0c6  pop     rbx
0x18002d0c7  retn
```
