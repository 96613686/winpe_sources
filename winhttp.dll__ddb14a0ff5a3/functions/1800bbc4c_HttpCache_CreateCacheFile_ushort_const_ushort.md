# HttpCache::CreateCacheFile(ushort const *,ushort * *)

- ea: `0x1800bbc4c`
- end: `0x1800bbe6a`
- name: `?CreateCacheFile@HttpCache@@AEAAJPEBGPEAPEAG@Z`
- size: `542`
- prototype: `__int64 __fastcall(WCHAR **this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800bc150`

## callees

- `0x180019384`
- `0x1800193a0`
- `0x18002acec`
- `0x18005cfd8`
- `0x1800940b0`
- `0x18009b04c`
- `0x1800a1d10`
- `0x1800bbc4c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x1800bbcf3`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x1800bbcf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbd6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbdde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbd6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbdde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bbd5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bbe27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bbd5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bbe27`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800bbdd4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800bbdd4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800bbd4c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800bbd4c`
- `CRYPTBASE!SystemFunction036` at `0x1800bbce9`
- `CRYPTBASE!SystemFunction036` at `0x1800bbce9`

## string_xrefs

- `0x1800bbd11`: `%s\%u.cache`

## pseudocode

```c
__int64 __fastcall HttpCache::CreateCacheFile(WCHAR **this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  int Directory; // edi
  HANDLE FileW; // r15
  signed int LastError; // eax
  signed int v9; // eax
  unsigned int RandomBuffer; // [rsp+40h] [rbp-30h] BYREF
  int v12; // [rsp+48h] [rbp-28h] BYREF
  int v13; // [rsp+4Ch] [rbp-24h]
  LPCWSTR lpFileName[2]; // [rsp+50h] [rbp-20h] BYREF

  v13 = 0;
  lpFileName[0] = (LPCWSTR)qword_1800E7D10;
  lpFileName[1] = 0;
  RandomBuffer = 0;
  v12 = 0;
  if ( a3 )
    *a3 = 0;
  if ( !a2 || !*a2 )
  {
    v13 = 264;
    goto LABEL_31;
  }
  if ( !a3 )
  {
    v13 = 265;
LABEL_31:
    Directory = -2147024809;
    goto LABEL_32;
  }
  Directory = WxCreateDirectory(*this);
  if ( Directory >= 0 )
  {
    if ( !SystemFunction036(&RandomBuffer, 4u) )
      RandomBuffer = rand();
    while ( 1 )
    {
      CWxString::Empty((CWxString *)lpFileName);
      Directory = CWxString::Format((CWxString *)lpFileName, L"%s\\%u.cache", *this, RandomBuffer);
      if ( Directory < 0 )
      {
        v13 = 277;
        goto LABEL_32;
      }
      FileW = CreateFileW(lpFileName[0], 0xC0000000, 3u, 0, 1u, 4u, 0);
      if ( FileW != (HANDLE)-1LL )
        break;
      LastError = GetLastError();
      Directory = LastError;
      if ( LastError != 80 )
      {
        if ( LastError > 0 )
          Directory = (unsigned __int16)LastError | 0x80070000;
        if ( Directory < 0 )
        {
          v13 = 296;
          goto LABEL_32;
        }
      }
      ++RandomBuffer;
    }
    Directory = WxStringCchLengthDWordW(a2, 0x7FFFFFFF, &v12);
    if ( Directory >= 0 )
    {
      if ( WriteFile(FileW, a2, 2 * v12, 0, 0) )
      {
        CWxString::Detach((CWxString *)lpFileName, a3);
        Directory = 0;
      }
      else
      {
        v9 = GetLastError();
        Directory = v9;
        if ( v9 > 0 )
          Directory = (unsigned __int16)v9 | 0x80070000;
        v13 = 309;
        if ( Directory >= 0 )
          Directory = -2147418113;
      }
    }
    else
    {
      v13 = 303;
    }
    CloseHandle(FileW);
  }
  else
  {
    v13 = 267;
  }
LABEL_32:
  CWxString::_Release((CWxString *)lpFileName);
  return (unsigned int)Directory;
}

```

## disassembly

```asm
0x1800bbc4c  mov     [rsp-38h+arg_18], rbx
0x1800bbc51  push    rbp
0x1800bbc52  push    rsi
0x1800bbc53  push    rdi
0x1800bbc54  push    r12
0x1800bbc56  push    r13
0x1800bbc58  push    r14
0x1800bbc5a  push    r15
0x1800bbc5c  mov     rbp, rsp
0x1800bbc5f  sub     rsp, 70h
0x1800bbc63  mov     rax, cs:__security_cookie
0x1800bbc6a  xor     rax, rsp
0x1800bbc6d  mov     [rbp+var_10], rax
0x1800bbc71  xor     r13d, r13d
0x1800bbc74  lea     rax, qword_1800E7D10
0x1800bbc7b  mov     [rbp+var_24], r13d
0x1800bbc7f  mov     rsi, r8
0x1800bbc82  mov     [rbp+lpFileName], rax
0x1800bbc86  mov     r14, rdx
0x1800bbc89  mov     [rbp+var_18], r13
0x1800bbc8d  mov     r12, rcx
0x1800bbc90  mov     [rbp+RandomBuffer], r13d
0x1800bbc94  mov     [rbp+var_28], r13d
0x1800bbc98  test    r8, r8
0x1800bbc9b  jz      short loc_1800BBCA0
0x1800bbc9d  mov     [r8], r13
0x1800bbca0  test    r14, r14
0x1800bbca3  jz      loc_1800BBE2F
0x1800bbca9  cmp     [rdx], r13w
0x1800bbcad  jz      loc_1800BBE2F
0x1800bbcb3  test    rsi, rsi
0x1800bbcb6  jnz     short loc_1800BBCC4
0x1800bbcb8  mov     [rbp+var_24], 109h
0x1800bbcbf  jmp     loc_1800BBE36
0x1800bbcc4  mov     rcx, [rcx]; unsigned __int16 *
0x1800bbcc7  call    ?WxCreateDirectory@@YAJPEBG@Z; WxCreateDirectory(ushort const *)
0x1800bbccc  mov     edi, eax
0x1800bbcce  test    eax, eax
0x1800bbcd0  jns     short loc_1800BBCDE
0x1800bbcd2  mov     [rbp+var_24], 10Bh
0x1800bbcd9  jmp     loc_1800BBE3B
0x1800bbcde  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800bbce2  lea     rcx, [rbp+RandomBuffer]; RandomBuffer
0x1800bbce6  lea     edx, [rbx+5]; RandomBufferLength
0x1800bbce9  call    cs:__imp_SystemFunction036
0x1800bbcef  test    al, al
0x1800bbcf1  jnz     short loc_1800BBCFC
0x1800bbcf3  call    cs:__imp_rand
0x1800bbcf9  mov     [rbp+RandomBuffer], eax
0x1800bbcfc  lea     rcx, [rbp+lpFileName]; this
0x1800bbd00  call    ?Empty@CWxString@@QEAAXXZ; CWxString::Empty(void)
0x1800bbd05  mov     r9d, [rbp+RandomBuffer]
0x1800bbd09  lea     rcx, [rbp+lpFileName]; this
0x1800bbd0d  mov     r8, [r12]
0x1800bbd11  lea     rdx, aSUCache; "%s\\%u.cache"
0x1800bbd18  call    ?Format@CWxString@@QEAAJPEBGZZ; CWxString::Format(ushort const *,...)
0x1800bbd1d  mov     edi, eax
0x1800bbd1f  test    eax, eax
0x1800bbd21  js      loc_1800BBE17
0x1800bbd27  mov     rcx, [rbp+lpFileName]; lpFileName
0x1800bbd2b  xor     r9d, r9d; lpSecurityAttributes
0x1800bbd2e  mov     [rsp+70h+hTemplateFile], r13; hTemplateFile
0x1800bbd33  mov     edx, 0C0000000h; dwDesiredAccess
0x1800bbd38  mov     [rsp+70h+dwFlagsAndAttributes], 4; dwFlagsAndAttributes
0x1800bbd40  mov     [rsp+70h+dwCreationDisposition], 1; dwCreationDisposition
0x1800bbd48  lea     r8d, [r9+3]; dwShareMode
0x1800bbd4c  call    cs:__imp_CreateFileW
0x1800bbd52  mov     r15, rax
0x1800bbd55  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800bbd59  jz      short loc_1800BBD64
0x1800bbd5b  mov     rcx, rbx; hObject
0x1800bbd5e  call    cs:__imp_CloseHandle
0x1800bbd64  mov     rbx, r15
0x1800bbd67  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1800bbd6b  jnz     short loc_1800BBD9F
0x1800bbd6d  call    cs:__imp_GetLastError
0x1800bbd73  mov     edi, eax
0x1800bbd75  cmp     eax, 50h ; 'P'
0x1800bbd78  jz      short loc_1800BBD8B
0x1800bbd7a  test    eax, eax
0x1800bbd7c  jle     short loc_1800BBD87
0x1800bbd7e  movzx   edi, ax
0x1800bbd81  or      edi, 80070000h
0x1800bbd87  test    edi, edi
0x1800bbd89  js      short loc_1800BBD93
0x1800bbd8b  inc     [rbp+RandomBuffer]
0x1800bbd8e  jmp     loc_1800BBCFC
0x1800bbd93  mov     [rbp+var_24], 128h
0x1800bbd9a  jmp     loc_1800BBE3B
0x1800bbd9f  lea     r8, [rbp+var_28]
0x1800bbda3  mov     edx, 7FFFFFFFh
0x1800bbda8  mov     rcx, r14
0x1800bbdab  call    WxStringCchLengthDWordW
0x1800bbdb0  mov     edi, eax
0x1800bbdb2  test    eax, eax
0x1800bbdb4  jns     short loc_1800BBDBF
0x1800bbdb6  mov     [rbp+var_24], 12Fh
0x1800bbdbd  jmp     short loc_1800BBE24
0x1800bbdbf  mov     r8d, [rbp+var_28]
0x1800bbdc3  xor     r9d, r9d; lpNumberOfBytesWritten
0x1800bbdc6  add     r8d, r8d; nNumberOfBytesToWrite
0x1800bbdc9  mov     qword ptr [rsp+70h+dwCreationDisposition], r13; lpOverlapped
0x1800bbdce  mov     rdx, r14; lpBuffer
0x1800bbdd1  mov     rcx, r15; hFile
0x1800bbdd4  call    cs:__imp_WriteFile
0x1800bbdda  test    eax, eax
0x1800bbddc  jnz     short loc_1800BBE06
0x1800bbdde  call    cs:__imp_GetLastError
0x1800bbde4  mov     edi, eax
0x1800bbde6  test    eax, eax
0x1800bbde8  jle     short loc_1800BBDF3
0x1800bbdea  movzx   edi, ax
0x1800bbded  or      edi, 80070000h
0x1800bbdf3  test    edi, edi
0x1800bbdf5  mov     [rbp+var_24], 135h
0x1800bbdfc  mov     eax, 8000FFFFh
0x1800bbe01  cmovns  edi, eax
0x1800bbe04  jmp     short loc_1800BBE24
0x1800bbe06  mov     rdx, rsi; unsigned __int16 **
0x1800bbe09  lea     rcx, [rbp+lpFileName]; this
0x1800bbe0d  call    ?Detach@CWxString@@QEAAXPEAPEAG@Z; CWxString::Detach(ushort * *)
0x1800bbe12  mov     edi, r13d
0x1800bbe15  jmp     short loc_1800BBE24
0x1800bbe17  mov     [rbp+var_24], 115h
0x1800bbe1e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800bbe22  jz      short loc_1800BBE3B
0x1800bbe24  mov     rcx, rbx; hObject
0x1800bbe27  call    cs:__imp_CloseHandle
0x1800bbe2d  jmp     short loc_1800BBE3B
0x1800bbe2f  mov     [rbp+var_24], 108h
0x1800bbe36  mov     edi, 80070057h
0x1800bbe3b  lea     rcx, [rbp+lpFileName]; this
0x1800bbe3f  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800bbe44  mov     eax, edi
0x1800bbe46  mov     rcx, [rbp+var_10]
0x1800bbe4a  xor     rcx, rsp; StackCookie
0x1800bbe4d  call    __security_check_cookie
0x1800bbe52  mov     rbx, [rsp+70h+arg_18]
0x1800bbe5a  add     rsp, 70h
0x1800bbe5e  pop     r15
0x1800bbe60  pop     r14
0x1800bbe62  pop     r13
0x1800bbe64  pop     r12
0x1800bbe66  pop     rdi
0x1800bbe67  pop     rsi
0x1800bbe68  pop     rbp
0x1800bbe69  retn
```
