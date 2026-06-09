# FltCommStubCreateChild

- ea: `0x1800250c4`
- end: `0x18002529d`
- name: `FltCommStubCreateChild`
- size: `473`
- prototype: `__int64 __fastcall(int, int, int, int, int, void *Src, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180021484`

## callees

- `0x1800219c4`
- `0x1800250c4`
- `0x180060e42`
- `0x180060e70`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002526d`
- `KERNEL32!HeapFree` at `0x18002526d`
- `KERNEL32!HeapAlloc` at `0x18002518a`
- `KERNEL32!HeapAlloc` at `0x18002518a`
- `KERNEL32!GetProcessHeap` at `0x180025171`
- `KERNEL32!GetProcessHeap` at `0x180025259`
- `KERNEL32!GetProcessHeap` at `0x180025171`
- `KERNEL32!GetProcessHeap` at `0x180025259`

## string_xrefs

- `0x180025115`: `FltCommStubCreateChild`
- `0x180025247`: `FltCommStubCreateChild`

## pseudocode

```c
__int64 __fastcall FltCommStubCreateChild(__int64 a1, __int64 a2, int a3, int a4, int a5, _WORD *Src, _QWORD *a7)
{
  unsigned int v9; // ebx
  unsigned int v10; // r8d
  int v11; // r9d
  __int64 v12; // rdi
  unsigned int v13; // edi
  unsigned int v14; // r15d
  HANDLE ProcessHeap; // rax
  char *v16; // rax
  void *v17; // rsi
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rdx
  HANDLE v21; // rax
  int v23; // [rsp+40h] [rbp-48h] BYREF
  _QWORD v24[8]; // [rsp+48h] [rbp-40h] BYREF
  int v26; // [rsp+98h] [rbp+10h]

  v26 = a2;
  v23 = 0;
  v24[0] = 0;
  *a7 = -1;
  if ( !g_FilterPointers )
  {
    v9 = -1052638943;
    v10 = 177;
LABEL_3:
    v11 = v9;
LABEL_4:
    UtilReportError((__int64)L"FltCommStubCreateChild", a2, v10, v11);
    goto LABEL_18;
  }
  if ( !Src )
  {
    v11 = -2147024809;
    v10 = 183;
    v9 = -2147024809;
    goto LABEL_4;
  }
  v12 = -1;
  do
    ++v12;
  while ( Src[v12] );
  v13 = 2 * v12;
  if ( v13 > 0xFFFF )
  {
    v11 = -2147024809;
    v10 = 189;
    v9 = -2147024809;
    goto LABEL_4;
  }
  v14 = v13 + 48;
  ProcessHeap = GetProcessHeap();
  v16 = (char *)HeapAlloc(ProcessHeap, 8u, v13 + 48);
  v17 = v16;
  if ( !v16 )
  {
    v9 = -2147024882;
    v10 = 195;
    goto LABEL_3;
  }
  *((_DWORD *)v16 + 3) = 5;
  *((_DWORD *)v16 + 1) = 65539;
  *(_DWORD *)v16 = 1111638594;
  *((_DWORD *)v16 + 2) = v14;
  *((_QWORD *)v16 + 2) = a1;
  *((_DWORD *)v16 + 6) = v26;
  *((_DWORD *)v16 + 9) = a5;
  *((_DWORD *)v16 + 7) = a3;
  *((_DWORD *)v16 + 8) = a4;
  *((_WORD *)v16 + 20) = v13;
  memcpy_0(v16 + 42, Src, v13);
  v18 = 0;
  if ( g_FilterPointers )
    v18 = *(_QWORD *)(g_FilterPointers + 48);
  v19 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD, _QWORD *, int, int *))(g_FilterPointers + 24))(
          v18,
          v17,
          v14,
          v24,
          8,
          &v23);
  v9 = v19;
  *a7 = v24[0];
  if ( v19 < 0 )
    UtilReportError((__int64)L"FltCommStubCreateChild", v20, 0xDDu, v19);
  v21 = GetProcessHeap();
  HeapFree(v21, 0, v17);
LABEL_18:
  if ( !*a7 )
    *a7 = -1;
  return v9;
}

```

## disassembly

```asm
0x1800250c4  mov     [rsp+arg_10], rbx
0x1800250c9  mov     [rsp+arg_8], edx
0x1800250cd  mov     [rsp+arg_0], rcx
0x1800250d2  push    rbp
0x1800250d3  push    rsi
0x1800250d4  push    rdi
0x1800250d5  push    r12
0x1800250d7  push    r13
0x1800250d9  push    r14
0x1800250db  push    r15
0x1800250dd  sub     rsp, 50h
0x1800250e1  mov     r14, [rsp+88h+arg_30]
0x1800250e9  xor     eax, eax
0x1800250eb  mov     r12d, r9d
0x1800250ee  mov     [rsp+88h+var_48], eax
0x1800250f2  mov     r13d, r8d
0x1800250f5  mov     [rsp+88h+var_40], rax
0x1800250fa  or      qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x1800250fe  cmp     cs:g_FilterPointers, rax
0x180025105  jnz     short loc_180025126
0x180025107  mov     ebx, 0C1420121h
0x18002510c  mov     r8d, 0B1h
0x180025112  mov     r9d, ebx
0x180025115  lea     rcx, aFltcommstubcre; "FltCommStubCreateChild"
0x18002511c  call    UtilReportError
0x180025121  jmp     loc_180025279
0x180025126  mov     rbp, [rsp+88h+Src]
0x18002512e  test    rbp, rbp
0x180025131  jnz     short loc_180025144
0x180025133  mov     r9d, 80070057h
0x180025139  mov     r8d, 0B7h
0x18002513f  mov     ebx, r9d
0x180025142  jmp     short loc_180025115
0x180025144  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180025148  inc     rdi
0x18002514b  cmp     [rbp+rdi*2+0], ax
0x180025150  jnz     short loc_180025148
0x180025152  add     edi, edi
0x180025154  cmp     edi, 0FFFFh
0x18002515a  jbe     short loc_18002516D
0x18002515c  mov     r9d, 80070057h
0x180025162  mov     r8d, 0BDh
0x180025168  mov     ebx, r9d
0x18002516b  jmp     short loc_180025115
0x18002516d  lea     r15d, [rdi+30h]
0x180025171  call    cs:__imp_GetProcessHeap
0x180025178  nop     dword ptr [rax+rax+00h]
0x18002517d  mov     ebx, 8
0x180025182  mov     r8d, r15d; dwBytes
0x180025185  mov     rcx, rax; hHeap
0x180025188  mov     edx, ebx; dwFlags
0x18002518a  call    cs:__imp_HeapAlloc
0x180025191  nop     dword ptr [rax+rax+00h]
0x180025196  mov     rsi, rax
0x180025199  test    rax, rax
0x18002519c  jnz     short loc_1800251AE
0x18002519e  mov     ebx, 8007000Eh
0x1800251a3  mov     r8d, 0C3h
0x1800251a9  jmp     loc_180025112
0x1800251ae  mov     dword ptr [rax+0Ch], 5
0x1800251b5  lea     rcx, [rsi+2Ah]; void *
0x1800251b9  mov     dword ptr [rax+4], 10003h
0x1800251c0  mov     rdx, rbp; Src
0x1800251c3  mov     dword ptr [rax], 42424242h
0x1800251c9  mov     [rax+8], r15d
0x1800251cd  mov     rax, [rsp+88h+arg_0]
0x1800251d5  mov     [rsi+10h], rax
0x1800251d9  mov     eax, [rsp+88h+arg_8]
0x1800251e0  mov     [rsi+18h], eax
0x1800251e3  mov     eax, [rsp+88h+arg_20]
0x1800251ea  mov     r8d, edi; Size
0x1800251ed  mov     [rsi+24h], eax
0x1800251f0  mov     [rsi+1Ch], r13d
0x1800251f4  mov     [rsi+20h], r12d
0x1800251f8  mov     [rsi+28h], di
0x1800251fc  call    memcpy_0
0x180025201  mov     rax, cs:g_FilterPointers
0x180025208  xor     ecx, ecx
0x18002520a  test    rax, rax
0x18002520d  jz      short loc_180025213
0x18002520f  mov     rcx, [rax+30h]
0x180025213  mov     rax, [rax+18h]
0x180025217  lea     rdx, [rsp+88h+var_48]
0x18002521c  mov     [rsp+88h+var_60], rdx
0x180025221  lea     r9, [rsp+88h+var_40]
0x180025226  mov     rdx, rsi
0x180025229  mov     [rsp+88h+var_68], ebx
0x18002522d  mov     r8d, r15d
0x180025230  call    cs:__guard_dispatch_icall_fptr
0x180025236  mov     rcx, [rsp+88h+var_40]
0x18002523b  mov     ebx, eax
0x18002523d  mov     [r14], rcx
0x180025240  test    eax, eax
0x180025242  jns     short loc_180025259
0x180025244  mov     r9d, eax
0x180025247  lea     rcx, aFltcommstubcre; "FltCommStubCreateChild"
0x18002524e  mov     r8d, 0DDh
0x180025254  call    UtilReportError
0x180025259  call    cs:__imp_GetProcessHeap
0x180025260  nop     dword ptr [rax+rax+00h]
0x180025265  mov     r8, rsi; lpMem
0x180025268  xor     edx, edx; dwFlags
0x18002526a  mov     rcx, rax; hHeap
0x18002526d  call    cs:__imp_HeapFree
0x180025274  nop     dword ptr [rax+rax+00h]
0x180025279  cmp     qword ptr [r14], 0
0x18002527d  jnz     short loc_180025283
0x18002527f  or      qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x180025283  mov     eax, ebx
0x180025285  mov     rbx, [rsp+88h+arg_10]
0x18002528d  add     rsp, 50h
0x180025291  pop     r15
0x180025293  pop     r14
0x180025295  pop     r13
0x180025297  pop     r12
0x180025299  pop     rdi
0x18002529a  pop     rsi
0x18002529b  pop     rbp
0x18002529c  retn
```
