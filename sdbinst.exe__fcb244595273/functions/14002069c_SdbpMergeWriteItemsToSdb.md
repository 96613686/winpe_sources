# SdbpMergeWriteItemsToSdb

- ea: `0x14002069c`
- end: `0x1400207c4`
- name: `SdbpMergeWriteItemsToSdb`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14001d808`

## callees

- `0x14001008c`
- `0x14001b1f0`
- `0x14001c730`
- `0x14002069c`

## string_xrefs

- `0x14002079f`: `SdbpMergeCopyItemToSdb failed to copy entry item`
- `0x1400207ac`: `SdbpMergeWriteItemsToSdb`

## pseudocode

```c
__int64 __fastcall SdbpMergeWriteItemsToSdb(
        unsigned __int64 *a1,
        __int64 a2,
        __int64 **a3,
        __int64 a4,
        unsigned __int64 *a5)
{
  unsigned __int64 v5; // rax
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // rbx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rcx
  __int64 *v13; // rax
  __int64 v14; // rcx
  __int64 *v15; // r9
  int v16; // r8d
  int v17; // ebp
  __int128 v19; // [rsp+30h] [rbp-38h] BYREF

  v5 = a1[2];
  v19 = 0;
  if ( !v5 )
    return 0;
  v9 = 0;
  while ( 1 )
  {
    v10 = 0;
    if ( v9 < v5 )
    {
      v11 = a1[1] * v9;
      if ( !is_mul_ok(a1[1], v9) || (v12 = a1[5], v10 = v12 + v11, v12 + v11 < v12) )
        v10 = 0;
    }
    if ( *(_WORD *)(v10 + 14) == 4120 )
      goto LABEL_13;
    if ( *(_DWORD *)(v10 + 4) )
    {
      v13 = a3[1];
      DWORD2(v19) = *(_DWORD *)(v10 + 4);
      v14 = *v13;
    }
    else
    {
      v14 = **a3;
      DWORD2(v19) = *(_DWORD *)v10;
    }
    v15 = a3[2];
    *(_QWORD *)&v19 = v14;
    SdbpMergeActivateDeActivateItemIndexes(v10, 1, a2, *v15);
    v17 = SdbpMergeCopyItemToSdb((__int64 *)&v19, 0, v16, a3, a5);
    if ( !v17 )
      break;
    SdbpMergeActivateDeActivateItemIndexes(v10, 0, a2, *a3[2]);
    *(_DWORD *)(v10 + 52) = v17;
LABEL_13:
    v5 = a1[2];
    if ( ++v9 >= v5 )
      return 0;
  }
  AslLogCallPrintf(1, "SdbpMergeWriteItemsToSdb", 1775, "SdbpMergeCopyItemToSdb failed to copy entry item");
  return 3221225701LL;
}

```

## disassembly

```asm
0x14002069c  mov     [rsp+arg_8], rbx
0x1400206a1  mov     [rsp+arg_10], rbp
0x1400206a6  push    rsi
0x1400206a7  push    rdi
0x1400206a8  push    r12
0x1400206aa  push    r14
0x1400206ac  push    r15
0x1400206ae  sub     rsp, 40h
0x1400206b2  mov     rax, [rcx+10h]
0x1400206b6  xorps   xmm0, xmm0
0x1400206b9  mov     r14, r8
0x1400206bc  mov     r15, rdx
0x1400206bf  mov     rsi, rcx
0x1400206c2  movups  [rsp+68h+var_38], xmm0
0x1400206c7  test    rax, rax
0x1400206ca  jz      loc_140020784
0x1400206d0  mov     r12, [rsp+68h+arg_20]
0x1400206d8  xor     edi, edi
0x1400206da  xor     ebx, ebx
0x1400206dc  cmp     rdi, rax
0x1400206df  jnb     short loc_1400206FC
0x1400206e1  mov     rax, rdi
0x1400206e4  mul     qword ptr [rsi+8]
0x1400206e8  test    rdx, rdx
0x1400206eb  jnz     short loc_1400206FA
0x1400206ed  mov     rcx, [rsi+28h]
0x1400206f1  lea     rbx, [rcx+rax]
0x1400206f5  cmp     rbx, rcx
0x1400206f8  jnb     short loc_1400206FC
0x1400206fa  xor     ebx, ebx
0x1400206fc  mov     eax, 1018h
0x140020701  cmp     [rbx+0Eh], ax
0x140020705  jz      short loc_140020774
0x140020707  mov     edx, [rbx+4]
0x14002070a  test    edx, edx
0x14002070c  jz      short loc_14002071B
0x14002070e  mov     rax, [r14+8]
0x140020712  mov     dword ptr [rsp+68h+var_38+8], edx
0x140020716  mov     rcx, [rax]
0x140020719  jmp     short loc_140020727
0x14002071b  mov     rax, [r14]
0x14002071e  mov     rcx, [rax]
0x140020721  mov     eax, [rbx]
0x140020723  mov     dword ptr [rsp+68h+var_38+8], eax
0x140020727  mov     r9, [r14+10h]
0x14002072b  mov     r8, r15
0x14002072e  mov     qword ptr [rsp+68h+var_38], rcx
0x140020733  mov     edx, 1
0x140020738  mov     rcx, rbx
0x14002073b  mov     r9, [r9]
0x14002073e  call    SdbpMergeActivateDeActivateItemIndexes
0x140020743  xor     edx, edx
0x140020745  mov     [rsp+68h+var_48], r12
0x14002074a  lea     rcx, [rsp+68h+var_38]
0x14002074f  mov     r9, r14
0x140020752  call    SdbpMergeCopyItemToSdb
0x140020757  mov     ebp, eax
0x140020759  test    eax, eax
0x14002075b  jz      short loc_14002079F
0x14002075d  mov     r9, [r14+10h]
0x140020761  mov     r8, r15
0x140020764  xor     edx, edx
0x140020766  mov     rcx, rbx
0x140020769  mov     r9, [r9]
0x14002076c  call    SdbpMergeActivateDeActivateItemIndexes
0x140020771  mov     [rbx+34h], ebp
0x140020774  mov     rax, [rsi+10h]
0x140020778  inc     rdi
0x14002077b  cmp     rdi, rax
0x14002077e  jb      loc_1400206DA
0x140020784  xor     eax, eax
0x140020786  lea     r11, [rsp+68h+var_28]
0x14002078b  mov     rbx, [r11+38h]
0x14002078f  mov     rbp, [r11+40h]
0x140020793  mov     rsp, r11
0x140020796  pop     r15
0x140020798  pop     r14
0x14002079a  pop     r12
0x14002079c  pop     rdi
0x14002079d  pop     rsi
0x14002079e  retn
0x14002079f  lea     r9, aSdbpmergecopyi_0; "SdbpMergeCopyItemToSdb failed to copy e"...
0x1400207a6  mov     r8d, 6EFh
0x1400207ac  lea     rdx, aSdbpmergewrite_6; "SdbpMergeWriteItemsToSdb"
0x1400207b3  mov     ecx, 1
0x1400207b8  call    AslLogCallPrintf
0x1400207bd  mov     eax, 0C00000E5h
0x1400207c2  jmp     short loc_140020786
```
