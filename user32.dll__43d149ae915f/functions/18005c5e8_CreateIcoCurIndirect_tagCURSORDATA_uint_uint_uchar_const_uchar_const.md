# CreateIcoCurIndirect(tagCURSORDATA *,uint,uint,uchar const *,uchar const *)

- ea: `0x18005c5e8`
- end: `0x18005c879`
- name: `?CreateIcoCurIndirect@@YAPEAUHICON__@@PEAUtagCURSORDATA@@IIPEBE1@Z`
- size: `657`
- prototype: `HICON __usercall@<rax>(struct tagCURSORDATA *@<rcx>, UINT nPlanes@<edx>, UINT nBitCount@<r8d>, const unsigned __int8 *@<r9>, const unsigned __int8 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005c420`
- `0x18005c4f0`

## callees

- `0x180003b18`
- `0x180005f7c`
- `0x18005c5e8`
- `0x180096dad`

## import_xrefs

- `win32u!NtUserDestroyCursor` at `0x18005c63c`
- `win32u!NtUserDestroyCursor` at `0x18005c7cc`
- `win32u!NtUserDestroyCursor` at `0x18009ff4f`
- `win32u!NtUserDestroyCursor` at `0x18005c63c`
- `win32u!NtUserDestroyCursor` at `0x18005c7cc`
- `win32u!NtUserDestroyCursor` at `0x18009ff4f`
- `win32u!NtUserCreateEmptyCursorObject` at `0x18005c607`
- `win32u!NtUserCreateEmptyCursorObject` at `0x18005c607`
- `ntdll!RtlFreeHeap` at `0x18005c7b9`
- `ntdll!RtlFreeHeap` at `0x18005c7fe`
- `ntdll!RtlFreeHeap` at `0x18009ff37`
- `ntdll!RtlFreeHeap` at `0x18005c7b9`
- `ntdll!RtlFreeHeap` at `0x18005c7fe`
- `ntdll!RtlFreeHeap` at `0x18009ff37`
- `ntdll!RtlAllocateHeap` at `0x18005c689`
- `ntdll!RtlAllocateHeap` at `0x18009fee1`
- `ntdll!RtlAllocateHeap` at `0x18005c689`
- `ntdll!RtlAllocateHeap` at `0x18009fee1`
- `GDI32!CreateBitmap` at `0x18005c746`
- `GDI32!CreateBitmap` at `0x18005c84c`
- `GDI32!CreateBitmap` at `0x18009ff21`
- `GDI32!CreateBitmap` at `0x18005c746`
- `GDI32!CreateBitmap` at `0x18005c84c`
- `GDI32!CreateBitmap` at `0x18009ff21`
- `GDI32!DeleteObject` at `0x18005c7d6`
- `GDI32!DeleteObject` at `0x18005c863`
- `GDI32!DeleteObject` at `0x18005c86e`
- `GDI32!DeleteObject` at `0x18005c7d6`
- `GDI32!DeleteObject` at `0x18005c863`
- `GDI32!DeleteObject` at `0x18005c86e`

## pseudocode

```c
HICON __fastcall CreateIcoCurIndirect(
        struct tagCURSORDATA *a1,
        UINT nPlanes,
        UINT nBitCount,
        unsigned __int8 *a4,
        const unsigned __int8 *a5)
{
  HICON EmptyCursorObject; // rsi
  int *v9; // r15
  unsigned __int64 v10; // rcx
  unsigned __int64 v12; // rcx
  __int64 v13; // r14
  unsigned __int64 v14; // rax
  int v15; // r12d
  unsigned __int8 *Heap; // rax
  unsigned __int8 *v17; // rdi
  const unsigned __int8 *lpBits; // rcx
  int v19; // eax
  unsigned __int64 v20; // r14
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  size_t v23; // r15
  unsigned __int64 v24; // rax
  HBITMAP v25; // rax
  int v26; // r15d
  UINT v27; // ebp
  int ThreadDefCursorSize; // eax
  void *v29; // rcx
  HBITMAP v30; // rax
  PVOID v31; // rax
  void *v32; // rdi
  HBITMAP Bitmap; // rax
  PVOID v34; // rcx
  int nWidth; // [rsp+30h] [rbp-58h]

  EmptyCursorObject = (HICON)NtUserCreateEmptyCursorObject(0);
  if ( !EmptyCursorObject )
    return 0;
  v9 = (int *)((char *)a1 + 84);
  if ( (nBitCount | nPlanes) > 1 )
  {
    lpBits = a4;
    v17 = 0;
    v15 = 1;
  }
  else
  {
    v10 = (unsigned int)(*v9 + 15);
    if ( (unsigned int)v10 < *v9 )
      goto LABEL_4;
    v12 = *((unsigned int *)a1 + 22) * ((v10 >> 3) & 0x1FFFFFFE);
    if ( v12 > 0xFFFFFFFF )
      goto LABEL_4;
    v13 = (unsigned int)v12;
    v14 = 2LL * (unsigned int)v12;
    if ( v14 > 0xFFFFFFFF )
      goto LABEL_4;
    v15 = 0;
    Heap = (unsigned __int8 *)RtlAllocateHeap(pUserHeap, 8u, (unsigned int)v14);
    v17 = Heap;
    if ( !Heap )
      goto LABEL_4;
    memcpy_0(Heap, a4, (unsigned int)v13);
    memcpy_0(&v17[v13], a5, (unsigned int)v13);
    lpBits = v17;
    a4 = v17;
  }
  v19 = *v9;
  v20 = 2LL * *((unsigned int *)a1 + 22);
  *((_QWORD *)a1 + 4) = 0;
  nWidth = v19;
  if ( v20 > 0xFFFFFFFF )
  {
    LODWORD(v20) = -1;
LABEL_12:
    if ( v15 )
    {
      v21 = (unsigned int)(*v9 + 15);
      if ( (unsigned int)v21 < *v9 )
        goto LABEL_4;
      v22 = *((unsigned int *)a1 + 22) * ((v21 >> 3) & 0x1FFFFFFE);
      if ( v22 > 0xFFFFFFFF )
        goto LABEL_4;
      v23 = (unsigned int)v22;
      v24 = 2LL * (unsigned int)v22;
      if ( v24 > 0xFFFFFFFF )
        goto LABEL_4;
      v31 = RtlAllocateHeap(pUserHeap, 8u, (unsigned int)v24);
      v32 = v31;
      if ( !v31 )
        goto LABEL_4;
      memcpy_0(v31, a4, v23);
      v26 = nWidth;
      Bitmap = CreateBitmap(nWidth, v20, 1u, 1u, v32);
      v34 = pUserHeap;
      *((_QWORD *)a1 + 4) = Bitmap;
      RtlFreeHeap(v34, 0, v32);
      v17 = 0;
    }
    else
    {
      v26 = nWidth;
    }
    if ( !*((_QWORD *)a1 + 4) )
    {
      NtUserDestroyCursor(EmptyCursorObject, 0);
LABEL_27:
      if ( v17 )
        RtlFreeHeap(pUserHeap, 0, v17);
      return 0;
    }
    goto LABEL_19;
  }
  v25 = CreateBitmap(v19, v20, 1u, 1u, lpBits);
  *((_QWORD *)a1 + 4) = v25;
  if ( !v25 )
    goto LABEL_12;
  v26 = nWidth;
LABEL_19:
  if ( !v15 )
  {
    *((_QWORD *)a1 + 5) = 0;
    v27 = 1;
    goto LABEL_21;
  }
  v30 = CreateBitmap(v26, (unsigned int)v20 >> 1, nPlanes, nBitCount, a5);
  *((_QWORD *)a1 + 5) = v30;
  if ( !v30 )
  {
    DeleteObject(*((HGDIOBJ *)a1 + 4));
LABEL_4:
    NtUserDestroyCursor(EmptyCursorObject, 0);
    return 0;
  }
  v27 = nBitCount * nPlanes;
LABEL_21:
  *((_DWORD *)a1 + 20) = v27;
  *((_DWORD *)a1 + 22) = v20;
  *((_QWORD *)a1 + 1) = 0;
  *(_QWORD *)a1 = 0;
  *((_DWORD *)a1 + 6) = 0;
  ThreadDefCursorSize = GetThreadDefCursorSize();
  if ( !(unsigned int)_SetCursorIconData(EmptyCursorObject, a1, ThreadDefCursorSize) )
  {
    NtUserDestroyCursor(EmptyCursorObject, 0);
    DeleteObject(*((HGDIOBJ *)a1 + 4));
    v29 = (void *)*((_QWORD *)a1 + 5);
    if ( v29 )
      DeleteObject(v29);
    goto LABEL_27;
  }
  if ( v17 )
    RtlFreeHeap(pUserHeap, 0, v17);
  return EmptyCursorObject;
}

```

## disassembly

```asm
0x18005c5e8  mov     [rsp+Src], r9
0x18005c5ed  push    rbx
0x18005c5ee  push    rbp
0x18005c5ef  push    rsi
0x18005c5f0  push    rdi
0x18005c5f1  push    r12
0x18005c5f3  push    r13
0x18005c5f5  push    r14
0x18005c5f7  push    r15
0x18005c5f9  sub     rsp, 48h
0x18005c5fd  mov     rbx, rcx
0x18005c600  mov     r13d, r8d
0x18005c603  xor     ecx, ecx
0x18005c605  mov     ebp, edx
0x18005c607  call    cs:__imp_NtUserCreateEmptyCursorObject
0x18005c60d  mov     rsi, rax
0x18005c610  test    rax, rax
0x18005c613  jz      short loc_18005C642
0x18005c615  mov     edx, ebp
0x18005c617  lea     r15, [rbx+54h]
0x18005c61b  or      edx, r13d
0x18005c61e  mov     r8d, 0FFFFFFFFh
0x18005c624  cmp     edx, 1
0x18005c627  ja      loc_18005C809
0x18005c62d  mov     eax, [r15]
0x18005c630  lea     ecx, [rax+0Fh]
0x18005c633  cmp     ecx, eax
0x18005c635  jnb     short loc_18005C655
0x18005c637  xor     edx, edx
0x18005c639  mov     rcx, rsi
0x18005c63c  call    cs:__imp_NtUserDestroyCursor
0x18005c642  xor     eax, eax
0x18005c644  add     rsp, 48h
0x18005c648  pop     r15
0x18005c64a  pop     r14
0x18005c64c  pop     r13
0x18005c64e  pop     r12
0x18005c650  pop     rdi
0x18005c651  pop     rsi
0x18005c652  pop     rbp
0x18005c653  pop     rbx
0x18005c654  retn
0x18005c655  mov     eax, [rbx+58h]
0x18005c658  shr     rcx, 3
0x18005c65c  and     ecx, 1FFFFFFEh
0x18005c662  imul    rcx, rax
0x18005c666  cmp     rcx, r8
0x18005c669  ja      short loc_18005C637
0x18005c66b  mov     r14d, ecx
0x18005c66e  lea     rax, [r14+r14]
0x18005c672  cmp     rax, r8
0x18005c675  ja      short loc_18005C637
0x18005c677  mov     rcx, cs:pUserHeap; HeapHandle
0x18005c67e  xor     r12d, r12d
0x18005c681  mov     r8d, eax; Size
0x18005c684  lea     edx, [r12+8]; Flags
0x18005c689  call    cs:__imp_RtlAllocateHeap
0x18005c68f  mov     rdi, rax
0x18005c692  test    rax, rax
0x18005c695  jz      short loc_18005C637
0x18005c697  mov     rdx, [rsp+88h+Src]; Src
0x18005c69f  mov     r8d, r14d; Size
0x18005c6a2  mov     rcx, rax; void *
0x18005c6a5  call    memcpy_0
0x18005c6aa  mov     rdx, [rsp+88h+arg_20]; Src
0x18005c6b2  lea     rcx, [r14+rdi]; void *
0x18005c6b6  mov     r8d, r14d; Size
0x18005c6b9  call    memcpy_0
0x18005c6be  mov     rcx, rdi
0x18005c6c1  mov     r8d, 0FFFFFFFFh
0x18005c6c7  mov     [rsp+88h+Src], rcx
0x18005c6cf  mov     r14d, [rbx+58h]
0x18005c6d3  mov     eax, [r15]
0x18005c6d6  add     r14, r14
0x18005c6d9  mov     qword ptr [rbx+20h], 0
0x18005c6e1  mov     [rsp+88h+nWidth], eax
0x18005c6e5  cmp     r14, r8
0x18005c6e8  jbe     short loc_18005C733
0x18005c6ea  mov     r14d, r8d
0x18005c6ed  test    r12d, r12d
0x18005c6f0  jz      loc_18005C827
0x18005c6f6  mov     eax, [r15]
0x18005c6f9  lea     ecx, [rax+0Fh]
0x18005c6fc  cmp     ecx, eax
0x18005c6fe  jb      loc_18005C637
0x18005c704  mov     eax, [rbx+58h]
0x18005c707  shr     rcx, 3
0x18005c70b  and     ecx, 1FFFFFFEh
0x18005c711  imul    rcx, rax
0x18005c715  cmp     rcx, r8
0x18005c718  ja      loc_18005C637
0x18005c71e  mov     r15d, ecx
0x18005c721  lea     rax, [r15+r15]
0x18005c725  cmp     rax, r8
0x18005c728  ja      loc_18005C637
0x18005c72e  jmp     loc_18009FED2
0x18005c733  mov     r9d, 1; nBitCount
0x18005c739  mov     [rsp+88h+lpBits], rcx; lpBits
0x18005c73e  mov     r8d, r9d; nPlanes
0x18005c741  mov     edx, r14d; nHeight
0x18005c744  mov     ecx, eax; nWidth
0x18005c746  call    cs:__imp_CreateBitmap
0x18005c74c  mov     [rbx+20h], rax
0x18005c750  test    rax, rax
0x18005c753  jz      loc_18005C81C
0x18005c759  mov     r15d, [rsp+88h+nWidth]
0x18005c75e  test    r12d, r12d
0x18005c761  jnz     loc_18005C831
0x18005c767  mov     qword ptr [rbx+28h], 0
0x18005c76f  lea     ebp, [r12+1]
0x18005c774  mov     [rbx+50h], ebp
0x18005c777  mov     [rbx+58h], r14d
0x18005c77b  mov     qword ptr [rbx+8], 0
0x18005c783  mov     qword ptr [rbx], 0
0x18005c78a  mov     dword ptr [rbx+18h], 0
0x18005c791  call    ?GetThreadDefCursorSize@@YAHXZ; GetThreadDefCursorSize(void)
0x18005c796  mov     r8d, eax; int
0x18005c799  mov     rdx, rbx; struct tagCURSORDATA *
0x18005c79c  mov     rcx, rsi; HICON
0x18005c79f  call    ?_SetCursorIconData@@YAHPEAUHICON__@@PEAUtagCURSORDATA@@H@Z; _SetCursorIconData(HICON__ *,tagCURSORDATA *,int)
0x18005c7a4  test    eax, eax
0x18005c7a6  jz      short loc_18005C7C7
0x18005c7a8  test    rdi, rdi
0x18005c7ab  jz      short loc_18005C7BF
0x18005c7ad  mov     rcx, cs:pUserHeap; HeapHandle
0x18005c7b4  mov     r8, rdi; P
0x18005c7b7  xor     edx, edx; Flags
0x18005c7b9  call    cs:__imp_RtlFreeHeap
0x18005c7bf  mov     rax, rsi
0x18005c7c2  jmp     loc_18005C644
0x18005c7c7  xor     edx, edx
0x18005c7c9  mov     rcx, rsi
0x18005c7cc  call    cs:__imp_NtUserDestroyCursor
0x18005c7d2  mov     rcx, [rbx+20h]; ho
0x18005c7d6  call    cs:__imp_DeleteObject
0x18005c7dc  mov     rcx, [rbx+28h]; ho
0x18005c7e0  test    rcx, rcx
0x18005c7e3  jnz     loc_18005C86E
0x18005c7e9  test    rdi, rdi
0x18005c7ec  jz      loc_18005C642
0x18005c7f2  mov     rcx, cs:pUserHeap; HeapHandle
0x18005c7f9  mov     r8, rdi; P
0x18005c7fc  xor     edx, edx; Flags
0x18005c7fe  call    cs:__imp_RtlFreeHeap
0x18005c804  jmp     loc_18005C642
0x18005c809  mov     rcx, [rsp+88h+Src]
0x18005c811  xor     edi, edi
0x18005c813  lea     r12d, [rdi+1]
0x18005c817  jmp     loc_18005C6CF
0x18005c81c  mov     r8d, 0FFFFFFFFh
0x18005c822  jmp     loc_18005C6ED
0x18005c827  mov     r15d, [rsp+88h+nWidth]
0x18005c82c  jmp     loc_18009FF3F
0x18005c831  mov     rax, [rsp+88h+arg_20]
0x18005c839  mov     edx, r14d
0x18005c83c  shr     edx, 1; nHeight
0x18005c83e  mov     r9d, r13d; nBitCount
0x18005c841  mov     r8d, ebp; nPlanes
0x18005c844  mov     [rsp+88h+lpBits], rax; lpBits
0x18005c849  mov     ecx, r15d; nWidth
0x18005c84c  call    cs:__imp_CreateBitmap
0x18005c852  mov     [rbx+28h], rax
0x18005c856  test    rax, rax
0x18005c859  jnz     loc_18009FF5B
0x18005c85f  mov     rcx, [rbx+20h]; ho
0x18005c863  call    cs:__imp_DeleteObject
0x18005c869  jmp     loc_18005C637
0x18005c86e  call    cs:__imp_DeleteObject
0x18005c874  jmp     loc_18005C7E9
0x18009fed2  mov     rcx, cs:pUserHeap; HeapHandle
0x18009fed9  mov     edx, 8; Flags
0x18009fede  mov     r8d, eax; Size
0x18009fee1  call    cs:__imp_RtlAllocateHeap
0x18009fee7  mov     rdi, rax
0x18009feea  test    rax, rax
0x18009feed  jz      loc_18005C637
0x18009fef3  mov     rdx, [rsp+88h+Src]; Src
0x18009fefb  mov     r8, r15; Size
0x18009fefe  mov     rcx, rax; void *
0x18009ff01  call    memcpy_0
0x18009ff06  mov     r15d, [rsp+88h+nWidth]
0x18009ff0b  mov     eax, 1
0x18009ff10  mov     r9d, eax; nBitCount
0x18009ff13  mov     [rsp+88h+lpBits], rdi; lpBits
0x18009ff18  mov     r8d, eax; nPlanes
0x18009ff1b  mov     edx, r14d; nHeight
0x18009ff1e  mov     ecx, r15d; nWidth
0x18009ff21  call    cs:__imp_CreateBitmap
0x18009ff27  mov     rcx, cs:pUserHeap; HeapHandle
0x18009ff2e  mov     r8, rdi; P
0x18009ff31  xor     edx, edx; Flags
0x18009ff33  mov     [rbx+20h], rax
0x18009ff37  call    cs:__imp_RtlFreeHeap
0x18009ff3d  xor     edi, edi
0x18009ff3f  cmp     qword ptr [rbx+20h], 0
0x18009ff44  jnz     loc_18005C75E
0x18009ff4a  xor     edx, edx
0x18009ff4c  mov     rcx, rsi
0x18009ff4f  call    cs:__imp_NtUserDestroyCursor
0x18009ff55  nop
0x18009ff56  jmp     loc_18005C7E9
0x18009ff5b  imul    ebp, r13d
0x18009ff5f  jmp     loc_18005C774
```
