# CSqlSortManager::BackTrackPattern(PATTBLK *,PATTBLK *,int,ulong,__int64 *,uchar *,__int64 *,ulong &)

- ea: `0x1004a4ae0`
- end: `0x1004a4ca8`
- name: `?BackTrackPattern@CSqlSortManager@@MEAAXPEAUPATTBLK@@0HKPEA_JPEAE1AEAK@Z`
- size: `456`
- prototype: `void __fastcall(CSqlSortManager *__hidden this, struct PATTBLK *, struct PATTBLK *, int, unsigned int, void *, unsigned __int8 *, __int64 *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x100401cc0`
- `0x1004a4ae0`

## import_xrefs

- `sqldk!SystemThread_TlsIndex` at `0x1004a4b06`
- `sqldk!SystemThread_TlsOffset` at `0x1004a4b15`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004a4b30`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004a4b30`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1004a4bc8`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1004a4bee`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1004a4c25`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1004a4c47`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1004a4bc8`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1004a4bee`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1004a4c25`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1004a4c47`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1004a4bd4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1004a4bfa`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1004a4c31`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1004a4c53`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1004a4bd4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1004a4bfa`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1004a4c31`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1004a4c53`

## pseudocode

```c
void __fastcall CSqlSortManager::BackTrackPattern(
        CSqlSortManager *this,
        void **a2,
        struct PATTBLK *a3,
        int a4,
        unsigned int a5,
        char *a6,
        unsigned __int8 *a7,
        __int64 *a8,
        unsigned int *a9)
{
  struct PATTBLK *v9; // rsi
  __int64 v11; // rbp
  __int64 v12; // rdi
  __int64 v13; // rax
  size_t v14; // r8
  char *v15; // rdx
  int v16; // eax
  unsigned __int8 *v17; // rdx
  void *v18; // rax

  v9 = a3;
  v11 = a4;
  v12 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v13 = *(_QWORD *)(v12 + 256);
  if ( !v13 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v13 = *(_QWORD *)(v12 + 256);
  }
  if ( (*(_DWORD *)(v13 + 800) & 0x100000) == 0 )
  {
    LOBYTE(a3) = -15;
    (*(void (__fastcall **)(struct ISqlTypeSystemExtender_IExecControl *, unsigned int *, struct PATTBLK *))(*(_QWORD *)x_pIExecControlExtender + 24LL))(
      x_pIExecControlExtender,
      a9,
      a3);
  }
  memmove(a2[13], (char *)a2[13] + 4 * v11, 4LL * (*((_DWORD *)a2 + 34) - (int)v11));
  memmove(a2[14], (char *)a2[14] + 4 * v11, 4LL * (*((_DWORD *)a2 + 34) - (int)v11));
  if ( a8 )
  {
    v14 = 8LL * (*((_DWORD *)a2 + 34) - (int)v11);
    v15 = &a6[8 * v11];
    if ( v14 )
    {
      if ( a6 && v15 )
      {
        if ( 8 * (unsigned __int64)a5 >= v14 )
        {
          _mm_lfence();
          memmove(a6, v15, v14);
        }
        else
        {
          *_errno() = 34;
          _invalid_parameter_noinfo();
        }
      }
      else
      {
        *_errno() = 22;
        _invalid_parameter_noinfo();
      }
    }
  }
  v16 = *((_DWORD *)a2 + 34) - v11;
  v17 = &a7[v11];
  if ( v16 )
  {
    if ( a7 && v17 )
    {
      if ( a5 >= (unsigned __int64)v16 )
      {
        _mm_lfence();
        memmove(a7, v17, v16);
      }
      else
      {
        *_errno() = 34;
        _invalid_parameter_noinfo();
      }
    }
    else
    {
      *_errno() = 22;
      _invalid_parameter_noinfo();
    }
  }
  *((_DWORD *)a2 + 33) -= v11;
  *((_DWORD *)a2 + 34) -= v11;
  *((_QWORD *)v9 + 19) -= 4 * v11;
  v18 = (void *)*((_QWORD *)v9 + 19);
  if ( v18 < a2[13] )
    v18 = a2[13];
  *((_QWORD *)v9 + 19) = v18;
}

```

## disassembly

```asm
0x1004a4ae0  mov     [rsp+arg_0], rbx
0x1004a4ae5  mov     [rsp+arg_8], rbp
0x1004a4aea  mov     [rsp+arg_10], rsi
0x1004a4aef  mov     [rsp+arg_18], rdi
0x1004a4af4  push    r15
0x1004a4af6  sub     rsp, 20h
0x1004a4afa  mov     r10, gs:58h
0x1004a4b03  mov     rsi, r8
0x1004a4b06  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004a4b0d  mov     rbx, rdx
0x1004a4b10  movsxd  rbp, r9d
0x1004a4b13  mov     ecx, [rax]
0x1004a4b15  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004a4b1c  mov     edi, [rax]
0x1004a4b1e  add     rdi, [r10+rcx*8]
0x1004a4b22  mov     rax, [rdi+100h]
0x1004a4b29  test    rax, rax
0x1004a4b2c  jnz     short loc_1004A4B3D
0x1004a4b2e  xor     ecx, ecx
0x1004a4b30  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004a4b36  mov     rax, [rdi+100h]
0x1004a4b3d  test    dword ptr [rax+320h], 100000h
0x1004a4b47  jnz     short loc_1004A4B5E
0x1004a4b49  mov     rcx, cs:?x_pIExecControlExtender@@3PEAUISqlTypeSystemExtender_IExecControl@@EA; ISqlTypeSystemExtender_IExecControl * x_pIExecControlExtender
0x1004a4b50  mov     r8b, 0F1h
0x1004a4b53  mov     rdx, [rsp+28h+arg_40]
0x1004a4b58  mov     rax, [rcx]
0x1004a4b5b  call    qword ptr [rax+18h]
0x1004a4b5e  mov     eax, [rbx+88h]
0x1004a4b64  lea     r15, ds:0[rbp*4]
0x1004a4b6c  mov     rcx, [rbx+68h]; void *
0x1004a4b70  sub     eax, ebp
0x1004a4b72  movsxd  r8, eax
0x1004a4b75  shl     r8, 2; Size
0x1004a4b79  lea     rdx, [r15+rcx]; Src
0x1004a4b7d  call    memmove
0x1004a4b82  mov     eax, [rbx+88h]
0x1004a4b88  mov     rcx, [rbx+70h]; void *
0x1004a4b8c  sub     eax, ebp
0x1004a4b8e  movsxd  r8, eax
0x1004a4b91  shl     r8, 2; Size
0x1004a4b95  lea     rdx, [r15+rcx]; Src
0x1004a4b99  call    memmove
0x1004a4b9e  cmp     [rsp+28h+arg_38], 0
0x1004a4ba4  jz      short loc_1004A4C0A
0x1004a4ba6  mov     eax, [rbx+88h]
0x1004a4bac  mov     rcx, [rsp+28h+arg_28]; void *
0x1004a4bb1  sub     eax, ebp
0x1004a4bb3  movsxd  r8, eax
0x1004a4bb6  shl     r8, 3; Size
0x1004a4bba  lea     rdx, [rcx+rbp*8]; Src
0x1004a4bbe  test    r8, r8
0x1004a4bc1  jz      short loc_1004A4C0A
0x1004a4bc3  test    rcx, rcx
0x1004a4bc6  jnz     short loc_1004A4BDC
0x1004a4bc8  call    cs:__imp__errno
0x1004a4bce  mov     dword ptr [rax], 16h
0x1004a4bd4  call    cs:__imp__invalid_parameter_noinfo
0x1004a4bda  jmp     short loc_1004A4C0A
0x1004a4bdc  test    rdx, rdx
0x1004a4bdf  jz      short loc_1004A4BC8
0x1004a4be1  mov     eax, [rsp+28h+arg_20]
0x1004a4be5  shl     rax, 3
0x1004a4be9  cmp     rax, r8
0x1004a4bec  jnb     short loc_1004A4C02
0x1004a4bee  call    cs:__imp__errno
0x1004a4bf4  mov     dword ptr [rax], 22h ; '"'
0x1004a4bfa  call    cs:__imp__invalid_parameter_noinfo
0x1004a4c00  jmp     short loc_1004A4C0A
0x1004a4c02  lfence
0x1004a4c05  call    memmove
0x1004a4c0a  mov     rcx, [rsp+28h+arg_30]; void *
0x1004a4c0f  mov     eax, [rbx+88h]
0x1004a4c15  sub     eax, ebp
0x1004a4c17  movsxd  r8, eax; Size
0x1004a4c1a  lea     rdx, [rcx+rbp]; Src
0x1004a4c1e  jz      short loc_1004A4C63
0x1004a4c20  test    rcx, rcx
0x1004a4c23  jnz     short loc_1004A4C39
0x1004a4c25  call    cs:__imp__errno
0x1004a4c2b  mov     dword ptr [rax], 16h
0x1004a4c31  call    cs:__imp__invalid_parameter_noinfo
0x1004a4c37  jmp     short loc_1004A4C63
0x1004a4c39  test    rdx, rdx
0x1004a4c3c  jz      short loc_1004A4C25
0x1004a4c3e  mov     eax, [rsp+28h+arg_20]
0x1004a4c42  cmp     rax, r8
0x1004a4c45  jnb     short loc_1004A4C5B
0x1004a4c47  call    cs:__imp__errno
0x1004a4c4d  mov     dword ptr [rax], 22h ; '"'
0x1004a4c53  call    cs:__imp__invalid_parameter_noinfo
0x1004a4c59  jmp     short loc_1004A4C63
0x1004a4c5b  lfence
0x1004a4c5e  call    memmove
0x1004a4c63  sub     [rbx+84h], ebp
0x1004a4c69  sub     [rbx+88h], ebp
0x1004a4c6f  sub     [rsi+98h], r15
0x1004a4c76  mov     rax, [rsi+98h]
0x1004a4c7d  cmp     rax, [rbx+68h]
0x1004a4c81  mov     rbp, [rsp+28h+arg_8]
0x1004a4c86  cmovb   rax, [rbx+68h]
0x1004a4c8b  mov     rbx, [rsp+28h+arg_0]
0x1004a4c90  mov     rdi, [rsp+28h+arg_18]
0x1004a4c95  mov     [rsi+98h], rax
0x1004a4c9c  mov     rsi, [rsp+28h+arg_10]
0x1004a4ca1  add     rsp, 20h
0x1004a4ca5  pop     r15
0x1004a4ca7  retn
```
