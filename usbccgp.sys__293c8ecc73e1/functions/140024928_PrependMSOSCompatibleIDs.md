# PrependMSOSCompatibleIDs

- ea: `0x140024928`
- end: `0x1400249cc`
- name: `PrependMSOSCompatibleIDs`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400249d4`

## callees

- `0x140014e00`
- `0x14002231c`
- `0x140024928`
- `0x14002d610`

## pseudocode

```c
__int64 __fastcall PrependMSOSCompatibleIDs(__int64 a1)
{
  __int64 v1; // rdi
  int v2; // esi
  __int64 v3; // rax
  __int64 v4; // rbx
  const void *v5; // rdx
  unsigned int v6; // ebp
  unsigned int v8; // [rsp+40h] [rbp+8h] BYREF
  _BYTE *v9; // [rsp+48h] [rbp+10h] BYREF
  _BYTE *v10; // [rsp+50h] [rbp+18h] BYREF

  v1 = *(_QWORD *)(a1 + 240);
  v10 = 0;
  v9 = 0;
  v8 = 0;
  GetFunctionMSOSCompatibleIDs(a1, &v10, &v9);
  if ( *(_QWORD *)(v1 + 48) )
    v2 = *(unsigned __int16 *)(v1 + 40);
  else
    v2 = 0;
  v3 = BuildMSOSCompatibleIDs(v10, v9, v2, &v8);
  v4 = v3;
  if ( v3 )
  {
    v5 = *(const void **)(v1 + 48);
    v6 = v8;
    if ( v5 )
      memmove((void *)(v3 + 2 * ((unsigned __int64)v8 >> 1)), v5, *(unsigned __int16 *)(v1 + 40));
    *(_WORD *)(v4 + 2 * ((unsigned __int64)(v2 + v6) >> 1)) = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x140024928  mov     rax, rsp
0x14002492b  mov     [rax+20h], rbx
0x14002492f  push    rbp
0x140024930  push    rsi
0x140024931  push    rdi
0x140024932  sub     rsp, 20h
0x140024936  mov     rdi, [rcx+0F0h]
0x14002493d  lea     r8, [rax+10h]
0x140024941  lea     rdx, [rax+18h]
0x140024945  mov     qword ptr [rax+18h], 0
0x14002494d  mov     qword ptr [rax+10h], 0
0x140024955  mov     dword ptr [rax+8], 0
0x14002495c  call    GetFunctionMSOSCompatibleIDs
0x140024961  cmp     qword ptr [rdi+30h], 0
0x140024966  jz      short loc_14002496E
0x140024968  movzx   esi, word ptr [rdi+28h]
0x14002496c  jmp     short loc_140024970
0x14002496e  xor     esi, esi
0x140024970  mov     rdx, [rsp+38h+arg_8]
0x140024975  lea     r9, [rsp+38h+arg_0]
0x14002497a  mov     rcx, [rsp+38h+arg_10]
0x14002497f  mov     r8d, esi
0x140024982  call    BuildMSOSCompatibleIDs
0x140024987  mov     rbx, rax
0x14002498a  test    rax, rax
0x14002498d  jz      short loc_1400249BB
0x14002498f  mov     rdx, [rdi+30h]; Src
0x140024993  mov     ebp, [rsp+38h+arg_0]
0x140024997  test    rdx, rdx
0x14002499a  jz      short loc_1400249AF
0x14002499c  movzx   r8d, word ptr [rdi+28h]; Size
0x1400249a1  mov     ecx, ebp
0x1400249a3  shr     rcx, 1
0x1400249a6  lea     rcx, [rax+rcx*2]; void *
0x1400249aa  call    memmove
0x1400249af  lea     ecx, [rsi+rbp]
0x1400249b2  shr     rcx, 1
0x1400249b5  xor     eax, eax
0x1400249b7  mov     [rbx+rcx*2], ax
0x1400249bb  mov     rax, rbx
0x1400249be  mov     rbx, [rsp+38h+arg_18]
0x1400249c3  add     rsp, 20h
0x1400249c7  pop     rdi
0x1400249c8  pop     rsi
0x1400249c9  pop     rbp
0x1400249ca  retn
```
