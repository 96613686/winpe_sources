# FlRdmaNsiEnumerateNdkItemsCommon

- ea: `0x1401ad758`
- end: `0x1401adcb6`
- name: `FlRdmaNsiEnumerateNdkItemsCommon`
- size: `1374`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1401ad5b0`
- `0x1401ad740`

## callees

- `0x14004c4c0`
- `0x140072d50`
- `0x1400c6700`
- `0x1400c82f8`
- `0x1401ad758`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401ad82c`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401ad997`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401ad82c`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401ad997`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401ad8f8`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401adb9c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401adbc9`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401adc0b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401adc3a`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401ad8f8`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401adb9c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401adbc9`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401adc0b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401adc3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401adbe7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401adc74`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401adbe7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401adc74`

## pseudocode

```c
__int64 __fastcall FlRdmaNsiEnumerateNdkItemsCommon(__int64 *a1, char a2)
{
  int v2; // r8d
  __int64 *v3; // r12
  int v4; // r8d
  __int64 v6; // rcx
  int v7; // ebx
  KSPIN_LOCK *v8; // r14
  unsigned int v9; // r13d
  KSPIN_LOCK *v10; // rdi
  unsigned int v11; // r15d
  __int64 v12; // rdx
  KSPIN_LOCK v13; // rsi
  KSPIN_LOCK v14; // rdi
  int v15; // ebx
  unsigned int v16; // eax
  int v17; // eax
  __int64 Memory; // rdi
  __int64 v19; // rsi
  char v20; // r15
  __int64 v21; // rdx
  KSPIN_LOCK *v22; // rax
  KSPIN_LOCK *v23; // r13
  int v24; // eax
  bool v25; // r10
  __int64 v26; // r15
  __int64 v27; // rdx
  unsigned int v28; // r9d
  bool v29; // cf
  __int64 v30; // rcx
  unsigned __int64 v31; // r10
  __int64 v32; // r11
  __int64 v33; // r12
  __int64 v34; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v35; // rcx
  unsigned int v36; // [rsp+40h] [rbp-29h]
  int v37; // [rsp+44h] [rbp-25h]
  unsigned int v38; // [rsp+48h] [rbp-21h] BYREF
  int v39; // [rsp+4Ch] [rbp-1Dh]
  unsigned int v40; // [rsp+50h] [rbp-19h]
  KSPIN_LOCK *i; // [rsp+58h] [rbp-11h]
  unsigned int v42; // [rsp+60h] [rbp-9h]
  unsigned int v43; // [rsp+64h] [rbp-5h]
  int v44; // [rsp+68h] [rbp-1h]
  __int64 v45; // [rsp+70h] [rbp+7h]
  int v48; // [rsp+E8h] [rbp+7Fh] BYREF

  v2 = *((_DWORD *)a1 + 8);
  v3 = a1;
  v38 = 0;
  v48 = 0;
  if ( !v2 )
    return 3221225474LL;
  v4 = v2 - 1;
  if ( v4 )
  {
    if ( v4 != 1 )
      return 3221225485LL;
    return 3221225474LL;
  }
  v36 = *((_DWORD *)a1 + 22);
  v42 = a2 != 0 ? 64 : 36;
  v6 = *a1;
  v7 = -(a2 != 0) - 66846204;
  v43 = 0xFFFFFFEF / v42;
  v37 = v7;
  v8 = (KSPIN_LOCK *)(*(_QWORD *)(v6 + 40) + 440LL);
  v9 = 0;
  v40 = 0;
  v39 = 0;
LABEL_6:
  v10 = v8 + 3;
  v11 = 0;
  RtlAcquireReadLock(v8);
  v13 = v8[4];
  while ( (KSPIN_LOCK *)v13 != v10 )
  {
    v14 = v13 - 16;
    if ( ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v13 - 16 + 80), 1u) )
    {
      LOBYTE(v12) = 0;
      RtlReleaseReadLock(v8, v12);
      BYTE1(v48) = 0;
      v15 = FlpNdisRequestUnderReference((int)v13 - 16, 0, 0, v7, (__int64)&v48, 4, (__int64)&v38);
      if ( v15 == -1073741789 )
      {
        if ( v38 < 0x10 || BYTE1(v48) != 1 )
        {
          v15 = -1073741262;
          goto LABEL_68;
        }
        v16 = (v38 - 16) / v42 + 20;
        if ( v16 > v43 )
          v16 = v43;
        if ( v16 > v9 )
          v9 = v16;
        v40 = v9;
        if ( v16 + v11 < v11 )
        {
          v15 = -1073741675;
LABEL_68:
          ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v14 + 80), 1u);
          return (unsigned int)v15;
        }
        v11 += v16;
      }
      else if ( v15 != -1073741637 )
      {
        if ( v15 >= 0 )
          v15 = -1073741823;
        goto LABEL_68;
      }
      RtlAcquireReadLock(v8);
      v13 = *(_QWORD *)(v13 + 8);
      ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v14 + 80), 1u);
      v7 = v37;
    }
    else
    {
      v13 = *(_QWORD *)(v13 + 8);
    }
    v10 = v8 + 3;
  }
  LOBYTE(v12) = 0;
  RtlReleaseReadLock(v8, v12);
  if ( v36 < v11 )
  {
    *((_DWORD *)v3 + 22) = v11;
    return v36 != 0 ? 0x105u : 0;
  }
  if ( a2 )
    v17 = v9 << 6;
  else
    v17 = 36 * v9;
  v44 = v17 + 16;
  Memory = FlpAllocateMemory((unsigned int)(v17 + 16));
  if ( !Memory )
    return (unsigned int)-1073741670;
  v15 = 0;
  v19 = 0;
  v20 = 0;
  RtlAcquireReadLock(v8);
  v22 = (KSPIN_LOCK *)v8[4];
LABEL_28:
  for ( i = v22; ; v22 = i )
  {
    if ( v22 == v8 + 3 )
    {
      LOBYTE(v21) = 0;
      RtlReleaseReadLock(v8, v21);
      if ( v20 && v15 == -1073741637 )
        v15 = 0;
      *((_DWORD *)v3 + 22) = v19;
      goto LABEL_79;
    }
    v23 = v22 - 2;
    if ( !ExAcquireRundownProtectionCacheAwareEx((PEX_RUNDOWN_REF_CACHE_AWARE)v22[8], 1u) )
    {
      v22 = (KSPIN_LOCK *)i[1];
      goto LABEL_28;
    }
    LOBYTE(v21) = 0;
    RtlReleaseReadLock(v8, v21);
    v24 = FlpNdisRequestUnderReference((_DWORD)v23, 0, 0, v37, Memory, v44, 0);
    v15 = v24;
    if ( v24 == -1073741789 )
      goto LABEL_65;
    v25 = 0;
    if ( v24 < 0 )
      break;
    v26 = v3[2];
    v27 = v3[9];
    v45 = v26;
    if ( !a2 )
    {
      v32 = 0;
      if ( (unsigned int)v19 >= v36 )
      {
LABEL_59:
        v25 = (unsigned int)v32 < *(_DWORD *)(Memory + 8);
        goto LABEL_60;
      }
      v33 = v45;
      while ( 1 )
      {
        if ( (unsigned int)v32 >= *(_DWORD *)(Memory + 8) )
        {
LABEL_58:
          v3 = a1;
          goto LABEL_59;
        }
        v34 = 32LL * (unsigned int)v19;
        *(_DWORD *)(v34 + v33) = *((_DWORD *)v23 + 294);
        *(_OWORD *)(v34 + v33 + 4) = *(_OWORD *)(Memory + 36 * v32 + 16);
        *(_OWORD *)(v34 + v33 + 16) = *(_OWORD *)(Memory + 36 * v32 + 28);
        if ( v27 )
        {
          if ( *(_BYTE *)(Memory + 12) )
          {
            if ( (v32 & 1) != 0 )
            {
              *(_BYTE *)(v27 + 8 * v19) = 0;
              goto LABEL_57;
            }
            *(_BYTE *)(v27 + 8 * v19) = 1;
          }
          else
          {
            *(_BYTE *)(v27 + 8 * v19) = 0;
          }
          *(_BYTE *)(v27 + 8 * v19 + 1) = *(_BYTE *)(Memory + 36 * v32 + 44);
          *(_DWORD *)(v27 + 8 * v19 + 4) = *(_DWORD *)(Memory + 36 * v32 + 48);
          *(_BYTE *)(v27 + 8 * v19 + 2) = *(_BYTE *)(Memory + 36 * v32 + 45);
        }
LABEL_57:
        v19 = (unsigned int)(v19 + 1);
        v32 = (unsigned int)(v32 + 1);
        if ( (unsigned int)v19 >= v36 )
          goto LABEL_58;
      }
    }
    v28 = 0;
    while ( (unsigned int)v19 < v36 )
    {
      v29 = v28 < *(_DWORD *)(Memory + 8);
      if ( v28 >= *(_DWORD *)(Memory + 8) )
        goto LABEL_46;
      v30 = 60LL * (unsigned int)v19;
      v31 = (unsigned __int64)v28 << 6;
      *(_DWORD *)(v30 + v26) = *((_DWORD *)v23 + 294);
      *(_OWORD *)(v30 + v26 + 4) = *(_OWORD *)(v31 + Memory + 16);
      *(_OWORD *)(v30 + v26 + 16) = *(_OWORD *)(v31 + Memory + 28);
      *(_OWORD *)(v30 + v26 + 32) = *(_OWORD *)(v31 + Memory + 44);
      *(_OWORD *)(v30 + v26 + 44) = *(_OWORD *)(v31 + Memory + 56);
      if ( v27 )
      {
        if ( !*(_BYTE *)(Memory + 12) )
        {
          *(_BYTE *)(v27 + 8 * v19) = 0;
LABEL_41:
          *(_BYTE *)(v27 + 8 * v19 + 1) = *(_BYTE *)(v31 + Memory + 72);
          *(_DWORD *)(v27 + 8 * v19 + 4) = *(_DWORD *)(v31 + Memory + 76);
          goto LABEL_43;
        }
        if ( (v28 & 1) == 0 )
        {
          *(_BYTE *)(v27 + 8 * v19) = 1;
          goto LABEL_41;
        }
        *(_BYTE *)(v27 + 8 * v19) = 0;
      }
LABEL_43:
      v19 = (unsigned int)(v19 + 1);
      ++v28;
    }
    v29 = v28 < *(_DWORD *)(Memory + 8);
LABEL_46:
    v25 = v29;
LABEL_60:
    v20 = 1;
LABEL_62:
    if ( v25 )
    {
LABEL_65:
      ExReleaseRundownProtectionCacheAwareEx((PEX_RUNDOWN_REF_CACHE_AWARE)v23[10], 1u);
      if ( (unsigned int)++v39 >= 0xA )
      {
        v15 = -1073741823;
        goto LABEL_79;
      }
      ExFreePoolWithTag((PVOID)Memory, 0);
      v9 = v40;
      v7 = v37;
      goto LABEL_6;
    }
    RtlAcquireReadLock(v8);
    v35 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)v23[10];
    i = (KSPIN_LOCK *)i[1];
    ExReleaseRundownProtectionCacheAwareEx(v35, 1u);
  }
  if ( v24 == -1073741637 )
    goto LABEL_62;
  ExReleaseRundownProtectionCacheAwareEx((PEX_RUNDOWN_REF_CACHE_AWARE)v23[10], 1u);
LABEL_79:
  ExFreePoolWithTag((PVOID)Memory, 0);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1401ad758  mov     [rsp-8+arg_8], dl
0x1401ad75c  mov     [rsp-8+arg_0], rcx
0x1401ad761  push    rbp
0x1401ad762  push    rbx
0x1401ad763  push    rsi
0x1401ad764  push    rdi
0x1401ad765  push    r12
0x1401ad767  push    r13
0x1401ad769  push    r14
0x1401ad76b  push    r15
0x1401ad76d  lea     rbp, [rsp-1Fh]
0x1401ad772  sub     rsp, 88h
0x1401ad779  mov     r8d, [rcx+20h]
0x1401ad77d  mov     r12, rcx
0x1401ad780  mov     [rbp+57h+var_78], 0
0x1401ad787  mov     [rbp+57h+arg_10], 0
0x1401ad78b  mov     [rbp+57h+arg_18], 0
0x1401ad792  test    r8d, r8d
0x1401ad795  jz      loc_1401ADC9C
0x1401ad79b  sub     r8d, 1
0x1401ad79f  jz      short loc_1401AD7B5
0x1401ad7a1  cmp     r8d, 1
0x1401ad7a5  jz      loc_1401ADC9C
0x1401ad7ab  mov     eax, 0C000000Dh
0x1401ad7b0  jmp     loc_1401ADCA1
0x1401ad7b5  mov     eax, [rcx+58h]
0x1401ad7b8  mov     [rbp+57h+var_80], eax
0x1401ad7bb  mov     al, dl
0x1401ad7bd  neg     al
0x1401ad7bf  mov     al, dl
0x1401ad7c1  sbb     ecx, ecx
0x1401ad7c3  and     ecx, 1Ch
0x1401ad7c6  add     ecx, 24h ; '$'
0x1401ad7c9  neg     al
0x1401ad7cb  mov     [rbp+57h+var_60], ecx
0x1401ad7ce  mov     eax, 0FFFFFFEFh
0x1401ad7d3  sbb     ebx, ebx
0x1401ad7d5  xor     edx, edx
0x1401ad7d7  div     ecx
0x1401ad7d9  mov     rcx, [r12]
0x1401ad7dd  add     ebx, 0FC040204h
0x1401ad7e3  mov     [rbp+57h+var_5C], eax
0x1401ad7e6  mov     [rbp+57h+var_7C], ebx
0x1401ad7e9  mov     r14, [rcx+28h]
0x1401ad7ed  add     r14, 1B8h
0x1401ad7f4  xor     r13d, r13d
0x1401ad7f7  mov     [rbp+57h+var_70], r13d
0x1401ad7fb  mov     [rbp+57h+var_74], r13d
0x1401ad7ff  lea     rdi, [r14+18h]
0x1401ad803  xor     r15d, r15d
0x1401ad806  lea     rdx, [rbp+57h+arg_10]
0x1401ad80a  mov     rcx, r14; SpinLock
0x1401ad80d  call    RtlAcquireReadLock
0x1401ad812  mov     rsi, [r14+20h]
0x1401ad816  cmp     rsi, rdi
0x1401ad819  jz      loc_1401AD916
0x1401ad81f  lea     rdi, [rsi-10h]
0x1401ad823  mov     edx, 1; Count
0x1401ad828  mov     rcx, [rdi+50h]; RunRefCacheAware
0x1401ad82c  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1401ad833  nop     dword ptr [rax+rax+00h]
0x1401ad838  test    al, al
0x1401ad83a  jz      loc_1401AD909
0x1401ad840  mov     dl, [rbp+57h+arg_10]
0x1401ad843  mov     rcx, r14
0x1401ad846  call    RtlReleaseReadLock
0x1401ad84b  lea     rax, [rbp+57h+var_78]
0x1401ad84f  mov     byte ptr [rbp+57h+arg_18+1], 0
0x1401ad856  mov     [rsp+0C0h+var_90], rax
0x1401ad85b  mov     r9d, ebx
0x1401ad85e  lea     rax, [rbp+57h+arg_18]
0x1401ad862  mov     [rsp+0C0h+var_98], 4
0x1401ad86a  xor     r8d, r8d
0x1401ad86d  mov     [rsp+0C0h+var_A0], rax
0x1401ad872  xor     edx, edx
0x1401ad874  mov     rcx, rdi
0x1401ad877  call    FlpNdisRequestUnderReference
0x1401ad87c  mov     ebx, eax
0x1401ad87e  cmp     eax, 0C0000023h
0x1401ad883  jnz     short loc_1401AD8D3
0x1401ad885  mov     eax, [rbp+57h+var_78]
0x1401ad888  mov     r8d, 1
0x1401ad88e  cmp     eax, 10h
0x1401ad891  jb      loc_1401ADC19
0x1401ad897  cmp     byte ptr [rbp+57h+arg_18+1], r8b
0x1401ad89e  jnz     loc_1401ADC19
0x1401ad8a4  add     eax, 0FFFFFFF0h
0x1401ad8a7  xor     edx, edx
0x1401ad8a9  div     [rbp+57h+var_60]
0x1401ad8ac  add     eax, 14h
0x1401ad8af  cmp     eax, [rbp+57h+var_5C]
0x1401ad8b2  cmova   eax, [rbp+57h+var_5C]
0x1401ad8b6  cmp     eax, r13d
0x1401ad8b9  cmova   r13d, eax
0x1401ad8bd  lea     ecx, [rax+r15]
0x1401ad8c1  mov     [rbp+57h+var_70], r13d
0x1401ad8c5  cmp     ecx, r15d
0x1401ad8c8  jb      loc_1401ADBFF
0x1401ad8ce  mov     r15d, ecx
0x1401ad8d1  jmp     short loc_1401AD8DF
0x1401ad8d3  cmp     ebx, 0C00000BBh
0x1401ad8d9  jnz     loc_1401ADC20
0x1401ad8df  lea     rdx, [rbp+57h+arg_10]
0x1401ad8e3  mov     rcx, r14; SpinLock
0x1401ad8e6  call    RtlAcquireReadLock
0x1401ad8eb  mov     rcx, [rdi+50h]; RunRef
0x1401ad8ef  mov     edx, 1; Count
0x1401ad8f4  mov     rsi, [rsi+8]
0x1401ad8f8  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1401ad8ff  nop     dword ptr [rax+rax+00h]
0x1401ad904  mov     ebx, [rbp+57h+var_7C]
0x1401ad907  jmp     short loc_1401AD90D
0x1401ad909  mov     rsi, [rsi+8]
0x1401ad90d  lea     rdi, [r14+18h]
0x1401ad911  jmp     loc_1401AD816
0x1401ad916  mov     dl, [rbp+57h+arg_10]
0x1401ad919  mov     rcx, r14
0x1401ad91c  call    RtlReleaseReadLock
0x1401ad921  mov     ebx, [rbp+57h+var_80]
0x1401ad924  cmp     ebx, r15d
0x1401ad927  jb      loc_1401ADC89
0x1401ad92d  cmp     [rbp+57h+arg_8], 0
0x1401ad931  jz      short loc_1401AD93B
0x1401ad933  mov     eax, r13d
0x1401ad936  shl     eax, 6
0x1401ad939  jmp     short loc_1401AD949
0x1401ad93b  lea     eax, ds:0[r13*8]
0x1401ad943  add     eax, r13d
0x1401ad946  shl     eax, 2
0x1401ad949  add     eax, 10h
0x1401ad94c  mov     ecx, eax
0x1401ad94e  mov     [rbp+57h+var_58], eax
0x1401ad951  call    FlpAllocateMemory
0x1401ad956  mov     rdi, rax
0x1401ad959  test    rax, rax
0x1401ad95c  jz      loc_1401ADC82
0x1401ad962  xor     ebx, ebx
0x1401ad964  lea     rdx, [rbp+57h+arg_10]
0x1401ad968  xor     esi, esi
0x1401ad96a  xor     r15b, r15b
0x1401ad96d  mov     rcx, r14; SpinLock
0x1401ad970  call    RtlAcquireReadLock
0x1401ad975  mov     rax, [r14+20h]
0x1401ad979  mov     [rbp+57h+var_68], rax
0x1401ad97d  lea     rcx, [r14+18h]
0x1401ad981  cmp     rax, rcx
0x1401ad984  jz      loc_1401ADC4F
0x1401ad98a  lea     r13, [rax-10h]
0x1401ad98e  mov     edx, 1; Count
0x1401ad993  mov     rcx, [r13+50h]; RunRefCacheAware
0x1401ad997  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1401ad99e  nop     dword ptr [rax+rax+00h]
0x1401ad9a3  test    al, al
0x1401ad9a5  jz      loc_1401ADBB1
0x1401ad9ab  mov     dl, [rbp+57h+arg_10]
0x1401ad9ae  mov     rcx, r14
0x1401ad9b1  call    RtlReleaseReadLock
0x1401ad9b6  mov     eax, [rbp+57h+var_58]
0x1401ad9b9  xor     r8d, r8d
0x1401ad9bc  mov     r9d, [rbp+57h+var_7C]
0x1401ad9c0  xor     edx, edx
0x1401ad9c2  mov     [rsp+0C0h+var_90], 0
0x1401ad9cb  mov     rcx, r13
0x1401ad9ce  mov     [rsp+0C0h+var_98], eax
0x1401ad9d2  mov     [rsp+0C0h+var_A0], rdi
0x1401ad9d7  call    FlpNdisRequestUnderReference
0x1401ad9dc  mov     ebx, eax
0x1401ad9de  cmp     eax, 0C0000023h
0x1401ad9e3  jz      loc_1401ADBBE
0x1401ad9e9  xor     r10b, r10b
0x1401ad9ec  test    eax, eax
0x1401ad9ee  js      loc_1401ADB6B
0x1401ad9f4  mov     r15, [r12+10h]
0x1401ad9f9  mov     rdx, [r12+48h]
0x1401ad9fe  mov     [rbp+57h+var_50], r15
0x1401ada02  cmp     [rbp+57h+arg_8], r10b
0x1401ada06  jz      loc_1401ADAC1
0x1401ada0c  mov     r11d, [rbp+57h+var_80]
0x1401ada10  xor     r9d, r9d
0x1401ada13  jmp     loc_1401ADAA6
0x1401ada18  cmp     r9d, [rdi+8]
0x1401ada1c  jnb     loc_1401ADAB3
0x1401ada22  mov     eax, [r13+498h]
0x1401ada29  mov     r8d, esi
0x1401ada2c  imul    rcx, r8, 3Ch ; '<'
0x1401ada30  mov     r10d, r9d
0x1401ada33  shl     r10, 6
0x1401ada37  mov     [rcx+r15], eax
0x1401ada3b  movups  xmm0, xmmword ptr [r10+rdi+10h]
0x1401ada41  movups  xmmword ptr [rcx+r15+4], xmm0
0x1401ada47  movups  xmm1, xmmword ptr [r10+rdi+1Ch]
0x1401ada4d  movups  xmmword ptr [rcx+r15+10h], xmm1
0x1401ada53  movups  xmm0, xmmword ptr [r10+rdi+2Ch]
0x1401ada59  movups  xmmword ptr [rcx+r15+20h], xmm0
0x1401ada5f  movups  xmm1, xmmword ptr [r10+rdi+38h]
0x1401ada65  movups  xmmword ptr [rcx+r15+2Ch], xmm1
0x1401ada6b  mov     ecx, 1
0x1401ada70  test    rdx, rdx
0x1401ada73  jz      short loc_1401ADAA1
0x1401ada75  cmp     byte ptr [rdi+0Ch], 0
0x1401ada79  jnz     short loc_1401ADA81
0x1401ada7b  mov     byte ptr [rdx+rsi*8], 0
0x1401ada7f  jmp     short loc_1401ADA89
0x1401ada81  test    cl, r9b
0x1401ada84  jnz     short loc_1401ADA9D
0x1401ada86  mov     [rdx+rsi*8], cl
0x1401ada89  mov     al, [r10+rdi+48h]
0x1401ada8e  mov     [rdx+rsi*8+1], al
0x1401ada92  mov     eax, [r10+rdi+4Ch]
0x1401ada97  mov     [rdx+rsi*8+4], eax
0x1401ada9b  jmp     short loc_1401ADAA1
0x1401ada9d  mov     byte ptr [rdx+rsi*8], 0
0x1401adaa1  add     esi, ecx
0x1401adaa3  add     r9d, ecx
0x1401adaa6  cmp     esi, r11d
0x1401adaa9  jb      loc_1401ADA18
0x1401adaaf  cmp     r9d, [rdi+8]
0x1401adab3  setb    r10b
0x1401adab7  mov     eax, 1
0x1401adabc  jmp     loc_1401ADB66
0x1401adac1  mov     r15d, [rbp+57h+var_80]
0x1401adac5  xor     r11d, r11d
0x1401adac8  cmp     esi, r15d
0x1401adacb  jnb     loc_1401ADB55
0x1401adad1  mov     r12, [rbp+57h+var_50]
0x1401adad5  cmp     r11d, [rdi+8]
0x1401adad9  jnb     short loc_1401ADB51
0x1401adadb  mov     eax, [r13+498h]
0x1401adae2  lea     r9, [r11+r11*8]
0x1401adae6  mov     ecx, esi
0x1401adae8  shl     rcx, 5
0x1401adaec  mov     [rcx+r12], eax
0x1401adaf0  movups  xmm0, xmmword ptr [rdi+r9*4+10h]
0x1401adaf6  movups  xmmword ptr [rcx+r12+4], xmm0
0x1401adafc  movups  xmm1, xmmword ptr [rdi+r9*4+1Ch]
0x1401adb02  movups  xmmword ptr [rcx+r12+10h], xmm1
0x1401adb08  mov     ecx, 1
0x1401adb0d  test    rdx, rdx
0x1401adb10  jz      short loc_1401ADB47
0x1401adb12  cmp     [rdi+0Ch], r10b
0x1401adb16  jnz     short loc_1401ADB1E
0x1401adb18  mov     [rdx+rsi*8], r10b
0x1401adb1c  jmp     short loc_1401ADB26
0x1401adb1e  test    cl, r11b
0x1401adb21  jnz     short loc_1401ADB43
0x1401adb23  mov     [rdx+rsi*8], cl
0x1401adb26  mov     al, [rdi+r9*4+2Ch]
0x1401adb2b  mov     [rdx+rsi*8+1], al
0x1401adb2f  mov     eax, [rdi+r9*4+30h]
0x1401adb34  mov     [rdx+rsi*8+4], eax
0x1401adb38  mov     al, [rdi+r9*4+2Dh]
0x1401adb3d  mov     [rdx+rsi*8+2], al
0x1401adb41  jmp     short loc_1401ADB47
0x1401adb43  mov     [rdx+rsi*8], r10b
0x1401adb47  add     esi, ecx
0x1401adb49  add     r11d, ecx
0x1401adb4c  cmp     esi, r15d
0x1401adb4f  jb      short loc_1401ADAD5
0x1401adb51  mov     r12, [rbp+57h+arg_0]
0x1401adb55  cmp     r11d, [rdi+8]
0x1401adb59  mov     eax, 1
0x1401adb5e  movzx   r10d, r10b
0x1401adb62  cmovb   r10d, eax
0x1401adb66  mov     r15b, al
0x1401adb69  jmp     short loc_1401ADB76
0x1401adb6b  cmp     eax, 0C00000BBh
0x1401adb70  jnz     loc_1401ADC31
0x1401adb76  test    r10b, r10b
0x1401adb79  jnz     short loc_1401ADBBE
0x1401adb7b  lea     rdx, [rbp+57h+arg_10]
0x1401adb7f  mov     rcx, r14; SpinLock
0x1401adb82  call    RtlAcquireReadLock
0x1401adb87  mov     rax, [rbp+57h+var_68]
0x1401adb8b  mov     edx, 1; Count
0x1401adb90  mov     rcx, [r13+50h]; RunRef
0x1401adb94  mov     rax, [rax+8]
0x1401adb98  mov     [rbp+57h+var_68], rax
0x1401adb9c  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1401adba3  nop     dword ptr [rax+rax+00h]
0x1401adba8  mov     rax, [rbp+57h+var_68]
0x1401adbac  jmp     loc_1401AD97D
0x1401adbb1  mov     rax, [rbp+57h+var_68]
0x1401adbb5  mov     rax, [rax+8]
0x1401adbb9  jmp     loc_1401AD979
0x1401adbbe  mov     rcx, [r13+50h]; RunRef
0x1401adbc2  mov     esi, 1
0x1401adbc7  mov     edx, esi; Count
0x1401adbc9  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1401adbd0  nop     dword ptr [rax+rax+00h]
0x1401adbd5  mov     ebx, [rbp+57h+var_74]
0x1401adbd8  add     ebx, esi
0x1401adbda  mov     [rbp+57h+var_74], ebx
0x1401adbdd  cmp     ebx, 0Ah
0x1401adbe0  jnb     short loc_1401ADC48
0x1401adbe2  xor     edx, edx; Tag
0x1401adbe4  mov     rcx, rdi; P
0x1401adbe7  call    cs:__imp_ExFreePoolWithTag
0x1401adbee  nop     dword ptr [rax+rax+00h]
0x1401adbf3  mov     r13d, [rbp+57h+var_70]
0x1401adbf7  mov     ebx, [rbp+57h+var_7C]
  ... truncated ...
```
