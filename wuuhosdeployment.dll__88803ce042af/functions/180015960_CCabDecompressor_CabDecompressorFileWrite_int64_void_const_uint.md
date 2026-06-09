# CCabDecompressor::CabDecompressorFileWrite(__int64,void const *,uint)

- ea: `0x180015960`
- end: `0x180015a9e`
- name: `?CabDecompressorFileWrite@CCabDecompressor@@CAI_JPEBXI@Z`
- size: `318`
- prototype: `UINT __cdecl(INT_PTR hf, void *pv, UINT cb)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000956c`
- `0x18000e2a4`
- `0x180015960`
- `0x180042630`
- `0x1800496a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800159b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800159b8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800159ae`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800159ae`

## string_xrefs

- `0x1800159d6`: `CabDecompressorFileWrite - WriteFile`
- `0x180015a00`: `CabDecompressorFileWrite - invalid buffer`
- `0x180015a56`: `Write decompressed file to buffer`

## pseudocode

```c
__int64 __fastcall CCabDecompressor::CabDecompressorFileWrite(INT_PTR hf, void *pv, UINT cb)
{
  unsigned int v3; // ebx
  size_t v4; // rbp
  void *v7; // rcx
  __int64 v8; // r9
  __int64 v9; // rdi
  UINT v10; // eax
  UINT v11; // r14d
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-38h] BYREF

  v3 = -1;
  v4 = cb;
  if ( *(_DWORD *)(hf + 16) == 1 )
  {
    v7 = *(void **)(hf + 8);
    NumberOfBytesWritten = 0;
    if ( !WriteFile(v7, pv, cb, &NumberOfBytesWritten, 0) )
    {
      GetLastError();
LABEL_4:
      v8 = 3;
LABEL_12:
      WUTrace(0, 0, 32, v8);
      return v3;
    }
    return NumberOfBytesWritten;
  }
  else
  {
    v9 = *(_QWORD *)(hf + 8);
    if ( !v9 )
      goto LABEL_4;
    v10 = *(_DWORD *)(v9 + 20);
    v11 = v10 + cb;
    if ( v10 + cb < v10
      || *(_DWORD *)(v9 + 16) < v11 && (int)CSafeBuffer<unsigned char>::resize(*(_QWORD *)(hf + 8), v11) < 0 )
    {
      v8 = 5;
      goto LABEL_12;
    }
    memmove((void *)(*(_QWORD *)(v9 + 8) + *(unsigned int *)(v9 + 20)), pv, v4);
    *(_DWORD *)(v9 + 20) = v11;
    v3 = v4;
    *(_DWORD *)(hf + 20) += v4;
  }
  return v3;
}

```

## disassembly

```asm
0x180015960  mov     [rsp+arg_18], rbx
0x180015965  push    rbp
0x180015966  push    rsi
0x180015967  push    rdi
0x180015968  push    r14
0x18001596a  push    r15
0x18001596c  sub     rsp, 40h
0x180015970  mov     rax, cs:__security_cookie
0x180015977  xor     rax, rsp
0x18001597a  mov     [rsp+68h+var_30], rax
0x18001597f  or      ebx, 0FFFFFFFFh
0x180015982  mov     ebp, r8d
0x180015985  cmp     dword ptr [rcx+10h], 1
0x180015989  mov     r15, rdx
0x18001598c  mov     rsi, rcx
0x18001598f  jnz     short loc_1800159F7
0x180015991  mov     rcx, [rcx+8]; hFile
0x180015995  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001599a  mov     r8d, ebp; nNumberOfBytesToWrite
0x18001599d  mov     [rsp+68h+NumberOfBytesWritten], 0
0x1800159a5  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x1800159ae  call    cs:__imp_WriteFile
0x1800159b4  test    eax, eax
0x1800159b6  jnz     short loc_1800159EE
0x1800159b8  call    cs:__imp_GetLastError
0x1800159be  movzx   ecx, ax
0x1800159c1  or      ecx, 80070000h
0x1800159c7  test    eax, eax
0x1800159c9  cmovle  ecx, eax
0x1800159cc  mov     eax, 8000FFFFh
0x1800159d1  test    ecx, ecx
0x1800159d3  cmovns  ecx, eax
0x1800159d6  lea     rax, aCabdecompresso_3; "CabDecompressorFileWrite - WriteFile"
0x1800159dd  mov     [rsp+68h+var_40], rax
0x1800159e2  mov     dword ptr [rsp+68h+lpOverlapped], ecx
0x1800159e6  mov     r9d, 3
0x1800159ec  jmp     short loc_180015A6C
0x1800159ee  mov     ebx, [rsp+68h+NumberOfBytesWritten]
0x1800159f2  jmp     loc_180015A7B
0x1800159f7  mov     rdi, [rcx+8]
0x1800159fb  test    rdi, rdi
0x1800159fe  jnz     short loc_180015A13
0x180015a00  lea     rax, aCabdecompresso_1; "CabDecompressorFileWrite - invalid buff"...
0x180015a07  mov     [rsp+68h+var_40], rax
0x180015a0c  mov     [rsp+68h+lpOverlapped], rdi
0x180015a11  jmp     short loc_1800159E6
0x180015a13  mov     eax, [rdi+14h]
0x180015a16  lea     r14d, [rax+rbp]
0x180015a1a  cmp     r14d, eax
0x180015a1d  jb      short loc_180015A51
0x180015a1f  cmp     [rdi+10h], r14d
0x180015a23  jnb     short loc_180015A34
0x180015a25  mov     edx, r14d
0x180015a28  mov     rcx, rdi
0x180015a2b  call    ?resize@?$CSafeBuffer@E@@QEAAJI@Z; CSafeBuffer<uchar>::resize(uint)
0x180015a30  test    eax, eax
0x180015a32  js      short loc_180015A56
0x180015a34  mov     ecx, [rdi+14h]
0x180015a37  mov     r8, rbp; Size
0x180015a3a  add     rcx, [rdi+8]; void *
0x180015a3e  mov     rdx, r15; Src
0x180015a41  call    memmove
0x180015a46  mov     [rdi+14h], r14d
0x180015a4a  mov     ebx, ebp
0x180015a4c  add     [rsi+14h], ebp
0x180015a4f  jmp     short loc_180015A7B
0x180015a51  mov     eax, 80070216h
0x180015a56  lea     rcx, aWriteDecompres; "Write decompressed file to buffer"
0x180015a5d  mov     r9d, 5
0x180015a63  mov     [rsp+68h+var_40], rcx
0x180015a68  mov     dword ptr [rsp+68h+lpOverlapped], eax
0x180015a6c  mov     r8d, 20h ; ' '
0x180015a72  xor     edx, edx
0x180015a74  xor     ecx, ecx
0x180015a76  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180015a7b  mov     eax, ebx
0x180015a7d  mov     rcx, [rsp+68h+var_30]
0x180015a82  xor     rcx, rsp; StackCookie
0x180015a85  call    __security_check_cookie
0x180015a8a  mov     rbx, [rsp+68h+arg_18]
0x180015a92  add     rsp, 40h
0x180015a96  pop     r15
0x180015a98  pop     r14
0x180015a9a  pop     rdi
0x180015a9b  pop     rsi
0x180015a9c  pop     rbp
0x180015a9d  retn
```
