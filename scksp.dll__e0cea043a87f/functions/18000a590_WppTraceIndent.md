# WppTraceIndent

- ea: `0x18000a590`
- end: `0x18000a6ff`
- name: `WppTraceIndent`
- size: `367`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x180009f20`
- `0x180036dcc`
- `0x180037070`
- `0x180037120`
- `0x180037258`
- `0x1800374f4`
- `0x1800375d4`
- `0x180037730`
- `0x180037a4c`
- `0x18003ae44`
- `0x18003aec8`
- `0x18003af5c`
- `0x18003afc0`

## callees

- `0x18000a324`
- `0x18000a590`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a5a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a5a4`

## pseudocode

```c
char *__fastcall WppTraceIndent(__int64 a1, unsigned int a2)
{
  DWORD CurrentThreadId; // eax
  size_t v4; // rdx
  char *i; // rcx
  int v6; // ebx
  bool v7; // zf
  int v8; // edi
  int j; // esi
  unsigned __int64 v10; // rcx
  const char *v11; // r8
  char *result; // rax

  CurrentThreadId = GetCurrentThreadId();
  v6 = `WppTraceIndent'::`2'::idxCurrentThread;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v6 = 0;
    `WppTraceIndent'::`2'::ThreadTable[0] = CurrentThreadId;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    dword_18004BC24 = 0;
  }
  else
  {
    if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
      || `WppTraceIndent'::`2'::ThreadTable[2 * `WppTraceIndent'::`2'::idxCurrentThread] != CurrentThreadId )
    {
      v4 = 0xFFFFFFFFLL;
      for ( i = 0; ; i = (char *)(unsigned int)((_DWORD)i + 1) )
      {
        v7 = (_DWORD)i == 32;
        if ( (unsigned int)i >= 0x20 )
          break;
        if ( `WppTraceIndent'::`2'::ThreadTable[2 * (int)i] == CurrentThreadId )
        {
          v6 = (int)i;
          `WppTraceIndent'::`2'::idxCurrentThread = (int)i;
          v7 = (_DWORD)i == 32;
          break;
        }
        if ( (_DWORD)v4 == -1 && !`WppTraceIndent'::`2'::ThreadTable[2 * (int)i] )
          v4 = (unsigned int)i;
      }
      if ( v7 )
      {
        if ( (_DWORD)v4 == -1 )
        {
          v6 = -2;
          `WppTraceIndent'::`2'::idxCurrentThread = -2;
        }
        else
        {
          v6 = v4;
          `WppTraceIndent'::`2'::idxCurrentThread = v4;
          `WppTraceIndent'::`2'::ThreadTable[2 * (int)v4] = CurrentThreadId;
          `WppTraceIndent'::`2'::ThreadTable[2 * (int)v4 + 1] = 0;
        }
      }
    }
    if ( v6 < 0 )
    {
      v8 = 0;
      goto LABEL_23;
    }
  }
  if ( !a2 )
    ++`WppTraceIndent'::`2'::ThreadTable[2 * v6 + 1];
  v8 = `WppTraceIndent'::`2'::ThreadTable[2 * v6 + 1];
LABEL_23:
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    for ( j = 1; j <= v8; ++j )
    {
      if ( StringCbCatA(i, v4, "..") )
        break;
    }
  }
  v10 = a2;
  if ( !a2 )
  {
    v11 = ">";
    goto LABEL_34;
  }
  v10 = a2 - 1;
  if ( a2 == 1 )
  {
    v11 = "<";
    goto LABEL_34;
  }
  if ( a2 == 2 )
  {
    v11 = " ";
LABEL_34:
    StringCbCatA((STRSAFE_LPSTR)v10, v4, v11);
  }
  if ( v6 >= 0 && a2 == 1 )
  {
    v7 = `WppTraceIndent'::`2'::ThreadTable[2 * v6 + 1]-- == 1;
    if ( v7 )
      `WppTraceIndent'::`2'::ThreadTable[2 * v6] = 0;
  }
  result = &`WppTraceIndent'::`2'::szIndentPrefix;
  WPP_pszIndent = (__int64)&`WppTraceIndent'::`2'::szIndentPrefix;
  return result;
}

```

## disassembly

```asm
0x18000a590  mov     [rsp+arg_8], rbx
0x18000a595  mov     [rsp+arg_10], rbp
0x18000a59a  push    rsi
0x18000a59b  push    rdi
0x18000a59c  push    r14
0x18000a59e  sub     rsp, 20h
0x18000a5a2  mov     ebp, edx
0x18000a5a4  call    cs:__imp_GetCurrentThreadId
0x18000a5aa  movsxd  rbx, cs:?idxCurrentThread@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::idxCurrentThread
0x18000a5b1  lea     r14, ?ThreadTable@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::ThreadTable
0x18000a5b8  mov     r8d, eax
0x18000a5bb  cmp     ebx, 0FFFFFFFFh
0x18000a5be  jnz     short loc_18000A5D6
0x18000a5c0  xor     ebx, ebx
0x18000a5c2  mov     cs:?ThreadTable@?1??WppTraceIndent@@9@9, eax; `WppTraceIndent'::`2'::ThreadTable
0x18000a5c8  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ebx; `WppTraceIndent'::`2'::idxCurrentThread
0x18000a5ce  mov     cs:dword_18004BC24, ebx
0x18000a5d4  jmp     short loc_18000A640
0x18000a5d6  cmp     ebx, 0FFFFFFFEh
0x18000a5d9  jz      short loc_18000A5E1
0x18000a5db  cmp     [r14+rbx*8], r8d
0x18000a5df  jz      short loc_18000A63C
0x18000a5e1  or      edx, 0FFFFFFFFh; cbDest
0x18000a5e4  xor     ecx, ecx; pszDest
0x18000a5e6  cmp     ecx, 20h ; ' '
0x18000a5e9  jnb     short loc_18000A610
0x18000a5eb  movsxd  rax, ecx
0x18000a5ee  cmp     [r14+rax*8], r8d
0x18000a5f2  jz      short loc_18000A605
0x18000a5f4  cmp     edx, 0FFFFFFFFh
0x18000a5f7  jnz     short loc_18000A601
0x18000a5f9  cmp     dword ptr [r14+rax*8], 0
0x18000a5fe  cmovz   edx, ecx
0x18000a601  inc     ecx
0x18000a603  jmp     short loc_18000A5E6
0x18000a605  mov     ebx, ecx
0x18000a607  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ecx; `WppTraceIndent'::`2'::idxCurrentThread
0x18000a60d  cmp     ecx, 20h ; ' '
0x18000a610  jnz     short loc_18000A63C
0x18000a612  cmp     edx, 0FFFFFFFFh
0x18000a615  jz      short loc_18000A631
0x18000a617  movsxd  rax, edx
0x18000a61a  mov     ebx, edx
0x18000a61c  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, edx; `WppTraceIndent'::`2'::idxCurrentThread
0x18000a622  mov     [r14+rax*8], r8d
0x18000a626  mov     dword ptr [r14+rax*8+4], 0
0x18000a62f  jmp     short loc_18000A63C
0x18000a631  mov     ebx, 0FFFFFFFEh
0x18000a636  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ebx; `WppTraceIndent'::`2'::idxCurrentThread
0x18000a63c  test    ebx, ebx
0x18000a63e  js      short loc_18000A65A
0x18000a640  movsxd  rax, ebx
0x18000a643  test    ebp, ebp
0x18000a645  jnz     short loc_18000A653
0x18000a647  inc     dword ptr [r14+rax*8+4]
0x18000a64c  mov     edi, [r14+rax*8+4]
0x18000a651  jmp     short loc_18000A65C
0x18000a653  mov     edi, [r14+rax*8+4]
0x18000a658  jmp     short loc_18000A65C
0x18000a65a  xor     edi, edi
0x18000a65c  mov     rax, cs:WPP_GLOBAL_Control
0x18000a663  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@9@9, 0; `WppTraceIndent'::`2'::szIndentPrefix
0x18000a66a  test    byte ptr [rax+1Ch], 2
0x18000a66e  jz      short loc_18000A695
0x18000a670  cmp     byte ptr [rax+19h], 5
0x18000a674  jb      short loc_18000A695
0x18000a676  mov     esi, 1
0x18000a67b  cmp     edi, esi
0x18000a67d  jl      short loc_18000A695
0x18000a67f  lea     r8, pszSrc; ".."
0x18000a686  call    StringCbCatA
0x18000a68b  test    eax, eax
0x18000a68d  jnz     short loc_18000A695
0x18000a68f  inc     esi
0x18000a691  cmp     esi, edi
0x18000a693  jle     short loc_18000A67F
0x18000a695  mov     ecx, ebp; pszDest
0x18000a697  test    ebp, ebp
0x18000a699  jz      short loc_18000A6B7
0x18000a69b  sub     ecx, 1
0x18000a69e  jz      short loc_18000A6AE
0x18000a6a0  cmp     ecx, 1
0x18000a6a3  jnz     short loc_18000A6C3
0x18000a6a5  lea     r8, asc_180043464; " "
0x18000a6ac  jmp     short loc_18000A6BE
0x18000a6ae  lea     r8, asc_180043468; "<"
0x18000a6b5  jmp     short loc_18000A6BE
0x18000a6b7  lea     r8, asc_180043460; ">"
0x18000a6be  call    StringCbCatA
0x18000a6c3  test    ebx, ebx
0x18000a6c5  js      short loc_18000A6DE
0x18000a6c7  cmp     ebp, 1
0x18000a6ca  jnz     short loc_18000A6DE
0x18000a6cc  movsxd  rcx, ebx
0x18000a6cf  sub     [r14+rcx*8+4], ebp
0x18000a6d4  jnz     short loc_18000A6DE
0x18000a6d6  mov     dword ptr [r14+rcx*8], 0
0x18000a6de  mov     rbx, [rsp+38h+arg_8]
0x18000a6e3  lea     rax, ?szIndentPrefix@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::szIndentPrefix
0x18000a6ea  mov     rbp, [rsp+38h+arg_10]
0x18000a6ef  mov     cs:WPP_pszIndent, rax
0x18000a6f6  add     rsp, 20h
0x18000a6fa  pop     r14
0x18000a6fc  pop     rdi
0x18000a6fd  pop     rsi
0x18000a6fe  retn
```
