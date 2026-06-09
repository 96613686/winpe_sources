# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(void)

- ea: `0x180015290`
- end: `0x1800152f8`
- name: `??1?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180015844`

## callees

- `0x180015290`
- `0x1800157d4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800152c4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800152c4`

## pseudocode

```c
void __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>(
        __int64 a1)
{
  void **v1; // rdi
  void **v3; // rsi

  v1 = *(void ***)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(void ***)(a1 + 8);
    while ( v1 != v3 )
    {
      Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping::~CMapping(v1);
      v1 += 8;
    }
    operator delete(*(void **)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x180015290  mov     [rsp+arg_0], rbx
0x180015295  mov     [rsp+arg_8], rsi
0x18001529a  push    rdi
0x18001529b  sub     rsp, 20h
0x18001529f  mov     rdi, [rcx]
0x1800152a2  mov     rbx, rcx
0x1800152a5  test    rdi, rdi
0x1800152a8  jz      short loc_1800152E7
0x1800152aa  mov     rsi, [rcx+8]
0x1800152ae  jmp     short loc_1800152BC
0x1800152b0  mov     rcx, rdi; this
0x1800152b3  call    ??1CMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAA@XZ; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping::~CMapping(void)
0x1800152b8  add     rdi, 40h ; '@'
0x1800152bc  cmp     rdi, rsi
0x1800152bf  jnz     short loc_1800152B0
0x1800152c1  mov     rcx, [rbx]
0x1800152c4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800152cb  nop     dword ptr [rax+rax+00h]
0x1800152d0  mov     qword ptr [rbx], 0
0x1800152d7  mov     qword ptr [rbx+8], 0
0x1800152df  mov     qword ptr [rbx+10h], 0
0x1800152e7  mov     rbx, [rsp+28h+arg_0]
0x1800152ec  mov     rsi, [rsp+28h+arg_8]
0x1800152f1  add     rsp, 20h
0x1800152f5  pop     rdi
0x1800152f6  retn
```
