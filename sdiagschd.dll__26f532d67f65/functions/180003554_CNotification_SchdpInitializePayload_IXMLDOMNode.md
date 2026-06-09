# CNotification::SchdpInitializePayload(IXMLDOMNode *)

- ea: `0x180003554`
- end: `0x180003a8e`
- name: `?SchdpInitializePayload@CNotification@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `1338`
- prototype: `__int64 __fastcall(CNotification *__hidden this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180002de0`

## callees

- `0x180003554`
- `0x18000b13c`
- `0x18000b234`
- `0x18000b498`
- `0x18000b884`
- `0x18000d010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18000366e`
- `msvcrt!_wtoi` at `0x18000371e`
- `msvcrt!_wtoi` at `0x1800037cf`
- `msvcrt!_wtoi` at `0x18000366e`
- `msvcrt!_wtoi` at `0x18000371e`
- `msvcrt!_wtoi` at `0x1800037cf`
- `OLEAUT32!__imp_SysFreeString` at `0x18000387b`
- `OLEAUT32!__imp_SysFreeString` at `0x180003a18`
- `OLEAUT32!__imp_SysFreeString` at `0x180003a32`
- `OLEAUT32!__imp_SysFreeString` at `0x180003a4c`
- `OLEAUT32!__imp_SysFreeString` at `0x180003a66`
- `OLEAUT32!__imp_SysFreeString` at `0x18000387b`
- `OLEAUT32!__imp_SysFreeString` at `0x180003a18`
- `OLEAUT32!__imp_SysFreeString` at `0x180003a32`
- `OLEAUT32!__imp_SysFreeString` at `0x180003a4c`
- `OLEAUT32!__imp_SysFreeString` at `0x180003a66`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800038f0`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800038f0`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000381a`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000381a`

## pseudocode

```c
__int64 __fastcall CNotification::SchdpInitializePayload(CNotification *this, struct IXMLDOMNode *a2)
{
  struct IXMLDOMNode *v2; // rdi
  int ChildNodes; // eax
  struct IXMLDOMNodeList *v5; // r12
  unsigned int v6; // ebx
  int v7; // r9d
  int v8; // r8d
  LONG v9; // r14d
  int v10; // eax
  int v11; // r8d
  int v12; // eax
  HRESULT v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  ULONG v19; // r14d
  SAFEARRAY *Vector; // rax
  int v21; // eax
  BSTR bstrString; // [rsp+20h] [rbp-30h] BYREF
  wchar_t *String; // [rsp+28h] [rbp-28h] BYREF
  BSTR v25; // [rsp+30h] [rbp-20h] BYREF
  BSTR v26; // [rsp+38h] [rbp-18h] BYREF
  struct IXMLDOMNodeList *v27; // [rsp+40h] [rbp-10h] BYREF
  LONG rgIndices; // [rsp+90h] [rbp+40h] BYREF
  struct IXMLDOMNode *v29; // [rsp+98h] [rbp+48h] BYREF

  v27 = 0;
  v2 = 0;
  String = 0;
  v25 = 0;
  v26 = 0;
  bstrString = 0;
  rgIndices = 0;
  v29 = 0;
  ChildNodes = SdpXmlGetChildNodes((struct IXMLDOMDocument2 *)this, a2, &v27, (unsigned int *)&rgIndices);
  v5 = v27;
  v6 = ChildNodes;
  if ( ChildNodes >= 0 )
  {
    v9 = rgIndices;
    if ( (unsigned int)rgIndices < 3 )
    {
      v6 = -2147024809;
      v8 = 75;
      v7 = -2147024809;
      goto LABEL_67;
    }
    v10 = SdpXmlNextNode(v27, &v29);
    v6 = v10;
    if ( v10 < 0 )
    {
      v11 = 79;
      goto LABEL_7;
    }
    v2 = v29;
    v12 = SdpXmlCheckNode(v29, L"DefaultStateID");
    v6 = v12;
    if ( v12 < 0 )
    {
      v7 = v12;
LABEL_66:
      v8 = 80;
      goto LABEL_67;
    }
    if ( v12 == 1 || !v2 )
    {
      v7 = -2147467259;
      v6 = -2147467259;
      goto LABEL_66;
    }
    v13 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, wchar_t **))v2->lpVtbl->get_text)(v2, &String);
    v6 = v13;
    if ( v13 < 0 )
    {
      v8 = 83;
      goto LABEL_14;
    }
    v14 = _wtoi(String);
    if ( v14 < 0 )
    {
      *((_DWORD *)this + 2) = -1;
      v6 = -2147024362;
      v7 = -2147024362;
      v8 = 86;
      goto LABEL_67;
    }
    *((_DWORD *)this + 2) = v14;
    ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
    v29 = 0;
    v10 = SdpXmlNextNode(v5, &v29);
    v6 = v10;
    if ( v10 < 0 )
    {
      v11 = 92;
      goto LABEL_7;
    }
    v2 = v29;
    v15 = SdpXmlCheckNode(v29, L"DisabledStateID");
    v6 = v15;
    if ( v15 >= 0 )
    {
      if ( v15 != 1 && v2 )
      {
        v13 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v2->lpVtbl->get_text)(v2, &v25);
        v6 = v13;
        if ( v13 < 0 )
        {
          v8 = 96;
          goto LABEL_14;
        }
        v16 = _wtoi(v25);
        if ( v16 < 0 )
        {
          *((_DWORD *)this + 3) = -1;
          v6 = -2147024362;
          v7 = -2147024362;
          v8 = 99;
          goto LABEL_67;
        }
        *((_DWORD *)this + 3) = v16;
        ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
        v29 = 0;
        v10 = SdpXmlNextNode(v5, &v29);
        v6 = v10;
        if ( v10 < 0 )
        {
          v11 = 105;
          goto LABEL_7;
        }
        v2 = v29;
        v17 = SdpXmlCheckNode(v29, L"StateID");
        v6 = v17;
        if ( v17 >= 0 )
        {
          if ( v17 != 1 && v2 )
          {
            v13 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v2->lpVtbl->get_text)(v2, &v26);
            v6 = v13;
            if ( v13 >= 0 )
            {
              v18 = _wtoi(v26);
              if ( v18 < 0 )
              {
                *((_DWORD *)this + 1) = -1;
                v6 = -2147024362;
                v7 = -2147024362;
                v8 = 112;
                goto LABEL_67;
              }
              v6 = 0;
              *((_DWORD *)this + 1) = v18;
              v19 = v9 - 3;
              ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
              v2 = 0;
              v29 = 0;
              if ( !v19 )
                goto LABEL_68;
              Vector = SafeArrayCreateVector(8u, 0, v19);
              *((_QWORD *)this + 2) = Vector;
              if ( !Vector )
              {
                v6 = -2147024882;
                v8 = 122;
                v7 = -2147024882;
                goto LABEL_67;
              }
              if ( v19 > 0x7FFFFFFF )
              {
                v6 = -2147024362;
                v8 = 125;
                v7 = -2147024362;
                goto LABEL_67;
              }
              rgIndices = 0;
              while ( 1 )
              {
                if ( v2 )
                {
                  ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
                  v29 = 0;
                }
                if ( bstrString )
                {
                  SysFreeString(bstrString);
                  bstrString = 0;
                }
                v10 = SdpXmlNextNode(v5, &v29);
                v6 = v10;
                if ( v10 < 0 )
                  break;
                v2 = v29;
                v21 = SdpXmlCheckNode(v29, L"Data");
                v6 = v21;
                if ( v21 < 0 )
                {
                  v7 = v21;
                  goto LABEL_56;
                }
                if ( v21 == 1 || !v2 )
                {
                  v7 = -2147467259;
                  v6 = -2147467259;
LABEL_56:
                  v8 = 134;
                  goto LABEL_67;
                }
                v13 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v2->lpVtbl->get_text)(v2, &bstrString);
                v6 = v13;
                if ( v13 < 0 )
                {
                  v8 = 137;
                  goto LABEL_14;
                }
                v13 = SafeArrayPutElement(*((SAFEARRAY **)this + 2), &rgIndices, bstrString);
                v6 = v13;
                if ( v13 < 0 )
                {
                  v8 = 140;
                  goto LABEL_14;
                }
                if ( ++rgIndices >= (int)v19 )
                  goto LABEL_68;
              }
              v11 = 133;
LABEL_7:
              SdpDebugTrace(1u, L"CNotification::SchdpInitializePayload", v11, v10);
              v2 = v29;
              goto LABEL_68;
            }
            v8 = 109;
LABEL_14:
            v7 = v13;
            goto LABEL_67;
          }
          v7 = -2147467259;
          v6 = -2147467259;
        }
        else
        {
          v7 = v17;
        }
        v8 = 106;
        goto LABEL_67;
      }
      v7 = -2147467259;
      v6 = -2147467259;
    }
    else
    {
      v7 = v15;
    }
    v8 = 93;
    goto LABEL_67;
  }
  v7 = ChildNodes;
  v8 = 71;
LABEL_67:
  SdpDebugTrace(1u, L"CNotification::SchdpInitializePayload", v8, v7);
LABEL_68:
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v5->lpVtbl->Release)(v5);
  if ( v2 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
  if ( String )
  {
    SysFreeString(String);
    String = 0;
  }
  if ( v25 )
  {
    SysFreeString(v25);
    v25 = 0;
  }
  if ( v26 )
  {
    SysFreeString(v26);
    v26 = 0;
  }
  if ( bstrString )
    SysFreeString(bstrString);
  return v6;
}

```

## disassembly

```asm
0x180003554  mov     [rsp-28h+arg_0], rbx
0x180003559  mov     [rsp-28h+arg_8], rsi
0x18000355e  push    rbp
0x18000355f  push    rdi
0x180003560  push    r12
0x180003562  push    r13
0x180003564  push    r14
0x180003566  mov     rbp, rsp
0x180003569  sub     rsp, 50h
0x18000356d  and     [rbp+var_10], 0
0x180003572  lea     r9, [rbp+rgIndices]; unsigned int *
0x180003576  xor     edi, edi
0x180003578  lea     r8, [rbp+var_10]; struct IXMLDOMNodeList **
0x18000357c  and     [rbp+String], rdi
0x180003580  mov     r13, rcx
0x180003583  and     [rbp+var_20], rdi
0x180003587  and     [rbp+var_18], rdi
0x18000358b  and     [rbp+bstrString], rdi
0x18000358f  and     [rbp+rgIndices], edi
0x180003592  mov     [rbp+arg_18], rdi
0x180003596  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x18000359b  mov     r12, [rbp+var_10]
0x18000359f  mov     ebx, eax
0x1800035a1  test    eax, eax
0x1800035a3  jns     short loc_1800035B6
0x1800035a5  mov     r9d, eax
0x1800035a8  lea     r8d, [rdi+47h]
0x1800035ac  mov     ecx, 1
0x1800035b1  jmp     loc_1800039DA
0x1800035b6  mov     r14d, [rbp+rgIndices]
0x1800035ba  cmp     r14d, 3
0x1800035be  jnb     short loc_1800035D0
0x1800035c0  mov     ebx, 80070057h
0x1800035c5  mov     r8d, 4Bh ; 'K'
0x1800035cb  mov     r9d, ebx
0x1800035ce  jmp     short loc_1800035AC
0x1800035d0  lea     rdx, [rbp+arg_18]; struct IXMLDOMNode **
0x1800035d4  mov     rcx, r12; struct IXMLDOMNodeList *
0x1800035d7  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x1800035dc  mov     ebx, eax
0x1800035de  test    eax, eax
0x1800035e0  jns     short loc_180003604
0x1800035e2  mov     r8d, 4Fh ; 'O'; int
0x1800035e8  lea     ecx, [r8-4Eh]; Level
0x1800035ec  mov     r9d, eax; int
0x1800035ef  lea     rdx, aCnotificationS_3; "CNotification::SchdpInitializePayload"
0x1800035f6  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800035fb  mov     rdi, [rbp+arg_18]
0x1800035ff  jmp     loc_1800039E6
0x180003604  mov     rdi, [rbp+arg_18]
0x180003608  lea     rdx, aDefaultstateid; "DefaultStateID"
0x18000360f  mov     rcx, rdi; struct IXMLDOMNode *
0x180003612  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180003617  mov     ebx, eax
0x180003619  test    eax, eax
0x18000361b  jns     short loc_18000362A
0x18000361d  mov     r9d, eax
0x180003620  mov     ecx, 1
0x180003625  jmp     loc_1800039D4
0x18000362a  mov     esi, 1
0x18000362f  cmp     eax, esi
0x180003631  jz      loc_1800039C9
0x180003637  test    rdi, rdi
0x18000363a  jz      loc_1800039C9
0x180003640  mov     rax, [rdi]
0x180003643  lea     rdx, [rbp+String]
0x180003647  mov     rcx, rdi
0x18000364a  mov     rax, [rax+0D0h]
0x180003651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003656  mov     ebx, eax
0x180003658  test    eax, eax
0x18000365a  jns     short loc_18000366A
0x18000365c  lea     r8d, [rsi+52h]
0x180003660  mov     r9d, eax
0x180003663  mov     ecx, esi
0x180003665  jmp     loc_1800039DA
0x18000366a  mov     rcx, [rbp+String]; String
0x18000366e  call    cs:__imp__wtoi
0x180003675  nop     dword ptr [rax+rax+00h]
0x18000367a  test    eax, eax
0x18000367c  js      loc_1800039B1
0x180003682  mov     [r13+8], eax
0x180003686  test    rdi, rdi
0x180003689  jz      short loc_18000369F
0x18000368b  mov     rax, [rdi]
0x18000368e  mov     rcx, rdi
0x180003691  mov     rax, [rax+10h]
0x180003695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000369a  and     [rbp+arg_18], 0
0x18000369f  lea     rdx, [rbp+arg_18]; struct IXMLDOMNode **
0x1800036a3  mov     rcx, r12; struct IXMLDOMNodeList *
0x1800036a6  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x1800036ab  mov     ebx, eax
0x1800036ad  test    eax, eax
0x1800036af  jns     short loc_1800036BE
0x1800036b1  mov     r8d, 5Ch ; '\'
0x1800036b7  mov     ecx, esi
0x1800036b9  jmp     loc_1800035EC
0x1800036be  mov     rdi, [rbp+arg_18]
0x1800036c2  lea     rdx, aDisabledstatei; "DisabledStateID"
0x1800036c9  mov     rcx, rdi; struct IXMLDOMNode *
0x1800036cc  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x1800036d1  mov     ebx, eax
0x1800036d3  test    eax, eax
0x1800036d5  jns     short loc_1800036E2
0x1800036d7  mov     r9d, eax
0x1800036da  mov     r8d, 5Dh ; ']'
0x1800036e0  jmp     short loc_180003663
0x1800036e2  cmp     eax, esi
0x1800036e4  jz      loc_1800039A3
0x1800036ea  test    rdi, rdi
0x1800036ed  jz      loc_1800039A3
0x1800036f3  mov     rax, [rdi]
0x1800036f6  lea     rdx, [rbp+var_20]
0x1800036fa  mov     rcx, rdi
0x1800036fd  mov     rax, [rax+0D0h]
0x180003704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003709  mov     ebx, eax
0x18000370b  test    eax, eax
0x18000370d  jns     short loc_18000371A
0x18000370f  mov     r8d, 60h ; '`'
0x180003715  jmp     loc_180003660
0x18000371a  mov     rcx, [rbp+var_20]; String
0x18000371e  call    cs:__imp__wtoi
0x180003725  nop     dword ptr [rax+rax+00h]
0x18000372a  test    eax, eax
0x18000372c  js      loc_18000398B
0x180003732  mov     [r13+0Ch], eax
0x180003736  test    rdi, rdi
0x180003739  jz      short loc_18000374F
0x18000373b  mov     rax, [rdi]
0x18000373e  mov     rcx, rdi
0x180003741  mov     rax, [rax+10h]
0x180003745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000374a  and     [rbp+arg_18], 0
0x18000374f  lea     rdx, [rbp+arg_18]; struct IXMLDOMNode **
0x180003753  mov     rcx, r12; struct IXMLDOMNodeList *
0x180003756  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18000375b  mov     ebx, eax
0x18000375d  test    eax, eax
0x18000375f  jns     short loc_18000376C
0x180003761  mov     r8d, 69h ; 'i'
0x180003767  jmp     loc_1800036B7
0x18000376c  mov     rdi, [rbp+arg_18]
0x180003770  lea     rdx, aStateid; "StateID"
0x180003777  mov     rcx, rdi; struct IXMLDOMNode *
0x18000377a  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18000377f  mov     ebx, eax
0x180003781  test    eax, eax
0x180003783  jns     short loc_180003793
0x180003785  mov     r9d, eax
0x180003788  mov     r8d, 6Ah ; 'j'
0x18000378e  jmp     loc_180003663
0x180003793  cmp     eax, esi
0x180003795  jz      loc_18000397D
0x18000379b  test    rdi, rdi
0x18000379e  jz      loc_18000397D
0x1800037a4  mov     rax, [rdi]
0x1800037a7  lea     rdx, [rbp+var_18]
0x1800037ab  mov     rcx, rdi
0x1800037ae  mov     rax, [rax+0D0h]
0x1800037b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037ba  mov     ebx, eax
0x1800037bc  test    eax, eax
0x1800037be  jns     short loc_1800037CB
0x1800037c0  mov     r8d, 6Dh ; 'm'
0x1800037c6  jmp     loc_180003660
0x1800037cb  mov     rcx, [rbp+var_18]; String
0x1800037cf  call    cs:__imp__wtoi
0x1800037d6  nop     dword ptr [rax+rax+00h]
0x1800037db  test    eax, eax
0x1800037dd  js      loc_180003965
0x1800037e3  xor     ebx, ebx
0x1800037e5  mov     [r13+4], eax
0x1800037e9  sub     r14d, 3
0x1800037ed  test    rdi, rdi
0x1800037f0  jz      short loc_180003807
0x1800037f2  mov     rax, [rdi]
0x1800037f5  mov     rcx, rdi
0x1800037f8  mov     rax, [rax+10h]
0x1800037fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003801  xor     edi, edi
0x180003803  mov     [rbp+arg_18], rdi
0x180003807  test    r14d, r14d
0x18000380a  jz      loc_1800039E6
0x180003810  mov     ecx, 8; vt
0x180003815  mov     r8d, r14d; cElements
0x180003818  xor     edx, edx; lLbound
0x18000381a  call    cs:__imp_SafeArrayCreateVector
0x180003821  nop     dword ptr [rax+rax+00h]
0x180003826  mov     [r13+10h], rax
0x18000382a  test    rax, rax
0x18000382d  jnz     short loc_180003840
0x18000382f  mov     ebx, 8007000Eh
0x180003834  lea     r8d, [rax+7Ah]
0x180003838  mov     r9d, ebx
0x18000383b  jmp     loc_180003663
0x180003840  cmp     r14d, 7FFFFFFFh
0x180003847  ja      loc_180003952
0x18000384d  and     [rbp+rgIndices], ebx
0x180003850  test    r14d, r14d
0x180003853  jle     loc_1800039E6
0x180003859  test    rdi, rdi
0x18000385c  jz      short loc_180003872
0x18000385e  mov     rax, [rdi]
0x180003861  mov     rcx, rdi
0x180003864  mov     rax, [rax+10h]
0x180003868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000386d  and     [rbp+arg_18], 0
0x180003872  mov     rcx, [rbp+bstrString]; bstrString
0x180003876  test    rcx, rcx
0x180003879  jz      short loc_18000388C
0x18000387b  call    cs:__imp_SysFreeString
0x180003882  nop     dword ptr [rax+rax+00h]
0x180003887  and     [rbp+bstrString], 0
0x18000388c  lea     rdx, [rbp+arg_18]; struct IXMLDOMNode **
0x180003890  mov     rcx, r12; struct IXMLDOMNodeList *
0x180003893  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180003898  mov     ebx, eax
0x18000389a  test    eax, eax
0x18000389c  js      loc_180003947
0x1800038a2  mov     rdi, [rbp+arg_18]
0x1800038a6  lea     rdx, aData; "Data"
0x1800038ad  mov     rcx, rdi; struct IXMLDOMNode *
0x1800038b0  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x1800038b5  mov     ebx, eax
0x1800038b7  test    eax, eax
0x1800038b9  js      loc_180003942
0x1800038bf  cmp     eax, esi
0x1800038c1  jz      short loc_18000392E
0x1800038c3  test    rdi, rdi
0x1800038c6  jz      short loc_18000392E
0x1800038c8  mov     rax, [rdi]
0x1800038cb  lea     rdx, [rbp+bstrString]
0x1800038cf  mov     rcx, rdi
0x1800038d2  mov     rax, [rax+0D0h]
0x1800038d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038de  mov     ebx, eax
0x1800038e0  test    eax, eax
0x1800038e2  js      short loc_180003923
0x1800038e4  mov     r8, [rbp+bstrString]; pv
0x1800038e8  lea     rdx, [rbp+rgIndices]; rgIndices
0x1800038ec  mov     rcx, [r13+10h]; psa
0x1800038f0  call    cs:__imp_SafeArrayPutElement
0x1800038f7  nop     dword ptr [rax+rax+00h]
0x1800038fc  mov     ebx, eax
0x1800038fe  test    eax, eax
0x180003900  js      short loc_180003918
0x180003902  mov     eax, [rbp+rgIndices]
0x180003905  add     eax, esi
0x180003907  mov     [rbp+rgIndices], eax
0x18000390a  cmp     eax, r14d
0x18000390d  jl      loc_180003859
0x180003913  jmp     loc_1800039E6
0x180003918  mov     r8d, 8Ch
0x18000391e  jmp     loc_180003660
0x180003923  mov     r8d, 89h
0x180003929  jmp     loc_180003660
0x18000392e  mov     r9d, 80004005h
0x180003934  mov     ebx, r9d
0x180003937  mov     r8d, 86h
0x18000393d  jmp     loc_180003663
0x180003942  mov     r9d, eax
0x180003945  jmp     short loc_180003937
0x180003947  mov     r8d, 85h
0x18000394d  jmp     loc_1800036B7
0x180003952  mov     ebx, 80070216h
0x180003957  mov     r8d, 7Dh ; '}'
0x18000395d  mov     r9d, ebx
0x180003960  jmp     loc_180003663
0x180003965  or      dword ptr [r13+4], 0FFFFFFFFh
0x18000396a  mov     ebx, 80070216h
0x18000396f  mov     r9d, ebx
0x180003972  mov     r8d, 70h ; 'p'
0x180003978  jmp     loc_180003663
0x18000397d  mov     r9d, 80004005h
0x180003983  mov     ebx, r9d
0x180003986  jmp     loc_180003788
0x18000398b  or      dword ptr [r13+0Ch], 0FFFFFFFFh
0x180003990  mov     ebx, 80070216h
0x180003995  mov     r9d, ebx
0x180003998  mov     r8d, 63h ; 'c'
0x18000399e  jmp     loc_180003663
0x1800039a3  mov     r9d, 80004005h
0x1800039a9  mov     ebx, r9d
0x1800039ac  jmp     loc_1800036DA
0x1800039b1  or      dword ptr [r13+8], 0FFFFFFFFh
0x1800039b6  mov     ebx, 80070216h
0x1800039bb  mov     r9d, ebx
0x1800039be  mov     r8d, 56h ; 'V'
0x1800039c4  jmp     loc_180003663
0x1800039c9  mov     r9d, 80004005h; int
0x1800039cf  mov     ecx, esi; Level
0x1800039d1  mov     ebx, r9d
0x1800039d4  mov     r8d, 50h ; 'P'; int
0x1800039da  lea     rdx, aCnotificationS_3; "CNotification::SchdpInitializePayload"
0x1800039e1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800039e6  test    r12, r12
0x1800039e9  jz      short loc_1800039FB
0x1800039eb  mov     rax, [r12]
  ... truncated ...
```
