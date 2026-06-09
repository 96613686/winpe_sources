# TdipRemoveMultiSzFromMultiSz

- ea: `0x1400041d0`
- end: `0x1400042a3`
- name: `TdipRemoveMultiSzFromMultiSz`
- size: `211`
- prototype: `__int64 __fastcall(wchar_t *Str2, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001df0`

## callees

- `0x140001c10`
- `0x1400041d0`
- `0x140005600`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x140004230`
- `ntoskrnl!_wcsicmp` at `0x140004230`

## pseudocode

```c
void __fastcall TdipRemoveMultiSzFromMultiSz(wchar_t *Str2, _WORD *a2)
{
  _WORD *v2; // rbx
  const wchar_t *i; // rsi
  __int64 v5; // rbp
  int v6; // eax
  __int64 v7; // r9
  __int64 v8; // rax

  if ( a2 )
  {
    v2 = a2;
    if ( Str2 )
    {
      if ( *Str2 && *a2 )
      {
        do
        {
          for ( i = Str2; *i; i += (unsigned int)(v5 + 1) )
          {
            v5 = -1;
            do
              ++v5;
            while ( i[v5] );
            if ( !_wcsicmp(v2, i) )
            {
              v6 = TdipCbOfMultiSzSafe(&v2[(unsigned int)v5 + 1]);
              memmove(v2, (const void *)(v7 + 2), v6 + 2);
              goto LABEL_15;
            }
          }
          v8 = -1;
          while ( v2[++v8] != 0 )
            ;
          v2 += v8 + 1;
LABEL_15:
          ;
        }
        while ( *v2 );
      }
    }
  }
}

```

## disassembly

```asm
0x1400041d0  test    rdx, rdx
0x1400041d3  jz      locret_1400042A1
0x1400041d9  mov     [rsp+arg_10], rbx
0x1400041de  push    rdi
0x1400041df  sub     rsp, 20h
0x1400041e3  mov     rbx, rdx
0x1400041e6  mov     rdi, rcx
0x1400041e9  test    rcx, rcx
0x1400041ec  jz      loc_140004297
0x1400041f2  cmp     word ptr [rcx], 0
0x1400041f6  jz      loc_140004297
0x1400041fc  cmp     word ptr [rdx], 0
0x140004200  jz      loc_140004297
0x140004206  mov     [rsp+28h+arg_0], rbp
0x14000420b  mov     [rsp+28h+arg_8], rsi
0x140004210  mov     rsi, rdi
0x140004213  cmp     word ptr [rsi], 0
0x140004217  jz      short loc_14000426C
0x140004219  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x140004220  inc     rbp
0x140004223  cmp     word ptr [rsi+rbp*2], 0
0x140004228  jnz     short loc_140004220
0x14000422a  mov     rdx, rsi; Str2
0x14000422d  mov     rcx, rbx; Str1
0x140004230  call    cs:__imp__wcsicmp
0x140004237  nop     dword ptr [rax+rax+00h]
0x14000423c  test    eax, eax
0x14000423e  jz      short loc_140004249
0x140004240  lea     eax, [rbp+1]
0x140004243  lea     rsi, [rsi+rax*2]
0x140004247  jmp     short loc_140004213
0x140004249  mov     eax, ebp
0x14000424b  lea     r9, [rbx+rax*2]
0x14000424f  lea     rcx, [r9+2]
0x140004253  call    TdipCbOfMultiSzSafe
0x140004258  add     eax, 2
0x14000425b  lea     rdx, [r9+2]; Src
0x14000425f  movsxd  r8, eax; Size
0x140004262  mov     rcx, rbx; void *
0x140004265  call    memmove
0x14000426a  jmp     short loc_140004287
0x14000426c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140004273  cmp     word ptr [rbx+rax*2+2], 0
0x140004279  lea     rax, [rax+1]
0x14000427d  jnz     short loc_140004273
0x14000427f  lea     rbx, [rbx+rax*2]
0x140004283  add     rbx, 2
0x140004287  cmp     word ptr [rbx], 0
0x14000428b  jnz     short loc_140004210
0x14000428d  mov     rsi, [rsp+28h+arg_8]
0x140004292  mov     rbp, [rsp+28h+arg_0]
0x140004297  mov     rbx, [rsp+28h+arg_10]
0x14000429c  add     rsp, 20h
0x1400042a0  pop     rdi
0x1400042a1  retn
```
