# ChGpadlCreated

- ea: `0x14000eec8`
- end: `0x14000ef62`
- name: `ChGpadlCreated`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140011418`

## callees

- `0x14000eec8`
- `0x14000f6c4`
- `0x14000f794`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14000ef3b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000ef3b`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000eef9`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000eef9`

## pseudocode

```c
void __fastcall ChGpadlCreated(__int64 a1, __int64 a2, unsigned int a3, int a4)
{
  struct _FAST_MUTEX *v4; // rbp
  int v9; // eax
  __int64 v10; // [rsp+40h] [rbp+8h] BYREF

  v4 = (struct _FAST_MUTEX *)(a1 + 432);
  v10 = 0;
  ExAcquireFastMutex((PFAST_MUTEX)(a1 + 432));
  if ( (int)ChpLookupGpadlByHandleLocked(a1, a2, a3, &v10) < 0 || (v9 = *(_DWORD *)(v10 + 16)) != 0 && v9 != 3 )
    __fastfail(0x3Au);
  ChpGpadlCreatedLocked(a1, v10, a4);
  ExReleaseFastMutex(v4);
}

```

## disassembly

```asm
0x14000eec8  mov     [rsp+arg_8], rbx
0x14000eecd  mov     [rsp+arg_10], rbp
0x14000eed2  push    rsi
0x14000eed3  push    rdi
0x14000eed4  push    r14
0x14000eed6  sub     rsp, 20h
0x14000eeda  lea     rbp, [rcx+1B0h]
0x14000eee1  mov     [rsp+38h+arg_0], 0
0x14000eeea  mov     rsi, rcx
0x14000eeed  mov     r14d, r9d
0x14000eef0  mov     rcx, rbp; FastMutex
0x14000eef3  mov     ebx, r8d
0x14000eef6  mov     rdi, rdx
0x14000eef9  call    cs:__imp_ExAcquireFastMutex
0x14000ef00  nop     dword ptr [rax+rax+00h]
0x14000ef05  lea     r9, [rsp+38h+arg_0]
0x14000ef0a  mov     r8d, ebx
0x14000ef0d  mov     rdx, rdi
0x14000ef10  mov     rcx, rsi
0x14000ef13  call    ChpLookupGpadlByHandleLocked
0x14000ef18  test    eax, eax
0x14000ef1a  js      short loc_14000EF5B
0x14000ef1c  mov     rdx, [rsp+38h+arg_0]
0x14000ef21  mov     eax, [rdx+10h]
0x14000ef24  test    eax, eax
0x14000ef26  jz      short loc_14000EF2D
0x14000ef28  cmp     eax, 3
0x14000ef2b  jnz     short loc_14000EF5B
0x14000ef2d  mov     r8d, r14d
0x14000ef30  mov     rcx, rsi
0x14000ef33  call    ChpGpadlCreatedLocked
0x14000ef38  mov     rcx, rbp; FastMutex
0x14000ef3b  call    cs:__imp_ExReleaseFastMutex
0x14000ef42  nop     dword ptr [rax+rax+00h]
0x14000ef47  mov     rbx, [rsp+38h+arg_8]
0x14000ef4c  mov     rbp, [rsp+38h+arg_10]
0x14000ef51  add     rsp, 20h
0x14000ef55  pop     r14
0x14000ef57  pop     rdi
0x14000ef58  pop     rsi
0x14000ef59  retn
0x14000ef5b  mov     ecx, 3Ah ; ':'
0x14000ef60  int     29h; Win8: RtlFailFast(ecx)
```
