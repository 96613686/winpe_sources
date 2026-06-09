# p9fs::File::DetermineSymlinkType(std::basic_string_view<ushort,std::char_traits<ushort>>)

- ea: `0x18001f194`
- end: `0x18001f41d`
- name: `?DetermineSymlinkType@File@p9fs@@AEAA?AW4SymlinkType@12@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x1800218b0`

## callees

- `0x180004120`
- `0x18001ce4c`
- `0x18001d6fc`
- `0x18001d940`
- `0x18001dcb0`
- `0x18001f194`
- `0x180022f2c`
- `0x180022f44`
- `0x180023460`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001f1c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001f1c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001f224`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001f224`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall p9fs::File::DetermineSymlinkType(RTL_SRWLOCK *a1, _QWORD *a2)
{
  RTL_SRWLOCK *v4; // rbx
  RTL_SRWLOCK *v5; // rcx
  unsigned __int64 v6; // rdx
  PVOID Ptr; // rax
  __int64 v8; // rax
  __int64 v9; // r8
  const unsigned __int16 *v10; // r8
  _OWORD *v11; // rax
  unsigned __int64 v12; // r8
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  unsigned __int64 v15; // rdx
  unsigned int v16; // ebx
  wchar_t **v17; // rcx
  wchar_t **v18; // rcx
  __int128 v20; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v21; // [rsp+50h] [rbp-B0h]
  RTL_SRWLOCK *v22; // [rsp+60h] [rbp-A0h]
  wchar_t *S1[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v24; // [rsp+78h] [rbp-88h]
  unsigned __int64 v25; // [rsp+80h] [rbp-80h]
  _OWORD Src[2]; // [rsp+88h] [rbp-78h] BYREF
  char v27[64]; // [rsp+B0h] [rbp-50h] BYREF
  int v28; // [rsp+F0h] [rbp-10h]
  int v29; // [rsp+F4h] [rbp-Ch]

  v4 = a1 + 1;
  AcquireSRWLockShared(a1 + 1);
  v22 = v4;
  v5 = a1 + 2;
  v6 = *((_QWORD *)a1[9].Ptr + 9);
  v20 = 0;
  v21 = 0;
  Ptr = a1[4].Ptr;
  if ( (unsigned __int64)Ptr < v6 )
    std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
  v8 = (__int64)Ptr - v6;
  v9 = -1;
  if ( v8 != -1 )
    v9 = v8;
  if ( a1[5].Ptr > (PVOID)7 )
    v5 = (RTL_SRWLOCK *)v5->Ptr;
  std::wstring::_Construct<1,unsigned short const *>(&v20, (char *)v5 + 2 * v6, v9);
  if ( v4 )
    ReleaseSRWLockShared(v4);
  Src[0] = v20;
  Src[1] = v21;
  *(_QWORD *)&v21 = 0;
  *((_QWORD *)&v21 + 1) = 7;
  LOWORD(v20) = 0;
  std::wstring::~wstring(&v20);
  v20 = 0;
  v21 = 0u;
  std::wstring::_Construct<1,unsigned short const *>(&v20, *a2, a2[1]);
  std::filesystem::path::operator/=(Src, (std::filesystem *)&v20);
  std::wstring::~wstring(&v20);
  v11 = std::filesystem::path::lexically_normal((std::filesystem *)Src, (__int64)&v20, v10);
  std::wstring::wstring(S1, v11);
  std::wstring::~wstring(&v20);
  v12 = v24;
  v13 = (const wchar_t *)S1;
  v14 = S1[0];
  v15 = v25;
  if ( v25 > 7 )
    v13 = S1[0];
  v16 = 2;
  if ( v24 == 2 )
  {
    if ( !wmemcmp(v13, L"..", 2u) )
      goto LABEL_28;
    v15 = v25;
    v12 = v24;
    v14 = S1[0];
  }
  v17 = S1;
  if ( v15 > 7 )
    v17 = (wchar_t **)v14;
  if ( v12 >= 3 )
  {
    if ( !wmemcmp((const wchar_t *)v17, L"..\\", 3u) )
      goto LABEL_28;
    v15 = v25;
    v12 = v24;
    v14 = S1[0];
  }
  v18 = S1;
  if ( v15 > 7 )
    v18 = (wchar_t **)v14;
  if ( v12 == 1 && !wmemcmp((const wchar_t *)v18, L".", 1u) )
    goto LABEL_27;
  (*(void (__fastcall **)(_QWORD, char *, _QWORD, wchar_t **, _QWORD, _QWORD, int))(**((_QWORD **)a1[9].Ptr + 14) + 24LL))(
    *((_QWORD *)a1[9].Ptr + 14),
    v27,
    *((_QWORD *)a1[9].Ptr + 3),
    S1,
    0,
    0,
    1);
  if ( v27[0] && ((v28 & 0x400) == 0 || v29 != -1610612707) )
  {
    if ( (v28 & 0x10) == 0 )
      v16 = 1;
LABEL_27:
    std::wstring::~wstring(S1);
    std::wstring::~wstring(Src);
    return v16;
  }
LABEL_28:
  std::wstring::~wstring(S1);
  std::wstring::~wstring(Src);
  return 0;
}

```

## disassembly

```asm
0x18001f194  push    rbp
0x18001f196  push    rbx
0x18001f197  push    rsi
0x18001f198  push    rdi
0x18001f199  lea     rbp, [rsp-38h]
0x18001f19e  sub     rsp, 138h
0x18001f1a5  mov     rax, cs:__security_cookie
0x18001f1ac  xor     rax, rsp
0x18001f1af  mov     [rbp+50h+var_30], rax
0x18001f1b3  mov     rsi, rdx
0x18001f1b6  mov     rdi, rcx
0x18001f1b9  lea     rbx, [rcx+8]
0x18001f1bd  mov     rcx, rbx; SRWLock
0x18001f1c0  call    cs:__imp_AcquireSRWLockShared
0x18001f1c6  mov     [rsp+150h+var_F0], rbx
0x18001f1cb  lea     rcx, [rdi+10h]
0x18001f1cf  mov     rax, [rdi+48h]
0x18001f1d3  mov     rdx, [rax+48h]
0x18001f1d7  xorps   xmm0, xmm0
0x18001f1da  movups  [rsp+150h+var_110], xmm0
0x18001f1df  xorps   xmm1, xmm1
0x18001f1e2  movdqu  [rsp+150h+var_100], xmm1
0x18001f1e8  mov     rax, [rcx+10h]
0x18001f1ec  cmp     rax, rdx
0x18001f1ef  jb      loc_18001F417
0x18001f1f5  sub     rax, rdx
0x18001f1f8  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001f1fc  cmp     rax, r8
0x18001f1ff  cmovb   r8, rax
0x18001f203  cmp     qword ptr [rcx+18h], 7
0x18001f208  jbe     short loc_18001F20D
0x18001f20a  mov     rcx, [rcx]
0x18001f20d  lea     rdx, [rcx+rdx*2]
0x18001f211  lea     rcx, [rsp+150h+var_110]
0x18001f216  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001f21b  nop
0x18001f21c  test    rbx, rbx
0x18001f21f  jz      short loc_18001F22A
0x18001f221  mov     rcx, rbx; SRWLock
0x18001f224  call    cs:__imp_ReleaseSRWLockShared
0x18001f22a  movups  xmm0, [rsp+150h+var_110]
0x18001f22f  movups  [rbp+50h+Src], xmm0
0x18001f233  movups  xmm1, [rsp+150h+var_100]
0x18001f238  movups  [rbp+50h+var_B8], xmm1
0x18001f23c  mov     qword ptr [rsp+150h+var_100], 0
0x18001f245  mov     qword ptr [rsp+150h+var_100+8], 7
0x18001f24e  xor     eax, eax
0x18001f250  mov     word ptr [rsp+150h+var_110], ax
0x18001f255  lea     rcx, [rsp+150h+var_110]
0x18001f25a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f25f  xorps   xmm0, xmm0
0x18001f262  movups  [rsp+150h+var_110], xmm0
0x18001f267  mov     qword ptr [rsp+150h+var_100], 0
0x18001f270  mov     qword ptr [rsp+150h+var_100+8], 0
0x18001f279  mov     r8, [rsi+8]
0x18001f27d  mov     rdx, [rsi]
0x18001f280  lea     rcx, [rsp+150h+var_110]
0x18001f285  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001f28a  nop
0x18001f28b  lea     rdx, [rsp+150h+var_110]; this
0x18001f290  lea     rcx, [rbp+50h+Src]; Src
0x18001f294  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x18001f299  nop
0x18001f29a  lea     rcx, [rsp+150h+var_110]
0x18001f29f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f2a4  lea     rdx, [rsp+150h+var_110]
0x18001f2a9  lea     rcx, [rbp+50h+Src]
0x18001f2ad  call    ?lexically_normal@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::lexically_normal(void)
0x18001f2b2  nop
0x18001f2b3  mov     rdx, rax
0x18001f2b6  lea     rcx, [rsp+150h+S1]
0x18001f2bb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001f2c0  nop
0x18001f2c1  lea     rcx, [rsp+150h+var_110]
0x18001f2c6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f2cb  mov     r8, [rsp+150h+var_D8]
0x18001f2d0  lea     rcx, [rsp+150h+S1]
0x18001f2d5  mov     rax, [rsp+150h+S1]
0x18001f2da  mov     rdx, [rbp+50h+var_D0]
0x18001f2de  cmp     rdx, 7
0x18001f2e2  cmova   rcx, rax; S1
0x18001f2e6  mov     ebx, 2
0x18001f2eb  cmp     r8, rbx
0x18001f2ee  jnz     short loc_18001F315
0x18001f2f0  mov     r8d, ebx; N
0x18001f2f3  lea     rdx, S2; ".."
0x18001f2fa  call    wmemcmp
0x18001f2ff  test    eax, eax
0x18001f301  jz      loc_18001F3E9
0x18001f307  mov     rdx, [rbp+50h+var_D0]
0x18001f30b  mov     r8, [rsp+150h+var_D8]
0x18001f310  mov     rax, [rsp+150h+S1]
0x18001f315  lea     rcx, [rsp+150h+S1]
0x18001f31a  cmp     rdx, 7
0x18001f31e  cmova   rcx, rax; S1
0x18001f322  cmp     r8, 3
0x18001f326  jb      short loc_18001F350
0x18001f328  mov     r8d, 3; N
0x18001f32e  lea     rdx, asc_180036EE8; "..\\"
0x18001f335  call    wmemcmp
0x18001f33a  test    eax, eax
0x18001f33c  jz      loc_18001F3E9
0x18001f342  mov     rdx, [rbp+50h+var_D0]
0x18001f346  mov     r8, [rsp+150h+var_D8]
0x18001f34b  mov     rax, [rsp+150h+S1]
0x18001f350  lea     rcx, [rsp+150h+S1]
0x18001f355  cmp     rdx, 7
0x18001f359  cmova   rcx, rax; S1
0x18001f35d  mov     esi, 1
0x18001f362  cmp     r8, rsi
0x18001f365  jnz     short loc_18001F37A
0x18001f367  mov     r8d, esi; N
0x18001f36a  lea     rdx, asc_180036E68; "."
0x18001f371  call    wmemcmp
0x18001f376  test    eax, eax
0x18001f378  jz      short loc_18001F3D1
0x18001f37a  mov     r8, [rdi+48h]
0x18001f37e  mov     rcx, [r8+70h]
0x18001f382  mov     rax, [rcx]
0x18001f385  mov     [rsp+150h+var_120], esi
0x18001f389  mov     [rsp+150h+var_128], 0
0x18001f392  mov     [rsp+150h+var_130], 0
0x18001f39b  lea     r9, [rsp+150h+S1]
0x18001f3a0  mov     r8, [r8+18h]
0x18001f3a4  lea     rdx, [rbp+50h+var_A0]
0x18001f3a8  mov     rax, [rax+18h]
0x18001f3ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3b1  cmp     [rbp+50h+var_A0], 0
0x18001f3b5  jz      short loc_18001F3E9
0x18001f3b7  test    [rbp+50h+var_60], 400h
0x18001f3be  jz      short loc_18001F3C9
0x18001f3c0  cmp     [rbp+50h+var_5C], 0A000001Dh
0x18001f3c7  jz      short loc_18001F3E9
0x18001f3c9  test    byte ptr [rbp+50h+var_60], 10h
0x18001f3cd  jnz     short loc_18001F3D1
0x18001f3cf  mov     ebx, esi
0x18001f3d1  lea     rcx, [rsp+150h+S1]
0x18001f3d6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f3db  nop
0x18001f3dc  lea     rcx, [rbp+50h+Src]
0x18001f3e0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f3e5  mov     eax, ebx
0x18001f3e7  jmp     short loc_18001F3FF
0x18001f3e9  lea     rcx, [rsp+150h+S1]
0x18001f3ee  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f3f3  nop
0x18001f3f4  lea     rcx, [rbp+50h+Src]
0x18001f3f8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f3fd  xor     eax, eax
0x18001f3ff  mov     rcx, [rbp+50h+var_30]
0x18001f403  xor     rcx, rsp; StackCookie
0x18001f406  call    __security_check_cookie
0x18001f40b  add     rsp, 138h
0x18001f412  pop     rdi
0x18001f413  pop     rsi
0x18001f414  pop     rbx
0x18001f415  pop     rbp
0x18001f416  retn
0x18001f417  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
