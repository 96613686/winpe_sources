# DeleteTracerptSection(_TRACERPT_SECTION *)

- ea: `0x140032660`
- end: `0x14003289c`
- name: `?DeleteTracerptSection@@YAXPEAU_TRACERPT_SECTION@@@Z`
- size: `572`
- prototype: `void __fastcall(struct _TRACERPT_SECTION *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14003252c`

## callees

- `0x1400020f0`
- `0x140030694`
- `0x14003074c`
- `0x1400307e4`
- `0x1400308a0`
- `0x140032660`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140032750`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400327e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003283d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140032750`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400327e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003283d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140032742`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400327d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003282f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140032742`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400327d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003282f`

## pseudocode

```c
void __fastcall DeleteTracerptSection(struct _TRACERPT_SECTION *this)
{
  char *v1; // r12
  struct _TRACERPT_SECTION *v3; // rdi
  char *v4; // r14
  struct _TRACERPT_SECTION **v5; // rax
  _TRACERPT_COLUMN *v6; // rsi
  _TRACERPT_COLUMN *v7; // rax
  _TRACERPT_COLUMN **v8; // rcx
  _TRACERPT_COLUMN *v9; // rbx
  _TRACERPT_COLUMN *v10; // rsi
  _TRACERPT_COLUMN *v11; // rax
  _TRACERPT_COLUMN **v12; // rcx
  _TRACERPT_COLUMN *v13; // rbx
  _TRACERPT_EVENT_TABLE *v14; // rbx
  void *v15; // rsi
  HANDLE ProcessHeap; // rax
  struct _TRACERPT_SECTION *v17; // rdi
  struct _TRACERPT_SECTION *v18; // r14
  struct _TRACERPT_SECTION **v19; // rax
  _QWORD *v20; // rbx
  _QWORD *v21; // rax
  _QWORD *v22; // rdx
  _QWORD *v23; // r13
  void *v24; // r12
  HANDLE v25; // rax
  _QWORD *v26; // rbx
  _QWORD *v27; // rax
  _QWORD *v28; // rdx
  _QWORD *v29; // r13
  void *v30; // r12
  HANDLE v31; // rax
  _TRACERPT_COUNTER_TABLE *v32; // rbx

  v1 = (char *)this + 16;
  v3 = (struct _TRACERPT_SECTION *)*((_QWORD *)this + 2);
  if ( (struct _TRACERPT_SECTION *)((char *)this + 16) != v3 )
  {
    while ( 1 )
    {
      v4 = *(char **)v3;
      if ( *(struct _TRACERPT_SECTION **)(*(_QWORD *)v3 + 8LL) != v3 )
        break;
      v5 = (struct _TRACERPT_SECTION **)*((_QWORD *)v3 + 1);
      if ( *v5 != v3 )
        break;
      *v5 = (struct _TRACERPT_SECTION *)v4;
      *((_QWORD *)v4 + 1) = v5;
      v6 = (_TRACERPT_COLUMN *)*((_QWORD *)v3 + 2);
      while ( (struct _TRACERPT_SECTION *)((char *)v3 + 16) != v6 )
      {
        v7 = *(_TRACERPT_COLUMN **)v6;
        if ( *(_TRACERPT_COLUMN **)(*(_QWORD *)v6 + 8LL) != v6 )
          goto LABEL_38;
        v8 = (_TRACERPT_COLUMN **)*((_QWORD *)v6 + 1);
        if ( *v8 != v6 )
          goto LABEL_38;
        *v8 = v7;
        v9 = v6;
        *((_QWORD *)v7 + 1) = v8;
        v6 = v7;
        _TRACERPT_COLUMN::~_TRACERPT_COLUMN(v9);
        operator delete(v9);
      }
      v10 = (_TRACERPT_COLUMN *)*((_QWORD *)v3 + 73);
      while ( (struct _TRACERPT_SECTION *)((char *)v3 + 584) != v10 )
      {
        v11 = *(_TRACERPT_COLUMN **)v10;
        if ( *(_TRACERPT_COLUMN **)(*(_QWORD *)v10 + 8LL) != v10 )
          goto LABEL_38;
        v12 = (_TRACERPT_COLUMN **)*((_QWORD *)v10 + 1);
        if ( *v12 != v10 )
          goto LABEL_38;
        *v12 = v11;
        v13 = v10;
        *((_QWORD *)v11 + 1) = v12;
        v10 = v11;
        _TRACERPT_COLUMN::~_TRACERPT_COLUMN(v13);
        operator delete(v13);
      }
      v14 = v3;
      v3 = (struct _TRACERPT_SECTION *)v4;
      v15 = (void *)*((_QWORD *)v14 + 5);
      if ( v15 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v15);
      }
      _TRACERPT_EVENT_TABLE::~_TRACERPT_EVENT_TABLE(v14);
      operator delete(v14);
      if ( v1 == v4 )
        goto LABEL_17;
    }
LABEL_38:
    __fastfail(3u);
  }
LABEL_17:
  v17 = (struct _TRACERPT_SECTION *)*((_QWORD *)this + 4);
  if ( (struct _TRACERPT_SECTION *)((char *)this + 32) != v17 )
  {
    do
    {
      v18 = *(struct _TRACERPT_SECTION **)v17;
      if ( *(struct _TRACERPT_SECTION **)(*(_QWORD *)v17 + 8LL) != v17 )
        goto LABEL_38;
      v19 = (struct _TRACERPT_SECTION **)*((_QWORD *)v17 + 1);
      if ( *v19 != v17 )
        goto LABEL_38;
      *v19 = v18;
      *((_QWORD *)v18 + 1) = v19;
      v20 = (_QWORD *)*((_QWORD *)v17 + 2);
      while ( (_QWORD *)((char *)v17 + 16) != v20 )
      {
        v21 = (_QWORD *)*v20;
        if ( *(_QWORD **)(*v20 + 8LL) != v20 )
          goto LABEL_38;
        v22 = (_QWORD *)v20[1];
        if ( (_QWORD *)*v22 != v20 )
          goto LABEL_38;
        v23 = v20;
        *v22 = v21;
        v21[1] = v22;
        v20 = v21;
        v24 = (void *)v23[4];
        if ( v24 )
        {
          v25 = GetProcessHeap();
          HeapFree(v25, 0, v24);
        }
        operator delete(v23);
      }
      v26 = (_QWORD *)*((_QWORD *)v17 + 4);
      while ( (_QWORD *)((char *)v17 + 32) != v26 )
      {
        v27 = (_QWORD *)*v26;
        if ( *(_QWORD **)(*v26 + 8LL) != v26 )
          goto LABEL_38;
        v28 = (_QWORD *)v26[1];
        if ( (_QWORD *)*v28 != v26 )
          goto LABEL_38;
        v29 = v26;
        *v28 = v27;
        v27[1] = v28;
        v26 = v27;
        v30 = (void *)v29[4];
        if ( v30 )
        {
          v31 = GetProcessHeap();
          HeapFree(v31, 0, v30);
        }
        operator delete(v29);
      }
      v32 = v17;
      v17 = v18;
      _TRACERPT_COUNTER_TABLE::~_TRACERPT_COUNTER_TABLE(v32);
      operator delete(v32);
    }
    while ( (struct _TRACERPT_SECTION *)((char *)this + 32) != v18 );
  }
  if ( this )
  {
    _TRACERPT_SECTION::~_TRACERPT_SECTION(this);
    operator delete(this);
  }
}

```

## disassembly

```asm
0x140032660  push    rbx
0x140032662  push    rbp
0x140032663  push    rsi
0x140032664  push    rdi
0x140032665  push    r12
0x140032667  push    r13
0x140032669  push    r14
0x14003266b  push    r15
0x14003266d  sub     rsp, 28h
0x140032671  lea     r12, [rcx+10h]
0x140032675  mov     rbp, rcx
0x140032678  mov     rdi, [r12]
0x14003267c  cmp     r12, rdi
0x14003267f  jz      loc_14003276F
0x140032685  mov     r14, [rdi]
0x140032688  cmp     [r14+8], rdi
0x14003268c  jnz     loc_140032895
0x140032692  mov     rax, [rdi+8]
0x140032696  cmp     [rax], rdi
0x140032699  jnz     loc_140032895
0x14003269f  mov     [rax], r14
0x1400326a2  lea     r15, [rdi+10h]
0x1400326a6  mov     [r14+8], rax
0x1400326aa  mov     rsi, [r15]
0x1400326ad  jmp     short loc_1400326E6
0x1400326af  mov     rax, [rsi]
0x1400326b2  cmp     [rax+8], rsi
0x1400326b6  jnz     loc_140032895
0x1400326bc  mov     rcx, [rsi+8]
0x1400326c0  cmp     [rcx], rsi
0x1400326c3  jnz     loc_140032895
0x1400326c9  mov     [rcx], rax
0x1400326cc  mov     rbx, rsi
0x1400326cf  mov     [rax+8], rcx
0x1400326d3  mov     rsi, rax
0x1400326d6  mov     rcx, rbx; this
0x1400326d9  call    ??1_TRACERPT_COLUMN@@QEAA@XZ; _TRACERPT_COLUMN::~_TRACERPT_COLUMN(void)
0x1400326de  mov     rcx, rbx; Block
0x1400326e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400326e6  cmp     r15, rsi
0x1400326e9  jnz     short loc_1400326AF
0x1400326eb  lea     r15, [rdi+248h]
0x1400326f2  mov     rsi, [r15]
0x1400326f5  jmp     short loc_14003272E
0x1400326f7  mov     rax, [rsi]
0x1400326fa  cmp     [rax+8], rsi
0x1400326fe  jnz     loc_140032895
0x140032704  mov     rcx, [rsi+8]
0x140032708  cmp     [rcx], rsi
0x14003270b  jnz     loc_140032895
0x140032711  mov     [rcx], rax
0x140032714  mov     rbx, rsi
0x140032717  mov     [rax+8], rcx
0x14003271b  mov     rsi, rax
0x14003271e  mov     rcx, rbx; this
0x140032721  call    ??1_TRACERPT_COLUMN@@QEAA@XZ; _TRACERPT_COLUMN::~_TRACERPT_COLUMN(void)
0x140032726  mov     rcx, rbx; Block
0x140032729  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003272e  cmp     r15, rsi
0x140032731  jnz     short loc_1400326F7
0x140032733  mov     rbx, rdi
0x140032736  mov     rdi, r14
0x140032739  mov     rsi, [rbx+28h]
0x14003273d  test    rsi, rsi
0x140032740  jz      short loc_140032756
0x140032742  call    cs:__imp_GetProcessHeap
0x140032748  mov     r8, rsi; lpMem
0x14003274b  xor     edx, edx; dwFlags
0x14003274d  mov     rcx, rax; hHeap
0x140032750  call    cs:__imp_HeapFree
0x140032756  mov     rcx, rbx; this
0x140032759  call    ??1_TRACERPT_EVENT_TABLE@@QEAA@XZ; _TRACERPT_EVENT_TABLE::~_TRACERPT_EVENT_TABLE(void)
0x14003275e  mov     rcx, rbx; Block
0x140032761  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140032766  cmp     r12, r14
0x140032769  jnz     loc_140032685
0x14003276f  lea     r15, [rbp+20h]
0x140032773  mov     rdi, [r15]
0x140032776  cmp     r15, rdi
0x140032779  jz      loc_14003286F
0x14003277f  mov     r14, [rdi]
0x140032782  cmp     [r14+8], rdi
0x140032786  jnz     loc_140032895
0x14003278c  mov     rax, [rdi+8]
0x140032790  cmp     [rax], rdi
0x140032793  jnz     loc_140032895
0x140032799  mov     [rax], r14
0x14003279c  lea     rsi, [rdi+10h]
0x1400327a0  mov     [r14+8], rax
0x1400327a4  mov     rbx, [rsi]
0x1400327a7  jmp     short loc_1400327F5
0x1400327a9  mov     rax, [rbx]
0x1400327ac  cmp     [rax+8], rbx
0x1400327b0  jnz     loc_140032895
0x1400327b6  mov     rdx, [rbx+8]
0x1400327ba  cmp     [rdx], rbx
0x1400327bd  jnz     loc_140032895
0x1400327c3  mov     r13, rbx
0x1400327c6  mov     [rdx], rax
0x1400327c9  mov     [rax+8], rdx
0x1400327cd  mov     rbx, rax
0x1400327d0  mov     r12, [r13+20h]
0x1400327d4  test    r12, r12
0x1400327d7  jz      short loc_1400327ED
0x1400327d9  call    cs:__imp_GetProcessHeap
0x1400327df  mov     r8, r12; lpMem
0x1400327e2  xor     edx, edx; dwFlags
0x1400327e4  mov     rcx, rax; hHeap
0x1400327e7  call    cs:__imp_HeapFree
0x1400327ed  mov     rcx, r13; Block
0x1400327f0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400327f5  cmp     rsi, rbx
0x1400327f8  jnz     short loc_1400327A9
0x1400327fa  lea     rsi, [rdi+20h]
0x1400327fe  mov     rbx, [rsi]
0x140032801  jmp     short loc_14003284B
0x140032803  mov     rax, [rbx]
0x140032806  cmp     [rax+8], rbx
0x14003280a  jnz     loc_140032895
0x140032810  mov     rdx, [rbx+8]
0x140032814  cmp     [rdx], rbx
0x140032817  jnz     short loc_140032895
0x140032819  mov     r13, rbx
0x14003281c  mov     [rdx], rax
0x14003281f  mov     [rax+8], rdx
0x140032823  mov     rbx, rax
0x140032826  mov     r12, [r13+20h]
0x14003282a  test    r12, r12
0x14003282d  jz      short loc_140032843
0x14003282f  call    cs:__imp_GetProcessHeap
0x140032835  mov     r8, r12; lpMem
0x140032838  xor     edx, edx; dwFlags
0x14003283a  mov     rcx, rax; hHeap
0x14003283d  call    cs:__imp_HeapFree
0x140032843  mov     rcx, r13; Block
0x140032846  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003284b  cmp     rsi, rbx
0x14003284e  jnz     short loc_140032803
0x140032850  mov     rbx, rdi
0x140032853  mov     rdi, r14
0x140032856  mov     rcx, rbx; this
0x140032859  call    ??1_TRACERPT_COUNTER_TABLE@@QEAA@XZ; _TRACERPT_COUNTER_TABLE::~_TRACERPT_COUNTER_TABLE(void)
0x14003285e  mov     rcx, rbx; Block
0x140032861  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140032866  cmp     r15, r14
0x140032869  jnz     loc_14003277F
0x14003286f  test    rbp, rbp
0x140032872  jz      short loc_140032884
0x140032874  mov     rcx, rbp; this
0x140032877  call    ??1_TRACERPT_SECTION@@QEAA@XZ; _TRACERPT_SECTION::~_TRACERPT_SECTION(void)
0x14003287c  mov     rcx, rbp; Block
0x14003287f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140032884  add     rsp, 28h
0x140032888  pop     r15
0x14003288a  pop     r14
0x14003288c  pop     r13
0x14003288e  pop     r12
0x140032890  pop     rdi
0x140032891  pop     rsi
0x140032892  pop     rbp
0x140032893  pop     rbx
0x140032894  retn
0x140032895  mov     ecx, 3
0x14003289a  int     29h; Win8: RtlFailFast(ecx)
```
