# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::~_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>(void)

- ea: `0x18001de54`
- end: `0x18001ded3`
- name: `??1?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA@XZ`
- size: `127`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001de10`
- `0x18001df44`

## callees

- `0x18001de54`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001de6c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001dea6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001de6c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001dea6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001dec7`

## pseudocode

```c
void __fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::~_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>(
        __int64 a1)
{
  void *v2; // rcx
  _QWORD *v3; // rdx
  _QWORD *v4; // rcx
  _QWORD *v5; // rbx

  v2 = *(void **)(a1 + 16);
  if ( v2 )
  {
    operator delete(v2);
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_QWORD *)(a1 + 32) = 0;
  }
  v3 = **(_QWORD ***)a1;
  **(_QWORD **)a1 = *(_QWORD *)a1;
  *(_QWORD *)(*(_QWORD *)a1 + 8LL) = *(_QWORD *)a1;
  v4 = *(_QWORD **)a1;
  *(_QWORD *)(a1 + 8) = 0;
  if ( v3 != v4 )
  {
    do
    {
      v5 = (_QWORD *)*v3;
      operator delete(v3);
      v4 = *(_QWORD **)a1;
      v3 = v5;
    }
    while ( v5 != *(_QWORD **)a1 );
  }
  operator delete(v4);
}

```

## disassembly

```asm
0x18001de54  mov     [rsp+arg_0], rbx
0x18001de59  push    rdi
0x18001de5a  sub     rsp, 20h
0x18001de5e  mov     rdi, rcx
0x18001de61  xor     ebx, ebx
0x18001de63  mov     rcx, [rcx+10h]
0x18001de67  test    rcx, rcx
0x18001de6a  jz      short loc_18001DE84
0x18001de6c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001de73  nop     dword ptr [rax+rax+00h]
0x18001de78  mov     [rdi+10h], rbx
0x18001de7c  mov     [rdi+18h], rbx
0x18001de80  mov     [rdi+20h], rbx
0x18001de84  mov     rax, [rdi]
0x18001de87  mov     rdx, [rax]
0x18001de8a  mov     [rax], rax
0x18001de8d  mov     rax, [rdi]
0x18001de90  mov     [rax+8], rax
0x18001de94  mov     rcx, [rdi]
0x18001de97  mov     [rdi+8], rbx
0x18001de9b  cmp     rdx, rcx
0x18001de9e  jz      short loc_18001DEBD
0x18001dea0  mov     rbx, [rdx]
0x18001dea3  mov     rcx, rdx
0x18001dea6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001dead  nop     dword ptr [rax+rax+00h]
0x18001deb2  mov     rcx, [rdi]
0x18001deb5  mov     rdx, rbx
0x18001deb8  cmp     rbx, rcx
0x18001debb  jnz     short loc_18001DEA0
0x18001debd  mov     rbx, [rsp+28h+arg_0]
0x18001dec2  add     rsp, 20h
0x18001dec6  pop     rdi
0x18001dec7  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
