# CWallpaperPage::LayoutInitialized(void)

- ea: `0x180044280`
- end: `0x1800444c7`
- name: `?LayoutInitialized@CWallpaperPage@@UEAAJXZ`
- size: `583`
- prototype: `__int64 __fastcall(CWallpaperPage *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task`

## callees

- `0x18000268c`
- `0x180024828`
- `0x18003a508`
- `0x18003b8e8`
- `0x18003bacc`
- `0x180044280`
- `0x18004f80c`
- `0x180052ff8`
- `0x180057010`

## import_xrefs

- `PROPSYS!PSPropertyBag_ReadType` at `0x18004430e`
- `PROPSYS!PSPropertyBag_ReadType` at `0x18004430e`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800442d7`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800442d7`
- `OLEAUT32!__imp_VariantClear` at `0x1800443de`
- `OLEAUT32!__imp_VariantClear` at `0x1800443de`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180044460`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180044460`
- `DUI70!StrToID` at `0x18004444e`
- `DUI70!StrToID` at `0x18004444e`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180044485`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180044485`

## pseudocode

```c
__int64 __fastcall CWallpaperPage::LayoutInitialized(CWallpaperCore **this)
{
  __int64 v2; // r8
  IUnknown *v3; // rcx
  HRESULT v4; // esi
  CWallpaperCore *v5; // rax
  CWallpaperCore *v6; // rax
  CWallpaperCore *v7; // r14
  CWallpaperCore *v8; // rcx
  int v9; // esi
  unsigned __int16 v10; // ax
  DirectUI::Element *Descendent; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-30h] BYREF
  VARIANT var; // [rsp+38h] [rbp-18h] BYREF
  void *ppvOut; // [rsp+80h] [rbp+30h] BYREF
  CWallpaperCore *v16; // [rsp+88h] [rbp+38h]

  CControlPanelPage::LayoutInitialized((CControlPanelPage *)this);
  if ( !this[5] )
  {
    v3 = (IUnknown *)*(this - 1);
    ppvOut = 0;
    if ( IUnknown_QueryService(
           v3,
           (const GUID *const)&SID_PerNamespaceIDPropertyBag,
           &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
           &ppvOut) < 0 )
      return (unsigned int)DisplayPageBarricade(
                             (struct DirectUI::Element *)(this - 28),
                             L"PageContent",
                             L"GenericDisabledBarricade");
    memset(&var, 0, sizeof(var));
    v4 = PSPropertyBag_ReadType((IPropertyBag *)ppvOut, L"WallpaperCore", &var, 0xDu);
    if ( v4 < 0 )
    {
      v5 = (CWallpaperCore *)operator new(0x1C0u, (const struct std::nothrow_t *)&std::nothrow);
      v16 = v5;
      if ( v5 && (v6 = CWallpaperCore::CWallpaperCore(v5), (v7 = v6) != 0) )
      {
        v4 = CWallpaperCore::Initialize(v6);
        if ( v4 >= 0 )
        {
          v4 = (**(__int64 (__fastcall ***)(CWallpaperCore *, GUID *, char *))v7)(
                 v7,
                 &GUID_00000000_0000_0000_c000_000000000046,
                 (char *)this + 40);
          if ( v4 >= 0 )
          {
            v8 = this[5];
            memset(&pvarg, 0, sizeof(pvarg));
            pvarg.vt = 13;
            v4 = (**(__int64 (__fastcall ***)(CWallpaperCore *, GUID *, ULONG *))v8)(
                   v8,
                   &GUID_00000000_0000_0000_c000_000000000046,
                   (ULONG *)&pvarg.cyVal);
            if ( v4 >= 0 )
            {
              v4 = (*(__int64 (__fastcall **)(void *, const WCHAR *, VARIANTARG *))(*(_QWORD *)ppvOut + 32LL))(
                     ppvOut,
                     L"WallpaperCore",
                     &pvarg);
              VariantClear(&pvarg);
            }
          }
        }
        (*(void (__fastcall **)(CWallpaperCore *))(*(_QWORD *)v7 + 16LL))(v7);
      }
      else
      {
        v4 = -2147024882;
      }
    }
    else
    {
      this[5] = (CWallpaperCore *)var.llVal;
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    if ( v4 < 0 )
      return (unsigned int)DisplayPageBarricade(
                             (struct DirectUI::Element *)(this - 28),
                             L"PageContent",
                             L"GenericDisabledBarricade");
  }
  v9 = CWallpaperCore::InitializePage(this[5], (struct CWallpaperPage *)(this - 28), v2);
  if ( v9 >= 0 )
  {
    if ( (unsigned int)IsWallpaperDisabledByTerminalServerClient() )
      v9 = DisplayPageBarricade((struct DirectUI::Element *)(this - 28), L"PageContent", L"RemoteSessionBarricade");
    v10 = StrToID(L"ControlsParent");
    Descendent = DirectUI::Element::FindDescendent((DirectUI::Element *)(this - 28), v10);
    this[6] = Descendent;
    if ( Descendent )
      DirectUI::Element::AddListener(
        Descendent,
        (struct DirectUI::IElementListener *)((unsigned __int64)(this + 4) & -(__int64)(this != (CWallpaperCore **)224)));
  }
  else
  {
    return (unsigned int)DisplayPageBarricade(
                           (struct DirectUI::Element *)(this - 28),
                           L"PageContent",
                           L"GenericDisabledBarricade");
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180044280  mov     [rsp-28h+arg_10], rbx
0x180044285  mov     [rsp-28h+arg_18], rsi
0x18004428a  push    rbp
0x18004428b  push    rdi
0x18004428c  push    r12
0x18004428e  push    r14
0x180044290  push    r15
0x180044292  mov     rbp, rsp
0x180044295  sub     rsp, 50h
0x180044299  mov     rbx, rcx
0x18004429c  call    ?LayoutInitialized@CControlPanelPage@@UEAAJXZ; CControlPanelPage::LayoutInitialized(void)
0x1800442a1  lea     rdi, [rbx-0E0h]
0x1800442a8  lea     r15, [rdi+108h]
0x1800442af  cmp     qword ptr [r15], 0
0x1800442b3  jnz     loc_180044414
0x1800442b9  mov     rcx, [rbx-8]; punk
0x1800442bd  lea     r9, [rbp+ppvOut]; ppvOut
0x1800442c1  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x1800442c8  mov     [rbp+ppvOut], 0
0x1800442d0  lea     rdx, SID_PerNamespaceIDPropertyBag; guidService
0x1800442d7  call    cs:__imp_IUnknown_QueryService
0x1800442de  nop     dword ptr [rax+rax+00h]
0x1800442e3  test    eax, eax
0x1800442e5  js      loc_180044493
0x1800442eb  mov     rcx, [rbp+ppvOut]; propBag
0x1800442ef  lea     r8, [rbp+var]; var
0x1800442f3  xor     eax, eax
0x1800442f5  lea     rdx, aWallpapercore; "WallpaperCore"
0x1800442fc  xorps   xmm0, xmm0
0x1800442ff  mov     qword ptr [rbp+var+10h], rax
0x180044303  movups  xmmword ptr [rbp+var], xmm0
0x180044307  lea     r12d, [rax+0Dh]
0x18004430b  mov     r9d, r12d; type
0x18004430e  call    cs:__imp_PSPropertyBag_ReadType
0x180044315  nop     dword ptr [rax+rax+00h]
0x18004431a  mov     esi, eax
0x18004431c  test    eax, eax
0x18004431e  js      short loc_18004432D
0x180044320  mov     rcx, qword ptr [rbp+var+8]
0x180044324  mov     [rbx+28h], rcx
0x180044328  jmp     loc_180044400
0x18004432d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180044334  mov     ecx, 1C0h; unsigned __int64
0x180044339  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004433e  mov     [rbp+arg_8], rax
0x180044342  test    rax, rax
0x180044345  jz      loc_1800443FB
0x18004434b  mov     rcx, rax; this
0x18004434e  call    ??0CWallpaperCore@@QEAA@XZ; CWallpaperCore::CWallpaperCore(void)
0x180044353  mov     r14, rax
0x180044356  test    rax, rax
0x180044359  jz      loc_1800443FB
0x18004435f  mov     rcx, rax; this
0x180044362  call    ?Initialize@CWallpaperCore@@QEAAJXZ; CWallpaperCore::Initialize(void)
0x180044367  mov     esi, eax
0x180044369  test    eax, eax
0x18004436b  js      short loc_1800443EA
0x18004436d  mov     rcx, [r14]
0x180044370  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180044377  mov     r8, r15
0x18004437a  mov     rax, [rcx]
0x18004437d  mov     rcx, r14
0x180044380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044385  mov     esi, eax
0x180044387  test    eax, eax
0x180044389  js      short loc_1800443EA
0x18004438b  mov     rcx, [rbx+28h]
0x18004438f  lea     r8, [rbp+pvarg+8]
0x180044393  xor     eax, eax
0x180044395  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18004439c  mov     qword ptr [rbp+pvarg+10h], rax
0x1800443a0  xorps   xmm0, xmm0
0x1800443a3  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800443a7  mov     word ptr [rbp+pvarg], r12w
0x1800443ac  mov     rax, [rcx]
0x1800443af  mov     rax, [rax]
0x1800443b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443b7  mov     esi, eax
0x1800443b9  test    eax, eax
0x1800443bb  js      short loc_1800443EA
0x1800443bd  mov     rcx, [rbp+ppvOut]
0x1800443c1  lea     r8, [rbp+pvarg]
0x1800443c5  lea     rdx, aWallpapercore; "WallpaperCore"
0x1800443cc  mov     rax, [rcx]
0x1800443cf  mov     rax, [rax+20h]
0x1800443d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443d8  lea     rcx, [rbp+pvarg]; pvarg
0x1800443dc  mov     esi, eax
0x1800443de  call    cs:__imp_VariantClear
0x1800443e5  nop     dword ptr [rax+rax+00h]
0x1800443ea  mov     rax, [r14]
0x1800443ed  mov     rcx, r14
0x1800443f0  mov     rax, [rax+10h]
0x1800443f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443f9  jmp     short loc_180044400
0x1800443fb  mov     esi, 8007000Eh
0x180044400  mov     rcx, [rbp+ppvOut]
0x180044404  mov     rax, [rcx]
0x180044407  mov     rax, [rax+10h]
0x18004440b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044410  test    esi, esi
0x180044412  js      short loc_180044493
0x180044414  mov     rcx, [rbx+28h]; this
0x180044418  mov     rdx, rdi; struct CWallpaperPage *
0x18004441b  call    ?InitializePage@CWallpaperCore@@QEAAJPEAVCWallpaperPage@@@Z; CWallpaperCore::InitializePage(CWallpaperPage *)
0x180044420  mov     esi, eax
0x180044422  test    eax, eax
0x180044424  js      short loc_180044493
0x180044426  call    IsWallpaperDisabledByTerminalServerClient
0x18004442b  test    eax, eax
0x18004442d  jz      short loc_180044447
0x18004442f  lea     r8, aRemotesessionb; "RemoteSessionBarricade"
0x180044436  mov     rcx, rdi; struct DirectUI::Element *
0x180044439  lea     rdx, aPagecontent; "PageContent"
0x180044440  call    ?DisplayPageBarricade@@YAJPEAVElement@DirectUI@@PEBG1@Z; DisplayPageBarricade(DirectUI::Element *,ushort const *,ushort const *)
0x180044445  mov     esi, eax
0x180044447  lea     rcx, aControlsparent; "ControlsParent"
0x18004444e  call    cs:__imp_StrToID
0x180044455  nop     dword ptr [rax+rax+00h]
0x18004445a  movzx   edx, ax
0x18004445d  mov     rcx, rdi
0x180044460  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180044467  nop     dword ptr [rax+rax+00h]
0x18004446c  mov     [rbx+30h], rax
0x180044470  test    rax, rax
0x180044473  jz      short loc_1800444AB
0x180044475  neg     rdi
0x180044478  lea     rcx, [rbx+20h]
0x18004447c  sbb     rdx, rdx
0x18004447f  and     rdx, rcx
0x180044482  mov     rcx, rax
0x180044485  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x18004448c  nop     dword ptr [rax+rax+00h]
0x180044491  jmp     short loc_1800444AB
0x180044493  lea     r8, aGenericdisable; "GenericDisabledBarricade"
0x18004449a  mov     rcx, rdi; struct DirectUI::Element *
0x18004449d  lea     rdx, aPagecontent; "PageContent"
0x1800444a4  call    ?DisplayPageBarricade@@YAJPEAVElement@DirectUI@@PEBG1@Z; DisplayPageBarricade(DirectUI::Element *,ushort const *,ushort const *)
0x1800444a9  mov     esi, eax
0x1800444ab  lea     r11, [rsp+50h+var_s0]
0x1800444b0  mov     eax, esi
0x1800444b2  mov     rbx, [r11+40h]
0x1800444b6  mov     rsi, [r11+48h]
0x1800444ba  mov     rsp, r11
0x1800444bd  pop     r15
0x1800444bf  pop     r14
0x1800444c1  pop     r12
0x1800444c3  pop     rdi
0x1800444c4  pop     rbp
0x1800444c5  retn
```
