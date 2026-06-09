# VmbChannelCreateGpadlFromBuffer

- ea: `0x14000fb50`
- end: `0x14000fba6`
- name: `VmbChannelCreateGpadlFromBuffer`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000fb50`
- `0x140011ed0`

## pseudocode

```c
__int64 __fastcall VmbChannelCreateGpadlFromBuffer(__int64 a1, char a2, __int64 a3, unsigned int a4, __int64 a5)
{
  __int64 result; // rax

  result = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, __int64))(a1 + 2424))(
             *(_QWORD *)(a1 + 2368),
             a3,
             a4,
             2 * (unsigned int)((a2 & 1) == 0),
             a5);
  if ( (int)result >= 0 )
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 2816));
  return result;
}

```

## disassembly

```asm
0x14000fb50  mov     [rsp+arg_0], rbx
0x14000fb55  push    rdi
0x14000fb56  sub     rsp, 30h
0x14000fb5a  mov     rax, [rcx+978h]
0x14000fb61  not     edx
0x14000fb63  mov     r10, [rsp+38h+arg_20]
0x14000fb68  and     edx, 1
0x14000fb6b  mov     r11d, r9d
0x14000fb6e  mov     [rsp+38h+var_18], r10
0x14000fb73  mov     rbx, r8
0x14000fb76  mov     rdi, rcx
0x14000fb79  mov     rcx, [rcx+940h]
0x14000fb80  mov     r8d, r11d
0x14000fb83  lea     r9d, [rdx+rdx]
0x14000fb87  mov     rdx, rbx
0x14000fb8a  call    _guard_dispatch_icall
0x14000fb8f  test    eax, eax
0x14000fb91  js      short loc_14000FB9A
0x14000fb93  lock inc dword ptr [rdi+0B00h]
0x14000fb9a  mov     rbx, [rsp+38h+arg_0]
0x14000fb9f  add     rsp, 30h
0x14000fba3  pop     rdi
0x14000fba4  retn
```
