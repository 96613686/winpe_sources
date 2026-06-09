# XE_CXFileWriter::FlushDirectory(int)

- ea: `0x100451370`
- end: `0x100451553`
- name: `?FlushDirectory@XE_CXFileWriter@@AEAAHH@Z`
- size: `483`
- prototype: `__int64 __fastcall(XE_CXFileWriter *__hidden this, int)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10044dfd0`
- `0x100451110`
- `0x100451560`
- `0x1005d74f0`
- `0x1005d78b0`
- `0x1005d7ea0`

## callees

- `0x100450920`
- `0x1004509e0`
- `0x100451370`

## import_xrefs

- `KERNEL32!WriteFile` at `0x1004514e9`
- `KERNEL32!WriteFile` at `0x1004514e9`
- `KERNEL32!GetLastError` at `0x1004514f3`
- `KERNEL32!GetLastError` at `0x100451517`
- `KERNEL32!GetLastError` at `0x1004514f3`
- `KERNEL32!GetLastError` at `0x100451517`

## pseudocode

```c
__int64 __fastcall XE_CXFileWriter::FlushDirectory(XE_CXFileWriter *this, int a2)
{
  __int64 v2; // rax
  struct _OVERLAPPED *lpOverlapped; // rdi
  int v6; // eax
  unsigned int v7; // r8d
  int v8; // ecx
  int v9; // edx
  DWORD v10; // r14d
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned int v15; // esi
  __int64 v16; // rbp
  DWORD LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 82);
  lpOverlapped = (struct _OVERLAPPED *)((char *)this + 632);
  do
  {
    if ( v2 && LODWORD(lpOverlapped->Internal) == 259 )
    {
      if ( !a2 )
        return 1;
      ++*((_QWORD *)this + 93);
      if ( !(unsigned int)XE_CXFileWriter::WaitForIOToComplete(this) )
        return 0;
    }
    v2 = *((_QWORD *)this + 82);
  }
  while ( v2 && LODWORD(lpOverlapped->Internal) == 259 );
  if ( !(unsigned int)XE_CXFileWriter::ProcessIOResult(this, lpOverlapped) )
    return 0;
  if ( *((_QWORD *)this + 82) )
  {
    v6 = *((_DWORD *)this + 156);
    v7 = *((_DWORD *)this + 4);
    *((_DWORD *)this + 155) = v6;
    if ( 4 * v6 + v7 - 1 - (4 * v6 + v7 - 1) % v7 != 4 * v6 )
    {
      v8 = v7;
      if ( 4 * v6 > v7 )
        v8 = 4 * v6;
      *((_DWORD *)this + 155) = (v8 - 1 - (v8 - 1) % v7) >> 2;
    }
  }
  *(_OWORD *)&lpOverlapped->Internal = 0;
  *(_OWORD *)&lpOverlapped->Offset = 0;
  v9 = *((_DWORD *)this + 154) - *((_DWORD *)this + 155);
  if ( !*((_DWORD *)this + 154) )
  {
    if ( **((_DWORD **)this + 69) )
      v9 = 1;
  }
  v10 = *((_DWORD *)this + 4) - 1 + 4 * v9 - (unsigned int)(*((_DWORD *)this + 4) - 1 + 4 * v9) % *((_DWORD *)this + 4);
  if ( v10 )
  {
    _mm_lfence();
    v11 = *((_DWORD *)this + 154);
    v12 = *((unsigned int *)this + 155);
    ++*((_QWORD *)this + 92);
    *((_DWORD *)this + 156) = v11;
    v13 = *((_QWORD *)this + 84);
    *((_DWORD *)this + 162) = *((_DWORD *)this + 142) + 4 * v12;
    *((_QWORD *)this + 82) = v13;
    v14 = *((_QWORD *)this + 69);
    *((_DWORD *)this + 163) = 0;
    NumberOfBytesWritten = 0;
    if ( WriteFile(*((HANDLE *)this + 73), (LPCVOID)(v14 + 4 * v12), v10, &NumberOfBytesWritten, lpOverlapped) )
    {
      ++*((_QWORD *)this + 97);
    }
    else if ( GetLastError() != 997 )
    {
      _mm_lfence();
      v15 = *((_DWORD *)this + 162);
      v16 = **((_QWORD **)this + 105);
      LastError = GetLastError();
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, char *))(v16 + 64))(
        *((_QWORD *)this + 105),
        LastError,
        v15,
        v10,
        (char *)this + 32);
      return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x100451370  mov     [rsp+arg_10], rbx
0x100451375  push    rbp
0x100451376  push    rsi
0x100451377  push    rdi
0x100451378  sub     rsp, 30h
0x10045137c  mov     rax, [rcx+290h]
0x100451383  lea     rdi, [rcx+278h]
0x10045138a  mov     esi, edx
0x10045138c  mov     [rsp+48h+arg_8], r14
0x100451391  mov     rbx, rcx
0x100451394  mov     ebp, 1
0x100451399  test    rax, rax
0x10045139c  jz      short loc_1004513C5
0x10045139e  cmp     dword ptr [rdi], 103h
0x1004513a4  jnz     short loc_1004513C5
0x1004513a6  test    esi, esi
0x1004513a8  jz      loc_10045153F
0x1004513ae  inc     qword ptr [rbx+2E8h]
0x1004513b5  mov     rcx, rbx; this
0x1004513b8  call    ?WaitForIOToComplete@XE_CXFileWriter@@AEAAHXZ; XE_CXFileWriter::WaitForIOToComplete(void)
0x1004513bd  test    eax, eax
0x1004513bf  jz      loc_100451534
0x1004513c5  mov     rax, [rbx+290h]
0x1004513cc  test    rax, rax
0x1004513cf  jz      short loc_1004513D9
0x1004513d1  cmp     dword ptr [rdi], 103h
0x1004513d7  jz      short loc_100451394
0x1004513d9  mov     rdx, rdi; struct _OVERLAPPED *
0x1004513dc  mov     rcx, rbx; this
0x1004513df  call    ?ProcessIOResult@XE_CXFileWriter@@AEAAHPEAU_OVERLAPPED@@@Z; XE_CXFileWriter::ProcessIOResult(_OVERLAPPED *)
0x1004513e4  test    eax, eax
0x1004513e6  jz      loc_100451534
0x1004513ec  cmp     qword ptr [rbx+290h], 0
0x1004513f4  jz      short loc_100451441
0x1004513f6  mov     eax, [rbx+270h]
0x1004513fc  xor     edx, edx
0x1004513fe  mov     r8d, [rbx+10h]
0x100451402  mov     [rbx+26Ch], eax
0x100451408  lea     r9d, ds:0[rax*4]
0x100451410  lea     ecx, [r8-1]
0x100451414  add     ecx, r9d
0x100451417  mov     eax, ecx
0x100451419  div     r8d
0x10045141c  sub     ecx, edx
0x10045141e  cmp     ecx, r9d
0x100451421  jz      short loc_100451441
0x100451423  cmp     r9d, r8d
0x100451426  mov     ecx, r8d
0x100451429  cmova   ecx, r9d
0x10045142d  xor     edx, edx
0x10045142f  dec     ecx
0x100451431  mov     eax, ecx
0x100451433  div     r8d
0x100451436  sub     ecx, edx
0x100451438  shr     ecx, 2
0x10045143b  mov     [rbx+26Ch], ecx
0x100451441  xorps   xmm0, xmm0
0x100451444  movups  xmmword ptr [rdi], xmm0
0x100451447  movups  xmmword ptr [rdi+10h], xmm0
0x10045144b  mov     eax, [rbx+268h]
0x100451451  mov     edx, eax
0x100451453  sub     edx, [rbx+26Ch]
0x100451459  test    eax, eax
0x10045145b  jnz     short loc_10045146A
0x10045145d  mov     rax, [rbx+228h]
0x100451464  cmp     dword ptr [rax], 0
0x100451467  cmovnz  edx, ebp
0x10045146a  mov     ecx, [rbx+10h]
0x10045146d  lea     r14d, [rcx-1]
0x100451471  lea     r14d, [r14+rdx*4]
0x100451475  xor     edx, edx
0x100451477  mov     eax, r14d
0x10045147a  div     ecx
0x10045147c  sub     r14d, edx
0x10045147f  jz      loc_10045153F
0x100451485  lfence
0x100451488  mov     eax, [rbx+268h]
0x10045148e  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x100451493  mov     edx, [rbx+26Ch]
0x100451499  mov     r8d, r14d; nNumberOfBytesToWrite
0x10045149c  inc     qword ptr [rbx+2E0h]
0x1004514a3  mov     [rbx+270h], eax
0x1004514a9  mov     eax, [rbx+238h]
0x1004514af  mov     [rsp+48h+lpOverlapped], rdi; lpOverlapped
0x1004514b4  lea     ecx, [rax+rdx*4]
0x1004514b7  mov     rax, [rbx+2A0h]
0x1004514be  mov     [rbx+288h], ecx
0x1004514c4  xor     ecx, ecx
0x1004514c6  mov     [rbx+290h], rax
0x1004514cd  mov     rax, [rbx+228h]
0x1004514d4  mov     [rbx+28Ch], ecx
0x1004514da  mov     [rsp+48h+NumberOfBytesWritten], ecx
0x1004514de  mov     rcx, [rbx+248h]; hFile
0x1004514e5  lea     rdx, [rax+rdx*4]; lpBuffer
0x1004514e9  call    cs:__imp_WriteFile
0x1004514ef  test    eax, eax
0x1004514f1  jnz     short loc_100451538
0x1004514f3  call    cs:__imp_GetLastError
0x1004514f9  cmp     eax, 3E5h
0x1004514fe  jz      short loc_10045153F
0x100451500  lfence
0x100451503  mov     rax, [rbx+348h]
0x10045150a  lea     rdi, [rbx+20h]
0x10045150e  mov     esi, [rbx+288h]
0x100451514  mov     rbp, [rax]
0x100451517  call    cs:__imp_GetLastError
0x10045151d  mov     rcx, [rbx+348h]
0x100451524  mov     r9d, r14d
0x100451527  mov     edx, eax
0x100451529  mov     [rsp+48h+lpOverlapped], rdi
0x10045152e  mov     r8d, esi
0x100451531  call    qword ptr [rbp+40h]
0x100451534  xor     eax, eax
0x100451536  jmp     short loc_100451541
0x100451538  inc     qword ptr [rbx+308h]
0x10045153f  mov     eax, ebp
0x100451541  mov     r14, [rsp+48h+arg_8]
0x100451546  mov     rbx, [rsp+48h+arg_10]
0x10045154b  add     rsp, 30h
0x10045154f  pop     rdi
0x100451550  pop     rsi
0x100451551  pop     rbp
0x100451552  retn
```
