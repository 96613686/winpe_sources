# sub_18000CDFC

- ea: `0x18000cdfc`
- end: `0x18000cea1`
- name: `sub_18000CDFC`
- size: `165`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000cea8`
- `0x18000ebf8`

## callees

- `0x1800099a0`
- `0x18000cdfc`
- `0x180018d5e`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ce36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ce36`

## pseudocode

```c
__int64 __fastcall sub_18000CDFC(__int64 a1)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  int v3; // ebx
  __int64 v4; // rcx
  signed __int32 v6[10]; // [rsp+0h] [rbp-28h] BYREF

  v2 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 264);
  if ( v2 )
    (**v2)(v2, 1);
  *(_QWORD *)(a1 + 264) = 0;
  v3 = *(_DWORD *)(a1 + 344);
  if ( GetCurrentThreadId() != v3 )
    SHTaskPoolAllowThreadReuse();
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 272));
  if ( *(int *)(a1 + 168) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 168), 0xFFFFFFFF) == 1 )
  {
    _InterlockedOr(v6, 0);
    v4 = *(_QWORD *)(a1 + 152);
    *(_QWORD *)(a1 + 152) = 0;
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return sub_1800099A0(a1 + 8);
}

```

## disassembly

```asm
0x18000cdfc  mov     [rsp+arg_0], rbx
0x18000ce01  push    rdi
0x18000ce02  sub     rsp, 20h
0x18000ce06  mov     rdi, rcx
0x18000ce09  mov     rcx, [rcx+108h]
0x18000ce10  test    rcx, rcx
0x18000ce13  jz      short loc_18000CE25
0x18000ce15  mov     rax, [rcx]
0x18000ce18  mov     edx, 1
0x18000ce1d  mov     rax, [rax]
0x18000ce20  call    j__guard_dispatch_icall
0x18000ce25  mov     qword ptr [rdi+108h], 0
0x18000ce30  mov     ebx, [rdi+158h]
0x18000ce36  call    cs:GetCurrentThreadId
0x18000ce3c  cmp     eax, ebx
0x18000ce3e  jz      short loc_18000CE45
0x18000ce40  call    SHTaskPoolAllowThreadReuse
0x18000ce45  lock inc dword ptr [rdi+110h]
0x18000ce4c  cmp     dword ptr [rdi+0A8h], 0
0x18000ce53  jle     short loc_18000CE8E
0x18000ce55  or      eax, 0FFFFFFFFh
0x18000ce58  lock xadd [rdi+0A8h], eax
0x18000ce60  cmp     eax, 1
0x18000ce63  jnz     short loc_18000CE8E
0x18000ce65  lock or [rsp+28h+var_28], 0
0x18000ce6a  mov     rcx, [rdi+98h]
0x18000ce71  mov     qword ptr [rdi+98h], 0
0x18000ce7c  test    rcx, rcx
0x18000ce7f  jz      short loc_18000CE8E
0x18000ce81  mov     rax, [rcx]
0x18000ce84  mov     rax, [rax+10h]
0x18000ce88  call    j__guard_dispatch_icall
0x18000ce8d  nop
0x18000ce8e  lea     rcx, [rdi+8]
0x18000ce92  mov     rbx, [rsp+28h+arg_0]
0x18000ce97  add     rsp, 20h
0x18000ce9b  pop     rdi
0x18000ce9c  jmp     sub_1800099A0
```
