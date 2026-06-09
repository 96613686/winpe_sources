# ArgpReadArgumentParams(_ARGUMENT_INPUT *,ARGUMENT *,unsigned __int64,ushort const *,int)

- ea: `0x14003e608`
- end: `0x14003e7db`
- name: `?ArgpReadArgumentParams@@YAJPEAU_ARGUMENT_INPUT@@PEAVARGUMENT@@_KPEBGH@Z`
- size: `467`
- prototype: `int(struct _ARGUMENT_INPUT *, struct ARGUMENT *, unsigned __int64, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14003c1ac`

## callees

- `0x14003b898`
- `0x14003d4f0`
- `0x14003e564`
- `0x14003e608`
- `0x14003e7e4`
- `0x14003e954`
- `0x14003eb98`
- `0x14003ecb4`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003e7bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003e7bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003e7ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003e7ae`

## pseudocode

```c
__int64 __fastcall ArgpReadArgumentParams(
        __int64 (__fastcall **a1)(struct _ARGUMENT_INPUT *, LPVOID *, unsigned __int64, const unsigned __int16 *),
        struct ARGUMENT *a2,
        unsigned __int64 a3,
        const unsigned __int16 *a4,
        int a5)
{
  int v9; // ebx
  int v10; // eax
  __int64 v11; // r8
  int String; // eax
  void *v13; // rdi
  HANDLE ProcessHeap; // rax
  LPVOID lpMem[2]; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v16; // [rsp+60h] [rbp+30h] BYREF

  lpMem[0] = 0;
  v16 = 0;
  if ( a3 < 0x80 )
    return 2147942487LL;
  if ( (*((_BYTE *)a2 + 44) & 0x10) != 0 )
  {
    *((_DWORD *)a2 + 21) = 1;
    g_Debug = 1;
  }
  if ( !*((_DWORD *)a2 + 10) || *((_DWORD *)a2 + 26) && (*((_DWORD *)a2 + 11) & 0x100) != 0 )
    return 0;
  if ( !a5 )
  {
    v10 = a1[1]((struct _ARGUMENT_INPUT *)a1, lpMem, a3, a4);
    v9 = v10;
    if ( v10 < 0 )
      goto LABEL_36;
    if ( v10 == 1 )
    {
      if ( (*((_BYTE *)a2 + 44) & 2) == 0 )
      {
        v11 = (unsigned int)(v10 + 55);
        if ( *((_DWORD *)a2 + 9) != v10 )
          v11 = (unsigned int)(v10 + 47);
        ArgPrintMessage(0, 0x3C34u, *(_QWORD *)((char *)a2 + v11));
        v9 = -2147024809;
        goto LABEL_36;
      }
      goto LABEL_35;
    }
LABEL_17:
    switch ( *((_DWORD *)a2 + 10) )
    {
      case 1:
        if ( a3 != 136 )
          goto LABEL_32;
        String = ArgpReadString(lpMem[0], a2);
        break;
      case 2:
        if ( a3 != 136 )
          goto LABEL_32;
        String = ArgpReadMultiString(a1, lpMem[0], a2);
        break;
      case 3:
        if ( a3 != 144 )
          goto LABEL_32;
        String = ArgpReadTime(lpMem[0], a2);
        break;
      case 4:
        if ( a3 != 144 )
          goto LABEL_32;
        String = ArgpReadDate(a1, lpMem[0], a2);
        break;
      case 5:
        if ( a3 == 136 )
        {
          v9 = ArgpParseNumber((OLECHAR *)lpMem[0], &v16);
          if ( v9 < 0 )
            goto LABEL_36;
          *((_DWORD *)a2 + 32) = v16;
LABEL_35:
          v9 = 0;
          goto LABEL_36;
        }
LABEL_32:
        v9 = -2147467259;
        goto LABEL_36;
      default:
        goto LABEL_35;
    }
    v9 = String;
    if ( String < 0 )
      goto LABEL_36;
    goto LABEL_35;
  }
  lpMem[0] = ArgDuplicateString(a4);
  if ( lpMem[0] )
    goto LABEL_17;
  v9 = -2147024882;
LABEL_36:
  v13 = lpMem[0];
  if ( lpMem[0] )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v13);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14003e608  mov     [rsp-18h+arg_0], rbx
0x14003e60d  mov     [rsp-18h+arg_8], rsi
0x14003e612  push    rbp
0x14003e613  push    rdi
0x14003e614  push    r14
0x14003e616  mov     rbp, rsp
0x14003e619  sub     rsp, 30h
0x14003e61d  mov     [rbp+lpMem], 0
0x14003e625  mov     rsi, r8
0x14003e628  mov     [rbp+arg_10], 0
0x14003e62f  mov     rdi, rdx
0x14003e632  mov     r14, rcx
0x14003e635  cmp     r8, 80h
0x14003e63c  jnb     short loc_14003E648
0x14003e63e  mov     eax, 80070057h
0x14003e643  jmp     loc_14003E7C8
0x14003e648  test    byte ptr [rdx+2Ch], 10h
0x14003e64c  jz      short loc_14003E65F
0x14003e64e  mov     dword ptr [rdx+54h], 1
0x14003e655  mov     cs:?g_Debug@@3HA, 1; int g_Debug
0x14003e65f  cmp     dword ptr [rdx+28h], 0
0x14003e663  jz      loc_14003E7C6
0x14003e669  cmp     dword ptr [rdx+68h], 0
0x14003e66d  jz      short loc_14003E67C
0x14003e66f  test    dword ptr [rdx+2Ch], 100h
0x14003e676  jnz     loc_14003E7C6
0x14003e67c  cmp     [rbp+arg_20], 0
0x14003e680  jz      short loc_14003E69D
0x14003e682  mov     rcx, r9; Src
0x14003e685  call    ?ArgDuplicateString@@YAPEAGPEBG@Z; ArgDuplicateString(ushort const *)
0x14003e68a  mov     [rbp+lpMem], rax
0x14003e68e  test    rax, rax
0x14003e691  jnz     short loc_14003E6EB
0x14003e693  mov     ebx, 8007000Eh
0x14003e698  jmp     loc_14003E7A5
0x14003e69d  mov     rax, [rcx+8]
0x14003e6a1  lea     rdx, [rbp+lpMem]
0x14003e6a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e6aa  mov     ebx, eax
0x14003e6ac  test    eax, eax
0x14003e6ae  js      loc_14003E7A5
0x14003e6b4  cmp     eax, 1
0x14003e6b7  jnz     short loc_14003E6EB
0x14003e6b9  test    byte ptr [rdi+2Ch], 2
0x14003e6bd  jnz     loc_14003E7A3
0x14003e6c3  cmp     [rdi+24h], ebx
0x14003e6c6  lea     eax, [rbx+2Fh]
0x14003e6c9  lea     r8d, [rbx+37h]
0x14003e6cd  mov     edx, 3C34h; uID
0x14003e6d2  cmovnz  r8d, eax
0x14003e6d6  xor     ecx, ecx; unsigned int *
0x14003e6d8  mov     r8, [r8+rdi]
0x14003e6dc  call    ?ArgPrintMessage@@YAJPEAKIZZ; ArgPrintMessage(ulong *,uint,...)
0x14003e6e1  mov     ebx, 80070057h
0x14003e6e6  jmp     loc_14003E7A5
0x14003e6eb  mov     ecx, [rdi+28h]
0x14003e6ee  sub     ecx, 1
0x14003e6f1  jz      loc_14003E781
0x14003e6f7  sub     ecx, 1
0x14003e6fa  jz      short loc_14003E767
0x14003e6fc  sub     ecx, 1
0x14003e6ff  jz      short loc_14003E750
0x14003e701  sub     ecx, 1
0x14003e704  jz      short loc_14003E736
0x14003e706  cmp     ecx, 1
0x14003e709  jnz     loc_14003E7A3
0x14003e70f  cmp     rsi, 88h
0x14003e716  jnz     short loc_14003E78A
0x14003e718  mov     rcx, [rbp+lpMem]; psz
0x14003e71c  lea     rdx, [rbp+arg_10]; unsigned int *
0x14003e720  call    ?ArgpParseNumber@@YAJPEBGPEAK@Z; ArgpParseNumber(ushort const *,ulong *)
0x14003e725  mov     ebx, eax
0x14003e727  test    eax, eax
0x14003e729  js      short loc_14003E7A5
0x14003e72b  mov     eax, [rbp+arg_10]
0x14003e72e  mov     [rdi+80h], eax
0x14003e734  jmp     short loc_14003E7A3
0x14003e736  cmp     rsi, 90h
0x14003e73d  jnz     short loc_14003E78A
0x14003e73f  mov     rdx, [rbp+lpMem]
0x14003e743  mov     r8, rdi
0x14003e746  mov     rcx, r14
0x14003e749  call    ?ArgpReadDate@@YAJPEAU_ARGUMENT_INPUT@@PEBGPEAV?$TYPED_ARGUMENT@U_SYSTEMTIME@@@@@Z; ArgpReadDate(_ARGUMENT_INPUT *,ushort const *,TYPED_ARGUMENT<_SYSTEMTIME> *)
0x14003e74e  jmp     short loc_14003E79D
0x14003e750  cmp     rsi, 90h
0x14003e757  jnz     short loc_14003E78A
0x14003e759  mov     rcx, [rbp+lpMem]
0x14003e75d  mov     rdx, rdi
0x14003e760  call    ?ArgpReadTime@@YAJPEBGPEAV?$TYPED_ARGUMENT@U_SYSTEMTIME@@@@@Z; ArgpReadTime(ushort const *,TYPED_ARGUMENT<_SYSTEMTIME> *)
0x14003e765  jmp     short loc_14003E79D
0x14003e767  cmp     rsi, 88h
0x14003e76e  jnz     short loc_14003E78A
0x14003e770  mov     rdx, [rbp+lpMem]
0x14003e774  mov     r8, rdi
0x14003e777  mov     rcx, r14
0x14003e77a  call    ?ArgpReadMultiString@@YAJPEAU_ARGUMENT_INPUT@@PEBGPEAV?$TYPED_ARGUMENT@PEAG@@@Z; ArgpReadMultiString(_ARGUMENT_INPUT *,ushort const *,TYPED_ARGUMENT<ushort *> *)
0x14003e77f  jmp     short loc_14003E79D
0x14003e781  cmp     rsi, 88h
0x14003e788  jz      short loc_14003E791
0x14003e78a  mov     ebx, 80004005h
0x14003e78f  jmp     short loc_14003E7A5
0x14003e791  mov     rcx, [rbp+lpMem]
0x14003e795  mov     rdx, rdi
0x14003e798  call    ?ArgpReadString@@YAJPEBGPEAV?$TYPED_ARGUMENT@PEAG@@@Z; ArgpReadString(ushort const *,TYPED_ARGUMENT<ushort *> *)
0x14003e79d  mov     ebx, eax
0x14003e79f  test    eax, eax
0x14003e7a1  js      short loc_14003E7A5
0x14003e7a3  xor     ebx, ebx
0x14003e7a5  mov     rdi, [rbp+lpMem]
0x14003e7a9  test    rdi, rdi
0x14003e7ac  jz      short loc_14003E7C2
0x14003e7ae  call    cs:__imp_GetProcessHeap
0x14003e7b4  mov     r8, rdi; lpMem
0x14003e7b7  xor     edx, edx; dwFlags
0x14003e7b9  mov     rcx, rax; hHeap
0x14003e7bc  call    cs:__imp_HeapFree
0x14003e7c2  mov     eax, ebx
0x14003e7c4  jmp     short loc_14003E7C8
0x14003e7c6  xor     eax, eax
0x14003e7c8  mov     rbx, [rsp+30h+arg_0]
0x14003e7cd  mov     rsi, [rsp+30h+arg_8]
0x14003e7d2  add     rsp, 30h
0x14003e7d6  pop     r14
0x14003e7d8  pop     rdi
0x14003e7d9  pop     rbp
0x14003e7da  retn
```
