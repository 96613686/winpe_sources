# std::_Uninit_move<uchar *,uchar *,AlignedStore::AlignedAllocator<uchar,16>,uchar>(uchar *,uchar *,uchar *,std::_Wrap_alloc<AlignedStore::AlignedAllocator<uchar,16>> &,uchar *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x1800040cc`
- end: `0x1800040ea`
- name: `??$_Uninit_move@PEAEPEAEV?$AlignedAllocator@E$0BA@@AlignedStore@@E@std@@YAPEAEPEAE00AEAU?$_Wrap_alloc@V?$AlignedAllocator@E$0BA@@AlignedStore@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bba4`

## callees

- `0x1800040cc`

## pseudocode

```c
_BYTE *__fastcall std::_Uninit_move<unsigned char *,unsigned char *,AlignedStore::AlignedAllocator<unsigned char,16>,unsigned char>(
        _BYTE *a1,
        _BYTE *a2,
        _BYTE *a3)
{
  while ( a1 != a2 )
    *a3++ = *a1++;
  return a3;
}

```

## disassembly

```asm
0x1800040cc  sub     rsp, 28h
0x1800040d0  jmp     short loc_1800040DD
0x1800040d2  mov     al, [rcx]
0x1800040d4  mov     [r8], al
0x1800040d7  inc     r8
0x1800040da  inc     rcx
0x1800040dd  cmp     rcx, rdx
0x1800040e0  jnz     short loc_1800040D2
0x1800040e2  mov     rax, r8
0x1800040e5  add     rsp, 28h
0x1800040e9  retn
```
