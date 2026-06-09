# VmbChannelCreateGpadlFromMdl

- ea: `0x14000fbb0`
- end: `0x14000fbf9`
- name: `VmbChannelCreateGpadlFromMdl`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000fbb0`
- `0x140011ed0`

## pseudocode

```c
__int64 __fastcall VmbChannelCreateGpadlFromMdl(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6)
{
  __int64 result; // rax

  result = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, __int64))(a1 + 2440))(
             *(_QWORD *)(a1 + 2368),
             a3,
             a4,
             a5,
             a6);
  if ( (int)result >= 0 )
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 2816));
  return result;
}

```

## disassembly

```asm
0x14000fbb0  push    rbx
0x14000fbb2  sub     rsp, 30h
0x14000fbb6  mov     rdx, [rsp+38h+arg_28]
0x14000fbbb  mov     r10d, r9d
0x14000fbbe  mov     rax, [rcx+988h]
0x14000fbc5  mov     r11, r8
0x14000fbc8  mov     r9d, [rsp+38h+arg_20]
0x14000fbcd  mov     rbx, rcx
0x14000fbd0  mov     rcx, [rcx+940h]
0x14000fbd7  mov     r8d, r10d
0x14000fbda  mov     [rsp+38h+var_18], rdx
0x14000fbdf  mov     rdx, r11
0x14000fbe2  call    _guard_dispatch_icall
0x14000fbe7  test    eax, eax
0x14000fbe9  js      short loc_14000FBF2
0x14000fbeb  lock inc dword ptr [rbx+0B00h]
0x14000fbf2  add     rsp, 30h
0x14000fbf6  pop     rbx
0x14000fbf7  retn
```
