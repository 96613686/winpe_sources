# WcnMarshalVendorExtensionBundle

- ea: `0x180033904`
- end: `0x180033bc3`
- name: `WcnMarshalVendorExtensionBundle`
- size: `703`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x180035a70`
- `0x180036a10`

## callees

- `0x180002940`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000a808`
- `0x180033904`
- `0x180053004`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180033b7a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180033baa`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180033b7a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180033baa`

## string_xrefs

- `0x180033978`: `ppExtensions`
- `0x1800339fb`: `pBundle->pExtensions`

## pseudocode

```c
__int64 __fastcall WcnMarshalVendorExtensionBundle(unsigned __int64 a1, __int64 a2, __int64 a3)
{
  _BYTE *v6; // r10
  const char *Indent; // rax
  __int64 v8; // r10
  __int64 v9; // rdx
  const char *v10; // r9
  void *v12; // rax
  int v13; // ebx
  _QWORD *v14; // r10
  __int64 v15; // rdx
  const char *v16; // r9
  unsigned __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rsi
  CSbSafeBuffer *v20; // r15
  __int64 v21; // r14
  _QWORD *v22; // rcx
  __int64 v23; // rax
  unsigned __int8 *v24; // rax
  int v25; // eax
  unsigned int v26; // eax
  __int64 v27; // r10
  unsigned __int64 i; // rsi
  void *v29; // rcx
  void *v30; // rcx

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v8 + 16), 139, WPP_b6f763267c4d324c721a67068f3e4818_Traceguids, Indent);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v6 == (_BYTE *)&WPP_GLOBAL_Control || v6[25] < 2u )
      return 2147500035LL;
    v9 = 140;
    v10 = "ppExtensions";
LABEL_12:
    WPP_SF_s(*((_QWORD *)v6 + 2), v9, WPP_b6f763267c4d324c721a67068f3e4818_Traceguids, v10);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    if ( v6 == (_BYTE *)&WPP_GLOBAL_Control || v6[25] < 2u )
      return 2147500035LL;
    v9 = 141;
    v10 = "pBundle";
    goto LABEL_12;
  }
  *(_DWORD *)a3 = 0;
  v12 = operator new[](16 * a1, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)(a3 + 8) = v12;
  if ( v12 )
  {
    v13 = 0;
    v17 = 0;
    if ( !a1 )
    {
LABEL_27:
      *(_DWORD *)a3 = a1;
LABEL_28:
      v14 = WPP_GLOBAL_Control;
      goto LABEL_29;
    }
    do
    {
      v18 = 2 * v17++;
      *(_DWORD *)(*(_QWORD *)(a3 + 8) + 8 * v18) = 0;
    }
    while ( v17 < a1 );
    v19 = 0;
    while ( 1 )
    {
      v20 = *(CSbSafeBuffer **)(a2 + 8 * v19);
      v21 = *(_QWORD *)(a3 + 8);
      v22 = (_QWORD *)*((_QWORD *)v20 + 3);
      if ( v22 )
        v23 = v22[1] - *v22;
      else
        LODWORD(v23) = 0;
      *(_DWORD *)(v21 + 16 * v19) = v23;
      v24 = (unsigned __int8 *)operator new[]((unsigned int)v23, (const struct std::nothrow_t *)&std::nothrow);
      *(_QWORD *)(v21 + 16 * v19 + 8) = v24;
      if ( !v24 )
        break;
      v25 = CSbSafeBuffer::CopyToBuffer(v20, v24, *(unsigned int *)(v21 + 16 * v19));
      v13 = v25;
      if ( v25 < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            144,
            WPP_b6f763267c4d324c721a67068f3e4818_Traceguids,
            (unsigned int)v25);
          goto LABEL_41;
        }
        goto LABEL_42;
      }
      if ( ++v19 >= a1 )
        goto LABEL_27;
    }
    v13 = -2147024882;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 143;
      v16 = "Ext.pbBlob";
      goto LABEL_40;
    }
  }
  else
  {
    v13 = -2147024882;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 142;
      v16 = "pBundle->pExtensions";
LABEL_40:
      WPP_SF_s(v14[2], v15, WPP_b6f763267c4d324c721a67068f3e4818_Traceguids, v16);
LABEL_41:
      v14 = WPP_GLOBAL_Control;
    }
  }
LABEL_42:
  if ( *(_QWORD *)(a3 + 8) )
  {
    for ( i = 0; i < a1; ++i )
    {
      v29 = *(void **)(*(_QWORD *)(a3 + 8) + 16 * i + 8);
      if ( v29 )
      {
        operator delete[](v29);
        *(_DWORD *)(*(_QWORD *)(a3 + 8) + 16 * i) = 0;
        *(_QWORD *)(*(_QWORD *)(a3 + 8) + 16 * i + 8) = 0;
      }
    }
    v30 = *(void **)(a3 + 8);
    if ( v30 )
      operator delete[](v30);
    *(_QWORD *)(a3 + 8) = 0;
    *(_DWORD *)a3 = 0;
    goto LABEL_28;
  }
LABEL_29:
  if ( v14 != &WPP_GLOBAL_Control && (v13 < 0 || *((_BYTE *)v14 + 25) >= 6u) )
  {
    v26 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v27 + 16), 145, (unsigned int)WPP_b6f763267c4d324c721a67068f3e4818_Traceguids, v26, v13);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180033904  push    rbx
0x180033906  push    rbp
0x180033907  push    rsi
0x180033908  push    rdi
0x180033909  push    r12
0x18003390b  push    r14
0x18003390d  push    r15
0x18003390f  sub     rsp, 30h
0x180033913  mov     rdi, r8
0x180033916  mov     r12, rdx
0x180033919  mov     rbp, rcx
0x18003391c  mov     r10, cs:WPP_GLOBAL_Control
0x180033923  lea     r15, WPP_GLOBAL_Control
0x18003392a  lea     rsi, WPP_b6f763267c4d324c721a67068f3e4818_Traceguids
0x180033931  cmp     r10, r15
0x180033934  jz      short loc_180033962
0x180033936  cmp     byte ptr [r10+19h], 6
0x18003393b  jb      short loc_180033962
0x18003393d  mov     ecx, 1; int
0x180033942  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180033947  mov     rcx, [r10+10h]
0x18003394b  mov     edx, 8Bh
0x180033950  mov     r9, rax
0x180033953  mov     r8, rsi
0x180033956  call    WPP_SF_s
0x18003395b  mov     r10, cs:WPP_GLOBAL_Control
0x180033962  test    r12, r12
0x180033965  jnz     short loc_180033981
0x180033967  cmp     r10, r15
0x18003396a  jz      short loc_1800339AA
0x18003396c  cmp     byte ptr [r10+19h], 2
0x180033971  jb      short loc_1800339AA
0x180033973  mov     edx, 8Ch
0x180033978  lea     r9, aPpextensions; "ppExtensions"
0x18003397f  jmp     short loc_18003399E
0x180033981  test    rdi, rdi
0x180033984  jnz     short loc_1800339B4
0x180033986  cmp     r10, r15
0x180033989  jz      short loc_1800339AA
0x18003398b  cmp     byte ptr [r10+19h], 2
0x180033990  jb      short loc_1800339AA
0x180033992  mov     edx, 8Dh
0x180033997  lea     r9, aPbundle; "pBundle"
0x18003399e  mov     rcx, [r10+10h]
0x1800339a2  mov     r8, rsi
0x1800339a5  call    WPP_SF_s
0x1800339aa  mov     eax, 80004003h
0x1800339af  jmp     loc_180033ACF
0x1800339b4  mov     rcx, rbp
0x1800339b7  mov     dword ptr [rdi], 0
0x1800339bd  shl     rcx, 4; unsigned __int64
0x1800339c1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800339c8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800339cd  mov     [rdi+8], rax
0x1800339d1  test    rax, rax
0x1800339d4  jnz     short loc_180033A0A
0x1800339d6  mov     ebx, 8007000Eh
0x1800339db  mov     r10, cs:WPP_GLOBAL_Control
0x1800339e2  cmp     r10, r15
0x1800339e5  jz      loc_180033B54
0x1800339eb  cmp     byte ptr [r10+19h], 2
0x1800339f0  jb      loc_180033B54
0x1800339f6  mov     edx, 8Eh
0x1800339fb  lea     r9, aPbundlePextens; "pBundle->pExtensions"
0x180033a02  mov     r8, rsi
0x180033a05  jmp     loc_180033B44
0x180033a0a  xor     ebx, ebx
0x180033a0c  xor     edx, edx
0x180033a0e  test    rbp, rbp
0x180033a11  jz      short loc_180033A90
0x180033a13  mov     rax, [rdi+8]
0x180033a17  mov     rcx, rdx
0x180033a1a  add     rcx, rcx
0x180033a1d  inc     rdx
0x180033a20  mov     [rax+rcx*8], ebx
0x180033a23  cmp     rdx, rbp
0x180033a26  jb      short loc_180033A13
0x180033a28  xor     esi, esi
0x180033a2a  mov     r15, [r12+rsi*8]
0x180033a2e  mov     rbx, rsi
0x180033a31  mov     r14, [rdi+8]
0x180033a35  add     rbx, rbx
0x180033a38  mov     rcx, [r15+18h]
0x180033a3c  test    rcx, rcx
0x180033a3f  jz      short loc_180033A4A
0x180033a41  mov     rax, [rcx+8]
0x180033a45  sub     rax, [rcx]
0x180033a48  jmp     short loc_180033A4C
0x180033a4a  xor     eax, eax
0x180033a4c  mov     ecx, eax; unsigned __int64
0x180033a4e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180033a55  mov     [r14+rbx*8], ecx
0x180033a59  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180033a5e  mov     [r14+rbx*8+8], rax
0x180033a63  test    rax, rax
0x180033a66  jz      loc_180033B12
0x180033a6c  mov     r8d, [r14+rbx*8]; unsigned __int64
0x180033a70  mov     rdx, rax; unsigned __int8 *
0x180033a73  mov     rcx, r15; this
0x180033a76  call    ?CopyToBuffer@CSbSafeBuffer@@QEBAJPEAE_K@Z; CSbSafeBuffer::CopyToBuffer(uchar *,unsigned __int64)
0x180033a7b  mov     ebx, eax
0x180033a7d  test    eax, eax
0x180033a7f  js      short loc_180033ADE
0x180033a81  inc     rsi
0x180033a84  cmp     rsi, rbp
0x180033a87  jb      short loc_180033A2A
0x180033a89  lea     r15, WPP_GLOBAL_Control
0x180033a90  mov     [rdi], ebp
0x180033a92  mov     r10, cs:WPP_GLOBAL_Control
0x180033a99  cmp     r10, r15
0x180033a9c  jz      short loc_180033ACD
0x180033a9e  test    ebx, ebx
0x180033aa0  js      short loc_180033AA9
0x180033aa2  cmp     byte ptr [r10+19h], 6
0x180033aa7  jb      short loc_180033ACD
0x180033aa9  or      ecx, 0FFFFFFFFh; int
0x180033aac  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180033ab1  mov     rcx, [r10+10h]
0x180033ab5  lea     r8, WPP_b6f763267c4d324c721a67068f3e4818_Traceguids
0x180033abc  mov     edx, 91h
0x180033ac1  mov     [rsp+68h+var_48], ebx
0x180033ac5  mov     r9, rax
0x180033ac8  call    WPP_SF_sd
0x180033acd  mov     eax, ebx
0x180033acf  add     rsp, 30h
0x180033ad3  pop     r15
0x180033ad5  pop     r14
0x180033ad7  pop     r12
0x180033ad9  pop     rdi
0x180033ada  pop     rsi
0x180033adb  pop     rbp
0x180033adc  pop     rbx
0x180033add  retn
0x180033ade  mov     r10, cs:WPP_GLOBAL_Control
0x180033ae5  lea     r15, WPP_GLOBAL_Control
0x180033aec  cmp     r10, r15
0x180033aef  jz      short loc_180033B54
0x180033af1  cmp     byte ptr [r10+19h], 2
0x180033af6  jb      short loc_180033B54
0x180033af8  mov     rcx, [r10+10h]
0x180033afc  lea     r8, WPP_b6f763267c4d324c721a67068f3e4818_Traceguids
0x180033b03  mov     edx, 90h
0x180033b08  mov     r9d, eax
0x180033b0b  call    WPP_SF_d
0x180033b10  jmp     short loc_180033B4D
0x180033b12  mov     ebx, 8007000Eh
0x180033b17  mov     r10, cs:WPP_GLOBAL_Control
0x180033b1e  lea     r15, WPP_GLOBAL_Control
0x180033b25  cmp     r10, r15
0x180033b28  jz      short loc_180033B54
0x180033b2a  cmp     byte ptr [r10+19h], 2
0x180033b2f  jb      short loc_180033B54
0x180033b31  mov     edx, 8Fh
0x180033b36  lea     r9, aExtPbblob; "Ext.pbBlob"
0x180033b3d  lea     r8, WPP_b6f763267c4d324c721a67068f3e4818_Traceguids
0x180033b44  mov     rcx, [r10+10h]
0x180033b48  call    WPP_SF_s
0x180033b4d  mov     r10, cs:WPP_GLOBAL_Control
0x180033b54  cmp     qword ptr [rdi+8], 0
0x180033b59  jz      loc_180033A99
0x180033b5f  xor     esi, esi
0x180033b61  test    rbp, rbp
0x180033b64  jz      short loc_180033BA1
0x180033b66  mov     rax, [rdi+8]
0x180033b6a  mov     r14, rsi
0x180033b6d  add     r14, r14
0x180033b70  mov     rcx, [rax+r14*8+8]
0x180033b75  test    rcx, rcx
0x180033b78  jz      short loc_180033B99
0x180033b7a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180033b80  mov     rax, [rdi+8]
0x180033b84  mov     dword ptr [rax+r14*8], 0
0x180033b8c  mov     rax, [rdi+8]
0x180033b90  mov     qword ptr [rax+r14*8+8], 0
0x180033b99  inc     rsi
0x180033b9c  cmp     rsi, rbp
0x180033b9f  jb      short loc_180033B66
0x180033ba1  mov     rcx, [rdi+8]
0x180033ba5  test    rcx, rcx
0x180033ba8  jz      short loc_180033BB0
0x180033baa  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180033bb0  mov     qword ptr [rdi+8], 0
0x180033bb8  mov     dword ptr [rdi], 0
0x180033bbe  jmp     loc_180033A92
```
