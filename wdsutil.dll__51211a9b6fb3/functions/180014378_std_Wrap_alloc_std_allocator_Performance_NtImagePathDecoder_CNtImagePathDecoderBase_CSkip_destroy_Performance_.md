# std::_Wrap_alloc<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>::destroy<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *)

- ea: `0x180014378`
- end: `0x1800143af`
- name: `??$destroy@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@?$_Wrap_alloc@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAAXPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@Z`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18003248c`

## callees

- `0x180014378`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001438b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001438b`

## pseudocode

```c
__int64 __fastcall std::_Wrap_alloc<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>::destroy<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax

  if ( *(_QWORD *)(a2 + 24) >= 8u )
    operator delete(*(void **)a2);
  result = 0;
  *(_QWORD *)(a2 + 24) = 7;
  *(_QWORD *)(a2 + 16) = 0;
  *(_WORD *)a2 = 0;
  return result;
}

```

## disassembly

```asm
0x180014378  push    rbx
0x18001437a  sub     rsp, 20h
0x18001437e  cmp     qword ptr [rdx+18h], 8
0x180014383  mov     rbx, rdx
0x180014386  jb      short loc_180014397
0x180014388  mov     rcx, [rdx]
0x18001438b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180014392  nop     dword ptr [rax+rax+00h]
0x180014397  xor     eax, eax
0x180014399  mov     qword ptr [rbx+18h], 7
0x1800143a1  mov     [rbx+10h], rax
0x1800143a5  mov     [rbx], ax
0x1800143a8  add     rsp, 20h
0x1800143ac  pop     rbx
0x1800143ad  retn
```
