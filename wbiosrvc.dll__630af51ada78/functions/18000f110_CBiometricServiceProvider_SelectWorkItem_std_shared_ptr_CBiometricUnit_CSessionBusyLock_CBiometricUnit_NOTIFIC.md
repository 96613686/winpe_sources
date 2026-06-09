# CBiometricServiceProvider::SelectWorkItem(std::shared_ptr<CBiometricUnit> &,CSessionBusyLock &,CBiometricUnit::_NOTIFICATION_TYPE)

- ea: `0x18000f110`
- end: `0x18000f51a`
- name: `?SelectWorkItem@CBiometricServiceProvider@@QEAA?AV?$shared_ptr@VCAsyncWorkItem@@@std@@AEAV?$shared_ptr@VCBiometricUnit@@@3@AEAVCSessionBusyLock@@W4_NOTIFICATION_TYPE@CBiometricUnit@@@Z`
- size: `1034`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180047580`

## callees

- `0x18000e470`
- `0x18000f110`
- `0x18000f520`
- `0x18001a960`
- `0x18005dd6c`
- `0x180068f60`
- `0x1800d2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f2e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f3ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f2e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f3ce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f29d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f2b3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f29d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f2b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f196`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f196`

## string_xrefs

- `0x18000f158`: `CBiometricServiceProvider::SelectWorkItem`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall CBiometricServiceProvider::SelectWorkItem(
        RTL_SRWLOCK *a1,
        _QWORD *a2,
        RTL_SRWLOCK **a3,
        __int64 a4,
        int a5)
{
  DWORD CurrentThreadId; // eax
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  int v12; // r10d
  PVOID *v13; // r9
  __int64 v14; // r8
  char *v15; // rax
  __int64 v16; // rcx
  const char *v17; // rdx
  char *v18; // r10
  char v19; // al
  char *v20; // rax
  RTL_SRWLOCK *v21; // rbp
  RTL_SRWLOCK *v22; // rbx
  RTL_SRWLOCK *v23; // r15
  _DWORD *Ptr; // rdx
  volatile signed __int32 *v25; // rbx
  std::_Ref_count_base *v26; // rsi
  signed __int32 v28; // eax
  signed __int32 v29; // ett
  unsigned int v30; // r10d
  unsigned int i; // r8d
  bool v32; // zf
  int v33; // r9d
  int v34; // r10d
  int v35; // r11d
  int v36; // [rsp+30h] [rbp-C8h] BYREF
  int v37; // [rsp+34h] [rbp-C4h]
  _QWORD *v38; // [rsp+38h] [rbp-C0h] BYREF
  std::_Ref_count_base *v39[2]; // [rsp+40h] [rbp-B8h]
  _QWORD v40[3]; // [rsp+58h] [rbp-A0h] BYREF
  char v41[48]; // [rsp+70h] [rbp-88h] BYREF

  v38 = a2;
  v37 = a5;
  v36 = 0;
  strcpy(v41, "CBiometricServiceProvider::SelectWorkItem");
  v40[0] = v41;
  v40[1] = &v36;
  CurrentThreadId = GetCurrentThreadId();
  v10 = CurrentThreadId;
  v11 = `WppTraceIndent'::`2'::idxCurrentThread;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v11 = 0;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    `WppTraceIndent'::`2'::ThreadTable[0] = CurrentThreadId;
    dword_180110614[0] = 0;
    goto LABEL_5;
  }
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
    || `WppTraceIndent'::`2'::ThreadTable[2 * `WppTraceIndent'::`2'::idxCurrentThread] != CurrentThreadId )
  {
    v30 = -1;
    for ( i = 0; ; ++i )
    {
      v32 = i == 32;
      if ( i >= 0x20 )
        break;
      v33 = `WppTraceIndent'::`2'::ThreadTable[2 * i];
      if ( v33 == CurrentThreadId )
      {
        v11 = i;
        `WppTraceIndent'::`2'::idxCurrentThread = i;
        v32 = i == 32;
        break;
      }
      if ( v30 == -1 && !v33 )
        v30 = i;
    }
    if ( v32 )
    {
      if ( v30 == -1 )
      {
        `WppTraceIndent'::`2'::idxCurrentThread = -2;
        goto LABEL_42;
      }
      v11 = v30;
      `WppTraceIndent'::`2'::idxCurrentThread = v30;
      *(_QWORD *)&`WppTraceIndent'::`2'::ThreadTable[2 * v30] = CurrentThreadId;
    }
  }
  if ( (v11 & 0x80000000) == 0LL )
  {
LABEL_5:
    v12 = ++`WppTraceIndent'::`2'::ThreadTable[2 * (int)v11 + 1];
    goto LABEL_6;
  }
LABEL_42:
  v12 = 0;
LABEL_6:
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u && v12 >= 1 )
  {
    while ( !(unsigned int)StringCbCatA((char *)v11, v10, "..") && v35 + 1 <= v34 )
      ;
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  v14 = 256;
  v15 = &`WppTraceIndent'::`2'::szIndentPrefix;
  while ( *v15 )
  {
    ++v15;
    if ( !--v14 )
      goto LABEL_16;
  }
  v16 = 2147483646;
  v17 = ">";
  v18 = (char *)`WppTraceIndent'::`2'::ThreadTable - v14;
  do
  {
    if ( !v16 )
      break;
    v19 = *v17;
    if ( !*v17 )
      break;
    ++v17;
    *v18++ = v19;
    --v16;
    --v14;
  }
  while ( v14 );
  v20 = v18 - 1;
  if ( v14 )
    v20 = v18;
  *v20 = 0;
LABEL_16:
  WPP_pszIndent = &`WppTraceIndent'::`2'::szIndentPrefix;
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 2) != 0 && *((_BYTE *)v13 + 25) >= 5u )
    WPP_SF_ss(
      (unsigned int)v13[2],
      14,
      (unsigned int)WPP_862778ae5d09346480cbb82d4a77c4d4_Traceguids,
      (_DWORD)v13,
      (__int64)v41);
  v36 = 1;
  v38 = v40;
  if ( !*a3 )
  {
    *(_OWORD *)a2 = 0;
    *a2 = 0;
    a2[1] = 0;
    goto LABEL_30;
  }
  v21 = a1 + 1;
  AcquireSRWLockShared(v21);
  v40[2] = v21;
  v22 = *a3;
  v23 = *a3 + 1;
  AcquireSRWLockShared(v23);
  *(_OWORD *)v39 = 0;
  Ptr = v22[9].Ptr;
  if ( Ptr )
  {
    v28 = Ptr[2];
    while ( v28 )
    {
      v29 = v28;
      v28 = _InterlockedCompareExchange(Ptr + 2, v28 + 1, v28);
      if ( v29 == v28 )
      {
        v26 = (std::_Ref_count_base *)v22[8].Ptr;
        v39[0] = v26;
        v25 = (volatile signed __int32 *)v22[9].Ptr;
        v39[1] = (std::_Ref_count_base *)v25;
        goto LABEL_21;
      }
    }
  }
  v25 = (volatile signed __int32 *)v39[1];
  v26 = v39[0];
LABEL_21:
  if ( v23 )
    ReleaseSRWLockShared(v23);
  if ( v26 )
  {
    (*(void (__fastcall **)(std::_Ref_count_base *, _QWORD *, RTL_SRWLOCK **, __int64, int))(*(_QWORD *)v26 + 8LL))(
      v26,
      a2,
      a3,
      a4,
      v37);
    if ( v25 && _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
      std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v25);
    }
    if ( !v21 )
      goto LABEL_30;
LABEL_39:
    ReleaseSRWLockShared(v21);
    goto LABEL_30;
  }
  *(_OWORD *)a2 = 0;
  *a2 = 0;
  a2[1] = 0;
  if ( v25 && _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
    std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v25);
  }
  if ( v21 )
    goto LABEL_39;
LABEL_30:
  WppTraceUnwinder__lambda_82ad66f9b4edff7ee3d2d62b9d25cd7d____::_WppTraceUnwinder__lambda_82ad66f9b4edff7ee3d2d62b9d25cd7d____(&v38);
  return a2;
}

```

## disassembly

```asm
0x18000f110  push    rbx
0x18000f112  push    rbp
0x18000f113  push    rsi
0x18000f114  push    rdi
0x18000f115  push    r12
0x18000f117  push    r13
0x18000f119  push    r14
0x18000f11b  push    r15
0x18000f11d  sub     rsp, 0B8h
0x18000f124  mov     rax, cs:__security_cookie
0x18000f12b  xor     rax, rsp
0x18000f12e  mov     [rsp+0F8h+var_58], rax
0x18000f136  mov     r13, r9
0x18000f139  mov     r12, r8
0x18000f13c  mov     rdi, rdx
0x18000f13f  mov     rbp, rcx
0x18000f142  mov     [rsp+0F8h+var_C0], rdx
0x18000f147  mov     eax, [rsp+0F8h+arg_20]
0x18000f14e  mov     [rsp+0F8h+var_C4], eax
0x18000f152  xor     ebx, ebx
0x18000f154  mov     [rsp+0F8h+var_C8], ebx
0x18000f158  movups  xmm0, xmmword ptr cs:aCbiometricserv_10; "CBiometricServiceProvider::SelectWorkIt"...
0x18000f15f  movups  xmmword ptr [rsp+0F8h+var_88], xmm0
0x18000f164  movups  xmm1, xmmword ptr cs:aCbiometricserv_10+10h; "eProvider::SelectWorkItem"
0x18000f16b  movups  xmmword ptr [rsp+0F8h+var_88+10h], xmm1
0x18000f173  movups  xmm0, xmmword ptr cs:aCbiometricserv_10+1Ah; ":SelectWorkItem"
0x18000f17a  movups  xmmword ptr [rsp+0F8h+var_88+1Ah], xmm0
0x18000f182  lea     rax, [rsp+0F8h+var_88]
0x18000f187  mov     [rsp+0F8h+var_A0], rax
0x18000f18c  lea     rax, [rsp+0F8h+var_C8]
0x18000f191  mov     [rsp+0F8h+var_98], rax
0x18000f196  call    cs:__imp_GetCurrentThreadId
0x18000f19c  mov     edx, eax; unsigned __int64
0x18000f19e  lea     r11, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x18000f1a5  mov     r14d, 0FFFFFFFFh
0x18000f1ab  movsxd  rcx, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; char *
0x18000f1b2  cmp     ecx, r14d
0x18000f1b5  jz      loc_18000F3D9
0x18000f1bb  cmp     ecx, 0FFFFFFFEh
0x18000f1be  jz      loc_18000F437
0x18000f1c4  cmp     [r11+rcx*8], eax
0x18000f1c8  jnz     loc_18000F437
0x18000f1ce  test    ecx, ecx
0x18000f1d0  js      loc_18000F3FC
0x18000f1d6  movsxd  rax, ecx
0x18000f1d9  inc     dword ptr [r11+rax*8+4]
0x18000f1de  mov     r10d, [r11+rax*8+4]
0x18000f1e3  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, bl; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x18000f1e9  mov     r9, cs:WPP_GLOBAL_Control
0x18000f1f0  test    byte ptr [r9+1Ch], 2
0x18000f1f5  jnz     loc_18000F4DC
0x18000f1fb  mov     r8d, 100h
0x18000f201  lea     r11, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x18000f208  mov     rax, r11
0x18000f20b  cmp     [rax], bl
0x18000f20d  jnz     loc_18000F4CA
0x18000f213  mov     ecx, 7FFFFFFEh
0x18000f218  lea     rdx, asc_1800DBCD0; ">"
0x18000f21f  lea     r10, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x18000f226  sub     r10, r8
0x18000f229  test    r8, r8
0x18000f22c  jz      short loc_18000F24E
0x18000f22e  xchg    ax, ax
0x18000f230  test    rcx, rcx
0x18000f233  jz      short loc_18000F24E
0x18000f235  movzx   eax, byte ptr [rdx]
0x18000f238  test    al, al
0x18000f23a  jz      short loc_18000F24E
0x18000f23c  inc     rdx
0x18000f23f  mov     [r10], al
0x18000f242  inc     r10
0x18000f245  dec     rcx
0x18000f248  sub     r8, 1
0x18000f24c  jnz     short loc_18000F230
0x18000f24e  lea     rax, [r10-1]
0x18000f252  test    r8, r8
0x18000f255  cmovnz  rax, r10
0x18000f259  mov     [rax], bl
0x18000f25b  mov     cs:?WPP_pszIndent@@3PEADEA, r11; char * WPP_pszIndent
0x18000f262  lea     rax, WPP_GLOBAL_Control
0x18000f269  cmp     r9, rax
0x18000f26c  jz      short loc_18000F279
0x18000f26e  test    byte ptr [r9+1Ch], 2
0x18000f273  jnz     loc_18000F49B
0x18000f279  mov     [rsp+0F8h+var_C8], 1
0x18000f281  lea     rax, [rsp+0F8h+var_A0]
0x18000f286  mov     [rsp+0F8h+var_C0], rax
0x18000f28b  cmp     qword ptr [r12], 0
0x18000f290  jz      loc_18000F332
0x18000f296  add     rbp, 8
0x18000f29a  mov     rcx, rbp; SRWLock
0x18000f29d  call    cs:__imp_AcquireSRWLockShared
0x18000f2a3  mov     [rsp+0F8h+var_90], rbp
0x18000f2a8  mov     rbx, [r12]
0x18000f2ac  lea     r15, [rbx+8]
0x18000f2b0  mov     rcx, r15; SRWLock
0x18000f2b3  call    cs:__imp_AcquireSRWLockShared
0x18000f2b9  xorps   xmm0, xmm0
0x18000f2bc  movdqu  xmmword ptr [rsp+0F8h+var_B8], xmm0
0x18000f2c2  mov     rdx, [rbx+48h]
0x18000f2c6  test    rdx, rdx
0x18000f2c9  jnz     loc_18000F370
0x18000f2cf  mov     rbx, [rsp+0F8h+var_B8+8]
0x18000f2d4  mov     rsi, [rsp+0F8h+var_B8]
0x18000f2d9  test    r15, r15
0x18000f2dc  jz      short loc_18000F2E8
0x18000f2de  mov     rcx, r15; SRWLock
0x18000f2e1  call    cs:__imp_ReleaseSRWLockShared
0x18000f2e7  nop
0x18000f2e8  test    rsi, rsi
0x18000f2eb  jz      loc_18000F39C
0x18000f2f1  mov     rax, [rsi]
0x18000f2f4  mov     ecx, [rsp+0F8h+var_C4]
0x18000f2f8  mov     dword ptr [rsp+0F8h+var_D8], ecx
0x18000f2fc  mov     r9, r13
0x18000f2ff  mov     r8, r12
0x18000f302  mov     rdx, rdi
0x18000f305  mov     rcx, rsi
0x18000f308  mov     rax, [rax+8]
0x18000f30c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f311  nop
0x18000f312  test    rbx, rbx
0x18000f315  jz      short loc_18000F327
0x18000f317  lock xadd [rbx+8], r14d
0x18000f31d  cmp     r14d, 1
0x18000f321  jz      loc_18000F404
0x18000f327  test    rbp, rbp
0x18000f32a  jnz     loc_18000F3CB
0x18000f330  jmp     short loc_18000F33F
0x18000f332  xorps   xmm0, xmm0
0x18000f335  movups  xmmword ptr [rdi], xmm0
0x18000f338  mov     [rdi], rbx
0x18000f33b  mov     [rdi+8], rbx
0x18000f33f  lea     rcx, [rsp+0F8h+var_C0]
0x18000f344  call    WppTraceUnwinder__lambda_82ad66f9b4edff7ee3d2d62b9d25cd7d_______WppTraceUnwinder__lambda_82ad66f9b4edff7ee3d2d62b9d25cd7d____
0x18000f349  mov     rax, rdi
0x18000f34c  mov     rcx, [rsp+0F8h+var_58]
0x18000f354  xor     rcx, rsp; StackCookie
0x18000f357  call    __security_check_cookie
0x18000f35c  add     rsp, 0B8h
0x18000f363  pop     r15
0x18000f365  pop     r14
0x18000f367  pop     r13
0x18000f369  pop     r12
0x18000f36b  pop     rdi
0x18000f36c  pop     rsi
0x18000f36d  pop     rbp
0x18000f36e  pop     rbx
0x18000f36f  retn
0x18000f370  mov     eax, [rdx+8]
0x18000f373  test    eax, eax
0x18000f375  jz      loc_18000F2CF
0x18000f37b  lea     ecx, [rax+1]
0x18000f37e  lock cmpxchg [rdx+8], ecx
0x18000f383  jnz     short loc_18000F373
0x18000f385  mov     rsi, [rbx+40h]
0x18000f389  mov     [rsp+0F8h+var_B8], rsi
0x18000f38e  mov     rbx, [rbx+48h]
0x18000f392  mov     [rsp+0F8h+var_B8+8], rbx
0x18000f397  jmp     loc_18000F2D9
0x18000f39c  xorps   xmm0, xmm0
0x18000f39f  movups  xmmword ptr [rdi], xmm0
0x18000f3a2  mov     qword ptr [rdi], 0
0x18000f3a9  mov     qword ptr [rdi+8], 0
0x18000f3b1  test    rbx, rbx
0x18000f3b4  jz      short loc_18000F3C2
0x18000f3b6  lock xadd [rbx+8], r14d
0x18000f3bc  cmp     r14d, 1
0x18000f3c0  jz      short loc_18000F41F
0x18000f3c2  test    rbp, rbp
0x18000f3c5  jz      loc_18000F33F
0x18000f3cb  mov     rcx, rbp; SRWLock
0x18000f3ce  call    cs:__imp_ReleaseSRWLockShared
0x18000f3d4  jmp     loc_18000F33F
0x18000f3d9  mov     ecx, ebx
0x18000f3db  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ebx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000f3e1  mov     cs:?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A, edx; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x18000f3e7  mov     cs:dword_180110614, ebx
0x18000f3ed  jmp     loc_18000F1D6
0x18000f3f2  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, 0FFFFFFFEh; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000f3fc  mov     r10d, ebx
0x18000f3ff  jmp     loc_18000F1E3
0x18000f404  mov     rax, [rbx]
0x18000f407  mov     rcx, rbx
0x18000f40a  mov     rax, [rax]
0x18000f40d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f412  mov     rcx, rbx; this
0x18000f415  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18000f41a  jmp     loc_18000F327
0x18000f41f  mov     rax, [rbx]
0x18000f422  mov     rcx, rbx
0x18000f425  mov     rax, [rax]
0x18000f428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f42d  mov     rcx, rbx; this
0x18000f430  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18000f435  jmp     short loc_18000F3C2
0x18000f437  mov     r10d, r14d
0x18000f43a  mov     r8d, ebx
0x18000f43d  nop     dword ptr [rax]
0x18000f440  cmp     r8d, 20h ; ' '
0x18000f444  jnb     short loc_18000F469
0x18000f446  movsxd  rax, r8d
0x18000f449  mov     r9d, [r11+rax*8]
0x18000f44d  cmp     r9d, edx
0x18000f450  jz      short loc_18000F45C
0x18000f452  cmp     r10d, r14d
0x18000f455  jz      short loc_18000F492
0x18000f457  inc     r8d
0x18000f45a  jmp     short loc_18000F440
0x18000f45c  mov     ecx, r8d
0x18000f45f  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ecx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000f465  cmp     r8d, 20h ; ' '
0x18000f469  jnz     loc_18000F1CE
0x18000f46f  cmp     r10d, r14d
0x18000f472  jz      loc_18000F3F2
0x18000f478  mov     ecx, r10d
0x18000f47b  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ecx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000f481  movsxd  rax, r10d
0x18000f484  mov     [r11+rax*8], edx
0x18000f488  mov     [r11+rax*8+4], ebx
0x18000f48d  jmp     loc_18000F1CE
0x18000f492  test    r9d, r9d
0x18000f495  cmovz   r10d, r8d
0x18000f499  jmp     short loc_18000F457
0x18000f49b  cmp     byte ptr [r9+19h], 5
0x18000f4a0  jb      loc_18000F279
0x18000f4a6  mov     edx, 0Eh
0x18000f4ab  lea     rax, [rsp+0F8h+var_88]
0x18000f4b0  mov     [rsp+0F8h+var_D8], rax
0x18000f4b5  lea     r8, WPP_862778ae5d09346480cbb82d4a77c4d4_Traceguids
0x18000f4bc  mov     rcx, [r9+10h]
0x18000f4c0  call    WPP_SF_ss
0x18000f4c5  jmp     loc_18000F279
0x18000f4ca  inc     rax
0x18000f4cd  sub     r8, 1
0x18000f4d1  jnz     loc_18000F20B
0x18000f4d7  jmp     loc_18000F25B
0x18000f4dc  cmp     byte ptr [r9+19h], 5
0x18000f4e1  jb      loc_18000F1FB
0x18000f4e7  mov     r11d, 1
0x18000f4ed  cmp     r10d, r11d
0x18000f4f0  jl      loc_18000F1FB
0x18000f4f6  lea     r8, asc_1800E1998; ".."
0x18000f4fd  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x18000f502  test    eax, eax
0x18000f504  jnz     short loc_18000F50E
0x18000f506  inc     r11d
0x18000f509  cmp     r11d, r10d
0x18000f50c  jle     short loc_18000F4F6
0x18000f50e  mov     r9, cs:WPP_GLOBAL_Control
0x18000f515  jmp     loc_18000F1FB
```
