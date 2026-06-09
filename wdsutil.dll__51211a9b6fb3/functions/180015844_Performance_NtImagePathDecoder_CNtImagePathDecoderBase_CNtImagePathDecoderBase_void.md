# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::~CNtImagePathDecoderBase(void)

- ea: `0x180015844`
- end: `0x1800158bd`
- name: `??1CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAA@XZ`
- size: `121`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CNtImagePathDecoderBase *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180015590`
- `0x1800157c8`
- `0x180020a24`
- `0x180020b40`
- `0x180032b31`

## callees

- `0x180015290`
- `0x180015300`
- `0x180015844`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180015858`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015885`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015858`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015885`

## pseudocode

```c
void __fastcall Performance::NtImagePathDecoder::CNtImagePathDecoderBase::~CNtImagePathDecoderBase(void **this)
{
  if ( (unsigned __int64)this[13] >= 8 )
    operator delete(this[10]);
  this[13] = (void *)7;
  this[12] = 0;
  *((_WORD *)this + 40) = 0;
  if ( (unsigned __int64)this[9] >= 8 )
    operator delete(this[6]);
  this[9] = (void *)7;
  this[8] = 0;
  *((_WORD *)this + 24) = 0;
  std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>(this + 3);
  std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>(this);
}

```

## disassembly

```asm
0x180015844  push    rbx
0x180015846  sub     rsp, 20h
0x18001584a  cmp     qword ptr [rcx+68h], 8
0x18001584f  mov     rbx, rcx
0x180015852  jb      short loc_180015864
0x180015854  mov     rcx, [rcx+50h]
0x180015858  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001585f  nop     dword ptr [rax+rax+00h]
0x180015864  xor     eax, eax
0x180015866  mov     qword ptr [rbx+68h], 7
0x18001586e  mov     qword ptr [rbx+60h], 0
0x180015876  mov     [rbx+50h], ax
0x18001587a  cmp     qword ptr [rbx+48h], 8
0x18001587f  jb      short loc_180015891
0x180015881  mov     rcx, [rbx+30h]
0x180015885  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001588c  nop     dword ptr [rax+rax+00h]
0x180015891  xor     eax, eax
0x180015893  mov     qword ptr [rbx+48h], 7
0x18001589b  mov     qword ptr [rbx+40h], 0
0x1800158a3  lea     rcx, [rbx+18h]
0x1800158a7  mov     [rbx+30h], ax
0x1800158ab  call    ??1?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>(void)
0x1800158b0  mov     rcx, rbx
0x1800158b3  add     rsp, 20h
0x1800158b7  pop     rbx
0x1800158b8  jmp     ??1?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>(void)
```
