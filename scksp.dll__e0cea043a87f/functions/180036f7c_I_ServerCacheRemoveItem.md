# I_ServerCacheRemoveItem

- ea: `0x180036f7c`
- end: `0x180037000`
- name: `I_ServerCacheRemoveItem`
- size: `132`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180037120`
- `0x180037730`
- `0x180037a4c`

## callees

- `0x180036ef4`
- `0x180036f7c`
- `0x18003833c`

## pseudocode

```c
__int64 __fastcall I_ServerCacheRemoveItem(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // eax
  unsigned int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rcx

  --*(_DWORD *)(a1 + 84);
  v3 = *(_DWORD *)(a1 + 80);
  if ( v3 < *(_DWORD *)(a2 + 8) )
    v5 = 0;
  else
    v5 = v3 - *(_DWORD *)(a2 + 8);
  *(_DWORD *)(a1 + 80) = v5;
  if ( *(_QWORD *)(a1 + 64) == a2 )
    *(_QWORD *)(a1 + 64) = *(_QWORD *)(a2 + 56);
  if ( *(_QWORD *)(a1 + 72) == a2 )
    *(_QWORD *)(a1 + 72) = *(_QWORD *)(a2 + 48);
  v6 = *(_QWORD *)(a2 + 56);
  if ( v6 )
    *(_QWORD *)(v6 + 48) = *(_QWORD *)(a2 + 48);
  v7 = *(_QWORD *)(a2 + 48);
  if ( v7 )
    *(_QWORD *)(v7 + 56) = *(_QWORD *)(a2 + 56);
  CacheDeleteItem(*(_QWORD *)(a1 + 40), a3);
  return I_ServerCacheFreeItem(a1);
}

```

## disassembly

```asm
0x180036f7c  mov     [rsp+arg_0], rbx
0x180036f81  push    rdi
0x180036f82  sub     rsp, 20h
0x180036f86  dec     dword ptr [rcx+54h]
0x180036f89  mov     rbx, rdx
0x180036f8c  mov     eax, [rcx+50h]
0x180036f8f  mov     rdi, rcx
0x180036f92  cmp     eax, [rdx+8]
0x180036f95  jb      short loc_180036F9C
0x180036f97  sub     eax, [rdx+8]
0x180036f9a  jmp     short loc_180036F9E
0x180036f9c  xor     eax, eax
0x180036f9e  mov     [rcx+50h], eax
0x180036fa1  cmp     [rcx+40h], rbx
0x180036fa5  jnz     short loc_180036FAF
0x180036fa7  mov     rax, [rdx+38h]
0x180036fab  mov     [rcx+40h], rax
0x180036faf  cmp     [rcx+48h], rbx
0x180036fb3  jnz     short loc_180036FBD
0x180036fb5  mov     rax, [rdx+30h]
0x180036fb9  mov     [rcx+48h], rax
0x180036fbd  mov     rcx, [rdx+38h]
0x180036fc1  test    rcx, rcx
0x180036fc4  jz      short loc_180036FCE
0x180036fc6  mov     rax, [rdx+30h]
0x180036fca  mov     [rcx+30h], rax
0x180036fce  mov     rcx, [rdx+30h]
0x180036fd2  test    rcx, rcx
0x180036fd5  jz      short loc_180036FDF
0x180036fd7  mov     rax, [rdx+38h]
0x180036fdb  mov     [rcx+38h], rax
0x180036fdf  mov     rcx, [rdi+28h]
0x180036fe3  mov     rdx, r8
0x180036fe6  call    CacheDeleteItem
0x180036feb  mov     rdx, rbx
0x180036fee  mov     rcx, rdi
0x180036ff1  mov     rbx, [rsp+28h+arg_0]
0x180036ff6  add     rsp, 20h
0x180036ffa  pop     rdi
0x180036ffb  jmp     I_ServerCacheFreeItem
```
