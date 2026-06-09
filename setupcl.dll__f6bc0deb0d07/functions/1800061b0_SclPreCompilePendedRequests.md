# SclPreCompilePendedRequests

- ea: `0x1800061b0`
- end: `0x18000647b`
- name: `SclPreCompilePendedRequests`
- size: `715`
- prototype: `__int64 __fastcall(wchar_t *, __int64, _OWORD *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001010`
- `0x180001970`
- `0x180002010`
- `0x180004428`
- `0x180005efc`
- `0x180005fe0`
- `0x1800061b0`
- `0x1800065f8`
- `0x1800073c4`
- `0x18000ab50`
- `0x18000dae0`
- `0x18000deec`
- `0x180017995`
- `0x1800179c5`
- `0x1800179e0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000638d`
- `ntdll!RtlFreeHeap` at `0x1800063b3`
- `ntdll!RtlFreeHeap` at `0x1800063dc`
- `ntdll!RtlFreeHeap` at `0x18000640b`
- `ntdll!RtlFreeHeap` at `0x18000642c`
- `ntdll!RtlFreeHeap` at `0x18000644d`
- `ntdll!RtlFreeHeap` at `0x18000638d`
- `ntdll!RtlFreeHeap` at `0x1800063b3`
- `ntdll!RtlFreeHeap` at `0x1800063dc`
- `ntdll!RtlFreeHeap` at `0x18000640b`
- `ntdll!RtlFreeHeap` at `0x18000642c`
- `ntdll!RtlFreeHeap` at `0x18000644d`

## pseudocode

```c
__int64 __fastcall SclPreCompilePendedRequests(wchar_t *a1, __int64 a2, _OWORD *a3)
{
  PVOID v7; // rsi
  int inited; // ebx
  void *v9; // rcx
  __int64 v10; // rcx
  PVOID v11; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v12[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v13; // [rsp+58h] [rbp-A8h]
  const wchar_t *v14[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v15[8]; // [rsp+A0h] [rbp-60h] BYREF
  PVOID P; // [rsp+A8h] [rbp-58h]
  PVOID v17; // [rsp+B0h] [rbp-50h]
  PVOID v18; // [rsp+4C8h] [rbp+3C8h]
  int v19; // [rsp+520h] [rbp+420h] BYREF
  PVOID v20; // [rsp+528h] [rbp+428h]
  PVOID v21; // [rsp+530h] [rbp+430h]
  PVOID v22; // [rsp+948h] [rbp+848h]
  _BYTE v23[2400]; // [rsp+9A0h] [rbp+8A0h] BYREF

  if ( !a1 )
    return 3221225485LL;
  memset_0(v23, 0, 0x958u);
  memset_0(v14, 0, sizeof(v14));
  memset_0(&v19, 0, 0x478u);
  memset_0(v15, 0, 0x478u);
  v7 = 0;
  v13 = 0;
  memset(v12, 0, sizeof(v12));
  v11 = 0;
  SclInitFeedbackContext(a2, v23);
  inited = SclInitChanges(v12);
  if ( inited < 0 )
    goto LABEL_13;
  inited = SclAcquireRequiredPrivileges(&v11);
  if ( inited < 0 )
    goto LABEL_12;
  inited = SclOpenOS(v9, a1, v14);
  if ( inited < 0 )
    goto LABEL_12;
  inited = SclGetPendedRequest((__int64)v14, &v19);
  if ( inited < 0
    || (v19 |= 0x8000u, inited = SclpResolveRequest(v14, &v19, v15), inited < 0)
    || (inited = SclpExecuteRequestInternal((__int64)v15, (__int64)v14, (__int64)v23, a3, (union _LARGE_INTEGER)v12, 1),
        inited < 0)
    || (inited = SclCloseOS(v10, v14), inited < 0)
    || (LODWORD(v14[0]) = 2, v14[1] = a1, inited = SclStateStoreChanges(v23, v14, v12), inited < 0) )
  {
LABEL_12:
    v7 = v11;
LABEL_13:
    SclReleasePrivileges(v7);
    goto LABEL_14;
  }
  inited = SclReleasePrivileges(v11);
LABEL_14:
  SclFreeChanges(v12);
  if ( P )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    P = 0;
  }
  if ( v17 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
    v17 = 0;
  }
  if ( v18 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
  memset_0(v15, 0, 0x478u);
  if ( v20 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
  if ( v21 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
  if ( v22 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v22);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800061b0  mov     [rsp-8+arg_8], rbx
0x1800061b5  push    rbp
0x1800061b6  push    rsi
0x1800061b7  push    rdi
0x1800061b8  push    r14
0x1800061ba  push    r15
0x1800061bc  lea     rbp, [rsp-1210h]
0x1800061c4  mov     eax, 1310h
0x1800061c9  call    __chkstk_0
0x1800061ce  sub     rsp, rax
0x1800061d1  mov     rax, cs:__security_cookie
0x1800061d8  xor     rax, rsp
0x1800061db  mov     [rbp+1230h+var_30], rax
0x1800061e2  mov     r14, r8
0x1800061e5  mov     rbx, rdx
0x1800061e8  mov     rdi, rcx
0x1800061eb  test    rcx, rcx
0x1800061ee  jnz     short loc_1800061FA
0x1800061f0  mov     eax, 0C000000Dh
0x1800061f5  jmp     loc_180006455
0x1800061fa  xor     edx, edx; Val
0x1800061fc  lea     rcx, [rbp+1230h+var_990]; void *
0x180006203  mov     r8d, 958h; Size
0x180006209  call    memset_0
0x18000620e  xor     edx, edx; Val
0x180006210  lea     rcx, [rsp+1330h+var_12D0]; void *
0x180006215  lea     r8d, [rdx+40h]; Size
0x180006219  call    memset_0
0x18000621e  mov     r15d, 478h
0x180006224  lea     rcx, [rbp+1230h+var_E10]; void *
0x18000622b  mov     r8d, r15d; Size
0x18000622e  xor     edx, edx; Val
0x180006230  call    memset_0
0x180006235  mov     r8d, r15d; Size
0x180006238  lea     rcx, [rbp+1230h+var_1290]; void *
0x18000623c  xor     edx, edx; Val
0x18000623e  call    memset_0
0x180006243  xorps   xmm0, xmm0
0x180006246  lea     rdx, [rbp+1230h+var_990]
0x18000624d  xor     eax, eax
0x18000624f  xor     esi, esi
0x180006251  mov     rcx, rbx
0x180006254  mov     [rsp+1330h+var_12D8], rax
0x180006259  movups  [rsp+1330h+var_12F8], xmm0
0x18000625e  mov     [rsp+1330h+var_1300], rsi
0x180006263  movups  [rsp+1330h+var_12E8], xmm0
0x180006268  call    SclInitFeedbackContext
0x18000626d  lea     rcx, [rsp+1330h+var_12F8]
0x180006272  call    SclInitChanges
0x180006277  mov     ebx, eax
0x180006279  test    eax, eax
0x18000627b  js      loc_180006363
0x180006281  lea     rcx, [rsp+1330h+var_1300]
0x180006286  call    SclAcquireRequiredPrivileges
0x18000628b  mov     ebx, eax
0x18000628d  test    eax, eax
0x18000628f  js      loc_18000635E
0x180006295  lea     r8, [rsp+1330h+var_12D0]
0x18000629a  mov     rdx, rdi
0x18000629d  call    SclOpenOS
0x1800062a2  mov     ebx, eax
0x1800062a4  test    eax, eax
0x1800062a6  js      loc_18000635E
0x1800062ac  lea     rdx, [rbp+1230h+var_E10]
0x1800062b3  lea     rcx, [rsp+1330h+var_12D0]
0x1800062b8  call    SclGetPendedRequest
0x1800062bd  mov     ebx, eax
0x1800062bf  test    eax, eax
0x1800062c1  js      loc_18000635E
0x1800062c7  bts     [rbp+1230h+var_E10], 0Fh
0x1800062cf  lea     r8, [rbp+1230h+var_1290]
0x1800062d3  lea     rdx, [rbp+1230h+var_E10]
0x1800062da  lea     rcx, [rsp+1330h+var_12D0]
0x1800062df  call    SclpResolveRequest
0x1800062e4  mov     ebx, eax
0x1800062e6  test    eax, eax
0x1800062e8  js      short loc_18000635E
0x1800062ea  lea     rax, [rsp+1330h+var_12F8]
0x1800062ef  mov     [rsp+1330h+var_1308], 1
0x1800062f4  mov     r9, r14
0x1800062f7  mov     [rsp+1330h+var_1310], rax
0x1800062fc  lea     r8, [rbp+1230h+var_990]
0x180006303  lea     rdx, [rsp+1330h+var_12D0]
0x180006308  lea     rcx, [rbp+1230h+var_1290]
0x18000630c  call    SclpExecuteRequestInternal
0x180006311  mov     ebx, eax
0x180006313  test    eax, eax
0x180006315  js      short loc_18000635E
0x180006317  lea     rdx, [rsp+1330h+var_12D0]
0x18000631c  call    SclCloseOS
0x180006321  mov     ebx, eax
0x180006323  test    eax, eax
0x180006325  js      short loc_18000635E
0x180006327  lea     r8, [rsp+1330h+var_12F8]
0x18000632c  mov     [rsp+1330h+var_12D0], 2
0x180006334  lea     rdx, [rsp+1330h+var_12D0]
0x180006339  mov     [rsp+1330h+var_12C8], rdi
0x18000633e  lea     rcx, [rbp+1230h+var_990]
0x180006345  call    SclStateStoreChanges
0x18000634a  mov     ebx, eax
0x18000634c  test    eax, eax
0x18000634e  js      short loc_18000635E
0x180006350  mov     rcx, [rsp+1330h+var_1300]; P
0x180006355  call    SclReleasePrivileges
0x18000635a  mov     ebx, eax
0x18000635c  jmp     short loc_18000636B
0x18000635e  mov     rsi, [rsp+1330h+var_1300]
0x180006363  mov     rcx, rsi; P
0x180006366  call    SclReleasePrivileges
0x18000636b  lea     rcx, [rsp+1330h+var_12F8]
0x180006370  call    SclFreeChanges
0x180006375  mov     r8, [rbp+1230h+P]; P
0x180006379  test    r8, r8
0x18000637c  jz      short loc_18000639B
0x18000637e  mov     rcx, gs:60h
0x180006387  xor     edx, edx; Flags
0x180006389  mov     rcx, [rcx+30h]; HeapHandle
0x18000638d  call    cs:__imp_RtlFreeHeap
0x180006393  mov     [rbp+1230h+P], 0
0x18000639b  mov     r8, [rbp+1230h+var_1280]; P
0x18000639f  test    r8, r8
0x1800063a2  jz      short loc_1800063C1
0x1800063a4  mov     rcx, gs:60h
0x1800063ad  xor     edx, edx; Flags
0x1800063af  mov     rcx, [rcx+30h]; HeapHandle
0x1800063b3  call    cs:__imp_RtlFreeHeap
0x1800063b9  mov     [rbp+1230h+var_1280], 0
0x1800063c1  mov     r8, [rbp+1230h+var_E68]; P
0x1800063c8  test    r8, r8
0x1800063cb  jz      short loc_1800063E2
0x1800063cd  mov     rcx, gs:60h
0x1800063d6  xor     edx, edx; Flags
0x1800063d8  mov     rcx, [rcx+30h]; HeapHandle
0x1800063dc  call    cs:__imp_RtlFreeHeap
0x1800063e2  mov     r8, r15; Size
0x1800063e5  lea     rcx, [rbp+1230h+var_1290]; void *
0x1800063e9  xor     edx, edx; Val
0x1800063eb  call    memset_0
0x1800063f0  mov     r8, [rbp+1230h+var_E08]; P
0x1800063f7  test    r8, r8
0x1800063fa  jz      short loc_180006411
0x1800063fc  mov     rcx, gs:60h
0x180006405  xor     edx, edx; Flags
0x180006407  mov     rcx, [rcx+30h]; HeapHandle
0x18000640b  call    cs:__imp_RtlFreeHeap
0x180006411  mov     r8, [rbp+1230h+var_E00]; P
0x180006418  test    r8, r8
0x18000641b  jz      short loc_180006432
0x18000641d  mov     rcx, gs:60h
0x180006426  xor     edx, edx; Flags
0x180006428  mov     rcx, [rcx+30h]; HeapHandle
0x18000642c  call    cs:__imp_RtlFreeHeap
0x180006432  mov     r8, [rbp+1230h+var_9E8]; P
0x180006439  test    r8, r8
0x18000643c  jz      short loc_180006453
0x18000643e  mov     rcx, gs:60h
0x180006447  xor     edx, edx; Flags
0x180006449  mov     rcx, [rcx+30h]; HeapHandle
0x18000644d  call    cs:__imp_RtlFreeHeap
0x180006453  mov     eax, ebx
0x180006455  mov     rcx, [rbp+1230h+var_30]
0x18000645c  xor     rcx, rsp; StackCookie
0x18000645f  call    __security_check_cookie
0x180006464  mov     rbx, [rsp+1330h+arg_8]
0x18000646c  add     rsp, 1310h
0x180006473  pop     r15
0x180006475  pop     r14
0x180006477  pop     rdi
0x180006478  pop     rsi
0x180006479  pop     rbp
0x18000647a  retn
```
