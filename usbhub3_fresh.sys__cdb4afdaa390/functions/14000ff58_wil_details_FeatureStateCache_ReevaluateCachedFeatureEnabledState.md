# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x14000ff58`
- end: `0x1400101b1`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `601`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ff58`
- `0x140010210`

## callees

- `0x14000ff58`
- `0x140045530`
- `0x140045570`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000ffcf`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000ffcf`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v3; // r15d
  signed __int32 v5; // ebx
  char v7; // cl
  BOOL v8; // ebp
  bool v9; // cf
  bool v10; // zf
  __int64 v11; // rcx
  int v12; // eax
  int v13; // r8d
  int v14; // ecx
  int v15; // eax
  int v16; // edx
  int v17; // ecx
  int v18; // r9d
  int v19; // eax
  int v20; // r8d
  int v21; // ecx
  unsigned int v22; // r8d
  int v23; // esi
  unsigned int ***v24; // rdi
  unsigned int **v25; // rcx
  unsigned __int8 v26; // al
  BOOL v27; // ecx
  unsigned int v28; // eax
  unsigned int v29; // esi
  signed __int32 v30; // edi
  signed __int32 v31; // eax
  __int64 v34; // [rsp+20h] [rbp-68h]
  __int64 v35; // [rsp+28h] [rbp-60h]
  __int64 v36; // [rsp+30h] [rbp-58h] BYREF
  __int64 v37; // [rsp+38h] [rbp-50h] BYREF
  int v38; // [rsp+40h] [rbp-48h]

  v3 = 0;
  v5 = a2;
  if ( g_wil_details_ensureSubscribedToFeatureConfigurationChanges )
    v3 = g_wil_details_ensureSubscribedToFeatureConfigurationChanges(a1);
  v7 = *(_BYTE *)(a3 + 28);
  v36 = 0;
  v7 -= 2;
  v8 = 1;
  v9 = v7 == 0;
  v10 = v7 == 1;
  v11 = *(unsigned int *)(a3 + 24);
  v37 = 0;
  v38 = 0;
  v12 = RtlQueryFeatureConfiguration(v11, !v9 && !v10, &v36, &v37, a2);
  if ( v12 )
  {
    v16 = 0;
    if ( v12 == 279 )
    {
      v13 = 1;
      v17 = 8 * (BYTE4(v37) & 0x80);
LABEL_7:
      v18 = 0;
      goto LABEL_8;
    }
    v14 = 0;
    v15 = 0;
    v13 = 0;
  }
  else
  {
    v13 = 1;
    v14 = (HIDWORD(v37) >> 7) & 1;
    v15 = (HIDWORD(v37) >> 6) & 1;
    v16 = (HIDWORD(v37) >> 4) & 3;
  }
  v17 = v14 << 10;
  if ( !v15 )
    goto LABEL_7;
  v18 = 2048;
LABEL_8:
  v19 = v13 != 0 ? v16 : 0;
  v20 = v18 | v17 | (v19 << 7);
  if ( v19 )
  {
    v21 = 64;
    if ( v16 != 2 )
      v21 = 0;
  }
  else
  {
    v21 = *(_BYTE *)(a3 + 31) != 0 ? 0x40 : 0;
  }
  v22 = v21 | v20;
  v23 = v22 | (v22 >> 6) & 1;
  if ( ((v22 >> 6) & 1) != 0 )
  {
    v24 = *(unsigned int ****)(a3 + 32);
    if ( v24 )
    {
      while ( (v23 & 1) != 0 )
      {
        v25 = *v24;
        if ( !*v24 )
          break;
        if ( *((_BYTE *)v25 + 30) || *((_BYTE *)v25 + 29) )
        {
          v28 = (v23 & 1) != 0 && *((_BYTE *)v25 + 31);
          v29 = v23 & 0xFFFFFFFE;
        }
        else
        {
          v35 = **v25;
          if ( (v35 & 2) != 0 )
            v26 = **v25;
          else
            v26 = wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(*v25, v35, v25);
          v27 = (v26 & (unsigned __int8)v23 & 1) != 0;
          v28 = v23 & 0xFFFFFFFE;
          v29 = v27;
        }
        v23 = v28 | v29;
        ++v24;
      }
    }
  }
  if ( !*(_BYTE *)(a3 + 28) )
    v8 = v3 != 0;
  while ( 1 )
  {
    LODWORD(v34) = v5;
    v30 = v5;
    if ( v8 )
    {
      LODWORD(v34) = v5;
      if ( (v5 & 2) == 0 )
      {
        v30 = v5 ^ ((unsigned __int16)v5 ^ (unsigned __int16)v23) & 0x9C1 | 2;
        LODWORD(v34) = v30;
      }
    }
    if ( (v5 & 4) == 0 )
    {
      v30 = v30 ^ ((unsigned __int16)v23 ^ (unsigned __int16)v30) & 0x400 | 4;
      LODWORD(v34) = v30;
    }
    v31 = _InterlockedCompareExchange(a1, v30, v5);
    if ( v5 == v31 )
      break;
    v5 = v31;
  }
  if ( (v5 & 4) == 0 && g_wil_details_subscribeFeatureStateCacheToConfigurationChanges )
    g_wil_details_subscribeFeatureStateCacheToConfigurationChanges(a1, *(unsigned __int8 *)(a3 + 28), v3);
  if ( !v8 )
    LODWORD(v34) = v30 ^ ((unsigned __int16)v30 ^ (unsigned __int16)v23) & 0x9C1;
  return v34;
}

```

## disassembly

```asm
0x14000ff58  push    rbx
0x14000ff5a  push    rbp
0x14000ff5b  push    rsi
0x14000ff5c  push    rdi
0x14000ff5d  push    r12
0x14000ff5f  push    r14
0x14000ff61  push    r15
0x14000ff63  sub     rsp, 50h
0x14000ff67  mov     rax, cs:__security_cookie
0x14000ff6e  xor     rax, rsp
0x14000ff71  mov     [rsp+88h+var_40], rax
0x14000ff76  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x14000ff7d  xor     r15d, r15d
0x14000ff80  mov     [rsp+88h+var_68], rdx
0x14000ff85  mov     r14, r8
0x14000ff88  mov     rbx, rdx
0x14000ff8b  mov     r12, rcx
0x14000ff8e  test    rax, rax
0x14000ff91  jz      short loc_14000FF9B
0x14000ff93  call    _guard_dispatch_icall
0x14000ff98  mov     r15d, eax
0x14000ff9b  mov     cl, [r14+1Ch]
0x14000ff9f  lea     r9, [rsp+88h+var_50]
0x14000ffa4  xor     edx, edx
0x14000ffa6  mov     [rsp+88h+var_58], 0
0x14000ffaf  sub     cl, 2
0x14000ffb2  lea     r8, [rsp+88h+var_58]
0x14000ffb7  lea     ebp, [rdx+1]
0x14000ffba  cmp     cl, bpl
0x14000ffbd  mov     ecx, [r14+18h]
0x14000ffc1  setnbe  dl
0x14000ffc4  xor     eax, eax
0x14000ffc6  mov     [rsp+88h+var_50], rax
0x14000ffcb  mov     [rsp+88h+var_48], eax
0x14000ffcf  call    cs:__imp_RtlQueryFeatureConfiguration
0x14000ffd6  nop     dword ptr [rax+rax+00h]
0x14000ffdb  test    eax, eax
0x14000ffdd  jnz     short loc_14000FFFC
0x14000ffdf  mov     edx, dword ptr [rsp+88h+var_50+4]
0x14000ffe3  mov     r8d, ebp
0x14000ffe6  mov     ecx, edx
0x14000ffe8  mov     eax, edx
0x14000ffea  shr     ecx, 7
0x14000ffed  shr     eax, 6
0x14000fff0  and     ecx, ebp
0x14000fff2  and     eax, ebp
0x14000fff4  shr     edx, 4
0x14000fff7  and     edx, 3
0x14000fffa  jmp     short loc_140010047
0x14000fffc  xor     edx, edx
0x14000fffe  cmp     eax, 117h
0x140010003  jnz     short loc_140010040
0x140010005  mov     eax, dword ptr [rsp+88h+var_50+4]
0x140010009  mov     r8d, ebp
0x14001000c  and     eax, 80h
0x140010011  lea     ecx, ds:0[rax*8]
0x140010018  xor     r9d, r9d
0x14001001b  neg     r8d
0x14001001e  sbb     eax, eax
0x140010020  and     eax, edx
0x140010022  mov     r8d, eax
0x140010025  shl     r8d, 7
0x140010029  or      r8d, ecx
0x14001002c  or      r8d, r9d
0x14001002f  test    eax, eax
0x140010031  jnz     short loc_140010056
0x140010033  mov     al, [r14+1Fh]
0x140010037  neg     al
0x140010039  sbb     ecx, ecx
0x14001003b  and     ecx, 40h
0x14001003e  jmp     short loc_140010063
0x140010040  xor     ecx, ecx
0x140010042  xor     eax, eax
0x140010044  xor     r8d, r8d
0x140010047  shl     ecx, 0Ah
0x14001004a  test    eax, eax
0x14001004c  jz      short loc_140010018
0x14001004e  mov     r9d, 800h
0x140010054  jmp     short loc_14001001B
0x140010056  xor     eax, eax
0x140010058  mov     ecx, 40h ; '@'
0x14001005d  cmp     edx, 2
0x140010060  cmovnz  ecx, eax
0x140010063  or      r8d, ecx
0x140010066  mov     eax, r8d
0x140010069  shr     eax, 6
0x14001006c  and     eax, ebp
0x14001006e  mov     esi, eax
0x140010070  or      esi, r8d
0x140010073  test    eax, eax
0x140010075  jz      loc_1400100FF
0x14001007b  mov     rdi, [r14+20h]
0x14001007f  test    rdi, rdi
0x140010082  jz      short loc_1400100FF
0x140010084  jmp     short loc_1400100FA
0x140010086  mov     rcx, [rdi]
0x140010089  test    rcx, rcx
0x14001008c  jz      short loc_1400100FF
0x14001008e  cmp     byte ptr [rcx+1Eh], 0
0x140010092  jnz     short loc_1400100E0
0x140010094  cmp     byte ptr [rcx+1Dh], 0
0x140010098  jnz     short loc_1400100E0
0x14001009a  mov     r9, [rcx]
0x14001009d  mov     [rsp+88h+var_60], 0
0x1400100a6  mov     eax, [r9]
0x1400100a9  mov     dword ptr [rsp+88h+var_60], eax
0x1400100ad  test    al, 2
0x1400100af  jz      short loc_1400100B8
0x1400100b1  mov     rax, [rsp+88h+var_60]
0x1400100b6  jmp     short loc_1400100C8
0x1400100b8  mov     rdx, [rsp+88h+var_60]
0x1400100bd  mov     r8, rcx
0x1400100c0  mov     rcx, r9
0x1400100c3  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x1400100c8  mov     ecx, esi
0x1400100ca  and     ecx, eax
0x1400100cc  mov     eax, esi
0x1400100ce  test    bpl, cl
0x1400100d1  mov     ecx, 0
0x1400100d6  setnz   cl
0x1400100d9  and     eax, 0FFFFFFFEh
0x1400100dc  mov     esi, ecx
0x1400100de  jmp     short loc_1400100F4
0x1400100e0  test    bpl, sil
0x1400100e3  jz      short loc_1400100EF
0x1400100e5  cmp     byte ptr [rcx+1Fh], 0
0x1400100e9  jz      short loc_1400100EF
0x1400100eb  mov     eax, ebp
0x1400100ed  jmp     short loc_1400100F1
0x1400100ef  xor     eax, eax
0x1400100f1  and     esi, 0FFFFFFFEh
0x1400100f4  or      esi, eax
0x1400100f6  add     rdi, 8
0x1400100fa  test    bpl, sil
0x1400100fd  jnz     short loc_140010086
0x1400100ff  cmp     byte ptr [r14+1Ch], 0
0x140010104  jnz     short loc_14001010F
0x140010106  mov     eax, r15d
0x140010109  neg     eax
0x14001010b  sbb     ecx, ecx
0x14001010d  and     ebp, ecx
0x14001010f  mov     dword ptr [rsp+88h+var_68], ebx
0x140010113  mov     edi, ebx
0x140010115  test    ebp, ebp
0x140010117  jz      short loc_140010135
0x140010119  mov     dword ptr [rsp+88h+var_68], ebx
0x14001011d  test    bl, 2
0x140010120  jnz     short loc_140010135
0x140010122  mov     edi, esi
0x140010124  xor     edi, ebx
0x140010126  and     edi, 9C1h
0x14001012c  xor     edi, ebx
0x14001012e  or      edi, 2
0x140010131  mov     dword ptr [rsp+88h+var_68], edi
0x140010135  mov     ecx, ebx
0x140010137  and     ecx, 4
0x14001013a  jnz     short loc_14001014F
0x14001013c  mov     eax, edi
0x14001013e  xor     edi, esi
0x140010140  and     edi, 400h
0x140010146  xor     edi, eax
0x140010148  or      edi, 4
0x14001014b  mov     dword ptr [rsp+88h+var_68], edi
0x14001014f  mov     eax, ebx
0x140010151  lock cmpxchg [r12], edi
0x140010157  jz      short loc_14001015D
0x140010159  mov     ebx, eax
0x14001015b  jmp     short loc_14001010F
0x14001015d  test    ecx, ecx
0x14001015f  jnz     short loc_14001017D
0x140010161  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x140010168  test    rax, rax
0x14001016b  jz      short loc_14001017D
0x14001016d  movzx   edx, byte ptr [r14+1Ch]
0x140010172  mov     r8d, r15d
0x140010175  mov     rcx, r12
0x140010178  call    _guard_dispatch_icall
0x14001017d  test    ebp, ebp
0x14001017f  jnz     short loc_14001018F
0x140010181  xor     esi, edi
0x140010183  and     esi, 9C1h
0x140010189  xor     esi, edi
0x14001018b  mov     dword ptr [rsp+88h+var_68], esi
0x14001018f  mov     rax, [rsp+88h+var_68]
0x140010194  mov     rcx, [rsp+88h+var_40]
0x140010199  xor     rcx, rsp; StackCookie
0x14001019c  call    __security_check_cookie
0x1400101a1  add     rsp, 50h
0x1400101a5  pop     r15
0x1400101a7  pop     r14
0x1400101a9  pop     r12
0x1400101ab  pop     rdi
0x1400101ac  pop     rsi
0x1400101ad  pop     rbp
0x1400101ae  pop     rbx
0x1400101af  retn
```
