# UlAtqSendHttpResponse(void *,int,ulong,_HTTP_RESPONSE_V2 *,_HTTP_CACHE_POLICY *,ulong *,_HTTP_LOG_DATA *)

- ea: `0x18000f930`
- end: `0x18000fabf`
- name: `?UlAtqSendHttpResponse@@YAJPEAXHKPEAU_HTTP_RESPONSE_V2@@PEAU_HTTP_CACHE_POLICY@@PEAKPEAU_HTTP_LOG_DATA@@@Z`
- size: `399`
- prototype: `int(void *, int, unsigned int, struct _HTTP_RESPONSE_V2 *, struct _HTTP_CACHE_POLICY *, unsigned int *, struct _HTTP_LOG_DATA *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000f930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f9ce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f9ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000fa61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000fa9e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000fa61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000fa9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f9b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f9b2`
- `HTTPAPI!HttpSendHttpResponse` at `0x18000fa44`
- `HTTPAPI!HttpSendHttpResponse` at `0x18000fa44`

## pseudocode

```c
__int64 __fastcall UlAtqSendHttpResponse(
        char *a1,
        int a2,
        ULONG a3,
        struct _HTTP_RESPONSE_V2 *a4,
        struct _HTTP_CACHE_POLICY *CachePolicy,
        unsigned int *BytesSent,
        struct _HTTP_LOG_DATA *LogData)
{
  ULONG v7; // r14d
  WP_CONTEXT *v10; // rdi
  struct _OVERLAPPED *Overlapped; // r12
  _QWORD *v12; // rbx
  RTL_SRWLOCK *v13; // r15
  void *v14; // rcx
  ULONG v15; // eax
  int v16; // ebx

  v7 = a3;
  if ( a2 || BytesSent )
  {
    if ( !UL_NATIVE_REQUEST::sm_fDisableCopySend && (!a2 || (a3 & 2) != 0) )
      v7 = a3 | 4;
    v10 = g_pwpContext;
    Overlapped = (struct _OVERLAPPED *)(a1 + 3064);
    *(_OWORD *)(a1 + 3064) = 0;
    *(_OWORD *)(a1 + 3080) = 0;
    v12 = (_QWORD *)*((_QWORD *)v10 + 96);
    v13 = (RTL_SRWLOCK *)(*v12 + v12[1] * ((unsigned __int64)GetCurrentThreadId() % v12[2]));
    AcquireSRWLockShared(v13);
    v14 = (void *)*((_QWORD *)v10 + 95);
    if ( v14 )
    {
      if ( a2 )
        _InterlockedIncrement((volatile signed __int32 *)a1 + 784);
      else
        Overlapped = 0;
      v15 = HttpSendHttpResponse(
              v14,
              *(_QWORD *)(*((_QWORD *)a1 + 368) + 16LL),
              v7,
              a4,
              CachePolicy,
              BytesSent,
              0,
              0,
              Overlapped,
              LogData);
      v16 = v15;
      if ( a2 )
      {
        if ( v15 != 997 )
          _InterlockedDecrement((volatile signed __int32 *)a1 + 784);
      }
      ReleaseSRWLockShared(v13);
      if ( v16 <= 0 )
        return (unsigned int)v16;
    }
    else
    {
      LOWORD(v16) = 6;
      ReleaseSRWLockShared(v13);
    }
    return (unsigned __int16)v16 | 0x80070000;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000f930  mov     [rsp+HttpResponse], r9
0x18000f935  push    rbp
0x18000f936  push    rsi
0x18000f937  push    r13
0x18000f939  push    r14
0x18000f93b  sub     rsp, 58h
0x18000f93f  mov     r13, [rsp+78h+arg_28]
0x18000f947  mov     r14d, r8d
0x18000f94a  mov     ebp, edx
0x18000f94c  mov     rsi, rcx
0x18000f94f  test    edx, edx
0x18000f951  jz      loc_18000FAA6
0x18000f957  cmp     cs:?sm_fDisableCopySend@UL_NATIVE_REQUEST@@0HA, 0; int UL_NATIVE_REQUEST::sm_fDisableCopySend
0x18000f95e  mov     [rsp+78h+arg_0], rbx
0x18000f966  mov     [rsp+78h+arg_8], rdi
0x18000f96e  mov     [rsp+78h+arg_10], r12
0x18000f976  mov     [rsp+78h+var_28], r15
0x18000f97b  jnz     short loc_18000F98F
0x18000f97d  test    ebp, ebp
0x18000f97f  jz      loc_18000FAB6
0x18000f985  test    r14b, 2
0x18000f989  jnz     loc_18000FAB6
0x18000f98f  mov     rdi, cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA; WP_CONTEXT * g_pwpContext
0x18000f996  lea     r12, [rcx+0BF8h]
0x18000f99d  xorps   xmm0, xmm0
0x18000f9a0  movups  xmmword ptr [r12], xmm0
0x18000f9a5  movups  xmmword ptr [r12+10h], xmm0
0x18000f9ab  mov     rbx, [rdi+300h]
0x18000f9b2  call    cs:__imp_GetCurrentThreadId
0x18000f9b8  mov     eax, eax
0x18000f9ba  xor     edx, edx
0x18000f9bc  div     qword ptr [rbx+10h]
0x18000f9c0  mov     r15d, edx
0x18000f9c3  imul    r15, [rbx+8]
0x18000f9c8  add     r15, [rbx]
0x18000f9cb  mov     rcx, r15; SRWLock
0x18000f9ce  call    cs:__imp_AcquireSRWLockShared
0x18000f9d4  mov     rcx, [rdi+2F8h]; RequestQueueHandle
0x18000f9db  mov     rdi, [rsp+78h+arg_8]
0x18000f9e3  test    rcx, rcx
0x18000f9e6  jz      loc_18000FA96
0x18000f9ec  test    ebp, ebp
0x18000f9ee  jz      short loc_18000F9F7
0x18000f9f0  lock inc dword ptr [rsi+0C40h]
0x18000f9f7  mov     rax, [rsp+78h+arg_30]
0x18000f9ff  xor     r8d, r8d
0x18000fa02  mov     rdx, [rsi+0B80h]
0x18000fa09  test    ebp, ebp
0x18000fa0b  mov     r9, [rsp+78h+HttpResponse]; HttpResponse
0x18000fa13  mov     [rsp+78h+LogData], rax; LogData
0x18000fa18  cmovz   r12, r8
0x18000fa1c  mov     rax, [rsp+78h+arg_20]
0x18000fa24  mov     rdx, [rdx+10h]; RequestId
0x18000fa28  mov     [rsp+78h+Overlapped], r12; Overlapped
0x18000fa2d  mov     [rsp+78h+Reserved2], r8d; Reserved2
0x18000fa32  mov     [rsp+78h+Reserved1], r8; Reserved1
0x18000fa37  mov     r8d, r14d; Flags
0x18000fa3a  mov     [rsp+78h+BytesSent], r13; BytesSent
0x18000fa3f  mov     [rsp+78h+CachePolicy], rax; CachePolicy
0x18000fa44  call    cs:__imp_HttpSendHttpResponse
0x18000fa4a  mov     ebx, eax
0x18000fa4c  test    ebp, ebp
0x18000fa4e  jz      short loc_18000FA5E
0x18000fa50  cmp     eax, 3E5h
0x18000fa55  jz      short loc_18000FA5E
0x18000fa57  lock dec dword ptr [rsi+0C40h]
0x18000fa5e  mov     rcx, r15; SRWLock
0x18000fa61  call    cs:__imp_ReleaseSRWLockShared
0x18000fa67  test    ebx, ebx
0x18000fa69  jle     short loc_18000FA74
0x18000fa6b  movzx   ebx, bx
0x18000fa6e  or      ebx, 80070000h
0x18000fa74  mov     r15, [rsp+78h+var_28]
0x18000fa79  mov     eax, ebx
0x18000fa7b  mov     rbx, [rsp+78h+arg_0]
0x18000fa83  mov     r12, [rsp+78h+arg_10]
0x18000fa8b  add     rsp, 58h
0x18000fa8f  pop     r14
0x18000fa91  pop     r13
0x18000fa93  pop     rsi
0x18000fa94  pop     rbp
0x18000fa95  retn
0x18000fa96  mov     rcx, r15; SRWLock
0x18000fa99  mov     ebx, 6
0x18000fa9e  call    cs:__imp_ReleaseSRWLockShared
0x18000faa4  jmp     short loc_18000FA6B
0x18000faa6  test    r13, r13
0x18000faa9  jnz     loc_18000F957
0x18000faaf  mov     eax, 80070057h
0x18000fab4  jmp     short loc_18000FA8B
0x18000fab6  or      r14d, 4
0x18000faba  jmp     loc_18000F98F
```
