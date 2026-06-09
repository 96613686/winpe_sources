# MvmpReceiveMessageSynchronous

- ea: `0x14000e880`
- end: `0x14000e8e3`
- name: `MvmpReceiveMessageSynchronous`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000dce0`
- `0x14000dd98`
- `0x14000dde8`
- `0x14000df90`

## callees

- `0x140003450`
- `0x14000b3e0`
- `0x14000e008`
- `0x14000e880`

## pseudocode

```c
char __fastcall MvmpReceiveMessageSynchronous(__int64 a1, int a2, __int64 a3)
{
  unsigned __int64 v5; // rbx
  size_t v7; // rax

  v5 = *(_QWORD *)(a1 + 32) + ((unsigned __int64)*(unsigned int *)(a1 + 92) << 8);
  while ( !*(_DWORD *)v5 )
    MvmStall();
  v7 = *(unsigned __int8 *)(v5 + 4);
  *(_DWORD *)a3 = v7;
  if ( (unsigned int)v7 > 0xF0 )
    __fastfail(0x3Au);
  RtlCopyDeviceMemory((char *)(a3 + 4), (char *)(v5 + 16), v7);
  return MvmpCompleteMessage(a1, a2);
}

```

## disassembly

```asm
0x14000e880  push    rbx
0x14000e882  push    rbp
0x14000e883  push    rsi
0x14000e884  push    rdi
0x14000e885  sub     rsp, 28h
0x14000e889  mov     ebx, [rcx+5Ch]
0x14000e88c  mov     rdi, r8
0x14000e88f  shl     rbx, 8
0x14000e893  mov     rbp, rdx
0x14000e896  add     rbx, [rcx+20h]
0x14000e89a  mov     rsi, rcx
0x14000e89d  jmp     short loc_14000E8A4
0x14000e89f  call    MvmStall
0x14000e8a4  mov     eax, [rbx]
0x14000e8a6  test    eax, eax
0x14000e8a8  jz      short loc_14000E89F
0x14000e8aa  movzx   eax, byte ptr [rbx+4]
0x14000e8ae  mov     [rdi], eax
0x14000e8b0  cmp     eax, 0F0h
0x14000e8b5  jbe     short loc_14000E8BE
0x14000e8b7  mov     ecx, 3Ah ; ':'
0x14000e8bc  int     29h; Win8: RtlFailFast(ecx)
0x14000e8be  mov     r8, rax
0x14000e8c1  lea     rdx, [rbx+10h]
0x14000e8c5  lea     rcx, [rdi+4]; void *
0x14000e8c9  call    RtlCopyDeviceMemory
0x14000e8ce  mov     rdx, rbp
0x14000e8d1  mov     rcx, rsi
0x14000e8d4  call    MvmpCompleteMessage
0x14000e8d9  add     rsp, 28h
0x14000e8dd  pop     rdi
0x14000e8de  pop     rsi
0x14000e8df  pop     rbp
0x14000e8e0  pop     rbx
0x14000e8e1  retn
```
