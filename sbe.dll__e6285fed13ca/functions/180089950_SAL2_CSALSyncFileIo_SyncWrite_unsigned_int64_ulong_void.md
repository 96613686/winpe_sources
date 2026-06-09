# SAL2::CSALSyncFileIo::SyncWrite(unsigned __int64,ulong,void *)

- ea: `0x180089950`
- end: `0x180089ae8`
- name: `?SyncWrite@CSALSyncFileIo@SAL2@@UEAAJ_KKPEAX@Z`
- size: `408`
- prototype: `int(SAL2::CSALSyncFileIo *__hidden this, unsigned __int64, unsigned int, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1800627f0`
- `0x180089950`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180089a08`
- `KERNEL32!GetLastError` at `0x180089a45`
- `KERNEL32!GetLastError` at `0x180089ac8`
- `KERNEL32!GetLastError` at `0x180089a08`
- `KERNEL32!GetLastError` at `0x180089a45`
- `KERNEL32!GetLastError` at `0x180089ac8`
- `KERNEL32!GetOverlappedResult` at `0x180089a3b`
- `KERNEL32!GetOverlappedResult` at `0x180089abe`
- `KERNEL32!GetOverlappedResult` at `0x180089a3b`
- `KERNEL32!GetOverlappedResult` at `0x180089abe`
- `KERNEL32!WriteFile` at `0x1800899fa`
- `KERNEL32!WriteFile` at `0x1800899fa`

## pseudocode

```c
__int64 __fastcall SAL2::CSALSyncFileIo::SyncWrite(SAL2::CSALSyncFileIo *this, void *a2, DWORD a3, void *a4)
{
  void *v5; // rcx
  unsigned int v7; // ebx
  unsigned int v8; // r9d
  unsigned int v9; // r8d
  void *v10; // rax
  signed int v11; // eax
  signed int v12; // eax
  signed int LastError; // eax
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-28h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+80h] [rbp+28h] BYREF

  NumberOfBytesTransferred = 0;
  v5 = (void *)*((_QWORD *)this + 36);
  Overlapped.Internal = 0;
  Overlapped.InternalHigh = 0;
  if ( v5 == (void *)-1LL )
  {
    v7 = -2147418113;
    v8 = -2147418113;
    v9 = 1352;
LABEL_19:
    SBEBasicTracers::EtwTraceError(
      (SAL2::CSALSyncFileIo *)((char *)this + 112),
      "multimedia\\dshow\\filters\\sbe\\sal\\salfileio.cpp",
      v9,
      v8);
    return v7;
  }
  if ( !a3 )
  {
    v7 = -2147024809;
    v8 = -2147024809;
    v9 = 1353;
    goto LABEL_19;
  }
  if ( !a4 )
  {
    v7 = -2147024809;
    v8 = -2147024809;
    v9 = 1354;
    goto LABEL_19;
  }
  v10 = (void *)*((_QWORD *)this + 38);
  Overlapped.Pointer = a2;
  Overlapped.hEvent = v10;
  if ( WriteFile(v5, a4, a3, 0, &Overlapped) )
  {
    v7 = 0;
    if ( !GetOverlappedResult(*((HANDLE *)this + 36), &Overlapped, &NumberOfBytesTransferred, 1) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v8 = v7;
      v9 = 1388;
      goto LABEL_19;
    }
  }
  else
  {
    v11 = GetLastError();
    if ( v11 > 0 )
      v7 = (unsigned __int16)v11 | 0x80070000;
    else
      v7 = v11;
    if ( v11 == 997 )
    {
      if ( !GetOverlappedResult(*((HANDLE *)this + 36), &Overlapped, &NumberOfBytesTransferred, 1) )
      {
        v12 = GetLastError();
        v7 = v12;
        if ( v12 > 0 )
          v7 = (unsigned __int16)v12 | 0x80070000;
        v8 = v7;
        v9 = 1378;
        goto LABEL_19;
      }
      v7 = 0;
    }
    else if ( (v7 & 0x80000000) != 0 )
    {
      v8 = v7;
      v9 = 1382;
      goto LABEL_19;
    }
  }
  if ( NumberOfBytesTransferred < a3 )
  {
    v7 = -2147024774;
    v8 = -2147024774;
    v9 = 1394;
    goto LABEL_19;
  }
  return v7;
}

```

## disassembly

```asm
0x180089950  push    rbp
0x180089952  push    rbx
0x180089953  push    rdi
0x180089954  push    r14
0x180089956  mov     rbp, rsp
0x180089959  sub     rsp, 58h
0x18008995d  mov     rdi, rcx
0x180089960  mov     [rbp+NumberOfBytesTransferred], 0
0x180089967  mov     rcx, [rcx+120h]; hFile
0x18008996e  mov     r10, r9
0x180089971  mov     [rbp+Overlapped.Internal], 0
0x180089979  mov     r14d, r8d
0x18008997c  mov     [rbp+Overlapped.InternalHigh], 0
0x180089984  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180089988  jnz     short loc_1800899A0
0x18008998a  mov     ebx, 8000FFFFh
0x18008998f  mov     r9d, 8000FFFFh
0x180089995  mov     r8d, 548h
0x18008999b  jmp     loc_180089A7E
0x1800899a0  test    r14d, r14d
0x1800899a3  jnz     short loc_1800899BB
0x1800899a5  mov     ebx, 80070057h
0x1800899aa  mov     r9d, 80070057h
0x1800899b0  mov     r8d, 549h
0x1800899b6  jmp     loc_180089A7E
0x1800899bb  test    r10, r10
0x1800899be  jnz     short loc_1800899D6
0x1800899c0  mov     ebx, 80070057h
0x1800899c5  mov     r9d, 80070057h
0x1800899cb  mov     r8d, 54Ah; nNumberOfBytesToWrite
0x1800899d1  jmp     loc_180089A7E
0x1800899d6  mov     rax, [rdi+130h]
0x1800899dd  xor     r9d, r9d; lpNumberOfBytesWritten
0x1800899e0  mov     dword ptr [rbp+Overlapped.10h], edx
0x1800899e3  shr     rdx, 20h
0x1800899e7  mov     [rbp+Overlapped.hEvent], rax
0x1800899eb  lea     rax, [rbp+Overlapped]
0x1800899ef  mov     dword ptr [rbp+Overlapped.10h+4], edx
0x1800899f2  mov     rdx, r10; lpBuffer
0x1800899f5  mov     [rsp+58h+lpOverlapped], rax; lpOverlapped
0x1800899fa  call    cs:__imp_WriteFile
0x180089a00  test    eax, eax
0x180089a02  jnz     loc_180089AA9
0x180089a08  call    cs:__imp_GetLastError
0x180089a0e  test    eax, eax
0x180089a10  jg      short loc_180089A16
0x180089a12  mov     ebx, eax
0x180089a14  jmp     short loc_180089A1F
0x180089a16  movzx   ebx, ax
0x180089a19  or      ebx, 80070000h
0x180089a1f  cmp     eax, 3E5h
0x180089a24  jnz     short loc_180089A9A
0x180089a26  mov     rcx, [rdi+120h]; hFile
0x180089a2d  lea     r8, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180089a31  mov     r9d, 1; bWait
0x180089a37  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x180089a3b  call    cs:__imp_GetOverlappedResult
0x180089a41  test    eax, eax
0x180089a43  jnz     short loc_180089A65
0x180089a45  call    cs:__imp_GetLastError
0x180089a4b  mov     ebx, eax
0x180089a4d  test    eax, eax
0x180089a4f  jle     short loc_180089A5A
0x180089a51  movzx   ebx, ax
0x180089a54  or      ebx, 80070000h
0x180089a5a  mov     r9d, ebx
0x180089a5d  mov     r8d, 562h
0x180089a63  jmp     short loc_180089A7E
0x180089a65  xor     ebx, ebx
0x180089a67  cmp     [rbp+NumberOfBytesTransferred], r14d
0x180089a6b  jnb     short loc_180089A8E
0x180089a6d  mov     ebx, 8007007Ah
0x180089a72  mov     r9d, 8007007Ah; unsigned int
0x180089a78  mov     r8d, 572h; unsigned int
0x180089a7e  lea     rdx, aMultimediaDsho_11; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x180089a85  lea     rcx, [rdi+70h]; struct CEhEventTracer *
0x180089a89  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x180089a8e  mov     eax, ebx
0x180089a90  add     rsp, 58h
0x180089a94  pop     r14
0x180089a96  pop     rdi
0x180089a97  pop     rbx
0x180089a98  pop     rbp
0x180089a99  retn
0x180089a9a  test    ebx, ebx
0x180089a9c  jns     short loc_180089A67
0x180089a9e  mov     r9d, ebx
0x180089aa1  mov     r8d, 566h
0x180089aa7  jmp     short loc_180089A7E
0x180089aa9  mov     rcx, [rdi+120h]; hFile
0x180089ab0  lea     r8, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180089ab4  xor     ebx, ebx
0x180089ab6  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x180089aba  lea     r9d, [rbx+1]; bWait
0x180089abe  call    cs:__imp_GetOverlappedResult
0x180089ac4  test    eax, eax
0x180089ac6  jnz     short loc_180089A67
0x180089ac8  call    cs:__imp_GetLastError
0x180089ace  mov     ebx, eax
0x180089ad0  test    eax, eax
0x180089ad2  jle     short loc_180089ADD
0x180089ad4  movzx   ebx, ax
0x180089ad7  or      ebx, 80070000h
0x180089add  mov     r9d, ebx
0x180089ae0  mov     r8d, 56Ch
0x180089ae6  jmp     short loc_180089A7E
```
