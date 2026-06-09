# IASSDOHelper::GetAttributeValueEnumerations(_ATTRIBUTEID,tagVARIANT *,tagVARIANT *,tagVARIANT *)

- ea: `0x18002d420`
- end: `0x18002d6ef`
- name: `?GetAttributeValueEnumerations@IASSDOHelper@@UEAAJW4_ATTRIBUTEID@@PEAUtagVARIANT@@11@Z`
- size: `719`
- prototype: `int(IASSDOHelper *__hidden this, enum _ATTRIBUTEID, struct tagVARIANT *, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180024cac`
- `0x180027ee4`
- `0x18002cd00`
- `0x18002d420`
- `0x18002f14c`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002d479`
- `OLEAUT32!__imp_VariantInit` at `0x18002d482`
- `OLEAUT32!__imp_VariantInit` at `0x18002d48b`
- `OLEAUT32!__imp_VariantInit` at `0x18002d479`
- `OLEAUT32!__imp_VariantInit` at `0x18002d482`
- `OLEAUT32!__imp_VariantInit` at `0x18002d48b`

## string_xrefs

- `0x18002d4e2`: `m_pDict->CreateAttribute(%d) failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IASSDOHelper::GetAttributeValueEnumerations(
        IASSDOHelper *this,
        unsigned int a2,
        struct tagVARIANT *a3,
        struct tagVARIANT *a4,
        struct tagVARIANT *pvarg)
{
  struct tagVARIANT *v9; // rdi
  int SdoProperty; // ebx
  int v11; // edx
  __int64 v13[3]; // [rsp+30h] [rbp-18h] BYREF
  struct ISdo *v14; // [rsp+90h] [rbp+48h] BYREF

  v13[0] = 0;
  v14 = 0;
  if ( a3 )
  {
    if ( a4 )
    {
      v9 = pvarg;
      if ( pvarg )
      {
        if ( *((_QWORD *)this + 13) )
        {
          VariantInit(a3);
          VariantInit(a4);
          VariantInit(v9);
          SdoProperty = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 13) + 80LL))(
                          *((_QWORD *)this + 13),
                          a2,
                          v13);
          if ( SdoProperty < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            {
              WppDbgPrint("m_pDict->CreateAttribute(%d) failed with 0x%x");
              WPP_SF_sdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids);
            }
            goto LABEL_32;
          }
          SdoProperty = (**(__int64 (__fastcall ***)(__int64, GUID *, struct ISdo **))v13[0])(v13[0], &IID_ISdo, &v14);
          if ( SdoProperty >= 0 )
          {
            SdoProperty = GetSdoProperty(v14, 0x404u, a3);
            if ( SdoProperty >= 0 )
            {
              a3->vt = 8204;
              SdoProperty = GetSdoProperty(v14, 0x405u, a4);
              if ( SdoProperty >= 0 )
              {
                a4->vt = 8204;
                SdoProperty = GetSdoProperty(v14, 0x411u, v9);
                if ( SdoProperty >= 0 )
                {
                  v9->vt = 8204;
                  goto LABEL_32;
                }
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
                  || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
                {
                  goto LABEL_32;
                }
                WppDbgPrint("GetSdoProperty(PROPERTY_ATTRIBUTE_ENUM_FILTERS) hr=0x%X");
                v11 = 36;
              }
              else
              {
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
                  || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
                {
                  goto LABEL_32;
                }
                WppDbgPrint("GetSdoProperty(PROPERTY_ATTRIBUTE_ENUM_VALUES) hr=0x%X");
                v11 = 35;
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
              {
                goto LABEL_32;
              }
              WppDbgPrint("GetSdoProperty(PROPERTY_ATTRIBUTE_ENUM_NAMES) hr=0x%X");
              v11 = 34;
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
            {
              goto LABEL_32;
            }
            WppDbgPrint("IASAttributesCollection::Add -- QI(ISdo) failed with 0x%x");
            v11 = 33;
          }
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v11,
            (unsigned int)WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids,
            (unsigned int)"NPSSDO",
            SdoProperty);
LABEL_32:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v14);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v13);
          return (unsigned int)SdoProperty;
        }
      }
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v14);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v13);
  return 2147500035LL;
}

```

## disassembly

```asm
0x18002d420  push    rbp
0x18002d422  push    rbx
0x18002d423  push    rsi
0x18002d424  push    rdi
0x18002d425  push    r14
0x18002d427  push    r15
0x18002d429  mov     rbp, rsp
0x18002d42c  sub     rsp, 48h
0x18002d430  mov     rsi, r9
0x18002d433  mov     r14, r8
0x18002d436  mov     r15d, edx
0x18002d439  mov     rbx, rcx
0x18002d43c  mov     [rbp+var_18], 0
0x18002d444  mov     [rbp+arg_10], 0
0x18002d44c  test    r8, r8
0x18002d44f  jz      loc_18002D6CB
0x18002d455  test    r9, r9
0x18002d458  jz      loc_18002D6CB
0x18002d45e  mov     rdi, [rbp+pvarg]
0x18002d462  test    rdi, rdi
0x18002d465  jz      loc_18002D6CB
0x18002d46b  cmp     qword ptr [rcx+68h], 0
0x18002d470  jz      loc_18002D6CB
0x18002d476  mov     rcx, r8; pvarg
0x18002d479  call    cs:__imp_VariantInit
0x18002d47f  mov     rcx, rsi; pvarg
0x18002d482  call    cs:__imp_VariantInit
0x18002d488  mov     rcx, rdi; pvarg
0x18002d48b  call    cs:__imp_VariantInit
0x18002d491  mov     rcx, [rbx+68h]
0x18002d495  mov     rax, [rcx]
0x18002d498  lea     r8, [rbp+var_18]
0x18002d49c  mov     edx, r15d
0x18002d49f  mov     rax, [rax+50h]
0x18002d4a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4a8  mov     ebx, eax
0x18002d4aa  test    eax, eax
0x18002d4ac  jns     short loc_18002D518
0x18002d4ae  lea     rax, WPP_GLOBAL_Control
0x18002d4b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d4bc  cmp     rcx, rax
0x18002d4bf  jz      loc_18002D6B5
0x18002d4c5  cmp     byte ptr [rcx+19h], 2
0x18002d4c9  jb      loc_18002D6B5
0x18002d4cf  test    dword ptr [rcx+1Ch], 400h
0x18002d4d6  jz      loc_18002D6B5
0x18002d4dc  mov     r8d, ebx
0x18002d4df  mov     edx, r15d
0x18002d4e2  lea     rcx, aMPdictCreateat; "m_pDict->CreateAttribute(%d) failed wit"...
0x18002d4e9  call    WppDbgPrint
0x18002d4ee  mov     edx, 20h ; ' '
0x18002d4f3  mov     [rsp+48h+var_20], ebx
0x18002d4f7  mov     [rsp+48h+var_28], r15d
0x18002d4fc  lea     r8, WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids
0x18002d503  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d50a  mov     rcx, [rcx+10h]
0x18002d50e  call    WPP_SF_sdD
0x18002d513  jmp     loc_18002D6B5
0x18002d518  mov     rcx, [rbp+var_18]
0x18002d51c  mov     rax, [rcx]
0x18002d51f  lea     r8, [rbp+arg_10]
0x18002d523  lea     rdx, IID_ISdo
0x18002d52a  mov     rax, [rax]
0x18002d52d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d532  mov     ebx, eax
0x18002d534  test    eax, eax
0x18002d536  jns     short loc_18002D5A0
0x18002d538  lea     rax, WPP_GLOBAL_Control
0x18002d53f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d546  cmp     rcx, rax
0x18002d549  jz      loc_18002D6B5
0x18002d54f  cmp     byte ptr [rcx+19h], 2
0x18002d553  jb      loc_18002D6B5
0x18002d559  test    dword ptr [rcx+1Ch], 400h
0x18002d560  jz      loc_18002D6B5
0x18002d566  mov     edx, ebx
0x18002d568  lea     rcx, aIasattributesc; "IASAttributesCollection::Add -- QI(ISdo"...
0x18002d56f  call    WppDbgPrint
0x18002d574  mov     edx, 21h ; '!'
0x18002d579  mov     [rsp+48h+var_28], ebx
0x18002d57d  lea     r9, aNpssdo; "NPSSDO"
0x18002d584  lea     r8, WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids
0x18002d58b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d592  mov     rcx, [rcx+10h]
0x18002d596  call    WPP_SF_sd
0x18002d59b  jmp     loc_18002D6B5
0x18002d5a0  mov     r8, r14; struct tagVARIANT *
0x18002d5a3  mov     edx, 404h; unsigned int
0x18002d5a8  mov     rcx, [rbp+arg_10]; struct ISdo *
0x18002d5ac  call    ?GetSdoProperty@@YAJPEAUISdo@@KPEAUtagVARIANT@@@Z; GetSdoProperty(ISdo *,ulong,tagVARIANT *)
0x18002d5b1  mov     ebx, eax
0x18002d5b3  test    eax, eax
0x18002d5b5  jns     short loc_18002D5FD
0x18002d5b7  lea     rax, WPP_GLOBAL_Control
0x18002d5be  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d5c5  cmp     rcx, rax
0x18002d5c8  jz      loc_18002D6B5
0x18002d5ce  cmp     byte ptr [rcx+19h], 2
0x18002d5d2  jb      loc_18002D6B5
0x18002d5d8  test    dword ptr [rcx+1Ch], 400h
0x18002d5df  jz      loc_18002D6B5
0x18002d5e5  mov     edx, ebx
0x18002d5e7  lea     rcx, aGetsdoproperty_7; "GetSdoProperty(PROPERTY_ATTRIBUTE_ENUM_"...
0x18002d5ee  call    WppDbgPrint
0x18002d5f3  mov     edx, 22h ; '"'
0x18002d5f8  jmp     loc_18002D579
0x18002d5fd  mov     r15d, 200Ch
0x18002d603  mov     [r14], r15w
0x18002d607  mov     r8, rsi; struct tagVARIANT *
0x18002d60a  mov     edx, 405h; unsigned int
0x18002d60f  mov     rcx, [rbp+arg_10]; struct ISdo *
0x18002d613  call    ?GetSdoProperty@@YAJPEAUISdo@@KPEAUtagVARIANT@@@Z; GetSdoProperty(ISdo *,ulong,tagVARIANT *)
0x18002d618  mov     ebx, eax
0x18002d61a  test    eax, eax
0x18002d61c  jns     short loc_18002D65C
0x18002d61e  lea     rax, WPP_GLOBAL_Control
0x18002d625  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d62c  cmp     rcx, rax
0x18002d62f  jz      loc_18002D6B5
0x18002d635  cmp     byte ptr [rcx+19h], 2
0x18002d639  jb      short loc_18002D6B5
0x18002d63b  test    dword ptr [rcx+1Ch], 400h
0x18002d642  jz      short loc_18002D6B5
0x18002d644  mov     edx, ebx
0x18002d646  lea     rcx, aGetsdoproperty; "GetSdoProperty(PROPERTY_ATTRIBUTE_ENUM_"...
0x18002d64d  call    WppDbgPrint
0x18002d652  mov     edx, 23h ; '#'
0x18002d657  jmp     loc_18002D579
0x18002d65c  mov     [rsi], r15w
0x18002d660  mov     r8, rdi; struct tagVARIANT *
0x18002d663  mov     edx, 411h; unsigned int
0x18002d668  mov     rcx, [rbp+arg_10]; struct ISdo *
0x18002d66c  call    ?GetSdoProperty@@YAJPEAUISdo@@KPEAUtagVARIANT@@@Z; GetSdoProperty(ISdo *,ulong,tagVARIANT *)
0x18002d671  mov     ebx, eax
0x18002d673  test    eax, eax
0x18002d675  jns     short loc_18002D6B1
0x18002d677  lea     rax, WPP_GLOBAL_Control
0x18002d67e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d685  cmp     rcx, rax
0x18002d688  jz      short loc_18002D6B5
0x18002d68a  cmp     byte ptr [rcx+19h], 2
0x18002d68e  jb      short loc_18002D6B5
0x18002d690  test    dword ptr [rcx+1Ch], 400h
0x18002d697  jz      short loc_18002D6B5
0x18002d699  mov     edx, ebx
0x18002d69b  lea     rcx, aGetsdoproperty_1; "GetSdoProperty(PROPERTY_ATTRIBUTE_ENUM_"...
0x18002d6a2  call    WppDbgPrint
0x18002d6a7  mov     edx, 24h ; '$'
0x18002d6ac  jmp     loc_18002D579
0x18002d6b1  mov     [rdi], r15w
0x18002d6b5  lea     rcx, [rbp+arg_10]
0x18002d6b9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002d6be  lea     rcx, [rbp+var_18]
0x18002d6c2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002d6c7  mov     eax, ebx
0x18002d6c9  jmp     short loc_18002D6E2
0x18002d6cb  lea     rcx, [rbp+arg_10]
0x18002d6cf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002d6d4  lea     rcx, [rbp+var_18]
0x18002d6d8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002d6dd  mov     eax, 80004003h
0x18002d6e2  add     rsp, 48h
0x18002d6e6  pop     r15
0x18002d6e8  pop     r14
0x18002d6ea  pop     rdi
0x18002d6eb  pop     rsi
0x18002d6ec  pop     rbx
0x18002d6ed  pop     rbp
0x18002d6ee  retn
```
