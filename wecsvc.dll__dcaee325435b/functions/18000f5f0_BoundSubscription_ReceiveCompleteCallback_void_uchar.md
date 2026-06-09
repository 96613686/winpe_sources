# BoundSubscription::ReceiveCompleteCallback(void *,uchar)

- ea: `0x18000f5f0`
- end: `0x18000f669`
- name: `?ReceiveCompleteCallback@BoundSubscription@@CAXPEAXE@Z`
- size: `121`
- prototype: `void __fastcall(char *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000e81c`
- `0x18000f5f0`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f628`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f628`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f642`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f642`

## pseudocode

```c
void __fastcall BoundSubscription::ReceiveCompleteCallback(char *a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  const wmi::Exception *v3; // rdi
  int v4; // eax
  wchar_t *v5; // rbx
  const wchar_t *v6; // rax
  const wchar_t *v7; // rcx
  __int64 v8; // rax
  const wchar_t *v9; // rax
  const wchar_t *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  char v13; // al
  int v14; // r8d
  _QWORD *v15; // rcx
  _QWORD *v16; // r9
  int v17; // [rsp+40h] [rbp-68h] BYREF
  wchar_t *v18; // [rsp+48h] [rbp-60h]
  struct _RTL_CRITICAL_SECTION *v19; // [rsp+50h] [rbp-58h]
  char *v20; // [rsp+58h] [rbp-50h]
  const wmi::Exception *v21; // [rsp+60h] [rbp-48h] BYREF
  const wchar_t *v22; // [rsp+68h] [rbp-40h] BYREF
  int v23; // [rsp+70h] [rbp-38h]
  int v24; // [rsp+74h] [rbp-34h]
  const wchar_t *v25; // [rsp+78h] [rbp-30h]
  int v26; // [rsp+80h] [rbp-28h]
  int v27; // [rsp+84h] [rbp-24h]
  int *v28; // [rsp+88h] [rbp-20h]
  __int64 v29; // [rsp+90h] [rbp-18h]

  v18 = (wchar_t *)a1;
  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
  v19 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
  v20 = a1 + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  try
  {
    BoundSubscription::OnReceiveComplete((BoundSubscription *)a1);
  }
  catch ( const wmi::Exception *v21 )
  {
    v3 = v21;
    v4 = (**(__int64 (__fastcall ***)(const wmi::Exception *))v21)(v21);
    v5 = v18;
    *((_DWORD *)v18 + 45) = v4;
    BoundSubscription::InternalDeactivate((BoundSubscription *)v5, 0);
    v17 = (**(__int64 (__fastcall ***)(const wmi::Exception *))v3)(v3);
    v6 = (const wchar_t *)(*((_QWORD *)v5 + 8) + 56LL);
    if ( *(_QWORD *)(*((_QWORD *)v5 + 8) + 80LL) >= 8u )
      v6 = *(const wchar_t **)v6;
    v7 = &word_180026AD8;
    if ( v6 )
      v7 = v6;
    v8 = -1;
    do
      ++v8;
    while ( v7[v8] );
    v22 = v7;
    v23 = 2 * v8 + 2;
    v24 = 0;
    v9 = v5 + 36;
    if ( *((_QWORD *)v5 + 12) >= 8u )
      v9 = *(const wchar_t **)v9;
    v10 = &word_180026AD8;
    if ( v9 )
      v10 = v9;
    v11 = -1;
    do
      ++v11;
    while ( v10[v11] );
    v25 = v10;
    v26 = 2 * v11 + 2;
    v27 = 0;
    v28 = &v17;
    v29 = 4;
    v12 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v5 + 8) + 104LL) + 136LL);
    (*(void (__fastcall **)(__int64, __int64 *, __int64, const wchar_t **))(*(_QWORD *)v12 + 8LL))(
      v12,
      EVTCOLL_SUBSCRIPTION_ACTIVATION_ERROR,
      3,
      &v22);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = (**(__int64 (__fastcall ***)(const wmi::Exception *))v3)(v3);
      v15 = v5 + 36;
      if ( *((_QWORD *)v5 + 12) >= 8u )
        v15 = (_QWORD *)*v15;
      v16 = (_QWORD *)(*((_QWORD *)v5 + 8) + 56LL);
      if ( *(_QWORD *)(*((_QWORD *)v5 + 8) + 80LL) >= 8u )
        v16 = (_QWORD *)*v16;
      WPP_SF_SSqD(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, v14, (_DWORD)v16, (__int64)v15, (char)v5, v13);
    }
    v2 = v19;
  }
  catch ( ... )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58);
    }
    EcTerminateService();
  }
  LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x18000f5f0  mov     [rsp+arg_8], rbx
0x18000f5f5  push    rdi
0x18000f5f6  sub     rsp, 0A0h
0x18000f5fd  mov     rax, cs:__security_cookie
0x18000f604  xor     rax, rsp
0x18000f607  mov     [rsp+0A8h+var_10], rax
0x18000f60f  mov     rdi, rcx
0x18000f612  mov     [rsp+0A8h+var_60], rcx
0x18000f617  lea     rbx, [rcx+10h]
0x18000f61b  mov     [rsp+0A8h+var_58], rbx
0x18000f620  mov     [rsp+0A8h+var_50], rbx
0x18000f625  mov     rcx, rbx; lpCriticalSection
0x18000f628  call    cs:__imp_EnterCriticalSection
0x18000f62e  nop
0x18000f62f  mov     rcx, rdi; this
0x18000f632  call    ?OnReceiveComplete@BoundSubscription@@AEAAXXZ; BoundSubscription::OnReceiveComplete(void)
0x18000f637  nop
0x18000f638  jmp     short loc_18000F63F
0x18000f63a  mov     rbx, [rsp+0A8h+var_58]
0x18000f63f  mov     rcx, rbx; lpCriticalSection
0x18000f642  call    cs:__imp_LeaveCriticalSection
0x18000f648  mov     rcx, [rsp+0A8h+var_10]
0x18000f650  xor     rcx, rsp; StackCookie
0x18000f653  call    __security_check_cookie
0x18000f658  mov     rbx, [rsp+0A8h+arg_8]
0x18000f660  add     rsp, 0A0h
0x18000f667  pop     rdi
0x18000f668  retn
```
