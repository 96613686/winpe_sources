# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x140002078`
- end: `0x140002308`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `656`
- prototype: `__int64 __fastcall(volatile signed __int32 *, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140002078`
- `0x140002354`

## callees

- `0x140002078`
- `0x140002750`
- `0x140002790`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400020f9`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400020f9`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v3; // r12d
  signed __int32 v5; // ebx
  volatile signed __int32 *v6; // r14
  char v7; // cl
  BOOL v8; // ebp
  bool v9; // cf
  bool v10; // zf
  __int64 v11; // rcx
  int v12; // eax
  int v13; // edx
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int v17; // eax
  int v18; // ecx
  int v19; // edi
  int v20; // r15d
  unsigned int ***v21; // r14
  BOOL v22; // esi
  unsigned int **v23; // rcx
  char v24; // al
  BOOL v25; // eax
  unsigned int v26; // edi
  signed __int32 v27; // esi
  signed __int32 v28; // eax
  __int64 v31; // [rsp+20h] [rbp-78h]
  __int64 v32; // [rsp+28h] [rbp-70h]
  __int64 v34; // [rsp+38h] [rbp-60h] BYREF
  __int64 v35; // [rsp+40h] [rbp-58h] BYREF
  int v36; // [rsp+48h] [rbp-50h]

  v3 = 0;
  v5 = a2;
  v6 = a1;
  if ( g_wil_details_ensureSubscribedToFeatureConfigurationChanges )
    v3 = g_wil_details_ensureSubscribedToFeatureConfigurationChanges(a1);
  v7 = *(_BYTE *)(a3 + 28);
  v34 = 0;
  v7 -= 2;
  v8 = 1;
  v9 = v7 == 0;
  v10 = v7 == 1;
  v11 = *(unsigned int *)(a3 + 24);
  v35 = 0;
  v36 = 0;
  v12 = RtlQueryFeatureConfiguration(v11, !v9 && !v10, &v34, &v35, a2);
  if ( v12 )
  {
    v13 = 0;
    if ( v12 == 279 )
    {
      v14 = 1;
      v15 = 8 * (BYTE4(v35) & 0x80);
    }
    else
    {
      v14 = 0;
      v15 = 0;
    }
  }
  else
  {
    v13 = (HIDWORD(v35) >> 4) & 3;
    v14 = 1;
    v15 = 8 * (BYTE4(v35) & 0x80);
    if ( (v35 & 0x4000000000LL) != 0 )
    {
      v16 = 2048;
      goto LABEL_10;
    }
  }
  v16 = 0;
LABEL_10:
  v17 = v14 != 0 ? v13 : 0;
  if ( v17 )
  {
    v18 = 64;
    if ( v13 != 2 )
      v18 = 0;
  }
  else
  {
    v18 = *(_BYTE *)(a3 + 31) != 0 ? 0x40 : 0;
  }
  v19 = v18 | v16 | v15 | (v17 << 7);
  if ( (v19 & 0xC00) == 0xC00 )
  {
    v20 = 1;
  }
  else
  {
    v20 = 0;
    if ( !(v18 & 0x40 | v16 & 0x40 | v15 & 0x40) )
    {
      v22 = 0;
      goto LABEL_33;
    }
  }
  v21 = *(unsigned int ****)(a3 + 32);
  v22 = 1;
  if ( v21 )
  {
    while ( 1 )
    {
      v23 = *v21;
      if ( !*v21 )
        break;
      if ( *((_BYTE *)v23 + 30) || *((_BYTE *)v23 + 29) )
      {
        if ( !*((_BYTE *)v23 + 31) )
        {
          v22 = 0;
          break;
        }
        v22 = 1;
        ++v21;
      }
      else
      {
        v32 = **v23;
        if ( (v32 & 2) != 0 )
          v24 = **v23;
        else
          v24 = wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(*v23, v32, v23);
        v22 = (v24 & 1) != 0;
        ++v21;
        if ( (v24 & 1) == 0 )
          break;
      }
    }
  }
  v6 = a1;
  if ( v20 && !v22 )
    v19 &= ~0x400u;
LABEL_33:
  v25 = (v19 & 0x40) != 0 && v22;
  v26 = v25 | v19 & 0xFFFFFFFE;
  if ( !*(_BYTE *)(a3 + 28) )
    v8 = v3 != 0;
  while ( 1 )
  {
    LODWORD(v31) = v5;
    v27 = v5;
    if ( v8 )
    {
      LODWORD(v31) = v5;
      if ( (v5 & 2) == 0 )
      {
        v27 = v5 ^ (v5 ^ v26) & 0x9C1 | 2;
        LODWORD(v31) = v27;
      }
    }
    if ( (v5 & 4) == 0 )
    {
      v27 = v27 ^ ((unsigned __int16)v26 ^ (unsigned __int16)v27) & 0x400 | 4;
      LODWORD(v31) = v27;
    }
    v28 = _InterlockedCompareExchange(v6, v27, v5);
    if ( v5 == v28 )
      break;
    v5 = v28;
  }
  if ( (v5 & 4) == 0 && g_wil_details_subscribeFeatureStateCacheToConfigurationChanges )
    g_wil_details_subscribeFeatureStateCacheToConfigurationChanges(v6, *(unsigned __int8 *)(a3 + 28), v3);
  if ( !v8 )
    LODWORD(v31) = v27 ^ (v27 ^ v26) & 0x9C1;
  return v31;
}

```

## disassembly

```asm
0x140002078  mov     [rsp+arg_18], rbx
0x14000207d  push    rbp
0x14000207e  push    rsi
0x14000207f  push    rdi
0x140002080  push    r12
0x140002082  push    r13
0x140002084  push    r14
0x140002086  push    r15
0x140002088  sub     rsp, 60h
0x14000208c  mov     rax, cs:__security_cookie
0x140002093  xor     rax, rsp
0x140002096  mov     [rsp+98h+var_48], rax
0x14000209b  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x1400020a2  xor     r12d, r12d
0x1400020a5  mov     [rsp+98h+var_68], rcx
0x1400020aa  mov     r13, r8
0x1400020ad  mov     [rsp+98h+var_78], rdx
0x1400020b2  mov     rbx, rdx
0x1400020b5  mov     r14, rcx
0x1400020b8  test    rax, rax
0x1400020bb  jz      short loc_1400020C5
0x1400020bd  call    _guard_dispatch_icall
0x1400020c2  mov     r12d, eax
0x1400020c5  mov     cl, [r13+1Ch]
0x1400020c9  lea     r9, [rsp+98h+var_58]
0x1400020ce  xor     edx, edx
0x1400020d0  mov     [rsp+98h+var_60], 0
0x1400020d9  sub     cl, 2
0x1400020dc  lea     r8, [rsp+98h+var_60]
0x1400020e1  lea     ebp, [rdx+1]
0x1400020e4  cmp     cl, bpl
0x1400020e7  mov     ecx, [r13+18h]
0x1400020eb  setnbe  dl
0x1400020ee  xor     eax, eax
0x1400020f0  mov     [rsp+98h+var_58], rax
0x1400020f5  mov     [rsp+98h+var_50], eax
0x1400020f9  call    cs:__imp_RtlQueryFeatureConfiguration
0x140002100  nop     dword ptr [rax+rax+00h]
0x140002105  test    eax, eax
0x140002107  jnz     short loc_140002133
0x140002109  mov     ecx, dword ptr [rsp+98h+var_58+4]
0x14000210d  mov     edx, ecx
0x14000210f  mov     eax, ecx
0x140002111  shr     edx, 4
0x140002114  and     eax, 80h
0x140002119  and     edx, 3
0x14000211c  test    cl, 40h
0x14000211f  mov     ecx, ebp
0x140002121  lea     r8d, ds:0[rax*8]
0x140002129  jz      short loc_140002156
0x14000212b  mov     r9d, 800h
0x140002131  jmp     short loc_140002159
0x140002133  xor     edx, edx
0x140002135  cmp     eax, 117h
0x14000213a  jnz     short loc_140002151
0x14000213c  mov     eax, dword ptr [rsp+98h+var_58+4]
0x140002140  mov     ecx, ebp
0x140002142  and     eax, 80h
0x140002147  lea     r8d, ds:0[rax*8]
0x14000214f  jmp     short loc_140002156
0x140002151  xor     ecx, ecx
0x140002153  xor     r8d, r8d
0x140002156  xor     r9d, r9d
0x140002159  neg     ecx
0x14000215b  sbb     eax, eax
0x14000215d  and     eax, edx
0x14000215f  mov     edi, eax
0x140002161  shl     edi, 7
0x140002164  or      edi, r8d
0x140002167  or      edi, r9d
0x14000216a  test    eax, eax
0x14000216c  jnz     short loc_14000217B
0x14000216e  mov     al, [r13+1Fh]
0x140002172  neg     al
0x140002174  sbb     ecx, ecx
0x140002176  and     ecx, 40h
0x140002179  jmp     short loc_140002188
0x14000217b  xor     eax, eax
0x14000217d  mov     ecx, 40h ; '@'
0x140002182  cmp     edx, 2
0x140002185  cmovnz  ecx, eax
0x140002188  or      edi, ecx
0x14000218a  mov     ecx, 0C00h
0x14000218f  mov     eax, edi
0x140002191  and     eax, ecx
0x140002193  cmp     eax, ecx
0x140002195  jnz     short loc_14000219C
0x140002197  mov     r15d, ebp
0x14000219a  jmp     short loc_1400021A9
0x14000219c  xor     r15d, r15d
0x14000219f  test    dil, 40h
0x1400021a3  jz      loc_140002237
0x1400021a9  mov     r14, [r13+20h]
0x1400021ad  mov     esi, ebp
0x1400021af  test    r14, r14
0x1400021b2  jz      short loc_140002223
0x1400021b4  mov     rcx, [r14]
0x1400021b7  test    rcx, rcx
0x1400021ba  jz      short loc_140002223
0x1400021bc  cmp     byte ptr [rcx+1Eh], 0
0x1400021c0  jnz     short loc_14000220F
0x1400021c2  cmp     byte ptr [rcx+1Dh], 0
0x1400021c6  jnz     short loc_14000220F
0x1400021c8  mov     r9, [rcx]
0x1400021cb  mov     [rsp+98h+var_70], 0
0x1400021d4  mov     eax, [r9]
0x1400021d7  mov     dword ptr [rsp+98h+var_70], eax
0x1400021db  test    al, 2
0x1400021dd  jz      short loc_1400021E6
0x1400021df  mov     rax, [rsp+98h+var_70]
0x1400021e4  jmp     short loc_1400021F6
0x1400021e6  mov     rdx, [rsp+98h+var_70]
0x1400021eb  mov     r8, rcx
0x1400021ee  mov     rcx, r9
0x1400021f1  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x1400021f6  test    esi, esi
0x1400021f8  jz      short loc_140002203
0x1400021fa  test    bpl, al
0x1400021fd  jz      short loc_140002203
0x1400021ff  mov     esi, ebp
0x140002201  jmp     short loc_140002205
0x140002203  xor     esi, esi
0x140002205  add     r14, 8
0x140002209  test    esi, esi
0x14000220b  jnz     short loc_1400021B4
0x14000220d  jmp     short loc_140002223
0x14000220f  test    esi, esi
0x140002211  jz      short loc_140002221
0x140002213  cmp     byte ptr [rcx+1Fh], 0
0x140002217  jz      short loc_140002221
0x140002219  mov     esi, ebp
0x14000221b  add     r14, 8
0x14000221f  jmp     short loc_1400021B4
0x140002221  xor     esi, esi
0x140002223  mov     r14, [rsp+98h+var_68]
0x140002228  test    r15d, r15d
0x14000222b  jz      short loc_140002239
0x14000222d  test    esi, esi
0x14000222f  jnz     short loc_140002239
0x140002231  btr     edi, 0Ah
0x140002235  jmp     short loc_140002239
0x140002237  xor     esi, esi
0x140002239  test    dil, 40h
0x14000223d  jz      short loc_140002247
0x14000223f  test    esi, esi
0x140002241  jz      short loc_140002247
0x140002243  mov     eax, ebp
0x140002245  jmp     short loc_140002249
0x140002247  xor     eax, eax
0x140002249  and     edi, 0FFFFFFFEh
0x14000224c  or      edi, eax
0x14000224e  cmp     byte ptr [r13+1Ch], 0
0x140002253  jnz     short loc_14000225E
0x140002255  mov     eax, r12d
0x140002258  neg     eax
0x14000225a  sbb     ecx, ecx
0x14000225c  and     ebp, ecx
0x14000225e  mov     r15d, 9C1h
0x140002264  mov     dword ptr [rsp+98h+var_78], ebx
0x140002268  mov     esi, ebx
0x14000226a  test    ebp, ebp
0x14000226c  jz      short loc_140002287
0x14000226e  mov     dword ptr [rsp+98h+var_78], ebx
0x140002272  test    bl, 2
0x140002275  jnz     short loc_140002287
0x140002277  mov     esi, edi
0x140002279  xor     esi, ebx
0x14000227b  and     esi, r15d
0x14000227e  xor     esi, ebx
0x140002280  or      esi, 2
0x140002283  mov     dword ptr [rsp+98h+var_78], esi
0x140002287  mov     ecx, ebx
0x140002289  and     ecx, 4
0x14000228c  jnz     short loc_1400022A1
0x14000228e  mov     eax, esi
0x140002290  xor     esi, edi
0x140002292  and     esi, 400h
0x140002298  xor     esi, eax
0x14000229a  or      esi, 4
0x14000229d  mov     dword ptr [rsp+98h+var_78], esi
0x1400022a1  mov     eax, ebx
0x1400022a3  lock cmpxchg [r14], esi
0x1400022a8  jz      short loc_1400022AE
0x1400022aa  mov     ebx, eax
0x1400022ac  jmp     short loc_140002264
0x1400022ae  test    ecx, ecx
0x1400022b0  jnz     short loc_1400022CE
0x1400022b2  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x1400022b9  test    rax, rax
0x1400022bc  jz      short loc_1400022CE
0x1400022be  movzx   edx, byte ptr [r13+1Ch]
0x1400022c3  mov     r8d, r12d
0x1400022c6  mov     rcx, r14
0x1400022c9  call    _guard_dispatch_icall
0x1400022ce  test    ebp, ebp
0x1400022d0  jnz     short loc_1400022DD
0x1400022d2  xor     edi, esi
0x1400022d4  and     edi, r15d
0x1400022d7  xor     edi, esi
0x1400022d9  mov     dword ptr [rsp+98h+var_78], edi
0x1400022dd  mov     rax, [rsp+98h+var_78]
0x1400022e2  mov     rcx, [rsp+98h+var_48]
0x1400022e7  xor     rcx, rsp; StackCookie
0x1400022ea  call    __security_check_cookie
0x1400022ef  mov     rbx, [rsp+98h+arg_18]
0x1400022f7  add     rsp, 60h
0x1400022fb  pop     r15
0x1400022fd  pop     r14
0x1400022ff  pop     r13
0x140002301  pop     r12
0x140002303  pop     rdi
0x140002304  pop     rsi
0x140002305  pop     rbp
0x140002306  retn
```
