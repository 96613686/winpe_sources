# WTL::CString::TrimLeft(void)

- ea: `0x18002c5e8`
- end: `0x18002c66b`
- name: `?TrimLeft@CString@WTL@@QEAAXXZ`
- size: `131`
- prototype: `void __fastcall(WTL::CString *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002c0d0`
- `0x18002c1d0`

## callees

- `0x180004c00`
- `0x180005840`
- `0x18002c5e8`

## import_xrefs

- `msvcrt!memmove_s` at `0x18002c648`
- `msvcrt!memmove_s` at `0x18002c648`
- `msvcrt!iswspace` at `0x18002c616`
- `msvcrt!iswspace` at `0x18002c616`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002c60a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002c60a`

## pseudocode

```c
void __fastcall WTL::CString::TrimLeft(WTL::CString *this)
{
  const WCHAR *v2; // rdi
  wint_t i; // cx
  int v4; // ebx
  errno_t v5; // eax

  WTL::CString::CopyBeforeWrite(this);
  v2 = *(const WCHAR **)this;
  for ( i = **(_WORD **)this; iswspace(i); i = *v2 )
    v2 = CharNextW(v2);
  v4 = *(_DWORD *)(*(_QWORD *)this - 8LL) - (((__int64)v2 - *(_QWORD *)this) >> 1);
  v5 = memmove_s(*(void *const *)this, 2LL * (*(_DWORD *)(*(_QWORD *)this - 4LL) + 1), v2, 2LL * (v4 + 1));
  ATL::AtlCrtErrorCheck(v5);
  *(_DWORD *)(*(_QWORD *)this - 8LL) = v4;
}

```

## disassembly

```asm
0x18002c5e8  mov     [rsp+arg_0], rbx
0x18002c5ed  mov     [rsp+arg_8], rsi
0x18002c5f2  push    rdi
0x18002c5f3  sub     rsp, 20h
0x18002c5f7  mov     rsi, rcx
0x18002c5fa  call    ?CopyBeforeWrite@CString@WTL@@IEAAXXZ; WTL::CString::CopyBeforeWrite(void)
0x18002c5ff  mov     rdi, [rsi]
0x18002c602  movzx   ecx, word ptr [rdi]
0x18002c605  jmp     short loc_18002C616
0x18002c607  mov     rcx, rdi; lpsz
0x18002c60a  call    cs:__imp_CharNextW
0x18002c610  mov     rdi, rax
0x18002c613  movzx   ecx, word ptr [rax]; C
0x18002c616  call    cs:__imp_iswspace
0x18002c61c  test    eax, eax
0x18002c61e  jnz     short loc_18002C607
0x18002c620  mov     rcx, [rsi]; Destination
0x18002c623  mov     rax, rdi
0x18002c626  sub     rax, rcx
0x18002c629  mov     r8, rdi; Source
0x18002c62c  sar     rax, 1
0x18002c62f  mov     ebx, [rcx-8]
0x18002c632  sub     ebx, eax
0x18002c634  lea     eax, [rbx+1]
0x18002c637  movsxd  r9, eax
0x18002c63a  mov     eax, [rcx-4]
0x18002c63d  add     r9, r9; SourceSize
0x18002c640  inc     eax
0x18002c642  movsxd  rdx, eax
0x18002c645  add     rdx, rdx; DestinationSize
0x18002c648  call    cs:__imp_memmove_s
0x18002c64e  mov     ecx, eax; int
0x18002c650  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002c655  mov     rax, [rsi]
0x18002c658  mov     rsi, [rsp+28h+arg_8]
0x18002c65d  mov     [rax-8], ebx
0x18002c660  mov     rbx, [rsp+28h+arg_0]
0x18002c665  add     rsp, 20h
0x18002c669  pop     rdi
0x18002c66a  retn
```
