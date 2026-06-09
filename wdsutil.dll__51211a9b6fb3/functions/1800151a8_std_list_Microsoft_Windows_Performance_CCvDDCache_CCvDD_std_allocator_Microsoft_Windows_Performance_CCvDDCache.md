# std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::~list<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>(void)

- ea: `0x1800151a8`
- end: `0x18001521b`
- name: `??1?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAA@XZ`
- size: `115`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800154a8`
- `0x180015590`
- `0x18003274f`

## callees

- `0x1800151a8`
- `0x1800153c4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800151e9`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800151e9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001520f`

## pseudocode

```c
void __fastcall std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::~list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>(
        __int64 a1)
{
  _QWORD *v2; // rsi
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx

  v2 = **(_QWORD ***)a1;
  **(_QWORD **)a1 = *(_QWORD *)a1;
  *(_QWORD *)(*(_QWORD *)a1 + 8LL) = *(_QWORD *)a1;
  *(_QWORD *)(a1 + 8) = 0;
  v3 = *(_QWORD **)a1;
  if ( v2 != v3 )
  {
    do
    {
      v4 = (_QWORD *)*v2;
      Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD((Microsoft::Windows::Performance::CCvDDCache::CCvDD *)(v2 + 2));
      operator delete(v2);
      v3 = *(_QWORD **)a1;
      v2 = v4;
    }
    while ( v4 != *(_QWORD **)a1 );
  }
  operator delete(v3);
}

```

## disassembly

```asm
0x1800151a8  mov     [rsp+arg_0], rbx
0x1800151ad  mov     [rsp+arg_8], rsi
0x1800151b2  push    rdi
0x1800151b3  sub     rsp, 20h
0x1800151b7  mov     rax, [rcx]
0x1800151ba  mov     rdi, rcx
0x1800151bd  mov     rsi, [rax]
0x1800151c0  mov     [rax], rax
0x1800151c3  mov     rax, [rcx]
0x1800151c6  mov     [rax+8], rax
0x1800151ca  mov     qword ptr [rcx+8], 0
0x1800151d2  mov     rcx, [rcx]
0x1800151d5  cmp     rsi, rcx
0x1800151d8  jz      short loc_180015200
0x1800151da  mov     rbx, [rsi]
0x1800151dd  lea     rcx, [rsi+10h]; this
0x1800151e1  call    ??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)
0x1800151e6  mov     rcx, rsi
0x1800151e9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800151f0  nop     dword ptr [rax+rax+00h]
0x1800151f5  mov     rcx, [rdi]
0x1800151f8  mov     rsi, rbx
0x1800151fb  cmp     rbx, rcx
0x1800151fe  jnz     short loc_1800151DA
0x180015200  mov     rbx, [rsp+28h+arg_0]
0x180015205  mov     rsi, [rsp+28h+arg_8]
0x18001520a  add     rsp, 20h
0x18001520e  pop     rdi
0x18001520f  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
