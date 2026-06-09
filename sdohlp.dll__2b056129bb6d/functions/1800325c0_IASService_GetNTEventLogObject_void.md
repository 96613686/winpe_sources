# IASService::GetNTEventLogObject(void)

- ea: `0x1800325c0`
- end: `0x180032776`
- name: `?GetNTEventLogObject@IASService@@QEAAJXZ`
- size: `438`
- prototype: `__int64 __fastcall(IASService *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180033230`
- `0x180033360`
- `0x180033b70`
- `0x180033cc0`

## callees

- `0x180024cac`
- `0x180027e60`
- `0x18002cd00`
- `0x18002f240`
- `0x1800325c0`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003265f`
- `OLEAUT32!__imp_SysAllocString` at `0x18003265f`
- `OLEAUT32!__imp_VariantInit` at `0x1800325ea`
- `OLEAUT32!__imp_VariantInit` at `0x1800325ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall IASService::GetNTEventLogObject(struct ISdo **this)
{
  int SdoCollection; // ebx
  int v3; // edx
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  __int64 (__fastcall ***v6)(_QWORD, GUID *, struct ISdo **); // [rsp+70h] [rbp+20h] BYREF
  struct ISdoCollection *v7; // [rsp+78h] [rbp+28h] BYREF
  __int64 v8; // [rsp+80h] [rbp+30h] BYREF

  v7 = 0;
  v6 = 0;
  v8 = 0;
  VariantInit(&pvarg);
  SdoCollection = GetSdoCollection(this[4], 0x404u, &v7);
  if ( SdoCollection >= 0 )
  {
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(L"Microsoft NT Event Log Auditor");
    SdoCollection = ((__int64 (__fastcall *)(struct ISdoCollection *, VARIANTARG *, _QWORD))v7->lpVtbl->Item)(
                      v7,
                      &pvarg,
                      &v6);
    if ( SdoCollection >= 0 )
    {
      SdoCollection = (**v6)(v6, &IID_ISdo, this + 22);
      if ( SdoCollection < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("pDispEventLog->QI(ISdo) failed with 0x%x");
        v3 = 15;
        goto LABEL_16;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("pAuditors->Item returned 0x%x");
      v3 = 14;
      goto LABEL_16;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("GetSdoCollection(PROPERTY_IAS_AUDITORS_COLLECTION) returned 0x%x");
    v3 = 13;
LABEL_16:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      (unsigned int)WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids,
      (unsigned int)"NPSSDO",
      SdoCollection);
  }
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v8);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v6);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v7);
  return (unsigned int)SdoCollection;
}

```

## disassembly

```asm
0x1800325c0  push    rbp
0x1800325c2  push    rbx
0x1800325c3  push    rdi
0x1800325c4  mov     rbp, rsp
0x1800325c7  sub     rsp, 50h
0x1800325cb  mov     rdi, rcx
0x1800325ce  mov     [rbp+arg_8], 0
0x1800325d6  mov     [rbp+arg_0], 0
0x1800325de  mov     [rbp+arg_10], 0
0x1800325e6  lea     rcx, [rbp+pvarg]; pvarg
0x1800325ea  call    cs:__imp_VariantInit
0x1800325f0  nop
0x1800325f1  lea     r8, [rbp+arg_8]; struct ISdoCollection **
0x1800325f5  mov     edx, 404h; unsigned int
0x1800325fa  mov     rcx, [rdi+20h]; struct ISdo *
0x1800325fe  call    ?GetSdoCollection@@YAJPEAUISdo@@KPEAPEAUISdoCollection@@@Z; GetSdoCollection(ISdo *,ulong,ISdoCollection * *)
0x180032603  mov     ebx, eax
0x180032605  test    eax, eax
0x180032607  jns     short loc_18003264F
0x180032609  lea     rax, WPP_GLOBAL_Control
0x180032610  mov     rcx, cs:WPP_GLOBAL_Control
0x180032617  cmp     rcx, rax
0x18003261a  jz      loc_180032745
0x180032620  cmp     byte ptr [rcx+19h], 2
0x180032624  jb      loc_180032745
0x18003262a  test    dword ptr [rcx+1Ch], 400h
0x180032631  jz      loc_180032745
0x180032637  mov     edx, ebx
0x180032639  lea     rcx, aGetsdocollecti_5; "GetSdoCollection(PROPERTY_IAS_AUDITORS_"...
0x180032640  call    WppDbgPrint
0x180032645  mov     edx, 0Dh
0x18003264a  jmp     loc_180032722
0x18003264f  mov     eax, 8
0x180032654  mov     word ptr [rbp+pvarg], ax
0x180032658  lea     rcx, aMicrosoftNtEve; "Microsoft NT Event Log Auditor"
0x18003265f  call    cs:__imp_SysAllocString
0x180032665  mov     qword ptr [rbp+pvarg+8], rax
0x180032669  mov     rcx, [rbp+arg_8]
0x18003266d  mov     rax, [rcx]
0x180032670  lea     r8, [rbp+arg_0]
0x180032674  lea     rdx, [rbp+pvarg]
0x180032678  mov     rax, [rax+68h]
0x18003267c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032681  mov     ebx, eax
0x180032683  test    eax, eax
0x180032685  jns     short loc_1800326CA
0x180032687  lea     rax, WPP_GLOBAL_Control
0x18003268e  mov     rcx, cs:WPP_GLOBAL_Control
0x180032695  cmp     rcx, rax
0x180032698  jz      loc_180032745
0x18003269e  cmp     byte ptr [rcx+19h], 2
0x1800326a2  jb      loc_180032745
0x1800326a8  test    dword ptr [rcx+1Ch], 400h
0x1800326af  jz      loc_180032745
0x1800326b5  mov     edx, ebx
0x1800326b7  lea     rcx, aPauditorsItemR; "pAuditors->Item returned 0x%x"
0x1800326be  call    WppDbgPrint
0x1800326c3  mov     edx, 0Eh
0x1800326c8  jmp     short loc_180032722
0x1800326ca  mov     rcx, [rbp+arg_0]
0x1800326ce  mov     rax, [rcx]
0x1800326d1  lea     r8, [rdi+0B0h]
0x1800326d8  lea     rdx, IID_ISdo
0x1800326df  mov     rax, [rax]
0x1800326e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800326e7  mov     ebx, eax
0x1800326e9  test    eax, eax
0x1800326eb  jns     short loc_180032745
0x1800326ed  lea     rax, WPP_GLOBAL_Control
0x1800326f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800326fb  cmp     rcx, rax
0x1800326fe  jz      short loc_180032745
0x180032700  cmp     byte ptr [rcx+19h], 2
0x180032704  jb      short loc_180032745
0x180032706  test    dword ptr [rcx+1Ch], 400h
0x18003270d  jz      short loc_180032745
0x18003270f  mov     edx, ebx
0x180032711  lea     rcx, aPdispeventlogQ; "pDispEventLog->QI(ISdo) failed with 0x%"...
0x180032718  call    WppDbgPrint
0x18003271d  mov     edx, 0Fh
0x180032722  mov     rcx, cs:WPP_GLOBAL_Control
0x180032729  mov     [rsp+50h+var_30], ebx
0x18003272d  lea     r9, aNpssdo; "NPSSDO"
0x180032734  lea     r8, WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids
0x18003273b  mov     rcx, [rcx+10h]
0x18003273f  call    WPP_SF_sd
0x180032744  nop
0x180032745  lea     rcx, [rbp+pvarg]; this
0x180032749  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003274e  nop
0x18003274f  lea     rcx, [rbp+arg_10]
0x180032753  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032758  nop
0x180032759  lea     rcx, [rbp+arg_0]
0x18003275d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032762  nop
0x180032763  lea     rcx, [rbp+arg_8]
0x180032767  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003276c  mov     eax, ebx
0x18003276e  add     rsp, 50h
0x180032772  pop     rdi
0x180032773  pop     rbx
0x180032774  pop     rbp
0x180032775  retn
```
