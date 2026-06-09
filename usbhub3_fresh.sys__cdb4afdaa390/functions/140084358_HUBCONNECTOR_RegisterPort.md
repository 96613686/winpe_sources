# HUBCONNECTOR_RegisterPort

- ea: `0x140084358`
- end: `0x140084790`
- name: `HUBCONNECTOR_RegisterPort`
- size: `1080`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140083da8`
- `0x140083e7c`
- `0x140083fa4`
- `0x14008408c`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x140045570`
- `0x140084358`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140084415`
- `ntoskrnl!RtlCompareMemory` at `0x140084415`
- `ntoskrnl!ExAllocatePool2` at `0x14008444d`
- `ntoskrnl!ExAllocatePool2` at `0x14008444d`

## pseudocode

```c
__int64 __fastcall HUBCONNECTOR_RegisterPort(__int64 a1)
{
  __int64 v2; // rbp
  __int64 v3; // rax
  _QWORD *v4; // r14
  _QWORD *i; // rax
  volatile signed __int32 *v6; // rdx
  _QWORD *v7; // rsi
  __int64 Pool2; // rax
  unsigned int v9; // ebx
  _QWORD *v10; // rax
  int v11; // eax
  int v12; // r9d
  int v13; // r8d
  __int64 v14; // rcx
  int v15; // eax
  int v16; // r9d
  int v17; // r9d
  unsigned __int16 v18; // cx
  __int64 v19; // rax
  __int64 v21; // [rsp+28h] [rbp-30h]

  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         WdfDriverGlobals->Driver,
         off_14006B2C0);
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         WdfDriverGlobals->Driver,
         off_14006B2C0);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2504))(
    WdfDriverGlobals,
    *(_QWORD *)(v3 + 56),
    0);
  v4 = (_QWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
                    WdfDriverGlobals,
                    WdfDriverGlobals->Driver,
                    off_14006B2C0)
                + 40);
  for ( i = (_QWORD *)*v4; ; i = (_QWORD *)v7[10] )
  {
    v7 = i - 10;
    if ( v4 == i )
      goto LABEL_7;
    if ( RtlCompareMemory(i - 10, (const void *)(a1 + 1368), 0x38u) == 56 )
      break;
  }
  if ( v7 )
  {
LABEL_14:
    v11 = *(_DWORD *)(a1 + 208);
    v9 = 0;
    if ( v11 == 512 )
    {
      if ( v7[7] )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_49;
        v16 = 11;
        goto LABEL_24;
      }
      v6 = (volatile signed __int32 *)(a1 + 204);
      if ( (*(_DWORD *)(a1 + 204) & 0x200) != 0 )
      {
        v14 = v7[8];
        if ( v14 && (*(_DWORD *)(v14 + 204) & 0x200) == 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_49;
          v17 = 12;
          goto LABEL_48;
        }
        *(_WORD *)(a1 + 236) = *(_WORD *)(a1 + 200);
      }
      v7[7] = a1;
    }
    else
    {
      if ( v11 != 768 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_55;
        v12 = 17;
        LODWORD(v21) = *(_DWORD *)(a1 + 208);
        v13 = 6;
        goto LABEL_18;
      }
      v14 = v7[8];
      v6 = (volatile signed __int32 *)(a1 + 204);
      v15 = *(_DWORD *)(a1 + 204) & 0x200;
      if ( v14 )
      {
        if ( !v15 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_49;
          v16 = 15;
          goto LABEL_24;
        }
        if ( v7[9] )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
LABEL_49:
            v9 = -1073741823;
            goto LABEL_50;
          }
          v16 = 13;
LABEL_24:
          LOBYTE(v6) = 2;
          WPP_RECORDER_SF_(
            *(_QWORD *)(a1 + 1432),
            (_DWORD)v6,
            6,
            v16,
            (__int64)WPP_e747a75ab0a43332580ac19f3a627527_Traceguids);
          goto LABEL_49;
        }
        if ( (*(_DWORD *)(v14 + 204) & 0x200) == 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_49;
          v17 = 14;
LABEL_48:
          LOBYTE(v6) = 2;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(a1 + 1432),
            (_DWORD)v6,
            6,
            v17,
            (__int64)WPP_e747a75ab0a43332580ac19f3a627527_Traceguids,
            *(unsigned __int8 *)(v14 + 1341));
          goto LABEL_49;
        }
        v18 = *(_WORD *)(v14 + 200);
        if ( v18 >= *(_WORD *)(a1 + 200) )
          v18 = *(_WORD *)(a1 + 200);
        *(_WORD *)(a1 + 236) = v18;
        *(_WORD *)(v7[8] + 236LL) = v18;
        v7[9] = a1;
      }
      else
      {
        if ( v15 )
        {
          v14 = v7[7];
          if ( v14 && (*(_DWORD *)(v14 + 204) & 0x200) == 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_49;
            v17 = 16;
            goto LABEL_48;
          }
          *(_WORD *)(a1 + 236) = *(_WORD *)(a1 + 200);
        }
        v7[8] = a1;
      }
    }
    _InterlockedOr(v6, 0x20u);
    goto LABEL_55;
  }
LABEL_7:
  Pool2 = ExAllocatePool2(64, 96, 1882409045);
  v7 = (_QWORD *)Pool2;
  if ( Pool2 )
  {
    *(_OWORD *)Pool2 = *(_OWORD *)(a1 + 1368);
    *(_OWORD *)(Pool2 + 16) = *(_OWORD *)(a1 + 1384);
    *(_OWORD *)(Pool2 + 32) = *(_OWORD *)(a1 + 1400);
    *(_QWORD *)(Pool2 + 48) = *(_QWORD *)(a1 + 1416);
    v6 = *(volatile signed __int32 **)(v2 + 48);
    if ( *(_QWORD *)v6 != v2 + 40 )
      __fastfail(3u);
    v10 = (_QWORD *)(Pool2 + 80);
    v10[1] = v6;
    *v10 = v2 + 40;
    *(_QWORD *)v6 = v10;
    *(_QWORD *)(v2 + 48) = v10;
    goto LABEL_14;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_(
      *(_QWORD *)(a1 + 1432),
      (_DWORD)v6,
      4,
      10,
      (__int64)WPP_e747a75ab0a43332580ac19f3a627527_Traceguids);
  }
  v9 = -1073741670;
LABEL_50:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v12 = 18;
    LODWORD(v21) = v9;
    v13 = 4;
LABEL_18:
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(a1 + 1432),
      (_DWORD)v6,
      v13,
      v12,
      (__int64)WPP_e747a75ab0a43332580ac19f3a627527_Traceguids,
      v21);
  }
LABEL_55:
  v19 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
          WdfDriverGlobals,
          WdfDriverGlobals->Driver,
          off_14006B2C0);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2512))(
    WdfDriverGlobals,
    *(_QWORD *)(v19 + 56));
  return v9;
}

```

## disassembly

```asm
0x140084358  push    rbx
0x14008435a  push    rbp
0x14008435b  push    rsi
0x14008435c  push    rdi
0x14008435d  push    r14
0x14008435f  sub     rsp, 30h
0x140084363  mov     rax, cs:WdfFunctions_01015
0x14008436a  mov     rdi, rcx
0x14008436d  mov     rcx, cs:WdfDriverGlobals
0x140084374  mov     r8, cs:off_14006B2C0
0x14008437b  mov     rax, [rax+650h]
0x140084382  mov     rdx, [rcx]
0x140084385  call    _guard_dispatch_icall
0x14008438a  mov     rdx, cs:WdfFunctions_01015
0x140084391  mov     rbp, rax
0x140084394  mov     rcx, cs:WdfDriverGlobals
0x14008439b  mov     r8, cs:off_14006B2C0
0x1400843a2  mov     rax, [rdx+650h]
0x1400843a9  mov     rdx, [rcx]
0x1400843ac  call    _guard_dispatch_icall
0x1400843b1  mov     rcx, cs:WdfFunctions_01015
0x1400843b8  xor     r8d, r8d
0x1400843bb  mov     rdx, [rax+38h]
0x1400843bf  mov     r9, [rcx+9C8h]
0x1400843c6  mov     rcx, cs:WdfDriverGlobals
0x1400843cd  mov     rax, r9
0x1400843d0  call    _guard_dispatch_icall
0x1400843d5  mov     rax, cs:WdfFunctions_01015
0x1400843dc  mov     rcx, cs:WdfDriverGlobals
0x1400843e3  mov     r8, cs:off_14006B2C0
0x1400843ea  mov     rax, [rax+650h]
0x1400843f1  mov     rdx, [rcx]
0x1400843f4  call    _guard_dispatch_icall
0x1400843f9  lea     rbx, [rdi+558h]
0x140084400  lea     r14, [rax+28h]
0x140084404  mov     rax, [r14]
0x140084407  jmp     short loc_14008442B
0x140084409  mov     r8d, 38h ; '8'; Length
0x14008440f  mov     rdx, rbx; Source2
0x140084412  mov     rcx, rsi; Source1
0x140084415  call    cs:__imp_RtlCompareMemory
0x14008441c  nop     dword ptr [rax+rax+00h]
0x140084421  cmp     rax, 38h ; '8'
0x140084425  jz      short loc_140084436
0x140084427  mov     rax, [rsi+50h]
0x14008442b  lea     rsi, [rax-50h]
0x14008442f  cmp     r14, rax
0x140084432  jnz     short loc_140084409
0x140084434  jmp     short loc_14008443F
0x140084436  test    rsi, rsi
0x140084439  jnz     loc_1400844E3
0x14008443f  mov     edx, 60h ; '`'
0x140084444  mov     r8d, 70334855h
0x14008444a  lea     ecx, [rdx-20h]
0x14008444d  call    cs:__imp_ExAllocatePool2
0x140084454  nop     dword ptr [rax+rax+00h]
0x140084459  mov     rsi, rax
0x14008445c  test    rax, rax
0x14008445f  jnz     short loc_14008449D
0x140084461  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140084468  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14008446f  lea     rbp, WPP_e747a75ab0a43332580ac19f3a627527_Traceguids
0x140084476  jz      short loc_140084493
0x140084478  mov     rcx, [rdi+598h]
0x14008447f  lea     r9d, [rax+0Ah]
0x140084483  lea     r8d, [rax+4]
0x140084487  mov     [rsp+58h+var_38], rbp
0x14008448c  mov     dl, 2
0x14008448e  call    WPP_RECORDER_SF_
0x140084493  mov     ebx, 0C000009Ah
0x140084498  jmp     loc_14008470B
0x14008449d  movups  xmm0, xmmword ptr [rbx]
0x1400844a0  lea     rcx, [rbp+28h]
0x1400844a4  movups  xmmword ptr [rax], xmm0
0x1400844a7  movups  xmm1, xmmword ptr [rbx+10h]
0x1400844ab  movups  xmmword ptr [rax+10h], xmm1
0x1400844af  movups  xmm0, xmmword ptr [rbx+20h]
0x1400844b3  movups  xmmword ptr [rax+20h], xmm0
0x1400844b7  movsd   xmm1, qword ptr [rbx+30h]
0x1400844bc  movsd   qword ptr [rax+30h], xmm1
0x1400844c1  mov     rdx, [rcx+8]
0x1400844c5  cmp     [rdx], rcx
0x1400844c8  jz      short loc_1400844D1
0x1400844ca  mov     ecx, 3
0x1400844cf  int     29h; Win8: RtlFailFast(ecx)
0x1400844d1  add     rax, 50h ; 'P'
0x1400844d5  mov     [rax+8], rdx
0x1400844d9  mov     [rax], rcx
0x1400844dc  mov     [rdx], rax
0x1400844df  mov     [rcx+8], rax
0x1400844e3  mov     eax, [rdi+0D0h]
0x1400844e9  xor     ebx, ebx
0x1400844eb  mov     r8d, 200h
0x1400844f1  cmp     eax, r8d
0x1400844f4  jz      loc_14008467B
0x1400844fa  cmp     eax, 300h
0x1400844ff  jz      short loc_140084540
0x140084501  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140084508  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14008450f  jz      loc_14008473D
0x140084515  lea     r9d, [rbx+11h]
0x140084519  mov     dword ptr [rsp+58h+var_30], eax
0x14008451d  lea     rbp, WPP_e747a75ab0a43332580ac19f3a627527_Traceguids
0x140084524  lea     r8d, [rbx+6]
0x140084528  mov     rcx, [rdi+598h]
0x14008452f  mov     dl, 2
0x140084531  mov     [rsp+58h+var_38], rbp
0x140084536  call    WPP_RECORDER_SF_d
0x14008453b  jmp     loc_14008473D
0x140084540  mov     rcx, [rsi+40h]
0x140084544  lea     rdx, [rdi+0CCh]
0x14008454b  mov     eax, [rdx]
0x14008454d  and     eax, r8d
0x140084550  test    rcx, rcx
0x140084553  jz      loc_14008462B
0x140084559  test    eax, eax
0x14008455b  jz      loc_140084605
0x140084561  cmp     [rsi+48h], rbx
0x140084565  jz      short loc_1400845A6
0x140084567  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008456e  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140084575  lea     rbp, WPP_e747a75ab0a43332580ac19f3a627527_Traceguids
0x14008457c  jz      loc_140084706
0x140084582  mov     r9d, 0Dh
0x140084588  mov     rcx, [rdi+598h]
0x14008458f  mov     r8d, 6
0x140084595  mov     dl, 2
0x140084597  mov     [rsp+58h+var_38], rbp
0x14008459c  call    WPP_RECORDER_SF_
0x1400845a1  jmp     loc_140084706
0x1400845a6  test    [rcx+0CCh], r8d
0x1400845ad  jnz     short loc_1400845D5
0x1400845af  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400845b6  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400845bd  lea     rbp, WPP_e747a75ab0a43332580ac19f3a627527_Traceguids
0x1400845c4  jz      loc_140084706
0x1400845ca  mov     r9d, 0Eh
0x1400845d0  jmp     loc_1400846E2
0x1400845d5  movzx   eax, word ptr [rdi+0C8h]
0x1400845dc  movzx   ecx, word ptr [rcx+0C8h]
0x1400845e3  cmp     cx, ax
0x1400845e6  cmovnb  cx, ax
0x1400845ea  mov     [rdi+0ECh], cx
0x1400845f1  mov     rax, [rsi+40h]
0x1400845f5  mov     [rax+0ECh], cx
0x1400845fc  mov     [rsi+48h], rdi
0x140084600  jmp     loc_140084739
0x140084605  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008460c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140084613  lea     rbp, WPP_e747a75ab0a43332580ac19f3a627527_Traceguids
0x14008461a  jz      loc_140084706
0x140084620  mov     r9d, 0Fh
0x140084626  jmp     loc_140084588
0x14008462b  test    eax, eax
0x14008462d  jz      short loc_140084672
0x14008462f  mov     rcx, [rsi+38h]
0x140084633  test    rcx, rcx
0x140084636  jz      short loc_140084664
0x140084638  test    [rcx+0CCh], r8d
0x14008463f  jnz     short loc_140084664
0x140084641  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140084648  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14008464f  lea     rbp, WPP_e747a75ab0a43332580ac19f3a627527_Traceguids
0x140084656  jz      loc_140084706
0x14008465c  mov     r9d, 10h
0x140084662  jmp     short loc_1400846E2
0x140084664  movzx   eax, word ptr [rdi+0C8h]
0x14008466b  mov     [rdi+0ECh], ax
0x140084672  mov     [rsi+40h], rdi
0x140084676  jmp     loc_140084739
0x14008467b  cmp     [rsi+38h], rbx
0x14008467f  jz      short loc_1400846A3
0x140084681  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140084688  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14008468f  lea     rbp, WPP_e747a75ab0a43332580ac19f3a627527_Traceguids
0x140084696  jz      short loc_140084706
0x140084698  mov     r9d, 0Bh
0x14008469e  jmp     loc_140084588
0x1400846a3  lea     rdx, [rdi+0CCh]
0x1400846aa  test    [rdx], r8d
0x1400846ad  jz      loc_140084735
0x1400846b3  mov     rcx, [rsi+40h]
0x1400846b7  test    rcx, rcx
0x1400846ba  jz      short loc_140084727
0x1400846bc  test    [rcx+0CCh], r8d
0x1400846c3  jnz     short loc_140084727
0x1400846c5  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400846cc  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400846d3  lea     rbp, WPP_e747a75ab0a43332580ac19f3a627527_Traceguids
0x1400846da  jz      short loc_140084706
0x1400846dc  mov     r9d, 0Ch
0x1400846e2  movzx   eax, byte ptr [rcx+53Dh]
0x1400846e9  mov     r8d, 6
0x1400846ef  mov     rcx, [rdi+598h]
0x1400846f6  mov     dl, 2
0x1400846f8  mov     dword ptr [rsp+58h+var_30], eax
0x1400846fc  mov     [rsp+58h+var_38], rbp
0x140084701  call    WPP_RECORDER_SF_d
0x140084706  mov     ebx, 0C0000001h
0x14008470b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140084712  jz      short loc_14008473D
0x140084714  mov     r9d, 12h
0x14008471a  mov     dword ptr [rsp+58h+var_30], ebx
0x14008471e  lea     r8d, [r9-0Eh]
0x140084722  jmp     loc_140084528
0x140084727  movzx   eax, word ptr [rdi+0C8h]
0x14008472e  mov     [rdi+0ECh], ax
0x140084735  mov     [rsi+38h], rdi
0x140084739  lock or dword ptr [rdx], 20h
0x14008473d  mov     rax, cs:WdfFunctions_01015
0x140084744  mov     rcx, cs:WdfDriverGlobals
0x14008474b  mov     r8, cs:off_14006B2C0
0x140084752  mov     rax, [rax+650h]
0x140084759  mov     rdx, [rcx]
0x14008475c  call    _guard_dispatch_icall
0x140084761  mov     rcx, cs:WdfFunctions_01015
0x140084768  mov     rdx, [rax+38h]
0x14008476c  mov     r8, [rcx+9D0h]
0x140084773  mov     rcx, cs:WdfDriverGlobals
0x14008477a  mov     rax, r8
0x14008477d  call    _guard_dispatch_icall
0x140084782  mov     eax, ebx
0x140084784  add     rsp, 30h
0x140084788  pop     r14
0x14008478a  pop     rdi
0x14008478b  pop     rsi
0x14008478c  pop     rbp
0x14008478d  pop     rbx
0x14008478e  retn
```
