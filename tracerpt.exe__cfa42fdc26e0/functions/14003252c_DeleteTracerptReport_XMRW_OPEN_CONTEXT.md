# DeleteTracerptReport(_XMRW_OPEN_CONTEXT *)

- ea: `0x14003252c`
- end: `0x140032657`
- name: `?DeleteTracerptReport@@YAXPEAU_XMRW_OPEN_CONTEXT@@@Z`
- size: `299`
- prototype: `void __fastcall(struct _XMRW_OPEN_CONTEXT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140038330`

## callees

- `0x1400020f0`
- `0x1400305f0`
- `0x14003252c`
- `0x140032660`
- `0x1400328a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400325ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140032612`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400325ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140032612`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400325df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140032604`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400325df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140032604`

## pseudocode

```c
void __fastcall DeleteTracerptReport(struct _XMRW_OPEN_CONTEXT *a1)
{
  struct _TRACERPT_SECTION **v1; // rdi
  struct _TRACERPT_SECTION *v2; // rbx
  struct _TRACERPT_SECTION *v3; // rax
  struct _TRACERPT_SECTION **v4; // rdx
  struct _TRACERPT_SECTION *v5; // rcx
  struct _TRACERPT_STRING *v6; // rbx
  struct _TRACERPT_STRING *v7; // rax
  struct _TRACERPT_STRING **v8; // rdx
  struct _TRACERPT_STRING *v9; // rcx
  struct _TRACERPT_SECTION **v10; // rsi
  struct _TRACERPT_SECTION **v11; // rax
  struct _TRACERPT_SECTION ***v12; // rcx
  struct _TRACERPT_SECTION **v13; // rbx
  HANDLE ProcessHeap; // rax
  struct _TRACERPT_SECTION *v15; // rbx
  HANDLE v16; // rax

  v1 = (struct _TRACERPT_SECTION **)*((_QWORD *)a1 + 8);
  if ( v1 )
  {
    v2 = *v1;
    while ( v1 != (struct _TRACERPT_SECTION **)v2 )
    {
      v3 = *(struct _TRACERPT_SECTION **)v2;
      if ( *(struct _TRACERPT_SECTION **)(*(_QWORD *)v2 + 8LL) != v2
        || (v4 = (struct _TRACERPT_SECTION **)*((_QWORD *)v2 + 1), *v4 != v2) )
      {
LABEL_21:
        __fastfail(3u);
      }
      v5 = v2;
      *v4 = v3;
      v2 = v3;
      *((_QWORD *)v3 + 1) = v4;
      DeleteTracerptSection(v5);
    }
    v6 = v1[2];
    while ( v1 + 2 != (struct _TRACERPT_SECTION **)v6 )
    {
      v7 = *(struct _TRACERPT_STRING **)v6;
      if ( *(struct _TRACERPT_STRING **)(*(_QWORD *)v6 + 8LL) != v6 )
        goto LABEL_21;
      v8 = (struct _TRACERPT_STRING **)*((_QWORD *)v6 + 1);
      if ( *v8 != v6 )
        goto LABEL_21;
      v9 = v6;
      *v8 = v7;
      v6 = v7;
      *((_QWORD *)v7 + 1) = v8;
      DeleteTracerptString(v9);
    }
    v10 = (struct _TRACERPT_SECTION **)v1[4];
    while ( v1 + 4 != v10 )
    {
      v11 = (struct _TRACERPT_SECTION **)*v10;
      if ( *((struct _TRACERPT_SECTION ***)*v10 + 1) != v10 )
        goto LABEL_21;
      v12 = (struct _TRACERPT_SECTION ***)v10[1];
      if ( *v12 != v10 )
        goto LABEL_21;
      *v12 = v11;
      v13 = v10;
      v10 = v11;
      v11[1] = (struct _TRACERPT_SECTION *)v12;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v13);
    }
    v15 = v1[23];
    if ( v15 )
    {
      v16 = GetProcessHeap();
      HeapFree(v16, 0, v15);
    }
    v1[13] = (struct _TRACERPT_SECTION *)&RptStringHashTable<256>::`vftable';
    HashTable<RPT_STRING,0,0>::~HashTable<RPT_STRING,0,0>();
    v1[6] = (struct _TRACERPT_SECTION *)&RptStringHashTable<256>::`vftable';
    HashTable<RPT_STRING,0,0>::~HashTable<RPT_STRING,0,0>();
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x14003252c  push    rbx
0x14003252e  push    rsi
0x14003252f  push    rdi
0x140032530  push    r14
0x140032532  sub     rsp, 28h
0x140032536  mov     rdi, [rcx+40h]
0x14003253a  test    rdi, rdi
0x14003253d  jz      loc_140032646
0x140032543  mov     rbx, [rdi]
0x140032546  jmp     short loc_140032574
0x140032548  mov     rax, [rbx]
0x14003254b  cmp     [rax+8], rbx
0x14003254f  jnz     loc_140032650
0x140032555  mov     rdx, [rbx+8]
0x140032559  cmp     [rdx], rbx
0x14003255c  jnz     loc_140032650
0x140032562  mov     rcx, rbx; this
0x140032565  mov     [rdx], rax
0x140032568  mov     rbx, rax
0x14003256b  mov     [rax+8], rdx
0x14003256f  call    ?DeleteTracerptSection@@YAXPEAU_TRACERPT_SECTION@@@Z; DeleteTracerptSection(_TRACERPT_SECTION *)
0x140032574  cmp     rdi, rbx
0x140032577  jnz     short loc_140032548
0x140032579  lea     rsi, [rdi+10h]
0x14003257d  mov     rbx, [rsi]
0x140032580  jmp     short loc_1400325AE
0x140032582  mov     rax, [rbx]
0x140032585  cmp     [rax+8], rbx
0x140032589  jnz     loc_140032650
0x14003258f  mov     rdx, [rbx+8]
0x140032593  cmp     [rdx], rbx
0x140032596  jnz     loc_140032650
0x14003259c  mov     rcx, rbx; Block
0x14003259f  mov     [rdx], rax
0x1400325a2  mov     rbx, rax
0x1400325a5  mov     [rax+8], rdx
0x1400325a9  call    ?DeleteTracerptString@@YAXPEAU_TRACERPT_STRING@@@Z; DeleteTracerptString(_TRACERPT_STRING *)
0x1400325ae  cmp     rsi, rbx
0x1400325b1  jnz     short loc_140032582
0x1400325b3  lea     r14, [rdi+20h]
0x1400325b7  mov     rsi, [r14]
0x1400325ba  jmp     short loc_1400325F3
0x1400325bc  mov     rax, [rsi]
0x1400325bf  cmp     [rax+8], rsi
0x1400325c3  jnz     loc_140032650
0x1400325c9  mov     rcx, [rsi+8]
0x1400325cd  cmp     [rcx], rsi
0x1400325d0  jnz     short loc_140032650
0x1400325d2  mov     [rcx], rax
0x1400325d5  mov     rbx, rsi
0x1400325d8  mov     rsi, rax
0x1400325db  mov     [rax+8], rcx
0x1400325df  call    cs:__imp_GetProcessHeap
0x1400325e5  mov     r8, rbx; lpMem
0x1400325e8  xor     edx, edx; dwFlags
0x1400325ea  mov     rcx, rax; hHeap
0x1400325ed  call    cs:__imp_HeapFree
0x1400325f3  cmp     r14, rsi
0x1400325f6  jnz     short loc_1400325BC
0x1400325f8  mov     rbx, [rdi+0B8h]
0x1400325ff  test    rbx, rbx
0x140032602  jz      short loc_140032618
0x140032604  call    cs:__imp_GetProcessHeap
0x14003260a  mov     r8, rbx; lpMem
0x14003260d  xor     edx, edx; dwFlags
0x14003260f  mov     rcx, rax; hHeap
0x140032612  call    cs:__imp_HeapFree
0x140032618  lea     rcx, [rdi+68h]
0x14003261c  lea     rax, ??_7?$RptStringHashTable@$0BAA@@@6B@; const RptStringHashTable<256>::`vftable'
0x140032623  mov     [rcx], rax
0x140032626  call    ??1?$HashTable@VRPT_STRING@@$0A@$0A@@@QEAA@XZ; HashTable<RPT_STRING,0,0>::~HashTable<RPT_STRING,0,0>(void)
0x14003262b  lea     rcx, [rdi+30h]
0x14003262f  lea     rax, ??_7?$RptStringHashTable@$0BAA@@@6B@; const RptStringHashTable<256>::`vftable'
0x140032636  mov     [rcx], rax
0x140032639  call    ??1?$HashTable@VRPT_STRING@@$0A@$0A@@@QEAA@XZ; HashTable<RPT_STRING,0,0>::~HashTable<RPT_STRING,0,0>(void)
0x14003263e  mov     rcx, rdi; Block
0x140032641  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140032646  add     rsp, 28h
0x14003264a  pop     r14
0x14003264c  pop     rdi
0x14003264d  pop     rsi
0x14003264e  pop     rbx
0x14003264f  retn
0x140032650  mov     ecx, 3
0x140032655  int     29h; Win8: RtlFailFast(ecx)
```
