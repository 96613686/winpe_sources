# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(void)

- ea: `0x180015300`
- end: `0x18001538b`
- name: `??1?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180015844`

## callees

- `0x180015300`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001532a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015357`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001532a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015357`

## pseudocode

```c
void __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>(
        __int64 a1)
{
  void **v1; // rbx
  void **v3; // rsi

  v1 = *(void ***)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(void ***)(a1 + 8);
    while ( v1 != v3 )
    {
      if ( (unsigned __int64)v1[3] >= 8 )
        operator delete(*v1);
      v1[3] = (void *)7;
      v1[2] = 0;
      *(_WORD *)v1 = 0;
      v1 += 4;
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
0x180015300  mov     [rsp+arg_0], rbx
0x180015305  mov     [rsp+arg_8], rsi
0x18001530a  push    rdi
0x18001530b  sub     rsp, 20h
0x18001530f  mov     rbx, [rcx]
0x180015312  mov     rdi, rcx
0x180015315  test    rbx, rbx
0x180015318  jz      short loc_18001537A
0x18001531a  mov     rsi, [rcx+8]
0x18001531e  jmp     short loc_18001534F
0x180015320  cmp     qword ptr [rbx+18h], 8
0x180015325  jb      short loc_180015336
0x180015327  mov     rcx, [rbx]
0x18001532a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180015331  nop     dword ptr [rax+rax+00h]
0x180015336  xor     eax, eax
0x180015338  mov     qword ptr [rbx+18h], 7
0x180015340  mov     qword ptr [rbx+10h], 0
0x180015348  mov     [rbx], ax
0x18001534b  add     rbx, 20h ; ' '
0x18001534f  cmp     rbx, rsi
0x180015352  jnz     short loc_180015320
0x180015354  mov     rcx, [rdi]
0x180015357  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001535e  nop     dword ptr [rax+rax+00h]
0x180015363  mov     qword ptr [rdi], 0
0x18001536a  mov     qword ptr [rdi+8], 0
0x180015372  mov     qword ptr [rdi+10h], 0
0x18001537a  mov     rbx, [rsp+28h+arg_0]
0x18001537f  mov     rsi, [rsp+28h+arg_8]
0x180015384  add     rsp, 20h
0x180015388  pop     rdi
0x180015389  retn
```
