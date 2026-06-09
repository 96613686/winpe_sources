# ExpandDiamondFile(char *,ushort const *,int,tagLZI *)

- ea: `0x180002198`
- end: `0x180002392`
- name: `?ExpandDiamondFile@@YAHPEADPEBGHPEAUtagLZI@@@Z`
- size: `506`
- prototype: `__int64 __fastcall(char *, const unsigned __int16 *, int, struct tagLZI *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180002b00`

## callees

- `0x180002198`
- `0x1800026f0`
- `0x180002818`
- `0x1800031b0`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x180002352`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x180002352`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180002264`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180002264`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002206`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000221b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002232`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800022a9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800022ba`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002306`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002337`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002206`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000221b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002232`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800022a9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800022ba`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002306`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002337`
- `KERNEL32!_lclose` at `0x18000235c`
- `KERNEL32!_lclose` at `0x18000235c`

## pseudocode

```c
__int64 __fastcall ExpandDiamondFile(char *a1, const unsigned __int16 *a2, __int64 a3, struct tagLZI *a4)
{
  int v6; // ebx
  void *v7; // rax
  unsigned int v8; // edi
  void *v9; // rsi
  DWORD FileSize; // eax
  int (*v12)(void *, char *, char *, int, __int64 (*)(enum FDINOTIFICATIONTYPE, struct FDINOTIFICATION *), int (*)(struct FDIDECRYPT *), void *); // rdi
  __int64 v13; // rcx
  _DWORD *Value; // rax
  __int128 v15; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v16; // [rsp+50h] [rbp-B0h]
  struct tagLZI *v17; // [rsp+60h] [rbp-A0h]
  CHAR FileName[272]; // [rsp+70h] [rbp-90h] BYREF

  v15 = 0;
  v17 = 0;
  v16 = 0;
  StringCchPrintfA(FileName, 0x104u, "%ls", a2);
  if ( itlsDiamondContext != -1 && TlsGetValue(itlsDiamondContext) && *((_QWORD *)TlsGetValue(itlsDiamondContext) + 1) )
  {
    v6 = 1;
    *(_DWORD *)TlsGetValue(itlsDiamondContext) = 1;
    v7 = (void *)SpdFdiOpen(a1, 0);
    v8 = -1;
    v9 = v7;
    if ( v7 == (void *)-1LL )
      return v8;
    FileSize = GetFileSize(v7, 0);
    *((_DWORD *)a4 + 16) = FileSize;
    if ( FileSize == -1 )
    {
LABEL_24:
      _lclose((HFILE)v9);
      return v8;
    }
    v12 = pFDICopy;
    *(_QWORD *)&v16 = FileName;
    *(_QWORD *)&v15 = v9;
    *((_QWORD *)&v15 + 1) = a1;
    DWORD2(v16) = 0;
    v17 = a4;
    if ( itlsDiamondContext == -1 || !TlsGetValue(itlsDiamondContext) )
      v13 = 0;
    else
      v13 = *((_QWORD *)TlsGetValue(itlsDiamondContext) + 1);
    if ( ((unsigned int (__fastcall *)(__int64, char *, __int64 *, _QWORD, __int64 (__fastcall *)(enum FDINOTIFICATIONTYPE, struct FDINOTIFICATION *), _QWORD, __int128 *))v12)(
           v13,
           a1,
           &qword_1800055E8,
           0,
           DiamondNotifyFunction,
           0,
           &v15) )
    {
LABEL_23:
      v8 = v6;
      goto LABEL_24;
    }
    Value = TlsGetValue(itlsDiamondContext);
    if ( Value[4] != 3 && Value[4] != 4 )
    {
      if ( Value[4] == 5 )
      {
        v6 = -5;
LABEL_22:
        DeleteFileA(FileName);
        goto LABEL_23;
      }
      if ( Value[4] != 6 )
      {
        if ( Value[4] == 8 || Value[4] == 11 )
          v6 = *(_DWORD *)TlsGetValue(itlsDiamondContext);
        else
          v6 = -7;
        goto LABEL_22;
      }
    }
    v6 = -3;
    goto LABEL_22;
  }
  return 4294967289LL;
}

```

## disassembly

```asm
0x180002198  mov     [rsp-8+arg_10], rbx
0x18000219d  push    rbp
0x18000219e  push    rsi
0x18000219f  push    rdi
0x1800021a0  push    r14
0x1800021a2  push    r15
0x1800021a4  lea     rbp, [rsp-90h]
0x1800021ac  sub     rsp, 190h
0x1800021b3  mov     rax, cs:__security_cookie
0x1800021ba  xor     rax, rsp
0x1800021bd  mov     [rbp+0B0h+var_30], rax
0x1800021c4  xorps   xmm0, xmm0
0x1800021c7  lea     r8, aLs; "%ls"
0x1800021ce  mov     r14, r9
0x1800021d1  mov     r15, rcx
0x1800021d4  mov     r9, rdx
0x1800021d7  lea     rcx, [rsp+1B0h+FileName]; char *
0x1800021dc  xor     eax, eax
0x1800021de  mov     edx, 104h; unsigned __int64
0x1800021e3  movups  [rsp+1B0h+var_170], xmm0
0x1800021e8  mov     [rsp+1B0h+var_150], rax
0x1800021ed  movups  [rsp+1B0h+var_160], xmm0
0x1800021f2  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800021f7  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x1800021fd  cmp     ecx, 0FFFFFFFFh
0x180002200  jz      loc_180002367
0x180002206  call    cs:__imp_TlsGetValue
0x18000220c  test    rax, rax
0x18000220f  jz      loc_180002367
0x180002215  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x18000221b  call    cs:__imp_TlsGetValue
0x180002221  cmp     qword ptr [rax+8], 0
0x180002226  jz      loc_180002367
0x18000222c  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x180002232  call    cs:__imp_TlsGetValue
0x180002238  mov     ebx, 1
0x18000223d  xor     r8d, r8d; int
0x180002240  xor     edx, edx; int
0x180002242  mov     rcx, r15; char *
0x180002245  mov     [rax], ebx
0x180002247  call    ?SpdFdiOpen@@YA_JPEADHH@Z; SpdFdiOpen(char *,int,int)
0x18000224c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180002250  mov     rsi, rax
0x180002253  cmp     rax, rdi
0x180002256  jnz     short loc_18000225F
0x180002258  mov     eax, edi
0x18000225a  jmp     loc_18000236C
0x18000225f  xor     edx, edx; lpFileSizeHigh
0x180002261  mov     rcx, rsi; hFile
0x180002264  call    cs:__imp_GetFileSize
0x18000226a  mov     [r14+40h], eax
0x18000226e  cmp     eax, edi
0x180002270  jz      loc_18000235A
0x180002276  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x18000227c  lea     rax, [rsp+1B0h+FileName]
0x180002281  mov     rdi, cs:?pFDICopy@@3P6AHPEAXPEAD1HP6A_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@ZP6AHPEAUFDIDECRYPT@@@Z0@ZEA; int (*pFDICopy)(void *,char *,char *,int,__int64 (*)(FDINOTIFICATIONTYPE,FDINOTIFICATION *),int (*)(FDIDECRYPT *),void *)
0x180002288  mov     qword ptr [rsp+1B0h+var_160], rax
0x18000228d  mov     qword ptr [rsp+1B0h+var_170], rsi
0x180002292  mov     qword ptr [rsp+1B0h+var_170+8], r15
0x180002297  mov     dword ptr [rsp+1B0h+var_160+8], 0
0x18000229f  mov     [rsp+1B0h+var_150], r14
0x1800022a4  cmp     ecx, 0FFFFFFFFh
0x1800022a7  jz      short loc_1800022C6
0x1800022a9  call    cs:__imp_TlsGetValue
0x1800022af  test    rax, rax
0x1800022b2  jz      short loc_1800022C6
0x1800022b4  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x1800022ba  call    cs:__imp_TlsGetValue
0x1800022c0  mov     rcx, [rax+8]
0x1800022c4  jmp     short loc_1800022C8
0x1800022c6  xor     ecx, ecx
0x1800022c8  lea     rax, [rsp+1B0h+var_170]
0x1800022cd  xor     r9d, r9d
0x1800022d0  mov     [rsp+1B0h+var_180], rax
0x1800022d5  lea     r8, qword_1800055E8
0x1800022dc  lea     rax, ?DiamondNotifyFunction@@YA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z; DiamondNotifyFunction(FDINOTIFICATIONTYPE,FDINOTIFICATION *)
0x1800022e3  mov     [rsp+1B0h+var_188], 0
0x1800022ec  mov     [rsp+1B0h+var_190], rax
0x1800022f1  mov     rdx, r15
0x1800022f4  mov     rax, rdi
0x1800022f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022fc  test    eax, eax
0x1800022fe  jnz     short loc_180002358
0x180002300  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x180002306  call    cs:__imp_TlsGetValue
0x18000230c  mov     edx, [rax+10h]
0x18000230f  sub     edx, 3
0x180002312  jz      short loc_180002348
0x180002314  sub     edx, ebx
0x180002316  jz      short loc_180002348
0x180002318  sub     edx, ebx
0x18000231a  jz      short loc_180002341
0x18000231c  sub     edx, ebx
0x18000231e  jz      short loc_180002348
0x180002320  sub     edx, 2
0x180002323  jz      short loc_180002331
0x180002325  cmp     edx, 3
0x180002328  jz      short loc_180002331
0x18000232a  mov     ebx, 0FFFFFFF9h
0x18000232f  jmp     short loc_18000234D
0x180002331  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x180002337  call    cs:__imp_TlsGetValue
0x18000233d  mov     ebx, [rax]
0x18000233f  jmp     short loc_18000234D
0x180002341  mov     ebx, 0FFFFFFFBh
0x180002346  jmp     short loc_18000234D
0x180002348  mov     ebx, 0FFFFFFFDh
0x18000234d  lea     rcx, [rsp+1B0h+FileName]; lpFileName
0x180002352  call    cs:__imp_DeleteFileA
0x180002358  mov     edi, ebx
0x18000235a  mov     ecx, esi; hFile
0x18000235c  call    cs:__imp__lclose
0x180002362  jmp     loc_180002258
0x180002367  mov     eax, 0FFFFFFF9h
0x18000236c  mov     rcx, [rbp+0B0h+var_30]
0x180002373  xor     rcx, rsp; StackCookie
0x180002376  call    __security_check_cookie
0x18000237b  mov     rbx, [rsp+1B0h+arg_10]
0x180002383  add     rsp, 190h
0x18000238a  pop     r15
0x18000238c  pop     r14
0x18000238e  pop     rdi
0x18000238f  pop     rsi
0x180002390  pop     rbp
0x180002391  retn
```
