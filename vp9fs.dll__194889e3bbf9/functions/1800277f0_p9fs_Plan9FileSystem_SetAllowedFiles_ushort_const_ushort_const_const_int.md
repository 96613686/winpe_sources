# p9fs::Plan9FileSystem::SetAllowedFiles(ushort const *,ushort const * const *,int)

- ea: `0x1800277f0`
- end: `0x180027944`
- name: `?SetAllowedFiles@Plan9FileSystem@p9fs@@UEAAJPEBGPEBQEBGH@Z`
- size: `340`
- prototype: `__int64 __fastcall(p9fs::Plan9FileSystem *__hidden this, const unsigned __int16 *, const unsigned __int16 *const *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x18000ae8c`
- `0x18000c208`
- `0x18001c93c`
- `0x180025914`
- `0x1800275fc`
- `0x1800277f0`
- `0x1800283c8`
- `0x180034010`

## string_xrefs

- `0x18002792c`: `onecore\vm\dv\storage\plan9\dll\windows\p9fs.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall p9fs::Plan9FileSystem::SetAllowedFiles(
        p9fs::Plan9FileSystem *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *const *a3,
        int a4)
{
  __int128 *v4; // rbx
  unsigned __int64 v7; // r8
  __int128 *p_Src; // rax
  const char *v9; // r9
  volatile signed __int32 *v10; // rbx
  __int64 result; // rax
  __int128 *v12; // [rsp+30h] [rbp-58h] BYREF
  const unsigned __int16 *const *v13; // [rsp+38h] [rbp-50h]
  __int128 Src; // [rsp+40h] [rbp-48h] BYREF
  __m128i si128; // [rsp+50h] [rbp-38h]
  __int128 v16; // [rsp+60h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v4 = (__int128 *)a4;
  v16 = 0;
  Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(Src) = 0;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  try
  {
    Vml::WideToMultiByte(&Src, a2, v7);
    p_Src = &Src;
    if ( si128.m128i_i64[1] > 0xFuLL )
      p_Src = (__int128 *)Src;
    v12 = p_Src;
    v13 = (const unsigned __int16 *const *)si128.m128i_i64[0];
    p9fs::ShareList::Get((char *)this + 224, &v16, &v12);
    std::string::~string(&Src);
    if ( !(_QWORD)v16 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2BD,
        (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9fs.cpp",
        (const char *)0x490,
        1u);
    if ( (_DWORD)v4 == -1 || !a3 && (_DWORD)v4 )
      gsl::details::terminate((gsl::details *)v16);
    v12 = v4;
    v13 = a3;
    p9fs::Share::SetAllowedFileList(v16, &v12);
    v10 = (volatile signed __int32 *)*((_QWORD *)&v16 + 1);
    if ( *((_QWORD *)&v16 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v16 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2C3,
                           (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9fs.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x1800277f0  mov     rax, rsp
0x1800277f3  mov     [rax+18h], rbx
0x1800277f7  push    rsi
0x1800277f8  push    rdi
0x1800277f9  push    r14
0x1800277fb  sub     rsp, 70h
0x1800277ff  movsxd  rbx, r9d
0x180027802  mov     rdi, r8
0x180027805  mov     rsi, rcx
0x180027808  xor     r14d, r14d
0x18002780b  mov     [rax-68h], r14d
0x18002780f  xorps   xmm0, xmm0
0x180027812  movups  xmmword ptr [rax-28h], xmm0
0x180027816  movups  xmmword ptr [rax-48h], xmm0
0x18002781a  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180027822  movdqu  xmmword ptr [rax-38h], xmm1
0x180027827  mov     [rax-48h], r14b
0x18002782b  mov     dword ptr [rax-68h], 1
0x180027832  or      r8, 0FFFFFFFFFFFFFFFFh
0x180027836  inc     r8; cchWideChar
0x180027839  cmp     [rdx+r8*2], r14w
0x18002783e  jnz     short loc_180027836
0x180027840  lea     rcx, [rsp+88h+Src]; Src
0x180027845  call    ?WideToMultiByte@Vml@@YAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG_KI@Z; Vml::WideToMultiByte(std::string &,ushort const *,unsigned __int64,uint)
0x18002784a  lea     rax, [rsp+88h+Src]
0x18002784f  cmp     [rsp+88h+var_30], 0Fh
0x180027855  cmova   rax, qword ptr [rsp+88h+Src]
0x18002785b  mov     [rsp+88h+var_58], rax
0x180027860  mov     rax, [rsp+88h+var_38]
0x180027865  mov     [rsp+88h+var_50], rax
0x18002786a  lea     rcx, [rsi+0E0h]
0x180027871  lea     r8, [rsp+88h+var_58]
0x180027876  lea     rdx, [rsp+88h+var_28]
0x18002787b  call    ?Get@ShareList@p9fs@@QEAA?AV?$shared_ptr@UShare@p9fs@@@std@@V?$basic_string_view@DU?$char_traits@D@std@@@4@@Z; p9fs::ShareList::Get(std::string_view)
0x180027880  nop
0x180027881  lea     rcx, [rsp+88h+Src]
0x180027886  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002788b  mov     rcx, [rsp+88h+var_28]; this
0x180027890  test    rcx, rcx
0x180027893  jz      loc_18002791E
0x180027899  cmp     ebx, 0FFFFFFFFh
0x18002789c  jz      loc_18002793D
0x1800278a2  test    rdi, rdi
0x1800278a5  jnz     short loc_1800278AF
0x1800278a7  test    ebx, ebx
0x1800278a9  jnz     loc_18002793D
0x1800278af  mov     [rsp+88h+var_58], rbx
0x1800278b4  mov     [rsp+88h+var_50], rdi
0x1800278b9  lea     rdx, [rsp+88h+var_58]
0x1800278be  call    ?SetAllowedFileList@Share@p9fs@@QEAAXV?$span@QEBG$0?0@gsl@@@Z; p9fs::Share::SetAllowedFileList(gsl::span<ushort const * const,-1>)
0x1800278c3  nop
0x1800278c4  mov     rbx, [rsp+88h+var_20]
0x1800278c9  test    rbx, rbx
0x1800278cc  jz      short loc_180027905
0x1800278ce  or      eax, 0FFFFFFFFh
0x1800278d1  lock xadd [rbx+8], eax
0x1800278d6  cmp     eax, 1
0x1800278d9  jnz     short loc_180027905
0x1800278db  mov     rax, [rbx]
0x1800278de  mov     rcx, rbx
0x1800278e1  mov     rax, [rax]
0x1800278e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278e9  or      eax, 0FFFFFFFFh
0x1800278ec  lock xadd [rbx+0Ch], eax
0x1800278f1  cmp     eax, 1
0x1800278f4  jnz     short loc_180027905
0x1800278f6  mov     rax, [rbx]
0x1800278f9  mov     rcx, rbx
0x1800278fc  mov     rax, [rax+8]
0x180027900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027905  xor     eax, eax
0x180027907  jmp     short loc_18002790D
0x180027909  mov     eax, [rsp+88h+var_68]
0x18002790d  mov     rbx, [rsp+88h+arg_10]
0x180027915  add     rsp, 70h
0x180027919  pop     r14
0x18002791b  pop     rdi
0x18002791c  pop     rsi
0x18002791d  retn
0x18002791e  mov     rcx, [rsp+88h]; this
0x180027926  mov     r9d, 490h; char *
0x18002792c  lea     r8, aOnecoreVmDvSto_8; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x180027933  mov     edx, 2BDh; void *
0x180027938  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002793d  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```
