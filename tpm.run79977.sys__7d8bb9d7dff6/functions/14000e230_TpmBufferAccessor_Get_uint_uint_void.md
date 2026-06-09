# TpmBufferAccessor::Get<uint>(uint *,void *)

- ea: `0x14000e230`
- end: `0x14000e2a9`
- name: `??$Get@I@TpmBufferAccessor@@QEAAJPEAIPEAX@Z`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140005ae4`
- `0x1400116fc`
- `0x140016afc`
- `0x14002015c`
- `0x1400299ec`

## callees

- `0x14000e230`
- `0x14001a468`

## pseudocode

```c
__int64 __fastcall TpmBufferAccessor::Get<unsigned int>(__int64 a1, _BYTE *a2, void *a3)
{
  unsigned int v4; // ecx
  _BYTE *v5; // rcx
  __int64 result; // rax

  v4 = *(_DWORD *)(a1 + 16) - *(_DWORD *)a1;
  if ( v4 + 4 < v4 || (unsigned __int64)v4 + 4 > *(unsigned int *)(a1 + 8) )
    return 2147483653LL;
  v5 = (_BYTE *)(v4 + *(_QWORD *)a1);
  *a2 = v5[3];
  a2[1] = v5[2];
  a2[2] = v5[1];
  a2[3] = *v5;
  result = 0;
  if ( !a3 || (result = ShaHashData(a3, *(unsigned __int8 **)(a1 + 16), 4u), (int)result >= 0) )
    *(_QWORD *)(a1 + 16) += 4LL;
  return result;
}

```

## disassembly

```asm
0x14000e230  push    rbx
0x14000e232  sub     rsp, 20h
0x14000e236  mov     rbx, rcx
0x14000e239  mov     r10, r8
0x14000e23c  mov     ecx, [rcx+10h]
0x14000e23f  sub     ecx, [rbx]
0x14000e241  lea     eax, [rcx+4]
0x14000e244  cmp     eax, ecx
0x14000e246  jb      short loc_14000E28A
0x14000e248  mov     r9d, ecx
0x14000e24b  mov     ecx, [rbx+8]
0x14000e24e  lea     rax, [r9+4]
0x14000e252  cmp     rax, rcx
0x14000e255  ja      short loc_14000E28A
0x14000e257  mov     rcx, [rbx]
0x14000e25a  add     rcx, r9
0x14000e25d  movzx   eax, byte ptr [rcx+3]
0x14000e261  mov     [rdx], al
0x14000e263  movzx   eax, byte ptr [rcx+2]
0x14000e267  mov     [rdx+1], al
0x14000e26a  movzx   eax, byte ptr [rcx+1]
0x14000e26e  mov     [rdx+2], al
0x14000e271  movzx   eax, byte ptr [rcx]
0x14000e274  mov     [rdx+3], al
0x14000e277  xor     eax, eax
0x14000e279  test    r8, r8
0x14000e27c  jnz     short loc_14000E291
0x14000e27e  add     qword ptr [rbx+10h], 4
0x14000e283  add     rsp, 20h
0x14000e287  pop     rbx
0x14000e288  retn
0x14000e28a  mov     eax, 80000005h
0x14000e28f  jmp     short loc_14000E283
0x14000e291  mov     rdx, [rbx+10h]; unsigned __int8 *
0x14000e295  mov     r8d, 4; unsigned int
0x14000e29b  mov     rcx, r10; void *
0x14000e29e  call    ?ShaHashData@@YAJPEAXPEAEI@Z; ShaHashData(void *,uchar *,uint)
0x14000e2a3  test    eax, eax
0x14000e2a5  js      short loc_14000E283
0x14000e2a7  jmp     short loc_14000E27E
```
