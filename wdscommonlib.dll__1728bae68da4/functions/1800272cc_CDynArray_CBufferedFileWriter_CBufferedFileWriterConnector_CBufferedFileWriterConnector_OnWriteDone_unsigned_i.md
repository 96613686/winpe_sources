# CDynArray<CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::DATA_SEGMENT,CDeallocateNone>::AddItem(CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::DATA_SEGMENT)

- ea: `0x1800272cc`
- end: `0x1800273db`
- name: `?AddItem@?$CDynArray@UDATA_SEGMENT@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@VCDeallocateNone@@@@QEAAKUDATA_SEGMENT@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180027720`

## callees

- `0x18000214c`
- `0x1800024b2`
- `0x180027240`
- `0x1800272cc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180027375`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027375`

## pseudocode

```c
__int64 __fastcall CDynArray<CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>::DATA_SEGMENT,CDeallocateNone>::AddItem(
        __int64 a1,
        __int64 a2)
{
  unsigned int v3; // edi
  unsigned int v4; // ecx
  int v6; // eax
  unsigned int v7; // edx
  __int64 v8; // rsi
  unsigned __int64 v9; // rax
  char *v10; // rax
  void *v11; // r14
  char *v12; // rbp
  int i; // r15d
  __int64 v14; // xmm1_8
  __int64 v15; // rdx
  _QWORD *v16; // rcx

  v3 = 0;
  v4 = *(_DWORD *)(a1 + 8);
  if ( *(_DWORD *)(a1 + 12) == v4 )
  {
    v6 = v4 >> 1;
    if ( v4 >> 1 < 0x20 )
      v6 = 32;
    v7 = v4 + v6;
    if ( v4 + v6 < v4 )
      return 534;
    v8 = v7;
    v9 = 24LL * v7;
    if ( !is_mul_ok(v7, 0x18u) )
      v9 = -1;
    v10 = (char *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
    v11 = v10;
    if ( !v10 )
      return 8;
    v12 = v10;
    for ( i = v8; v8; --v8 )
    {
      CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>::DATA_SEGMENT::DATA_SEGMENT(v12);
      v12 += 24;
    }
    memmove_0(v11, *(const void **)a1, 24LL * *(unsigned int *)(a1 + 8));
    operator delete(*(void **)a1);
    *(_QWORD *)a1 = v11;
    *(_DWORD *)(a1 + 8) = i;
  }
  v14 = *(_QWORD *)(a2 + 16);
  v15 = 3LL * *(unsigned int *)(a1 + 12);
  v16 = *(_QWORD **)a1;
  *(_OWORD *)&v16[v15] = *(_OWORD *)a2;
  v16[v15 + 2] = v14;
  ++*(_DWORD *)(a1 + 12);
  return v3;
}

```

## disassembly

```asm
0x1800272cc  mov     rax, rsp
0x1800272cf  mov     [rax+8], rbx
0x1800272d3  mov     [rax+10h], rbp
0x1800272d7  mov     [rax+18h], rsi
0x1800272db  mov     [rax+20h], rdi
0x1800272df  push    r12
0x1800272e1  push    r14
0x1800272e3  push    r15
0x1800272e5  sub     rsp, 20h
0x1800272e9  mov     rbx, rcx
0x1800272ec  xor     edi, edi
0x1800272ee  mov     ecx, [rcx+8]
0x1800272f1  mov     r12, rdx
0x1800272f4  cmp     [rbx+0Ch], ecx
0x1800272f7  jnz     loc_180027388
0x1800272fd  lea     edx, [rdi+20h]
0x180027300  mov     eax, ecx
0x180027302  shr     eax, 1
0x180027304  cmp     eax, edx
0x180027306  cmovb   eax, edx
0x180027309  lea     edx, [rcx+rax]
0x18002730c  cmp     edx, ecx
0x18002730e  jb      loc_1800273D4
0x180027314  mov     esi, edx
0x180027316  lea     rcx, [rdi-1]
0x18002731a  lea     eax, [rdi+18h]
0x18002731d  mul     rsi
0x180027320  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180027327  cmovo   rax, rcx
0x18002732b  mov     rcx, rax; unsigned __int64
0x18002732e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180027333  mov     r14, rax
0x180027336  test    rax, rax
0x180027339  jz      loc_1800273CD
0x18002733f  mov     rbp, rax
0x180027342  mov     r15d, esi
0x180027345  test    rsi, rsi
0x180027348  jz      short loc_18002735C
0x18002734a  mov     rcx, rbp
0x18002734d  call    ??0DATA_SEGMENT@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@QEAA@XZ; CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::DATA_SEGMENT::DATA_SEGMENT(void)
0x180027352  add     rbp, 18h
0x180027356  sub     rsi, 1
0x18002735a  jnz     short loc_18002734A
0x18002735c  mov     eax, [rbx+8]
0x18002735f  mov     rcx, r14; void *
0x180027362  mov     rdx, [rbx]; Src
0x180027365  lea     r8, [rax+rax*2]
0x180027369  shl     r8, 3; Size
0x18002736d  call    memmove_0
0x180027372  mov     rcx, [rbx]
0x180027375  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002737c  nop     dword ptr [rax+rax+00h]
0x180027381  mov     [rbx], r14
0x180027384  mov     [rbx+8], r15d
0x180027388  mov     ecx, [rbx+0Ch]
0x18002738b  movaps  xmm0, xmmword ptr [r12]
0x180027390  movsd   xmm1, qword ptr [r12+10h]
0x180027397  lea     rdx, [rcx+rcx*2]
0x18002739b  mov     rcx, [rbx]
0x18002739e  movups  xmmword ptr [rcx+rdx*8], xmm0
0x1800273a2  movsd   qword ptr [rcx+rdx*8+10h], xmm1
0x1800273a8  inc     dword ptr [rbx+0Ch]
0x1800273ab  mov     rbx, [rsp+38h+arg_0]
0x1800273b0  mov     eax, edi
0x1800273b2  mov     rdi, [rsp+38h+arg_18]
0x1800273b7  mov     rbp, [rsp+38h+arg_8]
0x1800273bc  mov     rsi, [rsp+38h+arg_10]
0x1800273c1  add     rsp, 20h
0x1800273c5  pop     r15
0x1800273c7  pop     r14
0x1800273c9  pop     r12
0x1800273cb  retn
0x1800273cd  mov     edi, 8
0x1800273d2  jmp     short loc_1800273AB
0x1800273d4  mov     edi, 216h
0x1800273d9  jmp     short loc_1800273AB
```
