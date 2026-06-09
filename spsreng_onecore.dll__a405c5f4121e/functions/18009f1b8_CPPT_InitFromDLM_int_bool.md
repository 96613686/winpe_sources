# CPPT::InitFromDLM(int,bool)

- ea: `0x18009f1b8`
- end: `0x18009f356`
- name: `?InitFromDLM@CPPT@@QEAAJH_N@Z`
- size: `414`
- prototype: `__int64 __fastcall(CPPT *__hidden this, int, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180098e60`
- `0x180099390`

## callees

- `0x180002470`
- `0x1800034b0`
- `0x18009f17c`
- `0x18009f1b8`
- `0x18009f420`
- `0x1800c77ac`
- `0x1800e3c18`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18009f2d5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18009f2d5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18009f2e7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18009f2e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPPT::InitFromDLM(const unsigned __int16 **this, int a2)
{
  CSequentialReadFile *v4; // rax
  int v5; // r8d
  CSequentialReadFile *v6; // rbx
  int v7; // r8d
  int v8; // edi
  int v9; // r8d
  void **v11; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+38h] [rbp-C8h]
  unsigned int v13; // [rsp+40h] [rbp-C0h]
  __int16 v14; // [rsp+48h] [rbp-B8h] BYREF

  v4 = (CSequentialReadFile *)CWinHeap::Alloc(&g_heap, 0x28u, 0);
  v6 = v4;
  if ( !v4 )
    return (unsigned int)-2147024882;
  *((_QWORD *)v4 + 1) = 0;
  *((_QWORD *)v4 + 2) = 0;
  *((_DWORD *)v4 + 6) = 0;
  *(_QWORD *)v4 = &CSequentialReadFile::`vftable';
  *((_QWORD *)v4 + 4) = 0;
  if ( CSequentialReadFile::Open(v4, this[298], v5) >= 0 )
    goto LABEL_7;
  v13 = 0x80000000;
  lpExistingFileName = (LPCWSTR)&v14;
  v14 = 0;
  v11 = &CQuickStringW<260>::`vftable';
  CQuickStringW<260>::Append(&v11, this[298]);
  CQuickStringW<260>::Append(&v11, L".tmp");
  v8 = CSequentialReadFile::Open(v6, lpExistingFileName, v7);
  if ( v8 >= 0 )
  {
    (*(void (__fastcall **)(CSequentialReadFile *))(*(_QWORD *)v6 + 8LL))(v6);
    DeleteFileW(this[298]);
    MoveFileW(lpExistingFileName, this[298]);
    v8 = CSequentialReadFile::Open(v6, this[298], v9);
    if ( v8 >= 0 )
    {
      CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v11);
LABEL_7:
      this[80] = (const unsigned __int16 *)v6;
      return (unsigned int)CPPT::InitFromStream((CPPT *)this, a2, 0, 0);
    }
  }
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v11);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18009f1b8  mov     [rsp-8+arg_10], rbx
0x18009f1bd  mov     [rsp-8+arg_18], rsi
0x18009f1c2  push    rbp
0x18009f1c3  push    rdi
0x18009f1c4  push    r14
0x18009f1c6  lea     rbp, [rsp-170h]
0x18009f1ce  sub     rsp, 270h
0x18009f1d5  mov     rax, cs:__security_cookie
0x18009f1dc  xor     rax, rsp
0x18009f1df  mov     [rbp+180h+var_20], rax
0x18009f1e6  mov     r14d, edx
0x18009f1e9  mov     rsi, rcx
0x18009f1ec  xor     r8d, r8d; bool
0x18009f1ef  lea     edx, [r8+28h]; unsigned __int64
0x18009f1f3  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18009f1fa  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x18009f1ff  mov     rbx, rax
0x18009f202  mov     [rsp+280h+var_260], rax
0x18009f207  test    rax, rax
0x18009f20a  jz      loc_18009F328
0x18009f210  mov     qword ptr [rax+8], 0
0x18009f218  mov     qword ptr [rax+10h], 0
0x18009f220  mov     dword ptr [rax+18h], 0
0x18009f227  lea     rax, ??_7CSequentialReadFile@@6B@; const CSequentialReadFile::`vftable'
0x18009f22e  mov     [rbx], rax
0x18009f231  mov     qword ptr [rbx+20h], 0
0x18009f239  test    rbx, rbx
0x18009f23c  jz      loc_18009F328
0x18009f242  mov     rdx, [rsi+950h]; unsigned __int16 *
0x18009f249  mov     rcx, rbx; this
0x18009f24c  call    ?Open@CSequentialReadFile@@QEAAJPEBGH@Z; CSequentialReadFile::Open(ushort const *,int)
0x18009f251  test    eax, eax
0x18009f253  jns     loc_18009F30C
0x18009f259  mov     [rsp+280h+var_240], 80000000h
0x18009f261  lea     rax, [rsp+280h+var_238]
0x18009f266  mov     [rsp+280h+lpExistingFileName], rax
0x18009f26b  xor     eax, eax
0x18009f26d  mov     [rsp+280h+var_238], ax
0x18009f272  lea     rax, ??_7?$CQuickStringW@$0BAE@@@6B@; const CQuickStringW<260>::`vftable'
0x18009f279  mov     [rsp+280h+var_250], rax
0x18009f27e  mov     rdx, [rsi+950h]
0x18009f285  lea     rcx, [rsp+280h+var_250]
0x18009f28a  call    ?Append@?$CQuickStringW@$0BAE@@@QEAAJQEBG@Z; CQuickStringW<260>::Append(ushort const * const)
0x18009f28f  lea     rdx, aTmp; ".tmp"
0x18009f296  lea     rcx, [rsp+280h+var_250]
0x18009f29b  call    ?Append@?$CQuickStringW@$0BAE@@@QEAAJQEBG@Z; CQuickStringW<260>::Append(ushort const * const)
0x18009f2a0  mov     rdx, [rsp+280h+lpExistingFileName]; unsigned __int16 *
0x18009f2a5  mov     rcx, rbx; this
0x18009f2a8  call    ?Open@CSequentialReadFile@@QEAAJPEBGH@Z; CSequentialReadFile::Open(ushort const *,int)
0x18009f2ad  mov     edi, eax
0x18009f2af  test    eax, eax
0x18009f2b1  jns     short loc_18009F2BF
0x18009f2b3  lea     rcx, [rsp+280h+var_250]; this
0x18009f2b8  call    ??1CQuickStringTBase@@MEAA@XZ; CQuickStringTBase::~CQuickStringTBase(void)
0x18009f2bd  jmp     short loc_18009F32D
0x18009f2bf  mov     rax, [rbx]
0x18009f2c2  mov     rcx, rbx
0x18009f2c5  mov     rax, [rax+8]
0x18009f2c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f2ce  mov     rcx, [rsi+950h]; lpFileName
0x18009f2d5  call    cs:__imp_DeleteFileW
0x18009f2db  mov     rdx, [rsi+950h]; lpNewFileName
0x18009f2e2  mov     rcx, [rsp+280h+lpExistingFileName]; lpExistingFileName
0x18009f2e7  call    cs:__imp_MoveFileW
0x18009f2ed  mov     rdx, [rsi+950h]; unsigned __int16 *
0x18009f2f4  mov     rcx, rbx; this
0x18009f2f7  call    ?Open@CSequentialReadFile@@QEAAJPEBGH@Z; CSequentialReadFile::Open(ushort const *,int)
0x18009f2fc  mov     edi, eax
0x18009f2fe  lea     rcx, [rsp+280h+var_250]; this
0x18009f303  test    eax, eax
0x18009f305  js      short loc_18009F2B8
0x18009f307  call    ??1CQuickStringTBase@@MEAA@XZ; CQuickStringTBase::~CQuickStringTBase(void)
0x18009f30c  mov     [rsi+280h], rbx
0x18009f313  xor     r9d, r9d; bool
0x18009f316  xor     r8d, r8d; bool
0x18009f319  mov     edx, r14d; int
0x18009f31c  mov     rcx, rsi; this
0x18009f31f  call    ?InitFromStream@CPPT@@QEAAJH_N0@Z; CPPT::InitFromStream(int,bool,bool)
0x18009f324  mov     edi, eax
0x18009f326  jmp     short loc_18009F32D
0x18009f328  mov     edi, 8007000Eh
0x18009f32d  mov     eax, edi
0x18009f32f  mov     rcx, [rbp+180h+var_20]
0x18009f336  xor     rcx, rsp; StackCookie
0x18009f339  call    __security_check_cookie
0x18009f33e  lea     r11, [rsp+280h+var_10]
0x18009f346  mov     rbx, [r11+30h]
0x18009f34a  mov     rsi, [r11+38h]
0x18009f34e  mov     rsp, r11
0x18009f351  pop     r14
0x18009f353  pop     rdi
0x18009f354  pop     rbp
0x18009f355  retn
```
