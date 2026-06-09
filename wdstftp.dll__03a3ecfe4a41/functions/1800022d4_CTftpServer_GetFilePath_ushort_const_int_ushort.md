# CTftpServer::GetFilePath(ushort const *,int,ushort * *)

- ea: `0x1800022d4`
- end: `0x18000253d`
- name: `?GetFilePath@CTftpServer@@QEAAKPEBGHPEAPEAG@Z`
- size: `617`
- prototype: `__int64 __fastcall(CTftpServer *this, const unsigned __int16 *, __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x180006590`

## callees

- `0x1800022d4`
- `0x18000a960`
- `0x18000ab48`
- `0x18000ac7c`
- `0x18000acfc`
- `0x18003aa68`
- `0x18003ab60`
- `0x18003b8c8`
- `0x18003ce78`
- `0x18003cf50`
- `0x18003d028`
- `0x180060e70`

## import_xrefs

- `msvcrt!wcschr` at `0x180002334`
- `msvcrt!wcschr` at `0x180002334`
- `KERNEL32!EnterCriticalSection` at `0x180002404`
- `KERNEL32!EnterCriticalSection` at `0x180002404`
- `KERNEL32!LeaveCriticalSection` at `0x180002445`
- `KERNEL32!LeaveCriticalSection` at `0x180002445`
- `KERNEL32!GetFileAttributesW` at `0x1800024b3`
- `KERNEL32!GetFileAttributesW` at `0x1800024b3`

## string_xrefs

- `0x18000231a`: `CTftpServer::GetFilePath: Request Path=[%s]`
- `0x180002351`: `CTftpServer::GetFilePath: Request path contains invalid character ':' possible attempt to access an NTFS alternate data stream`
- `0x18000249e`: `CTftpServer::GetFilePath: Local Path=[%s]`

## pseudocode

```c
__int64 __fastcall CTftpServer::GetFilePath(
        CTftpServer *this,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 **a4)
{
  unsigned __int16 *v7; // rsi
  unsigned __int16 *v8; // rdi
  const unsigned __int16 *v9; // rdx
  const unsigned __int16 *v10; // r8
  int v11; // r9d
  int v12; // ebx
  const char *v13; // rdx
  const char *v14; // r8
  unsigned int v15; // r9d
  int v16; // eax
  const char *v17; // rdx
  int v18; // r14d
  __int64 v19; // rbp
  const char *v20; // rdx
  unsigned int v21; // eax
  LPCWSTR lpFileName; // [rsp+30h] [rbp-38h] BYREF
  LPCWSTR v24; // [rsp+38h] [rbp-30h] BYREF
  LPCWSTR pszPath; // [rsp+70h] [rbp+8h] BYREF

  CMRSWLock::ReaderLock((LPCRITICAL_SECTION)this);
  v7 = 0;
  pszPath = 0;
  v8 = 0;
  v24 = 0;
  lpFileName = 0;
  if ( g_ErrLibTraceFunctionEx )
    g_ErrLibTraceFunctionEx(0x20000u, L"CTftpServer::GetFilePath: Request Path=[%s]", a2);
  if ( wcschr(a2, 0x3Au) )
  {
    if ( g_ErrLibTraceFunctionEx )
      g_ErrLibTraceFunctionEx(
        0x40000u,
        L"CTftpServer::GetFilePath: Request path contains invalid character ':' possible attempt to access an NTFS alternate data stream");
    v12 = 5;
  }
  else
  {
    v12 = ReplaceInString(a2, v9, v10, v11, (unsigned __int16 **)&pszPath);
    ElValidateHrLite(v12, v13, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x341u);
    if ( v12 >= 0 )
      v16 = v12;
    else
      v16 = ElValidateHr(v12, (const char *)v9, v14, v15);
    if ( v16 >= 0 )
    {
      v12 = TptCanonicalizePath(pszPath, (unsigned __int16 **)&v24);
      if ( ElValidateWin32(v12, v17, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x34Bu) )
      {
        v7 = (unsigned __int16 *)v24;
      }
      else
      {
        v18 = 0;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
        v7 = (unsigned __int16 *)v24;
        v19 = 0;
        if ( *((_DWORD *)this + 76) )
        {
          while ( !(unsigned int)CFolderFilter::Match(
                                   (CTftpServer *)((char *)this + 264),
                                   *(const unsigned __int16 **)(*((_QWORD *)this + 39) + 8 * v19),
                                   v7) )
          {
            v19 = (unsigned int)(v19 + 1);
            if ( (unsigned int)v19 >= *((_DWORD *)this + 76) )
              goto LABEL_20;
          }
          v18 = 1;
        }
LABEL_20:
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
        if ( v18 )
        {
          v12 = TptConstructFullPath(*((LPCWSTR *)this + 32), v7, (unsigned __int16 **)&lpFileName);
          v21 = ElValidateWin32(v12, v20, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x35Eu);
          v8 = (unsigned __int16 *)lpFileName;
          if ( !v21 )
          {
            if ( g_ErrLibTraceFunctionEx )
              g_ErrLibTraceFunctionEx(0x20000u, L"CTftpServer::GetFilePath: Local Path=[%s]", lpFileName);
            if ( GetFileAttributesW(v8) == -1 )
              v12 = 2;
            else
              *a4 = v8;
          }
        }
        else
        {
          v12 = 5;
        }
      }
    }
    else if ( v12 < 0 && (v12 & 0x1FFF0000) == 0x70000 )
    {
      v12 = (unsigned __int16)v12;
    }
    if ( pszPath )
      operator delete((void *)pszPath);
    if ( v7 )
      operator delete(v7);
  }
  if ( ElValidateWin32(v12, (const char *)v9, "base\\eco\\wds\\transport\\server\\tftp\\tftpserver.cpp", 0x383u) && v8 )
    operator delete(v8);
  CMRSWLock::ReaderRelease(this);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800022d4  mov     [rsp+arg_8], rbx
0x1800022d9  mov     [rsp+arg_10], rbp
0x1800022de  push    rsi
0x1800022df  push    rdi
0x1800022e0  push    r12
0x1800022e2  push    r13
0x1800022e4  push    r14
0x1800022e6  sub     rsp, 40h
0x1800022ea  mov     r12, r9
0x1800022ed  mov     rbx, rdx
0x1800022f0  mov     r13, rcx
0x1800022f3  call    ?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x1800022f8  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800022ff  xor     esi, esi
0x180002301  and     [rsp+68h+pszPath], rsi
0x180002306  xor     edi, edi
0x180002308  mov     [rsp+68h+var_30], rsi
0x18000230d  mov     [rsp+68h+lpFileName], rdi
0x180002312  test    rax, rax
0x180002315  jz      short loc_18000232C
0x180002317  mov     r8, rbx
0x18000231a  lea     rdx, aCtftpserverGet_1; "CTftpServer::GetFilePath: Request Path="...
0x180002321  mov     ecx, 20000h
0x180002326  call    cs:__guard_dispatch_icall_fptr
0x18000232c  mov     edx, 3Ah ; ':'; Ch
0x180002331  mov     rcx, rbx; Str
0x180002334  call    cs:__imp_wcschr
0x18000233b  nop     dword ptr [rax+rax+00h]
0x180002340  test    rax, rax
0x180002343  jz      short loc_18000236D
0x180002345  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000234c  test    rax, rax
0x18000234f  jz      short loc_180002363
0x180002351  lea     rdx, aCtftpserverGet; "CTftpServer::GetFilePath: Request path "...
0x180002358  mov     ecx, 40000h
0x18000235d  call    cs:__guard_dispatch_icall_fptr
0x180002363  mov     ebx, 5
0x180002368  jmp     loc_1800024F5
0x18000236d  lea     rax, [rsp+68h+pszPath]
0x180002372  mov     rcx, rbx; unsigned __int16 *
0x180002375  mov     [rsp+68h+var_48], rax; unsigned __int16 **
0x18000237a  call    ?ReplaceInString@@YAJPEBG00HPEAPEAG@Z; ReplaceInString(ushort const *,ushort const *,ushort const *,int,ushort * *)
0x18000237f  mov     r9d, 341h; unsigned int
0x180002385  lea     r8, aBaseEcoWdsTran_8; "base\\eco\\wds\\transport\\server\\tftp"...
0x18000238c  mov     ecx, eax; int
0x18000238e  mov     ebx, eax
0x180002390  call    ?ElValidateHrLite@@YAJJPEBD0K@Z; ElValidateHrLite(long,char const *,char const *,ulong)
0x180002395  test    ebx, ebx
0x180002397  jns     short loc_1800023A2
0x180002399  mov     ecx, ebx; int
0x18000239b  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800023a0  jmp     short loc_1800023A4
0x1800023a2  mov     eax, ebx
0x1800023a4  test    eax, eax
0x1800023a6  jns     short loc_1800023CA
0x1800023a8  test    ebx, ebx
0x1800023aa  jns     loc_1800024D6
0x1800023b0  mov     eax, ebx
0x1800023b2  and     eax, 1FFF0000h
0x1800023b7  cmp     eax, 70000h
0x1800023bc  jnz     loc_1800024D6
0x1800023c2  movzx   ebx, bx
0x1800023c5  jmp     loc_1800024D6
0x1800023ca  mov     rcx, [rsp+68h+pszPath]; pszPath
0x1800023cf  lea     rdx, [rsp+68h+var_30]; unsigned __int16 **
0x1800023d4  call    ?TptCanonicalizePath@@YAKPEBGPEAPEAG@Z; TptCanonicalizePath(ushort const *,ushort * *)
0x1800023d9  mov     r9d, 34Bh; unsigned int
0x1800023df  lea     r8, aBaseEcoWdsTran_8; "base\\eco\\wds\\transport\\server\\tftp"...
0x1800023e6  mov     ecx, eax; unsigned int
0x1800023e8  mov     ebx, eax
0x1800023ea  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800023ef  test    eax, eax
0x1800023f1  jnz     loc_1800024D1
0x1800023f7  lea     rbx, [r13+108h]
0x1800023fe  xor     r14d, r14d
0x180002401  mov     rcx, rbx; lpCriticalSection
0x180002404  call    cs:__imp_EnterCriticalSection
0x18000240b  nop     dword ptr [rax+rax+00h]
0x180002410  mov     rsi, [rsp+68h+var_30]
0x180002415  xor     ebp, ebp
0x180002417  cmp     [rbx+28h], edi
0x18000241a  jbe     short loc_180002442
0x18000241c  mov     rdx, [rbx+30h]
0x180002420  mov     r8, rsi; unsigned __int16 *
0x180002423  mov     rcx, rbx; this
0x180002426  mov     rdx, [rdx+rbp*8]; unsigned __int16 *
0x18000242a  call    ?Match@CFolderFilter@@AEAAHPEBG0@Z; CFolderFilter::Match(ushort const *,ushort const *)
0x18000242f  test    eax, eax
0x180002431  jnz     short loc_18000243C
0x180002433  inc     ebp
0x180002435  cmp     ebp, [rbx+28h]
0x180002438  jb      short loc_18000241C
0x18000243a  jmp     short loc_180002442
0x18000243c  mov     r14d, 1
0x180002442  mov     rcx, rbx; lpCriticalSection
0x180002445  call    cs:__imp_LeaveCriticalSection
0x18000244c  nop     dword ptr [rax+rax+00h]
0x180002451  test    r14d, r14d
0x180002454  jnz     short loc_18000245C
0x180002456  lea     ebx, [r14+5]
0x18000245a  jmp     short loc_1800024D6
0x18000245c  mov     rcx, [r13+100h]; pszPath
0x180002463  lea     r8, [rsp+68h+lpFileName]; unsigned __int16 **
0x180002468  mov     rdx, rsi; LPCWSTR
0x18000246b  call    ?TptConstructFullPath@@YAKPEBG0PEAPEAG@Z; TptConstructFullPath(ushort const *,ushort const *,ushort * *)
0x180002470  mov     r9d, 35Eh; unsigned int
0x180002476  lea     r8, aBaseEcoWdsTran_8; "base\\eco\\wds\\transport\\server\\tftp"...
0x18000247d  mov     ecx, eax; unsigned int
0x18000247f  mov     ebx, eax
0x180002481  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002486  mov     rdi, [rsp+68h+lpFileName]
0x18000248b  test    eax, eax
0x18000248d  jnz     short loc_1800024D6
0x18000248f  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180002496  test    rax, rax
0x180002499  jz      short loc_1800024B0
0x18000249b  mov     r8, rdi
0x18000249e  lea     rdx, aCtftpserverGet_0; "CTftpServer::GetFilePath: Local Path=[%"...
0x1800024a5  mov     ecx, 20000h
0x1800024aa  call    cs:__guard_dispatch_icall_fptr
0x1800024b0  mov     rcx, rdi; lpFileName
0x1800024b3  call    cs:__imp_GetFileAttributesW
0x1800024ba  nop     dword ptr [rax+rax+00h]
0x1800024bf  cmp     eax, 0FFFFFFFFh
0x1800024c2  jnz     short loc_1800024CB
0x1800024c4  mov     ebx, 2
0x1800024c9  jmp     short loc_1800024D6
0x1800024cb  mov     [r12], rdi
0x1800024cf  jmp     short loc_1800024D6
0x1800024d1  mov     rsi, [rsp+68h+var_30]
0x1800024d6  cmp     [rsp+68h+pszPath], 0
0x1800024dc  jz      short loc_1800024E8
0x1800024de  mov     rcx, [rsp+68h+pszPath]; void *
0x1800024e3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800024e8  test    rsi, rsi
0x1800024eb  jz      short loc_1800024F5
0x1800024ed  mov     rcx, rsi; void *
0x1800024f0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800024f5  mov     r9d, 383h; unsigned int
0x1800024fb  lea     r8, aBaseEcoWdsTran_8; "base\\eco\\wds\\transport\\server\\tftp"...
0x180002502  mov     ecx, ebx; unsigned int
0x180002504  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002509  test    eax, eax
0x18000250b  jz      short loc_18000251A
0x18000250d  test    rdi, rdi
0x180002510  jz      short loc_18000251A
0x180002512  mov     rcx, rdi; void *
0x180002515  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000251a  mov     rcx, r13; this
0x18000251d  call    ?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x180002522  lea     r11, [rsp+68h+var_28]
0x180002527  mov     eax, ebx
0x180002529  mov     rbx, [r11+38h]
0x18000252d  mov     rbp, [r11+40h]
0x180002531  mov     rsp, r11
0x180002534  pop     r14
0x180002536  pop     r13
0x180002538  pop     r12
0x18000253a  pop     rdi
0x18000253b  pop     rsi
0x18000253c  retn
```
