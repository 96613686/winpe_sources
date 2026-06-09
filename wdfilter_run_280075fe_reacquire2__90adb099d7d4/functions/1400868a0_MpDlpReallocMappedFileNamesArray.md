# MpDlpReallocMappedFileNamesArray

- ea: `0x1400868a0`
- end: `0x140086a80`
- name: `MpDlpReallocMappedFileNamesArray`
- size: `480`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14007451c`

## callees

- `0x1400026c0`
- `0x1400102e8`
- `0x140011890`
- `0x140011900`
- `0x140011bc0`
- `0x1400868a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140086a31`
- `ntoskrnl!ExFreePoolWithTag` at `0x140086a31`
- `ntoskrnl!ExQueryDepthSList` at `0x1400869e7`
- `ntoskrnl!ExQueryDepthSList` at `0x1400869e7`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140086a17`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140086a17`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400868e1`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400868e1`

## pseudocode

```c
__int64 __fastcall MpDlpReallocMappedFileNamesArray(unsigned __int16 *a1, unsigned int a2)
{
  size_t v2; // rsi
  int v4; // r12d
  union _SLIST_HEADER *v5; // rbx
  int v6; // edx
  PSLIST_ENTRY PoolWithTag; // rbp
  int v8; // r8d
  __int64 result; // rax
  unsigned int v10; // eax
  struct _SLIST_ENTRY *v11; // r15
  char *v12; // r14
  USHORT v13; // bx
  USHORT DepthSList; // ax

  v2 = a2;
  v4 = 1;
  if ( a2 > 0x400 )
  {
    _mm_lfence();
    PoolWithTag = (PSLIST_ENTRY)MpAllocatePoolWithTag(1, a2, 1718440013);
  }
  else
  {
    v5 = (union _SLIST_HEADER *)MpDlpData;
    ++*((_DWORD *)MpDlpData + 17);
    PoolWithTag = ExpInterlockedPopEntrySList(v5 + 3);
    if ( !PoolWithTag )
    {
      ++*((_DWORD *)&v5[4].HeaderX64 + 2);
      PoolWithTag = (PSLIST_ENTRY)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, union _SLIST_HEADER *))v5[6].Alignment)(
                                    *((unsigned int *)&v5[5].HeaderX64 + 1),
                                    *((unsigned int *)&v5[5].HeaderX64 + 3),
                                    *((unsigned int *)&v5[5].HeaderX64 + 2),
                                    &v5[3]);
    }
    if ( PoolWithTag )
      memset(PoolWithTag, 0, v2);
    LODWORD(v2) = 1024;
    v4 = 3;
  }
  if ( !PoolWithTag )
    return 3221225626LL;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_qqDDZDD(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      v8,
      (unsigned int)KeGetCurrentThread(),
      (__int64)a1,
      *((_DWORD *)a1 + 5),
      v2,
      (__int64)a1,
      *((_DWORD *)a1 + 4),
      v4);
  if ( *a1 )
    memmove(PoolWithTag, *((const void **)a1 + 1), *a1);
  v10 = *((_DWORD *)a1 + 4);
  if ( (v10 & 1) != 0 )
  {
    v11 = (struct _SLIST_ENTRY *)*((_QWORD *)a1 + 1);
    if ( (v10 & 2) != 0 )
    {
      v12 = (char *)MpDlpData + 48;
      ++*((_DWORD *)MpDlpData + 19);
      v13 = *((_WORD *)v12 + 8);
      DepthSList = ExQueryDepthSList((PSLIST_HEADER)v12);
      _mm_lfence();
      if ( DepthSList < v13 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)v12, v11);
      }
      else
      {
        ++*((_DWORD *)v12 + 8);
        (*((void (__fastcall **)(struct _SLIST_ENTRY *, char *))v12 + 7))(v11, v12);
      }
      *((_DWORD *)a1 + 4) &= ~2u;
    }
    else
    {
      ExFreePoolWithTag(*((PVOID *)a1 + 1), 0x666D504Du);
    }
    v10 = *((_DWORD *)a1 + 4) & 0xFFFFFFFE;
  }
  *((_DWORD *)a1 + 5) = v2;
  *((_DWORD *)a1 + 4) = v4 | v10;
  *((_QWORD *)a1 + 1) = PoolWithTag;
  if ( (unsigned int)v2 > 0xFFFE )
    LOWORD(v2) = -2;
  result = 0;
  a1[1] = v2;
  return result;
}

```

## disassembly

```asm
0x1400868a0  mov     rax, rsp
0x1400868a3  mov     [rax+8], rbx
0x1400868a7  mov     [rax+10h], rbp
0x1400868ab  mov     [rax+18h], rsi
0x1400868af  mov     [rax+20h], rdi
0x1400868b3  push    r12
0x1400868b5  push    r14
0x1400868b7  push    r15
0x1400868b9  sub     rsp, 50h
0x1400868bd  mov     r15d, 400h
0x1400868c3  mov     esi, edx
0x1400868c5  mov     rdi, rcx
0x1400868c8  mov     r12d, 1
0x1400868ce  cmp     edx, r15d
0x1400868d1  ja      short loc_140086930
0x1400868d3  mov     rbx, cs:MpDlpData
0x1400868da  inc     dword ptr [rbx+44h]
0x1400868dd  lea     rcx, [rbx+30h]; ListHead
0x1400868e1  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400868e8  nop     dword ptr [rax+rax+00h]
0x1400868ed  mov     rbp, rax
0x1400868f0  test    rax, rax
0x1400868f3  jnz     short loc_140086913
0x1400868f5  inc     dword ptr [rbx+48h]
0x1400868f8  lea     r9, [rbx+30h]
0x1400868fc  mov     edx, [rbx+5Ch]
0x1400868ff  mov     rax, [rbx+60h]
0x140086903  mov     r8d, [rbx+58h]
0x140086907  mov     ecx, [rbx+54h]
0x14008690a  call    cs:__guard_dispatch_icall_fptr
0x140086910  mov     rbp, rax
0x140086913  test    rbp, rbp
0x140086916  jz      short loc_140086925
0x140086918  mov     r8, rsi; Size
0x14008691b  xor     edx, edx; Val
0x14008691d  mov     rcx, rbp; void *
0x140086920  call    memset
0x140086925  mov     esi, r15d
0x140086928  mov     r12d, 3
0x14008692e  jmp     short loc_140086947
0x140086930  lfence
0x140086933  mov     rdx, rsi
0x140086936  mov     ecx, r12d
0x140086939  mov     r8d, 666D504Dh
0x14008693f  call    MpAllocatePoolWithTag
0x140086944  mov     rbp, rax
0x140086947  test    rbp, rbp
0x14008694a  jnz     short loc_140086956
0x14008694c  mov     eax, 0C000009Ah
0x140086951  jmp     loc_140086A60
0x140086956  mov     rax, cs:WPP_GLOBAL_Control
0x14008695d  lea     rcx, WPP_GLOBAL_Control
0x140086964  cmp     rax, rcx
0x140086967  jz      short loc_1400869AA
0x140086969  mov     eax, [rax+2Ch]
0x14008696c  test    al, 1
0x14008696e  jz      short loc_1400869AA
0x140086970  mov     r9, gs:188h
0x140086979  mov     eax, [rdi+10h]
0x14008697c  mov     rcx, cs:WPP_GLOBAL_Control
0x140086983  mov     [rsp+68h+var_20], r12d
0x140086988  mov     [rsp+68h+var_28], eax
0x14008698c  mov     eax, [rdi+14h]
0x14008698f  mov     rcx, [rcx+18h]
0x140086993  mov     [rsp+68h+var_30], rdi
0x140086998  mov     [rsp+68h+var_38], esi
0x14008699c  mov     [rsp+68h+var_40], eax
0x1400869a0  mov     [rsp+68h+var_48], rdi
0x1400869a5  call    WPP_SF_qqDDZDD
0x1400869aa  movzx   eax, word ptr [rdi]
0x1400869ad  test    ax, ax
0x1400869b0  jz      short loc_1400869C1
0x1400869b2  mov     rdx, [rdi+8]; Src
0x1400869b6  mov     r8d, eax; Size
0x1400869b9  mov     rcx, rbp; void *
0x1400869bc  call    memmove
0x1400869c1  mov     eax, [rdi+10h]
0x1400869c4  test    al, 1
0x1400869c6  jz      short loc_140086A43
0x1400869c8  mov     r15, [rdi+8]
0x1400869cc  test    al, 2
0x1400869ce  jz      short loc_140086A29
0x1400869d0  mov     r14, cs:MpDlpData
0x1400869d7  add     r14, 30h ; '0'
0x1400869db  mov     rcx, r14; SListHead
0x1400869de  inc     dword ptr [r14+1Ch]
0x1400869e2  movzx   ebx, word ptr [r14+10h]
0x1400869e7  call    cs:__imp_ExQueryDepthSList
0x1400869ee  nop     dword ptr [rax+rax+00h]
0x1400869f3  lfence
0x1400869f6  cmp     ax, bx
0x1400869f9  jb      short loc_140086A11
0x1400869fb  inc     dword ptr [r14+20h]
0x1400869ff  mov     rdx, r14
0x140086a02  mov     rax, [r14+38h]
0x140086a06  mov     rcx, r15
0x140086a09  call    cs:__guard_dispatch_icall_fptr
0x140086a0f  jmp     short loc_140086A23
0x140086a11  mov     rdx, r15; ListEntry
0x140086a14  mov     rcx, r14; ListHead
0x140086a17  call    cs:__imp_ExpInterlockedPushEntrySList
0x140086a1e  nop     dword ptr [rax+rax+00h]
0x140086a23  and     dword ptr [rdi+10h], 0FFFFFFFDh
0x140086a27  jmp     short loc_140086A3D
0x140086a29  mov     edx, 666D504Dh; Tag
0x140086a2e  mov     rcx, r15; P
0x140086a31  call    cs:__imp_ExFreePoolWithTag
0x140086a38  nop     dword ptr [rax+rax+00h]
0x140086a3d  mov     eax, [rdi+10h]
0x140086a40  and     eax, 0FFFFFFFEh
0x140086a43  or      eax, r12d
0x140086a46  mov     [rdi+14h], esi
0x140086a49  mov     [rdi+10h], eax
0x140086a4c  mov     eax, 0FFFEh
0x140086a51  cmp     esi, eax
0x140086a53  mov     [rdi+8], rbp
0x140086a57  cmova   esi, eax
0x140086a5a  xor     eax, eax
0x140086a5c  mov     [rdi+2], si
0x140086a60  lea     r11, [rsp+68h+var_18]
0x140086a65  mov     rbx, [r11+20h]
0x140086a69  mov     rbp, [r11+28h]
0x140086a6d  mov     rsi, [r11+30h]
0x140086a71  mov     rdi, [r11+38h]
0x140086a75  mov     rsp, r11
0x140086a78  pop     r15
0x140086a7a  pop     r14
0x140086a7c  pop     r12
0x140086a7e  retn
```
