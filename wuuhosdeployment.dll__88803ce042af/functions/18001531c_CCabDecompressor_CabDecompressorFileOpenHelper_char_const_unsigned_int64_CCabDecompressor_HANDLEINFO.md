# CCabDecompressor::CabDecompressorFileOpenHelper(char const *,unsigned __int64,CCabDecompressor *,HANDLEINFO * *)

- ea: `0x18001531c`
- end: `0x180015669`
- name: `?CabDecompressorFileOpenHelper@CCabDecompressor@@CAJPEBD_KPEAV1@PEAPEAUHANDLEINFO@@@Z`
- size: `845`
- prototype: `__int64 __fastcall(const char *, unsigned int, struct CCabDecompressor *, struct HANDLEINFO **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180015ca0`

## callees

- `0x180003950`
- `0x180005f64`
- `0x18000a60c`
- `0x18000cea8`
- `0x18000e2a4`
- `0x18000f27c`
- `0x18001531c`
- `0x1800165a4`
- `0x18002eb34`
- `0x180042630`
- `0x180042a24`
- `0x1800430f8`
- `0x1800492e0`

## string_xrefs

- `0x18001536d`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`
- `0x1800153e6`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`
- `0x1800154dd`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`
- `0x18001559b`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`
- `0x180015584`: `C:\__w\1\s\src\Client\lib\CabDecompressor\OutputMemoryFile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CCabDecompressor::CabDecompressorFileOpenHelper(
        const char *a1,
        unsigned int a2,
        struct CCabDecompressor *a3,
        struct HANDLEINFO **a4)
{
  char *v7; // rax
  void *v8; // r14
  int FileAndDirectories; // ebp
  char *v10; // rax
  char *v11; // rsi
  COutputMemoryFile *v12; // rdi
  char *v13; // rdx
  __int64 v14; // rcx
  char v15; // al
  char *v16; // rax
  int v17; // eax
  void *v18; // rbx
  __int64 v19; // rdx
  unsigned int v20; // r8d
  unsigned int v21; // r9d
  _QWORD *v22; // rax
  _QWORD *v23; // rbx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rdx
  char **v27; // rax
  struct HANDLEINFO **v28; // rax
  char **v30; // rax
  struct _SECURITY_ATTRIBUTES *v31; // [rsp+20h] [rbp-2A8h]
  int v32; // [rsp+20h] [rbp-2A8h]
  unsigned int v33; // [rsp+28h] [rbp-2A0h]
  unsigned int v34; // [rsp+30h] [rbp-298h]
  void *v35; // [rsp+38h] [rbp-290h]
  void *lpMem; // [rsp+50h] [rbp-278h] BYREF
  struct HANDLEINFO **v37; // [rsp+58h] [rbp-270h]
  wchar_t v38[264]; // [rsp+60h] [rbp-268h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+0h]

  v37 = a4;
  *a4 = 0;
  v7 = (char *)SusAlloc(0x20u);
  v8 = v7;
  if ( !v7 )
  {
    FileAndDirectories = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x255,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressor.cpp",
      (const char *)0x8007000ELL,
      (int)v31);
    return (unsigned int)FileAndDirectories;
  }
  *(_QWORD *)(v7 + 20) = 0;
  *(_DWORD *)v7 = 1;
  v10 = (char *)operator new(0x120u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v10 )
  {
    *(_QWORD *)v10 = 0;
    *((_QWORD *)v10 + 1) = 0;
    *((_QWORD *)v10 + 2) = 0;
    v10[24] = 0;
  }
  else
  {
    v11 = 0;
  }
  FileAndDirectories = -2147024882;
  v12 = (COutputMemoryFile *)v11;
  if ( !v11 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x260,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressor.cpp",
      (const char *)0x8007000ELL,
      (int)v31);
    FileAndDirectories = -2147024882;
    goto LABEL_41;
  }
  v13 = v11 + 24;
  v14 = 260;
  do
  {
    if ( v14 == -2147483386 )
      break;
    v15 = v13[a1 - (v11 + 24)];
    if ( !v15 )
      break;
    *v13++ = v15;
    --v14;
  }
  while ( v14 );
  v16 = v13 - 1;
  if ( v14 )
    v16 = v13;
  *v16 = 0;
  if ( *((_DWORD *)a3 + 35) != 1 )
  {
    v22 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v23 = v22;
    if ( v22 )
    {
      v22[1] = 0;
      *v22 = &CSafeBuffer<unsigned char>::`vftable';
      v22[2] = 0;
      if ( a2 )
        CSafeBuffer<unsigned char>::resize(v22, a2);
    }
    else
    {
      v23 = 0;
    }
    *((_QWORD *)v11 + 2) = v23;
    if ( v23 )
    {
      if ( v23[1] )
      {
        *((_QWORD *)v8 + 1) = v23;
        *((_DWORD *)v8 + 4) = 0;
        goto LABEL_35;
      }
      v24 = 39;
    }
    else
    {
      v24 = 38;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\OutputMemoryFile.cpp",
      (const char *)0x8007000ELL,
      (int)v31);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x285,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressor.cpp",
      (const char *)0x8007000ELL,
      v32);
    goto LABEL_41;
  }
  lpMem = 0;
  memset(v38, 0, 522);
  v17 = ConvertAnsiToWide_Alloc(a1, (wchar_t **)&lpMem);
  v18 = lpMem;
  FileAndDirectories = v17;
  if ( v17 < 0 )
  {
    v19 = 621;
    goto LABEL_21;
  }
  FileAndDirectories = WUPathCchCombine(v38, 0x105u, *((const wchar_t **)a3 + 16), (const wchar_t *)lpMem);
  if ( FileAndDirectories < 0 )
  {
    v19 = 626;
    goto LABEL_21;
  }
  FileAndDirectories = SusCreateFileAndDirectories(
                         v38,
                         *((_DWORD *)a3 + 38),
                         v20,
                         v21,
                         v31,
                         v33,
                         v34,
                         v35,
                         (void **)v8 + 1);
  if ( FileAndDirectories < 0 )
  {
    v19 = 636;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressor.cpp",
      (const char *)(unsigned int)FileAndDirectories,
      (int)v31);
    if ( v18 )
      CSusBaseAllocTag<942762101>::operator delete(v18);
    goto LABEL_41;
  }
  *((_DWORD *)v8 + 4) = 1;
  if ( v18 )
    CSusBaseAllocTag<942762101>::operator delete(v18);
LABEL_35:
  v25 = *((_QWORD *)a3 + 8);
  v12 = 0;
  v26 = *(_QWORD *)(v25 + 16);
  *(_QWORD *)(v25 + 32) = v26;
  ++*(_DWORD *)(v25 + 24);
  *(_QWORD *)v11 = v26;
  if ( v26 )
  {
    *((_QWORD *)v11 + 1) = *(_QWORD *)(v26 + 8);
    *(_QWORD *)(v26 + 8) = v11;
    v30 = (char **)*((_QWORD *)v11 + 1);
    if ( v30 )
    {
      *v30 = v11;
      goto LABEL_40;
    }
  }
  else
  {
    v27 = *(char ***)(v25 + 8);
    if ( v27 )
      *v27 = v11;
    *((_QWORD *)v11 + 1) = *(_QWORD *)(v25 + 8);
    *(_QWORD *)(v25 + 8) = v11;
    if ( *(_QWORD *)(v25 + 16) )
      goto LABEL_40;
  }
  *(_QWORD *)(v25 + 16) = v11;
LABEL_40:
  v28 = v37;
  FileAndDirectories = 0;
  *(_QWORD *)(v25 + 32) = v11;
  *v28 = (struct HANDLEINFO *)v8;
  v8 = 0;
LABEL_41:
  CSusBaseAllocTag<942762101>::operator delete(v8);
  if ( v12 )
  {
    COutputMemoryFile::~COutputMemoryFile(v12);
    operator delete(v12, (const struct std::nothrow_t *)0x120);
  }
  return (unsigned int)FileAndDirectories;
}

```

## disassembly

```asm
0x18001531c  push    rbx
0x18001531e  push    rbp
0x18001531f  push    rsi
0x180015320  push    rdi
0x180015321  push    r12
0x180015323  push    r13
0x180015325  push    r14
0x180015327  push    r15
0x180015329  sub     rsp, 288h
0x180015330  mov     rax, cs:__security_cookie
0x180015337  xor     rax, rsp
0x18001533a  mov     [rsp+2C8h+var_58], rax
0x180015342  xor     ebx, ebx
0x180015344  mov     [rsp+2C8h+var_270], r9
0x180015349  mov     r12, rcx
0x18001534c  mov     [r9], rbx
0x18001534f  mov     r13, r8
0x180015352  mov     r15, rdx
0x180015355  lea     ecx, [rbx+20h]; unsigned __int64
0x180015358  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x18001535d  mov     r14, rax
0x180015360  test    rax, rax
0x180015363  jnz     short loc_18001538B
0x180015365  mov     rcx, [rsp+2C8h]; this
0x18001536d  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x180015374  mov     ebp, 8007000Eh
0x180015379  mov     edx, 255h; void *
0x18001537e  mov     r9d, ebp; char *
0x180015381  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015386  jmp     loc_180015629
0x18001538b  mov     [rax+14h], rbx
0x18001538f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015396  mov     ecx, 120h; unsigned __int64
0x18001539b  mov     dword ptr [rax], 1
0x1800153a1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800153a6  xor     r9d, r9d
0x1800153a9  mov     rsi, rax
0x1800153ac  test    rax, rax
0x1800153af  jz      short loc_1800153C2
0x1800153b1  mov     [rax], r9
0x1800153b4  mov     [rax+8], r9
0x1800153b8  mov     [rax+10h], r9
0x1800153bc  mov     [rax+18h], r9b
0x1800153c0  jmp     short loc_1800153C5
0x1800153c2  mov     rsi, r9
0x1800153c5  mov     rax, rsi
0x1800153c8  mov     ebp, 8007000Eh
0x1800153cd  neg     rax
0x1800153d0  mov     rdi, rsi
0x1800153d3  sbb     ebx, ebx
0x1800153d5  not     ebx
0x1800153d7  and     ebx, ebp
0x1800153d9  test    rsi, rsi
0x1800153dc  jnz     short loc_180015401
0x1800153de  mov     rcx, [rsp+2C8h]; this
0x1800153e6  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x1800153ed  mov     r9d, ebx; char *
0x1800153f0  mov     edx, 260h; void *
0x1800153f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800153fa  mov     ebp, ebx
0x1800153fc  jmp     loc_180015607
0x180015401  lea     rdx, [rsi+18h]
0x180015405  mov     r8, r12
0x180015408  sub     r8, rdx
0x18001540b  mov     ecx, 104h
0x180015410  lea     rax, [rcx+7FFFFEFAh]
0x180015417  test    rax, rax
0x18001541a  jz      short loc_18001542F
0x18001541c  mov     al, [rdx+r8]
0x180015420  test    al, al
0x180015422  jz      short loc_18001542F
0x180015424  mov     [rdx], al
0x180015426  inc     rdx
0x180015429  sub     rcx, 1
0x18001542d  jnz     short loc_180015410
0x18001542f  test    rcx, rcx
0x180015432  lea     rax, [rdx-1]
0x180015436  cmovnz  rax, rdx
0x18001543a  mov     [rax], r9b
0x18001543d  cmp     dword ptr [r13+8Ch], 1
0x180015445  jnz     loc_180015520
0x18001544b  xor     edx, edx; Val
0x18001544d  mov     [rsp+2C8h+lpMem], r9
0x180015452  mov     r8d, 208h; Size
0x180015458  mov     [rsp+2C8h+var_268], r9w
0x18001545e  lea     rcx, [rsp+2C8h+var_266]; void *
0x180015463  call    memset
0x180015468  lea     rdx, [rsp+2C8h+lpMem]; wchar_t **
0x18001546d  mov     rcx, r12; lpMultiByteStr
0x180015470  call    ?ConvertAnsiToWide_Alloc@@YAJPEBDPEAPEA_W@Z; ConvertAnsiToWide_Alloc(char const *,wchar_t * *)
0x180015475  mov     rbx, [rsp+2C8h+lpMem]
0x18001547a  xor     r12d, r12d
0x18001547d  mov     ebp, eax
0x18001547f  test    eax, eax
0x180015481  jns     short loc_18001548A
0x180015483  mov     edx, 26Dh
0x180015488  jmp     short loc_1800154D5
0x18001548a  mov     r8, [r13+80h]; wchar_t *
0x180015491  lea     rcx, [rsp+2C8h+var_268]; wchar_t *
0x180015496  mov     r9, rbx; wchar_t *
0x180015499  mov     edx, 105h; unsigned int
0x18001549e  call    ?WUPathCchCombine@@YAJPEA_WKPEB_W1@Z; WUPathCchCombine(wchar_t *,ulong,wchar_t const *,wchar_t const *)
0x1800154a3  mov     ebp, eax
0x1800154a5  test    eax, eax
0x1800154a7  jns     short loc_1800154B0
0x1800154a9  mov     edx, 272h
0x1800154ae  jmp     short loc_1800154D5
0x1800154b0  mov     edx, [r13+98h]; unsigned int
0x1800154b7  lea     rax, [r14+8]
0x1800154bb  lea     rcx, [rsp+2C8h+var_268]; wchar_t *
0x1800154c0  mov     [rsp+2C8h+var_288], rax; void **
0x1800154c5  call    ?SusCreateFileAndDirectories@@YAJPEB_WKKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEAPEAX@Z; SusCreateFileAndDirectories(wchar_t const *,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,void * *)
0x1800154ca  mov     ebp, eax
0x1800154cc  test    eax, eax
0x1800154ce  jns     short loc_180015502
0x1800154d0  mov     edx, 27Ch; void *
0x1800154d5  mov     rcx, [rsp+2C8h]; this
0x1800154dd  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x1800154e4  mov     r9d, ebp; char *
0x1800154e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800154ec  test    rbx, rbx
0x1800154ef  jz      loc_180015607
0x1800154f5  mov     rcx, rbx; lpMem
0x1800154f8  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x1800154fd  jmp     loc_180015607
0x180015502  mov     dword ptr [r14+10h], 1
0x18001550a  test    rbx, rbx
0x18001550d  jz      loc_1800155B9
0x180015513  mov     rcx, rbx; lpMem
0x180015516  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18001551b  jmp     loc_1800155B9
0x180015520  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015527  mov     ecx, 18h; unsigned __int64
0x18001552c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180015531  xor     r12d, r12d
0x180015534  mov     rbx, rax
0x180015537  test    rax, rax
0x18001553a  jz      short loc_180015560
0x18001553c  mov     [rbx+8], r12
0x180015540  lea     rax, ??_7?$CSafeBuffer@E@@6B@; const CSafeBuffer<uchar>::`vftable'
0x180015547  mov     [rbx], rax
0x18001554a  mov     [rbx+10h], r12
0x18001554e  test    r15d, r15d
0x180015551  jz      short loc_180015563
0x180015553  mov     edx, r15d
0x180015556  mov     rcx, rbx
0x180015559  call    ?resize@?$CSafeBuffer@E@@QEAAJI@Z; CSafeBuffer<uchar>::resize(uint)
0x18001555e  jmp     short loc_180015563
0x180015560  mov     rbx, r12
0x180015563  mov     [rsi+10h], rbx
0x180015567  test    rbx, rbx
0x18001556a  jnz     short loc_180015571
0x18001556c  lea     edx, [rbx+26h]
0x18001556f  jmp     short loc_18001557C
0x180015571  cmp     [rbx+8], r12
0x180015575  jnz     short loc_1800155B1
0x180015577  mov     edx, 27h ; '''; void *
0x18001557c  mov     rcx, [rsp+2C8h]; this
0x180015584  lea     r8, aCW1SSrcClientL_14; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x18001558b  mov     r9d, ebp; char *
0x18001558e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015593  mov     rcx, [rsp+2C8h]; this
0x18001559b  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x1800155a2  mov     r9d, ebp; char *
0x1800155a5  mov     edx, 285h; void *
0x1800155aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800155af  jmp     short loc_180015607
0x1800155b1  mov     [r14+8], rbx
0x1800155b5  mov     [r14+10h], r12d
0x1800155b9  mov     rcx, [r13+40h]
0x1800155bd  mov     rdi, r12
0x1800155c0  mov     rdx, [rcx+10h]
0x1800155c4  mov     [rcx+20h], rdx
0x1800155c8  inc     dword ptr [rcx+18h]
0x1800155cb  mov     [rsi], rdx
0x1800155ce  test    rdx, rdx
0x1800155d1  jnz     short loc_18001564F
0x1800155d3  mov     rax, [rcx+8]
0x1800155d7  test    rax, rax
0x1800155da  jz      short loc_1800155DF
0x1800155dc  mov     [rax], rsi
0x1800155df  mov     rax, [rcx+8]
0x1800155e3  mov     [rsi+8], rax
0x1800155e7  mov     [rcx+8], rsi
0x1800155eb  cmp     [rcx+10h], r12
0x1800155ef  jnz     short loc_1800155F5
0x1800155f1  mov     [rcx+10h], rsi
0x1800155f5  mov     rax, [rsp+2C8h+var_270]
0x1800155fa  mov     ebp, r12d
0x1800155fd  mov     [rcx+20h], rsi
0x180015601  mov     [rax], r14
0x180015604  mov     r14, r12
0x180015607  mov     rcx, r14; lpMem
0x18001560a  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18001560f  test    rdi, rdi
0x180015612  jz      short loc_180015629
0x180015614  mov     rcx, rdi; this
0x180015617  call    ??1COutputMemoryFile@@QEAA@XZ; COutputMemoryFile::~COutputMemoryFile(void)
0x18001561c  mov     edx, 120h; struct std::nothrow_t *
0x180015621  mov     rcx, rdi; void *
0x180015624  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015629  mov     eax, ebp
0x18001562b  mov     rcx, [rsp+2C8h+var_58]
0x180015633  xor     rcx, rsp; StackCookie
0x180015636  call    __security_check_cookie
0x18001563b  add     rsp, 288h
0x180015642  pop     r15
0x180015644  pop     r14
0x180015646  pop     r13
0x180015648  pop     r12
0x18001564a  pop     rdi
0x18001564b  pop     rsi
0x18001564c  pop     rbp
0x18001564d  pop     rbx
0x18001564e  retn
0x18001564f  mov     rax, [rdx+8]
0x180015653  mov     [rsi+8], rax
0x180015657  mov     [rdx+8], rsi
0x18001565b  mov     rax, [rsi+8]
0x18001565f  test    rax, rax
0x180015662  jz      short loc_1800155F1
0x180015664  mov     [rax], rsi
0x180015667  jmp     short loc_1800155F5
```
