# DBLockManager::HasLocked(__MIDL___MIDL_itf_unistore_0000_0002_0001)

- ea: `0x1800042c0`
- end: `0x18000442b`
- name: `?HasLocked@DBLockManager@@UEAAHW4__MIDL___MIDL_itf_unistore_0000_0002_0001@@@Z`
- size: `363`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800042c0`
- `0x180005490`
- `0x18006f180`
- `0x1800736c4`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004373`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004373`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180004311`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180004311`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180004420`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180004420`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180004346`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180004346`

## string_xrefs

- `0x1800043fe`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`

## pseudocode

```c
__int64 __fastcall DBLockManager::HasLocked(__int64 a1, int a2)
{
  __int64 (__fastcall *v3)(__int64, unsigned __int64 *, __int64, int *); // rdi
  unsigned __int64 *Value; // rax
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rcx
  DWORD v7; // eax
  __int64 v8; // rdx
  int v9; // eax
  int v10; // r8d
  unsigned __int64 v12[5]; // [rsp+40h] [rbp-28h] BYREF
  int v13; // [rsp+78h] [rbp+10h] BYREF
  int v14; // [rsp+80h] [rbp+18h] BYREF
  unsigned __int64 v15; // [rsp+88h] [rbp+20h]

  v14 = a2;
  v13 = 0;
  if ( a2 != 2147483645 )
  {
    if ( a2 != 2147483641 && a2 != 2147483643 && a2 != 2147483644 && a2 >= 2147483641 && a2 != 2147483646 )
      Log_AssertionEvent(
        (unsigned int)(a2 - 2147483644),
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dblockmanager.cpp",
        1147);
    v13 = 1;
  }
  v3 = *(__int64 (__fastcall **)(__int64, unsigned __int64 *, __int64, int *))(*(_QWORD *)a1 + 32LL);
  if ( g_dwCallerClientIdSlot == -1 )
  {
    v7 = TlsAlloc();
    if ( _InterlockedCompareExchange((volatile signed __int32 *)&g_dwCallerClientIdSlot, v7, -1) == -1 )
    {
      if ( v7 == -1 )
      {
        Log_AssertionEvent_2(0xFFFFFFFFLL, v8, 1073);
        goto LABEL_11;
      }
    }
    else
    {
      TlsFree(v7);
    }
  }
  Value = (unsigned __int64 *)TlsGetValue(g_dwCallerClientIdSlot);
  if ( Value )
  {
    v5 = *Value;
    v15 = v5;
    if ( (_DWORD)v5 )
    {
      v6 = HIDWORD(v15);
      goto LABEL_12;
    }
  }
LABEL_11:
  LODWORD(v6) = GetCurrentThreadId();
  LODWORD(v5) = -2;
LABEL_12:
  v12[0] = (unsigned int)v5 | ((unsigned __int64)(unsigned int)v6 << 32);
  v9 = v3(a1, v12, 1, &v14);
  if ( v9 < 0 )
    Log_UnistoreHREvent(v9, 0, v10, 1154, (unsigned int)&v13);
  return 0;
}

```

## disassembly

```asm
0x1800042c0  push    rbx
0x1800042c2  push    rdi
0x1800042c3  sub     rsp, 58h
0x1800042c7  xor     edi, edi
0x1800042c9  mov     [rsp+68h+arg_10], edx
0x1800042d0  mov     [rsp+68h+arg_8], edi
0x1800042d4  mov     rbx, rcx
0x1800042d7  cmp     edx, 7FFFFFFDh
0x1800042dd  jz      short loc_1800042F5
0x1800042df  mov     ecx, edx
0x1800042e1  sub     ecx, 7FFFFFF9h
0x1800042e7  jnz     loc_1800043D1
0x1800042ed  mov     [rsp+68h+arg_8], 1
0x1800042f5  mov     rax, [rbx]
0x1800042f8  mov     [rsp+68h+arg_0], edi
0x1800042fc  mov     rdi, [rax+20h]
0x180004300  mov     eax, cs:?g_dwCallerClientIdSlot@@3KC; ulong volatile g_dwCallerClientIdSlot
0x180004306  cmp     eax, 0FFFFFFFFh
0x180004309  jz      short loc_180004346
0x18000430b  mov     ecx, cs:?g_dwCallerClientIdSlot@@3KC; dwTlsIndex
0x180004311  call    cs:__imp_TlsGetValue
0x180004317  test    rax, rax
0x18000431a  jz      short loc_180004373
0x18000431c  mov     rax, [rax]
0x18000431f  mov     rcx, rax
0x180004322  mov     dword ptr [rsp+68h+arg_18], eax
0x180004329  shr     rcx, 20h
0x18000432d  mov     dword ptr [rsp+68h+arg_18+4], ecx
0x180004334  test    eax, eax
0x180004336  jz      short loc_180004373
0x180004338  mov     rcx, [rsp+68h+arg_18]
0x180004340  shr     rcx, 20h
0x180004344  jmp     short loc_180004380
0x180004346  call    cs:__imp_TlsAlloc
0x18000434c  mov     ecx, eax; dwTlsIndex
0x18000434e  mov     eax, 0FFFFFFFFh
0x180004353  lock cmpxchg cs:?g_dwCallerClientIdSlot@@3KC, ecx; ulong volatile g_dwCallerClientIdSlot
0x18000435b  cmp     eax, 0FFFFFFFFh
0x18000435e  jnz     loc_180004420
0x180004364  cmp     ecx, eax
0x180004366  jnz     short loc_18000430B
0x180004368  mov     r8d, 431h
0x18000436e  call    Log_AssertionEvent_2
0x180004373  call    cs:__imp_GetCurrentThreadId
0x180004379  mov     ecx, eax
0x18000437b  mov     eax, 0FFFFFFFEh
0x180004380  mov     edx, ecx
0x180004382  lea     r9, [rsp+68h+arg_10]
0x18000438a  mov     ecx, eax
0x18000438c  mov     r8d, 1
0x180004392  shl     rdx, 20h
0x180004396  lea     rax, [rsp+68h+arg_0]
0x18000439b  mov     [rsp+68h+var_40], rax
0x1800043a0  or      rdx, rcx
0x1800043a3  lea     rax, [rsp+68h+arg_8]
0x1800043a8  mov     [rsp+68h+var_28], rdx
0x1800043ad  mov     [rsp+68h+var_48], rax
0x1800043b2  lea     rdx, [rsp+68h+var_28]
0x1800043b7  mov     rax, rdi
0x1800043ba  mov     rcx, rbx
0x1800043bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043c2  test    eax, eax
0x1800043c4  js      short loc_18000440F
0x1800043c6  mov     eax, [rsp+68h+arg_0]
0x1800043ca  add     rsp, 58h
0x1800043ce  pop     rdi
0x1800043cf  pop     rbx
0x1800043d0  retn
0x1800043d1  sub     ecx, 2
0x1800043d4  jz      loc_1800042ED
0x1800043da  sub     ecx, 1
0x1800043dd  jz      loc_1800042ED
0x1800043e3  cmp     edx, 7FFFFFF9h
0x1800043e9  jl      loc_1800042ED
0x1800043ef  cmp     ecx, 2
0x1800043f2  jz      loc_1800042ED
0x1800043f8  mov     r8d, 47Bh
0x1800043fe  lea     rdx, aOnecoreuapBase_52; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180004405  call    Log_AssertionEvent
0x18000440a  jmp     loc_1800042ED
0x18000440f  xor     edx, edx
0x180004411  mov     r9d, 482h
0x180004417  mov     ecx, eax
0x180004419  call    Log_UnistoreHREvent
0x18000441e  jmp     short loc_1800043C6
0x180004420  call    cs:__imp_TlsFree
0x180004426  jmp     loc_18000430B
```
