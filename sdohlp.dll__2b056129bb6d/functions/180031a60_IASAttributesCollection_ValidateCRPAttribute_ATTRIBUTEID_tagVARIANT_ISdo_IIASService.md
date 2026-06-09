# IASAttributesCollection::ValidateCRPAttribute(_ATTRIBUTEID,tagVARIANT,ISdo *,IIASService *)

- ea: `0x180031a60`
- end: `0x180031e9f`
- name: `?ValidateCRPAttribute@IASAttributesCollection@@QEAAJW4_ATTRIBUTEID@@UtagVARIANT@@PEAUISdo@@PEAUIIASService@@@Z`
- size: `1087`
- prototype: `int(IASAttributesCollection *__hidden this, enum _ATTRIBUTEID, struct tagVARIANT *__struct_ptr, struct ISdo *, struct IIASService *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800317ec`

## callees

- `0x180024cac`
- `0x18002cca4`
- `0x18002cd00`
- `0x18003172c`
- `0x180031a60`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180031dc3`
- `msvcrt!_wcsicmp` at `0x180031dc3`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180031cca`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180031cca`

## string_xrefs

- `0x180031c83`: `pService->get_RemoteServers returned 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IASAttributesCollection::ValidateCRPAttribute(
        const wchar_t *this,
        enum _ATTRIBUTEID a2,
        struct tagVARIANT *a3,
        struct ISdo *a4,
        struct IIASService *a5)
{
  HRESULT Element; // ebx
  unsigned int i; // ecx
  int v9; // edx
  SAFEARRAY *parray; // rcx
  int v11; // edx
  char v12; // si
  __int64 v14; // [rsp+30h] [rbp-28h] BYREF
  __int64 v15; // [rsp+38h] [rbp-20h] BYREF
  __int64 v16; // [rsp+40h] [rbp-18h] BYREF
  const wchar_t *pv; // [rsp+48h] [rbp-10h] BYREF
  const wchar_t *rgIndices; // [rsp+80h] [rbp+28h] BYREF

  rgIndices = this;
  Element = 0;
  LOBYTE(rgIndices) = 0;
  for ( i = 0; i < 0xA; ++i )
  {
    if ( a2 == *((_DWORD *)&CRPAttributes + (int)i) )
      goto LABEL_17;
  }
  Element = IsAttributeAllowed(a4, 0x40Du, (bool *)&rgIndices);
  if ( Element < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("IsAttributeAllowed failed with 0x%x");
      v9 = 20;
LABEL_10:
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        (unsigned int)WPP_4b583fe665f33bdd9967a3ff271ecbd4_Traceguids,
        (unsigned int)"NPSSDO",
        Element);
      return (unsigned int)Element;
    }
    return (unsigned int)Element;
  }
  if ( !(_BYTE)rgIndices )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("Attribute 0x%x not allowed in profile");
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        (unsigned int)WPP_4b583fe665f33bdd9967a3ff271ecbd4_Traceguids,
        (unsigned int)"NPSSDO",
        a2);
    }
    return (unsigned int)-2147024809;
  }
LABEL_17:
  if ( a2 != IAS_ATTRIBUTE_AUTH_PROVIDER_NAME && a2 != IAS_ATTRIBUTE_ACCT_PROVIDER_NAME )
    return (unsigned int)Element;
  if ( ((a3->vt - 8) & 0xDFFF) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("Unexpected attribute data type");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_4b583fe665f33bdd9967a3ff271ecbd4_Traceguids, "NPSSDO");
    }
    return (unsigned int)-2147418113;
  }
  pv = 0;
  parray = a3->parray;
  if ( a3->vt == 8 )
  {
    pv = a3->bstrVal;
    goto LABEL_27;
  }
  LODWORD(rgIndices) = 0;
  Element = SafeArrayGetElement(parray, (LONG *)&rgIndices, &pv);
  if ( Element >= 0 )
  {
LABEL_27:
    v16 = 0;
    v15 = 0;
    v14 = 0;
    Element = (*(__int64 (__fastcall **)(struct IIASService *, __int64 *, struct tagVARIANT *, struct ISdo *))(*(_QWORD *)a5 + 216LL))(
                a5,
                &v16,
                a3,
                a4);
    if ( Element >= 0 )
    {
      Element = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 80LL))(v16, &v15);
      if ( Element >= 0 )
      {
        v12 = 0;
        while ( 1 )
        {
          Element = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 64LL))(v15, &v14);
          if ( Element )
            break;
          rgIndices = 0;
          Element = (*(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v14 + 96LL))(v14, &rgIndices);
          if ( !_wcsicmp(rgIndices, pv) )
          {
            v12 = 1;
            break;
          }
        }
        if ( Element >= 0 )
        {
          if ( !v12 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            {
              WppDbgPrint("Cannot add attribute %d as there is no matching server group");
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                27,
                (unsigned int)WPP_4b583fe665f33bdd9967a3ff271ecbd4_Traceguids,
                (unsigned int)"NPSSDO",
                a2);
            }
            Element = -2147024809;
          }
          goto LABEL_58;
        }
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        {
LABEL_58:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
          return (unsigned int)Element;
        }
        WppDbgPrint("pEnum->GetNextItem returned 0x%x");
        v11 = 26;
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        {
          goto LABEL_58;
        }
        WppDbgPrint("pColl->get_Enumerator returned 0x%x");
        v11 = 25;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      {
        goto LABEL_58;
      }
      WppDbgPrint("pService->get_RemoteServers returned 0x%x");
      v11 = 24;
    }
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      (unsigned int)WPP_4b583fe665f33bdd9967a3ff271ecbd4_Traceguids,
      (unsigned int)"NPSSDO",
      Element);
    goto LABEL_58;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("SafeArrayGetElement(psaRemoteServer)  failed with 0x%x");
    v9 = 23;
    goto LABEL_10;
  }
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x180031a60  mov     [rsp-20h+rgIndices], rcx
0x180031a65  push    rbp
0x180031a66  push    rbx
0x180031a67  push    rsi
0x180031a68  push    rdi
0x180031a69  mov     rbp, rsp
0x180031a6c  sub     rsp, 58h
0x180031a70  mov     rsi, r8
0x180031a73  mov     edi, edx
0x180031a75  xor     ebx, ebx
0x180031a77  mov     byte ptr [rbp+rgIndices], bl
0x180031a7a  xor     ecx, ecx
0x180031a7c  cmp     ecx, 0Ah
0x180031a7f  jnb     short loc_180031A98
0x180031a81  movsxd  rax, ecx
0x180031a84  lea     rdx, ?CRPAttributes@@3PAW4_ATTRIBUTEID@@A; _ATTRIBUTEID near * CRPAttributes
0x180031a8b  cmp     edi, [rdx+rax*4]
0x180031a8e  jz      loc_180031B7E
0x180031a94  inc     ecx
0x180031a96  jmp     short loc_180031A7C
0x180031a98  lea     r8, [rbp+rgIndices]; bool *
0x180031a9c  mov     edx, 40Dh; unsigned int
0x180031aa1  mov     rcx, r9; struct ISdo *
0x180031aa4  call    ?IsAttributeAllowed@@YAJPEAUISdo@@KPEA_N@Z; IsAttributeAllowed(ISdo *,ulong,bool *)
0x180031aa9  mov     ebx, eax
0x180031aab  test    eax, eax
0x180031aad  jns     short loc_180031B17
0x180031aaf  lea     rax, WPP_GLOBAL_Control
0x180031ab6  mov     rcx, cs:WPP_GLOBAL_Control
0x180031abd  cmp     rcx, rax
0x180031ac0  jz      loc_180031E94
0x180031ac6  cmp     byte ptr [rcx+19h], 2
0x180031aca  jb      loc_180031E94
0x180031ad0  test    dword ptr [rcx+1Ch], 400h
0x180031ad7  jz      loc_180031E94
0x180031add  mov     edx, ebx
0x180031adf  lea     rcx, aIsattributeall; "IsAttributeAllowed failed with 0x%x"
0x180031ae6  call    WppDbgPrint
0x180031aeb  mov     edx, 14h
0x180031af0  mov     [rsp+58h+var_38], ebx
0x180031af4  lea     r9, aNpssdo; "NPSSDO"
0x180031afb  lea     r8, WPP_4b583fe665f33bdd9967a3ff271ecbd4_Traceguids
0x180031b02  mov     rcx, cs:WPP_GLOBAL_Control
0x180031b09  mov     rcx, [rcx+10h]
0x180031b0d  call    WPP_SF_sd
0x180031b12  jmp     loc_180031E94
0x180031b17  cmp     byte ptr [rbp+rgIndices], 0
0x180031b1b  jnz     short loc_180031B7E
0x180031b1d  lea     rax, WPP_GLOBAL_Control
0x180031b24  mov     rcx, cs:WPP_GLOBAL_Control
0x180031b2b  cmp     rcx, rax
0x180031b2e  jz      short loc_180031B74
0x180031b30  cmp     byte ptr [rcx+19h], 2
0x180031b34  jb      short loc_180031B74
0x180031b36  test    dword ptr [rcx+1Ch], 400h
0x180031b3d  jz      short loc_180031B74
0x180031b3f  mov     edx, edi
0x180031b41  lea     rcx, aAttribute0xXNo_0; "Attribute 0x%x not allowed in profile"
0x180031b48  call    WppDbgPrint
0x180031b4d  mov     edx, 15h
0x180031b52  mov     [rsp+58h+var_38], edi
0x180031b56  lea     r9, aNpssdo; "NPSSDO"
0x180031b5d  lea     r8, WPP_4b583fe665f33bdd9967a3ff271ecbd4_Traceguids
0x180031b64  mov     rcx, cs:WPP_GLOBAL_Control
0x180031b6b  mov     rcx, [rcx+10h]
0x180031b6f  call    WPP_SF_sd
0x180031b74  mov     ebx, 80070057h
0x180031b79  jmp     loc_180031E94
0x180031b7e  mov     ecx, edi
0x180031b80  sub     ecx, 1029h
0x180031b86  jz      short loc_180031B91
0x180031b88  cmp     ecx, 2
0x180031b8b  jnz     loc_180031E94
0x180031b91  movzx   eax, word ptr [rsi]
0x180031b94  mov     edx, 8
0x180031b99  sub     ax, dx
0x180031b9c  mov     ecx, 0DFFFh
0x180031ba1  test    cx, ax
0x180031ba4  jz      short loc_180031C01
0x180031ba6  lea     rax, WPP_GLOBAL_Control
0x180031bad  mov     rcx, cs:WPP_GLOBAL_Control
0x180031bb4  cmp     rcx, rax
0x180031bb7  jz      short loc_180031BF7
0x180031bb9  cmp     byte ptr [rcx+19h], 2
0x180031bbd  jb      short loc_180031BF7
0x180031bbf  test    dword ptr [rcx+1Ch], 400h
0x180031bc6  jz      short loc_180031BF7
0x180031bc8  lea     rcx, aUnexpectedAttr; "Unexpected attribute data type"
0x180031bcf  call    WppDbgPrint
0x180031bd4  mov     edx, 16h
0x180031bd9  lea     r9, aNpssdo; "NPSSDO"
0x180031be0  lea     r8, WPP_4b583fe665f33bdd9967a3ff271ecbd4_Traceguids
0x180031be7  mov     rcx, cs:WPP_GLOBAL_Control
0x180031bee  mov     rcx, [rcx+10h]
0x180031bf2  call    WPP_SF_s
0x180031bf7  mov     ebx, 8000FFFFh
0x180031bfc  jmp     loc_180031E94
0x180031c01  mov     [rbp+pv], 0
0x180031c09  mov     rcx, [rsi+8]; psa
0x180031c0d  cmp     dx, [rsi]
0x180031c10  jnz     loc_180031CBB
0x180031c16  mov     [rbp+pv], rcx
0x180031c1a  mov     [rbp+var_18], 0
0x180031c22  mov     [rbp+var_20], 0
0x180031c2a  mov     [rbp+var_28], 0
0x180031c32  mov     rcx, [rbp+arg_20]
0x180031c36  mov     rax, [rcx]
0x180031c39  lea     rdx, [rbp+var_18]
0x180031c3d  mov     rax, [rax+0D8h]
0x180031c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c49  mov     ebx, eax
0x180031c4b  test    eax, eax
0x180031c4d  jns     loc_180031D20
0x180031c53  lea     rax, WPP_GLOBAL_Control
0x180031c5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180031c61  cmp     rcx, rax
0x180031c64  jz      loc_180031E77
0x180031c6a  cmp     byte ptr [rcx+19h], 2
0x180031c6e  jb      loc_180031E77
0x180031c74  test    dword ptr [rcx+1Ch], 400h
0x180031c7b  jz      loc_180031E77
0x180031c81  mov     edx, ebx
0x180031c83  lea     rcx, aPserviceGetRem; "pService->get_RemoteServers returned 0x"...
0x180031c8a  call    WppDbgPrint
0x180031c8f  mov     edx, 18h
0x180031c94  mov     [rsp+58h+var_38], ebx
0x180031c98  lea     r9, aNpssdo; "NPSSDO"
0x180031c9f  lea     r8, WPP_4b583fe665f33bdd9967a3ff271ecbd4_Traceguids
0x180031ca6  mov     rcx, cs:WPP_GLOBAL_Control
0x180031cad  mov     rcx, [rcx+10h]
0x180031cb1  call    WPP_SF_sd
0x180031cb6  jmp     loc_180031E77
0x180031cbb  mov     dword ptr [rbp+rgIndices], 0
0x180031cc2  lea     r8, [rbp+pv]; pv
0x180031cc6  lea     rdx, [rbp+rgIndices]; rgIndices
0x180031cca  call    cs:__imp_SafeArrayGetElement
0x180031cd0  mov     ebx, eax
0x180031cd2  test    eax, eax
0x180031cd4  jns     loc_180031C1A
0x180031cda  lea     rax, WPP_GLOBAL_Control
0x180031ce1  mov     rcx, cs:WPP_GLOBAL_Control
0x180031ce8  cmp     rcx, rax
0x180031ceb  jz      loc_180031E94
0x180031cf1  cmp     byte ptr [rcx+19h], 2
0x180031cf5  jb      loc_180031E94
0x180031cfb  test    dword ptr [rcx+1Ch], 400h
0x180031d02  jz      loc_180031E94
0x180031d08  mov     edx, ebx
0x180031d0a  lea     rcx, aSafearraygetel; "SafeArrayGetElement(psaRemoteServer)  f"...
0x180031d11  call    WppDbgPrint
0x180031d16  mov     edx, 17h
0x180031d1b  jmp     loc_180031AF0
0x180031d20  mov     rcx, [rbp+var_18]
0x180031d24  mov     rax, [rcx]
0x180031d27  lea     rdx, [rbp+var_20]
0x180031d2b  mov     rax, [rax+50h]
0x180031d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031d34  mov     ebx, eax
0x180031d36  test    eax, eax
0x180031d38  jns     short loc_180031D80
0x180031d3a  lea     rax, WPP_GLOBAL_Control
0x180031d41  mov     rcx, cs:WPP_GLOBAL_Control
0x180031d48  cmp     rcx, rax
0x180031d4b  jz      loc_180031E77
0x180031d51  cmp     byte ptr [rcx+19h], 2
0x180031d55  jb      loc_180031E77
0x180031d5b  test    dword ptr [rcx+1Ch], 400h
0x180031d62  jz      loc_180031E77
0x180031d68  mov     edx, ebx
0x180031d6a  lea     rcx, aPcollGetEnumer; "pColl->get_Enumerator returned 0x%x"
0x180031d71  call    WppDbgPrint
0x180031d76  mov     edx, 19h
0x180031d7b  jmp     loc_180031C94
0x180031d80  xor     sil, sil
0x180031d83  mov     rcx, [rbp+var_20]
0x180031d87  mov     rax, [rcx]
0x180031d8a  lea     rdx, [rbp+var_28]
0x180031d8e  mov     rax, [rax+40h]
0x180031d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031d97  mov     ebx, eax
0x180031d99  test    eax, eax
0x180031d9b  jnz     short loc_180031DD0
0x180031d9d  mov     [rbp+rgIndices], 0
0x180031da5  mov     rcx, [rbp+var_28]
0x180031da9  mov     rax, [rcx]
0x180031dac  lea     rdx, [rbp+rgIndices]
0x180031db0  mov     rax, [rax+60h]
0x180031db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031db9  mov     ebx, eax
0x180031dbb  mov     rdx, [rbp+pv]; String2
0x180031dbf  mov     rcx, [rbp+rgIndices]; String1
0x180031dc3  call    cs:__imp__wcsicmp
0x180031dc9  test    eax, eax
0x180031dcb  jnz     short loc_180031D83
0x180031dcd  mov     sil, 1
0x180031dd0  test    ebx, ebx
0x180031dd2  jns     short loc_180031E16
0x180031dd4  lea     rax, WPP_GLOBAL_Control
0x180031ddb  mov     rcx, cs:WPP_GLOBAL_Control
0x180031de2  cmp     rcx, rax
0x180031de5  jz      loc_180031E77
0x180031deb  cmp     byte ptr [rcx+19h], 2
0x180031def  jb      loc_180031E77
0x180031df5  test    dword ptr [rcx+1Ch], 400h
0x180031dfc  jz      short loc_180031E77
0x180031dfe  mov     edx, ebx
0x180031e00  lea     rcx, aPenumGetnextit; "pEnum->GetNextItem returned 0x%x"
0x180031e07  call    WppDbgPrint
0x180031e0c  mov     edx, 1Ah
0x180031e11  jmp     loc_180031C94
0x180031e16  test    sil, sil
0x180031e19  jnz     short loc_180031E77
0x180031e1b  lea     rax, WPP_GLOBAL_Control
0x180031e22  mov     rcx, cs:WPP_GLOBAL_Control
0x180031e29  cmp     rcx, rax
0x180031e2c  jz      short loc_180031E72
0x180031e2e  cmp     byte ptr [rcx+19h], 2
0x180031e32  jb      short loc_180031E72
0x180031e34  test    dword ptr [rcx+1Ch], 400h
0x180031e3b  jz      short loc_180031E72
0x180031e3d  mov     edx, edi
0x180031e3f  lea     rcx, aCannotAddAttri; "Cannot add attribute %d as there is no "...
0x180031e46  call    WppDbgPrint
0x180031e4b  mov     edx, 1Bh
0x180031e50  mov     [rsp+58h+var_38], edi
0x180031e54  lea     r9, aNpssdo; "NPSSDO"
0x180031e5b  lea     r8, WPP_4b583fe665f33bdd9967a3ff271ecbd4_Traceguids
0x180031e62  mov     rcx, cs:WPP_GLOBAL_Control
0x180031e69  mov     rcx, [rcx+10h]
0x180031e6d  call    WPP_SF_sd
0x180031e72  mov     ebx, 80070057h
0x180031e77  lea     rcx, [rbp+var_28]
0x180031e7b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180031e80  nop
0x180031e81  lea     rcx, [rbp+var_20]
0x180031e85  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180031e8a  nop
0x180031e8b  lea     rcx, [rbp+var_18]
0x180031e8f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180031e94  mov     eax, ebx
0x180031e96  add     rsp, 58h
0x180031e9a  pop     rdi
0x180031e9b  pop     rsi
0x180031e9c  pop     rbx
0x180031e9d  pop     rbp
0x180031e9e  retn
```
