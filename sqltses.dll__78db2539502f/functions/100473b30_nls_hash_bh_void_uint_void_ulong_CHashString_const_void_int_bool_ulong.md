# nls_hash_bh(void *,uint,void *,ulong,CHashString const *,void *,int,bool,ulong)

- ea: `0x100473b30`
- end: `0x100473d4a`
- name: `?nls_hash_bh@@YAHPEAXI0KPEBVCHashString@@0H_NK@Z`
- size: `538`
- prototype: `__int64 __fastcall(void *, unsigned int, void *, unsigned int, const struct CHashString *, void *Src, size_t Size, bool, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x100401170`
- `0x100401cc0`
- `0x1004024b0`
- `0x100473b30`
- `0x1004847a0`

## import_xrefs

- `sqldk!SystemThread_TlsIndex` at `0x100473b8d`
- `sqldk!SystemThread_TlsOffset` at `0x100473b96`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100473bb1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100473bb1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100473c91`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100473c91`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall nls_hash_bh(
        void *a1,
        unsigned int a2,
        void *a3,
        int a4,
        const struct CHashString *a5,
        char *Src,
        size_t Size,
        bool a8,
        unsigned int a9)
{
  char *v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // rax
  struct IMemObj *v15; // r15
  unsigned __int64 v16; // rcx
  __int64 v17; // rax
  void *v18; // rsp
  unsigned int v19; // ebx
  void ***v20; // rcx
  _BYTE v22[8]; // [rsp+50h] [rbp+0h] BYREF
  __int64 v23; // [rsp+58h] [rbp+8h]
  int v24; // [rsp+60h] [rbp+10h] BYREF
  char v25; // [rsp+64h] [rbp+14h]
  __int64 v26; // [rsp+68h] [rbp+18h]
  __int64 v27; // [rsp+80h] [rbp+30h]
  __int64 v28; // [rsp+90h] [rbp+40h]
  __int64 v29; // [rsp+A8h] [rbp+58h]
  char v30; // [rsp+B0h] [rbp+60h]
  wchar_t v31[2048]; // [rsp+C0h] [rbp+70h] BYREF

  v23 = -2;
  v12 = Src;
  v13 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v14 = *(_QWORD *)(v13 + 256);
  if ( !v14 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v14 = *(_QWORD *)(v13 + 256);
  }
  v15 = *(struct IMemObj **)(v14 + 1000);
  if ( ((unsigned __int8)Src & 7) != 0 )
  {
    v16 = (int)Size + 7;
    v17 = v16 + 15;
    if ( v16 + 15 < v16 )
      v17 = 0xFFFFFFFFFFFFFF0LL;
    v18 = alloca(v17 & 0xFFFFFFFFFFFFFFF0uLL);
    memmove(v22, Src, (unsigned int)Size);
    v12 = v22;
  }
  v24 = 1;
  v25 = 1;
  v19 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 1;
  CWCharReaderOnStr::InitReaderOnStr((CWCharReaderOnStr *)&v24, v15, a2, 0, 0, v12, Size, v31, 0x800u);
  if ( v25 )
    goto LABEL_21;
  if ( !v24 )
  {
    if ( (*(unsigned int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v27 + 152LL))(v27, v22) )
      ex_raise(71, 2, 20, 99);
    if ( (v22[0] & 1) != 0 )
    {
LABEL_21:
      v19 = a9;
      goto LABEL_22;
    }
  }
  switch ( *((_BYTE *)a5 + 92) )
  {
    case 0:
      v20 = &x_SqlSortManager_80;
      goto LABEL_20;
    case 1:
      v20 = &x_SqlSortManager_90;
      goto LABEL_20;
    case 2:
      v20 = &x_SqlSortManager_100;
      goto LABEL_20;
    case 3:
      v20 = &x_SqlSortManager_140;
LABEL_20:
      v19 = ((__int64 (__fastcall *)(void ***, void *, _QWORD, int *, bool))(*v20)[12])(
              v20,
              a3,
              a4 | 0x80000400,
              &v24,
              a8);
      break;
  }
LABEL_22:
  if ( !v24 && v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  return v19;
}

```

## disassembly

```asm
0x100473b30  push    rbp
0x100473b32  push    rsi
0x100473b33  push    rdi
0x100473b34  push    r12
0x100473b36  push    r13
0x100473b38  push    r14
0x100473b3a  push    r15
0x100473b3c  mov     eax, 10D0h
0x100473b41  call    _alloca_probe
0x100473b46  sub     rsp, rax
0x100473b49  lea     rbp, [rsp+50h]
0x100473b4e  mov     [rbp+10B0h+var_10A8], 0FFFFFFFFFFFFFFFEh
0x100473b56  mov     [rbp+10B0h+arg_0], rbx
0x100473b5d  mov     rax, cs:__security_cookie
0x100473b64  xor     rax, rbp
0x100473b67  mov     [rbp+10B0h+var_40], rax
0x100473b6e  mov     r14d, r9d
0x100473b71  mov     r13, r8
0x100473b74  mov     r12d, edx
0x100473b77  mov     rdi, [rbp+10B0h+Src]
0x100473b7e  mov     esi, dword ptr [rbp+10B0h+Size]
0x100473b84  mov     rdx, gs:58h
0x100473b8d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100473b94  mov     ecx, [rax]
0x100473b96  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100473b9d  mov     ebx, [rax]
0x100473b9f  add     rbx, [rdx+rcx*8]
0x100473ba3  mov     rax, [rbx+100h]
0x100473baa  test    rax, rax
0x100473bad  jnz     short loc_100473BBE
0x100473baf  xor     ecx, ecx
0x100473bb1  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100473bb7  mov     rax, [rbx+100h]
0x100473bbe  mov     r15, [rax+3E8h]
0x100473bc5  test    dil, 7
0x100473bc9  jz      short loc_100473C0E
0x100473bcb  lea     eax, [rsi+7]
0x100473bce  movsxd  rcx, eax
0x100473bd1  lea     rax, [rcx+0Fh]
0x100473bd5  cmp     rax, rcx
0x100473bd8  ja      short loc_100473BE4
0x100473bda  mov     rax, 0FFFFFFFFFFFFFF0h
0x100473be4  and     rax, 0FFFFFFFFFFFFFFF0h
0x100473be8  call    _alloca_probe
0x100473bed  sub     rsp, rax
0x100473bf0  lea     rbx, [rsp+1100h+var_10B0]
0x100473bf5  add     rbx, 7
0x100473bf9  and     rbx, 0FFFFFFFFFFFFFFF8h
0x100473bfd  mov     r8, rsi; Size
0x100473c00  mov     rdx, rdi; Src
0x100473c03  mov     rcx, rbx; void *
0x100473c06  call    memmove
0x100473c0b  mov     rdi, rbx
0x100473c0e  mov     [rbp+10B0h+var_10A0], 1
0x100473c15  mov     [rbp+10B0h+var_109C], 1
0x100473c19  xor     ebx, ebx
0x100473c1b  mov     [rbp+10B0h+var_1098], rbx
0x100473c1f  mov     [rbp+10B0h+var_1080], rbx
0x100473c23  mov     [rbp+10B0h+var_1070], rbx
0x100473c27  mov     [rbp+10B0h+var_1058], rbx
0x100473c2b  mov     [rbp+10B0h+var_1050], 1
0x100473c2f  mov     [rsp+1100h+var_10C0], 800h; unsigned int
0x100473c37  lea     rax, [rbp+10B0h+var_1040]
0x100473c3b  mov     [rsp+1100h+var_10C8], rax; wchar_t *
0x100473c40  mov     [rsp+1100h+var_10D0], esi; unsigned int
0x100473c44  mov     [rsp+1100h+var_10D8], rdi; char *
0x100473c49  mov     [rsp+1100h+var_10E0], ebx; int
0x100473c4d  xor     r9d, r9d; int
0x100473c50  mov     r8d, r12d; unsigned int
0x100473c53  mov     rdx, r15; struct IMemObj *
0x100473c56  lea     rcx, [rbp+10B0h+var_10A0]; this
0x100473c5a  call    ?InitReaderOnStr@CWCharReaderOnStr@@QEAAXPEAVIMemObj@@IHHPEBXKPEA_WK@Z; CWCharReaderOnStr::InitReaderOnStr(IMemObj *,uint,int,int,void const *,ulong,wchar_t *,ulong)
0x100473c5f  nop
0x100473c60  cmp     [rbp+10B0h+var_109C], bl
0x100473c63  jnz     loc_100473D04
0x100473c69  cmp     [rbp+10B0h+var_10A0], ebx
0x100473c6c  jnz     short loc_100473C9D
0x100473c6e  mov     rcx, [rbp+10B0h+var_1080]
0x100473c72  mov     rax, [rcx]
0x100473c75  lea     rdx, [rbp+10B0h+var_10B0]
0x100473c79  call    qword ptr [rax+98h]
0x100473c7f  test    eax, eax
0x100473c81  jz      short loc_100473C97
0x100473c83  lea     edx, [rbx+2]
0x100473c86  lea     ecx, [rbx+47h]
0x100473c89  lea     r9d, [rbx+63h]
0x100473c8d  lea     r8d, [rbx+14h]
0x100473c91  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100473c97  test    [rbp+10B0h+var_10B0], 1
0x100473c9b  jnz     short loc_100473D04
0x100473c9d  mov     rax, [rbp+10B0h+arg_20]
0x100473ca4  movzx   ecx, byte ptr [rax+5Ch]
0x100473ca8  test    ecx, ecx
0x100473caa  jz      short loc_100473CD6
0x100473cac  sub     ecx, 1
0x100473caf  jz      short loc_100473CCD
0x100473cb1  sub     ecx, 1
0x100473cb4  jz      short loc_100473CC4
0x100473cb6  cmp     ecx, 1
0x100473cb9  jnz     short loc_100473D0A
0x100473cbb  lea     rcx, ?x_SqlSortManager_140@@3VCSqlSortManager_140@@A; CSqlSortManager_140 x_SqlSortManager_140
0x100473cc2  jmp     short loc_100473CDD
0x100473cc4  lea     rcx, ?x_SqlSortManager_100@@3VCSqlSortManager_100@@A; CSqlSortManager_100 x_SqlSortManager_100
0x100473ccb  jmp     short loc_100473CDD
0x100473ccd  lea     rcx, ?x_SqlSortManager_90@@3VCSqlSortManager_90@@A; CSqlSortManager_90 x_SqlSortManager_90
0x100473cd4  jmp     short loc_100473CDD
0x100473cd6  lea     rcx, ?x_SqlSortManager_80@@3VCSqlSortManager_80@@A; CSqlSortManager_80 x_SqlSortManager_80
0x100473cdd  mov     r10, [rcx]
0x100473ce0  movzx   eax, [rbp+10B0h+arg_38]
0x100473ce7  or      r14d, 80000400h
0x100473cee  mov     [rsp+1100h+var_10E0], eax
0x100473cf2  lea     r9, [rbp+10B0h+var_10A0]
0x100473cf6  mov     r8d, r14d
0x100473cf9  mov     rdx, r13
0x100473cfc  call    qword ptr [r10+60h]
0x100473d00  mov     ebx, eax
0x100473d02  jmp     short loc_100473D0A
0x100473d04  mov     ebx, [rbp+10B0h+arg_40]
0x100473d0a  cmp     [rbp+10B0h+var_10A0], 0
0x100473d0e  jnz     short loc_100473D1F
0x100473d10  mov     rcx, [rbp+10B0h+var_1080]
0x100473d14  test    rcx, rcx
0x100473d17  jz      short loc_100473D1F
0x100473d19  mov     rax, [rcx]
0x100473d1c  call    qword ptr [rax+10h]
0x100473d1f  mov     eax, ebx
0x100473d21  mov     rcx, [rbp+10B0h+var_40]
0x100473d28  xor     rcx, rbp; StackCookie
0x100473d2b  call    __security_check_cookie
0x100473d30  mov     rbx, [rbp+10B0h+arg_0]
0x100473d37  lea     rsp, [rbp+1080h]
0x100473d3e  pop     r15
0x100473d40  pop     r14
0x100473d42  pop     r13
0x100473d44  pop     r12
0x100473d46  pop     rdi
0x100473d47  pop     rsi
0x100473d48  pop     rbp
0x100473d49  retn
```
