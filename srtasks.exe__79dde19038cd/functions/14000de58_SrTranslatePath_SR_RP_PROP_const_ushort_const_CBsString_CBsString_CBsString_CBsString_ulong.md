# SrTranslatePath(_SR_RP_PROP const *,ushort const *,CBsString *,CBsString *,CBsString *,CBsString *,ulong *)

- ea: `0x14000de58`
- end: `0x14000e0ea`
- name: `?SrTranslatePath@@YAJPEBU_SR_RP_PROP@@PEBGPEAVCBsString@@222PEAK@Z`
- size: `658`
- prototype: `__int64 __fastcall(const struct _SR_RP_PROP *, const unsigned __int16 *, struct CBsString *, struct CBsString *, struct CBsString *, struct CBsString *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000e0f0`

## callees

- `0x140002e1c`
- `0x14000de58`
- `0x14000e324`
- `0x14000e41c`
- `0x14000fe8c`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x14000dfa6`
- `msvcrt!_wcsnicmp` at `0x14000dfa6`

## string_xrefs

- `0x14000debd`: `SrTranslatePath`

## pseudocode

```c
__int64 __fastcall SrTranslatePath(
        const struct _SR_RP_PROP *a1,
        const unsigned __int16 *a2,
        struct CBsString *a3,
        struct CBsString *a4,
        struct CBsString *a5,
        struct CBsString *a6)
{
  const struct _SR_RP_PROP *v8; // r15
  unsigned __int64 v9; // rdx
  __int64 v10; // r8
  _WORD *v11; // rcx
  _WORD *v13; // rcx
  _WORD *v14; // rcx
  __int16 v15; // ax
  unsigned int v16; // r13d
  __int64 v17; // r15
  unsigned int v18; // eax
  size_t v19; // r12
  const wchar_t *v20; // r9
  __int16 v21; // ax
  _WORD *v22; // rcx
  unsigned int v23; // ebx
  _WORD *v24; // r8
  _WORD *v25; // r8
  int v27; // [rsp+20h] [rbp-40h] BYREF
  __int16 v28; // [rsp+24h] [rbp-3Ch]
  __int16 v29; // [rsp+26h] [rbp-3Ah]
  unsigned int v32; // [rsp+B0h] [rbp+50h]
  CBsString *v33; // [rsp+C0h] [rbp+60h]

  v8 = a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_356ece2e4ded3d022f22f9fb8e9950d0_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v27, "SrTranslatePath", 371, 1);
  if ( a4 && *((_DWORD *)a4 + 2) )
  {
    v11 = *(_WORD **)a4;
    *((_DWORD *)a4 + 2) = 0;
    *v11 = 0;
  }
  if ( a5 && *((_DWORD *)a5 + 2) )
  {
    v13 = *(_WORD **)a5;
    *((_DWORD *)a5 + 2) = 0;
    *v13 = 0;
  }
  if ( a6 && *((_DWORD *)a6 + 2) )
  {
    v14 = *(_WORD **)a6;
    *((_DWORD *)a6 + 2) = 0;
    *v14 = 0;
  }
  v15 = 386;
  if ( !v8 || (v28 = 386, v15 = 387, !a2) )
  {
    v23 = -2147024809;
    v27 = -2147024809;
    goto LABEL_50;
  }
  v27 = 0;
  v9 = -1;
  v28 = 387;
  do
    ++v9;
  while ( a2[v9] );
  v16 = 0;
  v33 = (CBsString *)v9;
  if ( !*((_DWORD *)v8 + 22) )
  {
LABEL_26:
    v21 = 460;
    goto LABEL_35;
  }
  while ( 1 )
  {
    v17 = *((_QWORD *)v8 + 12);
    v18 = 0;
    v32 = 0;
    if ( *(_DWORD *)(v17 + 48LL * v16 + 32) )
      break;
LABEL_25:
    v8 = a1;
    if ( ++v16 >= *((_DWORD *)a1 + 22) )
      goto LABEL_26;
  }
  while ( 1 )
  {
    v19 = -1;
    v20 = *(const wchar_t **)(*(_QWORD *)(v17 + 48LL * v16 + 40) + 8LL * v18);
    do
      ++v19;
    while ( v20[v19] );
    if ( v9 < v19 )
      goto LABEL_24;
    if ( !_wcsnicmp(a2, v20, v19) )
      break;
    v9 = (unsigned __int64)v33;
LABEL_24:
    v18 = v32 + 1;
    v32 = v18;
    if ( v18 >= *(_DWORD *)(v17 + 48LL * v16 + 32) )
      goto LABEL_25;
  }
  if ( !a4 )
    goto LABEL_32;
  if ( *((_DWORD *)a4 + 2) )
  {
    v22 = *(_WORD **)a4;
    *((_DWORD *)a4 + 2) = 0;
    *v22 = 0;
  }
  v27 = CBsString::Append(a4, (unsigned __int16 *)&a2[v19]);
  v23 = v27;
  v15 = 427;
  if ( v27 < 0 )
    goto LABEL_50;
  v28 = 427;
LABEL_32:
  if ( !a5 )
  {
LABEL_41:
    if ( a6 )
    {
      v9 = *(_QWORD *)(v17 + 48LL * v16 + 24);
      if ( !v9 )
      {
        v21 = 443;
LABEL_35:
        v23 = 1;
        goto LABEL_36;
      }
      if ( *((_DWORD *)a6 + 2) )
      {
        v25 = *(_WORD **)a6;
        *((_DWORD *)a6 + 2) = 0;
        *v25 = 0;
      }
      v27 = CBsString::Append(a6, (unsigned __int16 *)v9);
      v23 = v27;
      if ( v27 < 0 )
      {
        v15 = 445;
        goto LABEL_50;
      }
    }
    v23 = 0;
    v21 = 453;
LABEL_36:
    v27 = v23;
    v28 = v21;
    goto LABEL_51;
  }
  v9 = *(_QWORD *)(v17 + 48LL * v16 + 16);
  if ( !v9 )
  {
    v21 = 434;
    goto LABEL_35;
  }
  if ( *((_DWORD *)a5 + 2) )
  {
    v24 = *(_WORD **)a5;
    *((_DWORD *)a5 + 2) = 0;
    *v24 = 0;
  }
  v27 = CBsString::Append(a5, (unsigned __int16 *)v9);
  v23 = v27;
  v15 = 436;
  if ( v27 >= 0 )
  {
    v28 = 436;
    goto LABEL_41;
  }
LABEL_50:
  v29 = v15;
LABEL_51:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v27, v9, v10);
  return v23;
}

```

## disassembly

```asm
0x14000de58  mov     rax, rsp
0x14000de5b  mov     [rax+20h], rbx
0x14000de5f  mov     [rax+18h], r8
0x14000de63  mov     [rax+10h], rdx
0x14000de67  mov     [rax+8], rcx
0x14000de6b  push    rbp
0x14000de6c  push    rsi
0x14000de6d  push    rdi
0x14000de6e  push    r12
0x14000de70  push    r13
0x14000de72  push    r14
0x14000de74  push    r15
0x14000de76  mov     rbp, rsp
0x14000de79  sub     rsp, 60h
0x14000de7d  mov     rbx, r9
0x14000de80  mov     r14, rdx
0x14000de83  mov     r15, rcx
0x14000de86  mov     rcx, cs:WPP_GLOBAL_Control
0x14000de8d  lea     rax, WPP_GLOBAL_Control
0x14000de94  cmp     rcx, rax
0x14000de97  jz      short loc_14000DEB7
0x14000de99  test    dword ptr [rcx+1Ch], 20000000h
0x14000dea0  jz      short loc_14000DEB7
0x14000dea2  mov     rcx, [rcx+10h]
0x14000dea6  lea     r8, WPP_356ece2e4ded3d022f22f9fb8e9950d0_Traceguids
0x14000dead  mov     edx, 10h
0x14000deb2  call    WPP_SF_
0x14000deb7  mov     r9d, 1; unsigned __int16
0x14000debd  lea     rdx, aSrtranslatepat; "SrTranslatePath"
0x14000dec4  mov     r8d, 173h; unsigned __int16
0x14000deca  lea     rcx, [rbp+var_40]; this
0x14000dece  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x14000ded3  xor     r10d, r10d
0x14000ded6  test    rbx, rbx
0x14000ded9  jz      short loc_14000DEEC
0x14000dedb  cmp     [rbx+8], r10d
0x14000dedf  jz      short loc_14000DEEC
0x14000dee1  mov     rcx, [rbx]
0x14000dee4  mov     [rbx+8], r10d
0x14000dee8  mov     [rcx], r10w
0x14000deec  mov     rsi, [rbp+arg_20]
0x14000def0  test    rsi, rsi
0x14000def3  jz      short loc_14000DF06
0x14000def5  cmp     [rsi+8], r10d
0x14000def9  jz      short loc_14000DF06
0x14000defb  mov     rcx, [rsi]
0x14000defe  mov     [rsi+8], r10d
0x14000df02  mov     [rcx], r10w
0x14000df06  mov     rdi, [rbp+arg_28]
0x14000df0a  test    rdi, rdi
0x14000df0d  jz      short loc_14000DF20
0x14000df0f  cmp     [rdi+8], r10d
0x14000df13  jz      short loc_14000DF20
0x14000df15  mov     rcx, [rdi]
0x14000df18  mov     [rdi+8], r10d
0x14000df1c  mov     [rcx], r10w
0x14000df20  mov     eax, 182h
0x14000df25  test    r15, r15
0x14000df28  jz      loc_14000E0BB
0x14000df2e  mov     [rbp+var_3C], ax
0x14000df32  mov     eax, 183h
0x14000df37  test    r14, r14
0x14000df3a  jz      loc_14000E0BB
0x14000df40  mov     [rbp+var_40], r10d
0x14000df44  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000df48  mov     [rbp+var_3C], ax
0x14000df4c  inc     rdx
0x14000df4f  cmp     [r14+rdx*2], r10w
0x14000df54  jnz     short loc_14000DF4C
0x14000df56  mov     r13d, r10d
0x14000df59  mov     [rbp+arg_20], rdx
0x14000df5d  cmp     [r15+58h], r10d
0x14000df61  jbe     short loc_14000DFD3
0x14000df63  mov     r15, [r15+60h]
0x14000df67  mov     eax, r13d
0x14000df6a  lea     r14, [rax+rax*2]
0x14000df6e  mov     eax, r10d
0x14000df71  add     r14, r14
0x14000df74  mov     [rbp+arg_10], eax
0x14000df77  cmp     [r15+r14*8+20h], r10d
0x14000df7c  jbe     short loc_14000DFC6
0x14000df7e  mov     ecx, eax
0x14000df80  or      r12, 0FFFFFFFFFFFFFFFFh
0x14000df84  mov     rax, [r15+r14*8+28h]
0x14000df89  mov     r9, [rax+rcx*8]
0x14000df8d  inc     r12
0x14000df90  cmp     [r9+r12*2], r10w
0x14000df95  jnz     short loc_14000DF8D
0x14000df97  cmp     rdx, r12
0x14000df9a  jb      short loc_14000DFB7
0x14000df9c  mov     rcx, [rbp+String1]; String1
0x14000dfa0  mov     r8, r12; MaxCount
0x14000dfa3  mov     rdx, r9; String2
0x14000dfa6  call    cs:__imp__wcsnicmp
0x14000dfac  xor     r10d, r10d
0x14000dfaf  test    eax, eax
0x14000dfb1  jz      short loc_14000DFDA
0x14000dfb3  mov     rdx, [rbp+arg_20]
0x14000dfb7  mov     eax, [rbp+arg_10]
0x14000dfba  inc     eax
0x14000dfbc  mov     [rbp+arg_10], eax
0x14000dfbf  cmp     eax, [r15+r14*8+20h]
0x14000dfc4  jb      short loc_14000DF7E
0x14000dfc6  mov     r15, [rbp+arg_0]
0x14000dfca  inc     r13d
0x14000dfcd  cmp     r13d, [r15+58h]
0x14000dfd1  jb      short loc_14000DF63
0x14000dfd3  mov     eax, 1CCh
0x14000dfd8  jmp     short loc_14000E02D
0x14000dfda  test    rbx, rbx
0x14000dfdd  jz      short loc_14000E019
0x14000dfdf  cmp     [rbx+8], r10d
0x14000dfe3  jz      short loc_14000DFF0
0x14000dfe5  mov     rcx, [rbx]
0x14000dfe8  mov     [rbx+8], r10d
0x14000dfec  mov     [rcx], r10w
0x14000dff0  mov     rax, [rbp+String1]
0x14000dff4  mov     rcx, rbx; this
0x14000dff7  lea     rdx, [rax+r12*2]; unsigned __int16 *
0x14000dffb  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x14000e000  xor     r10d, r10d
0x14000e003  mov     [rbp+var_40], eax
0x14000e006  test    eax, eax
0x14000e008  mov     ebx, eax
0x14000e00a  mov     eax, 1ABh
0x14000e00f  js      loc_14000E0C3
0x14000e015  mov     [rbp+var_3C], ax
0x14000e019  test    rsi, rsi
0x14000e01c  jz      short loc_14000E06C
0x14000e01e  mov     rdx, [r15+r14*8+10h]; unsigned __int16 *
0x14000e023  test    rdx, rdx
0x14000e026  jnz     short loc_14000E03E
0x14000e028  mov     eax, 1B2h
0x14000e02d  mov     ebx, 1
0x14000e032  mov     [rbp+var_40], ebx
0x14000e035  mov     [rbp+var_3C], ax
0x14000e039  jmp     loc_14000E0C7
0x14000e03e  cmp     [rsi+8], r10d
0x14000e042  jz      short loc_14000E04F
0x14000e044  mov     r8, [rsi]
0x14000e047  mov     [rsi+8], r10d
0x14000e04b  mov     [r8], r10w
0x14000e04f  mov     rcx, rsi; this
0x14000e052  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x14000e057  xor     r10d, r10d
0x14000e05a  mov     [rbp+var_40], eax
0x14000e05d  test    eax, eax
0x14000e05f  mov     ebx, eax
0x14000e061  mov     eax, 1B4h
0x14000e066  js      short loc_14000E0C3
0x14000e068  mov     [rbp+var_3C], ax
0x14000e06c  test    rdi, rdi
0x14000e06f  jz      short loc_14000E0AE
0x14000e071  mov     rdx, [r15+r14*8+18h]; unsigned __int16 *
0x14000e076  test    rdx, rdx
0x14000e079  jnz     short loc_14000E082
0x14000e07b  mov     eax, 1BBh
0x14000e080  jmp     short loc_14000E02D
0x14000e082  cmp     [rdi+8], r10d
0x14000e086  jz      short loc_14000E093
0x14000e088  mov     r8, [rdi]
0x14000e08b  mov     [rdi+8], r10d
0x14000e08f  mov     [r8], r10w
0x14000e093  mov     rcx, rdi; this
0x14000e096  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x14000e09b  xor     r10d, r10d
0x14000e09e  mov     [rbp+var_40], eax
0x14000e0a1  mov     ebx, eax
0x14000e0a3  test    eax, eax
0x14000e0a5  jns     short loc_14000E0AE
0x14000e0a7  mov     eax, 1BDh
0x14000e0ac  jmp     short loc_14000E0C3
0x14000e0ae  mov     ebx, r10d
0x14000e0b1  mov     eax, 1C5h
0x14000e0b6  jmp     loc_14000E032
0x14000e0bb  mov     ebx, 80070057h
0x14000e0c0  mov     [rbp+var_40], ebx
0x14000e0c3  mov     [rbp+var_3A], ax
0x14000e0c7  lea     rcx, [rbp+var_40]; this
0x14000e0cb  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x14000e0d0  mov     eax, ebx
0x14000e0d2  mov     rbx, [rsp+60h+arg_18]
0x14000e0da  add     rsp, 60h
0x14000e0de  pop     r15
0x14000e0e0  pop     r14
0x14000e0e2  pop     r13
0x14000e0e4  pop     r12
0x14000e0e6  pop     rdi
0x14000e0e7  pop     rsi
0x14000e0e8  pop     rbp
0x14000e0e9  retn
```
