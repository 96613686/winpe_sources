# FlRdmaNsiEnumerateNdkItemsCommon

- ea: `0x1401ad898`
- end: `0x1401addf6`
- name: `FlRdmaNsiEnumerateNdkItemsCommon`
- size: `1374`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1401ad6f0`
- `0x1401ad880`

## callees

- `0x14004c760`
- `0x140072ff0`
- `0x1400c64e0`
- `0x1400c80d8`
- `0x1401ad898`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401ada38`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401adcdc`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401add09`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401add4b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401add7a`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401ada38`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401adcdc`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401add09`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401add4b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401add7a`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401ad96c`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401adad7`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401ad96c`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401adad7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401add27`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401addb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401add27`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401addb4`

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
0x1401ad898  mov     [rsp-8+arg_8], dl
0x1401ad89c  mov     [rsp-8+arg_0], rcx
0x1401ad8a1  push    rbp
0x1401ad8a2  push    rbx
0x1401ad8a3  push    rsi
0x1401ad8a4  push    rdi
0x1401ad8a5  push    r12
0x1401ad8a7  push    r13
0x1401ad8a9  push    r14
0x1401ad8ab  push    r15
0x1401ad8ad  lea     rbp, [rsp-1Fh]
0x1401ad8b2  sub     rsp, 88h
0x1401ad8b9  mov     r8d, [rcx+20h]
0x1401ad8bd  mov     r12, rcx
0x1401ad8c0  mov     [rbp+57h+var_78], 0
0x1401ad8c7  mov     [rbp+57h+arg_10], 0
0x1401ad8cb  mov     [rbp+57h+arg_18], 0
0x1401ad8d2  test    r8d, r8d
0x1401ad8d5  jz      loc_1401ADDDC
0x1401ad8db  sub     r8d, 1
0x1401ad8df  jz      short loc_1401AD8F5
0x1401ad8e1  cmp     r8d, 1
0x1401ad8e5  jz      loc_1401ADDDC
0x1401ad8eb  mov     eax, 0C000000Dh
0x1401ad8f0  jmp     loc_1401ADDE1
0x1401ad8f5  mov     eax, [rcx+58h]
0x1401ad8f8  mov     [rbp+57h+var_80], eax
0x1401ad8fb  mov     al, dl
0x1401ad8fd  neg     al
0x1401ad8ff  mov     al, dl
0x1401ad901  sbb     ecx, ecx
0x1401ad903  and     ecx, 1Ch
0x1401ad906  add     ecx, 24h ; '$'
0x1401ad909  neg     al
0x1401ad90b  mov     [rbp+57h+var_60], ecx
0x1401ad90e  mov     eax, 0FFFFFFEFh
0x1401ad913  sbb     ebx, ebx
0x1401ad915  xor     edx, edx
0x1401ad917  div     ecx
0x1401ad919  mov     rcx, [r12]
0x1401ad91d  add     ebx, 0FC040204h
0x1401ad923  mov     [rbp+57h+var_5C], eax
0x1401ad926  mov     [rbp+57h+var_7C], ebx
0x1401ad929  mov     r14, [rcx+28h]
0x1401ad92d  add     r14, 1B8h
0x1401ad934  xor     r13d, r13d
0x1401ad937  mov     [rbp+57h+var_70], r13d
0x1401ad93b  mov     [rbp+57h+var_74], r13d
0x1401ad93f  lea     rdi, [r14+18h]
0x1401ad943  xor     r15d, r15d
0x1401ad946  lea     rdx, [rbp+57h+arg_10]
0x1401ad94a  mov     rcx, r14; SpinLock
0x1401ad94d  call    RtlAcquireReadLock
0x1401ad952  mov     rsi, [r14+20h]
0x1401ad956  cmp     rsi, rdi
0x1401ad959  jz      loc_1401ADA56
0x1401ad95f  lea     rdi, [rsi-10h]
0x1401ad963  mov     edx, 1; Count
0x1401ad968  mov     rcx, [rdi+50h]; RunRefCacheAware
0x1401ad96c  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1401ad973  nop     dword ptr [rax+rax+00h]
0x1401ad978  test    al, al
0x1401ad97a  jz      loc_1401ADA49
0x1401ad980  mov     dl, [rbp+57h+arg_10]
0x1401ad983  mov     rcx, r14
0x1401ad986  call    RtlReleaseReadLock
0x1401ad98b  lea     rax, [rbp+57h+var_78]
0x1401ad98f  mov     byte ptr [rbp+57h+arg_18+1], 0
0x1401ad996  mov     [rsp+0C0h+var_90], rax
0x1401ad99b  mov     r9d, ebx
0x1401ad99e  lea     rax, [rbp+57h+arg_18]
0x1401ad9a2  mov     [rsp+0C0h+var_98], 4
0x1401ad9aa  xor     r8d, r8d
0x1401ad9ad  mov     [rsp+0C0h+var_A0], rax
0x1401ad9b2  xor     edx, edx
0x1401ad9b4  mov     rcx, rdi
0x1401ad9b7  call    FlpNdisRequestUnderReference
0x1401ad9bc  mov     ebx, eax
0x1401ad9be  cmp     eax, 0C0000023h
0x1401ad9c3  jnz     short loc_1401ADA13
0x1401ad9c5  mov     eax, [rbp+57h+var_78]
0x1401ad9c8  mov     r8d, 1
0x1401ad9ce  cmp     eax, 10h
0x1401ad9d1  jb      loc_1401ADD59
0x1401ad9d7  cmp     byte ptr [rbp+57h+arg_18+1], r8b
0x1401ad9de  jnz     loc_1401ADD59
0x1401ad9e4  add     eax, 0FFFFFFF0h
0x1401ad9e7  xor     edx, edx
0x1401ad9e9  div     [rbp+57h+var_60]
0x1401ad9ec  add     eax, 14h
0x1401ad9ef  cmp     eax, [rbp+57h+var_5C]
0x1401ad9f2  cmova   eax, [rbp+57h+var_5C]
0x1401ad9f6  cmp     eax, r13d
0x1401ad9f9  cmova   r13d, eax
0x1401ad9fd  lea     ecx, [rax+r15]
0x1401ada01  mov     [rbp+57h+var_70], r13d
0x1401ada05  cmp     ecx, r15d
0x1401ada08  jb      loc_1401ADD3F
0x1401ada0e  mov     r15d, ecx
0x1401ada11  jmp     short loc_1401ADA1F
0x1401ada13  cmp     ebx, 0C00000BBh
0x1401ada19  jnz     loc_1401ADD60
0x1401ada1f  lea     rdx, [rbp+57h+arg_10]
0x1401ada23  mov     rcx, r14; SpinLock
0x1401ada26  call    RtlAcquireReadLock
0x1401ada2b  mov     rcx, [rdi+50h]; RunRef
0x1401ada2f  mov     edx, 1; Count
0x1401ada34  mov     rsi, [rsi+8]
0x1401ada38  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1401ada3f  nop     dword ptr [rax+rax+00h]
0x1401ada44  mov     ebx, [rbp+57h+var_7C]
0x1401ada47  jmp     short loc_1401ADA4D
0x1401ada49  mov     rsi, [rsi+8]
0x1401ada4d  lea     rdi, [r14+18h]
0x1401ada51  jmp     loc_1401AD956
0x1401ada56  mov     dl, [rbp+57h+arg_10]
0x1401ada59  mov     rcx, r14
0x1401ada5c  call    RtlReleaseReadLock
0x1401ada61  mov     ebx, [rbp+57h+var_80]
0x1401ada64  cmp     ebx, r15d
0x1401ada67  jb      loc_1401ADDC9
0x1401ada6d  cmp     [rbp+57h+arg_8], 0
0x1401ada71  jz      short loc_1401ADA7B
0x1401ada73  mov     eax, r13d
0x1401ada76  shl     eax, 6
0x1401ada79  jmp     short loc_1401ADA89
0x1401ada7b  lea     eax, ds:0[r13*8]
0x1401ada83  add     eax, r13d
0x1401ada86  shl     eax, 2
0x1401ada89  add     eax, 10h
0x1401ada8c  mov     ecx, eax
0x1401ada8e  mov     [rbp+57h+var_58], eax
0x1401ada91  call    FlpAllocateMemory
0x1401ada96  mov     rdi, rax
0x1401ada99  test    rax, rax
0x1401ada9c  jz      loc_1401ADDC2
0x1401adaa2  xor     ebx, ebx
0x1401adaa4  lea     rdx, [rbp+57h+arg_10]
0x1401adaa8  xor     esi, esi
0x1401adaaa  xor     r15b, r15b
0x1401adaad  mov     rcx, r14; SpinLock
0x1401adab0  call    RtlAcquireReadLock
0x1401adab5  mov     rax, [r14+20h]
0x1401adab9  mov     [rbp+57h+var_68], rax
0x1401adabd  lea     rcx, [r14+18h]
0x1401adac1  cmp     rax, rcx
0x1401adac4  jz      loc_1401ADD8F
0x1401adaca  lea     r13, [rax-10h]
0x1401adace  mov     edx, 1; Count
0x1401adad3  mov     rcx, [r13+50h]; RunRefCacheAware
0x1401adad7  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1401adade  nop     dword ptr [rax+rax+00h]
0x1401adae3  test    al, al
0x1401adae5  jz      loc_1401ADCF1
0x1401adaeb  mov     dl, [rbp+57h+arg_10]
0x1401adaee  mov     rcx, r14
0x1401adaf1  call    RtlReleaseReadLock
0x1401adaf6  mov     eax, [rbp+57h+var_58]
0x1401adaf9  xor     r8d, r8d
0x1401adafc  mov     r9d, [rbp+57h+var_7C]
0x1401adb00  xor     edx, edx
0x1401adb02  mov     [rsp+0C0h+var_90], 0
0x1401adb0b  mov     rcx, r13
0x1401adb0e  mov     [rsp+0C0h+var_98], eax
0x1401adb12  mov     [rsp+0C0h+var_A0], rdi
0x1401adb17  call    FlpNdisRequestUnderReference
0x1401adb1c  mov     ebx, eax
0x1401adb1e  cmp     eax, 0C0000023h
0x1401adb23  jz      loc_1401ADCFE
0x1401adb29  xor     r10b, r10b
0x1401adb2c  test    eax, eax
0x1401adb2e  js      loc_1401ADCAB
0x1401adb34  mov     r15, [r12+10h]
0x1401adb39  mov     rdx, [r12+48h]
0x1401adb3e  mov     [rbp+57h+var_50], r15
0x1401adb42  cmp     [rbp+57h+arg_8], r10b
0x1401adb46  jz      loc_1401ADC01
0x1401adb4c  mov     r11d, [rbp+57h+var_80]
0x1401adb50  xor     r9d, r9d
0x1401adb53  jmp     loc_1401ADBE6
0x1401adb58  cmp     r9d, [rdi+8]
0x1401adb5c  jnb     loc_1401ADBF3
0x1401adb62  mov     eax, [r13+498h]
0x1401adb69  mov     r8d, esi
0x1401adb6c  imul    rcx, r8, 3Ch ; '<'
0x1401adb70  mov     r10d, r9d
0x1401adb73  shl     r10, 6
0x1401adb77  mov     [rcx+r15], eax
0x1401adb7b  movups  xmm0, xmmword ptr [r10+rdi+10h]
0x1401adb81  movups  xmmword ptr [rcx+r15+4], xmm0
0x1401adb87  movups  xmm1, xmmword ptr [r10+rdi+1Ch]
0x1401adb8d  movups  xmmword ptr [rcx+r15+10h], xmm1
0x1401adb93  movups  xmm0, xmmword ptr [r10+rdi+2Ch]
0x1401adb99  movups  xmmword ptr [rcx+r15+20h], xmm0
0x1401adb9f  movups  xmm1, xmmword ptr [r10+rdi+38h]
0x1401adba5  movups  xmmword ptr [rcx+r15+2Ch], xmm1
0x1401adbab  mov     ecx, 1
0x1401adbb0  test    rdx, rdx
0x1401adbb3  jz      short loc_1401ADBE1
0x1401adbb5  cmp     byte ptr [rdi+0Ch], 0
0x1401adbb9  jnz     short loc_1401ADBC1
0x1401adbbb  mov     byte ptr [rdx+rsi*8], 0
0x1401adbbf  jmp     short loc_1401ADBC9
0x1401adbc1  test    cl, r9b
0x1401adbc4  jnz     short loc_1401ADBDD
0x1401adbc6  mov     [rdx+rsi*8], cl
0x1401adbc9  mov     al, [r10+rdi+48h]
0x1401adbce  mov     [rdx+rsi*8+1], al
0x1401adbd2  mov     eax, [r10+rdi+4Ch]
0x1401adbd7  mov     [rdx+rsi*8+4], eax
0x1401adbdb  jmp     short loc_1401ADBE1
0x1401adbdd  mov     byte ptr [rdx+rsi*8], 0
0x1401adbe1  add     esi, ecx
0x1401adbe3  add     r9d, ecx
0x1401adbe6  cmp     esi, r11d
0x1401adbe9  jb      loc_1401ADB58
0x1401adbef  cmp     r9d, [rdi+8]
0x1401adbf3  setb    r10b
0x1401adbf7  mov     eax, 1
0x1401adbfc  jmp     loc_1401ADCA6
0x1401adc01  mov     r15d, [rbp+57h+var_80]
0x1401adc05  xor     r11d, r11d
0x1401adc08  cmp     esi, r15d
0x1401adc0b  jnb     loc_1401ADC95
0x1401adc11  mov     r12, [rbp+57h+var_50]
0x1401adc15  cmp     r11d, [rdi+8]
0x1401adc19  jnb     short loc_1401ADC91
0x1401adc1b  mov     eax, [r13+498h]
0x1401adc22  lea     r9, [r11+r11*8]
0x1401adc26  mov     ecx, esi
0x1401adc28  shl     rcx, 5
0x1401adc2c  mov     [rcx+r12], eax
0x1401adc30  movups  xmm0, xmmword ptr [rdi+r9*4+10h]
0x1401adc36  movups  xmmword ptr [rcx+r12+4], xmm0
0x1401adc3c  movups  xmm1, xmmword ptr [rdi+r9*4+1Ch]
0x1401adc42  movups  xmmword ptr [rcx+r12+10h], xmm1
0x1401adc48  mov     ecx, 1
0x1401adc4d  test    rdx, rdx
0x1401adc50  jz      short loc_1401ADC87
0x1401adc52  cmp     [rdi+0Ch], r10b
0x1401adc56  jnz     short loc_1401ADC5E
0x1401adc58  mov     [rdx+rsi*8], r10b
0x1401adc5c  jmp     short loc_1401ADC66
0x1401adc5e  test    cl, r11b
0x1401adc61  jnz     short loc_1401ADC83
0x1401adc63  mov     [rdx+rsi*8], cl
0x1401adc66  mov     al, [rdi+r9*4+2Ch]
0x1401adc6b  mov     [rdx+rsi*8+1], al
0x1401adc6f  mov     eax, [rdi+r9*4+30h]
0x1401adc74  mov     [rdx+rsi*8+4], eax
0x1401adc78  mov     al, [rdi+r9*4+2Dh]
0x1401adc7d  mov     [rdx+rsi*8+2], al
0x1401adc81  jmp     short loc_1401ADC87
0x1401adc83  mov     [rdx+rsi*8], r10b
0x1401adc87  add     esi, ecx
0x1401adc89  add     r11d, ecx
0x1401adc8c  cmp     esi, r15d
0x1401adc8f  jb      short loc_1401ADC15
0x1401adc91  mov     r12, [rbp+57h+arg_0]
0x1401adc95  cmp     r11d, [rdi+8]
0x1401adc99  mov     eax, 1
0x1401adc9e  movzx   r10d, r10b
0x1401adca2  cmovb   r10d, eax
0x1401adca6  mov     r15b, al
0x1401adca9  jmp     short loc_1401ADCB6
0x1401adcab  cmp     eax, 0C00000BBh
0x1401adcb0  jnz     loc_1401ADD71
0x1401adcb6  test    r10b, r10b
0x1401adcb9  jnz     short loc_1401ADCFE
0x1401adcbb  lea     rdx, [rbp+57h+arg_10]
0x1401adcbf  mov     rcx, r14; SpinLock
0x1401adcc2  call    RtlAcquireReadLock
0x1401adcc7  mov     rax, [rbp+57h+var_68]
0x1401adccb  mov     edx, 1; Count
0x1401adcd0  mov     rcx, [r13+50h]; RunRef
0x1401adcd4  mov     rax, [rax+8]
0x1401adcd8  mov     [rbp+57h+var_68], rax
0x1401adcdc  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1401adce3  nop     dword ptr [rax+rax+00h]
0x1401adce8  mov     rax, [rbp+57h+var_68]
0x1401adcec  jmp     loc_1401ADABD
0x1401adcf1  mov     rax, [rbp+57h+var_68]
0x1401adcf5  mov     rax, [rax+8]
0x1401adcf9  jmp     loc_1401ADAB9
0x1401adcfe  mov     rcx, [r13+50h]; RunRef
0x1401add02  mov     esi, 1
0x1401add07  mov     edx, esi; Count
0x1401add09  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1401add10  nop     dword ptr [rax+rax+00h]
0x1401add15  mov     ebx, [rbp+57h+var_74]
0x1401add18  add     ebx, esi
0x1401add1a  mov     [rbp+57h+var_74], ebx
0x1401add1d  cmp     ebx, 0Ah
0x1401add20  jnb     short loc_1401ADD88
0x1401add22  xor     edx, edx; Tag
0x1401add24  mov     rcx, rdi; P
0x1401add27  call    cs:__imp_ExFreePoolWithTag
0x1401add2e  nop     dword ptr [rax+rax+00h]
0x1401add33  mov     r13d, [rbp+57h+var_70]
0x1401add37  mov     ebx, [rbp+57h+var_7C]
  ... truncated ...
```
