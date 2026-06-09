# OutpCompletePacketListToClient

- ea: `0x1400068c0`
- end: `0x14000691a`
- name: `OutpCompletePacketListToClient`
- size: `90`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400064a0`
- `0x1400065a0`
- `0x140009d8c`

## callees

- `0x140004860`
- `0x1400068c0`
- `0x140011ed0`

## pseudocode

```c
void __fastcall OutpCompletePacketListToClient(_QWORD *a1)
{
  _QWORD *v2; // rcx
  __int64 v3; // rax

  while ( 1 )
  {
    v2 = (_QWORD *)*a1;
    if ( (_QWORD *)*a1 == a1 )
      break;
    if ( (_QWORD *)v2[1] != a1 || (v3 = *v2, *(_QWORD **)(*v2 + 8LL) != v2) )
      __fastfail(3u);
    *a1 = v3;
    *(_QWORD *)(v3 + 8) = a1;
    if ( *((_DWORD *)v2 + 4) == 2 )
      ((void (*)(void))v2[4])();
    else
      OutCompletePacketToClient((__int64)(v2 - 18), *((unsigned int *)v2 + 6), 0);
  }
}

```

## disassembly

```asm
0x1400068c0  push    rbx
0x1400068c2  sub     rsp, 20h
0x1400068c6  mov     rbx, rcx
0x1400068c9  mov     rcx, [rbx]
0x1400068cc  cmp     rcx, rbx
0x1400068cf  jz      short loc_140006913
0x1400068d1  cmp     [rcx+8], rbx
0x1400068d5  jnz     short loc_14000690C
0x1400068d7  mov     rax, [rcx]
0x1400068da  cmp     [rax+8], rcx
0x1400068de  jnz     short loc_14000690C
0x1400068e0  mov     [rbx], rax
0x1400068e3  mov     [rax+8], rbx
0x1400068e7  cmp     dword ptr [rcx+10h], 2
0x1400068eb  jnz     short loc_1400068F8
0x1400068ed  mov     rax, [rcx+20h]
0x1400068f1  call    _guard_dispatch_icall
0x1400068f6  jmp     short loc_1400068C9
0x1400068f8  mov     edx, [rcx+18h]
0x1400068fb  add     rcx, 0FFFFFFFFFFFFFF70h
0x140006902  xor     r8d, r8d
0x140006905  call    OutCompletePacketToClient
0x14000690a  jmp     short loc_1400068C9
0x14000690c  mov     ecx, 3
0x140006911  int     29h; Win8: RtlFailFast(ecx)
0x140006913  add     rsp, 20h
0x140006917  pop     rbx
0x140006918  retn
```
