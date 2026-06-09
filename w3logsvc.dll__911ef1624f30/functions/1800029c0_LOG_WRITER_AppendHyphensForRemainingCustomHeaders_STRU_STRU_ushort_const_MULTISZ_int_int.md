# LOG_WRITER::AppendHyphensForRemainingCustomHeaders(STRU *,STRU *,ushort const *,MULTISZ *,int,int)

- ea: `0x1800029c0`
- end: `0x180002a5c`
- name: `?AppendHyphensForRemainingCustomHeaders@LOG_WRITER@@AEAAJPEAVSTRU@@0PEBGPEAVMULTISZ@@HH@Z`
- size: `156`
- prototype: `int __fastcall(__int64 this, struct STRU *, struct STRU *, const unsigned __int16 *, struct MULTISZ *, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800023d8`

## callees

- `0x1800029c0`
- `0x180002eb8`

## import_xrefs

- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800029ee`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002a2f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800029ee`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002a2f`

## pseudocode

```c
int __fastcall LOG_WRITER::AppendHyphensForRemainingCustomHeaders(
        __int64 this,
        struct STRU *a2,
        struct STRU *a3,
        const unsigned __int16 *a4,
        struct MULTISZ *a5,
        int a6,
        int a7)
{
  const unsigned __int16 *v7; // rbx
  int result; // eax
  __int64 v11; // r9

  v7 = a4;
  result = 0;
  if ( a4 )
  {
    do
    {
      if ( a6 )
      {
        result = STRU::Append(a2, L"- ");
        if ( result < 0 )
          break;
      }
      if ( a7 )
      {
        v11 = -1;
        do
          ++v11;
        while ( v7[v11] );
        result = LOG_WRITER::AppendStringReplaceSpaces((LOG_WRITER *)this, a3, v7, v11, 0x2Du);
        if ( result < 0 )
          break;
        result = STRU::Append(a3, L" - ");
        if ( result < 0 )
          break;
      }
      this = -1;
      do
        ++this;
      while ( v7[this] );
      v7 += this + 1;
    }
    while ( *v7 );
  }
  return result;
}

```

## disassembly

```asm
0x1800029c0  push    rbx
0x1800029c2  push    rbp
0x1800029c3  push    rsi
0x1800029c4  push    rdi
0x1800029c5  sub     rsp, 38h
0x1800029c9  xor     ebp, ebp
0x1800029cb  mov     rbx, r9
0x1800029ce  mov     rdi, r8
0x1800029d1  mov     rsi, rdx
0x1800029d4  mov     eax, ebp
0x1800029d6  test    r9, r9
0x1800029d9  jz      short loc_180002A53
0x1800029db  cmp     [rsp+58h+arg_28], ebp
0x1800029e2  jz      short loc_1800029F8
0x1800029e4  lea     rdx, asc_180012130; "- "
0x1800029eb  mov     rcx, rsi
0x1800029ee  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800029f4  test    eax, eax
0x1800029f6  js      short loc_180002A53
0x1800029f8  cmp     [rsp+58h+arg_30], ebp
0x1800029ff  jz      short loc_180002A39
0x180002a01  or      r9, 0FFFFFFFFFFFFFFFFh
0x180002a05  inc     r9; unsigned int
0x180002a08  cmp     [rbx+r9*2], bp
0x180002a0d  jnz     short loc_180002A05
0x180002a0f  mov     r8, rbx; unsigned __int16 *
0x180002a12  mov     [rsp+58h+var_38], 2Dh ; '-'; unsigned __int16
0x180002a19  mov     rdx, rdi; struct STRU *
0x180002a1c  call    ?AppendStringReplaceSpaces@LOG_WRITER@@AEAAJPEAVSTRU@@PEBGKG@Z; LOG_WRITER::AppendStringReplaceSpaces(STRU *,ushort const *,ulong,ushort)
0x180002a21  test    eax, eax
0x180002a23  js      short loc_180002A53
0x180002a25  lea     rdx, asc_1800121F8; " - "
0x180002a2c  mov     rcx, rdi
0x180002a2f  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002a35  test    eax, eax
0x180002a37  js      short loc_180002A53
0x180002a39  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180002a3d  inc     rcx
0x180002a40  cmp     [rbx+rcx*2], bp
0x180002a44  jnz     short loc_180002A3D
0x180002a46  lea     rbx, [rbx+rcx*2]
0x180002a4a  add     rbx, 2
0x180002a4e  cmp     [rbx], bp
0x180002a51  jnz     short loc_1800029DB
0x180002a53  add     rsp, 38h
0x180002a57  pop     rdi
0x180002a58  pop     rsi
0x180002a59  pop     rbp
0x180002a5a  pop     rbx
0x180002a5b  retn
```
