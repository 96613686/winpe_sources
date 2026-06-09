# ArgpFileInitialize(ushort const *,_ARGUMENT_INPUT * *)

- ea: `0x14003f0cc`
- end: `0x14003f1ca`
- name: `?ArgpFileInitialize@@YAJPEBGPEAPEAU_ARGUMENT_INPUT@@@Z`
- size: `254`
- prototype: `__int64 __fastcall(wchar_t *FileName, struct _ARGUMENT_INPUT **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14003b990`

## callees

- `0x14003f060`
- `0x14003f0cc`

## import_xrefs

- `msvcrt!_wfopen` at `0x14003f181`
- `msvcrt!_wfopen` at `0x14003f181`
- `msvcrt!_errno` at `0x14003f190`
- `msvcrt!_errno` at `0x14003f190`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003f0e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003f148`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003f0e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003f148`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003f0f0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003f159`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003f0f0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003f159`

## pseudocode

```c
__int64 __fastcall ArgpFileInitialize(wchar_t *FileName, struct _ARGUMENT_INPUT **a2)
{
  HANDLE ProcessHeap; // rax
  struct _FILE_ARGUMENT_PARSING *v5; // rax
  struct _FILE_ARGUMENT_PARSING *v6; // rdi
  int v7; // ebx
  HANDLE v8; // rax
  _WORD *v9; // rax
  FILE *v10; // rax
  bool v11; // sf

  ProcessHeap = GetProcessHeap();
  v5 = (struct _FILE_ARGUMENT_PARSING *)HeapAlloc(ProcessHeap, 0, 0x38u);
  v6 = v5;
  if ( !v5 )
    goto LABEL_2;
  *((_QWORD *)v5 + 3) = 0;
  *((_QWORD *)v5 + 4) = 0;
  *((_QWORD *)v5 + 5) = 0;
  *((_QWORD *)v5 + 6) = 0;
  *(_QWORD *)v5 = ArgpFileNextArg;
  *((_QWORD *)v5 + 1) = ArgpFileNextArgParam;
  *((_QWORD *)v5 + 2) = ArgpFileCleanup;
  v8 = GetProcessHeap();
  v9 = HeapAlloc(v8, 0, 0x800u);
  *((_QWORD *)v6 + 5) = v9;
  if ( !v9 )
  {
LABEL_2:
    v7 = -2147024882;
LABEL_8:
    ArgpFileCleanup(v6);
    return (unsigned int)v7;
  }
  *v9 = 0;
  *((_QWORD *)v6 + 6) = 0;
  *((_DWORD *)v6 + 8) = 0;
  v10 = _wfopen(FileName, L"r");
  *((_QWORD *)v6 + 3) = v10;
  if ( v10 )
  {
    *a2 = v6;
    return 0;
  }
  v7 = *_errno();
  v11 = v7 < 0;
  if ( v7 > 0 )
  {
    v7 = (unsigned __int16)v7 | 0x80070000;
    v11 = v7 < 0;
  }
  if ( v11 )
    goto LABEL_8;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14003f0cc  mov     [rsp+arg_0], rbx
0x14003f0d1  mov     [rsp+arg_8], rsi
0x14003f0d6  push    rdi
0x14003f0d7  sub     rsp, 20h
0x14003f0db  mov     rbx, rdx
0x14003f0de  mov     rsi, rcx
0x14003f0e1  call    cs:__imp_GetProcessHeap
0x14003f0e7  xor     edx, edx; dwFlags
0x14003f0e9  mov     rcx, rax; hHeap
0x14003f0ec  lea     r8d, [rdx+38h]; dwBytes
0x14003f0f0  call    cs:__imp_HeapAlloc
0x14003f0f6  mov     rdi, rax
0x14003f0f9  test    rax, rax
0x14003f0fc  jnz     short loc_14003F108
0x14003f0fe  mov     ebx, 8007000Eh
0x14003f103  jmp     loc_14003F1A9
0x14003f108  mov     qword ptr [rax+18h], 0
0x14003f110  mov     qword ptr [rax+20h], 0
0x14003f118  mov     qword ptr [rax+28h], 0
0x14003f120  mov     qword ptr [rax+30h], 0
0x14003f128  lea     rax, ?ArgpFileNextArg@@YAJPEAU_FILE_ARGUMENT_PARSING@@PEAPEAGPEAH@Z; ArgpFileNextArg(_FILE_ARGUMENT_PARSING *,ushort * *,int *)
0x14003f12f  mov     [rdi], rax
0x14003f132  lea     rax, ?ArgpFileNextArgParam@@YAJPEAU_FILE_ARGUMENT_PARSING@@PEAPEAG@Z; ArgpFileNextArgParam(_FILE_ARGUMENT_PARSING *,ushort * *)
0x14003f139  mov     [rdi+8], rax
0x14003f13d  lea     rax, ?ArgpFileCleanup@@YAXPEAU_FILE_ARGUMENT_PARSING@@@Z; ArgpFileCleanup(_FILE_ARGUMENT_PARSING *)
0x14003f144  mov     [rdi+10h], rax
0x14003f148  call    cs:__imp_GetProcessHeap
0x14003f14e  xor     edx, edx; dwFlags
0x14003f150  mov     r8d, 800h; dwBytes
0x14003f156  mov     rcx, rax; hHeap
0x14003f159  call    cs:__imp_HeapAlloc
0x14003f15f  mov     [rdi+28h], rax
0x14003f163  mov     rcx, rax
0x14003f166  test    rax, rax
0x14003f169  jz      short loc_14003F0FE
0x14003f16b  xor     eax, eax
0x14003f16d  lea     rdx, aR; "r"
0x14003f174  mov     [rcx], ax
0x14003f177  mov     rcx, rsi; FileName
0x14003f17a  mov     [rdi+30h], rax
0x14003f17e  mov     [rdi+20h], eax
0x14003f181  call    cs:__imp__wfopen
0x14003f187  mov     [rdi+18h], rax
0x14003f18b  test    rax, rax
0x14003f18e  jnz     short loc_14003F1B3
0x14003f190  call    cs:__imp__errno
0x14003f196  mov     ebx, [rax]
0x14003f198  test    ebx, ebx
0x14003f19a  jle     short loc_14003F1A7
0x14003f19c  movzx   ebx, bx
0x14003f19f  or      ebx, 80070000h
0x14003f1a5  test    ebx, ebx
0x14003f1a7  jns     short loc_14003F1B8
0x14003f1a9  mov     rcx, rdi; lpMem
0x14003f1ac  call    ?ArgpFileCleanup@@YAXPEAU_FILE_ARGUMENT_PARSING@@@Z; ArgpFileCleanup(_FILE_ARGUMENT_PARSING *)
0x14003f1b1  jmp     short loc_14003F1B8
0x14003f1b3  mov     [rbx], rdi
0x14003f1b6  xor     ebx, ebx
0x14003f1b8  mov     rsi, [rsp+28h+arg_8]
0x14003f1bd  mov     eax, ebx
0x14003f1bf  mov     rbx, [rsp+28h+arg_0]
0x14003f1c4  add     rsp, 20h
0x14003f1c8  pop     rdi
0x14003f1c9  retn
```
