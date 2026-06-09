# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping::~CMapping(void)

- ea: `0x1800157d4`
- end: `0x18001583c`
- name: `??1CMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAA@XZ`
- size: `104`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180014368`
- `0x180015290`
- `0x180017f68`
- `0x1800198f0`
- `0x18001d118`
- `0x1800329b2`

## callees

- `0x1800157d4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800157e8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015814`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800157e8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015814`

## pseudocode

```c
void __fastcall Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping::~CMapping(void **this)
{
  if ( (unsigned __int64)this[7] >= 8 )
    operator delete(this[4]);
  this[7] = (void *)7;
  this[6] = 0;
  *((_WORD *)this + 16) = 0;
  if ( (unsigned __int64)this[3] >= 8 )
    operator delete(*this);
  this[3] = (void *)7;
  this[2] = 0;
  *(_WORD *)this = 0;
}

```

## disassembly

```asm
0x1800157d4  push    rbx
0x1800157d6  sub     rsp, 20h
0x1800157da  cmp     qword ptr [rcx+38h], 8
0x1800157df  mov     rbx, rcx
0x1800157e2  jb      short loc_1800157F4
0x1800157e4  mov     rcx, [rcx+20h]
0x1800157e8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800157ef  nop     dword ptr [rax+rax+00h]
0x1800157f4  xor     eax, eax
0x1800157f6  mov     qword ptr [rbx+38h], 7
0x1800157fe  mov     qword ptr [rbx+30h], 0
0x180015806  mov     [rbx+20h], ax
0x18001580a  cmp     qword ptr [rbx+18h], 8
0x18001580f  jb      short loc_180015820
0x180015811  mov     rcx, [rbx]
0x180015814  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001581b  nop     dword ptr [rax+rax+00h]
0x180015820  xor     eax, eax
0x180015822  mov     qword ptr [rbx+18h], 7
0x18001582a  mov     qword ptr [rbx+10h], 0
0x180015832  mov     [rbx], ax
0x180015835  add     rsp, 20h
0x180015839  pop     rbx
0x18001583a  retn
```
