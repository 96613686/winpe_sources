# ExeTask::NormalizePathAndArguments(void)

- ea: `0x18002fc90`
- end: `0x18002ff92`
- name: `?NormalizePathAndArguments@ExeTask@@QEAAJXZ`
- size: `770`
- prototype: `__int64 __fastcall(ExeTask *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, reparse_path, service_task`

## callers

- `0x18002fbf0`
- `0x180075b18`

## callees

- `0x180001e10`
- `0x180011e40`
- `0x18001d130`
- `0x18002fc90`
- `0x18002ff98`
- `0x1800301f0`
- `0x180030620`
- `0x180030d7c`
- `0x180032c30`
- `0x180039fd0`
- `0x18003bd70`
- `0x1800829fa`
- `0x180082a40`

## import_xrefs

- `msvcrt!_wsplitpath_s` at `0x18002fd3c`
- `msvcrt!_wsplitpath_s` at `0x18002fd3c`
- `msvcrt!wcschr` at `0x18002fe7a`
- `msvcrt!wcschr` at `0x18002fe7a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002fe43`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002fe43`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
errno_t __fastcall ExeTask::NormalizePathAndArguments(ExeTask *this)
{
  errno_t result; // eax
  errno_t v3; // ebx
  const unsigned __int16 ***v4; // rdi
  const wchar_t **v5; // rax
  const wchar_t *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx
  const unsigned __int16 ***v9; // rsi
  const unsigned __int16 *v10; // r8
  const unsigned __int16 *v11; // rbx
  const unsigned __int16 *v12; // r8
  DWORD FileAttributesW; // eax
  const wchar_t *v14; // rcx
  const unsigned __int16 *v15; // r8
  const unsigned __int16 *v16; // r8
  _BYTE v17[8]; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t Drive[8]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Dir[1024]; // [rsp+70h] [rbp-90h] BYREF

  memset_0(Dir, 0, sizeof(Dir));
  result = ExeTask::SetRealTarget(this);
  v3 = result;
  if ( result < 0 )
    return result;
  ExeTask::StripQuotes(this);
  *(_QWORD *)Drive = 0;
  v4 = (const unsigned __int16 ***)((char *)this + 48);
  v5 = (const wchar_t **)*((_QWORD *)this + 6);
  if ( v5 )
    v6 = *v5;
  else
    v6 = 0;
  result = _wsplitpath_s(v6, Drive, 4u, Dir, 0x400u, 0, 0, 0, 0);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( Dir[v8] );
  if ( !v8 )
  {
    do
      ++v7;
    while ( Drive[v7] );
    if ( !v7 )
    {
      v9 = (const unsigned __int16 ***)((char *)this + 64);
      if ( _bstr_t::length((ExeTask *)((char *)this + 64)) )
      {
        if ( *v9 )
          v10 = **v9;
        else
          v10 = 0;
        result = StringCchCopyW(Dir, 0x105u, v10);
        if ( result < 0 )
          return result;
        v11 = *v9 ? **v9 : 0LL;
        if ( v11[_bstr_t::length((ExeTask *)((char *)this + 64)) - 1] != 92 )
        {
          result = StringCchCatW(Dir, 0x105u, L"\\");
          if ( result < 0 )
            return result;
        }
        v12 = *v4 ? **v4 : 0LL;
        result = StringCchCatW(Dir, 0x105u, v12);
        v3 = result;
        if ( result < 0 )
          return result;
        FileAttributesW = GetFileAttributesW(Dir);
        if ( FileAttributesW != -1 && (FileAttributesW & 0x10) == 0 )
          _bstr_t::operator=((char *)this + 48, Dir);
      }
    }
  }
  if ( *v4 )
    v14 = **v4;
  else
    v14 = 0;
  if ( wcschr(v14, 0x20u) || !*((_DWORD *)this + 10) )
  {
    wcscpy(Dir, L"\"");
    if ( *v4 )
      v16 = **v4;
    else
      v16 = 0;
    result = StringCchCatW(Dir, 0x400u, v16);
    if ( result < 0 )
      return result;
    result = StringCchCatW(Dir, 0x400u, L"\"");
    v3 = result;
    if ( result < 0 )
      return result;
  }
  else
  {
    if ( *v4 )
      v15 = **v4;
    else
      v15 = 0;
    StringCchCopyW(Dir, 0x400u, v15);
  }
  if ( _bstr_t::length((ExeTask *)((char *)this + 56)) )
  {
    result = StringCchCatW(Dir, 0x400u, L" ");
    v3 = result;
    if ( result < 0 )
      return result;
    _bstr_t::_bstr_t((_bstr_t *)v17, Dir);
    _bstr_t::operator+=(v17, (char *)this + 56);
    _bstr_t::operator=((char *)this + 56, v17);
    _bstr_t::~_bstr_t((_bstr_t *)v17);
  }
  else
  {
    _bstr_t::operator=((char *)this + 56, Dir);
  }
  return v3;
}

```

## disassembly

```asm
0x18002fc90  push    rbp
0x18002fc92  push    rbx
0x18002fc93  push    rsi
0x18002fc94  push    rdi
0x18002fc95  push    r12
0x18002fc97  push    r13
0x18002fc99  push    r14
0x18002fc9b  push    r15
0x18002fc9d  lea     rbp, [rsp-788h]
0x18002fca5  sub     rsp, 888h
0x18002fcac  mov     rax, cs:__security_cookie
0x18002fcb3  xor     rax, rsp
0x18002fcb6  mov     [rbp+7C0h+var_50], rax
0x18002fcbd  mov     r14, rcx
0x18002fcc0  xor     r15d, r15d
0x18002fcc3  mov     [rsp+8C0h+var_870], r15d
0x18002fcc8  xor     edx, edx; Val
0x18002fcca  mov     r8d, 800h; Size
0x18002fcd0  lea     rcx, [rsp+8C0h+Dir]; void *
0x18002fcd5  call    memset_0
0x18002fcda  mov     rcx, r14; this
0x18002fcdd  call    ?SetRealTarget@ExeTask@@IEAAJXZ; ExeTask::SetRealTarget(void)
0x18002fce2  mov     ebx, eax
0x18002fce4  test    eax, eax
0x18002fce6  js      loc_18002FF6E
0x18002fcec  mov     rcx, r14; this
0x18002fcef  call    ?StripQuotes@ExeTask@@IEAAXXZ; ExeTask::StripQuotes(void)
0x18002fcf4  mov     qword ptr [rsp+8C0h+Drive], r15
0x18002fcf9  lea     rdi, [r14+30h]
0x18002fcfd  mov     rax, [rdi]
0x18002fd00  test    rax, rax
0x18002fd03  jz      short loc_18002FD0A
0x18002fd05  mov     rcx, [rax]
0x18002fd08  jmp     short loc_18002FD0D
0x18002fd0a  mov     rcx, r15; FullPath
0x18002fd0d  mov     [rsp+8C0h+ExtCount], r15; ExtCount
0x18002fd12  mov     [rsp+8C0h+Ext], r15; Ext
0x18002fd17  mov     [rsp+8C0h+FilenameCount], r15; FilenameCount
0x18002fd1c  mov     [rsp+8C0h+Filename], r15; Filename
0x18002fd21  mov     r13d, 400h
0x18002fd27  mov     [rsp+8C0h+DirCount], r13; DirCount
0x18002fd2c  lea     r9, [rsp+8C0h+Dir]; Dir
0x18002fd31  mov     r8d, 4; DriveCount
0x18002fd37  lea     rdx, [rsp+8C0h+Drive]; Drive
0x18002fd3c  call    cs:__imp__wsplitpath_s
0x18002fd43  nop     dword ptr [rax+rax+00h]
0x18002fd48  test    eax, eax
0x18002fd4a  jz      short loc_18002FD5F
0x18002fd4c  jle     loc_18002FF6E
0x18002fd52  movzx   eax, ax
0x18002fd55  or      eax, 80070000h
0x18002fd5a  jmp     loc_18002FF6E
0x18002fd5f  lea     rdx, [rsp+8C0h+Dir]
0x18002fd64  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002fd68  mov     rcx, rax
0x18002fd6b  inc     rcx
0x18002fd6e  cmp     [rdx+rcx*2], r15w
0x18002fd73  jnz     short loc_18002FD6B
0x18002fd75  test    rcx, rcx
0x18002fd78  jnz     loc_18002FE65
0x18002fd7e  lea     rcx, [rsp+8C0h+Drive]
0x18002fd83  inc     rax
0x18002fd86  cmp     [rcx+rax*2], r15w
0x18002fd8b  jnz     short loc_18002FD83
0x18002fd8d  test    rax, rax
0x18002fd90  jnz     loc_18002FE65
0x18002fd96  lea     rsi, [r14+40h]
0x18002fd9a  mov     rcx, rsi; this
0x18002fd9d  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18002fda2  test    eax, eax
0x18002fda4  jz      loc_18002FE65
0x18002fdaa  mov     rax, [rsi]
0x18002fdad  test    rax, rax
0x18002fdb0  jz      short loc_18002FDB7
0x18002fdb2  mov     r8, [rax]
0x18002fdb5  jmp     short loc_18002FDBA
0x18002fdb7  mov     r8, r15; unsigned __int16 *
0x18002fdba  mov     r12d, 105h
0x18002fdc0  mov     edx, r12d; unsigned __int64
0x18002fdc3  lea     rcx, [rsp+8C0h+Dir]; unsigned __int16 *
0x18002fdc8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002fdcd  test    eax, eax
0x18002fdcf  js      loc_18002FF6E
0x18002fdd5  mov     rax, [rsi]
0x18002fdd8  test    rax, rax
0x18002fddb  jz      short loc_18002FDE2
0x18002fddd  mov     rbx, [rax]
0x18002fde0  jmp     short loc_18002FDE5
0x18002fde2  mov     rbx, r15
0x18002fde5  mov     rcx, rsi; this
0x18002fde8  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18002fded  lea     ecx, [rax-1]
0x18002fdf0  mov     eax, 5Ch ; '\'
0x18002fdf5  cmp     ax, [rbx+rcx*2]
0x18002fdf9  jz      short loc_18002FE17
0x18002fdfb  lea     r8, asc_1800A7EC0; "\\"
0x18002fe02  mov     rdx, r12; unsigned __int64
0x18002fe05  lea     rcx, [rsp+8C0h+Dir]; unsigned __int16 *
0x18002fe0a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002fe0f  test    eax, eax
0x18002fe11  js      loc_18002FF6E
0x18002fe17  mov     rax, [rdi]
0x18002fe1a  test    rax, rax
0x18002fe1d  jz      short loc_18002FE24
0x18002fe1f  mov     r8, [rax]
0x18002fe22  jmp     short loc_18002FE27
0x18002fe24  mov     r8, r15; unsigned __int16 *
0x18002fe27  mov     rdx, r12; unsigned __int64
0x18002fe2a  lea     rcx, [rsp+8C0h+Dir]; unsigned __int16 *
0x18002fe2f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002fe34  mov     ebx, eax
0x18002fe36  test    eax, eax
0x18002fe38  js      loc_18002FF6E
0x18002fe3e  lea     rcx, [rsp+8C0h+Dir]; lpFileName
0x18002fe43  call    cs:__imp_GetFileAttributesW
0x18002fe4a  nop     dword ptr [rax+rax+00h]
0x18002fe4f  cmp     eax, 0FFFFFFFFh
0x18002fe52  jz      short loc_18002FE65
0x18002fe54  test    al, 10h
0x18002fe56  jnz     short loc_18002FE65
0x18002fe58  lea     rdx, [rsp+8C0h+Dir]
0x18002fe5d  mov     rcx, rdi
0x18002fe60  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18002fe65  mov     rax, [rdi]
0x18002fe68  test    rax, rax
0x18002fe6b  jz      short loc_18002FE72
0x18002fe6d  mov     rcx, [rax]
0x18002fe70  jmp     short loc_18002FE75
0x18002fe72  mov     rcx, r15; Str
0x18002fe75  mov     edx, 20h ; ' '; Ch
0x18002fe7a  call    cs:__imp_wcschr
0x18002fe81  nop     dword ptr [rax+rax+00h]
0x18002fe86  test    rax, rax
0x18002fe89  jnz     short loc_18002FEB0
0x18002fe8b  cmp     [r14+28h], r15d
0x18002fe8f  jz      short loc_18002FEB0
0x18002fe91  mov     rax, [rdi]
0x18002fe94  test    rax, rax
0x18002fe97  jz      short loc_18002FE9E
0x18002fe99  mov     r8, [rax]
0x18002fe9c  jmp     short loc_18002FEA1
0x18002fe9e  mov     r8, r15; unsigned __int16 *
0x18002fea1  mov     rdx, r13; unsigned __int64
0x18002fea4  lea     rcx, [rsp+8C0h+Dir]; unsigned __int16 *
0x18002fea9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002feae  jmp     short loc_18002FEF7
0x18002feb0  mov     dword ptr [rsp+8C0h+Dir], 22h ; '"'
0x18002feb8  mov     r8, [rdi]
0x18002febb  test    r8, r8
0x18002febe  jz      short loc_18002FEC5
0x18002fec0  mov     r8, [r8]
0x18002fec3  jmp     short loc_18002FEC8
0x18002fec5  mov     r8, r15; unsigned __int16 *
0x18002fec8  mov     rdx, r13; unsigned __int64
0x18002fecb  lea     rcx, [rsp+8C0h+Dir]; unsigned __int16 *
0x18002fed0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002fed5  test    eax, eax
0x18002fed7  js      loc_18002FF6E
0x18002fedd  lea     r8, asc_1800A88F0; "\""
0x18002fee4  mov     rdx, r13; unsigned __int64
0x18002fee7  lea     rcx, [rsp+8C0h+Dir]; unsigned __int16 *
0x18002feec  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002fef1  mov     ebx, eax
0x18002fef3  test    eax, eax
0x18002fef5  js      short loc_18002FF6E
0x18002fef7  lea     rdi, [r14+38h]
0x18002fefb  mov     rcx, rdi; this
0x18002fefe  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18002ff03  test    eax, eax
0x18002ff05  jz      short loc_18002FF5F
0x18002ff07  lea     r8, asc_1800A88F4; " "
0x18002ff0e  mov     rdx, r13; unsigned __int64
0x18002ff11  lea     rcx, [rsp+8C0h+Dir]; unsigned __int16 *
0x18002ff16  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002ff1b  mov     ebx, eax
0x18002ff1d  test    eax, eax
0x18002ff1f  js      short loc_18002FF6E
0x18002ff21  lea     rdx, [rsp+8C0h+Dir]; unsigned __int16 *
0x18002ff26  lea     rcx, [rsp+8C0h+var_868]; this
0x18002ff2b  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002ff30  mov     [rsp+8C0h+var_870], 1
0x18002ff38  mov     rdx, rdi
0x18002ff3b  lea     rcx, [rsp+8C0h+var_868]
0x18002ff40  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x18002ff45  lea     rdx, [rsp+8C0h+var_868]
0x18002ff4a  mov     rcx, rdi
0x18002ff4d  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18002ff52  nop
0x18002ff53  lea     rcx, [rsp+8C0h+var_868]; this
0x18002ff58  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18002ff5d  jmp     short loc_18002FF6C
0x18002ff5f  lea     rdx, [rsp+8C0h+Dir]
0x18002ff64  mov     rcx, rdi
0x18002ff67  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18002ff6c  mov     eax, ebx
0x18002ff6e  mov     rcx, [rbp+7C0h+var_50]
0x18002ff75  xor     rcx, rsp; StackCookie
0x18002ff78  call    __security_check_cookie
0x18002ff7d  add     rsp, 888h
0x18002ff84  pop     r15
0x18002ff86  pop     r14
0x18002ff88  pop     r13
0x18002ff8a  pop     r12
0x18002ff8c  pop     rdi
0x18002ff8d  pop     rsi
0x18002ff8e  pop     rbx
0x18002ff8f  pop     rbp
0x18002ff90  retn
```
