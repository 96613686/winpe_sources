# CDVRRingBufferWriter::ASF_MULTI_FILE_RECORDER_NODE::AddFile(ushort const *,ulong,unsigned __int64,unsigned __int64,__int64)

- ea: `0x180069ee0`
- end: `0x18006a231`
- name: `?AddFile@ASF_MULTI_FILE_RECORDER_NODE@CDVRRingBufferWriter@@QEAAJPEBGK_K1_J@Z`
- size: `849`
- prototype: `__int64 __fastcall(CDVRRingBufferWriter::ASF_MULTI_FILE_RECORDER_NODE *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int64, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callers

- `0x18006bd70`

## callees

- `0x1800017e0`
- `0x1800017ec`
- `0x180001c00`
- `0x18000262c`
- `0x180069ee0`
- `0x180072028`
- `0x180074ec4`
- `0x180076948`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18006a075`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18006a075`
- `KERNEL32!GetLastError` at `0x180069fbe`
- `KERNEL32!GetLastError` at `0x18006a046`
- `KERNEL32!GetLastError` at `0x18006a184`
- `KERNEL32!GetLastError` at `0x180069fbe`
- `KERNEL32!GetLastError` at `0x18006a046`
- `KERNEL32!GetLastError` at `0x18006a184`
- `KERNEL32!CreateHardLinkW` at `0x18006a0f9`
- `KERNEL32!CreateHardLinkW` at `0x18006a0f9`
- `KERNEL32!DeleteFileW` at `0x18006a1d7`
- `KERNEL32!DeleteFileW` at `0x1800b3e89`
- `KERNEL32!DeleteFileW` at `0x18006a1d7`
- `KERNEL32!DeleteFileW` at `0x1800b3e89`
- `KERNEL32!GetFullPathNameW` at `0x180069fb2`
- `KERNEL32!GetFullPathNameW` at `0x18006a03c`
- `KERNEL32!GetFullPathNameW` at `0x180069fb2`
- `KERNEL32!GetFullPathNameW` at `0x18006a03c`

## pseudocode

```c
__int64 __fastcall CDVRRingBufferWriter::ASF_MULTI_FILE_RECORDER_NODE::AddFile(
        CDVRFileCollection **this,
        const unsigned __int16 *a2,
        int a3,
        unsigned __int64 a4,
        unsigned __int64 a5,
        __int64 a6)
{
  unsigned __int64 v6; // rsi
  int v7; // r15d
  int v9; // r12d
  int v10; // r14d
  unsigned __int64 v11; // rdx
  int v12; // ebx
  DWORD FullPathNameW; // eax
  DWORD v14; // ebx
  signed int LastError; // eax
  unsigned __int64 v16; // rsi
  wchar_t *v17; // rax
  DWORD v18; // eax
  signed int v19; // eax
  wchar_t *v20; // rax
  wchar_t *v21; // r15
  size_t v22; // rsi
  signed int v23; // eax
  __int64 v24; // rdx
  unsigned int v26; // [rsp+A4h] [rbp-8Ch] BYREF
  unsigned __int64 v27; // [rsp+A8h] [rbp-88h]
  int v28; // [rsp+B0h] [rbp-80h]
  CDVRRingBufferWriter::ASF_MULTI_FILE_RECORDER_NODE *v29; // [rsp+B8h] [rbp-78h]
  LPCWSTR lpExistingFileName; // [rsp+C0h] [rbp-70h]
  unsigned __int64 v31; // [rsp+C8h] [rbp-68h]
  wchar_t *Str; // [rsp+D0h] [rbp-60h] BYREF
  LPWSTR FilePart; // [rsp+D8h] [rbp-58h] BYREF
  WCHAR Buffer[2]; // [rsp+E0h] [rbp-50h] BYREF
  unsigned int v35; // [rsp+E4h] [rbp-4Ch] BYREF

  v6 = a4;
  v27 = a4;
  v7 = a3;
  lpExistingFileName = a2;
  v29 = (CDVRRingBufferWriter::ASF_MULTI_FILE_RECORDER_NODE *)this;
  v31 = a4;
  v35 = 0;
  Str = 0;
  v9 = 0;
  v26 = 0;
  v28 = 0;
  v10 = 1;
  v12 = CDVRFileCollection::Lock(this[1], this + 4, &v26, 30, 1);
  v28 = 1;
  if ( v12 < 0 )
  {
    v10 = 0;
    goto LABEL_33;
  }
  Buffer[0] = 0;
  FilePart = 0;
  FullPathNameW = GetFullPathNameW(*((LPCWSTR *)this[2] + 7), 0, Buffer, 0);
  v14 = FullPathNameW;
  if ( !FullPathNameW )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    if ( v12 >= 0 )
      v12 = -2147467259;
    goto LABEL_33;
  }
  v16 = FullPathNameW + 16;
  v17 = (wchar_t *)operator new[](saturated_mul(v16, 2u));
  Str = v17;
  if ( !v17 )
  {
    v12 = -2147024882;
    goto LABEL_32;
  }
  v18 = GetFullPathNameW(*((LPCWSTR *)this[2] + 7), v14 + 1, v17, &FilePart);
  if ( !v18 )
  {
    v19 = GetLastError();
    v12 = v19;
    if ( v19 > 0 )
      v12 = (unsigned __int16)v19 | 0x80070000;
    goto LABEL_32;
  }
  if ( v18 > v14 )
  {
    v12 = -2147467259;
LABEL_32:
    v6 = v27;
    goto LABEL_33;
  }
  v20 = wcsrchr(Str, 0x2Eu);
  v21 = v20;
  if ( v20 && v20 >= FilePart )
  {
    v22 = v16 - (v20 - Str);
  }
  else
  {
    v22 = -1;
    do
      ++v22;
    while ( Str[v22] );
    v21 = &Str[v22];
  }
  while ( 1 )
  {
    if ( !*((_DWORD *)this + 6) )
    {
      v12 = -2147467259;
LABEL_31:
      v7 = a3;
      goto LABEL_32;
    }
    swprintf_s(v21, v22, L"_%d.sbe");
    ++*((_DWORD *)this + 6);
    if ( CreateHardLinkW(Str, lpExistingFileName, 0) )
      break;
    v23 = GetLastError();
    v12 = v23;
    if ( v23 != 183 )
    {
      if ( v23 > 0 )
        v12 = (unsigned __int16)v23 | 0x80070000;
      goto LABEL_31;
    }
  }
  v9 = 1;
  v6 = v27;
  v12 = CDVRFileCollection::AddFile(
          this[1],
          (const struct CDVRFileCollection::CClientInfo *)(this + 4),
          (LPCWSTR *)&Str,
          1u,
          v27,
          a5,
          1,
          0,
          a6,
          &v35);
  if ( v12 >= 0 )
  {
    v9 = 0;
    v12 = 0;
  }
  v7 = a3;
LABEL_33:
  if ( v12 >= 0 )
  {
    *((_DWORD *)this + 16) = v7;
    *((_DWORD *)this + 17) = v35;
    *this = (CDVRFileCollection *)v6;
  }
  if ( v9 )
  {
    DeleteFileW(Str);
    --*((_DWORD *)this + 6);
  }
  operator delete(Str, v11);
  CDVRFileCollection::Unlock(this[1], v24, v26, 30, v10);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180069ee0  mov     r11, rsp
0x180069ee3  mov     [r11+18h], r8d
0x180069ee7  push    rbx
0x180069ee8  push    rsi
0x180069ee9  push    rdi
0x180069eea  push    r12
0x180069eec  push    r13
0x180069eee  push    r14
0x180069ef0  push    r15
0x180069ef2  sub     rsp, 0B0h
0x180069ef9  mov     rax, cs:__security_cookie
0x180069f00  xor     rax, rsp
0x180069f03  mov     [rsp+0E8h+var_48], rax
0x180069f0b  mov     rsi, r9
0x180069f0e  mov     [rsp+0E8h+var_88], r9
0x180069f13  mov     r15d, r8d
0x180069f16  mov     [rsp+0E8h+lpExistingFileName], rdx
0x180069f1b  mov     rdi, rcx
0x180069f1e  mov     [rsp+0E8h+var_78], rcx
0x180069f23  mov     [rsp+0E8h+var_68], r9
0x180069f2b  xor     ecx, ecx
0x180069f2d  mov     [rsp+0E8h+var_98], ecx
0x180069f31  mov     [r11-4Ch], ecx
0x180069f35  mov     [r11-60h], rcx
0x180069f39  mov     r12d, ecx
0x180069f3c  mov     [rsp+0E8h+var_94], ecx
0x180069f40  mov     [rsp+0E8h+var_8C], ecx
0x180069f44  mov     [rsp+0E8h+var_80], ecx
0x180069f48  mov     [rsp+0E8h+var_90], ecx
0x180069f4c  lea     r14d, [rcx+1]
0x180069f50  mov     dword ptr [rsp+0E8h+var_C8], r14d
0x180069f55  lea     r9d, [rcx+1Eh]
0x180069f59  lea     r8, [rsp+0E8h+var_8C]
0x180069f5e  lea     rdx, [rdi+20h]
0x180069f62  mov     rcx, [rdi+8]
0x180069f66  call    ?Lock@CDVRFileCollection@@QEAAJPEBUCClientInfo@1@AEAHW4DVRFILECOLLECTIONCALLER@@H@Z; CDVRFileCollection::Lock(CDVRFileCollection::CClientInfo const *,int &,DVRFILECOLLECTIONCALLER,int)
0x180069f6b  mov     ebx, eax
0x180069f6d  mov     [rsp+0E8h+var_80], r14d
0x180069f72  xor     ecx, ecx
0x180069f74  test    eax, eax
0x180069f76  jns     short loc_180069F88
0x180069f78  mov     [rsp+0E8h+var_98], eax
0x180069f7c  mov     r14d, ecx
0x180069f7f  mov     [rsp+0E8h+var_90], ecx
0x180069f83  jmp     loc_18006A1B5
0x180069f88  mov     [rsp+0E8h+var_90], r14d
0x180069f8d  mov     [rsp+0E8h+Buffer], cx
0x180069f95  mov     [rsp+0E8h+FilePart], rcx
0x180069f9d  mov     rcx, [rdi+10h]
0x180069fa1  xor     r9d, r9d; lpFilePart
0x180069fa4  lea     r8, [rsp+0E8h+Buffer]; lpBuffer
0x180069fac  xor     edx, edx; nBufferLength
0x180069fae  mov     rcx, [rcx+38h]; lpFileName
0x180069fb2  call    cs:__imp_GetFullPathNameW
0x180069fb8  mov     ebx, eax
0x180069fba  test    eax, eax
0x180069fbc  jnz     short loc_180069FED
0x180069fbe  call    cs:__imp_GetLastError
0x180069fc4  mov     ebx, eax
0x180069fc6  test    eax, eax
0x180069fc8  jle     short loc_180069FD3
0x180069fca  movzx   ebx, ax
0x180069fcd  or      ebx, 80070000h
0x180069fd3  mov     [rsp+0E8h+var_98], ebx
0x180069fd7  test    ebx, ebx
0x180069fd9  js      loc_18006A1B5
0x180069fdf  mov     ebx, 80004005h
0x180069fe4  mov     [rsp+0E8h+var_98], ebx
0x180069fe8  jmp     loc_18006A1B5
0x180069fed  lea     esi, [rax+10h]
0x180069ff0  mov     eax, 2
0x180069ff5  mul     rsi
0x180069ff8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180069fff  cmovb   rax, rcx
0x18006a003  mov     rcx, rax; unsigned __int64
0x18006a006  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006a00b  mov     [rsp+0E8h+Str], rax
0x18006a013  test    rax, rax
0x18006a016  jnz     short loc_18006A026
0x18006a018  mov     ebx, 8007000Eh
0x18006a01d  mov     [rsp+0E8h+var_98], ebx
0x18006a021  jmp     loc_18006A1B0
0x18006a026  lea     edx, [rbx+1]; nBufferLength
0x18006a029  mov     rcx, [rdi+10h]
0x18006a02d  lea     r9, [rsp+0E8h+FilePart]; lpFilePart
0x18006a035  mov     r8, rax; lpBuffer
0x18006a038  mov     rcx, [rcx+38h]; lpFileName
0x18006a03c  call    cs:__imp_GetFullPathNameW
0x18006a042  test    eax, eax
0x18006a044  jnz     short loc_18006A05D
0x18006a046  call    cs:__imp_GetLastError
0x18006a04c  mov     ebx, eax
0x18006a04e  test    eax, eax
0x18006a050  jle     short loc_18006A01D
0x18006a052  movzx   ebx, ax
0x18006a055  or      ebx, 80070000h
0x18006a05b  jmp     short loc_18006A01D
0x18006a05d  cmp     eax, ebx
0x18006a05f  jbe     short loc_18006A068
0x18006a061  mov     ebx, 80004005h
0x18006a066  jmp     short loc_18006A01D
0x18006a068  mov     edx, 2Eh ; '.'; Ch
0x18006a06d  mov     rcx, [rsp+0E8h+Str]; Str
0x18006a075  call    cs:__imp_wcsrchr
0x18006a07b  mov     r15, rax
0x18006a07e  xor     ecx, ecx
0x18006a080  test    rax, rax
0x18006a083  jz      short loc_18006A09F
0x18006a085  cmp     rax, [rsp+0E8h+FilePart]
0x18006a08d  jb      short loc_18006A09F
0x18006a08f  sub     rax, [rsp+0E8h+Str]
0x18006a097  sar     rax, 1
0x18006a09a  sub     rsi, rax
0x18006a09d  jmp     short loc_18006A0C0
0x18006a09f  mov     rax, [rsp+0E8h+Str]
0x18006a0a7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006a0ab  inc     rsi
0x18006a0ae  cmp     [rax+rsi*2], cx
0x18006a0b2  jnz     short loc_18006A0AB
0x18006a0b4  mov     rax, [rsp+0E8h+Str]
0x18006a0bc  lea     r15, [rax+rsi*2]
0x18006a0c0  mov     r9d, [rdi+18h]
0x18006a0c4  test    r9d, r9d
0x18006a0c7  jnz     short loc_18006A0D3
0x18006a0c9  mov     ebx, 80004005h
0x18006a0ce  jmp     loc_18006A1A4
0x18006a0d3  lea     r8, aDSbe; "_%d.sbe"
0x18006a0da  mov     rdx, rsi; BufferCount
0x18006a0dd  mov     rcx, r15; Buffer
0x18006a0e0  call    swprintf_s
0x18006a0e5  add     [rdi+18h], r14d
0x18006a0e9  xor     r8d, r8d; lpSecurityAttributes
0x18006a0ec  mov     rdx, [rsp+0E8h+lpExistingFileName]; lpExistingFileName
0x18006a0f1  mov     rcx, [rsp+0E8h+Str]; lpFileName
0x18006a0f9  call    cs:__imp_CreateHardLinkW
0x18006a0ff  xor     ecx, ecx
0x18006a101  test    eax, eax
0x18006a103  jz      short loc_18006A184
0x18006a105  mov     r12d, r14d
0x18006a108  mov     [rsp+0E8h+var_94], r14d
0x18006a10d  lea     rax, [rsp+0E8h+var_4C]
0x18006a115  mov     [rsp+0E8h+var_A0], rax; unsigned int *
0x18006a11a  mov     rax, [rsp+0E8h+arg_28]
0x18006a122  mov     [rsp+0E8h+var_A8], rax; __int64
0x18006a127  mov     [rsp+0E8h+var_B0], ecx; int
0x18006a12b  mov     [rsp+0E8h+var_B8], r14d; int
0x18006a130  mov     rax, [rsp+0E8h+arg_20]
0x18006a138  mov     [rsp+0E8h+var_C0], rax; unsigned __int64
0x18006a13d  mov     rsi, [rsp+0E8h+var_88]
0x18006a142  mov     [rsp+0E8h+var_C8], rsi; unsigned __int64
0x18006a147  mov     r9d, r14d; int
0x18006a14a  lea     r8, [rsp+0E8h+Str]; unsigned __int16 **
0x18006a152  lea     rdx, [rdi+20h]; struct CDVRFileCollection::CClientInfo *
0x18006a156  mov     rcx, [rdi+8]; this
0x18006a15a  call    ?AddFile@CDVRFileCollection@@QEAAJPEBUCClientInfo@1@PEAPEAGH_K2HH_JPEAK@Z; CDVRFileCollection::AddFile(CDVRFileCollection::CClientInfo const *,ushort * *,int,unsigned __int64,unsigned __int64,int,int,__int64,ulong *)
0x18006a15f  mov     ebx, eax
0x18006a161  xor     ecx, ecx
0x18006a163  test    eax, eax
0x18006a165  jns     short loc_18006A175
0x18006a167  mov     [rsp+0E8h+var_98], eax
0x18006a16b  mov     r15d, [rsp+0E8h+arg_10]
0x18006a173  jmp     short loc_18006A1B5
0x18006a175  mov     r12d, ecx
0x18006a178  mov     [rsp+0E8h+var_94], ecx
0x18006a17c  mov     ebx, ecx
0x18006a17e  mov     [rsp+0E8h+var_98], ecx
0x18006a182  jmp     short loc_18006A16B
0x18006a184  call    cs:__imp_GetLastError
0x18006a18a  mov     ebx, eax
0x18006a18c  cmp     eax, 0B7h
0x18006a191  jz      loc_18006A22B
0x18006a197  test    eax, eax
0x18006a199  jle     short loc_18006A1A4
0x18006a19b  movzx   ebx, ax
0x18006a19e  or      ebx, 80070000h
0x18006a1a4  mov     [rsp+0E8h+var_98], ebx
0x18006a1a8  mov     r15d, [rsp+0E8h+arg_10]
0x18006a1b0  mov     rsi, [rsp+0E8h+var_88]
0x18006a1b5  test    ebx, ebx
0x18006a1b7  js      short loc_18006A1CA
0x18006a1b9  mov     [rdi+40h], r15d
0x18006a1bd  mov     eax, [rsp+0E8h+var_4C]
0x18006a1c4  mov     [rdi+44h], eax
0x18006a1c7  mov     [rdi], rsi
0x18006a1ca  test    r12d, r12d
0x18006a1cd  jz      short loc_18006A1E0
0x18006a1cf  mov     rcx, [rsp+0E8h+Str]; lpFileName
0x18006a1d7  call    cs:__imp_DeleteFileW
0x18006a1dd  dec     dword ptr [rdi+18h]
0x18006a1e0  mov     rcx, [rsp+0E8h+Str]; void *
0x18006a1e8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006a1ed  mov     dword ptr [rsp+0E8h+var_C8], r14d
0x18006a1f2  mov     r9d, 1Eh
0x18006a1f8  mov     r8d, [rsp+0E8h+var_8C]
0x18006a1fd  mov     rcx, [rdi+8]
0x18006a201  call    ?Unlock@CDVRFileCollection@@QEAAJPEBUCClientInfo@1@HW4DVRFILECOLLECTIONCALLER@@H@Z; CDVRFileCollection::Unlock(CDVRFileCollection::CClientInfo const *,int,DVRFILECOLLECTIONCALLER,int)
0x18006a206  mov     eax, ebx
0x18006a208  mov     rcx, [rsp+0E8h+var_48]
0x18006a210  xor     rcx, rsp; StackCookie
0x18006a213  call    __security_check_cookie
0x18006a218  add     rsp, 0B0h
0x18006a21f  pop     r15
0x18006a221  pop     r14
0x18006a223  pop     r13
0x18006a225  pop     r12
0x18006a227  pop     rdi
0x18006a228  pop     rsi
0x18006a229  pop     rbx
0x18006a22a  retn
0x18006a22b  jmp     loc_18006A0C0
0x1800b3e4c  push    rbx
0x1800b3e4e  push    rbp
0x1800b3e4f  sub     rsp, 58h
0x1800b3e53  mov     rbp, rdx
0x1800b3e56  mov     rbx, [rbp+70h]
0x1800b3e5a  cmp     dword ptr [rbp+50h], 0
0x1800b3e5e  jl      short loc_1800B3E7C
0x1800b3e60  mov     eax, [rbp+100h]
0x1800b3e66  mov     [rbx+40h], eax
0x1800b3e69  mov     eax, [rbp+9Ch]
0x1800b3e6f  mov     [rbx+44h], eax
0x1800b3e72  mov     rax, [rbp+80h]
0x1800b3e79  mov     [rbx], rax
0x1800b3e7c  cmp     dword ptr [rbp+54h], 0
0x1800b3e80  jz      short loc_1800B3E97
0x1800b3e82  mov     rcx, [rbp+88h]; lpFileName
0x1800b3e89  call    cs:__imp_DeleteFileW
0x1800b3e8f  mov     eax, [rbx+18h]
0x1800b3e92  dec     eax
0x1800b3e94  mov     [rbx+18h], eax
0x1800b3e97  mov     rcx, [rbp+88h]; void *
0x1800b3e9e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b3ea3  cmp     dword ptr [rbp+68h], 0
0x1800b3ea7  jz      short loc_1800B3EC4
0x1800b3ea9  mov     eax, [rbp+58h]
0x1800b3eac  mov     dword ptr [rsp+68h+var_48], eax
0x1800b3eb0  mov     r9d, 1Eh
0x1800b3eb6  mov     r8d, [rbp+5Ch]
0x1800b3eba  mov     rcx, [rbx+8]
0x1800b3ebe  call    ?Unlock@CDVRFileCollection@@QEAAJPEBUCClientInfo@1@HW4DVRFILECOLLECTIONCALLER@@H@Z; CDVRFileCollection::Unlock(CDVRFileCollection::CClientInfo const *,int,DVRFILECOLLECTIONCALLER,int)
0x1800b3ec3  nop
0x1800b3ec4  add     rsp, 58h
0x1800b3ec8  pop     rbp
0x1800b3ec9  pop     rbx
0x1800b3eca  retn
```
