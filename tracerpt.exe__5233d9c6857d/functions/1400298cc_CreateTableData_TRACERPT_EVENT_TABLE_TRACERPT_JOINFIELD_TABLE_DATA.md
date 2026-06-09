# CreateTableData(_TRACERPT_EVENT_TABLE *,_TRACERPT_JOINFIELD *,_TABLE_DATA *)

- ea: `0x1400298cc`
- end: `0x140029c42`
- name: `?CreateTableData@@YAKPEAU_TRACERPT_EVENT_TABLE@@PEAU_TRACERPT_JOINFIELD@@PEAU_TABLE_DATA@@@Z`
- size: `886`
- prototype: `unsigned int(struct _TRACERPT_EVENT_TABLE *, struct _TRACERPT_JOINFIELD *, struct _TABLE_DATA *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14002b5d8`

## callees

- `0x140004cac`
- `0x140029320`
- `0x1400298cc`
- `0x14002a1e0`
- `0x14002aa44`
- `0x14002dcec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400299f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029a33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029a84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400299f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029a33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029a84`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140029a04`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140029a44`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140029a95`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140029a04`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140029a44`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140029a95`

## pseudocode

```c
__int64 __fastcall CreateTableData(
        struct _TRACERPT_EVENT_TABLE *a1,
        struct _TRACERPT_JOINFIELD *a2,
        struct _TABLE_DATA *a3)
{
  unsigned int v3; // esi
  struct _TABLE_DATA *v5; // r12
  char v7; // cl
  unsigned int v8; // edx
  char v9; // r15
  struct _EVENT_DESCRIPTOR *v10; // rbx
  const struct _GUID *v11; // rcx
  __int64 v12; // rax
  unsigned int v13; // ebp
  unsigned __int8 v14; // r15
  struct _MOF_INFO *MofInfoHead; // rax
  unsigned __int8 v16; // r9
  int v17; // r14d
  unsigned int v18; // r14d
  struct _MOF_VERSION **v19; // rbx
  struct _MOF_VERSION *v20; // r11
  const struct _EVENT_DESCRIPTOR *v21; // rdx
  struct _MOF_VERSION *v22; // rbp
  HANDLE ProcessHeap; // rax
  LPVOID v24; // rax
  unsigned int i; // ebp
  HANDLE v26; // rax
  LPVOID v27; // rax
  unsigned __int8 v28; // r9
  __int64 v29; // r15
  HANDLE v30; // rax
  LPVOID v31; // rax
  const struct _EVENT_DESCRIPTOR *v32; // rcx
  unsigned int v33; // ebp
  struct _MOF_VERSION *v34; // r12
  struct _MOF_VERSION *v35; // rsi
  unsigned __int8 v36; // r14
  struct _TABLE_DATA *v37; // r11
  int v38; // ebx
  struct _MOF_EVENT *v39; // rcx
  unsigned int v40; // r12d
  unsigned int v41; // eax
  bool v42; // cf
  __int64 v43; // r8
  struct _EVENT_DESCRIPTOR *v45; // [rsp+40h] [rbp-68h]
  struct _MOF_INFO *v46; // [rsp+48h] [rbp-60h]
  struct _LIST_ENTRY *v47; // [rsp+50h] [rbp-58h]
  unsigned __int8 v48; // [rsp+B0h] [rbp+8h]
  struct _MOF_EVENT *v49; // [rsp+B0h] [rbp+8h]
  unsigned int v50; // [rsp+B8h] [rbp+10h]
  struct _MOF_VERSION *v51; // [rsp+B8h] [rbp+10h]
  unsigned int v53; // [rsp+C8h] [rbp+20h]
  struct _MOF_VERSION *v54; // [rsp+C8h] [rbp+20h]

  v3 = *((_DWORD *)a1 + 8);
  v5 = a3;
  v7 = *((_BYTE *)a1 + 681) & 4;
  if ( v7 )
    v8 = *((_DWORD *)a1 + 150);
  else
    v8 = 0;
  v50 = v8;
  v47 = (struct _LIST_ENTRY *)(((unsigned __int64)a1 + 584) & -(__int64)(v7 != 0));
  if ( a2 )
  {
    v9 = *((_BYTE *)a2 + 69);
    v10 = (struct _EVENT_DESCRIPTOR *)((char *)a2 + 104);
    v11 = (const struct _GUID *)((char *)a2 + 88);
  }
  else
  {
    if ( !v3 )
      return 0;
    v12 = *((_QWORD *)a1 + 2);
    v9 = *(_BYTE *)(v12 + 245);
    v10 = (struct _EVENT_DESCRIPTOR *)(v12 + 280);
    v11 = (const struct _GUID *)(v12 + 264);
  }
  v13 = *((_DWORD *)a1 + 9);
  v14 = v9 & 1;
  v48 = v14;
  v45 = v10;
  v53 = v13;
  MofInfoHead = GetMofInfoHead(v11);
  v46 = MofInfoHead;
  if ( !MofInfoHead )
    goto LABEL_53;
  if ( !a2 && !*((_DWORD *)a1 + 9) )
  {
    v17 = *((_DWORD *)a1 + 51);
    if ( v17 )
    {
      v18 = v17 + 1;
      goto LABEL_19;
    }
  }
  v18 = 0;
  v19 = (struct _MOF_VERSION **)((char *)MofInfoHead + 16 * v10->Version + 64);
  v20 = *v19;
  if ( v19 == (struct _MOF_VERSION **)*v19 )
  {
LABEL_53:
    CleanupTableData(v5);
    return 0;
  }
  v21 = v45;
  do
  {
    v22 = v20;
    if ( FindMatchMofVersion(v20, v21, v14, v16) )
      v18 += *((_DWORD *)v22 + 11);
  }
  while ( v19 != (struct _MOF_VERSION **)v20 );
  v13 = v53;
LABEL_19:
  if ( !v18 )
    goto LABEL_53;
  ProcessHeap = GetProcessHeap();
  v24 = HeapAlloc(ProcessHeap, 8u, 32LL * v18);
  *((_QWORD *)v5 + 1) = v24;
  if ( !v24 )
    goto LABEL_53;
  *(_DWORD *)v5 = v18;
  if ( a2 || v13 > 1 )
    ++v3;
  for ( i = 0; i < v18; ++i )
  {
    v26 = GetProcessHeap();
    v27 = HeapAlloc(v26, 8u, 32LL * v3);
    if ( !v27 )
    {
LABEL_52:
      v5 = a3;
      goto LABEL_53;
    }
    v29 = 32LL * i;
    *(_DWORD *)(v29 + *((_QWORD *)a3 + 1)) = v3;
    *(_QWORD *)(v29 + *((_QWORD *)a3 + 1) + 8) = v27;
    if ( v50 )
    {
      v30 = GetProcessHeap();
      v31 = HeapAlloc(v30, 8u, 32LL * v50);
      if ( !v31 )
        goto LABEL_52;
      *(_DWORD *)(v29 + *((_QWORD *)a3 + 1) + 16) = v50;
      *(_QWORD *)(v29 + *((_QWORD *)a3 + 1) + 24) = v31;
    }
  }
  v32 = v45;
  v33 = 0;
  v34 = (struct _MOF_INFO *)((char *)v46 + 16 * v45->Version + 64);
  v51 = v34;
  v35 = *(struct _MOF_VERSION **)v34;
  if ( v34 != *(struct _MOF_VERSION **)v34 )
  {
    v36 = v48;
    do
    {
      v54 = *(struct _MOF_VERSION **)v35;
      if ( FindMatchMofVersion(v35, v32, v36, v28) )
      {
        v38 = 0;
        v39 = (struct _MOF_EVENT *)*((_QWORD *)v35 + 6);
        if ( (struct _MOF_VERSION *)((char *)v35 + 48) != v39 )
        {
          while ( 1 )
          {
            v40 = v38 + v33;
            v49 = *(struct _MOF_EVENT **)v39;
            if ( !FillEventToRowData(
                    v46,
                    v35,
                    v39,
                    a2,
                    (struct _LIST_ENTRY *)a1 + 1,
                    v47,
                    (struct _ROW_DATA *)(*((_QWORD *)v37 + 1) + 32LL * (v38 + v33))) )
              goto LABEL_52;
            if ( *((_DWORD *)a1 + 9) || a2 || (v41 = *((_DWORD *)a1 + 51)) == 0 )
            {
              v5 = a3;
            }
            else
            {
              if ( *((_QWORD *)a1 + 7) )
              {
                v43 = v40;
                v5 = a3;
                v38 += SortRowData(a1, a3, v43);
                goto LABEL_46;
              }
              v42 = v40 < v41;
              v5 = a3;
              if ( !v42 )
                goto LABEL_47;
            }
            ++v38;
LABEL_46:
            v39 = v49;
            if ( (struct _MOF_VERSION *)((char *)v35 + 48) == v49 )
            {
LABEL_47:
              if ( v38 < 0 )
                goto LABEL_53;
              v34 = v51;
              break;
            }
            v37 = a3;
          }
        }
        v33 += v38;
      }
      v35 = v54;
      v32 = v45;
    }
    while ( v34 != v54 );
  }
  return v33;
}

```

## disassembly

```asm
0x1400298cc  mov     [rsp+arg_10], r8
0x1400298d1  push    rbx
0x1400298d2  push    rbp
0x1400298d3  push    rsi
0x1400298d4  push    rdi
0x1400298d5  push    r12
0x1400298d7  push    r13
0x1400298d9  push    r14
0x1400298db  push    r15
0x1400298dd  sub     rsp, 68h
0x1400298e1  mov     esi, [rcx+20h]
0x1400298e4  mov     rdi, rcx
0x1400298e7  mov     cl, [rcx+2A9h]
0x1400298ed  mov     r12, r8
0x1400298f0  mov     r13, rdx
0x1400298f3  and     cl, 4
0x1400298f6  jz      short loc_140029900
0x1400298f8  mov     edx, [rdi+258h]
0x1400298fe  jmp     short loc_140029902
0x140029900  xor     edx, edx
0x140029902  neg     cl
0x140029904  mov     dword ptr [rsp+0A8h+arg_8], edx
0x14002990b  lea     rax, [rdi+248h]
0x140029912  sbb     rcx, rcx
0x140029915  and     rcx, rax
0x140029918  mov     [rsp+0A8h+var_58], rcx
0x14002991d  test    r13, r13
0x140029920  jz      short loc_140029930
0x140029922  mov     r15b, [r13+45h]
0x140029926  lea     rbx, [r13+68h]
0x14002992a  lea     rcx, [r13+58h]
0x14002992e  jmp     short loc_140029951
0x140029930  test    esi, esi
0x140029932  jz      loc_140029C2F
0x140029938  mov     rax, [rdi+10h]
0x14002993c  mov     r15b, [rax+0F5h]
0x140029943  lea     rbx, [rax+118h]
0x14002994a  lea     rcx, [rax+108h]; struct _GUID *
0x140029951  mov     ebp, [rdi+24h]
0x140029954  and     r15b, 1
0x140029958  mov     [rsp+0A8h+arg_0], r15b
0x140029960  mov     [rsp+0A8h+var_68], rbx
0x140029965  mov     dword ptr [rsp+0A8h+arg_18], ebp
0x14002996c  call    ?GetMofInfoHead@@YAPEAU_MOF_INFO@@PEBU_GUID@@@Z; GetMofInfoHead(_GUID const *)
0x140029971  mov     [rsp+0A8h+var_60], rax
0x140029976  test    rax, rax
0x140029979  jz      loc_140029C27
0x14002997f  test    r13, r13
0x140029982  jnz     short loc_14002999B
0x140029984  cmp     [rdi+24h], r13d
0x140029988  jnz     short loc_14002999B
0x14002998a  mov     r14d, [rdi+0CCh]
0x140029991  test    r14d, r14d
0x140029994  jz      short loc_14002999B
0x140029996  inc     r14d
0x140029999  jmp     short loc_1400299E3
0x14002999b  movzx   ebx, byte ptr [rbx+2]
0x14002999f  xor     r14d, r14d
0x1400299a2  add     rbx, 4
0x1400299a6  shl     rbx, 4
0x1400299aa  add     rbx, rax
0x1400299ad  mov     r11, [rbx]
0x1400299b0  cmp     rbx, r11
0x1400299b3  jz      loc_140029C27
0x1400299b9  mov     rdx, [rsp+0A8h+var_68]; struct _EVENT_DESCRIPTOR *
0x1400299be  mov     rbp, r11
0x1400299c1  mov     r8b, r15b; unsigned __int8
0x1400299c4  mov     r11, [r11]
0x1400299c7  mov     rcx, rbp; struct _MOF_VERSION *
0x1400299ca  call    ?FindMatchMofVersion@@YAEPEAU_MOF_VERSION@@PEBU_EVENT_DESCRIPTOR@@EE@Z; FindMatchMofVersion(_MOF_VERSION *,_EVENT_DESCRIPTOR const *,uchar,uchar)
0x1400299cf  test    al, al
0x1400299d1  jz      short loc_1400299D7
0x1400299d3  add     r14d, [rbp+2Ch]
0x1400299d7  cmp     rbx, r11
0x1400299da  jnz     short loc_1400299BE
0x1400299dc  mov     ebp, dword ptr [rsp+0A8h+arg_18]
0x1400299e3  test    r14d, r14d
0x1400299e6  jz      loc_140029C27
0x1400299ec  mov     ebx, r14d
0x1400299ef  shl     rbx, 5
0x1400299f3  call    cs:__imp_GetProcessHeap
0x1400299f9  mov     r8, rbx; dwBytes
0x1400299fc  mov     edx, 8; dwFlags
0x140029a01  mov     rcx, rax; hHeap
0x140029a04  call    cs:__imp_HeapAlloc
0x140029a0a  mov     [r12+8], rax
0x140029a0f  test    rax, rax
0x140029a12  jz      loc_140029C27
0x140029a18  mov     [r12], r14d
0x140029a1c  test    r13, r13
0x140029a1f  jnz     short loc_140029A26
0x140029a21  cmp     ebp, 1
0x140029a24  jbe     short loc_140029A28
0x140029a26  inc     esi
0x140029a28  mov     eax, esi
0x140029a2a  xor     ebp, ebp
0x140029a2c  mov     r12d, eax
0x140029a2f  shl     r12, 5
0x140029a33  call    cs:__imp_GetProcessHeap
0x140029a39  mov     r8, r12; dwBytes
0x140029a3c  mov     edx, 8; dwFlags
0x140029a41  mov     rcx, rax; hHeap
0x140029a44  call    cs:__imp_HeapAlloc
0x140029a4a  test    rax, rax
0x140029a4d  jz      loc_140029C1F
0x140029a53  mov     r11, [rsp+0A8h+arg_10]
0x140029a5b  mov     r15d, ebp
0x140029a5e  shl     r15, 5
0x140029a62  mov     rcx, [r11+8]
0x140029a66  mov     [r15+rcx], esi
0x140029a6a  mov     rcx, [r11+8]
0x140029a6e  mov     [r15+rcx+8], rax
0x140029a73  mov     eax, dword ptr [rsp+0A8h+arg_8]
0x140029a7a  test    eax, eax
0x140029a7c  jz      short loc_140029AC5
0x140029a7e  mov     ebx, eax
0x140029a80  shl     rbx, 5
0x140029a84  call    cs:__imp_GetProcessHeap
0x140029a8a  mov     r8, rbx; dwBytes
0x140029a8d  mov     edx, 8; dwFlags
0x140029a92  mov     rcx, rax; hHeap
0x140029a95  call    cs:__imp_HeapAlloc
0x140029a9b  test    rax, rax
0x140029a9e  jz      loc_140029C1F
0x140029aa4  mov     r11, [rsp+0A8h+arg_10]
0x140029aac  mov     edx, dword ptr [rsp+0A8h+arg_8]
0x140029ab3  mov     rcx, [r11+8]
0x140029ab7  mov     [r15+rcx+10h], edx
0x140029abc  mov     rcx, [r11+8]
0x140029ac0  mov     [r15+rcx+18h], rax
0x140029ac5  inc     ebp
0x140029ac7  cmp     ebp, r14d
0x140029aca  jb      loc_140029A33
0x140029ad0  mov     rcx, [rsp+0A8h+var_68]
0x140029ad5  xor     ebp, ebp
0x140029ad7  movzx   r12d, byte ptr [rcx+2]
0x140029adc  add     r12, 4
0x140029ae0  shl     r12, 4
0x140029ae4  add     r12, [rsp+0A8h+var_60]
0x140029ae9  mov     [rsp+0A8h+arg_8], r12
0x140029af1  mov     rsi, [r12]
0x140029af5  cmp     r12, rsi
0x140029af8  jz      loc_140029C1B
0x140029afe  mov     r14b, [rsp+0A8h+arg_0]
0x140029b06  mov     rax, [rsi]
0x140029b09  mov     rdx, rcx; struct _EVENT_DESCRIPTOR *
0x140029b0c  mov     rcx, rsi; struct _MOF_VERSION *
0x140029b0f  mov     [rsp+0A8h+arg_18], rax
0x140029b17  mov     r8b, r14b; unsigned __int8
0x140029b1a  call    ?FindMatchMofVersion@@YAEPEAU_MOF_VERSION@@PEBU_EVENT_DESCRIPTOR@@EE@Z; FindMatchMofVersion(_MOF_VERSION *,_EVENT_DESCRIPTOR const *,uchar,uchar)
0x140029b1f  test    al, al
0x140029b21  jz      loc_140029BFD
0x140029b27  lea     r15, [rsi+30h]
0x140029b2b  xor     ebx, ebx
0x140029b2d  mov     rcx, [r15]
0x140029b30  cmp     r15, rcx
0x140029b33  jz      loc_140029BFB
0x140029b39  jmp     short loc_140029B43
0x140029b3b  mov     r11, [rsp+0A8h+arg_10]
0x140029b43  mov     rax, [rcx]
0x140029b46  lea     r12d, [rbx+rbp]
0x140029b4a  mov     qword ptr [rsp+0A8h+arg_0], rax
0x140029b52  mov     r8, rcx; struct _MOF_EVENT *
0x140029b55  mov     rcx, [rsp+0A8h+var_60]; struct _MOF_INFO *
0x140029b5a  mov     r9, r13; struct _TRACERPT_JOINFIELD *
0x140029b5d  mov     eax, r12d
0x140029b60  mov     rdx, rsi; struct _MOF_VERSION *
0x140029b63  shl     rax, 5
0x140029b67  add     rax, [r11+8]
0x140029b6b  mov     [rsp+0A8h+var_78], rax; struct _ROW_DATA *
0x140029b70  mov     rax, [rsp+0A8h+var_58]
0x140029b75  mov     [rsp+0A8h+var_80], rax; struct _LIST_ENTRY *
0x140029b7a  lea     rax, [rdi+10h]
0x140029b7e  mov     [rsp+0A8h+var_88], rax; struct _LIST_ENTRY *
0x140029b83  call    ?FillEventToRowData@@YAEPEAU_MOF_INFO@@PEAU_MOF_VERSION@@PEAU_MOF_EVENT@@PEAU_TRACERPT_JOINFIELD@@PEAU_LIST_ENTRY@@4PEAU_ROW_DATA@@@Z; FillEventToRowData(_MOF_INFO *,_MOF_VERSION *,_MOF_EVENT *,_TRACERPT_JOINFIELD *,_LIST_ENTRY *,_LIST_ENTRY *,_ROW_DATA *)
0x140029b88  test    al, al
0x140029b8a  jz      loc_140029C1F
0x140029b90  cmp     dword ptr [rdi+24h], 0
0x140029b94  ja      short loc_140029BD4
0x140029b96  test    r13, r13
0x140029b99  jnz     short loc_140029BD4
0x140029b9b  mov     eax, [rdi+0CCh]
0x140029ba1  test    eax, eax
0x140029ba3  jz      short loc_140029BD4
0x140029ba5  cmp     [rdi+38h], r13
0x140029ba9  jnz     short loc_140029BBA
0x140029bab  cmp     r12d, eax
0x140029bae  mov     r12, [rsp+0A8h+arg_10]
0x140029bb6  jnb     short loc_140029BEF
0x140029bb8  jmp     short loc_140029BDC
0x140029bba  mov     r8d, r12d
0x140029bbd  mov     rcx, rdi
0x140029bc0  mov     r12, [rsp+0A8h+arg_10]
0x140029bc8  mov     rdx, r12
0x140029bcb  call    SortRowData
0x140029bd0  add     ebx, eax
0x140029bd2  jmp     short loc_140029BDE
0x140029bd4  mov     r12, [rsp+0A8h+arg_10]
0x140029bdc  inc     ebx
0x140029bde  mov     rcx, qword ptr [rsp+0A8h+arg_0]
0x140029be6  cmp     r15, rcx
0x140029be9  jnz     loc_140029B3B
0x140029bef  test    ebx, ebx
0x140029bf1  js      short loc_140029C27
0x140029bf3  mov     r12, [rsp+0A8h+arg_8]
0x140029bfb  add     ebp, ebx
0x140029bfd  mov     rsi, [rsp+0A8h+arg_18]
0x140029c05  mov     r11, [rsp+0A8h+arg_10]
0x140029c0d  mov     rcx, [rsp+0A8h+var_68]
0x140029c12  cmp     r12, rsi
0x140029c15  jnz     loc_140029B06
0x140029c1b  mov     eax, ebp
0x140029c1d  jmp     short loc_140029C31
0x140029c1f  mov     r12, [rsp+0A8h+arg_10]
0x140029c27  mov     rcx, r12; struct _TABLE_DATA *
0x140029c2a  call    ?CleanupTableData@@YAXPEAU_TABLE_DATA@@@Z; CleanupTableData(_TABLE_DATA *)
0x140029c2f  xor     eax, eax
0x140029c31  add     rsp, 68h
0x140029c35  pop     r15
0x140029c37  pop     r14
0x140029c39  pop     r13
0x140029c3b  pop     r12
0x140029c3d  pop     rdi
0x140029c3e  pop     rsi
0x140029c3f  pop     rbp
0x140029c40  pop     rbx
0x140029c41  retn
```
