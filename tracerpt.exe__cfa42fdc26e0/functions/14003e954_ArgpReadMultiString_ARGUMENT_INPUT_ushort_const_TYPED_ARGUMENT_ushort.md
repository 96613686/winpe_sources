# ArgpReadMultiString(_ARGUMENT_INPUT *,ushort const *,TYPED_ARGUMENT<ushort *> *)

- ea: `0x14003e954`
- end: `0x14003eb8f`
- name: `?ArgpReadMultiString@@YAJPEAU_ARGUMENT_INPUT@@PEBGPEAV?$TYPED_ARGUMENT@PEAG@@@Z`
- size: `571`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14003e608`

## callees

- `0x14003b898`
- `0x14003dd0c`
- `0x14003e954`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003eae1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003eb36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003eb57`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003eae1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003eb36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003eb57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003e99a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003e9c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003ead3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003eb28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003eb49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003e99a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003e9c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003ead3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003eb28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003eb49`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003e9ab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003e9d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003e9ab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003e9d3`

## pseudocode

```c
__int64 __fastcall ArgpReadMultiString(__int64 a1, const unsigned __int16 *a2, __int64 a3)
{
  unsigned int v4; // ebx
  HANDLE ProcessHeap; // rax
  _WORD *v7; // rbp
  int v8; // edi
  unsigned __int64 v9; // rsi
  HANDLE v10; // rax
  __int16 *v11; // rcx
  int i; // edi
  int v13; // eax
  __int16 v14; // dx
  _WORD *v15; // r12
  int v16; // r14d
  _WORD *v17; // rdx
  __int64 v18; // rcx
  unsigned __int64 v19; // r8
  _WORD *v20; // rax
  __int64 v21; // r9
  _WORD *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r8
  void *v25; // rbx
  HANDLE v26; // rax
  int v27; // eax
  HANDLE v28; // rax
  void *v29; // rdi
  HANDLE v30; // rax
  bool v32; // zf
  LPVOID lpMem; // [rsp+88h] [rbp+20h] BYREF

  v4 = 0;
  lpMem = 0;
  lpMem = ArgDuplicateString(a2);
  if ( !lpMem )
    goto LABEL_2;
  if ( (*(_DWORD *)(a3 + 44) & 8) == 0 )
  {
    ProcessHeap = GetProcessHeap();
    v7 = HeapAlloc(ProcessHeap, 0, 0x1000u);
    if ( v7 )
    {
      v8 = 0;
      v9 = 2047;
      goto LABEL_13;
    }
LABEL_2:
    v4 = -2147024882;
    goto LABEL_38;
  }
  v10 = GetProcessHeap();
  v7 = HeapAlloc(v10, 0, 0x800u);
  if ( !v7 )
    goto LABEL_2;
  v11 = *(__int16 **)(a3 + 64);
  v9 = 1023;
  for ( i = 0; ; i = v13 )
  {
    v14 = *v11;
    if ( !*v11 )
      break;
    v13 = i + 1;
    ++v11;
    if ( v14 != 32 )
      v13 = i;
  }
  v8 = i + 1;
LABEL_13:
  v15 = v7;
  v16 = 0;
  do
  {
    if ( !v9 )
      goto LABEL_27;
    if ( v9 <= 0x7FFFFFFF )
    {
      v17 = lpMem;
      v18 = 2147483646;
      v19 = v9;
      v20 = v15;
      v21 = 0;
      do
      {
        if ( !v18 )
          break;
        if ( !*v17 )
          break;
        *v20++ = *v17++;
        --v18;
        ++v21;
        --v19;
      }
      while ( v19 );
      v22 = v20 - 1;
      v23 = v21 - 1;
      if ( v19 )
      {
        v22 = v20;
        v23 = v21;
      }
      v24 = -(__int64)v19;
      v9 -= v23;
      *v22 = 0;
      v15 += v23;
      if ( !v24 )
        v16 = -2147024774;
    }
    else
    {
      v16 = -2147024809;
      *v15 = 0;
    }
    if ( v9 )
    {
      ++v15;
      --v9;
      *v15 = 0;
    }
    else
    {
LABEL_27:
      v16 = -2147024774;
    }
    if ( (*(_BYTE *)(a3 + 44) & 8) != 0 && !--v8 )
      break;
    v25 = lpMem;
    if ( lpMem )
    {
      v26 = GetProcessHeap();
      HeapFree(v26, 0, v25);
      lpMem = 0;
    }
    v27 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(a1 + 8))(a1, &lpMem);
    v4 = v27;
    if ( v27 < 0 )
      goto LABEL_37;
    v4 = 0;
  }
  while ( v27 != 1 );
  if ( v16 < 0 )
  {
    v4 = v16;
LABEL_37:
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v7);
    goto LABEL_38;
  }
  v32 = *(_BYTE *)(a3 + 44) >= 0;
  *(_QWORD *)(a3 + 128) = v7;
  if ( !v32 )
    v4 = ArgExpandFiles((unsigned __int16 **)(a3 + 128), 1);
LABEL_38:
  v29 = lpMem;
  if ( lpMem )
  {
    v30 = GetProcessHeap();
    HeapFree(v30, 0, v29);
  }
  return v4;
}

```

## disassembly

```asm
0x14003e954  mov     rax, rsp
0x14003e957  push    rbx
0x14003e958  push    rbp
0x14003e959  push    rsi
0x14003e95a  push    rdi
0x14003e95b  push    r12
0x14003e95d  push    r13
0x14003e95f  push    r14
0x14003e961  push    r15
0x14003e963  sub     rsp, 28h
0x14003e967  mov     r13, rcx
0x14003e96a  xor     ebx, ebx
0x14003e96c  mov     rcx, rdx; Src
0x14003e96f  mov     [rax+20h], rbx
0x14003e973  mov     r15, r8
0x14003e976  call    ?ArgDuplicateString@@YAPEAGPEBG@Z; ArgDuplicateString(ushort const *)
0x14003e97b  mov     [rsp+68h+lpMem], rax
0x14003e983  test    rax, rax
0x14003e986  jnz     short loc_14003E992
0x14003e988  mov     ebx, 8007000Eh
0x14003e98d  jmp     loc_14003EB3C
0x14003e992  mov     eax, [r15+2Ch]
0x14003e996  test    al, 8
0x14003e998  jnz     short loc_14003E9C2
0x14003e99a  call    cs:__imp_GetProcessHeap
0x14003e9a0  xor     edx, edx; dwFlags
0x14003e9a2  mov     r8d, 1000h; dwBytes
0x14003e9a8  mov     rcx, rax; hHeap
0x14003e9ab  call    cs:__imp_HeapAlloc
0x14003e9b1  mov     rbp, rax
0x14003e9b4  test    rax, rax
0x14003e9b7  jz      short loc_14003E988
0x14003e9b9  mov     edi, ebx
0x14003e9bb  mov     esi, 7FFh
0x14003e9c0  jmp     short loc_14003EA08
0x14003e9c2  call    cs:__imp_GetProcessHeap
0x14003e9c8  xor     edx, edx; dwFlags
0x14003e9ca  mov     r8d, 800h; dwBytes
0x14003e9d0  mov     rcx, rax; hHeap
0x14003e9d3  call    cs:__imp_HeapAlloc
0x14003e9d9  mov     rbp, rax
0x14003e9dc  test    rax, rax
0x14003e9df  jz      short loc_14003E988
0x14003e9e1  mov     rcx, [r15+40h]
0x14003e9e5  mov     esi, 3FFh
0x14003e9ea  mov     edi, ebx
0x14003e9ec  jmp     short loc_14003E9FE
0x14003e9ee  lea     eax, [rdi+1]
0x14003e9f1  cmp     dx, 20h ; ' '
0x14003e9f5  lea     rcx, [rcx+2]
0x14003e9f9  cmovnz  eax, edi
0x14003e9fc  mov     edi, eax
0x14003e9fe  movzx   edx, word ptr [rcx]
0x14003ea01  test    dx, dx
0x14003ea04  jnz     short loc_14003E9EE
0x14003ea06  inc     edi
0x14003ea08  mov     r12, rbp
0x14003ea0b  mov     r14d, ebx
0x14003ea0e  test    rsi, rsi
0x14003ea11  jz      short loc_14003EA91
0x14003ea13  cmp     rsi, 7FFFFFFFh
0x14003ea1a  jbe     short loc_14003EA24
0x14003ea1c  mov     r14d, 80070057h
0x14003ea22  jmp     short loc_14003EA9C
0x14003ea24  mov     rdx, [rsp+68h+lpMem]
0x14003ea2c  mov     ecx, 7FFFFFFEh
0x14003ea31  mov     r8, rsi
0x14003ea34  mov     rax, r12
0x14003ea37  mov     r9, rbx
0x14003ea3a  test    rcx, rcx
0x14003ea3d  jz      short loc_14003EA61
0x14003ea3f  movzx   r10d, word ptr [rdx]
0x14003ea43  test    r10w, r10w
0x14003ea47  jz      short loc_14003EA61
0x14003ea49  mov     [rax], r10w
0x14003ea4d  add     rdx, 2
0x14003ea51  add     rax, 2
0x14003ea55  dec     rcx
0x14003ea58  inc     r9
0x14003ea5b  sub     r8, 1
0x14003ea5f  jnz     short loc_14003EA3A
0x14003ea61  test    r8, r8
0x14003ea64  lea     rcx, [rax-2]
0x14003ea68  lea     rdx, [r9-1]
0x14003ea6c  cmovnz  rcx, rax
0x14003ea70  cmovnz  rdx, r9
0x14003ea74  neg     r8
0x14003ea77  sbb     eax, eax
0x14003ea79  sub     rsi, rdx
0x14003ea7c  not     eax
0x14003ea7e  mov     [rcx], bx
0x14003ea81  lea     r12, [r12+rdx*2]
0x14003ea85  and     eax, 8007007Ah
0x14003ea8a  jns     short loc_14003EAA1
0x14003ea8c  mov     r14d, eax
0x14003ea8f  jmp     short loc_14003EAA1
0x14003ea91  mov     r14d, 80070057h
0x14003ea97  test    rsi, rsi
0x14003ea9a  jz      short loc_14003EAA6
0x14003ea9c  mov     [r12], bx
0x14003eaa1  test    rsi, rsi
0x14003eaa4  jnz     short loc_14003EAAE
0x14003eaa6  mov     r14d, 8007007Ah
0x14003eaac  jmp     short loc_14003EABA
0x14003eaae  add     r12, 2
0x14003eab2  dec     rsi
0x14003eab5  mov     [r12], bx
0x14003eaba  test    byte ptr [r15+2Ch], 8
0x14003eabf  jz      short loc_14003EAC6
0x14003eac1  sub     edi, 1
0x14003eac4  jz      short loc_14003EB1B
0x14003eac6  mov     rbx, [rsp+68h+lpMem]
0x14003eace  test    rbx, rbx
0x14003ead1  jz      short loc_14003EAF3
0x14003ead3  call    cs:__imp_GetProcessHeap
0x14003ead9  mov     r8, rbx; lpMem
0x14003eadc  xor     edx, edx; dwFlags
0x14003eade  mov     rcx, rax; hHeap
0x14003eae1  call    cs:__imp_HeapFree
0x14003eae7  mov     [rsp+68h+lpMem], 0
0x14003eaf3  mov     rax, [r13+8]
0x14003eaf7  lea     rdx, [rsp+68h+lpMem]
0x14003eaff  mov     rcx, r13
0x14003eb02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003eb07  mov     ebx, eax
0x14003eb09  test    eax, eax
0x14003eb0b  js      short loc_14003EB23
0x14003eb0d  mov     ebx, 0
0x14003eb12  cmp     eax, 1
0x14003eb15  jnz     loc_14003EA0E
0x14003eb1b  test    r14d, r14d
0x14003eb1e  jns     short loc_14003EB70
0x14003eb20  mov     ebx, r14d
0x14003eb23  test    rbp, rbp
0x14003eb26  jz      short loc_14003EB3C
0x14003eb28  call    cs:__imp_GetProcessHeap
0x14003eb2e  mov     r8, rbp; lpMem
0x14003eb31  xor     edx, edx; dwFlags
0x14003eb33  mov     rcx, rax; hHeap
0x14003eb36  call    cs:__imp_HeapFree
0x14003eb3c  mov     rdi, [rsp+68h+lpMem]
0x14003eb44  test    rdi, rdi
0x14003eb47  jz      short loc_14003EB5D
0x14003eb49  call    cs:__imp_GetProcessHeap
0x14003eb4f  mov     r8, rdi; lpMem
0x14003eb52  xor     edx, edx; dwFlags
0x14003eb54  mov     rcx, rax; hHeap
0x14003eb57  call    cs:__imp_HeapFree
0x14003eb5d  mov     eax, ebx
0x14003eb5f  add     rsp, 28h
0x14003eb63  pop     r15
0x14003eb65  pop     r14
0x14003eb67  pop     r13
0x14003eb69  pop     r12
0x14003eb6b  pop     rdi
0x14003eb6c  pop     rsi
0x14003eb6d  pop     rbp
0x14003eb6e  pop     rbx
0x14003eb6f  retn
0x14003eb70  test    byte ptr [r15+2Ch], 80h
0x14003eb75  lea     rcx, [r15+80h]; unsigned __int16 **
0x14003eb7c  mov     [rcx], rbp
0x14003eb7f  jz      short loc_14003EB3C
0x14003eb81  mov     edx, 1; int
0x14003eb86  call    ?ArgExpandFiles@@YAJPEAPEAGH@Z; ArgExpandFiles(ushort * *,int)
0x14003eb8b  mov     ebx, eax
0x14003eb8d  jmp     short loc_14003EB3C
```
