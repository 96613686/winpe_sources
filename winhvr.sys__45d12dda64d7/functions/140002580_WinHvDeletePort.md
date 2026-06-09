# WinHvDeletePort

- ea: `0x140002580`
- end: `0x1400025aa`
- name: `WinHvDeletePort`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140002ce8`

## pseudocode

```c
__int64 __fastcall WinHvDeletePort(__int64 a1, int a2)
{
  __int64 v3; // [rsp+20h] [rbp-18h] BYREF
  int v4; // [rsp+28h] [rbp-10h]
  int v5; // [rsp+2Ch] [rbp-Ch]

  v5 = 0;
  v4 = a2;
  v3 = a1;
  return WinHvpFastHypercall(88, &v3);
}

```

## disassembly

```asm
0x140002580  mov     rax, rsp
0x140002583  sub     rsp, 38h
0x140002587  mov     qword ptr [rax-10h], 0
0x14000258f  mov     [rax-10h], edx
0x140002592  lea     rdx, [rax-18h]
0x140002596  mov     [rax-18h], rcx
0x14000259a  mov     ecx, 58h ; 'X'
0x14000259f  call    WinHvpFastHypercall
0x1400025a4  add     rsp, 38h
0x1400025a8  retn
```
