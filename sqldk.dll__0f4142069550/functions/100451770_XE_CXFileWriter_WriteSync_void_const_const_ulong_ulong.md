# XE_CXFileWriter::WriteSync(void const * const,ulong,ulong)

- ea: `0x100451770`
- end: `0x1004518ca`
- name: `?WriteSync@XE_CXFileWriter@@AEAAHQEBXKK@Z`
- size: `346`
- prototype: `int(XE_CXFileWriter *__hidden this, const void *const, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x100450160`
- `0x100451260`

## callees

- `0x100401980`
- `0x100403070`
- `0x100404bf2`
- `0x100451770`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x10045184b`
- `KERNEL32!GetOverlappedResult` at `0x10045184b`
- `KERNEL32!WriteFile` at `0x10045181d`
- `KERNEL32!WriteFile` at `0x10045181d`
- `KERNEL32!GetLastError` at `0x100451827`
- `KERNEL32!GetLastError` at `0x100451869`
- `KERNEL32!GetLastError` at `0x100451827`
- `KERNEL32!GetLastError` at `0x100451869`

## pseudocode

```c
__int64 __fastcall XE_CXFileWriter::WriteSync(XE_CXFileWriter *this, _BYTE *a2, DWORD a3, DWORD a4)
{
  __int64 v4; // rdi
  __int64 v8; // rsi
  DWORD LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-268h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+38h] [rbp-260h] BYREF
  _BYTE v13[512]; // [rsp+60h] [rbp-238h] BYREF

  v4 = a4;
  NumberOfBytesWritten = 0;
  *(_OWORD *)&Overlapped.Offset = 0;
  Overlapped.Offset = a4;
  *(_OWORD *)&Overlapped.Internal = 0;
  memset_0(v13, 0, sizeof(v13));
  if ( (*((_DWORD *)this + 148) & 0x20000000) != 0 )
  {
    if ( a3 >= 0x200 )
    {
      if ( a3 % *((_DWORD *)this + 4) )
        return 0;
    }
    else
    {
      memmove(v13, a2, a3);
      a2 = v13;
      a3 = 512;
    }
  }
  if ( WriteFile(*((HANDLE *)this + 73), a2, a3, &NumberOfBytesWritten, &Overlapped)
    || GetLastError() == 997
    && GetOverlappedResult(*((HANDLE *)this + 73), &Overlapped, &NumberOfBytesWritten, 1)
    && NumberOfBytesWritten == a3 )
  {
    return 1;
  }
  v8 = **((_QWORD **)this + 105);
  LastError = GetLastError();
  (*(void (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, char *))(v8 + 64))(
    *((_QWORD *)this + 105),
    LastError,
    v4,
    a3,
    (char *)this + 32);
  return 0;
}

```

## disassembly

```asm
0x100451770  push    rbx
0x100451772  push    rbp
0x100451773  push    rdi
0x100451774  push    r14
0x100451776  sub     rsp, 278h
0x10045177d  mov     rax, cs:__security_cookie
0x100451784  xor     rax, rsp
0x100451787  mov     [rsp+298h+var_38], rax
0x10045178f  xorps   xmm0, xmm0
0x100451792  mov     edi, r9d
0x100451795  mov     ebp, r8d
0x100451798  mov     rbx, rdx
0x10045179b  mov     r14, rcx
0x10045179e  mov     [rsp+298h+NumberOfBytesWritten], 0
0x1004517a6  movups  xmmword ptr [rsp+298h+Overlapped.10h], xmm0
0x1004517ab  xor     edx, edx; Val
0x1004517ad  mov     dword ptr [rsp+298h+Overlapped.10h], edi
0x1004517b1  mov     r8d, 200h; Size
0x1004517b7  lea     rcx, [rsp+298h+var_238]; void *
0x1004517bc  movups  xmmword ptr [rsp+298h+Overlapped.Internal], xmm0
0x1004517c1  call    memset_0
0x1004517c6  test    dword ptr [r14+250h], 20000000h
0x1004517d1  jz      short loc_1004517F9
0x1004517d3  cmp     ebp, 200h
0x1004517d9  jnb     loc_10045188B
0x1004517df  mov     r8d, ebp; Size
0x1004517e2  lea     rcx, [rsp+298h+var_238]; void *
0x1004517e7  mov     rdx, rbx; Src
0x1004517ea  call    memmove
0x1004517ef  lea     rbx, [rsp+298h+var_238]
0x1004517f4  mov     ebp, 200h
0x1004517f9  mov     rcx, [r14+248h]; hFile
0x100451800  lea     rax, [rsp+298h+Overlapped]
0x100451805  lea     r9, [rsp+298h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x10045180a  mov     [rsp+298h+lpOverlapped], rax; lpOverlapped
0x10045180f  mov     r8d, ebp; nNumberOfBytesToWrite
0x100451812  mov     [rsp+298h+var_28], rsi
0x10045181a  mov     rdx, rbx; lpBuffer
0x10045181d  call    cs:__imp_WriteFile
0x100451823  test    eax, eax
0x100451825  jnz     short loc_1004518A0
0x100451827  call    cs:__imp_GetLastError
0x10045182d  cmp     eax, 3E5h
0x100451832  jnz     short loc_10045185B
0x100451834  mov     rcx, [r14+248h]; hFile
0x10045183b  lea     r8, [rsp+298h+NumberOfBytesWritten]; lpNumberOfBytesTransferred
0x100451840  mov     r9d, 1; bWait
0x100451846  lea     rdx, [rsp+298h+Overlapped]; lpOverlapped
0x10045184b  call    cs:__imp_GetOverlappedResult
0x100451851  test    eax, eax
0x100451853  jz      short loc_10045185B
0x100451855  cmp     [rsp+298h+NumberOfBytesWritten], ebp
0x100451859  jz      short loc_1004518A0
0x10045185b  mov     rax, [r14+348h]
0x100451862  lea     rbx, [r14+20h]
0x100451866  mov     rsi, [rax]
0x100451869  call    cs:__imp_GetLastError
0x10045186f  mov     rcx, [r14+348h]
0x100451876  mov     r9d, ebp
0x100451879  mov     edx, eax
0x10045187b  mov     [rsp+298h+lpOverlapped], rbx
0x100451880  mov     r8, rdi
0x100451883  call    qword ptr [rsi+40h]
0x100451886  xor     eax, eax
0x100451888  jmp     short loc_1004518A5
0x10045188b  xor     edx, edx
0x10045188d  mov     eax, ebp
0x10045188f  div     dword ptr [r14+10h]
0x100451893  test    edx, edx
0x100451895  jz      loc_1004517F9
0x10045189b  xor     eax, eax
0x10045189d  jmp     short loc_1004518AD
0x1004518a0  mov     eax, 1
0x1004518a5  mov     rsi, [rsp+298h+var_28]
0x1004518ad  mov     rcx, [rsp+298h+var_38]
0x1004518b5  xor     rcx, rsp; StackCookie
0x1004518b8  call    __security_check_cookie
0x1004518bd  add     rsp, 278h
0x1004518c4  pop     r14
0x1004518c6  pop     rdi
0x1004518c7  pop     rbp
0x1004518c8  pop     rbx
0x1004518c9  retn
```
