# CdsUpdateObjectParser::ParseXML(ushort const *,CdsUpdatePropertyCollection *)

- ea: `0x14006706c`
- end: `0x1400672f5`
- name: `?ParseXML@CdsUpdateObjectParser@@AEAAJPEBGPEAVCdsUpdatePropertyCollection@@@Z`
- size: `649`
- prototype: `__int64 __fastcall(CdsUpdateObjectParser *__hidden this, const unsigned __int16 *, struct CdsUpdatePropertyCollection *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140066da4`

## callees

- `0x140024688`
- `0x14003f17c`
- `0x140063b9c`
- `0x140066aa4`
- `0x14006706c`
- `0x1400672fc`
- `0x14009e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400672df`
- `OLEAUT32!__imp_SysFreeString` at `0x1400672df`
- `ole32!CoCreateInstance` at `0x140067139`
- `ole32!CoCreateInstance` at `0x140067139`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CdsUpdateObjectParser::ParseXML(
        LPVOID *this,
        const unsigned __int16 *a2,
        struct CdsUpdatePropertyCollection *a3)
{
  struct CdsUpdatePropertyCollection *v3; // r12
  LPVOID *ppv; // r14
  PVOID *v6; // r10
  OLECHAR *v7; // rbx
  int v8; // esi
  HRESULT Instance; // eax
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r8
  struct IXMLDOMNodeList *v14; // [rsp+30h] [rbp-48h] BYREF
  __int64 v15[8]; // [rsp+38h] [rbp-40h] BYREF
  __int16 v17; // [rsp+88h] [rbp+10h] BYREF
  struct CdsUpdatePropertyCollection *v18; // [rsp+90h] [rbp+18h]
  BSTR bstrString; // [rsp+98h] [rbp+20h] BYREF

  v18 = a3;
  v3 = a3;
  ppv = this;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      (unsigned int)&WPP_5bc790e457bb3992ae758839568a0175_Traceguids,
      (_DWORD)a2,
      (char)a3);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v17 = 0;
  v7 = 0;
  bstrString = 0;
  if ( a2 && v3 )
  {
    ATL::CComBSTR::operator=(&bstrString, a2);
    v7 = bstrString;
    if ( !bstrString )
    {
      v8 = -2147024882;
LABEL_15:
      v6 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_23;
    }
    if ( *ppv
      || (Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, ppv),
          v8 = Instance,
          Instance >= 0) )
    {
      try
      {
        v10 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int16 *))(*(_QWORD *)*ppv + 520LL))(*ppv, v7, &v17);
      }
      catch ( ... )
      {
        v17 = 0;
        ppv = this;
        v3 = v18;
        v7 = bstrString;
        goto LABEL_18;
      }
      v8 = v10;
      if ( v10 >= 0 && v17 )
        goto LABEL_15;
LABEL_18:
      v8 = -2147024883;
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          &WPP_5bc790e457bb3992ae758839568a0175_Traceguids,
          2147942413LL);
        goto LABEL_15;
      }
    }
    else
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          &WPP_5bc790e457bb3992ae758839568a0175_Traceguids,
          (unsigned int)Instance);
        goto LABEL_15;
      }
    }
  }
  else
  {
    v8 = -2147467261;
  }
LABEL_23:
  v11 = 0;
  v15[0] = 0;
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)*ppv + 360LL))(*ppv, v15);
    v11 = v15[0];
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v14 = 0;
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMNodeList **))(*(_QWORD *)v11 + 96LL))(v11, &v14);
    if ( v8 >= 0 )
    {
      LOBYTE(v12) = 1;
      v8 = CdsUpdateObjectParser::ParseXMLProperties((CdsUpdateObjectParser *)ppv, v14, v12, v3);
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v6 + 28) & 1) != 0
    && *((unsigned __int8 *)v6 + 25) >= ((v8 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(v6[2], 24, &WPP_5bc790e457bb3992ae758839568a0175_Traceguids, (unsigned int)v8);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v14);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v15);
  SysFreeString(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14006706c  mov     [rsp+arg_10], r8
0x140067071  mov     [rsp+arg_0], rcx
0x140067076  push    rbx
0x140067077  push    rsi
0x140067078  push    rdi
0x140067079  push    r12
0x14006707b  push    r14
0x14006707d  push    r15
0x14006707f  sub     rsp, 48h
0x140067083  mov     r12, r8
0x140067086  mov     rsi, rdx
0x140067089  mov     r14, rcx
0x14006708c  lea     r15, WPP_GLOBAL_Control
0x140067093  mov     r10, cs:WPP_GLOBAL_Control
0x14006709a  cmp     r10, r15
0x14006709d  jz      short loc_1400670D1
0x14006709f  test    byte ptr [r10+1Ch], 1
0x1400670a4  jz      short loc_1400670D1
0x1400670a6  cmp     byte ptr [r10+19h], 5
0x1400670ab  jb      short loc_1400670D1
0x1400670ad  mov     edx, 15h
0x1400670b2  mov     [rsp+78h+ppv], r8
0x1400670b7  mov     r9, rsi
0x1400670ba  lea     r8, WPP_5bc790e457bb3992ae758839568a0175_Traceguids
0x1400670c1  mov     rcx, [r10+10h]
0x1400670c5  call    WPP_SF_Sq
0x1400670ca  mov     r10, cs:WPP_GLOBAL_Control
0x1400670d1  xor     edi, edi
0x1400670d3  mov     [rsp+78h+arg_8], di
0x1400670db  mov     ebx, edi
0x1400670dd  mov     [rsp+78h+bstrString], rbx
0x1400670e5  test    rsi, rsi
0x1400670e8  jz      loc_14006721B
0x1400670ee  test    r12, r12
0x1400670f1  jz      loc_14006721B
0x1400670f7  mov     rdx, rsi
0x1400670fa  lea     rcx, [rsp+78h+bstrString]
0x140067102  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x140067107  mov     rbx, [rsp+78h+bstrString]
0x14006710f  test    rbx, rbx
0x140067112  jnz     short loc_14006711B
0x140067114  mov     esi, 8007000Eh
0x140067119  jmp     short loc_140067183
0x14006711b  cmp     [r14], rdi
0x14006711e  jnz     short loc_14006718F
0x140067120  mov     [rsp+78h+ppv], r14; ppv
0x140067125  lea     r9, IID_IXMLDOMDocument; riid
0x14006712c  xor     edx, edx; pUnkOuter
0x14006712e  lea     r8d, [rdx+1]; dwClsContext
0x140067132  lea     rcx, CLSID_DOMDocument60; rclsid
0x140067139  call    cs:__imp_CoCreateInstance
0x14006713f  mov     esi, eax
0x140067141  test    eax, eax
0x140067143  jns     short loc_14006718F
0x140067145  mov     r10, cs:WPP_GLOBAL_Control
0x14006714c  cmp     r10, r15
0x14006714f  jz      loc_140067220
0x140067155  test    byte ptr [r10+1Ch], 2
0x14006715a  jz      loc_140067220
0x140067160  cmp     byte ptr [r10+19h], 2
0x140067165  jb      loc_140067220
0x14006716b  mov     edx, 16h
0x140067170  mov     r9d, eax
0x140067173  lea     r8, WPP_5bc790e457bb3992ae758839568a0175_Traceguids
0x14006717a  mov     rcx, [r10+10h]
0x14006717e  call    WPP_SF_d
0x140067183  mov     r10, cs:WPP_GLOBAL_Control
0x14006718a  jmp     loc_140067220
0x14006718f  mov     rcx, [r14]
0x140067192  mov     rax, [rcx]
0x140067195  lea     r8, [rsp+78h+arg_8]
0x14006719d  mov     rdx, rbx
0x1400671a0  mov     rax, [rax+208h]
0x1400671a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400671ac  mov     esi, eax
0x1400671ae  test    eax, eax
0x1400671b0  js      short loc_1400671DF
0x1400671b2  cmp     di, [rsp+78h+arg_8]
0x1400671ba  jz      short loc_1400671DF
0x1400671bc  jmp     short loc_140067183
0x1400671be  lea     r15, WPP_GLOBAL_Control
0x1400671c5  xor     edi, edi
0x1400671c7  mov     r14, [rsp+78h+arg_0]
0x1400671cf  mov     r12, [rsp+78h+arg_10]
0x1400671d7  mov     rbx, [rsp+78h+bstrString]
0x1400671df  mov     esi, 8007000Dh
0x1400671e4  mov     r10, cs:WPP_GLOBAL_Control
0x1400671eb  cmp     r10, r15
0x1400671ee  jz      short loc_140067220
0x1400671f0  test    byte ptr [r10+1Ch], 2
0x1400671f5  jz      short loc_140067220
0x1400671f7  cmp     byte ptr [r10+19h], 2
0x1400671fc  jb      short loc_140067220
0x1400671fe  mov     edx, 17h
0x140067203  mov     r9d, esi
0x140067206  lea     r8, WPP_5bc790e457bb3992ae758839568a0175_Traceguids
0x14006720d  mov     rcx, [r10+10h]
0x140067211  call    WPP_SF_d
0x140067216  jmp     loc_140067183
0x14006721b  mov     esi, 80004003h
0x140067220  mov     rcx, rdi
0x140067223  mov     [rsp+78h+var_40], rcx
0x140067228  test    esi, esi
0x14006722a  js      short loc_140067251
0x14006722c  mov     rcx, [r14]
0x14006722f  mov     rax, [rcx]
0x140067232  lea     rdx, [rsp+78h+var_40]
0x140067237  mov     rax, [rax+168h]
0x14006723e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067243  mov     esi, eax
0x140067245  mov     rcx, [rsp+78h+var_40]
0x14006724a  mov     r10, cs:WPP_GLOBAL_Control
0x140067251  mov     [rsp+78h+var_48], rdi
0x140067256  test    esi, esi
0x140067258  js      short loc_14006728D
0x14006725a  mov     rax, [rcx]
0x14006725d  lea     rdx, [rsp+78h+var_48]
0x140067262  mov     rax, [rax+60h]
0x140067266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006726b  mov     esi, eax
0x14006726d  test    eax, eax
0x14006726f  js      short loc_140067286
0x140067271  mov     r9, r12; struct CdsUpdatePropertyCollection *
0x140067274  mov     r8b, 1; bool
0x140067277  mov     rdx, [rsp+78h+var_48]; struct IXMLDOMNodeList *
0x14006727c  mov     rcx, r14; this
0x14006727f  call    ?ParseXMLProperties@CdsUpdateObjectParser@@AEAAJPEAUIXMLDOMNodeList@@_NPEAVCdsUpdatePropertyCollection@@@Z; CdsUpdateObjectParser::ParseXMLProperties(IXMLDOMNodeList *,bool,CdsUpdatePropertyCollection *)
0x140067284  mov     esi, eax
0x140067286  mov     r10, cs:WPP_GLOBAL_Control
0x14006728d  cmp     r10, r15
0x140067290  jz      short loc_1400672C6
0x140067292  test    byte ptr [r10+1Ch], 1
0x140067297  jz      short loc_1400672C6
0x140067299  mov     ecx, esi
0x14006729b  sar     ecx, 1Fh
0x14006729e  and     ecx, 0FFFFFFFDh
0x1400672a1  add     ecx, 5
0x1400672a4  movzx   eax, byte ptr [r10+19h]
0x1400672a9  cmp     eax, ecx
0x1400672ab  jb      short loc_1400672C6
0x1400672ad  mov     edx, 18h
0x1400672b2  mov     r9d, esi
0x1400672b5  lea     r8, WPP_5bc790e457bb3992ae758839568a0175_Traceguids
0x1400672bc  mov     rcx, [r10+10h]
0x1400672c0  call    WPP_SF_d
0x1400672c5  nop
0x1400672c6  lea     rcx, [rsp+78h+var_48]
0x1400672cb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400672d0  nop
0x1400672d1  lea     rcx, [rsp+78h+var_40]
0x1400672d6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400672db  nop
0x1400672dc  mov     rcx, rbx; bstrString
0x1400672df  call    cs:__imp_SysFreeString
0x1400672e5  mov     eax, esi
0x1400672e7  add     rsp, 48h
0x1400672eb  pop     r15
0x1400672ed  pop     r14
0x1400672ef  pop     r12
0x1400672f1  pop     rdi
0x1400672f2  pop     rsi
0x1400672f3  pop     rbx
0x1400672f4  retn
```
