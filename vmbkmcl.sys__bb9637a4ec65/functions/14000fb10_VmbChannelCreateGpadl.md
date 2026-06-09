# VmbChannelCreateGpadl

- ea: `0x14000fb10`
- end: `0x14000fb44`
- name: `VmbChannelCreateGpadl`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000fb10`
- `0x140011ed0`

## pseudocode

```c
__int64 __fastcall VmbChannelCreateGpadl(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  __int64 result; // rax

  result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(a1 + 2416))(*(_QWORD *)(a1 + 2368), a3, a4);
  if ( (int)result >= 0 )
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 2816));
  return result;
}

```

## disassembly

```asm
0x14000fb10  push    rbx
0x14000fb12  sub     rsp, 20h
0x14000fb16  mov     rax, [rcx+970h]
0x14000fb1d  mov     edx, r8d
0x14000fb20  mov     rbx, rcx
0x14000fb23  mov     r8, r9
0x14000fb26  mov     rcx, [rcx+940h]
0x14000fb2d  call    _guard_dispatch_icall
0x14000fb32  test    eax, eax
0x14000fb34  js      short loc_14000FB3D
0x14000fb36  lock inc dword ptr [rbx+0B00h]
0x14000fb3d  add     rsp, 20h
0x14000fb41  pop     rbx
0x14000fb42  retn
```
