# TpmBufferAccessor::Get<ushort>(ushort *,void *)

- ea: `0x14000f410`
- end: `0x14000f47c`
- name: `??$Get@G@TpmBufferAccessor@@QEAAJPEAGPEAX@Z`
- size: `108`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140005ae4`
- `0x1400116fc`
- `0x140015214`
- `0x140016afc`
- `0x14002015c`
- `0x1400299ec`

## callees

- `0x14000f410`
- `0x14001a468`

## pseudocode

```c
__int64 __fastcall TpmBufferAccessor::Get<unsigned short>(__int64 *a1, _BYTE *a2, void *a3)
{
  unsigned int v4; // ecx
  __int64 v5; // r9
  __int64 v6; // rcx
  __int64 result; // rax

  v4 = *((_DWORD *)a1 + 4) - *(_DWORD *)a1;
  if ( v4 + 2 < v4 )
    return 2147483653LL;
  v5 = v4;
  if ( (unsigned __int64)v4 + 2 > *((unsigned int *)a1 + 2) )
    return 2147483653LL;
  v6 = *a1;
  *a2 = *(_BYTE *)(*a1 + v5 + 1);
  a2[1] = *(_BYTE *)(v6 + v5);
  result = 0;
  if ( !a3 || (result = ShaHashData(a3, (unsigned __int8 *)a1[2], 2u), (int)result >= 0) )
    a1[2] += 2;
  return result;
}

```

## disassembly

```asm
0x14000f410  push    rbx
0x14000f412  sub     rsp, 20h
0x14000f416  mov     rbx, rcx
0x14000f419  mov     r10, r8
0x14000f41c  mov     ecx, [rcx+10h]
0x14000f41f  sub     ecx, [rbx]
0x14000f421  lea     eax, [rcx+2]
0x14000f424  cmp     eax, ecx
0x14000f426  jb      short loc_14000F475
0x14000f428  mov     r9d, ecx
0x14000f42b  mov     ecx, [rbx+8]
0x14000f42e  lea     rax, [r9+2]
0x14000f432  cmp     rax, rcx
0x14000f435  ja      short loc_14000F475
0x14000f437  mov     rcx, [rbx]
0x14000f43a  movzx   eax, byte ptr [rcx+r9+1]
0x14000f440  mov     [rdx], al
0x14000f442  movzx   eax, byte ptr [rcx+r9]
0x14000f447  mov     [rdx+1], al
0x14000f44a  xor     eax, eax
0x14000f44c  test    r8, r8
0x14000f44f  jnz     short loc_14000F45D
0x14000f451  add     qword ptr [rbx+10h], 2
0x14000f456  add     rsp, 20h
0x14000f45a  pop     rbx
0x14000f45b  retn
0x14000f45d  mov     rdx, [rbx+10h]; unsigned __int8 *
0x14000f461  mov     r8d, 2; unsigned int
0x14000f467  mov     rcx, r10; void *
0x14000f46a  call    ?ShaHashData@@YAJPEAXPEAEI@Z; ShaHashData(void *,uchar *,uint)
0x14000f46f  test    eax, eax
0x14000f471  js      short loc_14000F456
0x14000f473  jmp     short loc_14000F451
0x14000f475  mov     eax, 80000005h
0x14000f47a  jmp     short loc_14000F456
```
