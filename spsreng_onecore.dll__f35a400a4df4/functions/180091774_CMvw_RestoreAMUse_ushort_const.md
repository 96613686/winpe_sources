# CMvw::RestoreAMUse(ushort const *)

- ea: `0x180091774`
- end: `0x180091877`
- name: `?RestoreAMUse@CMvw@@AEAAHPEBG@Z`
- size: `259`
- prototype: `int(CMvw *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800916a8`

## callees

- `0x180091774`
- `0x1800e42ec`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800917d4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800917d4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009184a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009184a`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180091812`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180091812`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180091862`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180091862`

## pseudocode

```c
__int64 __fastcall CMvw::RestoreAMUse(CMvw *this, const unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rax
  HANDLE FileW; // rdi
  unsigned int *v6; // r8
  __int64 v7; // rcx
  DWORD FileSize; // eax
  DWORD v9; // esi
  void *v10; // rdx
  DWORD nNumberOfBytesToRead; // [rsp+88h] [rbp+10h] BYREF

  v3 = 0;
  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
    if ( v4 )
    {
      FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
      if ( FileW != (HANDLE)-1LL )
      {
        v7 = *((_QWORD *)this + 15);
        nNumberOfBytesToRead = 0;
        if ( v7 )
        {
          if ( (int)CFileMapping::GetFileSize((CFileMapping *)(v7 + 24), &nNumberOfBytesToRead, v6) >= 0 )
          {
            FileSize = GetFileSize(FileW, 0);
            v9 = nNumberOfBytesToRead;
            if ( FileSize == nNumberOfBytesToRead )
            {
              v10 = (void *)*((_QWORD *)this + 16);
              nNumberOfBytesToRead = 0;
              if ( v10 )
              {
                if ( ReadFile(FileW, v10, v9, &nNumberOfBytesToRead, 0) && nNumberOfBytesToRead == v9 )
                  v3 = 1;
              }
            }
          }
        }
        CloseHandle(FileW);
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180091774  push    rbx
0x180091776  push    rbp
0x180091777  push    rsi
0x180091778  push    rdi
0x180091779  push    r14
0x18009177b  push    r15
0x18009177d  sub     rsp, 48h
0x180091781  xor     r14d, r14d
0x180091784  mov     r10, rdx
0x180091787  mov     rbp, rcx
0x18009178a  mov     ebx, r14d
0x18009178d  test    rdx, rdx
0x180091790  jz      loc_180091868
0x180091796  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009179a  inc     rax
0x18009179d  cmp     [rdx+rax*2], r14w
0x1800917a2  jnz     short loc_18009179A
0x1800917a4  test    rax, rax
0x1800917a7  jz      loc_180091868
0x1800917ad  xor     r9d, r9d; lpSecurityAttributes
0x1800917b0  mov     [rsp+78h+hTemplateFile], r14; hTemplateFile
0x1800917b5  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800917bd  mov     edx, 80000000h; dwDesiredAccess
0x1800917c2  mov     rcx, r10; lpFileName
0x1800917c5  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x1800917cd  lea     r15d, [r9+1]
0x1800917d1  mov     r8d, r15d; dwShareMode
0x1800917d4  call    cs:__imp_CreateFileW
0x1800917da  mov     rdi, rax
0x1800917dd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800917e1  jz      loc_180091868
0x1800917e7  mov     rcx, [rbp+78h]
0x1800917eb  mov     [rsp+78h+nNumberOfBytesToRead], r14d
0x1800917f3  test    rcx, rcx
0x1800917f6  jz      short loc_18009185F
0x1800917f8  add     rcx, 18h; this
0x1800917fc  lea     rdx, [rsp+78h+nNumberOfBytesToRead]; unsigned int *
0x180091804  call    ?GetFileSize@CFileMapping@@QEBAJPEAK0@Z; CFileMapping::GetFileSize(ulong *,ulong *)
0x180091809  test    eax, eax
0x18009180b  js      short loc_18009185F
0x18009180d  xor     edx, edx; lpFileSizeHigh
0x18009180f  mov     rcx, rdi; hFile
0x180091812  call    cs:__imp_GetFileSize
0x180091818  mov     esi, [rsp+78h+nNumberOfBytesToRead]
0x18009181f  cmp     eax, esi
0x180091821  jnz     short loc_18009185F
0x180091823  mov     rdx, [rbp+80h]; lpBuffer
0x18009182a  mov     [rsp+78h+nNumberOfBytesToRead], r14d
0x180091832  test    rdx, rdx
0x180091835  jz      short loc_18009185F
0x180091837  lea     r9, [rsp+78h+nNumberOfBytesToRead]; lpNumberOfBytesRead
0x18009183f  mov     qword ptr [rsp+78h+dwCreationDisposition], r14; lpOverlapped
0x180091844  mov     r8d, esi; nNumberOfBytesToRead
0x180091847  mov     rcx, rdi; hFile
0x18009184a  call    cs:__imp_ReadFile
0x180091850  test    eax, eax
0x180091852  jz      short loc_18009185F
0x180091854  cmp     [rsp+78h+nNumberOfBytesToRead], esi
0x18009185b  cmovz   ebx, r15d
0x18009185f  mov     rcx, rdi; hObject
0x180091862  call    cs:__imp_CloseHandle
0x180091868  mov     eax, ebx
0x18009186a  add     rsp, 48h
0x18009186e  pop     r15
0x180091870  pop     r14
0x180091872  pop     rdi
0x180091873  pop     rsi
0x180091874  pop     rbp
0x180091875  pop     rbx
0x180091876  retn
```
