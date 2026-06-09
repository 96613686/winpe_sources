# WcnUpnpGetVariantFromBlob

- ea: `0x18003fc80`
- end: `0x18003fec2`
- name: `WcnUpnpGetVariantFromBlob`
- size: `578`
- prototype: `__int64 __fastcall(CSbSafeBuffer *this, VARIANTARG *pvarg)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18003ff58`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000a808`
- `0x18003fc80`
- `0x180053004`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003fd34`
- `OLEAUT32!__imp_VariantInit` at `0x18003fd34`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18003fd66`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18003fd66`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18003fe60`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18003fe60`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18003fdb5`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18003fdb5`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18003fe22`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18003fe57`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18003fe22`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18003fe57`

## pseudocode

```c
__int64 __fastcall WcnUpnpGetVariantFromBlob(CSbSafeBuffer *this, VARIANTARG *pvarg)
{
  _BYTE *v4; // r10
  const char *Indent; // rax
  __int64 v6; // r10
  __int64 v7; // rdx
  const char *v8; // r9
  _QWORD *v10; // rax
  unsigned __int64 v11; // rsi
  SAFEARRAY *v12; // rax
  LONGLONG v13; // rdi
  int v14; // ebx
  _BYTE *v15; // r10
  const char *v16; // rax
  __int64 v17; // r10
  HRESULT v18; // eax
  int v19; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  unsigned int v22; // eax
  __int64 v23; // r10
  SAFEARRAYBOUND rgsabound; // [rsp+60h] [rbp+8h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 10, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids, Indent);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !this )
  {
    if ( v4 == (_BYTE *)&WPP_GLOBAL_Control || v4[25] < 2u )
      return 2147500035LL;
    v7 = 11;
    v8 = "pBlob";
LABEL_12:
    WPP_SF_s(*((_QWORD *)v4 + 2), v7, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids, v8);
    return 2147500035LL;
  }
  if ( !pvarg )
  {
    if ( v4 == (_BYTE *)&WPP_GLOBAL_Control || v4[25] < 2u )
      return 2147500035LL;
    v7 = 12;
    v8 = "pvar";
    goto LABEL_12;
  }
  VariantInit(pvarg);
  v10 = (_QWORD *)*((_QWORD *)this + 3);
  if ( v10 )
    v11 = v10[1] - *v10;
  else
    v11 = 0;
  rgsabound.lLbound = 0;
  rgsabound.cElements = v11;
  v12 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  v13 = (LONGLONG)v12;
  if ( v12 )
  {
    v18 = SafeArrayLock(v12);
    v14 = v18;
    if ( v18 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids,
          (unsigned int)v18);
      goto LABEL_35;
    }
    v19 = CSbSafeBuffer::CopyToBuffer(this, *(unsigned __int8 **)(v13 + 16), v11);
    v14 = v19;
    if ( v19 >= 0 )
    {
      v19 = SafeArrayUnlock((SAFEARRAY *)v13);
      v14 = v19;
      if ( v19 >= 0 )
      {
        pvarg->vt = 8209;
        pvarg->llVal = v13;
        goto LABEL_37;
      }
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_34;
      v21 = 16;
    }
    else
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_34;
      v21 = 15;
    }
    WPP_SF_d(v20[2], v21, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids, (unsigned int)v19);
LABEL_34:
    SafeArrayUnlock((SAFEARRAY *)v13);
LABEL_35:
    SafeArrayDestroy((SAFEARRAY *)v13);
    goto LABEL_37;
  }
  v14 = -2147024882;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_38:
      if ( v15 != (_BYTE *)&WPP_GLOBAL_Control && (v14 < 0 || v15[25] >= 6u) )
      {
        v22 = (unsigned int)GetIndent(-1);
        WPP_SF_sd(*(_QWORD *)(v23 + 16), 17, (unsigned int)WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids, v22, v14);
      }
      return (unsigned int)v14;
    }
    v16 = GetIndent(0);
    WPP_SF_s(*(_QWORD *)(v17 + 16), 13, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids, v16);
LABEL_37:
    v15 = WPP_GLOBAL_Control;
    goto LABEL_38;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18003fc80  mov     [rsp+arg_8], rbx
0x18003fc85  mov     [rsp+arg_10], rbp
0x18003fc8a  push    rsi
0x18003fc8b  push    rdi
0x18003fc8c  push    r12
0x18003fc8e  push    r14
0x18003fc90  push    r15
0x18003fc92  sub     rsp, 30h
0x18003fc96  mov     r14, rdx
0x18003fc99  mov     rbp, rcx
0x18003fc9c  mov     r10, cs:WPP_GLOBAL_Control
0x18003fca3  lea     r15, WPP_GLOBAL_Control
0x18003fcaa  lea     r12, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids
0x18003fcb1  mov     ebx, 1
0x18003fcb6  cmp     r10, r15
0x18003fcb9  jz      short loc_18003FCE2
0x18003fcbb  cmp     byte ptr [r10+19h], 6
0x18003fcc0  jb      short loc_18003FCE2
0x18003fcc2  mov     ecx, ebx; int
0x18003fcc4  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003fcc9  mov     rcx, [r10+10h]
0x18003fccd  lea     edx, [rbx+9]
0x18003fcd0  mov     r9, rax
0x18003fcd3  mov     r8, r12
0x18003fcd6  call    WPP_SF_s
0x18003fcdb  mov     r10, cs:WPP_GLOBAL_Control
0x18003fce2  test    rbp, rbp
0x18003fce5  jnz     short loc_18003FCFF
0x18003fce7  cmp     r10, r15
0x18003fcea  jz      short loc_18003FD27
0x18003fcec  cmp     byte ptr [r10+19h], 2
0x18003fcf1  jb      short loc_18003FD27
0x18003fcf3  lea     edx, [rbp+0Bh]
0x18003fcf6  lea     r9, aPblob; "pBlob"
0x18003fcfd  jmp     short loc_18003FD1B
0x18003fcff  test    r14, r14
0x18003fd02  jnz     short loc_18003FD31
0x18003fd04  cmp     r10, r15
0x18003fd07  jz      short loc_18003FD27
0x18003fd09  cmp     byte ptr [r10+19h], 2
0x18003fd0e  jb      short loc_18003FD27
0x18003fd10  lea     edx, [r14+0Ch]
0x18003fd14  lea     r9, aPvar; "pvar"
0x18003fd1b  mov     rcx, [r10+10h]
0x18003fd1f  mov     r8, r12
0x18003fd22  call    WPP_SF_s
0x18003fd27  mov     eax, 80004003h
0x18003fd2c  jmp     loc_18003FEAB
0x18003fd31  mov     rcx, r14; pvarg
0x18003fd34  call    cs:__imp_VariantInit
0x18003fd3a  mov     rax, [rbp+18h]
0x18003fd3e  test    rax, rax
0x18003fd41  jz      short loc_18003FD4C
0x18003fd43  mov     rsi, [rax+8]
0x18003fd47  sub     rsi, [rax]
0x18003fd4a  jmp     short loc_18003FD4E
0x18003fd4c  xor     esi, esi
0x18003fd4e  mov     ecx, 11h; vt
0x18003fd53  mov     [rsp+58h+rgsabound.lLbound], 0
0x18003fd5b  lea     r8, [rsp+58h+rgsabound]; rgsabound
0x18003fd60  mov     [rsp+58h+rgsabound.cElements], esi
0x18003fd64  mov     edx, ebx; cDims
0x18003fd66  call    cs:__imp_SafeArrayCreate
0x18003fd6c  mov     rdi, rax
0x18003fd6f  test    rax, rax
0x18003fd72  jnz     short loc_18003FDB2
0x18003fd74  mov     ebx, 8007000Eh
0x18003fd79  mov     r10, cs:WPP_GLOBAL_Control
0x18003fd80  cmp     r10, r15
0x18003fd83  jz      loc_18003FEA9
0x18003fd89  cmp     byte ptr [r10+19h], 2
0x18003fd8e  jb      loc_18003FE79
0x18003fd94  xor     ecx, ecx; int
0x18003fd96  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003fd9b  mov     rcx, [r10+10h]
0x18003fd9f  lea     edx, [rdi+0Dh]
0x18003fda2  mov     r9, rax
0x18003fda5  mov     r8, r12
0x18003fda8  call    WPP_SF_s
0x18003fdad  jmp     loc_18003FE72
0x18003fdb2  mov     rcx, rdi; psa
0x18003fdb5  call    cs:__imp_SafeArrayLock
0x18003fdbb  mov     ebx, eax
0x18003fdbd  test    eax, eax
0x18003fdbf  jns     short loc_18003FDF1
0x18003fdc1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fdc8  cmp     rcx, r15
0x18003fdcb  jz      loc_18003FE5D
0x18003fdd1  cmp     byte ptr [rcx+19h], 2
0x18003fdd5  jb      loc_18003FE5D
0x18003fddb  mov     rcx, [rcx+10h]
0x18003fddf  mov     edx, 0Eh
0x18003fde4  mov     r9d, eax
0x18003fde7  mov     r8, r12
0x18003fdea  call    WPP_SF_d
0x18003fdef  jmp     short loc_18003FE5D
0x18003fdf1  mov     rdx, [rdi+10h]; unsigned __int8 *
0x18003fdf5  mov     r8, rsi; unsigned __int64
0x18003fdf8  mov     rcx, rbp; this
0x18003fdfb  call    ?CopyToBuffer@CSbSafeBuffer@@QEBAJPEAE_K@Z; CSbSafeBuffer::CopyToBuffer(uchar *,unsigned __int64)
0x18003fe00  mov     ebx, eax
0x18003fe02  test    eax, eax
0x18003fe04  jns     short loc_18003FE1F
0x18003fe06  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fe0d  cmp     rcx, r15
0x18003fe10  jz      short loc_18003FE54
0x18003fe12  cmp     byte ptr [rcx+19h], 2
0x18003fe16  jb      short loc_18003FE54
0x18003fe18  mov     edx, 0Fh
0x18003fe1d  jmp     short loc_18003FE45
0x18003fe1f  mov     rcx, rdi; psa
0x18003fe22  call    cs:__imp_SafeArrayUnlock
0x18003fe28  mov     ebx, eax
0x18003fe2a  test    eax, eax
0x18003fe2c  jns     short loc_18003FE68
0x18003fe2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fe35  cmp     rcx, r15
0x18003fe38  jz      short loc_18003FE54
0x18003fe3a  cmp     byte ptr [rcx+19h], 2
0x18003fe3e  jb      short loc_18003FE54
0x18003fe40  mov     edx, 10h
0x18003fe45  mov     rcx, [rcx+10h]
0x18003fe49  mov     r9d, eax
0x18003fe4c  mov     r8, r12
0x18003fe4f  call    WPP_SF_d
0x18003fe54  mov     rcx, rdi; psa
0x18003fe57  call    cs:__imp_SafeArrayUnlock
0x18003fe5d  mov     rcx, rdi; psa
0x18003fe60  call    cs:__imp_SafeArrayDestroy
0x18003fe66  jmp     short loc_18003FE72
0x18003fe68  mov     word ptr [r14], 2011h
0x18003fe6e  mov     [r14+8], rdi
0x18003fe72  mov     r10, cs:WPP_GLOBAL_Control
0x18003fe79  cmp     r10, r15
0x18003fe7c  jz      short loc_18003FEA9
0x18003fe7e  test    ebx, ebx
0x18003fe80  js      short loc_18003FE89
0x18003fe82  cmp     byte ptr [r10+19h], 6
0x18003fe87  jb      short loc_18003FEA9
0x18003fe89  or      ecx, 0FFFFFFFFh; int
0x18003fe8c  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003fe91  mov     rcx, [r10+10h]
0x18003fe95  mov     edx, 11h
0x18003fe9a  mov     r9, rax
0x18003fe9d  mov     [rsp+58h+var_38], ebx
0x18003fea1  mov     r8, r12
0x18003fea4  call    WPP_SF_sd
0x18003fea9  mov     eax, ebx
0x18003feab  mov     rbx, [rsp+58h+arg_8]
0x18003feb0  mov     rbp, [rsp+58h+arg_10]
0x18003feb5  add     rsp, 30h
0x18003feb9  pop     r15
0x18003febb  pop     r14
0x18003febd  pop     r12
0x18003febf  pop     rdi
0x18003fec0  pop     rsi
0x18003fec1  retn
```
