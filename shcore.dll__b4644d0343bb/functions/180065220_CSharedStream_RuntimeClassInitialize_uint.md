# CSharedStream::RuntimeClassInitialize(uint)

- ea: `0x180065220`
- end: `0x180065327`
- name: `?RuntimeClassInitialize@CSharedStream@@QEAAJI@Z`
- size: `263`
- prototype: `int(CSharedStream *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x18007ebb0`

## callees

- `0x18001c82c`
- `0x1800244b4`
- `0x180065220`
- `0x180065330`
- `0x18007f3b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800652e7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800652e7`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180065249`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800652a9`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180065249`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800652a9`

## pseudocode

```c
__int64 __fastcall CSharedStream::RuntimeClassInitialize(CSharedStream *this, DWORD dwMaximumSizeLow)
{
  __int64 v2; // rdi
  HANDLE FileMappingW; // rax
  __int64 result; // rax
  HANDLE v6; // rax
  HANDLE MutexW; // rax
  CSharedStream *v8; // [rsp+30h] [rbp-18h] BYREF
  int v9; // [rsp+38h] [rbp-10h]

  v2 = dwMaximumSizeLow;
  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, dwMaximumSizeLow, 0);
  *((_QWORD *)this + 26) = FileMappingW;
  if ( FileMappingW || (result = ResultFromKnownLastError(), (int)result >= 0) )
  {
    result = anonymous_namespace_::_MapViewOfFile_unsigned_char_(*((_QWORD *)this + 26), 983071, v2, (char *)this + 216);
    if ( (int)result >= 0 )
    {
      v6 = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0xCu, 0);
      *((_QWORD *)this + 37) = v6;
      if ( v6 || (result = ResultFromKnownLastError(), (int)result >= 0) )
      {
        result = anonymous_namespace_::_MapViewOfFile_SHARED_STREAM_ACCESS_CHANNEL_(
                   *((_QWORD *)this + 37),
                   983071,
                   (char *)this + 304);
        if ( (int)result >= 0 )
        {
          MutexW = CreateMutexW(0, 0, 0);
          *((_QWORD *)this + 39) = MutexW;
          if ( MutexW || (result = ResultFromKnownLastError(), (int)result >= 0) )
          {
            *((_BYTE *)this + 288) = 1;
            v8 = this;
            v9 = v2;
            return anonymous_namespace_::_TryActionOnPageBackedDataWithExceptionHandling__lambda_4ef37bc121c30cbeae1dd66b88da76a8___(&v8);
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180065220  mov     [rsp+arg_0], rbx
0x180065225  push    rdi
0x180065226  sub     rsp, 40h
0x18006522a  mov     edi, edx
0x18006522c  xor     r9d, r9d; dwMaximumSizeHigh
0x18006522f  mov     rbx, rcx
0x180065232  mov     [rsp+48h+lpName], 0; lpName
0x18006523b  xor     edx, edx; lpFileMappingAttributes
0x18006523d  mov     [rsp+48h+dwMaximumSizeLow], edi; dwMaximumSizeLow
0x180065241  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180065245  lea     r8d, [r9+4]; flProtect
0x180065249  call    cs:__imp_CreateFileMappingW
0x18006524f  mov     [rbx+0D0h], rax
0x180065256  test    rax, rax
0x180065259  jnz     short loc_180065268
0x18006525b  call    ResultFromKnownLastError
0x180065260  test    eax, eax
0x180065262  js      loc_18006531C
0x180065268  mov     rcx, [rbx+0D0h]
0x18006526f  lea     r9, [rbx+0D8h]
0x180065276  mov     r8, rdi
0x180065279  mov     edx, 0F001Fh
0x18006527e  call    _anonymous_namespace____MapViewOfFile_unsigned_char_
0x180065283  test    eax, eax
0x180065285  js      loc_18006531C
0x18006528b  xor     r9d, r9d; dwMaximumSizeHigh
0x18006528e  mov     [rsp+48h+lpName], 0; lpName
0x180065297  xor     edx, edx; lpFileMappingAttributes
0x180065299  mov     [rsp+48h+dwMaximumSizeLow], 0Ch; dwMaximumSizeLow
0x1800652a1  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800652a5  lea     r8d, [r9+4]; flProtect
0x1800652a9  call    cs:__imp_CreateFileMappingW
0x1800652af  mov     [rbx+128h], rax
0x1800652b6  test    rax, rax
0x1800652b9  jnz     short loc_1800652C4
0x1800652bb  call    ResultFromKnownLastError
0x1800652c0  test    eax, eax
0x1800652c2  js      short loc_18006531C
0x1800652c4  mov     rcx, [rbx+128h]
0x1800652cb  lea     r8, [rbx+130h]
0x1800652d2  mov     edx, 0F001Fh
0x1800652d7  call    _anonymous_namespace____MapViewOfFile_SHARED_STREAM_ACCESS_CHANNEL_
0x1800652dc  test    eax, eax
0x1800652de  js      short loc_18006531C
0x1800652e0  xor     r8d, r8d; lpName
0x1800652e3  xor     edx, edx; bInitialOwner
0x1800652e5  xor     ecx, ecx; lpMutexAttributes
0x1800652e7  call    cs:__imp_CreateMutexW
0x1800652ed  mov     [rbx+138h], rax
0x1800652f4  test    rax, rax
0x1800652f7  jnz     short loc_180065302
0x1800652f9  call    ResultFromKnownLastError
0x1800652fe  test    eax, eax
0x180065300  js      short loc_18006531C
0x180065302  lea     rcx, [rsp+48h+var_18]
0x180065307  mov     byte ptr [rbx+120h], 1
0x18006530e  mov     [rsp+48h+var_18], rbx
0x180065313  mov     [rsp+48h+var_10], edi
0x180065317  call    _anonymous_namespace____TryActionOnPageBackedDataWithExceptionHandling__lambda_4ef37bc121c30cbeae1dd66b88da76a8___
0x18006531c  mov     rbx, [rsp+48h+arg_0]
0x180065321  add     rsp, 40h
0x180065325  pop     rdi
0x180065326  retn
```
