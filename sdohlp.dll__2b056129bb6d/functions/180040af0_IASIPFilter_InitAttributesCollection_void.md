# IASIPFilter::InitAttributesCollection(void)

- ea: `0x180040af0`
- end: `0x180040cc8`
- name: `?InitAttributesCollection@IASIPFilter@@AEAAJXZ`
- size: `472`
- prototype: `__int64 __fastcall(IASIPFilter *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180040cd0`

## callees

- `0x180024cac`
- `0x180027e60`
- `0x18002cd00`
- `0x180030814`
- `0x18003420c`
- `0x180040af0`
- `0x180042a80`
- `0x180058010`

## string_xrefs

- `0x180040ba9`: `CreateInstance(IASAttributesCollection) failed with 0x%x, when trying to initialize IP Filter attributes`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IASIPFilter::InitAttributesCollection(struct ISdo **this)
{
  int SdoCollection; // ebx
  int v3; // edx
  struct ISdo *v4; // rax
  struct ISdo *v5; // rdx
  struct ISdo *v6; // r9
  struct ISdoCollection *v7; // r8
  __int64 (__fastcall ***v8)(_QWORD, GUID *, struct ISdo **); // rsi
  struct ISdoCollection *v10; // [rsp+50h] [rbp+8h] BYREF
  __int64 v11; // [rsp+58h] [rbp+10h] BYREF

  v10 = 0;
  v11 = 0;
  SdoCollection = GetSdoCollection(this[4], 0x400u, &v10);
  if ( SdoCollection >= 0 )
  {
    SdoCollection = ATL::CComObject<IASAttributesCollection>::CreateInstance(&v11);
    if ( SdoCollection >= 0 )
    {
      v4 = this[7];
      v5 = this[6];
      v6 = this[5];
      v7 = v10;
      v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct ISdo **))v11;
      *(_DWORD *)(v11 + 128) = 19;
      SdoCollection = IASCollection::Initialize(v8 + 1, 11, v7, v6, v5, v4);
      if ( SdoCollection >= 0 )
      {
        SdoCollection = (**v8)(v8, &IID_IIASAttributesCollection, this + 15);
        if ( SdoCollection < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("QI(IID_IIASAttributesCollection) failed with 0x%x, when trying to initialize IP Filter attributes");
          v3 = 14;
          goto LABEL_21;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("pAttributes->Initialize failed with 0x%x, when trying to initialize IP Filter attributes");
        v3 = 13;
        goto LABEL_21;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("CreateInstance(IASAttributesCollection) failed with 0x%x, when trying to initialize IP Filter attributes");
      v3 = 12;
      goto LABEL_21;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("GetSdoCollection(PROPERTY_IPFILTER_ATTRIBUTES_COLLECTION) failed with 0x%x");
    v3 = 11;
LABEL_21:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      (unsigned int)WPP_2df12cdf81bf360e3d7ad639b5f29067_Traceguids,
      (unsigned int)"NPSSDO",
      SdoCollection);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v10);
  return (unsigned int)SdoCollection;
}

```

## disassembly

```asm
0x180040af0  mov     rax, rsp
0x180040af3  mov     [rax+18h], rbx
0x180040af7  push    rbp
0x180040af8  push    rsi
0x180040af9  push    rdi
0x180040afa  sub     rsp, 30h
0x180040afe  mov     rdi, rcx
0x180040b01  mov     qword ptr [rax+8], 0
0x180040b09  mov     qword ptr [rax+10h], 0
0x180040b11  lea     r8, [rax+8]; struct ISdoCollection **
0x180040b15  mov     ebp, 400h
0x180040b1a  mov     edx, ebp; unsigned int
0x180040b1c  mov     rcx, [rcx+20h]; struct ISdo *
0x180040b20  call    ?GetSdoCollection@@YAJPEAUISdo@@KPEAPEAUISdoCollection@@@Z; GetSdoCollection(ISdo *,ulong,ISdoCollection * *)
0x180040b25  mov     ebx, eax
0x180040b27  test    eax, eax
0x180040b29  jns     short loc_180040B6D
0x180040b2b  lea     rax, WPP_GLOBAL_Control
0x180040b32  mov     rcx, cs:WPP_GLOBAL_Control
0x180040b39  cmp     rcx, rax
0x180040b3c  jz      loc_180040CAF
0x180040b42  cmp     byte ptr [rcx+19h], 2
0x180040b46  jb      loc_180040CAF
0x180040b4c  test    [rcx+1Ch], ebp
0x180040b4f  jz      loc_180040CAF
0x180040b55  mov     edx, ebx
0x180040b57  lea     rcx, aGetsdocollecti_4; "GetSdoCollection(PROPERTY_IPFILTER_ATTR"...
0x180040b5e  call    WppDbgPrint
0x180040b63  mov     edx, 0Bh
0x180040b68  jmp     loc_180040C8C
0x180040b6d  lea     rcx, [rsp+48h+arg_8]
0x180040b72  call    ?CreateInstance@?$CComObject@VIASAttributesCollection@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<IASAttributesCollection>::CreateInstance(ATL::CComObject<IASAttributesCollection> * *)
0x180040b77  mov     ebx, eax
0x180040b79  test    eax, eax
0x180040b7b  jns     short loc_180040BBF
0x180040b7d  lea     rax, WPP_GLOBAL_Control
0x180040b84  mov     rcx, cs:WPP_GLOBAL_Control
0x180040b8b  cmp     rcx, rax
0x180040b8e  jz      loc_180040CAF
0x180040b94  cmp     byte ptr [rcx+19h], 2
0x180040b98  jb      loc_180040CAF
0x180040b9e  test    [rcx+1Ch], ebp
0x180040ba1  jz      loc_180040CAF
0x180040ba7  mov     edx, ebx
0x180040ba9  lea     rcx, aCreateinstance_12; "CreateInstance(IASAttributesCollection)"...
0x180040bb0  call    WppDbgPrint
0x180040bb5  mov     edx, 0Ch
0x180040bba  jmp     loc_180040C8C
0x180040bbf  mov     rax, [rdi+38h]
0x180040bc3  mov     rdx, [rdi+30h]
0x180040bc7  mov     r9, [rdi+28h]
0x180040bcb  mov     r8, [rsp+48h+arg_0]
0x180040bd0  mov     rsi, [rsp+48h+arg_8]
0x180040bd5  mov     dword ptr [rsi+80h], 13h
0x180040bdf  lea     rcx, [rsi+8]
0x180040be3  mov     [rsp+48h+var_20], rax
0x180040be8  mov     [rsp+48h+var_28], rdx
0x180040bed  mov     edx, 0Bh
0x180040bf2  call    ?Initialize@IASCollection@@QEAAJW4_ITEMTYPE@@PEAUISdoCollection@@PEAUISdo@@PEAUISdoMachine@@PEAUISdoDictionaryOld@@@Z; IASCollection::Initialize(_ITEMTYPE,ISdoCollection *,ISdo *,ISdoMachine *,ISdoDictionaryOld *)
0x180040bf7  mov     ebx, eax
0x180040bf9  test    eax, eax
0x180040bfb  jns     short loc_180040C3C
0x180040bfd  lea     rax, WPP_GLOBAL_Control
0x180040c04  mov     rcx, cs:WPP_GLOBAL_Control
0x180040c0b  cmp     rcx, rax
0x180040c0e  jz      loc_180040CAF
0x180040c14  cmp     byte ptr [rcx+19h], 2
0x180040c18  jb      loc_180040CAF
0x180040c1e  test    [rcx+1Ch], ebp
0x180040c21  jz      loc_180040CAF
0x180040c27  mov     edx, ebx
0x180040c29  lea     rcx, aPattributesIni; "pAttributes->Initialize failed with 0x%"...
0x180040c30  call    WppDbgPrint
0x180040c35  mov     edx, 0Dh
0x180040c3a  jmp     short loc_180040C8C
0x180040c3c  mov     rax, [rsi]
0x180040c3f  lea     r8, [rdi+78h]
0x180040c43  lea     rdx, IID_IIASAttributesCollection
0x180040c4a  mov     rcx, rsi
0x180040c4d  mov     rax, [rax]
0x180040c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c55  mov     ebx, eax
0x180040c57  test    eax, eax
0x180040c59  jns     short loc_180040CAF
0x180040c5b  lea     rax, WPP_GLOBAL_Control
0x180040c62  mov     rcx, cs:WPP_GLOBAL_Control
0x180040c69  cmp     rcx, rax
0x180040c6c  jz      short loc_180040CAF
0x180040c6e  cmp     byte ptr [rcx+19h], 2
0x180040c72  jb      short loc_180040CAF
0x180040c74  test    [rcx+1Ch], ebp
0x180040c77  jz      short loc_180040CAF
0x180040c79  mov     edx, ebx
0x180040c7b  lea     rcx, aQiIidIiasattri; "QI(IID_IIASAttributesCollection) failed"...
0x180040c82  call    WppDbgPrint
0x180040c87  mov     edx, 0Eh
0x180040c8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180040c93  mov     dword ptr [rsp+48h+var_28], ebx
0x180040c97  lea     r9, aNpssdo; "NPSSDO"
0x180040c9e  lea     r8, WPP_2df12cdf81bf360e3d7ad639b5f29067_Traceguids
0x180040ca5  mov     rcx, [rcx+10h]
0x180040ca9  call    WPP_SF_sd
0x180040cae  nop
0x180040caf  lea     rcx, [rsp+48h+arg_0]
0x180040cb4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180040cb9  mov     eax, ebx
0x180040cbb  mov     rbx, [rsp+48h+arg_10]
0x180040cc0  add     rsp, 30h
0x180040cc4  pop     rdi
0x180040cc5  pop     rsi
0x180040cc6  pop     rbp
0x180040cc7  retn
```
