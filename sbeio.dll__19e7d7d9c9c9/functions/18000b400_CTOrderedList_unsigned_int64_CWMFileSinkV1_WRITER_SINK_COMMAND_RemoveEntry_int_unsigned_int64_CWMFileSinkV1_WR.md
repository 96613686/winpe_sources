# CTOrderedList<unsigned __int64,CWMFileSinkV1::WRITER_SINK_COMMAND *>::RemoveEntry(int,unsigned __int64 &,CWMFileSinkV1::WRITER_SINK_COMMAND * &)

- ea: `0x18000b400`
- end: `0x18000b472`
- name: `?RemoveEntry@?$CTOrderedList@_KPEAUWRITER_SINK_COMMAND@CWMFileSinkV1@@@@QEAAHHAEA_KAEAPEAUWRITER_SINK_COMMAND@CWMFileSinkV1@@@Z`
- size: `114`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007bd8`
- `0x18000a750`
- `0x18000afa0`

## callees

- `0x18000b400`

## pseudocode

```c
__int64 __fastcall CTOrderedList<unsigned __int64,CWMFileSinkV1::WRITER_SINK_COMMAND *>::RemoveEntry(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4)
{
  _QWORD *v4; // rdx
  __int64 result; // rax
  __int64 v6; // r8
  __int64 v7; // r8

  v4 = *(_QWORD **)a1;
  if ( !*(_QWORD *)a1 )
    return 0;
  if ( *(_QWORD **)(a1 + 16) == v4 )
    *(_QWORD *)(a1 + 16) = 0;
  *a3 = *v4;
  *a4 = v4[1];
  if ( v4 == *(_QWORD **)(a1 + 8) )
    *(_QWORD *)(a1 + 8) = v4[3];
  *(_QWORD *)a1 = v4[2];
  v6 = v4[2];
  if ( v6 )
    *(_QWORD *)(v6 + 24) = v4[3];
  v7 = v4[3];
  if ( v7 )
    *(_QWORD *)(v7 + 16) = v4[2];
  v4[2] = *(_QWORD *)(a1 + 32);
  result = 1;
  *(_QWORD *)(a1 + 32) = v4;
  --*(_DWORD *)(a1 + 24);
  return result;
}

```

## disassembly

```asm
0x18000b400  mov     rdx, [rcx]
0x18000b403  test    rdx, rdx
0x18000b406  jnz     short loc_18000B40B
0x18000b408  xor     eax, eax
0x18000b40a  retn
0x18000b40b  cmp     [rcx+10h], rdx
0x18000b40f  jnz     short loc_18000B419
0x18000b411  mov     qword ptr [rcx+10h], 0
0x18000b419  mov     rax, [rdx]
0x18000b41c  mov     [r8], rax
0x18000b41f  mov     rax, [rdx+8]
0x18000b423  mov     [r9], rax
0x18000b426  cmp     rdx, [rcx+8]
0x18000b42a  jnz     short loc_18000B434
0x18000b42c  mov     rax, [rdx+18h]
0x18000b430  mov     [rcx+8], rax
0x18000b434  mov     rax, [rdx+10h]
0x18000b438  mov     [rcx], rax
0x18000b43b  mov     r8, [rdx+10h]
0x18000b43f  test    r8, r8
0x18000b442  jz      short loc_18000B44C
0x18000b444  mov     rax, [rdx+18h]
0x18000b448  mov     [r8+18h], rax
0x18000b44c  mov     r8, [rdx+18h]
0x18000b450  test    r8, r8
0x18000b453  jz      short loc_18000B45D
0x18000b455  mov     rax, [rdx+10h]
0x18000b459  mov     [r8+10h], rax
0x18000b45d  mov     rax, [rcx+20h]
0x18000b461  mov     [rdx+10h], rax
0x18000b465  mov     eax, 1
0x18000b46a  mov     [rcx+20h], rdx
0x18000b46e  dec     dword ptr [rcx+18h]
0x18000b471  retn
```
