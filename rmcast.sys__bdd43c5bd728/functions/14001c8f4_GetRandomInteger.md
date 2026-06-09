# GetRandomInteger

- ea: `0x14001c8f4`
- end: `0x14001c93c`
- name: `GetRandomInteger`
- size: `72`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ca08`
- `0x14000d414`
- `0x14000e03c`
- `0x140013d90`

## callees

- `0x14001c878`
- `0x14001c8f4`

## pseudocode

```c
__int64 __fastcall GetRandomInteger(unsigned int a1, unsigned int a2)
{
  unsigned int v5; // [rsp+30h] [rbp+8h] BYREF

  v5 = 0;
  if ( a1 >= a2 )
    return a1;
  GetRandomData((__int64)&v5, 4u);
  return a1 + v5 % (a2 - a1 + 1);
}

```

## disassembly

```asm
0x14001c8f4  mov     [rsp+arg_8], rbx
0x14001c8f9  push    rdi
0x14001c8fa  sub     rsp, 20h
0x14001c8fe  mov     [rsp+28h+arg_0], 0
0x14001c906  mov     edi, edx
0x14001c908  mov     ebx, ecx
0x14001c90a  cmp     ecx, edx
0x14001c90c  jb      short loc_14001C912
0x14001c90e  mov     eax, ecx
0x14001c910  jmp     short loc_14001C930
0x14001c912  mov     edx, 4
0x14001c917  lea     rcx, [rsp+28h+arg_0]
0x14001c91c  call    GetRandomData
0x14001c921  mov     eax, [rsp+28h+arg_0]
0x14001c925  sub     edi, ebx
0x14001c927  xor     edx, edx
0x14001c929  inc     edi
0x14001c92b  div     edi
0x14001c92d  lea     eax, [rbx+rdx]
0x14001c930  mov     rbx, [rsp+28h+arg_8]
0x14001c935  add     rsp, 20h
0x14001c939  pop     rdi
0x14001c93a  retn
```
