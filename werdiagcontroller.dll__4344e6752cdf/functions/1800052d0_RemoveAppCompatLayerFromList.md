# RemoveAppCompatLayerFromList

- ea: `0x1800052d0`
- end: `0x180005481`
- name: `RemoveAppCompatLayerFromList`
- size: `433`
- prototype: `__int64 __fastcall(__int16 *, __int64, __int64, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180003e10`

## callees

- `0x180001cc6`
- `0x180001cd4`
- `0x180001cec`
- `0x1800052d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800053c3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800053c3`
- `ntdll!DbgPrintEx` at `0x18000541f`
- `ntdll!DbgPrintEx` at `0x18000543f`
- `ntdll!DbgPrintEx` at `0x180005467`
- `ntdll!DbgPrintEx` at `0x18000541f`
- `ntdll!DbgPrintEx` at `0x18000543f`
- `ntdll!DbgPrintEx` at `0x180005467`

## pseudocode

```c
__int64 __fastcall RemoveAppCompatLayerFromList(__int16 *a1, __int64 a2, __int64 a3, void **a4)
{
  __int64 v6; // rax
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rbp
  void *v9; // rax
  void *v10; // rdi
  void *v11; // rcx
  _WORD *v12; // rdi
  __int16 v13; // ax
  __int16 *v14; // rbx
  int v15; // ecx
  int v16; // ebp
  __int16 v17; // ax
  unsigned int v18; // edi
  void *v19; // rcx

  if ( a1 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a1[v6] );
    if ( (_DWORD)v6 )
    {
      v7 = (unsigned int)(v6 + 1);
      if ( (unsigned int)v7 < (unsigned int)v6 )
      {
        v18 = -2147024362;
        DbgPrintEx(0x96u, 0, "WERDIAG: Arithmetic overflow\n");
      }
      else
      {
        v8 = 2 * v7;
        if ( !is_mul_ok(v7, 2u) )
          v8 = -1;
        v9 = operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
        v10 = v9;
        if ( v9 )
          memset_0(v9, 0, v8);
        else
          v10 = 0;
        v11 = *a4;
        *a4 = v10;
        if ( v11 )
          operator delete[](v11);
        v12 = *a4;
        if ( *a4 )
        {
          v13 = *a1;
          if ( *a1 )
          {
            v14 = a1;
            v15 = 0;
            v16 = 0;
            do
            {
              if ( v13 == 32 )
              {
                do
                {
                  if ( v15 )
                    v16 = 1;
                  ++v14;
                }
                while ( *v14 == 32 );
              }
              if ( v16 && *v14 )
              {
                *v12 = 32;
                v16 = 0;
                ++v12;
              }
              if ( !(unsigned int)_o__wcsnicmp(v14, L"FDR", 3)
                && (v14[3] & 0xFFDF) == 0
                && (v14 == a1 || v14 > a1 && !*(v14 - 1)) )
              {
                v14 += 3;
              }
              v17 = *v14;
              if ( !*v14 )
                break;
              ++v14;
              *v12++ = v17;
              v15 = 1;
              v13 = *v14;
            }
            while ( *v14 );
          }
          *v12 = 0;
          return 0;
        }
        DbgPrintEx(0x96u, 0, "WERDIAG: OOM\n");
        v18 = -2147024882;
      }
      v19 = *a4;
      *a4 = 0;
      if ( v19 )
        operator delete[](v19);
      return v18;
    }
  }
  DbgPrintEx(0x96u, 0, "WERDIAG: Invalid params\n");
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800052d0  push    rbx
0x1800052d2  push    rbp
0x1800052d3  push    rsi
0x1800052d4  push    rdi
0x1800052d5  push    r13
0x1800052d7  push    r14
0x1800052d9  push    r15
0x1800052db  sub     rsp, 20h
0x1800052df  xor     r14d, r14d
0x1800052e2  mov     rbx, r9
0x1800052e5  mov     rsi, rcx
0x1800052e8  test    rcx, rcx
0x1800052eb  jz      loc_180005459
0x1800052f1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800052f5  mov     rax, r8
0x1800052f8  inc     rax
0x1800052fb  cmp     [rcx+rax*2], r14w
0x180005300  jnz     short loc_1800052F8
0x180005302  test    eax, eax
0x180005304  jz      loc_180005459
0x18000530a  lea     ecx, [rax+1]
0x18000530d  cmp     ecx, eax
0x18000530f  jb      loc_18000542C
0x180005315  mov     eax, 2
0x18000531a  mul     rcx
0x18000531d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005324  mov     rbp, rax
0x180005327  cmovb   rbp, r8
0x18000532b  mov     rcx, rbp; unsigned __int64
0x18000532e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005333  mov     rdi, rax
0x180005336  test    rax, rax
0x180005339  jz      short loc_18000534A
0x18000533b  mov     r8, rbp; Size
0x18000533e  xor     edx, edx; Val
0x180005340  mov     rcx, rax; void *
0x180005343  call    memset_0
0x180005348  jmp     short loc_18000534D
0x18000534a  mov     rdi, r14
0x18000534d  mov     rcx, [rbx]; void *
0x180005350  mov     [rbx], rdi
0x180005353  test    rcx, rcx
0x180005356  jz      short loc_18000535D
0x180005358  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000535d  mov     rdi, [rbx]
0x180005360  test    rdi, rdi
0x180005363  jz      loc_180005411
0x180005369  movzx   eax, word ptr [rsi]
0x18000536c  test    ax, ax
0x18000536f  jz      loc_180005408
0x180005375  mov     r15d, 20h ; ' '
0x18000537b  mov     rbx, rsi
0x18000537e  mov     ecx, r14d
0x180005381  mov     ebp, r14d
0x180005384  lea     r13d, [r15-1Fh]
0x180005388  cmp     ax, r15w
0x18000538c  jnz     short loc_18000539E
0x18000538e  test    ecx, ecx
0x180005390  cmovnz  ebp, r13d
0x180005394  add     rbx, 2
0x180005398  cmp     [rbx], r15w
0x18000539c  jz      short loc_18000538E
0x18000539e  test    ebp, ebp
0x1800053a0  jz      short loc_1800053B3
0x1800053a2  cmp     [rbx], r14w
0x1800053a6  jz      short loc_1800053B3
0x1800053a8  mov     [rdi], r15w
0x1800053ac  mov     ebp, r14d
0x1800053af  add     rdi, 2
0x1800053b3  mov     r8d, 3
0x1800053b9  lea     rdx, aFdr; "FDR"
0x1800053c0  mov     rcx, rbx
0x1800053c3  call    cs:__imp__o__wcsnicmp
0x1800053c9  test    eax, eax
0x1800053cb  jnz     short loc_1800053EA
0x1800053cd  mov     ecx, 0FFDFh
0x1800053d2  test    [rbx+6], cx
0x1800053d6  jnz     short loc_1800053EA
0x1800053d8  cmp     rbx, rsi
0x1800053db  jz      short loc_1800053E6
0x1800053dd  jbe     short loc_1800053EA
0x1800053df  cmp     [rbx-2], r14w
0x1800053e4  jnz     short loc_1800053EA
0x1800053e6  add     rbx, 6
0x1800053ea  movzx   eax, word ptr [rbx]
0x1800053ed  test    ax, ax
0x1800053f0  jz      short loc_180005408
0x1800053f2  add     rbx, 2
0x1800053f6  mov     [rdi], ax
0x1800053f9  add     rdi, 2
0x1800053fd  mov     ecx, r13d
0x180005400  movzx   eax, word ptr [rbx]
0x180005403  test    ax, ax
0x180005406  jnz     short loc_180005388
0x180005408  mov     [rdi], r14w
0x18000540c  mov     edi, r14d
0x18000540f  jmp     short loc_180005455
0x180005411  lea     r8, aWerdiagOom; "WERDIAG: OOM\n"
0x180005418  xor     edx, edx; Level
0x18000541a  mov     ecx, 96h; ComponentId
0x18000541f  call    cs:__imp_DbgPrintEx
0x180005425  mov     edi, 8007000Eh
0x18000542a  jmp     short loc_180005445
0x18000542c  lea     r8, aWerdiagArithme; "WERDIAG: Arithmetic overflow\n"
0x180005433  xor     edx, edx; Level
0x180005435  mov     ecx, 96h; ComponentId
0x18000543a  mov     edi, 80070216h
0x18000543f  call    cs:__imp_DbgPrintEx
0x180005445  mov     rcx, [rbx]; void *
0x180005448  mov     [rbx], r14
0x18000544b  test    rcx, rcx
0x18000544e  jz      short loc_180005455
0x180005450  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180005455  mov     eax, edi
0x180005457  jmp     short loc_180005472
0x180005459  lea     r8, aWerdiagInvalid_1; "WERDIAG: Invalid params\n"
0x180005460  xor     edx, edx; Level
0x180005462  mov     ecx, 96h; ComponentId
0x180005467  call    cs:__imp_DbgPrintEx
0x18000546d  mov     eax, 80070057h
0x180005472  add     rsp, 20h
0x180005476  pop     r15
0x180005478  pop     r14
0x18000547a  pop     r13
0x18000547c  pop     rdi
0x18000547d  pop     rsi
0x18000547e  pop     rbp
0x18000547f  pop     rbx
0x180005480  retn
```
