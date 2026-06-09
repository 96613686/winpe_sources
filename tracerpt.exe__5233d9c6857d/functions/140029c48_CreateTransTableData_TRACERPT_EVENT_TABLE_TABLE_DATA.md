# CreateTransTableData(_TRACERPT_EVENT_TABLE *,_TABLE_DATA *)

- ea: `0x140029c48`
- end: `0x140029f7e`
- name: `?CreateTransTableData@@YAJPEAU_TRACERPT_EVENT_TABLE@@PEAU_TABLE_DATA@@@Z`
- size: `822`
- prototype: `__int64 __fastcall(struct _TRACERPT_EVENT_TABLE *, struct _TABLE_DATA *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14002b5d8`

## callees

- `0x140004cac`
- `0x140029320`
- `0x140029c48`
- `0x14002a42c`
- `0x14002aa9c`
- `0x14002dcec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029d5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029dbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029e01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029d5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029dbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029e01`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140029d6b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140029dcd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140029e12`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140029d6b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140029dcd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140029e12`

## pseudocode

```c
__int64 __fastcall CreateTransTableData(struct _TRACERPT_EVENT_TABLE *a1, struct _TABLE_DATA *a2)
{
  struct _TABLE_DATA *v3; // r12
  char v4; // cl
  unsigned int v5; // r13d
  __int64 v6; // rbx
  struct _MOF_INFO *MofInfoHead; // rax
  unsigned int v8; // r14d
  _QWORD **v9; // rsi
  _QWORD *v10; // rbx
  unsigned __int8 v11; // r15
  _QWORD *v12; // rbp
  unsigned int v13; // r15d
  HANDLE ProcessHeap; // rax
  LPVOID v15; // rax
  unsigned __int64 v16; // rax
  unsigned int v17; // ebp
  SIZE_T v18; // rbx
  HANDLE v19; // rax
  LPVOID v20; // rax
  __int64 v21; // rsi
  HANDLE v22; // rax
  LPVOID v23; // rax
  unsigned int v24; // ebp
  _QWORD *v25; // r13
  _QWORD *v26; // rbx
  _QWORD *v27; // r14
  struct _MOF_EVENT **v28; // rbx
  int v29; // esi
  struct _MOF_EVENT *v30; // rcx
  struct _MOF_EVENT *v31; // r15
  unsigned int v32; // r14d
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // ecx
  unsigned int v37; // [rsp+30h] [rbp-68h]
  struct _MOF_INFO *v38; // [rsp+38h] [rbp-60h]
  __int64 v39; // [rsp+40h] [rbp-58h]
  struct _LIST_ENTRY *v40; // [rsp+48h] [rbp-50h]
  unsigned __int8 v41; // [rsp+A0h] [rbp+8h]
  unsigned __int8 v43; // [rsp+B0h] [rbp+18h]
  unsigned int v44; // [rsp+B8h] [rbp+20h]
  unsigned __int64 v45; // [rsp+B8h] [rbp+20h]
  _QWORD *v46; // [rsp+B8h] [rbp+20h]

  v3 = a2;
  v37 = *((_DWORD *)a1 + 9);
  v44 = *((_DWORD *)a1 + 8);
  v4 = *((_BYTE *)a1 + 681) & 4;
  if ( v4 )
    v5 = *((_DWORD *)a1 + 150);
  else
    v5 = 0;
  v6 = *((_QWORD *)a1 + 2);
  v39 = v6;
  v40 = (struct _LIST_ENTRY *)(((unsigned __int64)a1 + 584) & -(__int64)(v4 != 0));
  MofInfoHead = GetMofInfoHead((const struct _GUID *)((char *)a1 + 632));
  v38 = MofInfoHead;
  if ( MofInfoHead )
  {
    v8 = 0;
    v9 = (_QWORD **)((char *)MofInfoHead + 16 * *(unsigned __int8 *)(v6 + 282) + 64);
    v43 = *(_BYTE *)(v6 + 245) & 1;
    v41 = *((_BYTE *)a1 + 680) >> 7;
    v10 = *v9;
    if ( v9 != *v9 )
    {
      v11 = *((_BYTE *)a1 + 680) >> 7;
      do
      {
        v12 = v10;
        v10 = (_QWORD *)*v10;
        if ( FindMatchMofVersionForTrans((struct _MOF_VERSION *)v12, a1, v43, v11) && *((_DWORD *)v12 + 11) )
          v8 += *((_DWORD *)v12 + 11);
      }
      while ( v9 != v10 );
      v13 = v44;
      v3 = a2;
      if ( v8 )
      {
        ProcessHeap = GetProcessHeap();
        v15 = HeapAlloc(ProcessHeap, 8u, 32LL * v8);
        *((_QWORD *)a2 + 1) = v15;
        if ( v15 )
        {
          *(_DWORD *)a2 = v8;
          if ( v37 <= 1 )
          {
            v16 = v44;
          }
          else
          {
            v13 = v44 + 1;
            v16 = v44 + 1;
          }
          v17 = 0;
          v45 = v16;
          while ( 1 )
          {
            v18 = 32 * v16;
            if ( !is_mul_ok(0x20u, v16) )
              break;
            v19 = GetProcessHeap();
            v20 = HeapAlloc(v19, 8u, v18);
            if ( !v20 )
              break;
            v21 = 32LL * v17;
            *(_DWORD *)(v21 + *((_QWORD *)a2 + 1)) = v13;
            *(_QWORD *)(v21 + *((_QWORD *)a2 + 1) + 8) = v20;
            if ( v5 )
            {
              v22 = GetProcessHeap();
              v23 = HeapAlloc(v22, 8u, 32LL * v5);
              if ( !v23 )
                break;
              *(_DWORD *)(v21 + *((_QWORD *)a2 + 1) + 16) = v5;
              *(_QWORD *)(v21 + *((_QWORD *)a2 + 1) + 24) = v23;
            }
            v16 = v45;
            if ( ++v17 >= v8 )
            {
              v24 = 0;
              v25 = (_QWORD *)((char *)v38 + 16 * *(unsigned __int8 *)(v39 + 282) + 64);
              v26 = (_QWORD *)*v25;
              if ( v25 != (_QWORD *)*v25 )
              {
                do
                {
                  v27 = (_QWORD *)*v26;
                  v46 = (_QWORD *)*v26;
                  if ( FindMatchMofVersionForTrans((struct _MOF_VERSION *)v26, a1, v43, v41) && *((_DWORD *)v26 + 11) )
                  {
                    v28 = (struct _MOF_EVENT **)(v26 + 6);
                    v29 = 0;
                    v30 = *v28;
                    if ( v28 != (struct _MOF_EVENT **)*v28 )
                    {
                      do
                      {
                        v31 = *(struct _MOF_EVENT **)v30;
                        v32 = v29 + v24;
                        v33 = FillEventToRowDataForTrans(
                                v38,
                                v30,
                                (struct _LIST_ENTRY *)a1 + 1,
                                v40,
                                (struct _ROW_DATA *)(*((_QWORD *)a2 + 1) + 32LL * (v29 + v24)));
                        if ( v33 )
                        {
                          if ( v33 != 1168 )
                            goto LABEL_44;
                        }
                        else if ( *((_DWORD *)a1 + 9) || (v34 = *((_DWORD *)a1 + 51)) == 0 )
                        {
                          ++v29;
                        }
                        else if ( *((_QWORD *)a1 + 7) )
                        {
                          v29 += SortRowData(a1, a2, v32);
                        }
                        else if ( v32 >= v34 )
                        {
                          break;
                        }
                        v30 = v31;
                      }
                      while ( v28 != (struct _MOF_EVENT **)v31 );
                      if ( v29 < 0 )
                        goto LABEL_44;
                      v27 = v46;
                    }
                    v24 += v29;
                    if ( !*((_QWORD *)a1 + 7) )
                    {
                      v35 = *((_DWORD *)a1 + 51);
                      if ( v35 )
                      {
                        if ( v24 >= v35 )
                          return v24;
                      }
                    }
                  }
                  v26 = v27;
                }
                while ( v25 != v27 );
              }
              return v24;
            }
          }
        }
      }
    }
  }
LABEL_44:
  CleanupTableData(v3);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x140029c48  mov     [rsp+arg_8], rdx
0x140029c4d  push    rbx
0x140029c4e  push    rbp
0x140029c4f  push    rsi
0x140029c50  push    rdi
0x140029c51  push    r12
0x140029c53  push    r13
0x140029c55  push    r14
0x140029c57  push    r15
0x140029c59  sub     rsp, 58h
0x140029c5d  mov     eax, [rcx+24h]
0x140029c60  mov     rdi, rcx
0x140029c63  mov     r15d, [rcx+20h]
0x140029c67  mov     r12, rdx
0x140029c6a  mov     cl, [rcx+2A9h]
0x140029c70  mov     dword ptr [rsp+98h+var_68], eax
0x140029c74  mov     dword ptr [rsp+98h+arg_18], r15d
0x140029c7c  and     cl, 4
0x140029c7f  jz      short loc_140029C8A
0x140029c81  mov     r13d, [rdi+258h]
0x140029c88  jmp     short loc_140029C8D
0x140029c8a  xor     r13d, r13d
0x140029c8d  mov     rbx, [rdi+10h]
0x140029c91  lea     rax, [rdi+248h]
0x140029c98  neg     cl
0x140029c9a  mov     [rsp+98h+var_58], rbx
0x140029c9f  sbb     rcx, rcx
0x140029ca2  and     rcx, rax
0x140029ca5  mov     [rsp+98h+var_50], rcx
0x140029caa  lea     rcx, [rdi+278h]; struct _GUID *
0x140029cb1  call    ?GetMofInfoHead@@YAPEAU_MOF_INFO@@PEBU_GUID@@@Z; GetMofInfoHead(_GUID const *)
0x140029cb6  mov     [rsp+98h+var_60], rax
0x140029cbb  test    rax, rax
0x140029cbe  jz      loc_140029F62
0x140029cc4  movzx   esi, byte ptr [rbx+11Ah]
0x140029ccb  xor     r14d, r14d
0x140029cce  mov     cl, [rbx+0F5h]
0x140029cd4  add     rsi, 4
0x140029cd8  and     cl, 1
0x140029cdb  shl     rsi, 4
0x140029cdf  add     rsi, rax
0x140029ce2  mov     [rsp+98h+arg_10], cl
0x140029ce9  mov     cl, [rdi+2A8h]
0x140029cef  shr     cl, 7
0x140029cf2  mov     [rsp+98h+arg_0], cl
0x140029cf9  mov     rbx, [rsi]
0x140029cfc  cmp     rsi, rbx
0x140029cff  jz      loc_140029F62
0x140029d05  mov     r12b, [rsp+98h+arg_10]
0x140029d0d  mov     r15b, cl
0x140029d10  mov     rbp, rbx
0x140029d13  mov     r9b, r15b; unsigned __int8
0x140029d16  mov     rbx, [rbx]
0x140029d19  mov     rcx, rbp; struct _MOF_VERSION *
0x140029d1c  mov     r8b, r12b; unsigned __int8
0x140029d1f  mov     rdx, rdi; struct _TRACERPT_EVENT_TABLE *
0x140029d22  call    ?FindMatchMofVersionForTrans@@YAEPEAU_MOF_VERSION@@PEAU_TRACERPT_EVENT_TABLE@@EE@Z; FindMatchMofVersionForTrans(_MOF_VERSION *,_TRACERPT_EVENT_TABLE *,uchar,uchar)
0x140029d27  test    al, al
0x140029d29  jz      short loc_140029D35
0x140029d2b  cmp     dword ptr [rbp+2Ch], 0
0x140029d2f  jbe     short loc_140029D35
0x140029d31  add     r14d, [rbp+2Ch]
0x140029d35  cmp     rsi, rbx
0x140029d38  jnz     short loc_140029D10
0x140029d3a  mov     r15d, dword ptr [rsp+98h+arg_18]
0x140029d42  mov     r12, [rsp+98h+arg_8]
0x140029d4a  test    r14d, r14d
0x140029d4d  jz      loc_140029F62
0x140029d53  mov     ebx, r14d
0x140029d56  shl     rbx, 5
0x140029d5a  call    cs:__imp_GetProcessHeap
0x140029d60  mov     r8, rbx; dwBytes
0x140029d63  mov     edx, 8; dwFlags
0x140029d68  mov     rcx, rax; hHeap
0x140029d6b  call    cs:__imp_HeapAlloc
0x140029d71  mov     [r12+8], rax
0x140029d76  test    rax, rax
0x140029d79  jz      loc_140029F62
0x140029d7f  cmp     dword ptr [rsp+98h+var_68], 1
0x140029d84  mov     [r12], r14d
0x140029d88  jbe     short loc_140029D92
0x140029d8a  inc     r15d
0x140029d8d  mov     eax, r15d
0x140029d90  jmp     short loc_140029D95
0x140029d92  mov     rax, r15
0x140029d95  xor     ebp, ebp
0x140029d97  mov     [rsp+98h+arg_18], rax
0x140029d9f  mov     ecx, 20h ; ' '
0x140029da4  mov     [rsp+98h+var_68], 0
0x140029dad  mul     rcx
0x140029db0  mov     rbx, rax
0x140029db3  test    rdx, rdx
0x140029db6  jnz     loc_140029F62
0x140029dbc  call    cs:__imp_GetProcessHeap
0x140029dc2  mov     r8, rbx; dwBytes
0x140029dc5  mov     edx, 8; dwFlags
0x140029dca  mov     rcx, rax; hHeap
0x140029dcd  call    cs:__imp_HeapAlloc
0x140029dd3  test    rax, rax
0x140029dd6  jz      loc_140029F62
0x140029ddc  mov     rcx, [r12+8]
0x140029de1  mov     esi, ebp
0x140029de3  shl     rsi, 5
0x140029de7  mov     [rsi+rcx], r15d
0x140029deb  mov     rcx, [r12+8]
0x140029df0  mov     [rsi+rcx+8], rax
0x140029df5  test    r13d, r13d
0x140029df8  jz      short loc_140029E35
0x140029dfa  mov     ebx, r13d
0x140029dfd  shl     rbx, 5
0x140029e01  call    cs:__imp_GetProcessHeap
0x140029e07  mov     r8, rbx; dwBytes
0x140029e0a  mov     edx, 8; dwFlags
0x140029e0f  mov     rcx, rax; hHeap
0x140029e12  call    cs:__imp_HeapAlloc
0x140029e18  test    rax, rax
0x140029e1b  jz      loc_140029F62
0x140029e21  mov     rcx, [r12+8]
0x140029e26  mov     [rsi+rcx+10h], r13d
0x140029e2b  mov     rcx, [r12+8]
0x140029e30  mov     [rsi+rcx+18h], rax
0x140029e35  mov     rax, [rsp+98h+arg_18]
0x140029e3d  inc     ebp
0x140029e3f  cmp     ebp, r14d
0x140029e42  jb      loc_140029D9F
0x140029e48  mov     rax, [rsp+98h+var_58]
0x140029e4d  xor     ebp, ebp
0x140029e4f  movzx   r13d, byte ptr [rax+11Ah]
0x140029e57  add     r13, 4
0x140029e5b  shl     r13, 4
0x140029e5f  add     r13, [rsp+98h+var_60]
0x140029e64  mov     rbx, [r13+0]
0x140029e68  cmp     r13, rbx
0x140029e6b  jz      loc_140029F5E
0x140029e71  mov     r14, [rbx]
0x140029e74  mov     rdx, rdi; struct _TRACERPT_EVENT_TABLE *
0x140029e77  mov     r9b, [rsp+98h+arg_0]; unsigned __int8
0x140029e7f  mov     rcx, rbx; struct _MOF_VERSION *
0x140029e82  mov     r8b, [rsp+98h+arg_10]; unsigned __int8
0x140029e8a  mov     [rsp+98h+arg_18], r14
0x140029e92  call    ?FindMatchMofVersionForTrans@@YAEPEAU_MOF_VERSION@@PEAU_TRACERPT_EVENT_TABLE@@EE@Z; FindMatchMofVersionForTrans(_MOF_VERSION *,_TRACERPT_EVENT_TABLE *,uchar,uchar)
0x140029e97  test    al, al
0x140029e99  jz      loc_140029F52
0x140029e9f  cmp     dword ptr [rbx+2Ch], 0
0x140029ea3  jbe     loc_140029F52
0x140029ea9  add     rbx, 30h ; '0'
0x140029ead  xor     esi, esi
0x140029eaf  mov     rcx, [rbx]
0x140029eb2  cmp     rbx, rcx
0x140029eb5  jz      loc_140029F3B
0x140029ebb  mov     r15, [rcx]
0x140029ebe  lea     r14d, [rsi+rbp]
0x140029ec2  mov     r9, [rsp+98h+var_50]; struct _LIST_ENTRY *
0x140029ec7  lea     r8, [rdi+10h]; struct _LIST_ENTRY *
0x140029ecb  mov     rdx, rcx; struct _MOF_EVENT *
0x140029ece  mov     eax, r14d
0x140029ed1  mov     rcx, [rsp+98h+var_60]; struct _MOF_INFO *
0x140029ed6  shl     rax, 5
0x140029eda  add     rax, [r12+8]
0x140029edf  mov     [rsp+98h+var_78], rax; struct _ROW_DATA *
0x140029ee4  call    ?FillEventToRowDataForTrans@@YAKPEAU_MOF_INFO@@PEAU_MOF_EVENT@@PEAU_LIST_ENTRY@@2PEAU_ROW_DATA@@@Z; FillEventToRowDataForTrans(_MOF_INFO *,_MOF_EVENT *,_LIST_ENTRY *,_LIST_ENTRY *,_ROW_DATA *)
0x140029ee9  test    eax, eax
0x140029eeb  jnz     short loc_140029F20
0x140029eed  cmp     [rdi+24h], eax
0x140029ef0  ja      short loc_140029F1C
0x140029ef2  mov     eax, [rdi+0CCh]
0x140029ef8  test    eax, eax
0x140029efa  jz      short loc_140029F1C
0x140029efc  cmp     qword ptr [rdi+38h], 0
0x140029f01  jnz     short loc_140029F0A
0x140029f03  cmp     r14d, eax
0x140029f06  jnb     short loc_140029F2F
0x140029f08  jmp     short loc_140029F27
0x140029f0a  mov     r8d, r14d
0x140029f0d  mov     rdx, r12
0x140029f10  mov     rcx, rdi
0x140029f13  call    SortRowData
0x140029f18  add     esi, eax
0x140029f1a  jmp     short loc_140029F27
0x140029f1c  inc     esi
0x140029f1e  jmp     short loc_140029F27
0x140029f20  cmp     eax, 490h
0x140029f25  jnz     short loc_140029F62
0x140029f27  mov     rcx, r15
0x140029f2a  cmp     rbx, r15
0x140029f2d  jnz     short loc_140029EBB
0x140029f2f  test    esi, esi
0x140029f31  js      short loc_140029F62
0x140029f33  mov     r14, [rsp+98h+arg_18]
0x140029f3b  add     ebp, esi
0x140029f3d  cmp     qword ptr [rdi+38h], 0
0x140029f42  jnz     short loc_140029F52
0x140029f44  mov     ecx, [rdi+0CCh]
0x140029f4a  test    ecx, ecx
0x140029f4c  jz      short loc_140029F52
0x140029f4e  cmp     ebp, ecx
0x140029f50  jnb     short loc_140029F5E
0x140029f52  mov     rbx, r14
0x140029f55  cmp     r13, r14
0x140029f58  jnz     loc_140029E71
0x140029f5e  mov     eax, ebp
0x140029f60  jmp     short loc_140029F6D
0x140029f62  mov     rcx, r12; struct _TABLE_DATA *
0x140029f65  call    ?CleanupTableData@@YAXPEAU_TABLE_DATA@@@Z; CleanupTableData(_TABLE_DATA *)
0x140029f6a  or      eax, 0FFFFFFFFh
0x140029f6d  add     rsp, 58h
0x140029f71  pop     r15
0x140029f73  pop     r14
0x140029f75  pop     r13
0x140029f77  pop     r12
0x140029f79  pop     rdi
0x140029f7a  pop     rsi
0x140029f7b  pop     rbp
0x140029f7c  pop     rbx
0x140029f7d  retn
```
