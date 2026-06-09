# FlRdmaNsiEnumerateNdkItemsCommon

- ea: `0x1401af458`
- end: `0x1401af9b6`
- name: `FlRdmaNsiEnumerateNdkItemsCommon`
- size: `1374`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1401af2b0`
- `0x1401af440`

## callees

- `0x1400538a0`
- `0x14007a280`
- `0x14007b0e8`
- `0x140103520`
- `0x1401af458`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401af52c`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401af697`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401af52c`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401af697`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401af5f8`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401af89c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401af8c9`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401af90b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401af93a`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401af5f8`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401af89c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401af8c9`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401af90b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401af93a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401af8e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401af974`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401af8e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401af974`

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
0x1401af458  mov     [rsp-8+arg_8], dl
0x1401af45c  mov     [rsp-8+arg_0], rcx
0x1401af461  push    rbp
0x1401af462  push    rbx
0x1401af463  push    rsi
0x1401af464  push    rdi
0x1401af465  push    r12
0x1401af467  push    r13
0x1401af469  push    r14
0x1401af46b  push    r15
0x1401af46d  lea     rbp, [rsp-1Fh]
0x1401af472  sub     rsp, 88h
0x1401af479  mov     r8d, [rcx+20h]
0x1401af47d  mov     r12, rcx
0x1401af480  mov     [rbp+57h+var_78], 0
0x1401af487  mov     [rbp+57h+arg_10], 0
0x1401af48b  mov     [rbp+57h+arg_18], 0
0x1401af492  test    r8d, r8d
0x1401af495  jz      loc_1401AF99C
0x1401af49b  sub     r8d, 1
0x1401af49f  jz      short loc_1401AF4B5
0x1401af4a1  cmp     r8d, 1
0x1401af4a5  jz      loc_1401AF99C
0x1401af4ab  mov     eax, 0C000000Dh
0x1401af4b0  jmp     loc_1401AF9A1
0x1401af4b5  mov     eax, [rcx+58h]
0x1401af4b8  mov     [rbp+57h+var_80], eax
0x1401af4bb  mov     al, dl
0x1401af4bd  neg     al
0x1401af4bf  mov     al, dl
0x1401af4c1  sbb     ecx, ecx
0x1401af4c3  and     ecx, 1Ch
0x1401af4c6  add     ecx, 24h ; '$'
0x1401af4c9  neg     al
0x1401af4cb  mov     [rbp+57h+var_60], ecx
0x1401af4ce  mov     eax, 0FFFFFFEFh
0x1401af4d3  sbb     ebx, ebx
0x1401af4d5  xor     edx, edx
0x1401af4d7  div     ecx
0x1401af4d9  mov     rcx, [r12]
0x1401af4dd  add     ebx, 0FC040204h
0x1401af4e3  mov     [rbp+57h+var_5C], eax
0x1401af4e6  mov     [rbp+57h+var_7C], ebx
0x1401af4e9  mov     r14, [rcx+28h]
0x1401af4ed  add     r14, 1B8h
0x1401af4f4  xor     r13d, r13d
0x1401af4f7  mov     [rbp+57h+var_70], r13d
0x1401af4fb  mov     [rbp+57h+var_74], r13d
0x1401af4ff  lea     rdi, [r14+18h]
0x1401af503  xor     r15d, r15d
0x1401af506  lea     rdx, [rbp+57h+arg_10]
0x1401af50a  mov     rcx, r14; SpinLock
0x1401af50d  call    RtlAcquireReadLock
0x1401af512  mov     rsi, [r14+20h]
0x1401af516  cmp     rsi, rdi
0x1401af519  jz      loc_1401AF616
0x1401af51f  lea     rdi, [rsi-10h]
0x1401af523  mov     edx, 1; Count
0x1401af528  mov     rcx, [rdi+50h]; RunRefCacheAware
0x1401af52c  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1401af533  nop     dword ptr [rax+rax+00h]
0x1401af538  test    al, al
0x1401af53a  jz      loc_1401AF609
0x1401af540  mov     dl, [rbp+57h+arg_10]
0x1401af543  mov     rcx, r14
0x1401af546  call    RtlReleaseReadLock
0x1401af54b  lea     rax, [rbp+57h+var_78]
0x1401af54f  mov     byte ptr [rbp+57h+arg_18+1], 0
0x1401af556  mov     [rsp+0C0h+var_90], rax
0x1401af55b  mov     r9d, ebx
0x1401af55e  lea     rax, [rbp+57h+arg_18]
0x1401af562  mov     [rsp+0C0h+var_98], 4
0x1401af56a  xor     r8d, r8d
0x1401af56d  mov     [rsp+0C0h+var_A0], rax
0x1401af572  xor     edx, edx
0x1401af574  mov     rcx, rdi
0x1401af577  call    FlpNdisRequestUnderReference
0x1401af57c  mov     ebx, eax
0x1401af57e  cmp     eax, 0C0000023h
0x1401af583  jnz     short loc_1401AF5D3
0x1401af585  mov     eax, [rbp+57h+var_78]
0x1401af588  mov     r8d, 1
0x1401af58e  cmp     eax, 10h
0x1401af591  jb      loc_1401AF919
0x1401af597  cmp     byte ptr [rbp+57h+arg_18+1], r8b
0x1401af59e  jnz     loc_1401AF919
0x1401af5a4  add     eax, 0FFFFFFF0h
0x1401af5a7  xor     edx, edx
0x1401af5a9  div     [rbp+57h+var_60]
0x1401af5ac  add     eax, 14h
0x1401af5af  cmp     eax, [rbp+57h+var_5C]
0x1401af5b2  cmova   eax, [rbp+57h+var_5C]
0x1401af5b6  cmp     eax, r13d
0x1401af5b9  cmova   r13d, eax
0x1401af5bd  lea     ecx, [rax+r15]
0x1401af5c1  mov     [rbp+57h+var_70], r13d
0x1401af5c5  cmp     ecx, r15d
0x1401af5c8  jb      loc_1401AF8FF
0x1401af5ce  mov     r15d, ecx
0x1401af5d1  jmp     short loc_1401AF5DF
0x1401af5d3  cmp     ebx, 0C00000BBh
0x1401af5d9  jnz     loc_1401AF920
0x1401af5df  lea     rdx, [rbp+57h+arg_10]
0x1401af5e3  mov     rcx, r14; SpinLock
0x1401af5e6  call    RtlAcquireReadLock
0x1401af5eb  mov     rcx, [rdi+50h]; RunRef
0x1401af5ef  mov     edx, 1; Count
0x1401af5f4  mov     rsi, [rsi+8]
0x1401af5f8  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1401af5ff  nop     dword ptr [rax+rax+00h]
0x1401af604  mov     ebx, [rbp+57h+var_7C]
0x1401af607  jmp     short loc_1401AF60D
0x1401af609  mov     rsi, [rsi+8]
0x1401af60d  lea     rdi, [r14+18h]
0x1401af611  jmp     loc_1401AF516
0x1401af616  mov     dl, [rbp+57h+arg_10]
0x1401af619  mov     rcx, r14
0x1401af61c  call    RtlReleaseReadLock
0x1401af621  mov     ebx, [rbp+57h+var_80]
0x1401af624  cmp     ebx, r15d
0x1401af627  jb      loc_1401AF989
0x1401af62d  cmp     [rbp+57h+arg_8], 0
0x1401af631  jz      short loc_1401AF63B
0x1401af633  mov     eax, r13d
0x1401af636  shl     eax, 6
0x1401af639  jmp     short loc_1401AF649
0x1401af63b  lea     eax, ds:0[r13*8]
0x1401af643  add     eax, r13d
0x1401af646  shl     eax, 2
0x1401af649  add     eax, 10h
0x1401af64c  mov     ecx, eax
0x1401af64e  mov     [rbp+57h+var_58], eax
0x1401af651  call    FlpAllocateMemory
0x1401af656  mov     rdi, rax
0x1401af659  test    rax, rax
0x1401af65c  jz      loc_1401AF982
0x1401af662  xor     ebx, ebx
0x1401af664  lea     rdx, [rbp+57h+arg_10]
0x1401af668  xor     esi, esi
0x1401af66a  xor     r15b, r15b
0x1401af66d  mov     rcx, r14; SpinLock
0x1401af670  call    RtlAcquireReadLock
0x1401af675  mov     rax, [r14+20h]
0x1401af679  mov     [rbp+57h+var_68], rax
0x1401af67d  lea     rcx, [r14+18h]
0x1401af681  cmp     rax, rcx
0x1401af684  jz      loc_1401AF94F
0x1401af68a  lea     r13, [rax-10h]
0x1401af68e  mov     edx, 1; Count
0x1401af693  mov     rcx, [r13+50h]; RunRefCacheAware
0x1401af697  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1401af69e  nop     dword ptr [rax+rax+00h]
0x1401af6a3  test    al, al
0x1401af6a5  jz      loc_1401AF8B1
0x1401af6ab  mov     dl, [rbp+57h+arg_10]
0x1401af6ae  mov     rcx, r14
0x1401af6b1  call    RtlReleaseReadLock
0x1401af6b6  mov     eax, [rbp+57h+var_58]
0x1401af6b9  xor     r8d, r8d
0x1401af6bc  mov     r9d, [rbp+57h+var_7C]
0x1401af6c0  xor     edx, edx
0x1401af6c2  mov     [rsp+0C0h+var_90], 0
0x1401af6cb  mov     rcx, r13
0x1401af6ce  mov     [rsp+0C0h+var_98], eax
0x1401af6d2  mov     [rsp+0C0h+var_A0], rdi
0x1401af6d7  call    FlpNdisRequestUnderReference
0x1401af6dc  mov     ebx, eax
0x1401af6de  cmp     eax, 0C0000023h
0x1401af6e3  jz      loc_1401AF8BE
0x1401af6e9  xor     r10b, r10b
0x1401af6ec  test    eax, eax
0x1401af6ee  js      loc_1401AF86B
0x1401af6f4  mov     r15, [r12+10h]
0x1401af6f9  mov     rdx, [r12+48h]
0x1401af6fe  mov     [rbp+57h+var_50], r15
0x1401af702  cmp     [rbp+57h+arg_8], r10b
0x1401af706  jz      loc_1401AF7C1
0x1401af70c  mov     r11d, [rbp+57h+var_80]
0x1401af710  xor     r9d, r9d
0x1401af713  jmp     loc_1401AF7A6
0x1401af718  cmp     r9d, [rdi+8]
0x1401af71c  jnb     loc_1401AF7B3
0x1401af722  mov     eax, [r13+498h]
0x1401af729  mov     r8d, esi
0x1401af72c  imul    rcx, r8, 3Ch ; '<'
0x1401af730  mov     r10d, r9d
0x1401af733  shl     r10, 6
0x1401af737  mov     [rcx+r15], eax
0x1401af73b  movups  xmm0, xmmword ptr [r10+rdi+10h]
0x1401af741  movups  xmmword ptr [rcx+r15+4], xmm0
0x1401af747  movups  xmm1, xmmword ptr [r10+rdi+1Ch]
0x1401af74d  movups  xmmword ptr [rcx+r15+10h], xmm1
0x1401af753  movups  xmm0, xmmword ptr [r10+rdi+2Ch]
0x1401af759  movups  xmmword ptr [rcx+r15+20h], xmm0
0x1401af75f  movups  xmm1, xmmword ptr [r10+rdi+38h]
0x1401af765  movups  xmmword ptr [rcx+r15+2Ch], xmm1
0x1401af76b  mov     ecx, 1
0x1401af770  test    rdx, rdx
0x1401af773  jz      short loc_1401AF7A1
0x1401af775  cmp     byte ptr [rdi+0Ch], 0
0x1401af779  jnz     short loc_1401AF781
0x1401af77b  mov     byte ptr [rdx+rsi*8], 0
0x1401af77f  jmp     short loc_1401AF789
0x1401af781  test    cl, r9b
0x1401af784  jnz     short loc_1401AF79D
0x1401af786  mov     [rdx+rsi*8], cl
0x1401af789  mov     al, [r10+rdi+48h]
0x1401af78e  mov     [rdx+rsi*8+1], al
0x1401af792  mov     eax, [r10+rdi+4Ch]
0x1401af797  mov     [rdx+rsi*8+4], eax
0x1401af79b  jmp     short loc_1401AF7A1
0x1401af79d  mov     byte ptr [rdx+rsi*8], 0
0x1401af7a1  add     esi, ecx
0x1401af7a3  add     r9d, ecx
0x1401af7a6  cmp     esi, r11d
0x1401af7a9  jb      loc_1401AF718
0x1401af7af  cmp     r9d, [rdi+8]
0x1401af7b3  setb    r10b
0x1401af7b7  mov     eax, 1
0x1401af7bc  jmp     loc_1401AF866
0x1401af7c1  mov     r15d, [rbp+57h+var_80]
0x1401af7c5  xor     r11d, r11d
0x1401af7c8  cmp     esi, r15d
0x1401af7cb  jnb     loc_1401AF855
0x1401af7d1  mov     r12, [rbp+57h+var_50]
0x1401af7d5  cmp     r11d, [rdi+8]
0x1401af7d9  jnb     short loc_1401AF851
0x1401af7db  mov     eax, [r13+498h]
0x1401af7e2  lea     r9, [r11+r11*8]
0x1401af7e6  mov     ecx, esi
0x1401af7e8  shl     rcx, 5
0x1401af7ec  mov     [rcx+r12], eax
0x1401af7f0  movups  xmm0, xmmword ptr [rdi+r9*4+10h]
0x1401af7f6  movups  xmmword ptr [rcx+r12+4], xmm0
0x1401af7fc  movups  xmm1, xmmword ptr [rdi+r9*4+1Ch]
0x1401af802  movups  xmmword ptr [rcx+r12+10h], xmm1
0x1401af808  mov     ecx, 1
0x1401af80d  test    rdx, rdx
0x1401af810  jz      short loc_1401AF847
0x1401af812  cmp     [rdi+0Ch], r10b
0x1401af816  jnz     short loc_1401AF81E
0x1401af818  mov     [rdx+rsi*8], r10b
0x1401af81c  jmp     short loc_1401AF826
0x1401af81e  test    cl, r11b
0x1401af821  jnz     short loc_1401AF843
0x1401af823  mov     [rdx+rsi*8], cl
0x1401af826  mov     al, [rdi+r9*4+2Ch]
0x1401af82b  mov     [rdx+rsi*8+1], al
0x1401af82f  mov     eax, [rdi+r9*4+30h]
0x1401af834  mov     [rdx+rsi*8+4], eax
0x1401af838  mov     al, [rdi+r9*4+2Dh]
0x1401af83d  mov     [rdx+rsi*8+2], al
0x1401af841  jmp     short loc_1401AF847
0x1401af843  mov     [rdx+rsi*8], r10b
0x1401af847  add     esi, ecx
0x1401af849  add     r11d, ecx
0x1401af84c  cmp     esi, r15d
0x1401af84f  jb      short loc_1401AF7D5
0x1401af851  mov     r12, [rbp+57h+arg_0]
0x1401af855  cmp     r11d, [rdi+8]
0x1401af859  mov     eax, 1
0x1401af85e  movzx   r10d, r10b
0x1401af862  cmovb   r10d, eax
0x1401af866  mov     r15b, al
0x1401af869  jmp     short loc_1401AF876
0x1401af86b  cmp     eax, 0C00000BBh
0x1401af870  jnz     loc_1401AF931
0x1401af876  test    r10b, r10b
0x1401af879  jnz     short loc_1401AF8BE
0x1401af87b  lea     rdx, [rbp+57h+arg_10]
0x1401af87f  mov     rcx, r14; SpinLock
0x1401af882  call    RtlAcquireReadLock
0x1401af887  mov     rax, [rbp+57h+var_68]
0x1401af88b  mov     edx, 1; Count
0x1401af890  mov     rcx, [r13+50h]; RunRef
0x1401af894  mov     rax, [rax+8]
0x1401af898  mov     [rbp+57h+var_68], rax
0x1401af89c  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1401af8a3  nop     dword ptr [rax+rax+00h]
0x1401af8a8  mov     rax, [rbp+57h+var_68]
0x1401af8ac  jmp     loc_1401AF67D
0x1401af8b1  mov     rax, [rbp+57h+var_68]
0x1401af8b5  mov     rax, [rax+8]
0x1401af8b9  jmp     loc_1401AF679
0x1401af8be  mov     rcx, [r13+50h]; RunRef
0x1401af8c2  mov     esi, 1
0x1401af8c7  mov     edx, esi; Count
0x1401af8c9  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1401af8d0  nop     dword ptr [rax+rax+00h]
0x1401af8d5  mov     ebx, [rbp+57h+var_74]
0x1401af8d8  add     ebx, esi
0x1401af8da  mov     [rbp+57h+var_74], ebx
0x1401af8dd  cmp     ebx, 0Ah
0x1401af8e0  jnb     short loc_1401AF948
0x1401af8e2  xor     edx, edx; Tag
0x1401af8e4  mov     rcx, rdi; P
0x1401af8e7  call    cs:__imp_ExFreePoolWithTag
0x1401af8ee  nop     dword ptr [rax+rax+00h]
0x1401af8f3  mov     r13d, [rbp+57h+var_70]
0x1401af8f7  mov     ebx, [rbp+57h+var_7C]
  ... truncated ...
```
