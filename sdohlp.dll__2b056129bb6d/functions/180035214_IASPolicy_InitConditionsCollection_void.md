# IASPolicy::InitConditionsCollection(void)

- ea: `0x180035214`
- end: `0x18003547a`
- name: `?InitConditionsCollection@IASPolicy@@AEAAJXZ`
- size: `614`
- prototype: `__int64 __fastcall(IASPolicy *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800356fc`

## callees

- `0x180024cac`
- `0x180027e60`
- `0x18002cd00`
- `0x180030814`
- `0x180034328`
- `0x180035214`
- `0x180042a80`
- `0x180058010`

## string_xrefs

- `0x1800352f8`: `CreateInstance(IASConditionsCollection) failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall IASPolicy::InitConditionsCollection(IASPolicy *this)
{
  _QWORD *v2; // rsi
  __int64 v3; // rcx
  int SdoCollection; // ebx
  int v5; // edx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  struct ISdoCollection *v9; // r10
  __int64 (__fastcall ***v10)(_QWORD, GUID *, _QWORD *); // r14
  PVOID *v11; // rax
  struct ISdoCollection *v13; // [rsp+50h] [rbp+8h] BYREF
  __int64 v14; // [rsp+58h] [rbp+10h] BYREF

  v2 = (_QWORD *)((char *)this + 136);
  v3 = *((_QWORD *)this + 17);
  if ( v3 )
  {
    *v2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  v13 = 0;
  SdoCollection = GetSdoCollection(*((struct ISdo **)this + 4), 0x406u, &v13);
  if ( SdoCollection >= 0 )
  {
    v14 = 0;
    SdoCollection = ATL::CComObject<IASConditionsCollection>::CreateInstance(&v14);
    if ( SdoCollection >= 0 )
    {
      v6 = *((_QWORD *)this + 7);
      v7 = *((_QWORD *)this + 6);
      v8 = *((_QWORD *)this + 5);
      v9 = v13;
      v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))v14;
      *(_DWORD *)(v14 + 128) = *((_DWORD *)this + 30);
      SdoCollection = IASCollection::Initialize(v10 + 1, 12, v9, v8, v7, v6);
      if ( SdoCollection >= 0 )
      {
        SdoCollection = (**v10)(v10, &IID_IIASConditionsCollection, v2);
        if ( SdoCollection < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("QI(IID_IIASConditionsCollection) failed with 0x%x");
          v5 = 40;
          goto LABEL_27;
        }
      }
      else
      {
        v11 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("IASCollection::Initialize(IASCONDITION) failed with 0x%x");
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              15,
              (unsigned int)WPP_d784a1b6d1803fc8648a97fdfe4f82a5_Traceguids,
              (unsigned int)"NPSSDO",
              SdoCollection);
            v11 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v11 != &WPP_GLOBAL_Control && *((_BYTE *)v11 + 25) >= 2u && (*((_DWORD *)v11 + 7) & 0x400) != 0 )
          {
            WppDbgPrint("pConditions->Initialize failed with 0x%x");
            v5 = 39;
            goto LABEL_27;
          }
        }
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("CreateInstance(IASConditionsCollection) failed with 0x%x");
      v5 = 38;
      goto LABEL_27;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("GetSdoCollection(PROPERTY_POLICY_CONDITIONS_COLLECTION) hr=0x%X");
    v5 = 37;
LABEL_27:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)WPP_dd21b8743a813b1e52cbedc9bc221252_Traceguids,
      (unsigned int)"NPSSDO",
      SdoCollection);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
  return (unsigned int)SdoCollection;
}

```

## disassembly

```asm
0x180035214  mov     [rsp+arg_10], rbx
0x180035219  push    rsi
0x18003521a  push    rdi
0x18003521b  push    r14
0x18003521d  sub     rsp, 30h
0x180035221  mov     rdi, rcx
0x180035224  lea     rsi, [rcx+88h]
0x18003522b  mov     rcx, [rsi]
0x18003522e  test    rcx, rcx
0x180035231  jz      short loc_180035247
0x180035233  mov     qword ptr [rsi], 0
0x18003523a  mov     rax, [rcx]
0x18003523d  mov     rax, [rax+10h]
0x180035241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035246  nop
0x180035247  mov     [rsp+48h+arg_0], 0
0x180035250  lea     r8, [rsp+48h+arg_0]; struct ISdoCollection **
0x180035255  mov     edx, 406h; unsigned int
0x18003525a  mov     rcx, [rdi+20h]; struct ISdo *
0x18003525e  call    ?GetSdoCollection@@YAJPEAUISdo@@KPEAPEAUISdoCollection@@@Z; GetSdoCollection(ISdo *,ulong,ISdoCollection * *)
0x180035263  mov     ebx, eax
0x180035265  test    eax, eax
0x180035267  jns     short loc_1800352AF
0x180035269  lea     rdi, WPP_GLOBAL_Control
0x180035270  mov     rax, cs:WPP_GLOBAL_Control
0x180035277  cmp     rax, rdi
0x18003527a  jz      loc_180035460
0x180035280  cmp     byte ptr [rax+19h], 2
0x180035284  jb      loc_180035460
0x18003528a  test    dword ptr [rax+1Ch], 400h
0x180035291  jz      loc_180035460
0x180035297  mov     edx, ebx
0x180035299  lea     rcx, aGetsdocollecti; "GetSdoCollection(PROPERTY_POLICY_CONDIT"...
0x1800352a0  call    WppDbgPrint
0x1800352a5  mov     edx, 25h ; '%'
0x1800352aa  jmp     loc_18003543D
0x1800352af  mov     [rsp+48h+arg_8], 0
0x1800352b8  lea     rcx, [rsp+48h+arg_8]
0x1800352bd  call    ?CreateInstance@?$CComObject@VIASConditionsCollection@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<IASConditionsCollection>::CreateInstance(ATL::CComObject<IASConditionsCollection> * *)
0x1800352c2  mov     ebx, eax
0x1800352c4  test    eax, eax
0x1800352c6  jns     short loc_18003530E
0x1800352c8  lea     rdi, WPP_GLOBAL_Control
0x1800352cf  mov     rax, cs:WPP_GLOBAL_Control
0x1800352d6  cmp     rax, rdi
0x1800352d9  jz      loc_180035460
0x1800352df  cmp     byte ptr [rax+19h], 2
0x1800352e3  jb      loc_180035460
0x1800352e9  test    dword ptr [rax+1Ch], 400h
0x1800352f0  jz      loc_180035460
0x1800352f6  mov     edx, ebx
0x1800352f8  lea     rcx, aCreateinstance_5; "CreateInstance(IASConditionsCollection)"...
0x1800352ff  call    WppDbgPrint
0x180035304  mov     edx, 26h ; '&'
0x180035309  jmp     loc_18003543D
0x18003530e  mov     rdx, [rdi+38h]
0x180035312  mov     r8, [rdi+30h]
0x180035316  mov     r9, [rdi+28h]
0x18003531a  mov     r10, [rsp+48h+arg_0]
0x18003531f  mov     r14, [rsp+48h+arg_8]
0x180035324  mov     eax, [rdi+78h]
0x180035327  mov     [r14+80h], eax
0x18003532e  lea     rcx, [r14+8]
0x180035332  mov     [rsp+48h+var_20], rdx
0x180035337  mov     [rsp+48h+var_28], r8
0x18003533c  mov     r8, r10
0x18003533f  mov     edx, 0Ch
0x180035344  call    ?Initialize@IASCollection@@QEAAJW4_ITEMTYPE@@PEAUISdoCollection@@PEAUISdo@@PEAUISdoMachine@@PEAUISdoDictionaryOld@@@Z; IASCollection::Initialize(_ITEMTYPE,ISdoCollection *,ISdo *,ISdoMachine *,ISdoDictionaryOld *)
0x180035349  mov     ebx, eax
0x18003534b  test    eax, eax
0x18003534d  jns     loc_1800353EA
0x180035353  lea     rdi, WPP_GLOBAL_Control
0x18003535a  mov     rax, cs:WPP_GLOBAL_Control
0x180035361  cmp     rax, rdi
0x180035364  jz      loc_180035460
0x18003536a  cmp     byte ptr [rax+19h], 2
0x18003536e  jb      short loc_1800353B5
0x180035370  test    dword ptr [rax+1Ch], 400h
0x180035377  jz      short loc_1800353B5
0x180035379  mov     edx, ebx
0x18003537b  lea     rcx, aIascollectionI; "IASCollection::Initialize(IASCONDITION)"...
0x180035382  call    WppDbgPrint
0x180035387  mov     edx, 0Fh
0x18003538c  mov     dword ptr [rsp+48h+var_28], ebx
0x180035390  lea     r9, aNpssdo; "NPSSDO"
0x180035397  lea     r8, WPP_d784a1b6d1803fc8648a97fdfe4f82a5_Traceguids
0x18003539e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800353a5  mov     rcx, [rcx+10h]
0x1800353a9  call    WPP_SF_sd
0x1800353ae  mov     rax, cs:WPP_GLOBAL_Control
0x1800353b5  cmp     rax, rdi
0x1800353b8  jz      loc_180035460
0x1800353be  cmp     byte ptr [rax+19h], 2
0x1800353c2  jb      loc_180035460
0x1800353c8  test    dword ptr [rax+1Ch], 400h
0x1800353cf  jz      loc_180035460
0x1800353d5  mov     edx, ebx
0x1800353d7  lea     rcx, aPconditionsIni; "pConditions->Initialize failed with 0x%"...
0x1800353de  call    WppDbgPrint
0x1800353e3  mov     edx, 27h ; '''
0x1800353e8  jmp     short loc_18003543D
0x1800353ea  mov     rax, [r14]
0x1800353ed  mov     r8, rsi
0x1800353f0  lea     rdx, IID_IIASConditionsCollection
0x1800353f7  mov     rcx, r14
0x1800353fa  mov     rax, [rax]
0x1800353fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035402  mov     ebx, eax
0x180035404  test    eax, eax
0x180035406  jns     short loc_180035460
0x180035408  lea     rdi, WPP_GLOBAL_Control
0x18003540f  mov     rax, cs:WPP_GLOBAL_Control
0x180035416  cmp     rax, rdi
0x180035419  jz      short loc_180035460
0x18003541b  cmp     byte ptr [rax+19h], 2
0x18003541f  jb      short loc_180035460
0x180035421  test    dword ptr [rax+1Ch], 400h
0x180035428  jz      short loc_180035460
0x18003542a  mov     edx, ebx
0x18003542c  lea     rcx, aQiIidIiascondi; "QI(IID_IIASConditionsCollection) failed"...
0x180035433  call    WppDbgPrint
0x180035438  mov     edx, 28h ; '('
0x18003543d  mov     rcx, cs:WPP_GLOBAL_Control
0x180035444  mov     dword ptr [rsp+48h+var_28], ebx
0x180035448  lea     r9, aNpssdo; "NPSSDO"
0x18003544f  lea     r8, WPP_dd21b8743a813b1e52cbedc9bc221252_Traceguids
0x180035456  mov     rcx, [rcx+10h]
0x18003545a  call    WPP_SF_sd
0x18003545f  nop
0x180035460  lea     rcx, [rsp+48h+arg_0]
0x180035465  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003546a  mov     eax, ebx
0x18003546c  mov     rbx, [rsp+48h+arg_10]
0x180035471  add     rsp, 30h
0x180035475  pop     r14
0x180035477  pop     rdi
0x180035478  pop     rsi
0x180035479  retn
```
