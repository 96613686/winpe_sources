# IASPolicy::InitProfileAttributesCollection(void)

- ea: `0x180035480`
- end: `0x1800356f3`
- name: `?InitProfileAttributesCollection@IASPolicy@@AEAAJXZ`
- size: `627`
- prototype: `__int64 __fastcall(IASPolicy *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800356fc`

## callees

- `0x180024cac`
- `0x180027e60`
- `0x18002cd00`
- `0x180030814`
- `0x18003420c`
- `0x180034f44`
- `0x180035480`
- `0x180042a80`
- `0x180058010`

## string_xrefs

- `0x1800355c8`: `CreateInstance(IASAttributesCollection) failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IASPolicy::InitProfileAttributesCollection(IASPolicy *this)
{
  _QWORD *v2; // r14
  __int64 v3; // rcx
  int SdoCollection; // ebx
  int v5; // edx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  struct ISdoCollection *v9; // r10
  __int64 (__fastcall ***v10)(_QWORD, GUID *, _QWORD *); // r15
  struct ISdoCollection *v12; // [rsp+60h] [rbp+8h] BYREF
  __int64 v13; // [rsp+68h] [rbp+10h] BYREF
  __int64 v14; // [rsp+70h] [rbp+18h] BYREF

  v14 = 0;
  v12 = 0;
  v2 = (_QWORD *)((char *)this + 144);
  v3 = *((_QWORD *)this + 18);
  if ( v3 )
  {
    *v2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  if ( *((_QWORD *)this + 16) || (SdoCollection = IASPolicy::GetProfileObject(this), SdoCollection >= 0) )
  {
    SdoCollection = GetSdoCollection(*((struct ISdo **)this + 16), 0x400u, &v12);
    if ( SdoCollection >= 0 )
    {
      v13 = 0;
      SdoCollection = ATL::CComObject<IASAttributesCollection>::CreateInstance(&v13);
      if ( SdoCollection >= 0 )
      {
        v6 = *((_QWORD *)this + 7);
        v7 = *((_QWORD *)this + 6);
        v8 = *((_QWORD *)this + 5);
        v9 = v12;
        v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))v13;
        *(_DWORD *)(v13 + 128) = *((_DWORD *)this + 30);
        SdoCollection = IASCollection::Initialize(v10 + 1, 11, v9, v8, v7, v6);
        if ( SdoCollection >= 0 )
        {
          SdoCollection = (**v10)(v10, &IID_IIASAttributesCollection, v2);
          if ( SdoCollection < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("QI(IID_IIASAttributesCollection) failed with 0x%x");
            v5 = 46;
            goto LABEL_29;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
               && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("pAttributes->Initialize failed with 0x%x");
          v5 = 45;
          goto LABEL_29;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("CreateInstance(IASAttributesCollection) failed with 0x%x");
        v5 = 44;
        goto LABEL_29;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("GetSdoCollection(PROPERTY_PROFILE_ATTRIBUTES_COLLECTION) failed with 0x%x");
      v5 = 43;
      goto LABEL_29;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("GetProfileObject failed with 0x%x");
    v5 = 42;
LABEL_29:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)WPP_dd21b8743a813b1e52cbedc9bc221252_Traceguids,
      (unsigned int)"NPSSDO",
      SdoCollection);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
  return (unsigned int)SdoCollection;
}

```

## disassembly

```asm
0x180035480  push    rbx
0x180035482  push    rsi
0x180035483  push    rdi
0x180035484  push    r14
0x180035486  push    r15
0x180035488  sub     rsp, 30h
0x18003548c  mov     rsi, rcx
0x18003548f  mov     [rsp+58h+arg_10], 0
0x180035498  mov     [rsp+58h+arg_0], 0
0x1800354a1  lea     r14, [rcx+90h]
0x1800354a8  mov     rcx, [r14]
0x1800354ab  test    rcx, rcx
0x1800354ae  jz      short loc_1800354C4
0x1800354b0  mov     qword ptr [r14], 0
0x1800354b7  mov     rax, [rcx]
0x1800354ba  mov     rax, [rax+10h]
0x1800354be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800354c3  nop
0x1800354c4  cmp     qword ptr [rsi+80h], 0
0x1800354cc  jnz     short loc_180035523
0x1800354ce  mov     rcx, rsi; this
0x1800354d1  call    ?GetProfileObject@IASPolicy@@QEAAJXZ; IASPolicy::GetProfileObject(void)
0x1800354d6  mov     ebx, eax
0x1800354d8  test    eax, eax
0x1800354da  jns     short loc_180035523
0x1800354dc  lea     rax, WPP_GLOBAL_Control
0x1800354e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800354ea  cmp     rcx, rax
0x1800354ed  jz      loc_1800356D0
0x1800354f3  cmp     byte ptr [rcx+19h], 2
0x1800354f7  jb      loc_1800356D0
0x1800354fd  mov     edi, 400h
0x180035502  test    [rcx+1Ch], edi
0x180035505  jz      loc_1800356D0
0x18003550b  mov     edx, ebx
0x18003550d  lea     rcx, aGetprofileobje; "GetProfileObject failed with 0x%x"
0x180035514  call    WppDbgPrint
0x180035519  mov     edx, 2Ah ; '*'
0x18003551e  jmp     loc_1800356AD
0x180035523  lea     r8, [rsp+58h+arg_0]; struct ISdoCollection **
0x180035528  mov     edi, 400h
0x18003552d  mov     edx, edi; unsigned int
0x18003552f  mov     rcx, [rsi+80h]; struct ISdo *
0x180035536  call    ?GetSdoCollection@@YAJPEAUISdo@@KPEAPEAUISdoCollection@@@Z; GetSdoCollection(ISdo *,ulong,ISdoCollection * *)
0x18003553b  mov     ebx, eax
0x18003553d  test    eax, eax
0x18003553f  jns     short loc_180035583
0x180035541  lea     rax, WPP_GLOBAL_Control
0x180035548  mov     rcx, cs:WPP_GLOBAL_Control
0x18003554f  cmp     rcx, rax
0x180035552  jz      loc_1800356D0
0x180035558  cmp     byte ptr [rcx+19h], 2
0x18003555c  jb      loc_1800356D0
0x180035562  test    [rcx+1Ch], edi
0x180035565  jz      loc_1800356D0
0x18003556b  mov     edx, ebx
0x18003556d  lea     rcx, aGetsdocollecti_2; "GetSdoCollection(PROPERTY_PROFILE_ATTRI"...
0x180035574  call    WppDbgPrint
0x180035579  mov     edx, 2Bh ; '+'
0x18003557e  jmp     loc_1800356AD
0x180035583  mov     [rsp+58h+arg_8], 0
0x18003558c  lea     rcx, [rsp+58h+arg_8]
0x180035591  call    ?CreateInstance@?$CComObject@VIASAttributesCollection@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<IASAttributesCollection>::CreateInstance(ATL::CComObject<IASAttributesCollection> * *)
0x180035596  mov     ebx, eax
0x180035598  test    eax, eax
0x18003559a  jns     short loc_1800355DE
0x18003559c  lea     rax, WPP_GLOBAL_Control
0x1800355a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800355aa  cmp     rcx, rax
0x1800355ad  jz      loc_1800356D0
0x1800355b3  cmp     byte ptr [rcx+19h], 2
0x1800355b7  jb      loc_1800356D0
0x1800355bd  test    [rcx+1Ch], edi
0x1800355c0  jz      loc_1800356D0
0x1800355c6  mov     edx, ebx
0x1800355c8  lea     rcx, aCreateinstance_8; "CreateInstance(IASAttributesCollection)"...
0x1800355cf  call    WppDbgPrint
0x1800355d4  mov     edx, 2Ch ; ','
0x1800355d9  jmp     loc_1800356AD
0x1800355de  mov     rdx, [rsi+38h]
0x1800355e2  mov     r8, [rsi+30h]
0x1800355e6  mov     r9, [rsi+28h]
0x1800355ea  mov     r10, [rsp+58h+arg_0]
0x1800355ef  mov     r15, [rsp+58h+arg_8]
0x1800355f4  mov     eax, [rsi+78h]
0x1800355f7  mov     [r15+80h], eax
0x1800355fe  lea     rcx, [r15+8]
0x180035602  mov     [rsp+58h+var_30], rdx
0x180035607  mov     [rsp+58h+var_38], r8
0x18003560c  mov     r8, r10
0x18003560f  mov     edx, 0Bh
0x180035614  call    ?Initialize@IASCollection@@QEAAJW4_ITEMTYPE@@PEAUISdoCollection@@PEAUISdo@@PEAUISdoMachine@@PEAUISdoDictionaryOld@@@Z; IASCollection::Initialize(_ITEMTYPE,ISdoCollection *,ISdo *,ISdoMachine *,ISdoDictionaryOld *)
0x180035619  mov     ebx, eax
0x18003561b  test    eax, eax
0x18003561d  jns     short loc_18003565E
0x18003561f  lea     rax, WPP_GLOBAL_Control
0x180035626  mov     rcx, cs:WPP_GLOBAL_Control
0x18003562d  cmp     rcx, rax
0x180035630  jz      loc_1800356D0
0x180035636  cmp     byte ptr [rcx+19h], 2
0x18003563a  jb      loc_1800356D0
0x180035640  test    [rcx+1Ch], edi
0x180035643  jz      loc_1800356D0
0x180035649  mov     edx, ebx
0x18003564b  lea     rcx, aPattributesIni_0; "pAttributes->Initialize failed with 0x%"...
0x180035652  call    WppDbgPrint
0x180035657  mov     edx, 2Dh ; '-'
0x18003565c  jmp     short loc_1800356AD
0x18003565e  mov     rax, [r15]
0x180035661  mov     r8, r14
0x180035664  lea     rdx, IID_IIASAttributesCollection
0x18003566b  mov     rcx, r15
0x18003566e  mov     rax, [rax]
0x180035671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035676  mov     ebx, eax
0x180035678  test    eax, eax
0x18003567a  jns     short loc_1800356D0
0x18003567c  lea     rax, WPP_GLOBAL_Control
0x180035683  mov     rcx, cs:WPP_GLOBAL_Control
0x18003568a  cmp     rcx, rax
0x18003568d  jz      short loc_1800356D0
0x18003568f  cmp     byte ptr [rcx+19h], 2
0x180035693  jb      short loc_1800356D0
0x180035695  test    [rcx+1Ch], edi
0x180035698  jz      short loc_1800356D0
0x18003569a  mov     edx, ebx
0x18003569c  lea     rcx, aQiIidIiasattri_0; "QI(IID_IIASAttributesCollection) failed"...
0x1800356a3  call    WppDbgPrint
0x1800356a8  mov     edx, 2Eh ; '.'
0x1800356ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800356b4  mov     dword ptr [rsp+58h+var_38], ebx
0x1800356b8  lea     r9, aNpssdo; "NPSSDO"
0x1800356bf  lea     r8, WPP_dd21b8743a813b1e52cbedc9bc221252_Traceguids
0x1800356c6  mov     rcx, [rcx+10h]
0x1800356ca  call    WPP_SF_sd
0x1800356cf  nop
0x1800356d0  lea     rcx, [rsp+58h+arg_0]
0x1800356d5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800356da  nop
0x1800356db  lea     rcx, [rsp+58h+arg_10]
0x1800356e0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800356e5  mov     eax, ebx
0x1800356e7  add     rsp, 30h
0x1800356eb  pop     r15
0x1800356ed  pop     r14
0x1800356ef  pop     rdi
0x1800356f0  pop     rsi
0x1800356f1  pop     rbx
0x1800356f2  retn
```
