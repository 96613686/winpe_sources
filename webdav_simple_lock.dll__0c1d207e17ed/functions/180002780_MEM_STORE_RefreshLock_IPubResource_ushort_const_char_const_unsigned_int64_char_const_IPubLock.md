# MEM_STORE::RefreshLock(IPubResource *,ushort const *,char const *,unsigned __int64,char const *,IPubLock * *)

- ea: `0x180002780`
- end: `0x180002900`
- name: `?RefreshLock@MEM_STORE@@UEAAJPEAVIPubResource@@PEBGPEBD_K2PEAPEAVIPubLock@@@Z`
- size: `384`
- prototype: `__int64 __fastcall(MEM_STORE *this, struct IPubResource *, const unsigned __int16 *, const char *, unsigned __int64, const char *, struct IPubLock **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002364`
- `0x180002780`
- `0x180003c30`
- `0x180004010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000289f`
- `msvcrt!_wcsnicmp` at `0x18000289f`
- `msvcrt!_wcsicmp` at `0x180002859`
- `msvcrt!_wcsicmp` at `0x180002859`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x1800027cb`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x1800027cb`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800028d1`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800028d1`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800027e2`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800027e2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800028dc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800028dc`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800027b7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800027b7`

## pseudocode

```c
__int64 __fastcall MEM_STORE::RefreshLock(
        MEM_STORE *this,
        struct IPubResource *a2,
        const unsigned __int16 *a3,
        const char *a4,
        unsigned __int64 a5,
        const char *a6,
        struct IPubLock **a7)
{
  int v11; // ebx
  CReaderWriterLock3 *v12; // rbp
  struct MEM_LOCK *LockByToken; // rax
  struct IPubLock *v14; // rdi
  __int64 v15; // rax
  int v16; // edx
  int v17; // ecx
  const wchar_t *v18; // r14
  const wchar_t *v19; // rsi
  unsigned __int64 v20; // rcx
  size_t v21; // r8
  _BYTE v23[32]; // [rsp+20h] [rbp-78h] BYREF
  unsigned __int16 *v24; // [rsp+40h] [rbp-58h]

  STRU::STRU((STRU *)v23);
  *a7 = 0;
  v11 = STRU::CopyA((STRU *)v23, a4);
  if ( v11 >= 0 )
  {
    v12 = (MEM_STORE *)((char *)this + 88);
    CReaderWriterLock3::WriteLock((MEM_STORE *)((char *)this + 88));
    LockByToken = MEM_STORE::FindLockByToken(this, v24);
    v14 = LockByToken;
    if ( !LockByToken )
      goto LABEL_3;
    v15 = (*(__int64 (__fastcall **)(struct MEM_LOCK *))(*(_QWORD *)LockByToken + 48LL))(LockByToken) - (_QWORD)a3;
    do
    {
      v16 = *(const unsigned __int16 *)((char *)a3 + v15);
      v17 = *a3 - v16;
      if ( v17 )
        break;
      ++a3;
    }
    while ( v16 );
    if ( v17 )
      goto LABEL_3;
    v18 = (const wchar_t *)(**(__int64 (__fastcall ***)(struct IPubResource *))a2)(a2);
    v19 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IPubLock *))(*(_QWORD *)v14 + 32LL))(v14);
    if ( !_wcsicmp(v18, v19) )
      goto LABEL_16;
    v20 = -1;
    v21 = -1;
    do
      ++v21;
    while ( v19[v21] );
    do
      ++v20;
    while ( v18[v20] );
    if ( v20 <= v21 || v21 && v19[v21 - 1] != 47 || _wcsnicmp(v19, v18, v21) )
    {
LABEL_3:
      v11 = -1917904448;
    }
    else
    {
LABEL_16:
      *((_QWORD *)v14 + 33) = a5;
      (*(void (__fastcall **)(struct IPubLock *))(*(_QWORD *)v14 + 8LL))(v14);
      *a7 = v14;
    }
    CReaderWriterLock3::WriteUnlock(v12);
  }
  STRU::~STRU((STRU *)v23);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180002780  push    rbx
0x180002782  push    rbp
0x180002783  push    rsi
0x180002784  push    rdi
0x180002785  push    r12
0x180002787  push    r14
0x180002789  push    r15
0x18000278b  sub     rsp, 60h
0x18000278f  mov     rax, cs:__security_cookie
0x180002796  xor     rax, rsp
0x180002799  mov     [rsp+98h+var_40], rax
0x18000279e  mov     r15, [rsp+98h+arg_30]
0x1800027a6  mov     rdi, rcx
0x1800027a9  lea     rcx, [rsp+98h+var_78]
0x1800027ae  mov     rbx, r9
0x1800027b1  mov     rsi, r8
0x1800027b4  mov     r14, rdx
0x1800027b7  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800027bd  xor     r12d, r12d
0x1800027c0  lea     rcx, [rsp+98h+var_78]
0x1800027c5  mov     rdx, rbx
0x1800027c8  mov     [r15], r12
0x1800027cb  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x1800027d1  mov     ebx, eax
0x1800027d3  test    eax, eax
0x1800027d5  js      loc_1800028D7
0x1800027db  lea     rbp, [rdi+58h]
0x1800027df  mov     rcx, rbp
0x1800027e2  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800027e8  mov     rdx, [rsp+98h+var_58]; unsigned __int16 *
0x1800027ed  mov     rcx, rdi; this
0x1800027f0  call    ?FindLockByToken@MEM_STORE@@AEAAPEAVMEM_LOCK@@PEBG@Z; MEM_STORE::FindLockByToken(ushort const *)
0x1800027f5  mov     rdi, rax
0x1800027f8  test    rax, rax
0x1800027fb  jnz     short loc_180002807
0x1800027fd  mov     ebx, 8DAF19C0h
0x180002802  jmp     loc_1800028CE
0x180002807  mov     rax, [rax]
0x18000280a  mov     rcx, rdi
0x18000280d  mov     rax, [rax+30h]
0x180002811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002816  sub     rax, rsi
0x180002819  movzx   ecx, word ptr [rsi]
0x18000281c  movzx   edx, word ptr [rsi+rax]
0x180002820  sub     ecx, edx
0x180002822  jnz     short loc_18000282C
0x180002824  add     rsi, 2
0x180002828  test    edx, edx
0x18000282a  jnz     short loc_180002819
0x18000282c  test    ecx, ecx
0x18000282e  jnz     short loc_1800027FD
0x180002830  mov     rax, [r14]
0x180002833  mov     rcx, r14
0x180002836  mov     rax, [rax]
0x180002839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000283e  mov     rcx, [rdi]
0x180002841  mov     r14, rax
0x180002844  mov     rax, [rcx+20h]
0x180002848  mov     rcx, rdi
0x18000284b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002850  mov     rdx, rax; String2
0x180002853  mov     rcx, r14; String1
0x180002856  mov     rsi, rax
0x180002859  call    cs:__imp__wcsicmp
0x18000285f  test    eax, eax
0x180002861  jz      short loc_1800028AD
0x180002863  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180002867  mov     r8, rcx
0x18000286a  inc     r8; MaxCount
0x18000286d  cmp     [rsi+r8*2], r12w
0x180002872  jnz     short loc_18000286A
0x180002874  inc     rcx
0x180002877  cmp     [r14+rcx*2], r12w
0x18000287c  jnz     short loc_180002874
0x18000287e  cmp     rcx, r8
0x180002881  jbe     loc_1800027FD
0x180002887  test    r8, r8
0x18000288a  jz      short loc_180002899
0x18000288c  cmp     word ptr [rsi+r8*2-2], 2Fh ; '/'
0x180002893  jnz     loc_1800027FD
0x180002899  mov     rdx, r14; String2
0x18000289c  mov     rcx, rsi; String1
0x18000289f  call    cs:__imp__wcsnicmp
0x1800028a5  test    eax, eax
0x1800028a7  jnz     loc_1800027FD
0x1800028ad  mov     rax, [rsp+98h+arg_20]
0x1800028b5  mov     rcx, rdi
0x1800028b8  mov     [rdi+108h], rax
0x1800028bf  mov     rax, [rdi]
0x1800028c2  mov     rax, [rax+8]
0x1800028c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028cb  mov     [r15], rdi
0x1800028ce  mov     rcx, rbp
0x1800028d1  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800028d7  lea     rcx, [rsp+98h+var_78]
0x1800028dc  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800028e2  mov     eax, ebx
0x1800028e4  mov     rcx, [rsp+98h+var_40]
0x1800028e9  xor     rcx, rsp; StackCookie
0x1800028ec  call    __security_check_cookie
0x1800028f1  add     rsp, 60h
0x1800028f5  pop     r15
0x1800028f7  pop     r14
0x1800028f9  pop     r12
0x1800028fb  pop     rdi
0x1800028fc  pop     rsi
0x1800028fd  pop     rbp
0x1800028fe  pop     rbx
0x1800028ff  retn
```
