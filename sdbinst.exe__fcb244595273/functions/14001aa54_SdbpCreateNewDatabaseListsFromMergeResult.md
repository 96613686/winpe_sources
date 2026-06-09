# SdbpCreateNewDatabaseListsFromMergeResult

- ea: `0x14001aa54`
- end: `0x14001adfe`
- name: `SdbpCreateNewDatabaseListsFromMergeResult`
- size: `938`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int64 *, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x14001d808`

## callees

- `0x140002212`
- `0x14001008c`
- `0x140013898`
- `0x140014380`
- `0x14001443c`
- `0x14001aa54`
- `0x14001ae04`
- `0x14002e3e2`
- `0x14002e3ee`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14001ad17`
- `ntdll!RtlAllocateHeap` at `0x14001ad17`
- `ntdll!RtlReAllocateHeap` at `0x14001ad3f`
- `ntdll!RtlReAllocateHeap` at `0x14001ad3f`

## string_xrefs

- `0x14001adcf`: `SdbpCreateNewDatabaseListsFromMergeResult`

## pseudocode

```c
__int64 __fastcall SdbpCreateNewDatabaseListsFromMergeResult(
        __int64 a1,
        __int64 a2,
        unsigned __int64 *a3,
        __int64 a4,
        __int64 a5,
        int a6)
{
  unsigned __int64 v6; // r10
  int v7; // ebp
  __int64 v9; // r9
  unsigned __int64 v10; // rcx
  int v11; // r15d
  unsigned __int64 v12; // rax
  unsigned int v13; // r13d
  __int64 v14; // r12
  unsigned int FirstTag; // esi
  int v16; // r14d
  int v17; // eax
  unsigned int v18; // ebx
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // r14
  unsigned __int16 *v21; // rsi
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // rcx
  unsigned int i; // eax
  unsigned int v25; // eax
  const wchar_t *StringTagPtr; // rax
  unsigned int v27; // eax
  __int64 v28; // rax
  unsigned __int16 *v29; // rcx
  __int64 v30; // rax
  int v31; // edx
  int v32; // r8d
  unsigned int v33; // ebx
  unsigned __int64 v34; // rcx
  int v35; // r15d
  unsigned __int64 v36; // rax
  unsigned __int64 v37; // r8
  char *v38; // rsi
  size_t v39; // rbx
  __int64 v40; // rax
  unsigned __int64 v41; // rsi
  unsigned __int64 v42; // rsi
  unsigned __int128 v43; // rax
  size_t v44; // rbp
  void *v45; // r8
  void *v46; // rcx
  PVOID v47; // rax
  PVOID Heap; // rbx
  unsigned __int64 v49; // rax
  unsigned __int64 v51; // [rsp+30h] [rbp-48h]
  __int64 v53; // [rsp+88h] [rbp+10h]
  unsigned __int64 *v54; // [rsp+90h] [rbp+18h]

  v54 = a3;
  v53 = a2;
  v6 = a3[2];
  v7 = 0;
  v9 = a1;
  if ( !v6 )
    return 0;
  v10 = 0;
  v11 = 0;
  v51 = 0;
  while ( 1 )
  {
    v12 = 0;
    if ( v10 < v6 )
    {
      if ( !is_mul_ok(a3[1], v10) || (v12 = a3[5] + a3[1] * v10, v12 < a3[5]) )
        v12 = 0;
      a2 = v53;
    }
    if ( *(_WORD *)(v12 + 14) == 4120 )
      goto LABEL_65;
    v13 = *(_DWORD *)(v12 + 4);
    v14 = a2;
    if ( !v13 )
    {
      v14 = v9;
      v13 = *(_DWORD *)v12;
    }
    FirstTag = SdbFindFirstTag(v14, v13, 28687);
    if ( FirstTag )
      break;
LABEL_19:
    if ( v11 )
    {
      v19 = *(_QWORD *)(a4 + 16);
      if ( v19 )
      {
        v20 = 0;
        while ( 1 )
        {
          v21 = 0;
          if ( v20 < v19 )
          {
            v22 = *(_QWORD *)(a4 + 8) * v20;
            if ( !is_mul_ok(*(_QWORD *)(a4 + 8), v20)
              || (v23 = *(_QWORD *)(a4 + 40), v21 = (unsigned __int16 *)(v23 + v22), v23 + v22 < v23) )
            {
              v21 = 0;
            }
          }
          for ( i = SdbFindFirstTag(v14, v13, 28687); ; i = SdbFindNextTag(v14, v13, v33) )
          {
            v33 = i;
            if ( !i )
              break;
            v25 = SdbFindFirstTag(v14, i, 24577);
            if ( v25 )
            {
              StringTagPtr = (const wchar_t *)SdbGetStringTagPtr(v14, v25);
              if ( StringTagPtr )
              {
                if ( !wcscmp_0(StringTagPtr, L"TagDatabaseWhenAllEntriesQualify") )
                {
                  v27 = SdbFindFirstTag(v14, v33, 24606);
                  if ( v27 )
                  {
                    v28 = SdbGetStringTagPtr(v14, v27);
                    if ( v28 )
                    {
                      v29 = v21;
                      v30 = v28 - (_QWORD)v21;
                      do
                      {
                        v31 = *(unsigned __int16 *)((char *)v29 + v30);
                        v32 = *v29 - v31;
                        if ( v32 )
                          break;
                        ++v29;
                      }
                      while ( v31 );
                      if ( !v32 )
                      {
                        v35 = 1;
                        goto LABEL_59;
                      }
                    }
                  }
                }
              }
            }
          }
          v34 = *(_QWORD *)(a4 + 16);
          v35 = 0;
          if ( v20 >= v34 )
            goto LABEL_59;
          v36 = *(_QWORD *)(a4 + 8) * v20;
          if ( !is_mul_ok(*(_QWORD *)(a4 + 8), v20) )
            goto LABEL_59;
          v37 = *(_QWORD *)(a4 + 40);
          v38 = (char *)(v37 + v36);
          if ( v37 + v36 < v37 )
            goto LABEL_59;
          v39 = v34 + ~v20;
          if ( !v39 )
            goto LABEL_46;
          v39 *= *(_QWORD *)(a4 + 8);
          if ( is_mul_ok(v34 + ~v20, *(_QWORD *)(a4 + 8)) )
          {
            v40 = *(_QWORD *)(a4 + 8) * (v20 + 1);
            if ( is_mul_ok(*(_QWORD *)(a4 + 8), v20 + 1) && v37 + v40 >= v37 )
              break;
          }
LABEL_59:
          v49 = v20 + 1;
          if ( !v35 )
            v49 = v20;
          v20 = v49;
          v19 = *(_QWORD *)(a4 + 16);
          if ( v20 >= v19 )
            goto LABEL_62;
        }
        memmove_0(v38, (const void *)(v37 + v40), v39);
LABEL_46:
        memset_0(&v38[v39], 0, *(_QWORD *)(a4 + 8));
        if ( --*(_QWORD *)(a4 + 16) > 0x10u )
        {
          v41 = *(_QWORD *)(a4 + 24);
          if ( *(_QWORD *)(a4 + 8) * v41 >= 0x400
            && *(_QWORD *)(a4 + 16) < v41 >> 2
            && is_mul_ok(v41, *(_QWORD *)(a4 + 8)) )
          {
            v42 = v41 >> 1;
            v43 = v42 * (unsigned __int128)*(unsigned __int64 *)(a4 + 8);
            v44 = v42 * *(_QWORD *)(a4 + 8);
            if ( is_mul_ok(v42, *(_QWORD *)(a4 + 8)) )
            {
              v45 = *(void **)(a4 + 40);
              v46 = *(void **)a4;
              if ( v45 )
              {
                Heap = RtlReAllocateHeap(v46, DWORD2(v43), v45, v42 * *(_QWORD *)(a4 + 8));
              }
              else
              {
                v47 = RtlAllocateHeap(v46, DWORD2(v43), v42 * *(_QWORD *)(a4 + 8));
                Heap = v47;
                if ( v47 )
                  memset_0(v47, 0, v44);
              }
              v7 = 0;
              if ( Heap )
              {
                *(_QWORD *)(a4 + 40) = Heap;
                *(_QWORD *)(a4 + 24) = v42;
              }
            }
            else
            {
              v7 = 0;
            }
          }
        }
        goto LABEL_59;
      }
    }
LABEL_62:
    if ( a6 && !*(_QWORD *)(a4 + 16) )
      return 0;
    a3 = v54;
    v11 = 1;
    v9 = a1;
LABEL_65:
    v6 = a3[2];
    v10 = v51 + 1;
    v51 = v10;
    if ( v10 >= v6 )
      return 0;
    a2 = v53;
  }
  if ( !a6 )
    v7 = a5;
  v16 = 0;
  if ( !v11 )
    v16 = a4;
  while ( 1 )
  {
    v17 = SdbpGatherDatabaseListsForMerge(v14, FirstTag, v16, v7, 0);
    v18 = v17;
    if ( v17 < 0 )
      break;
    FirstTag = SdbFindNextTag(v14, v13, FirstTag);
    if ( !FirstTag )
    {
      v7 = 0;
      goto LABEL_19;
    }
  }
  AslLogCallPrintf(
    1,
    "SdbpCreateNewDatabaseListsFromMergeResult",
    4302,
    "Failed to gather database list info [%x]",
    v17);
  return v18;
}

```

## disassembly

```asm
0x14001aa54  mov     rax, rsp
0x14001aa57  mov     [rax+20h], rbx
0x14001aa5b  mov     [rax+18h], r8
0x14001aa5f  mov     [rax+10h], rdx
0x14001aa63  mov     [rax+8], rcx
0x14001aa67  push    rbp
0x14001aa68  push    rsi
0x14001aa69  push    rdi
0x14001aa6a  push    r12
0x14001aa6c  push    r13
0x14001aa6e  push    r14
0x14001aa70  push    r15
0x14001aa72  sub     rsp, 40h
0x14001aa76  mov     r10, [r8+10h]
0x14001aa7a  xor     ebp, ebp
0x14001aa7c  mov     rdi, r9
0x14001aa7f  mov     r9, rcx
0x14001aa82  test    r10, r10
0x14001aa85  jz      loc_14001ADE2
0x14001aa8b  mov     ecx, ebp
0x14001aa8d  mov     r15d, ebp
0x14001aa90  mov     [rsp+78h+var_48], rcx
0x14001aa95  mov     rax, rbp
0x14001aa98  cmp     rcx, r10
0x14001aa9b  jnb     short loc_14001AABE
0x14001aa9d  mov     rax, rcx
0x14001aaa0  mul     qword ptr [r8+8]
0x14001aaa4  test    rdx, rdx
0x14001aaa7  jnz     short loc_14001AAB3
0x14001aaa9  add     rax, [r8+28h]
0x14001aaad  cmp     rax, [r8+28h]
0x14001aab1  jnb     short loc_14001AAB6
0x14001aab3  mov     rax, rbp
0x14001aab6  mov     rdx, [rsp+78h+arg_8]
0x14001aabe  mov     ecx, 1018h
0x14001aac3  cmp     [rax+0Eh], cx
0x14001aac7  jz      loc_14001AD9B
0x14001aacd  mov     r13d, [rax+4]
0x14001aad1  mov     r12, rdx
0x14001aad4  test    r13d, r13d
0x14001aad7  cmovz   r12, r9
0x14001aadb  jnz     short loc_14001AAE0
0x14001aadd  mov     r13d, [rax]
0x14001aae0  mov     r8d, 700Fh
0x14001aae6  mov     edx, r13d
0x14001aae9  mov     rcx, r12
0x14001aaec  call    SdbFindFirstTag
0x14001aaf1  mov     esi, eax
0x14001aaf3  test    eax, eax
0x14001aaf5  jz      short loc_14001AB4B
0x14001aaf7  cmp     [rsp+78h+arg_28], 0
0x14001aaff  cmovz   rbp, [rsp+78h+arg_20]
0x14001ab08  xor     r14d, r14d
0x14001ab0b  test    r15d, r15d
0x14001ab0e  cmovz   r14, rdi
0x14001ab12  mov     r9, rbp
0x14001ab15  mov     [rsp+78h+var_58], 0
0x14001ab1e  mov     r8, r14
0x14001ab21  mov     edx, esi
0x14001ab23  mov     rcx, r12
0x14001ab26  call    SdbpGatherDatabaseListsForMerge
0x14001ab2b  mov     ebx, eax
0x14001ab2d  test    eax, eax
0x14001ab2f  js      loc_14001ADBE
0x14001ab35  mov     r8d, esi
0x14001ab38  mov     edx, r13d
0x14001ab3b  mov     rcx, r12
0x14001ab3e  call    SdbFindNextTag
0x14001ab43  mov     esi, eax
0x14001ab45  test    eax, eax
0x14001ab47  jnz     short loc_14001AB12
0x14001ab49  xor     ebp, ebp
0x14001ab4b  test    r15d, r15d
0x14001ab4e  jz      loc_14001AD76
0x14001ab54  mov     rax, [rdi+10h]
0x14001ab58  test    rax, rax
0x14001ab5b  jz      loc_14001AD76
0x14001ab61  mov     r14, rbp
0x14001ab64  mov     rsi, rbp
0x14001ab67  cmp     r14, rax
0x14001ab6a  jnb     short loc_14001AB88
0x14001ab6c  mov     rax, r14
0x14001ab6f  mul     qword ptr [rdi+8]
0x14001ab73  test    rdx, rdx
0x14001ab76  jnz     short loc_14001AB85
0x14001ab78  mov     rcx, [rdi+28h]
0x14001ab7c  lea     rsi, [rcx+rax]
0x14001ab80  cmp     rsi, rcx
0x14001ab83  jnb     short loc_14001AB88
0x14001ab85  mov     rsi, rbp
0x14001ab88  mov     r8d, 700Fh
0x14001ab8e  mov     edx, r13d
0x14001ab91  mov     rcx, r12
0x14001ab94  call    SdbFindFirstTag
0x14001ab99  jmp     loc_14001AC29
0x14001ab9e  mov     r8d, 6001h
0x14001aba4  mov     edx, ebx
0x14001aba6  mov     rcx, r12
0x14001aba9  call    SdbFindFirstTag
0x14001abae  test    eax, eax
0x14001abb0  jz      short loc_14001AC1B
0x14001abb2  mov     edx, eax
0x14001abb4  mov     rcx, r12
0x14001abb7  call    SdbGetStringTagPtr
0x14001abbc  test    rax, rax
0x14001abbf  jz      short loc_14001AC1B
0x14001abc1  lea     rdx, aTagdatabasewhe_0; "TagDatabaseWhenAllEntriesQualify"
0x14001abc8  mov     rcx, rax; String1
0x14001abcb  call    wcscmp_0
0x14001abd0  test    eax, eax
0x14001abd2  jnz     short loc_14001AC1B
0x14001abd4  mov     r8d, 601Eh
0x14001abda  mov     edx, ebx
0x14001abdc  mov     rcx, r12
0x14001abdf  call    SdbFindFirstTag
0x14001abe4  test    eax, eax
0x14001abe6  jz      short loc_14001AC1B
0x14001abe8  mov     edx, eax
0x14001abea  mov     rcx, r12
0x14001abed  call    SdbGetStringTagPtr
0x14001abf2  test    rax, rax
0x14001abf5  jz      short loc_14001AC1B
0x14001abf7  mov     rcx, rsi
0x14001abfa  sub     rax, rsi
0x14001abfd  movzx   r8d, word ptr [rcx]
0x14001ac01  movzx   edx, word ptr [rcx+rax]
0x14001ac05  sub     r8d, edx
0x14001ac08  jnz     short loc_14001AC12
0x14001ac0a  add     rcx, 2
0x14001ac0e  test    edx, edx
0x14001ac10  jnz     short loc_14001ABFD
0x14001ac12  test    r8d, r8d
0x14001ac15  jz      loc_14001AD34
0x14001ac1b  mov     r8d, ebx
0x14001ac1e  mov     edx, r13d
0x14001ac21  mov     rcx, r12
0x14001ac24  call    SdbFindNextTag
0x14001ac29  mov     ebx, eax
0x14001ac2b  test    eax, eax
0x14001ac2d  jnz     loc_14001AB9E
0x14001ac33  mov     rcx, [rdi+10h]
0x14001ac37  mov     r15d, ebp
0x14001ac3a  cmp     r14, rcx
0x14001ac3d  jnb     loc_14001AD5B
0x14001ac43  mov     rax, r14
0x14001ac46  mul     qword ptr [rdi+8]
0x14001ac4a  test    rdx, rdx
0x14001ac4d  jnz     loc_14001AD5B
0x14001ac53  mov     r8, [rdi+28h]
0x14001ac57  lea     rsi, [r8+rax]
0x14001ac5b  cmp     rsi, r8
0x14001ac5e  jb      loc_14001AD5B
0x14001ac64  mov     rbx, r14
0x14001ac67  not     rbx
0x14001ac6a  add     rbx, rcx
0x14001ac6d  jz      short loc_14001ACAB
0x14001ac6f  mov     rax, [rdi+8]
0x14001ac73  mul     rbx
0x14001ac76  mov     rbx, rax
0x14001ac79  test    rdx, rdx
0x14001ac7c  jnz     loc_14001AD5B
0x14001ac82  lea     rax, [r14+1]
0x14001ac86  mul     qword ptr [rdi+8]
0x14001ac8a  test    rdx, rdx
0x14001ac8d  jnz     loc_14001AD5B
0x14001ac93  lea     rdx, [r8+rax]; Src
0x14001ac97  cmp     rdx, r8
0x14001ac9a  jb      loc_14001AD5B
0x14001aca0  mov     r8, rbx; Size
0x14001aca3  mov     rcx, rsi; void *
0x14001aca6  call    memmove_0
0x14001acab  mov     r8, [rdi+8]; Size
0x14001acaf  lea     rcx, [rsi+rbx]; void *
0x14001acb3  xor     edx, edx; Val
0x14001acb5  call    memset_0
0x14001acba  dec     qword ptr [rdi+10h]
0x14001acbe  cmp     qword ptr [rdi+10h], 10h
0x14001acc3  jbe     loc_14001AD5B
0x14001acc9  mov     rsi, [rdi+18h]
0x14001accd  mov     rax, rsi
0x14001acd0  imul    rax, [rdi+8]
0x14001acd5  cmp     rax, 400h
0x14001acdb  jb      short loc_14001AD5B
0x14001acdd  mov     rax, rsi
0x14001ace0  shr     rax, 2
0x14001ace4  cmp     [rdi+10h], rax
0x14001ace8  jnb     short loc_14001AD5B
0x14001acea  mov     rax, [rdi+8]
0x14001acee  mul     rsi
0x14001acf1  test    rdx, rdx
0x14001acf4  jnz     short loc_14001AD5B
0x14001acf6  mov     rax, [rdi+8]
0x14001acfa  shr     rsi, 1
0x14001acfd  mul     rsi
0x14001ad00  mov     rbp, rax
0x14001ad03  test    rdx, rdx
0x14001ad06  jnz     short loc_14001AD59
0x14001ad08  mov     r8, [rdi+28h]; Ptr
0x14001ad0c  mov     rcx, [rdi]; Heap
0x14001ad0f  test    r8, r8
0x14001ad12  jnz     short loc_14001AD3C
0x14001ad14  mov     r8, rax; Size
0x14001ad17  call    cs:__imp_RtlAllocateHeap
0x14001ad1d  mov     rbx, rax
0x14001ad20  test    rax, rax
0x14001ad23  jz      short loc_14001AD48
0x14001ad25  mov     r8, rbp; Size
0x14001ad28  xor     edx, edx; Val
0x14001ad2a  mov     rcx, rax; void *
0x14001ad2d  call    memset_0
0x14001ad32  jmp     short loc_14001AD48
0x14001ad34  mov     r15d, 1
0x14001ad3a  jmp     short loc_14001AD5B
0x14001ad3c  mov     r9, rbp; Size
0x14001ad3f  call    cs:__imp_RtlReAllocateHeap
0x14001ad45  mov     rbx, rax
0x14001ad48  xor     ebp, ebp
0x14001ad4a  test    rbx, rbx
0x14001ad4d  jz      short loc_14001AD5B
0x14001ad4f  mov     [rdi+28h], rbx
0x14001ad53  mov     [rdi+18h], rsi
0x14001ad57  jmp     short loc_14001AD5B
0x14001ad59  xor     ebp, ebp
0x14001ad5b  test    r15d, r15d
0x14001ad5e  lea     rax, [r14+1]
0x14001ad62  cmovz   rax, r14
0x14001ad66  mov     r14, rax
0x14001ad69  mov     rax, [rdi+10h]
0x14001ad6d  cmp     r14, rax
0x14001ad70  jb      loc_14001AB64
0x14001ad76  cmp     [rsp+78h+arg_28], ebp
0x14001ad7d  jz      short loc_14001AD85
0x14001ad7f  cmp     [rdi+10h], rbp
0x14001ad83  jz      short loc_14001ADE2
0x14001ad85  mov     r8, [rsp+78h+arg_10]
0x14001ad8d  mov     r15d, 1
0x14001ad93  mov     r9, [rsp+78h+arg_0]
0x14001ad9b  mov     rcx, [rsp+78h+var_48]
0x14001ada0  mov     r10, [r8+10h]
0x14001ada4  inc     rcx
0x14001ada7  mov     [rsp+78h+var_48], rcx
0x14001adac  cmp     rcx, r10
0x14001adaf  jnb     short loc_14001ADE2
0x14001adb1  mov     rdx, [rsp+78h+arg_8]
0x14001adb9  jmp     loc_14001AA95
0x14001adbe  lea     r9, aFailedToGather_0; "Failed to gather database list info [%x"...
0x14001adc5  mov     dword ptr [rsp+78h+var_58], eax
0x14001adc9  mov     r8d, 10CEh
0x14001adcf  lea     rdx, aSdbpcreatenewd; "SdbpCreateNewDatabaseListsFromMergeResu"...
0x14001add6  mov     ecx, 1
0x14001addb  call    AslLogCallPrintf
0x14001ade0  jmp     short loc_14001ADE4
0x14001ade2  mov     ebx, ebp
0x14001ade4  mov     eax, ebx
0x14001ade6  mov     rbx, [rsp+78h+arg_18]
0x14001adee  add     rsp, 40h
0x14001adf2  pop     r15
0x14001adf4  pop     r14
0x14001adf6  pop     r13
0x14001adf8  pop     r12
0x14001adfa  pop     rdi
0x14001adfb  pop     rsi
0x14001adfc  pop     rbp
0x14001adfd  retn
```
