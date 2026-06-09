# CreateGroupbyColumnDataFromList(_TRACERPT_EVENT_TABLE *,_TABLE_DATA *,_TABLE_DATA *,_LIST_ENTRY *)

- ea: `0x1400295e8`
- end: `0x14002978d`
- name: `?CreateGroupbyColumnDataFromList@@YAEPEAU_TRACERPT_EVENT_TABLE@@PEAU_TABLE_DATA@@1PEAU_LIST_ENTRY@@@Z`
- size: `421`
- prototype: `unsigned __int8 __fastcall(struct _TRACERPT_EVENT_TABLE *, struct _TABLE_DATA *, struct _TABLE_DATA *, struct _LIST_ENTRY *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140028464`
- `0x140028b3c`

## callees

- `0x1400295e8`
- `0x1400400be`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029694`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029694`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400296a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400296a5`

## pseudocode

```c
unsigned __int8 __fastcall CreateGroupbyColumnDataFromList(
        struct _TRACERPT_EVENT_TABLE *a1,
        struct _TABLE_DATA *a2,
        struct _TABLE_DATA *a3,
        struct _LIST_ENTRY *a4)
{
  struct _LIST_ENTRY *Flink; // rbx
  struct _LIST_ENTRY *v5; // r14
  struct _TABLE_DATA *v6; // r11
  struct _TABLE_DATA *v7; // rax
  unsigned int v9; // edi
  struct _LIST_ENTRY *v10; // r12
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v13; // r8
  int v14; // eax
  unsigned int v15; // eax
  struct _LIST_ENTRY *v16; // rsi
  HANDLE ProcessHeap; // rax
  struct _LIST_ENTRY *v18; // rax
  struct _LIST_ENTRY *v19; // r13
  struct _LIST_ENTRY *v20; // rax
  unsigned int v21; // r15d
  __int64 v22; // rsi
  struct _LIST_ENTRY *v23; // r14
  __int64 v24; // r8
  __int64 v25; // rdi
  _QWORD *v26; // rdx

  Flink = a4->Flink;
  v5 = a4;
  v6 = a3;
  v7 = a2;
  if ( a4 == a4->Flink )
    return 1;
  while ( 1 )
  {
    v9 = 0;
    v10 = Flink + 1;
    if ( *((_DWORD *)a1 + 9) )
    {
      v11 = 0;
      v12 = *(_QWORD *)(32LL * LODWORD(v10->Flink) + *((_QWORD *)v7 + 1) + 8);
      do
      {
        v13 = 32LL * (unsigned int)(*(_DWORD *)(*((_QWORD *)a1 + 5) + 4 * v11) + 1);
        v14 = *(_DWORD *)(v13 + v12 + 16);
        if ( v14 )
        {
          v15 = v9 + v14;
          if ( v15 < v9 )
            return 0;
          v9 = v15;
        }
        else
        {
          if ( v9 + *(_DWORD *)(*(_QWORD *)(32LL * HIDWORD(Flink[1].Flink) + *((_QWORD *)v6 + 1) + 8) + v13 + 16) < v9 )
            return 0;
          v9 += *(_DWORD *)(*(_QWORD *)(32LL * HIDWORD(Flink[1].Flink) + *((_QWORD *)v6 + 1) + 8) + v13 + 16);
        }
        v11 = (unsigned int)(v11 + 1);
      }
      while ( (unsigned int)v11 < *((_DWORD *)a1 + 9) );
    }
    v16 = Flink->Flink;
    LODWORD(Flink[2].Blink) = v9;
    ProcessHeap = GetProcessHeap();
    v18 = (struct _LIST_ENTRY *)HeapAlloc(ProcessHeap, 8u, v9);
    v19 = Flink + 2;
    Flink[2].Flink = v18;
    if ( !v18 )
      break;
    v20 = Flink;
    v21 = 0;
    Flink = v16;
    v22 = 0;
    LOBYTE(v20[3].Flink) = 1;
    if ( *((_DWORD *)a1 + 9) )
    {
      v23 = v20;
      do
      {
        v24 = 32LL * (unsigned int)(*(_DWORD *)(*((_QWORD *)a1 + 5) + 4 * v22) + 1);
        v25 = v24 + *(_QWORD *)(32LL * LODWORD(v10->Flink) + *((_QWORD *)a2 + 1) + 8);
        if ( !*(_DWORD *)(v25 + 16) )
          v25 = v24 + *(_QWORD *)(32LL * HIDWORD(v23[1].Flink) + *((_QWORD *)a3 + 1) + 8);
        v26 = (_QWORD *)(v25 + 8);
        if ( !*(_BYTE *)(v25 + 25) )
          v26 = (_QWORD *)*v26;
        memcpy_0((char *)v19->Flink + v21, v26, *(unsigned int *)(v25 + 16));
        v21 += *(_DWORD *)(v25 + 16);
        v22 = (unsigned int)(v22 + 1);
      }
      while ( (unsigned int)v22 < *((_DWORD *)a1 + 9) );
      v5 = a4;
    }
    if ( v5 == Flink )
      return 1;
    v6 = a3;
    v7 = a2;
  }
  return 0;
}

```

## disassembly

```asm
0x1400295e8  mov     rax, rsp
0x1400295eb  mov     [rax+8], rbx
0x1400295ef  mov     [rax+20h], r9
0x1400295f3  mov     [rax+18h], r8
0x1400295f7  mov     [rax+10h], rdx
0x1400295fb  push    rbp
0x1400295fc  push    rsi
0x1400295fd  push    rdi
0x1400295fe  push    r12
0x140029600  push    r13
0x140029602  push    r14
0x140029604  push    r15
0x140029606  sub     rsp, 30h
0x14002960a  mov     rbx, [r9]
0x14002960d  mov     r14, r9
0x140029610  mov     r11, r8
0x140029613  mov     rax, rdx
0x140029616  mov     rbp, rcx
0x140029619  cmp     r9, rbx
0x14002961c  jz      loc_140029776
0x140029622  xor     edi, edi
0x140029624  lea     r12, [rbx+10h]
0x140029628  cmp     [rbp+24h], edi
0x14002962b  jbe     short loc_14002968E
0x14002962d  mov     ecx, [r12]
0x140029631  xor     edx, edx
0x140029633  mov     rax, [rax+8]
0x140029637  mov     r10, [rbp+28h]
0x14002963b  shl     rcx, 5
0x14002963f  mov     r9, [rcx+rax+8]
0x140029644  mov     r8d, [r10+rdx*4]
0x140029648  inc     r8d
0x14002964b  shl     r8, 5
0x14002964f  mov     eax, [r8+r9+10h]
0x140029654  test    eax, eax
0x140029656  jz      short loc_140029666
0x140029658  add     eax, edi
0x14002965a  cmp     eax, edi
0x14002965c  jb      loc_140029772
0x140029662  mov     edi, eax
0x140029664  jmp     short loc_140029687
0x140029666  mov     ecx, [rbx+14h]
0x140029669  mov     rax, [r11+8]
0x14002966d  shl     rcx, 5
0x140029671  mov     rcx, [rcx+rax+8]
0x140029676  mov     ecx, [rcx+r8+10h]
0x14002967b  add     ecx, edi
0x14002967d  cmp     ecx, edi
0x14002967f  jb      loc_140029772
0x140029685  mov     edi, ecx
0x140029687  inc     edx
0x140029689  cmp     edx, [rbp+24h]
0x14002968c  jb      short loc_140029644
0x14002968e  mov     rsi, [rbx]
0x140029691  mov     [rbx+28h], edi
0x140029694  call    cs:__imp_GetProcessHeap
0x14002969a  mov     r8d, edi; dwBytes
0x14002969d  mov     edx, 8; dwFlags
0x1400296a2  mov     rcx, rax; hHeap
0x1400296a5  call    cs:__imp_HeapAlloc
0x1400296ab  lea     r13, [rbx+20h]
0x1400296af  mov     [r13+0], rax
0x1400296b3  test    rax, rax
0x1400296b6  jz      loc_140029772
0x1400296bc  mov     rax, rbx
0x1400296bf  xor     r15d, r15d
0x1400296c2  mov     rbx, rsi
0x1400296c5  xor     esi, esi
0x1400296c7  mov     [rsp+68h+var_40], rbx
0x1400296cc  mov     byte ptr [rax+30h], 1
0x1400296d0  cmp     [rbp+24h], esi
0x1400296d3  jbe     loc_14002975B
0x1400296d9  mov     rbx, [rsp+68h+arg_10]
0x1400296e1  mov     r14, rax
0x1400296e4  mov     rax, [rbp+28h]
0x1400296e8  mov     ecx, [r12]
0x1400296ec  shl     rcx, 5
0x1400296f0  mov     r8d, [rax+rsi*4]
0x1400296f4  mov     rax, [rsp+68h+arg_8]
0x1400296f9  inc     r8d
0x1400296fc  shl     r8, 5
0x140029700  mov     rax, [rax+8]
0x140029704  mov     rdi, [rcx+rax+8]
0x140029709  add     rdi, r8
0x14002970c  cmp     dword ptr [rdi+10h], 0
0x140029710  ja      short loc_140029726
0x140029712  mov     ecx, [r14+14h]
0x140029716  mov     rax, [rbx+8]
0x14002971a  shl     rcx, 5
0x14002971e  mov     rdi, [rcx+rax+8]
0x140029723  add     rdi, r8
0x140029726  mov     r8d, [rdi+10h]; Size
0x14002972a  lea     rdx, [rdi+8]
0x14002972e  mov     ecx, r15d
0x140029731  add     rcx, [r13+0]; void *
0x140029735  cmp     byte ptr [rdi+19h], 0
0x140029739  jnz     short loc_14002973E
0x14002973b  mov     rdx, [rdx]; Src
0x14002973e  call    memcpy_0
0x140029743  add     r15d, [rdi+10h]
0x140029747  inc     esi
0x140029749  cmp     esi, [rbp+24h]
0x14002974c  jb      short loc_1400296E4
0x14002974e  mov     rbx, [rsp+68h+var_40]
0x140029753  mov     r14, [rsp+68h+arg_18]
0x14002975b  cmp     r14, rbx
0x14002975e  jz      short loc_140029776
0x140029760  mov     r11, [rsp+68h+arg_10]
0x140029768  mov     rax, [rsp+68h+arg_8]
0x14002976d  jmp     loc_140029622
0x140029772  xor     al, al
0x140029774  jmp     short loc_140029778
0x140029776  mov     al, 1
0x140029778  mov     rbx, [rsp+68h+arg_0]
0x14002977d  add     rsp, 30h
0x140029781  pop     r15
0x140029783  pop     r14
0x140029785  pop     r13
0x140029787  pop     r12
0x140029789  pop     rdi
0x14002978a  pop     rsi
0x14002978b  pop     rbp
0x14002978c  retn
```
