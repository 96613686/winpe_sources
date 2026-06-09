# VmbusPipeClientUnregisterChannelNotification

- ea: `0x1800073d0`
- end: `0x18000747c`
- name: `VmbusPipeClientUnregisterChannelNotification`
- size: `172`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800024e0`
- `0x180004054`
- `0x18000416c`
- `0x180006e78`
- `0x1800073d0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180007437`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180007437`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180007454`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180007454`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800073fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800073fe`

## pseudocode

```c
__int64 __fastcall VmbusPipeClientUnregisterChannelNotification(__int64 a1, int a2)
{
  __int64 v2; // rdi
  __int64 v4; // rbx
  __int64 v7; // [rsp+20h] [rbp-48h] BYREF
  __int64 v8; // [rsp+28h] [rbp-40h] BYREF

  v2 = a1 + 616;
  v4 = 0;
  v8 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 616));
  v7 = v2;
  *(_BYTE *)(a1 + 664) = 1;
  if ( a2 )
  {
    wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>::operator=(&v8);
    v4 = v8;
  }
  if ( !*(_BYTE *)(a1 + 666) )
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 672));
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v7);
  if ( a2 )
    WaitForThreadpoolWorkCallbacks(*(PTP_WORK *)(v4 + 672), 0);
  return wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>::reset(&v8, 0);
}

```

## disassembly

```asm
0x1800073d0  push    rbx
0x1800073d2  push    rbp
0x1800073d3  push    rsi
0x1800073d4  push    rdi
0x1800073d5  sub     rsp, 48h
0x1800073d9  mov     rax, cs:__security_cookie
0x1800073e0  xor     rax, rsp
0x1800073e3  mov     [rsp+68h+var_38], rax
0x1800073e8  lea     rdi, [rcx+268h]
0x1800073ef  mov     rsi, rcx
0x1800073f2  xor     ebx, ebx
0x1800073f4  mov     rcx, rdi; lpCriticalSection
0x1800073f7  mov     ebp, edx
0x1800073f9  mov     [rsp+68h+var_40], rbx
0x1800073fe  call    cs:__imp_EnterCriticalSection
0x180007404  mov     [rsp+68h+var_48], rdi
0x180007409  lea     rdx, [rsi+290h]
0x180007410  mov     byte ptr [rdx+8], 1
0x180007414  test    ebp, ebp
0x180007416  jz      short loc_180007427
0x180007418  lea     rcx, [rsp+68h+var_40]
0x18000741d  call    ??4?$unique_ptr@UChannelNotificationContext@@U?$default_delete@UChannelNotificationContext@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>::operator=(wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>> &&)
0x180007422  mov     rbx, [rsp+68h+var_40]
0x180007427  cmp     byte ptr [rsi+29Ah], 0
0x18000742e  jnz     short loc_18000743D
0x180007430  mov     rcx, [rsi+2A0h]; pwk
0x180007437  call    cs:__imp_SubmitThreadpoolWork
0x18000743d  lea     rcx, [rsp+68h+var_48]
0x180007442  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180007447  test    ebp, ebp
0x180007449  jz      short loc_18000745A
0x18000744b  mov     rcx, [rbx+2A0h]; pwk
0x180007452  xor     edx, edx; fCancelPendingCallbacks
0x180007454  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000745a  xor     edx, edx
0x18000745c  lea     rcx, [rsp+68h+var_40]
0x180007461  call    ?reset@?$unique_ptr@UChannelNotificationContext@@U?$default_delete@UChannelNotificationContext@@@wistd@@@wistd@@QEAAXPEAUChannelNotificationContext@@@Z; wistd::unique_ptr<ChannelNotificationContext,wistd::default_delete<ChannelNotificationContext>>::reset(ChannelNotificationContext *)
0x180007466  mov     rcx, [rsp+68h+var_38]
0x18000746b  xor     rcx, rsp; StackCookie
0x18000746e  call    __security_check_cookie
0x180007473  add     rsp, 48h
0x180007477  pop     rdi
0x180007478  pop     rsi
0x180007479  pop     rbp
0x18000747a  pop     rbx
0x18000747b  retn
```
