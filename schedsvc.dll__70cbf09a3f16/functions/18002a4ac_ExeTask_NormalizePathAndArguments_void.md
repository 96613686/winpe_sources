# ExeTask::NormalizePathAndArguments(void)

- ea: `0x18002a4ac`
- end: `0x18002a79b`
- name: `?NormalizePathAndArguments@ExeTask@@QEAAJXZ`
- size: `751`
- prototype: `errno_t __fastcall(ExeTask *this)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, reparse_path, service_task`

## callers

- `0x18002a410`
- `0x180072178`

## callees

- `0x18000dc30`
- `0x180019130`
- `0x1800290f0`
- `0x18002a4ac`
- `0x18002a7a4`
- `0x18002a9e0`
- `0x18002aa5c`
- `0x18002ae80`
- `0x1800322a0`
- `0x1800339c0`
- `0x180037e10`
- `0x18007e68a`
- `0x18007e6d0`

## import_xrefs

- `msvcrt!_wsplitpath_s` at `0x18002a558`
- `msvcrt!_wsplitpath_s` at `0x18002a558`
- `msvcrt!wcschr` at `0x18002a68a`
- `msvcrt!wcschr` at `0x18002a68a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002a659`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002a659`

## pseudocode

```c
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
0x18002a4ac  push    rbp
0x18002a4ae  push    rbx
0x18002a4af  push    rsi
0x18002a4b0  push    rdi
0x18002a4b1  push    r12
0x18002a4b3  push    r13
0x18002a4b5  push    r14
0x18002a4b7  push    r15
0x18002a4b9  lea     rbp, [rsp-788h]
0x18002a4c1  sub     rsp, 888h
0x18002a4c8  mov     rax, cs:__security_cookie
0x18002a4cf  xor     rax, rsp
0x18002a4d2  mov     [rbp+7C0h+var_50], rax
0x18002a4d9  mov     r14, rcx
0x18002a4dc  xor     r15d, r15d
0x18002a4df  mov     [rsp+8C0h+var_870], r15d
0x18002a4e4  xor     edx, edx; Val
0x18002a4e6  mov     r8d, 800h; Size
0x18002a4ec  lea     rcx, [rsp+8C0h+Dir]; void *
0x18002a4f1  call    memset_0
0x18002a4f6  mov     rcx, r14; this
0x18002a4f9  call    ?SetRealTarget@ExeTask@@IEAAJXZ; ExeTask::SetRealTarget(void)
0x18002a4fe  mov     ebx, eax
0x18002a500  test    eax, eax
0x18002a502  js      loc_18002A778
0x18002a508  mov     rcx, r14; this
0x18002a50b  call    ?StripQuotes@ExeTask@@IEAAXXZ; ExeTask::StripQuotes(void)
0x18002a510  mov     qword ptr [rsp+8C0h+Drive], r15
0x18002a515  lea     rdi, [r14+30h]
0x18002a519  mov     rax, [rdi]
0x18002a51c  test    rax, rax
0x18002a51f  jz      short loc_18002A526
0x18002a521  mov     rcx, [rax]
0x18002a524  jmp     short loc_18002A529
0x18002a526  mov     rcx, r15; FullPath
0x18002a529  mov     [rsp+8C0h+ExtCount], r15; ExtCount
0x18002a52e  mov     [rsp+8C0h+Ext], r15; Ext
0x18002a533  mov     [rsp+8C0h+FilenameCount], r15; FilenameCount
0x18002a538  mov     [rsp+8C0h+Filename], r15; Filename
0x18002a53d  mov     r13d, 400h
0x18002a543  mov     [rsp+8C0h+DirCount], r13; DirCount
0x18002a548  lea     r9, [rsp+8C0h+Dir]; Dir
0x18002a54d  mov     r8d, 4; DriveCount
0x18002a553  lea     rdx, [rsp+8C0h+Drive]; Drive
0x18002a558  call    cs:__imp__wsplitpath_s
0x18002a55e  test    eax, eax
0x18002a560  jz      short loc_18002A575
0x18002a562  jle     loc_18002A778
0x18002a568  movzx   eax, ax
0x18002a56b  or      eax, 80070000h
0x18002a570  jmp     loc_18002A778
0x18002a575  lea     rdx, [rsp+8C0h+Dir]
0x18002a57a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a57e  mov     rcx, rax
0x18002a581  inc     rcx
0x18002a584  cmp     [rdx+rcx*2], r15w
0x18002a589  jnz     short loc_18002A581
0x18002a58b  test    rcx, rcx
0x18002a58e  jnz     loc_18002A675
0x18002a594  lea     rcx, [rsp+8C0h+Drive]
0x18002a599  inc     rax
0x18002a59c  cmp     [rcx+rax*2], r15w
0x18002a5a1  jnz     short loc_18002A599
0x18002a5a3  test    rax, rax
0x18002a5a6  jnz     loc_18002A675
0x18002a5ac  lea     rsi, [r14+40h]
0x18002a5b0  mov     rcx, rsi; this
0x18002a5b3  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18002a5b8  test    eax, eax
0x18002a5ba  jz      loc_18002A675
0x18002a5c0  mov     rax, [rsi]
0x18002a5c3  test    rax, rax
0x18002a5c6  jz      short loc_18002A5CD
0x18002a5c8  mov     r8, [rax]
0x18002a5cb  jmp     short loc_18002A5D0
0x18002a5cd  mov     r8, r15; unsigned __int16 *
0x18002a5d0  mov     r12d, 105h
0x18002a5d6  mov     edx, r12d; unsigned __int64
0x18002a5d9  lea     rcx, [rsp+8C0h+Dir]; unsigned __int16 *
0x18002a5de  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a5e3  test    eax, eax
0x18002a5e5  js      loc_18002A778
0x18002a5eb  mov     rax, [rsi]
0x18002a5ee  test    rax, rax
0x18002a5f1  jz      short loc_18002A5F8
0x18002a5f3  mov     rbx, [rax]
0x18002a5f6  jmp     short loc_18002A5FB
0x18002a5f8  mov     rbx, r15
0x18002a5fb  mov     rcx, rsi; this
0x18002a5fe  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18002a603  lea     ecx, [rax-1]
0x18002a606  mov     eax, 5Ch ; '\'
0x18002a60b  cmp     ax, [rbx+rcx*2]
0x18002a60f  jz      short loc_18002A62D
0x18002a611  lea     r8, asc_1800A3DA8; "\\"
0x18002a618  mov     rdx, r12; unsigned __int64
0x18002a61b  lea     rcx, [rsp+8C0h+Dir]; unsigned __int16 *
0x18002a620  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a625  test    eax, eax
0x18002a627  js      loc_18002A778
0x18002a62d  mov     rax, [rdi]
0x18002a630  test    rax, rax
0x18002a633  jz      short loc_18002A63A
0x18002a635  mov     r8, [rax]
0x18002a638  jmp     short loc_18002A63D
0x18002a63a  mov     r8, r15; unsigned __int16 *
0x18002a63d  mov     rdx, r12; unsigned __int64
0x18002a640  lea     rcx, [rsp+8C0h+Dir]; unsigned __int16 *
0x18002a645  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a64a  mov     ebx, eax
0x18002a64c  test    eax, eax
0x18002a64e  js      loc_18002A778
0x18002a654  lea     rcx, [rsp+8C0h+Dir]; lpFileName
0x18002a659  call    cs:__imp_GetFileAttributesW
0x18002a65f  cmp     eax, 0FFFFFFFFh
0x18002a662  jz      short loc_18002A675
0x18002a664  test    al, 10h
0x18002a666  jnz     short loc_18002A675
0x18002a668  lea     rdx, [rsp+8C0h+Dir]
0x18002a66d  mov     rcx, rdi
0x18002a670  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18002a675  mov     rax, [rdi]
0x18002a678  test    rax, rax
0x18002a67b  jz      short loc_18002A682
0x18002a67d  mov     rcx, [rax]
0x18002a680  jmp     short loc_18002A685
0x18002a682  mov     rcx, r15; Str
0x18002a685  mov     edx, 20h ; ' '; Ch
0x18002a68a  call    cs:__imp_wcschr
0x18002a690  test    rax, rax
0x18002a693  jnz     short loc_18002A6BA
0x18002a695  cmp     [r14+28h], r15d
0x18002a699  jz      short loc_18002A6BA
0x18002a69b  mov     rax, [rdi]
0x18002a69e  test    rax, rax
0x18002a6a1  jz      short loc_18002A6A8
0x18002a6a3  mov     r8, [rax]
0x18002a6a6  jmp     short loc_18002A6AB
0x18002a6a8  mov     r8, r15; unsigned __int16 *
0x18002a6ab  mov     rdx, r13; unsigned __int64
0x18002a6ae  lea     rcx, [rsp+8C0h+Dir]; unsigned __int16 *
0x18002a6b3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a6b8  jmp     short loc_18002A701
0x18002a6ba  mov     dword ptr [rsp+8C0h+Dir], 22h ; '"'
0x18002a6c2  mov     r8, [rdi]
0x18002a6c5  test    r8, r8
0x18002a6c8  jz      short loc_18002A6CF
0x18002a6ca  mov     r8, [r8]
0x18002a6cd  jmp     short loc_18002A6D2
0x18002a6cf  mov     r8, r15; unsigned __int16 *
0x18002a6d2  mov     rdx, r13; unsigned __int64
0x18002a6d5  lea     rcx, [rsp+8C0h+Dir]; unsigned __int16 *
0x18002a6da  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a6df  test    eax, eax
0x18002a6e1  js      loc_18002A778
0x18002a6e7  lea     r8, asc_1800A48E0; "\""
0x18002a6ee  mov     rdx, r13; unsigned __int64
0x18002a6f1  lea     rcx, [rsp+8C0h+Dir]; unsigned __int16 *
0x18002a6f6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a6fb  mov     ebx, eax
0x18002a6fd  test    eax, eax
0x18002a6ff  js      short loc_18002A778
0x18002a701  lea     rdi, [r14+38h]
0x18002a705  mov     rcx, rdi; this
0x18002a708  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18002a70d  test    eax, eax
0x18002a70f  jz      short loc_18002A769
0x18002a711  lea     r8, asc_1800A48E4; " "
0x18002a718  mov     rdx, r13; unsigned __int64
0x18002a71b  lea     rcx, [rsp+8C0h+Dir]; unsigned __int16 *
0x18002a720  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a725  mov     ebx, eax
0x18002a727  test    eax, eax
0x18002a729  js      short loc_18002A778
0x18002a72b  lea     rdx, [rsp+8C0h+Dir]; unsigned __int16 *
0x18002a730  lea     rcx, [rsp+8C0h+var_868]; this
0x18002a735  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002a73a  mov     [rsp+8C0h+var_870], 1
0x18002a742  mov     rdx, rdi
0x18002a745  lea     rcx, [rsp+8C0h+var_868]
0x18002a74a  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x18002a74f  lea     rdx, [rsp+8C0h+var_868]
0x18002a754  mov     rcx, rdi
0x18002a757  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18002a75c  nop
0x18002a75d  lea     rcx, [rsp+8C0h+var_868]; this
0x18002a762  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18002a767  jmp     short loc_18002A776
0x18002a769  lea     rdx, [rsp+8C0h+Dir]
0x18002a76e  mov     rcx, rdi
0x18002a771  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18002a776  mov     eax, ebx
0x18002a778  mov     rcx, [rbp+7C0h+var_50]
0x18002a77f  xor     rcx, rsp; StackCookie
0x18002a782  call    __security_check_cookie
0x18002a787  add     rsp, 888h
0x18002a78e  pop     r15
0x18002a790  pop     r14
0x18002a792  pop     r13
0x18002a794  pop     r12
0x18002a796  pop     rdi
0x18002a797  pop     rsi
0x18002a798  pop     rbx
0x18002a799  pop     rbp
0x18002a79a  retn
```
