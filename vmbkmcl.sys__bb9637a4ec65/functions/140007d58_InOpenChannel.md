# InOpenChannel

- ea: `0x140007d58`
- end: `0x140007e28`
- name: `InOpenChannel`
- size: `208`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14000b3d8`
- `0x14001cdd4`

## callees

- `0x140007914`
- `0x140007d58`
- `0x140008b48`
- `0x140011ed0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140007dac`
- `ntoskrnl!ExAllocatePool2` at `0x140007dac`

## pseudocode

```c
__int64 __fastcall InOpenChannel(__int64 *a1)
{
  __int64 v1; // rbp
  _QWORD *v3; // rsi
  int v4; // edi
  _QWORD *Pool2; // rax
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF

  v1 = *a1;
  v7 = 0;
  v3 = (_QWORD *)(v1 + 2368);
  if ( *(_BYTE *)(v1 + 1728) )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(v1 + 2584))(*v3, &v7);
    if ( v4 < 0 )
      goto LABEL_5;
    Pool2 = (_QWORD *)ExAllocatePool2(64, (unsigned int)(v7 + 16), 1668115286);
    a1[178] = (__int64)Pool2;
    if ( !Pool2 )
    {
      v4 = -1073741670;
      goto LABEL_5;
    }
    *Pool2 = a1;
    *((_BYTE *)a1 + 1432) = BYTE4(v7);
  }
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(v1 + 2544))(*v3, *(_QWORD *)(*a1 + 3264), a1 + 203);
  if ( v4 >= 0 )
  {
    v4 = InpReacquirePacketAllocationResources(a1, *((unsigned int *)a1 + 362));
    if ( v4 >= 0 )
      return 0;
  }
LABEL_5:
  InCloseChannel(a1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140007d58  push    rbx
0x140007d5a  push    rbp
0x140007d5b  push    rsi
0x140007d5c  push    rdi
0x140007d5d  sub     rsp, 28h
0x140007d61  mov     rbp, [rcx]
0x140007d64  mov     rbx, rcx
0x140007d67  mov     [rsp+48h+arg_0], 0
0x140007d70  cmp     byte ptr [rbp+6C0h], 0
0x140007d77  lea     rsi, [rbp+940h]
0x140007d7e  jz      short loc_140007DEA
0x140007d80  mov     rax, [rbp+0A18h]
0x140007d87  lea     rdx, [rsp+48h+arg_0]
0x140007d8c  mov     rcx, [rsi]
0x140007d8f  call    _guard_dispatch_icall
0x140007d94  mov     edi, eax
0x140007d96  test    eax, eax
0x140007d98  js      short loc_140007DC9
0x140007d9a  mov     edx, dword ptr [rsp+48h+arg_0]
0x140007d9e  mov     ecx, 40h ; '@'
0x140007da3  add     edx, 10h
0x140007da6  mov     r8d, 636D6B56h
0x140007dac  call    cs:__imp_ExAllocatePool2
0x140007db3  nop     dword ptr [rax+rax+00h]
0x140007db8  mov     [rbx+590h], rax
0x140007dbf  test    rax, rax
0x140007dc2  jnz     short loc_140007DDD
0x140007dc4  mov     edi, 0C000009Ah
0x140007dc9  mov     rcx, rbx
0x140007dcc  call    InCloseChannel
0x140007dd1  mov     eax, edi
0x140007dd3  add     rsp, 28h
0x140007dd7  pop     rdi
0x140007dd8  pop     rsi
0x140007dd9  pop     rbp
0x140007dda  pop     rbx
0x140007ddb  retn
0x140007ddd  mov     [rax], rbx
0x140007de0  mov     al, byte ptr [rsp+48h+arg_0+4]
0x140007de4  mov     [rbx+598h], al
0x140007dea  mov     rdx, [rbx]
0x140007ded  lea     r8, [rbx+658h]
0x140007df4  mov     rax, [rbp+9F0h]
0x140007dfb  mov     rcx, [rsi]
0x140007dfe  mov     rdx, [rdx+0CC0h]
0x140007e05  call    _guard_dispatch_icall
0x140007e0a  mov     edi, eax
0x140007e0c  test    eax, eax
0x140007e0e  js      short loc_140007DC9
0x140007e10  mov     edx, [rbx+5A8h]
0x140007e16  mov     rcx, rbx
0x140007e19  call    InpReacquirePacketAllocationResources
0x140007e1e  mov     edi, eax
0x140007e20  test    eax, eax
0x140007e22  js      short loc_140007DC9
0x140007e24  xor     edi, edi
0x140007e26  jmp     short loc_140007DD1
```
