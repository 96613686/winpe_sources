# CabReader::OpenCab(ushort const *,CAB_OPTIONS)

- ea: `0x180068804`
- end: `0x18006896f`
- name: `?OpenCab@CabReader@@QEAAJPEBGW4CAB_OPTIONS@@@Z`
- size: `363`
- prototype: `int __high(const unsigned __int16 *, enum CAB_OPTIONS)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180062f3c`

## callees

- `0x1800358c0`
- `0x180068280`
- `0x1800682e0`
- `0x180068804`
- `0x180068e68`
- `0x180069074`

## import_xrefs

- `Cabinet!__imp_FDICreate` at `0x18006888e`
- `Cabinet!__imp_FDICreate` at `0x18006888e`
- `Cabinet!__imp_FDIIsCabinet` at `0x180068900`
- `Cabinet!__imp_FDIIsCabinet` at `0x180068900`
- `Cabinet!__imp_FDIDestroy` at `0x18006893d`
- `Cabinet!__imp_FDIDestroy` at `0x18006893d`

## pseudocode

```c
__int64 __fastcall CabReader::OpenCab(__int64 a1, const unsigned __int16 *a2, int a3)
{
  int v6; // ebx
  HFDI v7; // rax
  INT_PTR v8; // rsi
  HFDI v9; // rcx
  __int64 v10; // r8
  FDICABINETINFO pfdici; // [rsp+50h] [rbp-158h] BYREF
  CHAR pszFile[272]; // [rsp+70h] [rbp-138h] BYREF

  if ( !a2 )
    return (unsigned int)-2147467261;
  v7 = FDICreate(
         CabReader::FdiMemAlloc,
         (PFNFREE)CabWriter::FciMemFree,
         (PFNOPEN)CabReader::FdiFileOpen,
         CabReader::FdiFileRead,
         (PFNWRITE)CabReader::FdiFileWrite,
         (PFNCLOSE)CabReader::FdiFileClose,
         CabReader::FdiFileSeek,
         -1,
         (PERF)(a1 + 8));
  *(_QWORD *)a1 = v7;
  if ( !v7 )
    return (unsigned int)-2147467259;
  v6 = UnicodeToAnsi(0xFDE9u, a2, pszFile, 0x104u);
  if ( v6 < 0 )
  {
LABEL_12:
    FDIDestroy(*(HFDI *)a1);
    *(_QWORD *)a1 = 0;
    return (unsigned int)v6;
  }
  v8 = CabReader::FdiFileOpen(pszFile, 32800, 0);
  if ( v8 == -1 )
  {
    v6 = -2147467259;
    goto LABEL_12;
  }
  v9 = *(HFDI *)a1;
  memset(&pfdici, 0, sizeof(pfdici));
  if ( FDIIsCabinet(v9, v8, &pfdici) )
  {
    v6 = 0;
    *(_DWORD *)(a1 + 2148) = a3;
    SplitFileNameA(pszFile, (char *)(a1 + 20), v10, (char *)(a1 + 280));
  }
  else
  {
    v6 = -2147467259;
  }
  CabReader::FdiFileClose(v8);
  if ( v6 < 0 )
    goto LABEL_12;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180068804  mov     [rsp+arg_10], rbx
0x180068809  push    rbp
0x18006880a  push    rsi
0x18006880b  push    rdi
0x18006880c  sub     rsp, 190h
0x180068813  mov     rax, cs:__security_cookie
0x18006881a  xor     rax, rsp
0x18006881d  mov     [rsp+1A8h+var_28], rax
0x180068825  mov     ebp, r8d
0x180068828  mov     rbx, rdx
0x18006882b  mov     rdi, rcx
0x18006882e  test    rdx, rdx
0x180068831  jnz     short loc_18006883D
0x180068833  mov     ebx, 80004003h
0x180068838  jmp     loc_18006894A
0x18006883d  lea     rax, [rcx+8]
0x180068841  mov     [rsp+1A8h+perf], rax; perf
0x180068846  lea     r9, ?FdiFileRead@CabReader@@CAI_JPEAXI@Z; pfnread
0x18006884d  mov     [rsp+1A8h+cpuType], 0FFFFFFFFh; cpuType
0x180068855  lea     rax, ?FdiFileSeek@CabReader@@CAJ_JJH@Z; CabReader::FdiFileSeek(__int64,long,int)
0x18006885c  mov     [rsp+1A8h+pfnseek], rax; pfnseek
0x180068861  lea     r8, ?FdiFileOpen@CabReader@@CA_JPEADHH@Z; pfnopen
0x180068868  lea     rax, ?FdiFileClose@CabReader@@CAH_J@Z; CabReader::FdiFileClose(__int64)
0x18006886f  mov     [rsp+1A8h+pfnclose], rax; pfnclose
0x180068874  lea     rdx, ?FciMemFree@CabWriter@@CAXPEAX@Z; pfnfree
0x18006887b  lea     rax, ?FdiFileWrite@CabReader@@CAI_JPEAXI@Z; CabReader::FdiFileWrite(__int64,void *,uint)
0x180068882  lea     rcx, ?FdiMemAlloc@CabReader@@CAPEAXK@Z; pfnalloc
0x180068889  mov     [rsp+1A8h+pfnwrite], rax; unsigned __int64
0x18006888e  call    cs:__imp_FDICreate
0x180068894  mov     [rdi], rax
0x180068897  test    rax, rax
0x18006889a  jnz     short loc_1800688A6
0x18006889c  mov     ebx, 80004005h
0x1800688a1  jmp     loc_18006894A
0x1800688a6  mov     r9d, 104h; unsigned __int64
0x1800688ac  lea     r8, [rsp+1A8h+pszFile]; char *
0x1800688b1  mov     rdx, rbx; unsigned __int16 *
0x1800688b4  mov     ecx, 0FDE9h; unsigned int
0x1800688b9  call    ?UnicodeToAnsi@@YAJIPEBGPEAD_K@Z; UnicodeToAnsi(uint,ushort const *,char *,unsigned __int64)
0x1800688be  mov     ebx, eax
0x1800688c0  test    eax, eax
0x1800688c2  js      short loc_18006893A
0x1800688c4  xor     r8d, r8d; pmode
0x1800688c7  lea     rcx, [rsp+1A8h+pszFile]; pszFile
0x1800688cc  mov     edx, 8020h; oflag
0x1800688d1  call    ?FdiFileOpen@CabReader@@CA_JPEADHH@Z; CabReader::FdiFileOpen(char *,int,int)
0x1800688d6  mov     rsi, rax
0x1800688d9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800688dd  jnz     short loc_1800688E6
0x1800688df  mov     ebx, 80004005h
0x1800688e4  jmp     short loc_18006893A
0x1800688e6  mov     rcx, [rdi]; hfdi
0x1800688e9  lea     r8, [rsp+1A8h+pfdici]; pfdici
0x1800688ee  xorps   xmm0, xmm0
0x1800688f1  xor     eax, eax
0x1800688f3  mov     rdx, rsi; hf
0x1800688f6  mov     qword ptr [rsp+1A8h+pfdici.hasprev], rax
0x1800688fb  movups  xmmword ptr [rsp+1A8h+pfdici.cbCabinet], xmm0
0x180068900  call    cs:__imp_FDIIsCabinet
0x180068906  test    eax, eax
0x180068908  jnz     short loc_180068911
0x18006890a  mov     ebx, 80004005h
0x18006890f  jmp     short loc_18006892E
0x180068911  xor     ebx, ebx
0x180068913  mov     [rdi+864h], ebp
0x180068919  lea     r9, [rdi+118h]; char *
0x180068920  lea     rdx, [rdi+14h]; char *
0x180068924  lea     rcx, [rsp+1A8h+pszFile]; char *
0x180068929  call    ?SplitFileNameA@@YAJPEBDPEAD_K12@Z; SplitFileNameA(char const *,char *,unsigned __int64,char *,unsigned __int64)
0x18006892e  mov     rcx, rsi; hf
0x180068931  call    ?FdiFileClose@CabReader@@CAH_J@Z; CabReader::FdiFileClose(__int64)
0x180068936  test    ebx, ebx
0x180068938  jns     short loc_18006894A
0x18006893a  mov     rcx, [rdi]; hfdi
0x18006893d  call    cs:__imp_FDIDestroy
0x180068943  mov     qword ptr [rdi], 0
0x18006894a  mov     eax, ebx
0x18006894c  mov     rcx, [rsp+1A8h+var_28]
0x180068954  xor     rcx, rsp; StackCookie
0x180068957  call    __security_check_cookie
0x18006895c  mov     rbx, [rsp+1A8h+arg_10]
0x180068964  add     rsp, 190h
0x18006896b  pop     rdi
0x18006896c  pop     rsi
0x18006896d  pop     rbp
0x18006896e  retn
```
