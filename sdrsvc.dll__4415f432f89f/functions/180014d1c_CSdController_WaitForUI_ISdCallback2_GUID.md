# CSdController::_WaitForUI(ISdCallback2 * *,_GUID *)

- ea: `0x180014d1c`
- end: `0x180014f68`
- name: `?_WaitForUI@CSdController@@AEAAJPEAPEAUISdCallback2@@PEAU_GUID@@@Z`
- size: `588`
- prototype: `__int64 __fastcall(CSdController *__hidden this, struct ISdCallback2 **, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18000f370`

## callees

- `0x180011cb8`
- `0x1800138bc`
- `0x180013c48`
- `0x180014d1c`
- `0x18001586c`
- `0x180015974`
- `0x18001a654`
- `0x18001bfcc`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ec6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ec6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014d8f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014d8f`

## string_xrefs

- `0x180014d95`: `SeAssignPrimaryTokenPrivilege`
- `0x180014db6`: `SeIncreaseQuotaPrivilege`
- `0x180014dd2`: `SeTcbPrivilege`

## pseudocode

```c
__int64 __fastcall CSdController::_WaitForUI(CSdController *this, struct ISdCallback2 **a2, struct _GUID *a3)
{
  struct AsyncISdCallback2 *v6; // rbx
  struct ISynchronize *v7; // rdi
  __int64 v8; // rcx
  struct _GUID *v9; // rax
  __int16 v10; // ax
  CSdController *v11; // rcx
  struct ISdCallback2 *v12; // rdx
  int v13; // eax
  bool v14; // sf
  __int64 v15; // rcx
  unsigned int v16; // esi
  __int64 v18; // rcx
  struct _GUID v19; // [rsp+20h] [rbp-50h] BYREF
  int v20; // [rsp+30h] [rbp-40h] BYREF
  __int16 v21; // [rsp+34h] [rbp-3Ch]
  __int16 v22; // [rsp+36h] [rbp-3Ah]
  struct AsyncISdCallback2 *v23; // [rsp+B0h] [rbp+40h] BYREF
  struct ISynchronize *v24; // [rsp+B8h] [rbp+48h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+C0h] [rbp+50h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v20, "CSdController::_WaitForUI", 952, 1);
  v6 = 0;
  v7 = 0;
  v23 = 0;
  v24 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
  {
    v8 = 16;
    v9 = a3;
    do
    {
      LOBYTE(v9->Data1) = 0;
      v9 = (struct _GUID *)((char *)v9 + 1);
      --v8;
    }
    while ( v8 );
  }
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v20 = AssertPrivilege(L"SeAssignPrimaryTokenPrivilege");
  v10 = 964;
  if ( v20 < 0 )
    goto LABEL_7;
  v21 = 964;
  v20 = AssertPrivilege(L"SeIncreaseQuotaPrivilege");
  v10 = 965;
  if ( v20 < 0 )
    goto LABEL_7;
  v21 = 965;
  v20 = AssertPrivilege(L"SeTcbPrivilege");
  v10 = 966;
  if ( v20 < 0 )
    goto LABEL_7;
  v12 = (struct ISdCallback2 *)*((_QWORD *)this + 18);
  v21 = 966;
  if ( !v12 )
    goto LABEL_14;
  v20 = CSdController::_GetAsyncCallObject(v11, v12, &v23, &v24);
  if ( !(unsigned int)IsRPCError(v20) )
  {
    v19 = (struct _GUID)*((_OWORD *)this + 7);
    v13 = CSdController::_ReleaseUI(this, &v19);
    v6 = v23;
    v14 = v13 < 0;
    v7 = v24;
    v20 = v13;
    v10 = 978;
    if ( v14 )
      goto LABEL_7;
    v21 = 978;
LABEL_14:
    v20 = CSdController::_SleepConditionVariable(
            (PCONDITION_VARIABLE)this + 6,
            (PCRITICAL_SECTION)((char *)this + 64),
            0xFFFFFFFF);
    v10 = 994;
    if ( v20 >= 0 )
    {
      v21 = 994;
      if ( a2 )
      {
        *a2 = (struct ISdCallback2 *)*((_QWORD *)this + 18);
        v15 = *((_QWORD *)this + 18);
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
        v20 = 0;
        v21 = 998;
      }
      if ( a3 )
        *a3 = *((struct _GUID *)this + 7);
      goto LABEL_21;
    }
LABEL_7:
    v22 = v10;
    goto LABEL_21;
  }
  if ( a2 )
  {
    *a2 = (struct ISdCallback2 *)*((_QWORD *)this + 18);
    v18 = *((_QWORD *)this + 18);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
  }
  if ( a3 )
    *a3 = *((struct _GUID *)this + 7);
  v7 = v24;
  v20 = 0;
  v6 = v23;
  v21 = 990;
LABEL_21:
  LeaveCriticalSection(lpCriticalSection);
  v16 = v20;
  if ( v7 )
    ((void (__fastcall *)(struct ISynchronize *))v7->lpVtbl->Release)(v7);
  if ( v6 )
    (*(void (__fastcall **)(struct AsyncISdCallback2 *))(*(_QWORD *)v6 + 16LL))(v6);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v20);
  return v16;
}

```

## disassembly

```asm
0x180014d1c  mov     [rsp-38h+arg_18], rbx
0x180014d21  push    rbp
0x180014d22  push    rsi
0x180014d23  push    rdi
0x180014d24  push    r12
0x180014d26  push    r13
0x180014d28  push    r14
0x180014d2a  push    r15
0x180014d2c  mov     rbp, rsp
0x180014d2f  sub     rsp, 70h
0x180014d33  mov     r14, r8
0x180014d36  mov     r15, rdx
0x180014d39  mov     rsi, rcx
0x180014d3c  lea     rdx, aCsdcontrollerW; "CSdController::_WaitForUI"
0x180014d43  mov     r8d, 3B8h; unsigned __int16
0x180014d49  lea     rcx, [rbp+var_40]; this
0x180014d4d  mov     r9d, 1; unsigned __int16
0x180014d53  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180014d58  xor     ebx, ebx
0x180014d5a  xor     edi, edi
0x180014d5c  mov     [rbp+arg_0], rbx
0x180014d60  mov     [rbp+arg_8], rdi
0x180014d64  test    r15, r15
0x180014d67  jz      short loc_180014D6C
0x180014d69  mov     [r15], rbx
0x180014d6c  test    r14, r14
0x180014d6f  jz      short loc_180014D84
0x180014d71  mov     ecx, 10h
0x180014d76  mov     rax, r14
0x180014d79  mov     [rax], bl
0x180014d7b  inc     rax
0x180014d7e  sub     rcx, 1
0x180014d82  jnz     short loc_180014D79
0x180014d84  lea     rax, [rsi+40h]
0x180014d88  mov     rcx, rax; lpCriticalSection
0x180014d8b  mov     [rbp+lpCriticalSection], rax
0x180014d8f  call    cs:__imp_EnterCriticalSection
0x180014d95  lea     rcx, aSeassignprimar; "SeAssignPrimaryTokenPrivilege"
0x180014d9c  call    ?AssertPrivilege@@YAJPEBG@Z; AssertPrivilege(ushort const *)
0x180014da1  mov     [rbp+var_40], eax
0x180014da4  test    eax, eax
0x180014da6  mov     eax, 3C4h
0x180014dab  jns     short loc_180014DB6
0x180014dad  mov     [rbp+var_3A], ax
0x180014db1  jmp     loc_180014EC2
0x180014db6  lea     rcx, aSeincreasequot; "SeIncreaseQuotaPrivilege"
0x180014dbd  mov     [rbp+var_3C], ax
0x180014dc1  call    ?AssertPrivilege@@YAJPEBG@Z; AssertPrivilege(ushort const *)
0x180014dc6  mov     [rbp+var_40], eax
0x180014dc9  test    eax, eax
0x180014dcb  mov     eax, 3C5h
0x180014dd0  js      short loc_180014DAD
0x180014dd2  lea     rcx, aSetcbprivilege; "SeTcbPrivilege"
0x180014dd9  mov     [rbp+var_3C], ax
0x180014ddd  call    ?AssertPrivilege@@YAJPEBG@Z; AssertPrivilege(ushort const *)
0x180014de2  mov     [rbp+var_40], eax
0x180014de5  test    eax, eax
0x180014de7  mov     eax, 3C6h
0x180014dec  js      short loc_180014DAD
0x180014dee  mov     rdx, [rsi+90h]; struct ISdCallback2 *
0x180014df5  mov     [rbp+var_3C], ax
0x180014df9  test    rdx, rdx
0x180014dfc  jz      short loc_180014E4E
0x180014dfe  lea     r9, [rbp+arg_8]; struct ISynchronize **
0x180014e02  lea     r8, [rbp+arg_0]; struct AsyncISdCallback2 **
0x180014e06  call    ?_GetAsyncCallObject@CSdController@@AEAAJPEAUISdCallback2@@PEAPEAUAsyncISdCallback2@@PEAPEAUISynchronize@@@Z; CSdController::_GetAsyncCallObject(ISdCallback2 *,AsyncISdCallback2 * *,ISynchronize * *)
0x180014e0b  mov     ecx, eax; int
0x180014e0d  mov     [rbp+var_40], eax
0x180014e10  call    ?IsRPCError@@YAJJ@Z; IsRPCError(long)
0x180014e15  test    eax, eax
0x180014e17  jnz     loc_180014F1A
0x180014e1d  movups  xmm0, xmmword ptr [rsi+70h]
0x180014e21  lea     rdx, [rbp+var_50]; struct _GUID
0x180014e25  mov     rcx, rsi; this
0x180014e28  movdqu  xmmword ptr [rbp+var_50.Data1], xmm0
0x180014e2d  call    ?_ReleaseUI@CSdController@@AEAAJU_GUID@@@Z; CSdController::_ReleaseUI(_GUID)
0x180014e32  mov     rbx, [rbp+arg_0]
0x180014e36  test    eax, eax
0x180014e38  mov     rdi, [rbp+arg_8]
0x180014e3c  mov     [rbp+var_40], eax
0x180014e3f  mov     eax, 3D2h
0x180014e44  js      loc_180014DAD
0x180014e4a  mov     [rbp+var_3C], ax
0x180014e4e  lea     rcx, [rsi+30h]; ConditionVariable
0x180014e52  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180014e56  lea     rdx, [rsi+40h]; CriticalSection
0x180014e5a  mov     r12d, 70h ; 'p'
0x180014e60  mov     r13, rsi
0x180014e63  call    ?_SleepConditionVariable@CSdController@@CAJPEAU_RTL_CONDITION_VARIABLE@@PEAU_RTL_CRITICAL_SECTION@@K@Z; CSdController::_SleepConditionVariable(_RTL_CONDITION_VARIABLE *,_RTL_CRITICAL_SECTION *,ulong)
0x180014e68  mov     [rbp+var_40], eax
0x180014e6b  test    eax, eax
0x180014e6d  mov     eax, 3E2h
0x180014e72  js      loc_180014DAD
0x180014e78  mov     [rbp+var_3C], ax
0x180014e7c  test    r15, r15
0x180014e7f  jz      short loc_180014EB3
0x180014e81  mov     rax, [rsi+90h]
0x180014e88  mov     [r15], rax
0x180014e8b  mov     rcx, [rsi+90h]
0x180014e92  test    rcx, rcx
0x180014e95  jz      short loc_180014EA3
0x180014e97  mov     rax, [rcx]
0x180014e9a  mov     rax, [rax+8]
0x180014e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ea3  mov     eax, 3E6h
0x180014ea8  mov     [rbp+var_40], 0
0x180014eaf  mov     [rbp+var_3C], ax
0x180014eb3  test    r14, r14
0x180014eb6  jz      short loc_180014EC2
0x180014eb8  movups  xmm0, xmmword ptr [r12+r13]
0x180014ebd  movdqu  xmmword ptr [r14], xmm0
0x180014ec2  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180014ec6  call    cs:__imp_LeaveCriticalSection
0x180014ecc  mov     esi, [rbp+var_40]
0x180014ecf  test    rdi, rdi
0x180014ed2  jz      short loc_180014EE3
0x180014ed4  mov     rax, [rdi]
0x180014ed7  mov     rcx, rdi
0x180014eda  mov     rax, [rax+10h]
0x180014ede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ee3  test    rbx, rbx
0x180014ee6  jz      short loc_180014EF7
0x180014ee8  mov     rcx, [rbx]
0x180014eeb  mov     rax, [rcx+10h]
0x180014eef  mov     rcx, rbx
0x180014ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ef7  lea     rcx, [rbp+var_40]; this
0x180014efb  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180014f00  mov     rbx, [rsp+70h+arg_18]
0x180014f08  mov     eax, esi
0x180014f0a  add     rsp, 70h
0x180014f0e  pop     r15
0x180014f10  pop     r14
0x180014f12  pop     r13
0x180014f14  pop     r12
0x180014f16  pop     rdi
0x180014f17  pop     rsi
0x180014f18  pop     rbp
0x180014f19  retn
0x180014f1a  test    r15, r15
0x180014f1d  jz      short loc_180014F41
0x180014f1f  mov     rax, [rsi+90h]
0x180014f26  mov     [r15], rax
0x180014f29  mov     rcx, [rsi+90h]
0x180014f30  test    rcx, rcx
0x180014f33  jz      short loc_180014F41
0x180014f35  mov     rax, [rcx]
0x180014f38  mov     rax, [rax+8]
0x180014f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f41  test    r14, r14
0x180014f44  jz      short loc_180014F4F
0x180014f46  movups  xmm0, xmmword ptr [rsi+70h]
0x180014f4a  movdqu  xmmword ptr [r14], xmm0
0x180014f4f  mov     rdi, [rbp+arg_8]
0x180014f53  mov     eax, 3DEh
0x180014f58  mov     [rbp+var_40], ebx
0x180014f5b  mov     rbx, [rbp+arg_0]
0x180014f5f  mov     [rbp+var_3C], ax
0x180014f63  jmp     loc_180014EC2
```
