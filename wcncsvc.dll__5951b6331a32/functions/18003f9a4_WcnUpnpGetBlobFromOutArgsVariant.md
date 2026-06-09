# WcnUpnpGetBlobFromOutArgsVariant

- ea: `0x18003f9a4`
- end: `0x18003fc77`
- name: `WcnUpnpGetBlobFromOutArgsVariant`
- size: `723`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003ff58`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x180005088`
- `0x18000a6d4`
- `0x18003f9a4`
- `0x180053004`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18003fbdb`
- `RPCRT4!UuidCreate` at `0x18003fbdb`
- `OLEAUT32!__imp_VariantInit` at `0x18003fa67`
- `OLEAUT32!__imp_VariantInit` at `0x18003fa67`
- `OLEAUT32!__imp_VariantClear` at `0x18003fc24`
- `OLEAUT32!__imp_VariantClear` at `0x18003fc24`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003fb6a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003fb6a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003fbe5`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003fbe5`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18003fab4`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18003fab4`

## pseudocode

```c
__int64 __fastcall WcnUpnpGetBlobFromOutArgsVariant(__int64 a1, UUID *a2)
{
  _BYTE *v4; // r10
  const char *Indent; // rax
  __int64 v6; // r10
  __int64 v7; // rdx
  const char *v8; // r9
  int v10; // ebx
  const char *v11; // rax
  __int64 v12; // r10
  __int64 v13; // rdx
  HRESULT Element; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  unsigned __int64 v17; // rdi
  unsigned int v18; // eax
  __int64 v19; // r10
  char v20; // r11
  int v21; // eax
  unsigned int v22; // eax
  __int64 v23; // r10
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+80h] [rbp+30h] BYREF
  void *ppvData; // [rsp+90h] [rbp+40h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  rgIndices = 0;
  ppvData = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 18, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids, Indent);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v4 == (_BYTE *)&WPP_GLOBAL_Control || v4[25] < 2u )
      return 2147500035LL;
    v7 = 19;
    v8 = "pvarOutputArg";
LABEL_12:
    WPP_SF_s(*((_QWORD *)v4 + 2), v7, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids, v8);
    return 2147500035LL;
  }
  if ( !a2 )
  {
    if ( v4 == (_BYTE *)&WPP_GLOBAL_Control || v4[25] < 2u )
      return 2147500035LL;
    v7 = 20;
    v8 = "pBlob";
    goto LABEL_12;
  }
  VariantInit(&pvarg);
  if ( *(_WORD *)a1 != 8204 )
  {
    v10 = -2147418113;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_43;
    v11 = GetIndent(0);
    v13 = 21;
    goto LABEL_42;
  }
  Element = SafeArrayGetElement(*(SAFEARRAY **)(a1 + 8), &rgIndices, &pvarg);
  v10 = Element;
  if ( Element < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_43;
    v16 = 22;
    goto LABEL_22;
  }
  if ( pvarg.vt != 8209 || *pvarg.bstrVal != 1 )
  {
    v10 = -2147176440;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_43;
    v11 = GetIndent(0);
    v13 = 23;
LABEL_42:
    WPP_SF_s(*(_QWORD *)(v12 + 16), v13, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids, v11);
    goto LABEL_43;
  }
  v17 = *(unsigned int *)(pvarg.llVal + 24);
  if ( v17 > 0x2800 )
  {
    v10 = -2147176440;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = (unsigned int)GetIndent(0);
      WPP_SF_sld(
        *(_QWORD *)(v19 + 16),
        24,
        (unsigned int)WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids,
        v18,
        v17,
        v20);
    }
    goto LABEL_43;
  }
  Element = SafeArrayAccessData(pvarg.parray, &ppvData);
  v10 = Element;
  if ( Element >= 0 )
  {
    v21 = CSbSafeBuffer::CopyFromBuffer((CSbSafeBuffer *)a2, (const unsigned __int8 *)ppvData, v17);
    v10 = v21;
    if ( v21 >= 0 )
    {
      UuidCreate(a2 + 2);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids,
        (unsigned int)v21);
    }
    SafeArrayUnaccessData(pvarg.parray);
    goto LABEL_43;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = 25;
LABEL_22:
    WPP_SF_d(v15[2], v16, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids, (unsigned int)Element);
  }
LABEL_43:
  VariantClear(&pvarg);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v10 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v22 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v23 + 16), 27, (unsigned int)WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids, v22, v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003f9a4  mov     [rsp-28h+arg_8], rbx
0x18003f9a9  push    rbp
0x18003f9aa  push    rsi
0x18003f9ab  push    rdi
0x18003f9ac  push    r14
0x18003f9ae  push    r15
0x18003f9b0  mov     rbp, rsp
0x18003f9b3  sub     rsp, 50h
0x18003f9b7  xor     eax, eax
0x18003f9b9  xorps   xmm0, xmm0
0x18003f9bc  movups  xmmword ptr [rbp+pvarg], xmm0
0x18003f9c0  mov     qword ptr [rbp+pvarg+10h], rax
0x18003f9c4  mov     rsi, rdx
0x18003f9c7  mov     [rbp+rgIndices], eax
0x18003f9ca  mov     rbx, rcx
0x18003f9cd  mov     [rbp+ppvData], rax
0x18003f9d1  mov     r10, cs:WPP_GLOBAL_Control
0x18003f9d8  lea     r14, WPP_GLOBAL_Control
0x18003f9df  lea     edi, [rax+1]
0x18003f9e2  lea     r15, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids
0x18003f9e9  cmp     r10, r14
0x18003f9ec  jz      short loc_18003FA15
0x18003f9ee  cmp     byte ptr [r10+19h], 6
0x18003f9f3  jb      short loc_18003FA15
0x18003f9f5  mov     ecx, edi; int
0x18003f9f7  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003f9fc  mov     rcx, [r10+10h]
0x18003fa00  lea     edx, [rdi+11h]
0x18003fa03  mov     r9, rax
0x18003fa06  mov     r8, r15
0x18003fa09  call    WPP_SF_s
0x18003fa0e  mov     r10, cs:WPP_GLOBAL_Control
0x18003fa15  test    rbx, rbx
0x18003fa18  jnz     short loc_18003FA32
0x18003fa1a  cmp     r10, r14
0x18003fa1d  jz      short loc_18003FA59
0x18003fa1f  cmp     byte ptr [r10+19h], 2
0x18003fa24  jb      short loc_18003FA59
0x18003fa26  lea     edx, [rbx+13h]
0x18003fa29  lea     r9, aPvaroutputarg; "pvarOutputArg"
0x18003fa30  jmp     short loc_18003FA4D
0x18003fa32  test    rsi, rsi
0x18003fa35  jnz     short loc_18003FA63
0x18003fa37  cmp     r10, r14
0x18003fa3a  jz      short loc_18003FA59
0x18003fa3c  cmp     byte ptr [r10+19h], 2
0x18003fa41  jb      short loc_18003FA59
0x18003fa43  lea     edx, [rsi+14h]
0x18003fa46  lea     r9, aPblob; "pBlob"
0x18003fa4d  mov     rcx, [r10+10h]
0x18003fa51  mov     r8, r15
0x18003fa54  call    WPP_SF_s
0x18003fa59  mov     eax, 80004003h
0x18003fa5e  jmp     loc_18003FC63
0x18003fa63  lea     rcx, [rbp+pvarg]; pvarg
0x18003fa67  call    cs:__imp_VariantInit
0x18003fa6d  mov     eax, 200Ch
0x18003fa72  cmp     [rbx], ax
0x18003fa75  jz      short loc_18003FAA8
0x18003fa77  mov     ebx, 8000FFFFh
0x18003fa7c  mov     r10, cs:WPP_GLOBAL_Control
0x18003fa83  cmp     r10, r14
0x18003fa86  jz      loc_18003FC20
0x18003fa8c  cmp     byte ptr [r10+19h], 2
0x18003fa91  jb      loc_18003FC20
0x18003fa97  xor     ecx, ecx; int
0x18003fa99  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003fa9e  mov     edx, 15h
0x18003faa3  jmp     loc_18003FC11
0x18003faa8  mov     rcx, [rbx+8]; psa
0x18003faac  lea     r8, [rbp+pvarg]; pv
0x18003fab0  lea     rdx, [rbp+rgIndices]; rgIndices
0x18003fab4  call    cs:__imp_SafeArrayGetElement
0x18003faba  mov     ebx, eax
0x18003fabc  test    eax, eax
0x18003fabe  jns     short loc_18003FAF3
0x18003fac0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fac7  cmp     rcx, r14
0x18003faca  jz      loc_18003FC20
0x18003fad0  cmp     byte ptr [rcx+19h], 2
0x18003fad4  jb      loc_18003FC20
0x18003fada  mov     edx, 16h
0x18003fadf  mov     rcx, [rcx+10h]
0x18003fae3  mov     r9d, eax
0x18003fae6  mov     r8, r15
0x18003fae9  call    WPP_SF_d
0x18003faee  jmp     loc_18003FC20
0x18003faf3  mov     eax, 2011h
0x18003faf8  cmp     word ptr [rbp+pvarg], ax
0x18003fafc  jnz     loc_18003FBED
0x18003fb02  mov     rcx, qword ptr [rbp+pvarg+8]; psa
0x18003fb06  cmp     [rcx], di
0x18003fb09  jnz     loc_18003FBED
0x18003fb0f  mov     edi, [rcx+18h]
0x18003fb12  mov     r11d, 2800h
0x18003fb18  cmp     rdi, r11
0x18003fb1b  jbe     short loc_18003FB66
0x18003fb1d  mov     ebx, 8004B008h
0x18003fb22  mov     r10, cs:WPP_GLOBAL_Control
0x18003fb29  cmp     r10, r14
0x18003fb2c  jz      loc_18003FC20
0x18003fb32  cmp     byte ptr [r10+19h], 2
0x18003fb37  jb      loc_18003FC20
0x18003fb3d  xor     ecx, ecx; int
0x18003fb3f  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003fb44  mov     rcx, [r10+10h]
0x18003fb48  mov     edx, 18h
0x18003fb4d  mov     [rsp+50h+var_28], r11d
0x18003fb52  mov     r9, rax
0x18003fb55  mov     r8, r15
0x18003fb58  mov     [rsp+50h+var_30], edi
0x18003fb5c  call    WPP_SF_sld
0x18003fb61  jmp     loc_18003FC20
0x18003fb66  lea     rdx, [rbp+ppvData]; ppvData
0x18003fb6a  call    cs:__imp_SafeArrayAccessData
0x18003fb70  mov     ebx, eax
0x18003fb72  test    eax, eax
0x18003fb74  jns     short loc_18003FB9A
0x18003fb76  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fb7d  cmp     rcx, r14
0x18003fb80  jz      loc_18003FC20
0x18003fb86  cmp     byte ptr [rcx+19h], 2
0x18003fb8a  jb      loc_18003FC20
0x18003fb90  mov     edx, 19h
0x18003fb95  jmp     loc_18003FADF
0x18003fb9a  mov     rdx, [rbp+ppvData]; unsigned __int8 *
0x18003fb9e  mov     r8, rdi; unsigned __int64
0x18003fba1  mov     rcx, rsi; this
0x18003fba4  call    ?CopyFromBuffer@CSbSafeBuffer@@QEAAJPEBE_K@Z; CSbSafeBuffer::CopyFromBuffer(uchar const *,unsigned __int64)
0x18003fba9  mov     ebx, eax
0x18003fbab  test    eax, eax
0x18003fbad  jns     short loc_18003FBD7
0x18003fbaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fbb6  cmp     rcx, r14
0x18003fbb9  jz      short loc_18003FBE1
0x18003fbbb  cmp     byte ptr [rcx+19h], 2
0x18003fbbf  jb      short loc_18003FBE1
0x18003fbc1  mov     rcx, [rcx+10h]
0x18003fbc5  mov     edx, 1Ah
0x18003fbca  mov     r9d, eax
0x18003fbcd  mov     r8, r15
0x18003fbd0  call    WPP_SF_d
0x18003fbd5  jmp     short loc_18003FBE1
0x18003fbd7  lea     rcx, [rsi+20h]; Uuid
0x18003fbdb  call    cs:__imp_UuidCreate
0x18003fbe1  mov     rcx, qword ptr [rbp+pvarg+8]; psa
0x18003fbe5  call    cs:__imp_SafeArrayUnaccessData
0x18003fbeb  jmp     short loc_18003FC20
0x18003fbed  mov     ebx, 8004B008h
0x18003fbf2  mov     r10, cs:WPP_GLOBAL_Control
0x18003fbf9  cmp     r10, r14
0x18003fbfc  jz      short loc_18003FC20
0x18003fbfe  cmp     byte ptr [r10+19h], 2
0x18003fc03  jb      short loc_18003FC20
0x18003fc05  xor     ecx, ecx; int
0x18003fc07  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003fc0c  mov     edx, 17h
0x18003fc11  mov     rcx, [r10+10h]
0x18003fc15  mov     r9, rax
0x18003fc18  mov     r8, r15
0x18003fc1b  call    WPP_SF_s
0x18003fc20  lea     rcx, [rbp+pvarg]; pvarg
0x18003fc24  call    cs:__imp_VariantClear
0x18003fc2a  mov     r10, cs:WPP_GLOBAL_Control
0x18003fc31  cmp     r10, r14
0x18003fc34  jz      short loc_18003FC61
0x18003fc36  test    ebx, ebx
0x18003fc38  js      short loc_18003FC41
0x18003fc3a  cmp     byte ptr [r10+19h], 6
0x18003fc3f  jb      short loc_18003FC61
0x18003fc41  or      ecx, 0FFFFFFFFh; int
0x18003fc44  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003fc49  mov     rcx, [r10+10h]
0x18003fc4d  mov     edx, 1Bh
0x18003fc52  mov     r9, rax
0x18003fc55  mov     [rsp+50h+var_30], ebx
0x18003fc59  mov     r8, r15
0x18003fc5c  call    WPP_SF_sd
0x18003fc61  mov     eax, ebx
0x18003fc63  mov     rbx, [rsp+50h+arg_8]
0x18003fc6b  add     rsp, 50h
0x18003fc6f  pop     r15
0x18003fc71  pop     r14
0x18003fc73  pop     rdi
0x18003fc74  pop     rsi
0x18003fc75  pop     rbp
0x18003fc76  retn
```
