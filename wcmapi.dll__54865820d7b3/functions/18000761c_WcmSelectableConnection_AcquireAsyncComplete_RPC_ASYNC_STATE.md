# WcmSelectableConnection::AcquireAsyncComplete(_RPC_ASYNC_STATE *)

- ea: `0x18000761c`
- end: `0x180007728`
- name: `?AcquireAsyncComplete@WcmSelectableConnection@@AEAAXPEAU_RPC_ASYNC_STATE@@@Z`
- size: `268`
- prototype: `void(WcmSelectableConnection *__hidden this, struct _RPC_ASYNC_STATE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016cc0`

## callees

- `0x18000761c`
- `0x180007730`
- `0x180008a90`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007650`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007650`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180007669`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180007669`

## pseudocode

```c
void __fastcall WcmSelectableConnection::AcquireAsyncComplete(
        struct _RTL_CRITICAL_SECTION *this,
        struct _RPC_ASYNC_STATE *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  RPC_STATUS v5; // eax
  unsigned int v6; // esi
  int v7; // esi
  HANDLE LockSemaphore; // rdi
  ULONG_PTR SpinCount; // rbx
  struct _RTL_CRITICAL_SECTION *v10; // [rsp+30h] [rbp-38h] BYREF
  int Reply; // [rsp+38h] [rbp-30h] BYREF

  v2 = this + 14;
  Reply = 0;
  EnterCriticalSection(this + 14);
  v10 = v2;
  v5 = RpcAsyncCompleteCall(a2, &Reply);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
    {
      v7 = (unsigned __int16)v5;
LABEL_6:
      v6 = v7 | 0x80070000;
    }
  }
  else
  {
    v6 = Reply;
    if ( Reply > 0 )
    {
      v7 = (unsigned __int16)Reply;
      goto LABEL_6;
    }
  }
  LockSemaphore = this[13].LockSemaphore;
  SpinCount = this[13].SpinCount;
  LODWORD(this->OwningThread) = HIDWORD(this[18].DebugInfo);
  this[13].LockSemaphore = 0;
  this[13].SpinCount = 0;
  LOBYTE(this[18].DebugInfo) = 0;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v10);
  (*(void (__fastcall **)(HANDLE, _QWORD, struct _RTL_CRITICAL_SECTION *, ULONG_PTR))(*(_QWORD *)LockSemaphore + 24LL))(
    LockSemaphore,
    v6,
    this,
    SpinCount);
  (*(void (__fastcall **)(HANDLE))(*(_QWORD *)LockSemaphore + 16LL))(LockSemaphore);
  ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this->DebugInfo->ProcessLocksList.Flink)(this);
}

```

## disassembly

```asm
0x18000761c  mov     [rsp+arg_10], rbx
0x180007621  push    rsi
0x180007622  push    rdi
0x180007623  push    r14
0x180007625  sub     rsp, 50h
0x180007629  mov     rax, cs:__security_cookie
0x180007630  xor     rax, rsp
0x180007633  mov     [rsp+68h+var_28], rax
0x180007638  lea     rbx, [rcx+230h]
0x18000763f  mov     [rsp+68h+Reply], 0
0x180007647  mov     r14, rcx
0x18000764a  mov     rdi, rdx
0x18000764d  mov     rcx, rbx; lpCriticalSection
0x180007650  call    cs:__imp_EnterCriticalSection
0x180007657  nop     dword ptr [rax+rax+00h]
0x18000765c  lea     rdx, [rsp+68h+Reply]; Reply
0x180007661  mov     [rsp+68h+var_38], rbx
0x180007666  mov     rcx, rdi; pAsync
0x180007669  call    cs:__imp_RpcAsyncCompleteCall
0x180007670  nop     dword ptr [rax+rax+00h]
0x180007675  mov     esi, eax
0x180007677  test    eax, eax
0x180007679  jz      short loc_180007682
0x18000767b  jle     short loc_180007693
0x18000767d  movzx   esi, ax
0x180007680  jmp     short loc_18000768D
0x180007682  mov     esi, [rsp+68h+Reply]
0x180007686  test    esi, esi
0x180007688  jle     short loc_180007693
0x18000768a  movzx   esi, si
0x18000768d  or      esi, 80070000h
0x180007693  mov     eax, [r14+2D4h]
0x18000769a  lea     rcx, [rsp+68h+var_38]
0x18000769f  mov     rdi, [r14+220h]
0x1800076a6  mov     rbx, [r14+228h]
0x1800076ad  mov     [r14+10h], eax
0x1800076b1  mov     qword ptr [r14+220h], 0
0x1800076bc  mov     qword ptr [r14+228h], 0
0x1800076c7  mov     byte ptr [r14+2D0h], 0
0x1800076cf  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800076d4  mov     rax, [rdi]
0x1800076d7  mov     r9, rbx
0x1800076da  mov     r8, r14
0x1800076dd  mov     edx, esi
0x1800076df  mov     rcx, rdi
0x1800076e2  mov     rax, [rax+18h]
0x1800076e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076eb  mov     rax, [rdi]
0x1800076ee  mov     rcx, rdi
0x1800076f1  mov     rax, [rax+10h]
0x1800076f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076fa  mov     rax, [r14]
0x1800076fd  mov     rcx, r14
0x180007700  mov     rax, [rax+10h]
0x180007704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007709  mov     rcx, [rsp+68h+var_28]
0x18000770e  xor     rcx, rsp; StackCookie
0x180007711  call    __security_check_cookie
0x180007716  mov     rbx, [rsp+68h+arg_10]
0x18000771e  add     rsp, 50h
0x180007722  pop     r14
0x180007724  pop     rdi
0x180007725  pop     rsi
0x180007726  retn
```
