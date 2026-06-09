# DiagPackage::get_Interactions(IXMLDOMDocument2 * *)

- ea: `0x180017c90`
- end: `0x18001819b`
- name: `?get_Interactions@DiagPackage@@QEAAJPEAPEAUIXMLDOMDocument2@@@Z`
- size: `1291`
- prototype: `__int64 __fastcall(DiagPackage *__hidden this, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180013720`

## callees

- `0x180017c90`
- `0x18001f844`
- `0x180026fa0`
- `0x180027ea4`
- `0x1800280f8`
- `0x18002827c`
- `0x1800288b8`
- `0x18002a010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180017f27`
- `msvcrt!_wcsicmp` at `0x180017f5f`
- `msvcrt!_wcsicmp` at `0x180017f97`
- `msvcrt!_wcsicmp` at `0x180017fca`
- `msvcrt!_wcsicmp` at `0x180017ffd`
- `msvcrt!_wcsicmp` at `0x180017f27`
- `msvcrt!_wcsicmp` at `0x180017f5f`
- `msvcrt!_wcsicmp` at `0x180017f97`
- `msvcrt!_wcsicmp` at `0x180017fca`
- `msvcrt!_wcsicmp` at `0x180017ffd`
- `OLEAUT32!__imp_SysFreeString` at `0x180017e93`
- `OLEAUT32!__imp_SysFreeString` at `0x1800180fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180017e93`
- `OLEAUT32!__imp_SysFreeString` at `0x1800180fe`

## string_xrefs

- `0x180017d0f`: `<?xml version="1.0" encoding="utf-8"?><Interactions/>`

## pseudocode

```c
__int64 __fastcall DiagPackage::get_Interactions(DiagPackage *this, struct IXMLDOMDocument2 **a2)
{
  struct IXMLDOMDocument2 *v3; // rsi
  struct IXMLDOMElement *v4; // r12
  struct IXMLDOMElement *v5; // r13
  struct IXMLDOMElement *v6; // r15
  unsigned int v7; // ebx
  int v8; // eax
  struct IXMLDOMDocument2 *v9; // r14
  int v10; // r8d
  int v11; // eax
  int v12; // eax
  int v13; // r8d
  int v14; // eax
  int RootNode; // eax
  struct IXMLDOMElement *v17; // [rsp+30h] [rbp-48h] BYREF
  struct IXMLDOMElement *v18; // [rsp+38h] [rbp-40h] BYREF
  struct IXMLDOMElement *v19; // [rsp+40h] [rbp-38h] BYREF
  struct IXMLDOMDocument2 *v20; // [rsp+48h] [rbp-30h] BYREF
  struct IXMLDOMElement *v21; // [rsp+50h] [rbp-28h] BYREF
  struct IXMLDOMElement *v22; // [rsp+58h] [rbp-20h] BYREF
  struct IXMLDOMElement *v23; // [rsp+60h] [rbp-18h] BYREF
  struct IXMLDOMDocument2 *v26; // [rsp+D0h] [rbp+58h] BYREF
  BSTR bstrString; // [rsp+D8h] [rbp+60h] BYREF

  v26 = 0;
  v3 = 0;
  v20 = 0;
  v4 = 0;
  v21 = 0;
  v5 = 0;
  v22 = 0;
  v6 = 0;
  v17 = 0;
  v18 = 0;
  v23 = 0;
  v19 = 0;
  bstrString = 0;
  if ( !a2 )
  {
    v7 = -2147024809;
    SdpDebugTrace(1u, L"DiagPackage::get_Interactions", 863, -2147024809);
    goto LABEL_57;
  }
  v8 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><Interactions/>", &v26);
  v9 = v26;
  v7 = v8;
  if ( v8 < 0 )
  {
    v10 = 866;
LABEL_5:
    SdpDebugTrace(1u, L"DiagPackage::get_Interactions", v10, v8);
    goto LABEL_43;
  }
  v8 = SdpXmlCreateNode(v26, 0, L"SingleResponseInteractions", 0, &v21);
  v7 = v8;
  if ( v8 < 0 )
  {
    v10 = 869;
    goto LABEL_5;
  }
  v8 = SdpXmlCreateNode(v9, 0, L"MultipleResponseInteractions", 0, &v22);
  v7 = v8;
  if ( v8 < 0 )
  {
    v10 = 872;
    goto LABEL_5;
  }
  v11 = SdpXmlCreateNode(v9, 0, L"TextInteractions", 0, &v17);
  v7 = v11;
  if ( v11 >= 0 )
  {
    v12 = SdpXmlCreateNode(v9, 0, L"PauseInteractions", 0, &v18);
    v7 = v12;
    if ( v12 >= 0 )
    {
      v12 = SdpXmlCreateNode(v9, 0, L"LaunchUIInteractions", 0, &v23);
      v7 = v12;
      if ( v12 >= 0 )
      {
        v4 = v17;
        v5 = v18;
        LODWORD(v26) = 0;
        if ( *((_DWORD *)this + 30) )
        {
          while ( 1 )
          {
            if ( v3 )
            {
              ((void (__fastcall *)(struct IXMLDOMDocument2 *))v3->lpVtbl->Release)(v3);
              v20 = 0;
            }
            if ( bstrString )
            {
              SysFreeString(bstrString);
              bstrString = 0;
            }
            if ( v6 )
            {
              ((void (__fastcall *)(struct IXMLDOMElement *))v6->lpVtbl->Release)(v6);
              v6 = 0;
              v19 = 0;
            }
            v14 = Interaction::BuildInteractionDocument(
                    *(Interaction **)(*((_QWORD *)this + 14) + 8LL * (unsigned int)v26),
                    &v20,
                    1);
            v7 = v14;
            if ( v14 < 0 )
              break;
            v3 = v20;
            RootNode = SdpXmlGetRootNode(v20, &v19);
            v7 = RootNode;
            if ( RootNode < 0 )
            {
              SdpDebugTrace(1u, L"DiagPackage::get_Interactions", 892, RootNode);
              v6 = v19;
              goto LABEL_43;
            }
            v6 = v19;
            v8 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))v19->lpVtbl->get_nodeName)(v19, &bstrString);
            v7 = v8;
            if ( v8 < 0 )
            {
              v10 = 895;
              goto LABEL_5;
            }
            if ( _wcsicmp(bstrString, L"SingleResponseInteraction") )
            {
              if ( _wcsicmp(bstrString, L"MultipleResponseInteraction") )
              {
                if ( _wcsicmp(bstrString, L"TextInteraction") )
                {
                  if ( _wcsicmp(bstrString, L"PauseInteraction") )
                  {
                    if ( !_wcsicmp(bstrString, L"LaunchUIInteraction") )
                    {
                      v8 = SdpXmlAppend(0, v23, v3);
                      v7 = v8;
                      if ( v8 < 0 )
                      {
                        v10 = 911;
                        goto LABEL_5;
                      }
                    }
                  }
                  else
                  {
                    v8 = SdpXmlAppend(0, v5, v3);
                    v7 = v8;
                    if ( v8 < 0 )
                    {
                      v10 = 908;
                      goto LABEL_5;
                    }
                  }
                }
                else
                {
                  v8 = SdpXmlAppend(0, v4, v3);
                  v7 = v8;
                  if ( v8 < 0 )
                  {
                    v10 = 905;
                    goto LABEL_5;
                  }
                }
              }
              else
              {
                v8 = SdpXmlAppend(0, v22, v3);
                v7 = v8;
                if ( v8 < 0 )
                {
                  v10 = 902;
                  goto LABEL_5;
                }
              }
            }
            else
            {
              v8 = SdpXmlAppend(0, v21, v3);
              v7 = v8;
              if ( v8 < 0 )
              {
                v10 = 899;
                goto LABEL_5;
              }
            }
            LODWORD(v26) = (_DWORD)v26 + 1;
            if ( (unsigned int)v26 >= *((_DWORD *)this + 30) )
              goto LABEL_42;
          }
          SdpDebugTrace(1u, L"Interaction::get_InteractionDocument", 894, v14);
          SdpDebugTrace(1u, L"DiagPackage::get_Interactions", 889, v7);
          v3 = v20;
        }
        else
        {
LABEL_42:
          *a2 = v9;
          ((void (__fastcall *)(struct IXMLDOMDocument2 *))v9->lpVtbl->AddRef)(v9);
        }
        goto LABEL_43;
      }
      v13 = 881;
    }
    else
    {
      v13 = 878;
    }
    SdpDebugTrace(1u, L"DiagPackage::get_Interactions", v13, v12);
    v4 = v17;
    v5 = v18;
  }
  else
  {
    SdpDebugTrace(1u, L"DiagPackage::get_Interactions", 875, v11);
    v4 = v17;
  }
LABEL_43:
  if ( v9 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v9->lpVtbl->Release)(v9);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v3->lpVtbl->Release)(v3);
  if ( v21 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v21->lpVtbl->Release)(v21);
  if ( v22 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v22->lpVtbl->Release)(v22);
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v4->lpVtbl->Release)(v4);
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v5->lpVtbl->Release)(v5);
  if ( v23 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v23->lpVtbl->Release)(v23);
LABEL_57:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v6->lpVtbl->Release)(v6);
  return v7;
}

```

## disassembly

```asm
0x180017c90  mov     [rsp-40h+arg_8], rdx
0x180017c95  mov     [rsp-40h+arg_0], rcx
0x180017c9a  push    rbp
0x180017c9b  push    rbx
0x180017c9c  push    rsi
0x180017c9d  push    rdi
0x180017c9e  push    r12
0x180017ca0  push    r13
0x180017ca2  push    r14
0x180017ca4  push    r15
0x180017ca6  mov     rbp, rsp
0x180017ca9  sub     rsp, 78h
0x180017cad  xor     r14d, r14d
0x180017cb0  mov     rdi, rcx
0x180017cb3  mov     [rbp+arg_10], r14
0x180017cb7  mov     esi, r14d
0x180017cba  mov     [rbp+var_30], r14
0x180017cbe  mov     r12d, r14d
0x180017cc1  mov     [rbp+var_28], r14
0x180017cc5  mov     r13d, r14d
0x180017cc8  mov     [rbp+var_20], r14
0x180017ccc  mov     r15d, r14d
0x180017ccf  mov     [rbp+var_48], r14
0x180017cd3  mov     [rbp+var_40], r14
0x180017cd7  mov     [rbp+var_18], r14
0x180017cdb  mov     [rbp+var_38], r14
0x180017cdf  mov     [rbp+bstrString], r14
0x180017ce3  test    rdx, rdx
0x180017ce6  jnz     short loc_180017D0B
0x180017ce8  mov     ebx, 80070057h
0x180017ced  lea     rdx, aDiagpackageGet_4; "DiagPackage::get_Interactions"
0x180017cf4  mov     r9d, ebx; int
0x180017cf7  lea     ecx, [r14+1]; Level
0x180017cfb  mov     r8d, 35Fh; int
0x180017d01  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180017d06  jmp     loc_1800180F5
0x180017d0b  lea     rdx, [rbp+arg_10]; struct IXMLDOMDocument2 **
0x180017d0f  lea     rcx, aXmlVersion10En_21; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180017d16  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x180017d1b  mov     r14, [rbp+arg_10]
0x180017d1f  mov     ebx, eax
0x180017d21  test    eax, eax
0x180017d23  jns     short loc_180017D44
0x180017d25  mov     r8d, 362h; int
0x180017d2b  mov     ecx, 1; Level
0x180017d30  mov     r9d, eax; int
0x180017d33  lea     rdx, aDiagpackageGet_4; "DiagPackage::get_Interactions"
0x180017d3a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180017d3f  jmp     loc_18001804A
0x180017d44  lea     rax, [rbp+var_28]
0x180017d48  xor     r9d, r9d; unsigned __int16 *
0x180017d4b  lea     r8, aSingleresponse_0; "SingleResponseInteractions"
0x180017d52  mov     [rsp+78h+var_58], rax; struct IXMLDOMElement **
0x180017d57  xor     edx, edx; struct IXMLDOMElement *
0x180017d59  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180017d5c  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180017d61  mov     ebx, eax
0x180017d63  test    eax, eax
0x180017d65  jns     short loc_180017D6F
0x180017d67  mov     r8d, 365h
0x180017d6d  jmp     short loc_180017D2B
0x180017d6f  lea     rax, [rbp+var_20]
0x180017d73  xor     r9d, r9d; unsigned __int16 *
0x180017d76  lea     r8, aMultiplerespon_3; "MultipleResponseInteractions"
0x180017d7d  mov     [rsp+78h+var_58], rax; struct IXMLDOMElement **
0x180017d82  xor     edx, edx; struct IXMLDOMElement *
0x180017d84  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180017d87  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180017d8c  mov     ebx, eax
0x180017d8e  test    eax, eax
0x180017d90  jns     short loc_180017D9A
0x180017d92  mov     r8d, 368h
0x180017d98  jmp     short loc_180017D2B
0x180017d9a  lea     rax, [rbp+var_48]
0x180017d9e  xor     r9d, r9d; unsigned __int16 *
0x180017da1  lea     r8, aTextinteractio_0; "TextInteractions"
0x180017da8  mov     [rsp+78h+var_58], rax; struct IXMLDOMElement **
0x180017dad  xor     edx, edx; struct IXMLDOMElement *
0x180017daf  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180017db2  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180017db7  mov     ebx, eax
0x180017db9  test    eax, eax
0x180017dbb  jns     short loc_180017DE0
0x180017dbd  mov     r9d, eax; int
0x180017dc0  lea     rdx, aDiagpackageGet_4; "DiagPackage::get_Interactions"
0x180017dc7  mov     r8d, 36Bh; int
0x180017dcd  mov     ecx, 1; Level
0x180017dd2  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180017dd7  mov     r12, [rbp+var_48]
0x180017ddb  jmp     loc_18001804A
0x180017de0  lea     rax, [rbp+var_40]
0x180017de4  xor     r9d, r9d; unsigned __int16 *
0x180017de7  lea     r8, aPauseinteracti_1; "PauseInteractions"
0x180017dee  mov     [rsp+78h+var_58], rax; struct IXMLDOMElement **
0x180017df3  xor     edx, edx; struct IXMLDOMElement *
0x180017df5  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180017df8  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180017dfd  mov     ebx, eax
0x180017dff  test    eax, eax
0x180017e01  jns     short loc_180017E2A
0x180017e03  mov     r8d, 36Eh; int
0x180017e09  mov     r9d, eax; int
0x180017e0c  lea     rdx, aDiagpackageGet_4; "DiagPackage::get_Interactions"
0x180017e13  mov     ecx, 1; Level
0x180017e18  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180017e1d  mov     r12, [rbp+var_48]
0x180017e21  mov     r13, [rbp+var_40]
0x180017e25  jmp     loc_18001804A
0x180017e2a  lea     rax, [rbp+var_18]
0x180017e2e  xor     r9d, r9d; unsigned __int16 *
0x180017e31  lea     r8, aLaunchuiintera_0; "LaunchUIInteractions"
0x180017e38  mov     [rsp+78h+var_58], rax; struct IXMLDOMElement **
0x180017e3d  xor     edx, edx; struct IXMLDOMElement *
0x180017e3f  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180017e42  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180017e47  mov     ebx, eax
0x180017e49  test    eax, eax
0x180017e4b  jns     short loc_180017E55
0x180017e4d  mov     r8d, 371h
0x180017e53  jmp     short loc_180017E09
0x180017e55  mov     r12, [rbp+var_48]
0x180017e59  mov     r13, [rbp+var_40]
0x180017e5d  mov     dword ptr [rbp+arg_10], esi
0x180017e60  cmp     [rdi+78h], esi
0x180017e63  jbe     loc_180018034
0x180017e69  mov     edi, 1
0x180017e6e  test    rsi, rsi
0x180017e71  jz      short loc_180017E8A
0x180017e73  mov     rax, [rsi]
0x180017e76  mov     rcx, rsi
0x180017e79  mov     rax, [rax+10h]
0x180017e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e82  mov     [rbp+var_30], 0
0x180017e8a  mov     rcx, [rbp+bstrString]; bstrString
0x180017e8e  test    rcx, rcx
0x180017e91  jz      short loc_180017EA1
0x180017e93  call    cs:__imp_SysFreeString
0x180017e99  mov     [rbp+bstrString], 0
0x180017ea1  test    r15, r15
0x180017ea4  jz      short loc_180017EBC
0x180017ea6  mov     rax, [r15]
0x180017ea9  mov     rcx, r15
0x180017eac  mov     rax, [rax+10h]
0x180017eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017eb5  xor     r15d, r15d
0x180017eb8  mov     [rbp+var_38], r15
0x180017ebc  mov     eax, dword ptr [rbp+arg_10]
0x180017ebf  lea     rdx, [rbp+var_30]; struct IXMLDOMDocument2 **
0x180017ec3  mov     rcx, [rbp+arg_0]
0x180017ec7  mov     r8d, edi; int
0x180017eca  mov     rcx, [rcx+70h]
0x180017ece  mov     rcx, [rcx+rax*8]; this
0x180017ed2  call    ?BuildInteractionDocument@Interaction@@IEAAJPEAPEAUIXMLDOMDocument2@@H@Z; Interaction::BuildInteractionDocument(IXMLDOMDocument2 * *,int)
0x180017ed7  mov     ebx, eax
0x180017ed9  test    eax, eax
0x180017edb  js      loc_180018164
0x180017ee1  mov     rsi, [rbp+var_30]
0x180017ee5  lea     rdx, [rbp+var_38]; struct IXMLDOMElement **
0x180017ee9  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x180017eec  call    ?SdpXmlGetRootNode@@YAJPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMElement@@@Z; SdpXmlGetRootNode(IXMLDOMDocument2 *,IXMLDOMElement * *)
0x180017ef1  mov     ebx, eax
0x180017ef3  test    eax, eax
0x180017ef5  js      loc_180018144
0x180017efb  mov     r15, [rbp+var_38]
0x180017eff  lea     rdx, [rbp+bstrString]
0x180017f03  mov     rcx, r15
0x180017f06  mov     rax, [r15]
0x180017f09  mov     rax, [rax+38h]
0x180017f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f12  mov     ebx, eax
0x180017f14  test    eax, eax
0x180017f16  js      loc_180018137
0x180017f1c  mov     rcx, [rbp+bstrString]; String1
0x180017f20  lea     rdx, aSingleresponse; "SingleResponseInteraction"
0x180017f27  call    cs:__imp__wcsicmp
0x180017f2d  test    eax, eax
0x180017f2f  jnz     short loc_180017F54
0x180017f31  mov     rdx, [rbp+var_28]; struct IXMLDOMElement *
0x180017f35  mov     r8, rsi; struct IXMLDOMDocument2 *
0x180017f38  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180017f3a  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x180017f3f  mov     ebx, eax
0x180017f41  test    eax, eax
0x180017f43  jns     loc_18001801F
0x180017f49  mov     r8d, 383h
0x180017f4f  jmp     loc_18001813D
0x180017f54  mov     rcx, [rbp+bstrString]; String1
0x180017f58  lea     rdx, aMultiplerespon; "MultipleResponseInteraction"
0x180017f5f  call    cs:__imp__wcsicmp
0x180017f65  test    eax, eax
0x180017f67  jnz     short loc_180017F8C
0x180017f69  mov     rdx, [rbp+var_20]; struct IXMLDOMElement *
0x180017f6d  mov     r8, rsi; struct IXMLDOMDocument2 *
0x180017f70  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180017f72  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x180017f77  mov     ebx, eax
0x180017f79  test    eax, eax
0x180017f7b  jns     loc_18001801F
0x180017f81  mov     r8d, 386h
0x180017f87  jmp     loc_18001813D
0x180017f8c  mov     rcx, [rbp+bstrString]; String1
0x180017f90  lea     rdx, aTextinteractio; "TextInteraction"
0x180017f97  call    cs:__imp__wcsicmp
0x180017f9d  test    eax, eax
0x180017f9f  jnz     short loc_180017FBF
0x180017fa1  mov     r8, rsi; struct IXMLDOMDocument2 *
0x180017fa4  mov     rdx, r12; struct IXMLDOMElement *
0x180017fa7  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180017fa9  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x180017fae  mov     ebx, eax
0x180017fb0  test    eax, eax
0x180017fb2  jns     short loc_18001801F
0x180017fb4  mov     r8d, 389h
0x180017fba  jmp     loc_18001813D
0x180017fbf  mov     rcx, [rbp+bstrString]; String1
0x180017fc3  lea     rdx, aPauseinteracti_0; "PauseInteraction"
0x180017fca  call    cs:__imp__wcsicmp
0x180017fd0  test    eax, eax
0x180017fd2  jnz     short loc_180017FF2
0x180017fd4  mov     r8, rsi; struct IXMLDOMDocument2 *
0x180017fd7  mov     rdx, r13; struct IXMLDOMElement *
0x180017fda  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180017fdc  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x180017fe1  mov     ebx, eax
0x180017fe3  test    eax, eax
0x180017fe5  jns     short loc_18001801F
0x180017fe7  mov     r8d, 38Ch
0x180017fed  jmp     loc_18001813D
0x180017ff2  mov     rcx, [rbp+bstrString]; String1
0x180017ff6  lea     rdx, aLaunchuiintera_1; "LaunchUIInteraction"
0x180017ffd  call    cs:__imp__wcsicmp
0x180018003  test    eax, eax
0x180018005  jnz     short loc_18001801F
0x180018007  mov     rdx, [rbp+var_18]; struct IXMLDOMElement *
0x18001800b  mov     r8, rsi; struct IXMLDOMDocument2 *
0x18001800e  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180018010  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x180018015  mov     ebx, eax
0x180018017  test    eax, eax
0x180018019  js      loc_18001812F
0x18001801f  mov     eax, dword ptr [rbp+arg_10]
0x180018022  mov     rcx, [rbp+arg_0]
0x180018026  add     eax, edi
0x180018028  mov     dword ptr [rbp+arg_10], eax
0x18001802b  cmp     eax, [rcx+78h]
0x18001802e  jb      loc_180017E6E
0x180018034  mov     rax, [rbp+arg_8]
0x180018038  mov     rcx, r14
0x18001803b  mov     [rax], r14
0x18001803e  mov     rax, [r14]
0x180018041  mov     rax, [rax+8]
0x180018045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001804a  test    r14, r14
0x18001804d  jz      short loc_18001805E
0x18001804f  mov     rax, [r14]
0x180018052  mov     rcx, r14
0x180018055  mov     rax, [rax+10h]
0x180018059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001805e  xor     r14d, r14d
0x180018061  test    rsi, rsi
0x180018064  jz      short loc_180018078
0x180018066  mov     rax, [rsi]
0x180018069  mov     rcx, rsi
0x18001806c  mov     rax, [rax+10h]
0x180018070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018075  mov     esi, r14d
0x180018078  mov     rcx, [rbp+var_28]
0x18001807c  test    rcx, rcx
0x18001807f  jz      short loc_18001808D
0x180018081  mov     rax, [rcx]
0x180018084  mov     rax, [rax+10h]
0x180018088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001808d  mov     rcx, [rbp+var_20]
0x180018091  test    rcx, rcx
0x180018094  jz      short loc_1800180A2
0x180018096  mov     rax, [rcx]
0x180018099  mov     rax, [rax+10h]
0x18001809d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180a2  test    r12, r12
0x1800180a5  jz      short loc_1800180B7
0x1800180a7  mov     rax, [r12]
0x1800180ab  mov     rcx, r12
0x1800180ae  mov     rax, [rax+10h]
0x1800180b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180b7  test    r13, r13
0x1800180ba  jz      short loc_1800180CC
0x1800180bc  mov     rax, [r13+0]
0x1800180c0  mov     rcx, r13
0x1800180c3  mov     rax, [rax+10h]
0x1800180c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180cc  mov     rcx, [rbp+var_18]
0x1800180d0  test    rcx, rcx
0x1800180d3  jz      short loc_1800180E1
0x1800180d5  mov     rax, [rcx]
0x1800180d8  mov     rax, [rax+10h]
0x1800180dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180e1  test    rsi, rsi
0x1800180e4  jz      short loc_1800180F5
0x1800180e6  mov     rax, [rsi]
0x1800180e9  mov     rcx, rsi
  ... truncated ...
```
