# CabWriter::CreateCab(ushort const *,CAB_OPTIONS,ulong,ulong)

- ea: `0x1800693c4`
- end: `0x180069617`
- name: `?CreateCab@CabWriter@@QEAAJPEBGW4CAB_OPTIONS@@KK@Z`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180066e28`

## callees

- `0x18000ab10`
- `0x180039e88`
- `0x180068d54`
- `0x180068e68`
- `0x1800690b8`
- `0x1800693c4`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800695bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800695f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800695bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800695f4`
- `Cabinet!__imp_FCICreate` at `0x180069541`
- `Cabinet!__imp_FCICreate` at `0x180069541`
- `Cabinet!__imp_FCIDestroy` at `0x1800695cd`
- `Cabinet!__imp_FCIDestroy` at `0x1800695cd`

## pseudocode

```c
__int64 __fastcall CabWriter::CreateCab(__int64 a1, const unsigned __int16 *a2, int a3)
{
  _WORD *v5; // rbp
  const WCHAR *v6; // r10
  UINT v7; // ecx
  int v8; // ebx
  unsigned __int64 v9; // r8
  unsigned int v10; // r10d
  HFCI v11; // rax
  UINT v12; // ecx
  PFNFCIOPEN pfnopen; // [rsp+20h] [rbp-A8h]
  char *v15; // [rsp+70h] [rbp-58h] BYREF
  unsigned __int16 *v16; // [rsp+D0h] [rbp+8h] BYREF

  if ( *(_QWORD *)(a1 + 1048) )
    return (unsigned int)-2147467259;
  if ( !a2 )
    return (unsigned int)-2147467259;
  v5 = (_WORD *)(a1 + 524);
  if ( (int)StringCchCopyW((unsigned __int16 *)(a1 + 524), 0x104u, a2) < 0 )
    return (unsigned int)-2147467259;
  v7 = *(_DWORD *)a1;
  *(_DWORD *)(a1 + 1056) = 0x80000000;
  *(_DWORD *)(a1 + 1060) = 0x100000;
  v15 = 0;
  v8 = UnicodeToAnsiWithAlloc(v7, v6, &v15);
  if ( v8 >= 0 )
  {
    v8 = SplitFileNameA(v15, (char *)(a1 + 4), v9, (char *)(a1 + 264), (unsigned __int64)pfnopen);
    if ( v8 >= 0 )
    {
      v8 = StringCchCopyA((char *)(a1 + 1602), 0x100u, (const char *)(a1 + 4));
      if ( v8 >= 0 )
      {
        v8 = StringCchCopyA((char *)(a1 + 1346), v10, (const char *)(a1 + 264));
        if ( v8 >= 0 )
        {
          *(_DWORD *)(a1 + 1896) = a3;
          *(_DWORD *)(a1 + 1860) = 0;
          v11 = FCICreate(
                  (PERF)(a1 + 1864),
                  CabWriter::FciFilePlaced,
                  CabReader::FdiMemAlloc,
                  (PFNFCIFREE)CabWriter::FciMemFree,
                  (PFNFCIOPEN)CabWriter::FciFileOpen,
                  CabWriter::FciFileRead,
                  (PFNFCIWRITE)CabWriter::FciFileWrite,
                  CabWriter::FciFileClose,
                  CabWriter::FciFileSeek,
                  CabWriter::FciFileDelete,
                  CabWriter::FciGetTempFile,
                  (PCCAB)(a1 + 1056),
                  (void *)a1);
          *(_QWORD *)(a1 + 1048) = v11;
          if ( v11 )
          {
            v8 = 0;
            if ( !*(_QWORD *)(a1 + 1880) )
              goto LABEL_17;
            v12 = *(_DWORD *)a1;
            v16 = 0;
            v8 = AnsiToUnicodeWithAlloc(v12, (LPCCH)(a1 + 1346), &v16);
            if ( v8 >= 0 )
            {
              if ( (*(unsigned int (__fastcall **)(__int64, unsigned __int16 *, _QWORD, _QWORD))(a1 + 1880))(
                     4,
                     v16,
                     0,
                     *(_QWORD *)(a1 + 1888)) == -1 )
                v8 = -2147023673;
              CoTaskMemFree(v16);
              if ( v8 >= 0 )
                goto LABEL_17;
            }
            FCIDestroy(*(HFCI *)(a1 + 1048));
            *(_QWORD *)(a1 + 1048) = 0;
          }
          else
          {
            v8 = -2147467259;
          }
        }
      }
      *(_BYTE *)(a1 + 4) = 0;
      *v5 = 0;
      *(_BYTE *)(a1 + 264) = 0;
    }
LABEL_17:
    CoTaskMemFree(v15);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800693c4  push    rbx
0x1800693c6  push    rbp
0x1800693c7  push    rsi
0x1800693c8  push    rdi
0x1800693c9  push    r12
0x1800693cb  push    r13
0x1800693cd  push    r14
0x1800693cf  push    r15
0x1800693d1  sub     rsp, 88h
0x1800693d8  cmp     qword ptr [rcx+418h], 0
0x1800693e0  mov     r13d, r8d
0x1800693e3  mov     r10, rdx
0x1800693e6  mov     rdi, rcx
0x1800693e9  jnz     loc_1800695FC
0x1800693ef  test    rdx, rdx
0x1800693f2  jz      loc_1800695FC
0x1800693f8  lea     rbp, [rcx+20Ch]
0x1800693ff  mov     r8, rdx; unsigned __int16 *
0x180069402  mov     rcx, rbp; unsigned __int16 *
0x180069405  mov     edx, 104h; unsigned __int64
0x18006940a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006940f  test    eax, eax
0x180069411  js      loc_1800695FC
0x180069417  mov     ecx, [rdi]; CodePage
0x180069419  lea     rsi, [rdi+420h]
0x180069420  lea     r8, [rsp+0C8h+var_58]; char **
0x180069425  mov     dword ptr [rsi], 80000000h
0x18006942b  mov     rdx, r10; lpWideCharStr
0x18006942e  mov     dword ptr [rdi+424h], 100000h
0x180069438  mov     [rsp+0C8h+var_58], 0
0x180069441  call    ?UnicodeToAnsiWithAlloc@@YAJIPEBGPEAPEAD@Z; UnicodeToAnsiWithAlloc(uint,ushort const *,char * *)
0x180069446  mov     ebx, eax
0x180069448  test    eax, eax
0x18006944a  js      loc_180069601
0x180069450  mov     rcx, [rsp+0C8h+var_58]; char *
0x180069455  lea     r15, [rdi+108h]
0x18006945c  lea     r14, [rdi+4]
0x180069460  mov     r9, r15; char *
0x180069463  mov     rdx, r14; char *
0x180069466  call    ?SplitFileNameA@@YAJPEBDPEAD_K12@Z; SplitFileNameA(char const *,char *,unsigned __int64,char *,unsigned __int64)
0x18006946b  mov     ebx, eax
0x18006946d  test    eax, eax
0x18006946f  js      loc_1800695EF
0x180069475  mov     r10d, 100h
0x18006947b  lea     rcx, [rsi+222h]; char *
0x180069482  mov     edx, r10d; unsigned __int64
0x180069485  mov     r8, r14; char *
0x180069488  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18006948d  mov     ebx, eax
0x18006948f  test    eax, eax
0x180069491  js      loc_1800695E1
0x180069497  lea     r12, [rsi+122h]
0x18006949e  mov     r8, r15; char *
0x1800694a1  mov     rcx, r12; char *
0x1800694a4  mov     edx, r10d; unsigned __int64
0x1800694a7  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800694ac  mov     ebx, eax
0x1800694ae  test    eax, eax
0x1800694b0  js      loc_1800695E1
0x1800694b6  mov     [rsp+0C8h+pv], rdi; pv
0x1800694bb  lea     rax, ?FciGetTempFile@CabWriter@@CAHPEADHPEAX@Z; CabWriter::FciGetTempFile(char *,int,void *)
0x1800694c2  mov     [rsp+0C8h+pccab], rsi; pccab
0x1800694c7  lea     rcx, [rdi+748h]; perf
0x1800694ce  mov     [rsp+0C8h+pfnfcigtf], rax; pfnfcigtf
0x1800694d3  lea     r9, ?FciMemFree@CabWriter@@CAXPEAX@Z; pfnf
0x1800694da  lea     rax, ?FciFileDelete@CabWriter@@CAHPEADPEAHPEAX@Z; CabWriter::FciFileDelete(char *,int *,void *)
0x1800694e1  mov     [rdi+768h], r13d
0x1800694e8  mov     [rsp+0C8h+pfndelete], rax; pfndelete
0x1800694ed  lea     r8, ?FdiMemAlloc@CabReader@@CAPEAXK@Z; pfna
0x1800694f4  lea     rax, ?FciFileSeek@CabWriter@@CAJ_JJHPEAHPEAX@Z; CabWriter::FciFileSeek(__int64,long,int,int *,void *)
0x1800694fb  xor     r13d, r13d
0x1800694fe  mov     [rsp+0C8h+pfnseek], rax; pfnseek
0x180069503  lea     rdx, ?FciFilePlaced@CabWriter@@CAHPEAUCCAB@@PEADJHPEAX@Z; pfnfcifp
0x18006950a  lea     rax, ?FciFileClose@CabWriter@@CAH_JPEAHPEAX@Z; CabWriter::FciFileClose(__int64,int *,void *)
0x180069511  mov     [rdi+744h], r13d
0x180069518  mov     [rsp+0C8h+pfnclose], rax; pfnclose
0x18006951d  lea     rax, ?FciFileWrite@CabWriter@@CAI_JPEAXIPEAH1@Z; CabWriter::FciFileWrite(__int64,void *,uint,int *,void *)
0x180069524  mov     [rsp+0C8h+pfnwrite], rax; pfnwrite
0x180069529  lea     rax, ?FciFileRead@CabWriter@@CAI_JPEAXIPEAH1@Z; CabWriter::FciFileRead(__int64,void *,uint,int *,void *)
0x180069530  mov     [rsp+0C8h+pfnread], rax; pfnread
0x180069535  lea     rax, ?FciFileOpen@CabWriter@@CA_JPEADHHPEAHPEAX@Z; CabWriter::FciFileOpen(char *,int,int,int *,void *)
0x18006953c  mov     [rsp+0C8h+pfnopen], rax; pfnopen
0x180069541  call    cs:__imp_FCICreate
0x180069547  mov     [rdi+418h], rax
0x18006954e  test    rax, rax
0x180069551  jz      loc_1800695DC
0x180069557  mov     ebx, r13d
0x18006955a  cmp     [rdi+758h], r13
0x180069561  jz      loc_1800695EF
0x180069567  mov     ecx, [rdi]; CodePage
0x180069569  lea     r8, [rsp+0C8h+arg_0]; unsigned __int16 **
0x180069571  mov     rdx, r12; lpMultiByteStr
0x180069574  mov     [rsp+0C8h+arg_0], r13
0x18006957c  call    ?AnsiToUnicodeWithAlloc@@YAJIPEBDPEAPEAG@Z; AnsiToUnicodeWithAlloc(uint,char const *,ushort * *)
0x180069581  mov     ebx, eax
0x180069583  test    eax, eax
0x180069585  js      short loc_1800695C6
0x180069587  mov     r9, [rdi+760h]
0x18006958e  lea     ecx, [r13+4]
0x180069592  mov     rdx, [rsp+0C8h+arg_0]
0x18006959a  xor     r8d, r8d
0x18006959d  mov     rax, [rdi+758h]
0x1800695a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800695a9  cmp     eax, 0FFFFFFFFh
0x1800695ac  mov     ecx, 800704C7h
0x1800695b1  cmovz   ebx, ecx
0x1800695b4  mov     rcx, [rsp+0C8h+arg_0]; pv
0x1800695bc  call    cs:__imp_CoTaskMemFree
0x1800695c2  test    ebx, ebx
0x1800695c4  jns     short loc_1800695EF
0x1800695c6  mov     rcx, [rdi+418h]; hfci
0x1800695cd  call    cs:__imp_FCIDestroy
0x1800695d3  mov     [rdi+418h], r13
0x1800695da  jmp     short loc_1800695E1
0x1800695dc  mov     ebx, 80004005h
0x1800695e1  xor     eax, eax
0x1800695e3  mov     byte ptr [r14], 0
0x1800695e7  mov     [rbp+0], ax
0x1800695eb  mov     byte ptr [r15], 0
0x1800695ef  mov     rcx, [rsp+0C8h+var_58]; pv
0x1800695f4  call    cs:__imp_CoTaskMemFree
0x1800695fa  jmp     short loc_180069601
0x1800695fc  mov     ebx, 80004005h
0x180069601  mov     eax, ebx
0x180069603  add     rsp, 88h
0x18006960a  pop     r15
0x18006960c  pop     r14
0x18006960e  pop     r13
0x180069610  pop     r12
0x180069612  pop     rdi
0x180069613  pop     rsi
0x180069614  pop     rbp
0x180069615  pop     rbx
0x180069616  retn
```
