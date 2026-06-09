# _CopyStringA

- ea: `0x180008acc`
- end: `0x180008b49`
- name: `_CopyStringA`
- size: `125`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180002d20`
- `0x180009df0`
- `0x180009fd0`
- `0x18000a490`
- `0x18000af60`
- `0x18000b230`
- `0x18000b330`

## callees

- `0x180008acc`
- `0x18000eea0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008b14`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008b14`

## pseudocode

```c
__int64 __fastcall CopyStringA(__int64 a1, _QWORD *a2, unsigned int *a3)
{
  unsigned int v6; // edi
  __int64 v7; // rax
  unsigned int v8; // r14d
  HLOCAL v9; // rax

  v6 = 1;
  if ( a1 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_BYTE *)(v7 + a1) );
    v8 = 2 * v7 + 2;
    v9 = LocalAlloc(0x40u, v8);
    *a2 = v9;
    if ( v9 )
    {
      if ( a3 )
        *a3 = v8;
      AnsiToUnicode(*a2, v8, a1);
    }
    else
    {
      return 0;
    }
  }
  else
  {
    *a2 = 0;
    if ( a3 )
      *a3 = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180008acc  push    rbx
0x180008ace  push    rbp
0x180008acf  push    rsi
0x180008ad0  push    rdi
0x180008ad1  push    r14
0x180008ad3  sub     rsp, 20h
0x180008ad7  mov     rbx, r8
0x180008ada  mov     rsi, rdx
0x180008add  mov     rbp, rcx
0x180008ae0  mov     edi, 1
0x180008ae5  test    rcx, rcx
0x180008ae8  jnz     short loc_180008AF7
0x180008aea  mov     [rdx], rcx
0x180008aed  test    rbx, rbx
0x180008af0  jz      short loc_180008B3C
0x180008af2  mov     [r8], ecx
0x180008af5  jmp     short loc_180008B3C
0x180008af7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008afb  inc     rax
0x180008afe  cmp     byte ptr [rax+rcx], 0
0x180008b02  jnz     short loc_180008AFB
0x180008b04  lea     r14d, ds:2[rax*2]
0x180008b0c  mov     ecx, 40h ; '@'; uFlags
0x180008b11  mov     edx, r14d; uBytes
0x180008b14  call    cs:__imp_LocalAlloc
0x180008b1a  mov     [rsi], rax
0x180008b1d  test    rax, rax
0x180008b20  jnz     short loc_180008B26
0x180008b22  xor     edi, edi
0x180008b24  jmp     short loc_180008B3C
0x180008b26  test    rbx, rbx
0x180008b29  jz      short loc_180008B2E
0x180008b2b  mov     [rbx], r14d
0x180008b2e  mov     rcx, [rsi]
0x180008b31  mov     r8, rbp
0x180008b34  mov     edx, r14d
0x180008b37  call    AnsiToUnicode
0x180008b3c  mov     eax, edi
0x180008b3e  add     rsp, 20h
0x180008b42  pop     r14
0x180008b44  pop     rdi
0x180008b45  pop     rsi
0x180008b46  pop     rbp
0x180008b47  pop     rbx
0x180008b48  retn
```
