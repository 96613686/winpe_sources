# WinNatFindNatInstance

- ea: `0x1400106dc`
- end: `0x140010747`
- name: `WinNatFindNatInstance`
- size: `107`
- prototype: `__int64 __fastcall(wchar_t *Str2)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140010810`
- `0x1400109a0`
- `0x140010e64`
- `0x1400110d0`
- `0x1400113c0`

## callees

- `0x1400106dc`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x1400106ff`
- `ntoskrnl!_wcsicmp` at `0x1400106ff`

## pseudocode

```c
__int64 __fastcall WinNatFindNatInstance(wchar_t *Str2)
{
  __int64 i; // rbx

  for ( i = qword_140026AA0; ; i = *(_QWORD *)i )
  {
    if ( (__int64 *)i == &qword_140026AA0 )
      return 0;
    if ( !_wcsicmp((const wchar_t *)(i + 16), Str2) )
      break;
  }
  if ( _InterlockedIncrement64((volatile signed __int64 *)(i - 8)) <= 1 )
    __fastfail(0xEu);
  return i - 328;
}

```

## disassembly

```asm
0x1400106dc  push    rbx
0x1400106de  push    rbp
0x1400106df  push    rsi
0x1400106e0  push    rdi
0x1400106e1  sub     rsp, 28h
0x1400106e5  mov     rbx, cs:qword_140026AA0
0x1400106ec  lea     rbp, qword_140026AA0
0x1400106f3  mov     rsi, rcx
0x1400106f6  jmp     short loc_140010712
0x1400106f8  lea     rcx, [rbx+10h]; Str1
0x1400106fc  mov     rdx, rsi; Str2
0x1400106ff  call    cs:__imp__wcsicmp
0x140010706  nop     dword ptr [rax+rax+00h]
0x14001070b  test    eax, eax
0x14001070d  jz      short loc_140010723
0x14001070f  mov     rbx, [rbx]
0x140010712  cmp     rbx, rbp
0x140010715  jnz     short loc_1400106F8
0x140010717  xor     eax, eax
0x140010719  add     rsp, 28h
0x14001071d  pop     rdi
0x14001071e  pop     rsi
0x14001071f  pop     rbp
0x140010720  pop     rbx
0x140010721  retn
0x140010723  mov     ecx, 1
0x140010728  lock xadd [rbx-8], rcx
0x14001072e  inc     rcx
0x140010731  cmp     rcx, 1
0x140010735  jg      short loc_14001073E
0x140010737  mov     ecx, 0Eh
0x14001073c  int     29h; Win8: RtlFailFast(ecx)
0x14001073e  lea     rax, [rbx-148h]
0x140010745  jmp     short loc_140010719
```
