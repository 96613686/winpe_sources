# GetOutputStringFromPatternMatch(ushort *,unsigned __int64,ushort *,unsigned __int64,ushort *,ulong *)

- ea: `0x140019960`
- end: `0x140019ad3`
- name: `?GetOutputStringFromPatternMatch@@YAPEAGPEAG_K010PEAK@Z`
- size: `371`
- prototype: `unsigned __int16 *__fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14001a078`

## callees

- `0x1400196f0`
- `0x140019760`
- `0x140019960`
- `0x140019b1c`
- `0x140019b70`
- `0x140019e10`

## import_xrefs

- `msvcrt!wprintf` at `0x1400199f6`
- `msvcrt!wprintf` at `0x1400199f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140019ab0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140019ab0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400199a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140019aa2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400199a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140019aa2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400199b8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400199b8`

## string_xrefs

- `0x140019a6d`: `Mal-formed replacement string: %s\n`

## pseudocode

```c
unsigned __int16 *__fastcall GetOutputStringFromPatternMatch(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        unsigned __int64 a4,
        unsigned __int16 *a5,
        unsigned int *a6)
{
  unsigned __int16 *v6; // r12
  SIZE_T v7; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *result; // rax
  struct _STRING_TOKEN *v14; // rsi
  unsigned int v15; // eax
  unsigned int *v16; // rbx
  int v17; // edx
  unsigned __int16 *v18; // r8
  __int64 v19; // rcx
  unsigned int v20; // eax
  HANDLE v21; // rax
  unsigned int v22; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v23; // [rsp+34h] [rbp-24h] BYREF
  struct _LIST_ENTRY v24; // [rsp+38h] [rbp-20h] BYREF
  int v25; // [rsp+A8h] [rbp+50h] BYREF

  v6 = 0;
  v24.Blink = &v24;
  v7 = 8 * a2;
  v22 = 0;
  v24.Flink = &v24;
  v23 = 0;
  v25 = 0;
  ProcessHeap = GetProcessHeap();
  result = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v7);
  v14 = (struct _STRING_TOKEN *)result;
  if ( result )
  {
    v15 = ParsePatternString(a1, a2, &v25);
    v16 = a6;
    *a6 = v15;
    if ( v15
      || (v17 = v25,
          v18 = a5,
          v19 = v25 != 0 ? 2 : 0,
          a1[a2 - 1] = 0,
          v15 = PatternMatch((unsigned __int16 *)((char *)a1 + v19 + 2), v17, v18, 0, v14, &v22),
          (*v16 = v15) != 0) )
    {
      if ( v15 == 13 )
        wprintf(L"Mal-formed pattern string: %s\n", a1);
    }
    else
    {
      v20 = ParseReplacementString(a3, a4, &v24, v14, v22, &v23);
      *v16 = v20;
      if ( v20 )
      {
        if ( v20 == 13 )
          wprintf(L"Mal-formed replacement string: %s\n", a3);
      }
      else
      {
        v6 = GenerateOutputString(a5, a3, v14, v23, &v24, v16);
      }
    }
    a1[a2 - 1] = 47;
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v14);
    FreeReplaceTokenList(&v24);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x140019960  push    rbp
0x140019962  push    rbx
0x140019963  push    rsi
0x140019964  push    rdi
0x140019965  push    r12
0x140019967  push    r13
0x140019969  push    r14
0x14001996b  push    r15
0x14001996d  mov     rbp, rsp
0x140019970  sub     rsp, 58h
0x140019974  xor     r12d, r12d
0x140019977  lea     rax, [rbp+var_20]
0x14001997b  mov     [rbp+var_20.Blink], rax
0x14001997f  lea     rbx, ds:0[rdx*8]
0x140019987  lea     rax, [rbp+var_20]
0x14001998b  mov     [rbp+var_28], r12d
0x14001998f  mov     [rbp+var_20.Flink], rax
0x140019993  mov     r13, r9
0x140019996  mov     r14, r8
0x140019999  mov     [rbp+var_24], r12d
0x14001999d  mov     r15, rdx
0x1400199a0  mov     [rbp+arg_8], r12d
0x1400199a4  mov     rdi, rcx
0x1400199a7  call    cs:__imp_GetProcessHeap
0x1400199ad  mov     r8, rbx; dwBytes
0x1400199b0  lea     edx, [r12+8]; dwFlags
0x1400199b5  mov     rcx, rax; hHeap
0x1400199b8  call    cs:__imp_HeapAlloc
0x1400199be  mov     rsi, rax
0x1400199c1  test    rax, rax
0x1400199c4  jz      loc_140019AC2
0x1400199ca  lea     r8, [rbp+arg_8]; int *
0x1400199ce  mov     rdx, r15; unsigned __int64
0x1400199d1  mov     rcx, rdi; unsigned __int16 *
0x1400199d4  call    ?ParsePatternString@@YAKPEAG_KPEAH@Z; ParsePatternString(ushort *,unsigned __int64,int *)
0x1400199d9  mov     rbx, [rbp+arg_28]
0x1400199dd  mov     [rbx], eax
0x1400199df  test    eax, eax
0x1400199e1  jz      short loc_140019A01
0x1400199e3  cmp     eax, 0Dh
0x1400199e6  jnz     loc_140019A9A
0x1400199ec  mov     rdx, rdi
0x1400199ef  lea     rcx, aMalFormedPatte; "Mal-formed pattern string: %s\n"
0x1400199f6  call    cs:__imp_wprintf
0x1400199fc  jmp     loc_140019A9A
0x140019a01  mov     edx, [rbp+arg_8]; int
0x140019a04  mov     eax, edx
0x140019a06  mov     r8, [rbp+arg_20]; unsigned __int16 *
0x140019a0a  neg     eax
0x140019a0c  sbb     rcx, rcx
0x140019a0f  xor     eax, eax
0x140019a11  and     ecx, 2
0x140019a14  mov     [rdi+r15*2-2], ax
0x140019a1a  add     rcx, 2
0x140019a1e  lea     rax, [rbp+var_28]
0x140019a22  mov     [rsp+58h+var_30], rax; unsigned int *
0x140019a27  add     rcx, rdi; unsigned __int16 *
0x140019a2a  xor     r9d, r9d; unsigned int
0x140019a2d  mov     [rsp+58h+var_38], rsi; struct _STRING_TOKEN *
0x140019a32  call    ?PatternMatch@@YAKPEAGH0KPEAU_STRING_TOKEN@@PEAK@Z; PatternMatch(ushort *,int,ushort *,ulong,_STRING_TOKEN *,ulong *)
0x140019a37  mov     [rbx], eax
0x140019a39  test    eax, eax
0x140019a3b  jnz     short loc_1400199E3
0x140019a3d  lea     rax, [rbp+var_24]
0x140019a41  mov     r9, rsi; struct _STRING_TOKEN *
0x140019a44  mov     [rsp+58h+var_30], rax; unsigned int *
0x140019a49  lea     r8, [rbp+var_20]; struct _LIST_ENTRY *
0x140019a4d  mov     eax, [rbp+var_28]
0x140019a50  mov     rdx, r13; unsigned __int64
0x140019a53  mov     rcx, r14; unsigned __int16 *
0x140019a56  mov     dword ptr [rsp+58h+var_38], eax; unsigned int
0x140019a5a  call    ?ParseReplacementString@@YAKPEAG_KPEAU_LIST_ENTRY@@PEAU_STRING_TOKEN@@KPEAK@Z; ParseReplacementString(ushort *,unsigned __int64,_LIST_ENTRY *,_STRING_TOKEN *,ulong,ulong *)
0x140019a5f  mov     [rbx], eax
0x140019a61  test    eax, eax
0x140019a63  jz      short loc_140019A76
0x140019a65  cmp     eax, 0Dh
0x140019a68  jnz     short loc_140019A9A
0x140019a6a  mov     rdx, r14
0x140019a6d  lea     rcx, aMalFormedRepla; "Mal-formed replacement string: %s\n"
0x140019a74  jmp     short loc_1400199F6
0x140019a76  mov     r9d, [rbp+var_24]; unsigned int
0x140019a7a  lea     rax, [rbp+var_20]
0x140019a7e  mov     rcx, [rbp+arg_20]; unsigned __int16 *
0x140019a82  mov     r8, rsi; struct _STRING_TOKEN *
0x140019a85  mov     [rsp+58h+var_30], rbx; unsigned int *
0x140019a8a  mov     rdx, r14; unsigned __int16 *
0x140019a8d  mov     [rsp+58h+var_38], rax; struct _LIST_ENTRY *
0x140019a92  call    ?GenerateOutputString@@YAPEAGPEAG0PEAU_STRING_TOKEN@@KPEAU_LIST_ENTRY@@PEAK@Z; GenerateOutputString(ushort *,ushort *,_STRING_TOKEN *,ulong,_LIST_ENTRY *,ulong *)
0x140019a97  mov     r12, rax
0x140019a9a  mov     word ptr [rdi+r15*2-2], 2Fh ; '/'
0x140019aa2  call    cs:__imp_GetProcessHeap
0x140019aa8  mov     r8, rsi; lpMem
0x140019aab  xor     edx, edx; dwFlags
0x140019aad  mov     rcx, rax; hHeap
0x140019ab0  call    cs:__imp_HeapFree
0x140019ab6  lea     rcx, [rbp+var_20]; struct _LIST_ENTRY *
0x140019aba  call    ?FreeReplaceTokenList@@YAXPEAU_LIST_ENTRY@@@Z; FreeReplaceTokenList(_LIST_ENTRY *)
0x140019abf  mov     rax, r12
0x140019ac2  add     rsp, 58h
0x140019ac6  pop     r15
0x140019ac8  pop     r14
0x140019aca  pop     r13
0x140019acc  pop     r12
0x140019ace  pop     rdi
0x140019acf  pop     rsi
0x140019ad0  pop     rbx
0x140019ad1  pop     rbp
0x140019ad2  retn
```
