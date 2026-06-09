# IASService::GetRADIUSProtocol(void)

- ea: `0x18003277c`
- end: `0x18003295a`
- name: `?GetRADIUSProtocol@IASService@@QEAAJXZ`
- size: `478`
- prototype: `__int64 __fastcall(IASService *__hidden this)`
- caller_count: `6`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032960`
- `0x180032a90`
- `0x180032ce0`
- `0x180032ea0`
- `0x1800338f0`
- `0x180033a30`

## callees

- `0x180024cac`
- `0x180027e60`
- `0x18002cd00`
- `0x18002f08c`
- `0x18002f240`
- `0x18003277c`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003281a`
- `OLEAUT32!__imp_SysAllocString` at `0x18003281a`
- `OLEAUT32!__imp_VariantInit` at `0x1800327a2`
- `OLEAUT32!__imp_VariantInit` at `0x1800327a2`

## string_xrefs

- `0x1800327f1`: `GetSdoCollection(PROPERTY_IAS_PROTOCOLS_COLLECTION) failed with 0x%x`
- `0x180032810`: `Microsoft Radius Protocol`
- `0x180032876`: `Protocols->Item(%S) failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall IASService::GetRADIUSProtocol(struct ISdo **this)
{
  int SdoCollection; // ebx
  int v3; // edx
  int v5; // [rsp+28h] [rbp-28h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  __int64 (__fastcall ***v7)(_QWORD, GUID *, struct ISdo **); // [rsp+70h] [rbp+20h] BYREF
  struct ISdoCollection *v8; // [rsp+78h] [rbp+28h] BYREF

  v8 = 0;
  v7 = 0;
  VariantInit(&pvarg);
  SdoCollection = GetSdoCollection(this[4], 0x403u, &v8);
  if ( SdoCollection >= 0 )
  {
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(L"Microsoft Radius Protocol");
    SdoCollection = ((__int64 (__fastcall *)(struct ISdoCollection *, VARIANTARG *, _QWORD))v8->lpVtbl->Item)(
                      v8,
                      &pvarg,
                      &v7);
    if ( SdoCollection >= 0 )
    {
      SdoCollection = (**v7)(v7, &IID_ISdo, this + 18);
      if ( SdoCollection < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("DispRADIUS->QI(ISdo) failed with 0x%x");
        v3 = 12;
        goto LABEL_16;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("Protocols->Item(%S) failed with 0x%x");
      v5 = SdoCollection;
      WPP_SF_sSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids,
        (unsigned int)"NPSSDO",
        (__int64)L"Microsoft Radius Protocol",
        v5);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("GetSdoCollection(PROPERTY_IAS_PROTOCOLS_COLLECTION) failed with 0x%x");
    v3 = 10;
LABEL_16:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      (unsigned int)WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids,
      (unsigned int)"NPSSDO",
      SdoCollection);
  }
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v8);
  return (unsigned int)SdoCollection;
}

```

## disassembly

```asm
0x18003277c  mov     [rsp-18h+arg_10], rbx
0x180032781  push    rbp
0x180032782  push    rsi
0x180032783  push    rdi
0x180032784  mov     rbp, rsp
0x180032787  sub     rsp, 50h
0x18003278b  mov     rdi, rcx
0x18003278e  mov     [rbp+arg_8], 0
0x180032796  mov     [rbp+arg_0], 0
0x18003279e  lea     rcx, [rbp+pvarg]; pvarg
0x1800327a2  call    cs:__imp_VariantInit
0x1800327a8  nop
0x1800327a9  lea     r8, [rbp+arg_8]; struct ISdoCollection **
0x1800327ad  mov     edx, 403h; unsigned int
0x1800327b2  mov     rcx, [rdi+20h]; struct ISdo *
0x1800327b6  call    ?GetSdoCollection@@YAJPEAUISdo@@KPEAPEAUISdoCollection@@@Z; GetSdoCollection(ISdo *,ulong,ISdoCollection * *)
0x1800327bb  mov     ebx, eax
0x1800327bd  test    eax, eax
0x1800327bf  jns     short loc_180032807
0x1800327c1  lea     rax, WPP_GLOBAL_Control
0x1800327c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800327cf  cmp     rcx, rax
0x1800327d2  jz      loc_18003292B
0x1800327d8  cmp     byte ptr [rcx+19h], 2
0x1800327dc  jb      loc_18003292B
0x1800327e2  test    dword ptr [rcx+1Ch], 400h
0x1800327e9  jz      loc_18003292B
0x1800327ef  mov     edx, ebx
0x1800327f1  lea     rcx, aGetsdocollecti_0; "GetSdoCollection(PROPERTY_IAS_PROTOCOLS"...
0x1800327f8  call    WppDbgPrint
0x1800327fd  mov     edx, 0Ah
0x180032802  jmp     loc_180032908
0x180032807  mov     eax, 8
0x18003280c  mov     word ptr [rbp+pvarg], ax
0x180032810  lea     rsi, aMicrosoftRadiu; "Microsoft Radius Protocol"
0x180032817  mov     rcx, rsi; psz
0x18003281a  call    cs:__imp_SysAllocString
0x180032820  mov     qword ptr [rbp+pvarg+8], rax
0x180032824  mov     rcx, [rbp+arg_8]
0x180032828  mov     rax, [rcx]
0x18003282b  lea     r8, [rbp+arg_0]
0x18003282f  lea     rdx, [rbp+pvarg]
0x180032833  mov     rax, [rax+68h]
0x180032837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003283c  mov     ebx, eax
0x18003283e  test    eax, eax
0x180032840  jns     short loc_1800328B0
0x180032842  lea     rax, WPP_GLOBAL_Control
0x180032849  mov     rcx, cs:WPP_GLOBAL_Control
0x180032850  cmp     rcx, rax
0x180032853  jz      loc_18003292B
0x180032859  cmp     byte ptr [rcx+19h], 2
0x18003285d  jb      loc_18003292B
0x180032863  test    dword ptr [rcx+1Ch], 400h
0x18003286a  jz      loc_18003292B
0x180032870  mov     r8d, ebx
0x180032873  mov     rdx, rsi
0x180032876  lea     rcx, aProtocolsItemS; "Protocols->Item(%S) failed with 0x%x"
0x18003287d  call    WppDbgPrint
0x180032882  mov     edx, 0Bh
0x180032887  mov     [rsp+50h+var_28], ebx
0x18003288b  mov     [rsp+50h+var_30], rsi
0x180032890  lea     r9, aNpssdo; "NPSSDO"
0x180032897  lea     r8, WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids
0x18003289e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800328a5  mov     rcx, [rcx+10h]
0x1800328a9  call    WPP_SF_sSd
0x1800328ae  jmp     short loc_18003292B
0x1800328b0  mov     rcx, [rbp+arg_0]
0x1800328b4  mov     rax, [rcx]
0x1800328b7  lea     r8, [rdi+90h]
0x1800328be  lea     rdx, IID_ISdo
0x1800328c5  mov     rax, [rax]
0x1800328c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800328cd  mov     ebx, eax
0x1800328cf  test    eax, eax
0x1800328d1  jns     short loc_18003292B
0x1800328d3  lea     rax, WPP_GLOBAL_Control
0x1800328da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800328e1  cmp     rcx, rax
0x1800328e4  jz      short loc_18003292B
0x1800328e6  cmp     byte ptr [rcx+19h], 2
0x1800328ea  jb      short loc_18003292B
0x1800328ec  test    dword ptr [rcx+1Ch], 400h
0x1800328f3  jz      short loc_18003292B
0x1800328f5  mov     edx, ebx
0x1800328f7  lea     rcx, aDispradiusQiIs; "DispRADIUS->QI(ISdo) failed with 0x%x"
0x1800328fe  call    WppDbgPrint
0x180032903  mov     edx, 0Ch
0x180032908  mov     rcx, cs:WPP_GLOBAL_Control
0x18003290f  mov     dword ptr [rsp+50h+var_30], ebx
0x180032913  lea     r9, aNpssdo; "NPSSDO"
0x18003291a  lea     r8, WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids
0x180032921  mov     rcx, [rcx+10h]
0x180032925  call    WPP_SF_sd
0x18003292a  nop
0x18003292b  lea     rcx, [rbp+pvarg]; this
0x18003292f  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180032934  nop
0x180032935  lea     rcx, [rbp+arg_0]
0x180032939  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003293e  nop
0x18003293f  lea     rcx, [rbp+arg_8]
0x180032943  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032948  mov     eax, ebx
0x18003294a  mov     rbx, [rsp+50h+arg_10]
0x180032952  add     rsp, 50h
0x180032956  pop     rdi
0x180032957  pop     rsi
0x180032958  pop     rbp
0x180032959  retn
```
