# UdfFindNameLink

- ea: `0x140056040`
- end: `0x140056103`
- name: `UdfFindNameLink`
- size: `195`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000a08c`
- `0x140044950`

## callees

- `0x140056040`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140056083`
- `ntoskrnl!RtlCompareMemory` at `0x140056083`
- `ntoskrnl!RtlSplay` at `0x1400560d3`
- `ntoskrnl!RtlSplay` at `0x1400560d3`

## pseudocode

```c
__int64 __fastcall UdfFindNameLink(__int64 a1, PRTL_SPLAY_LINKS *a2, const void **a3, unsigned int a4)
{
  PRTL_SPLAY_LINKS v4; // rbx
  __int64 v6; // rbp
  unsigned __int16 Parent; // r9
  unsigned int Parent_low; // esi
  int v10; // edi
  unsigned int v11; // eax

  v4 = *a2;
  v6 = a4;
  while ( v4 )
  {
    Parent = (unsigned __int16)v4[1].Parent;
    if ( Parent <= *(_WORD *)a3 )
    {
      v10 = -1;
      Parent_low = LOWORD(v4[1].Parent);
      if ( Parent == *(_WORD *)a3 )
        v10 = 0;
    }
    else
    {
      Parent_low = *(unsigned __int16 *)a3;
      v10 = 1;
    }
    v11 = RtlCompareMemory(v4[1].LeftChild, a3[1], Parent_low);
    if ( v11 < Parent_low )
      v10 = *((_WORD *)&v4[1].LeftChild->Parent + ((unsigned __int64)v11 >> 1)) < *((_WORD *)a3[1]
                                                                                  + ((unsigned __int64)v11 >> 1))
          ? -1
          : 1;
    if ( v10 == 1 )
    {
      v4 = v4->LeftChild;
    }
    else
    {
      if ( v10 != -1 )
      {
        *a2 = RtlSplay(v4);
        return (__int64)v4 - v6;
      }
      v4 = v4->RightChild;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140056040  push    rbx
0x140056042  push    rbp
0x140056043  push    rsi
0x140056044  push    rdi
0x140056045  push    r14
0x140056047  push    r15
0x140056049  sub     rsp, 28h
0x14005604d  mov     rbx, [rdx]
0x140056050  mov     r14, r8
0x140056053  mov     ebp, r9d
0x140056056  mov     r15, rdx
0x140056059  test    rbx, rbx
0x14005605c  jz      loc_1400560FF
0x140056062  movzx   r9d, word ptr [rbx+18h]
0x140056067  movzx   ecx, word ptr [r14]
0x14005606b  cmp     r9w, cx
0x14005606f  jbe     short loc_1400560BF
0x140056071  mov     esi, ecx
0x140056073  mov     edi, 1
0x140056078  mov     rdx, [r14+8]; Source2
0x14005607c  mov     rcx, [rbx+20h]; Source1
0x140056080  mov     r8d, esi; Length
0x140056083  call    cs:__imp_RtlCompareMemory
0x14005608a  nop     dword ptr [rax+rax+00h]
0x14005608f  cmp     eax, esi
0x140056091  jnb     short loc_1400560AF
0x140056093  mov     rcx, [rbx+20h]
0x140056097  mov     edx, eax
0x140056099  mov     rax, [r14+8]
0x14005609d  shr     rdx, 1
0x1400560a0  movzx   eax, word ptr [rax+rdx*2]
0x1400560a4  cmp     [rcx+rdx*2], ax
0x1400560a8  sbb     edi, edi
0x1400560aa  and     edi, 0FFFFFFFEh
0x1400560ad  inc     edi
0x1400560af  cmp     edi, 1
0x1400560b2  jz      short loc_1400560F6
0x1400560b4  cmp     edi, 0FFFFFFFFh
0x1400560b7  jnz     short loc_1400560D0
0x1400560b9  mov     rbx, [rbx+10h]
0x1400560bd  jmp     short loc_140056059
0x1400560bf  or      edi, 0FFFFFFFFh
0x1400560c2  xor     eax, eax
0x1400560c4  cmp     r9w, cx
0x1400560c8  mov     esi, r9d
0x1400560cb  cmovz   edi, eax
0x1400560ce  jmp     short loc_140056078
0x1400560d0  mov     rcx, rbx; Links
0x1400560d3  call    cs:__imp_RtlSplay
0x1400560da  nop     dword ptr [rax+rax+00h]
0x1400560df  sub     rbx, rbp
0x1400560e2  mov     [r15], rax
0x1400560e5  mov     rax, rbx
0x1400560e8  add     rsp, 28h
0x1400560ec  pop     r15
0x1400560ee  pop     r14
0x1400560f0  pop     rdi
0x1400560f1  pop     rsi
0x1400560f2  pop     rbp
0x1400560f3  pop     rbx
0x1400560f4  retn
0x1400560f6  mov     rbx, [rbx+8]
0x1400560fa  jmp     loc_140056059
0x1400560ff  xor     eax, eax
0x140056101  jmp     short loc_1400560E8
```
