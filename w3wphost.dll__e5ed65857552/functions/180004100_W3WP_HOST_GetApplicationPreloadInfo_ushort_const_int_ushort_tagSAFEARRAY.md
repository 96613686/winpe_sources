# W3WP_HOST::GetApplicationPreloadInfo(ushort const *,int *,ushort * *,tagSAFEARRAY * *)

- ea: `0x180004100`
- end: `0x1800043f7`
- name: `?GetApplicationPreloadInfo@W3WP_HOST@@UEAAJPEBGPEAHPEAPEAGPEAPEAUtagSAFEARRAY@@@Z`
- size: `759`
- prototype: `int(W3WP_HOST *__hidden this, const unsigned __int16 *, int *, unsigned __int16 **, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task`

## callees

- `0x180004100`
- `0x180004798`
- `0x18000d2be`
- `0x18000d2f0`
- `0x18000e010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180004353`
- `OLEAUT32!__imp_SysAllocString` at `0x180004353`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004261`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004344`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004261`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004344`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004155`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004155`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004185`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004185`
- `iisutil!SkipTo` at `0x1800041dc`
- `iisutil!SkipTo` at `0x1800041dc`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000423a`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000423a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800043b5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800043c5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800043b5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800043c5`

## string_xrefs

- `0x1800042bc`: `serviceAutoStartEnabled`
- `0x18000430d`: `serviceAutoStartProvider`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::GetApplicationPreloadInfo(
        W3WP_HOST *this,
        unsigned __int16 *a2,
        int *a3,
        unsigned __int16 **a4,
        struct tagSAFEARRAY **a5)
{
  int PreloadProvider; // ebx
  W3WP_HOST *v10; // r13
  unsigned __int16 *v11; // rax
  int i; // ebx
  unsigned __int16 v13; // cx
  unsigned __int16 *v14; // rdi
  __int64 (__fastcall *v15)(__int64, unsigned __int16 *, unsigned __int16 *, _QWORD, _QWORD, _QWORD, __int64 *, _QWORD); // rbx
  unsigned __int16 *Str; // rax
  int v17; // eax
  const OLECHAR *v18; // rax
  unsigned __int16 *v19; // rax
  int v21; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v22; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v24; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v25[56]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v26[56]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 v27[256]; // [rsp+E0h] [rbp-20h] BYREF

  v23 = 0;
  v22 = 0;
  v24 = 0;
  STRU::STRU((STRU *)v26);
  v21 = 0;
  memset_0(v27, 0, sizeof(v27));
  STRU::STRU((STRU *)v25, v27, 0x100u);
  if ( !a3 )
  {
    PreloadProvider = -2147024809;
    goto LABEL_32;
  }
  v10 = (W3WP_HOST *)((char *)this - 56);
  PreloadProvider = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 17) + 56LL))(
                      *((_QWORD *)this + 17),
                      &v23);
  if ( PreloadProvider >= 0 )
  {
    v11 = a2;
    for ( i = 0; i < 3; ++i )
    {
      v11 = SkipTo(v11, 0x2Fu);
      if ( !v11 )
      {
        if ( i != 2 )
        {
          PreloadProvider = -2147024893;
          goto LABEL_28;
        }
        break;
      }
      ++v11;
    }
    v13 = *v11;
    v14 = v11;
    while ( v13 && v13 != 47 )
      v13 = *++v14;
    PreloadProvider = STRU::Copy((STRU *)v25, v11, v14 - v11);
    if ( PreloadProvider >= 0 )
    {
      v15 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 *, _QWORD, _QWORD, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v23 + 40LL);
      Str = STRU::QueryStr((STRU *)v25);
      PreloadProvider = v15(v23, Str, v14, 0, 0, 0, &v22, 0);
      if ( PreloadProvider >= 0 )
      {
        PreloadProvider = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v22 + 72LL))(
                            v22,
                            L"serviceAutoStartEnabled",
                            &v21,
                            0,
                            0);
        if ( PreloadProvider >= 0 )
        {
          v17 = v21;
          *a3 = v21;
          if ( !v17 )
          {
            if ( a4 )
              *a4 = 0;
            goto LABEL_28;
          }
          if ( a4 )
          {
            PreloadProvider = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v22 + 64LL))(
                                v22,
                                L"serviceAutoStartProvider",
                                &v24,
                                0,
                                0);
            if ( PreloadProvider < 0 )
              goto LABEL_28;
            PreloadProvider = W3WP_HOST::GetPreloadProvider(v10, a2, v24, (struct STRU *)v26);
            if ( PreloadProvider < 0 )
              goto LABEL_28;
            v18 = STRU::QueryStr((STRU *)v26);
            v19 = SysAllocString(v18);
            if ( !v19 )
            {
              PreloadProvider = -2147024882;
              goto LABEL_28;
            }
            *a4 = v19;
          }
          if ( a5 )
            *a5 = 0;
        }
      }
    }
  }
LABEL_28:
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
LABEL_32:
  STRU::~STRU((STRU *)v25);
  STRU::~STRU((STRU *)v26);
  return (unsigned int)PreloadProvider;
}

```

## disassembly

```asm
0x180004100  push    rbp
0x180004102  push    rbx
0x180004103  push    rsi
0x180004104  push    rdi
0x180004105  push    r12
0x180004107  push    r13
0x180004109  push    r14
0x18000410b  push    r15
0x18000410d  lea     rbp, [rsp-1F8h]
0x180004115  sub     rsp, 2F8h
0x18000411c  mov     rax, cs:__security_cookie
0x180004123  xor     rax, rsp
0x180004126  mov     [rbp+230h+var_50], rax
0x18000412d  mov     r14, [rbp+230h+arg_20]
0x180004134  xor     edi, edi
0x180004136  mov     rbx, rcx
0x180004139  mov     [rsp+330h+var_2D0], rdi
0x18000413e  lea     rcx, [rbp+230h+var_288]
0x180004142  mov     [rsp+330h+var_2D8], rdi
0x180004147  mov     [rsp+330h+var_2C8], rdi
0x18000414c  mov     rsi, r9
0x18000414f  mov     r12, r8
0x180004152  mov     r15, rdx
0x180004155  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000415c  nop     dword ptr [rax+rax+00h]
0x180004161  xor     edx, edx; Val
0x180004163  mov     [rsp+330h+var_2E0], edi
0x180004167  mov     r8d, 200h; Size
0x18000416d  lea     rcx, [rbp+230h+var_250]; void *
0x180004171  call    memset_0
0x180004176  mov     r8d, 100h
0x18000417c  lea     rdx, [rbp+230h+var_250]
0x180004180  lea     rcx, [rsp+330h+var_2C0]
0x180004185  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000418c  nop     dword ptr [rax+rax+00h]
0x180004191  test    r12, r12
0x180004194  jnz     short loc_1800041A0
0x180004196  mov     ebx, 80070057h
0x18000419b  jmp     loc_1800043B0
0x1800041a0  lea     r13, [rbx-38h]
0x1800041a4  mov     rcx, [r13+0C0h]
0x1800041ab  lea     rdx, [rsp+330h+var_2D0]
0x1800041b0  mov     rax, [rcx]
0x1800041b3  mov     rax, [rax+38h]
0x1800041b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041bc  mov     ebx, eax
0x1800041be  test    eax, eax
0x1800041c0  js      loc_18000437A
0x1800041c6  mov     rax, r15
0x1800041c9  mov     ebx, edi
0x1800041cb  mov     r8d, 2Fh ; '/'
0x1800041d1  cmp     ebx, 3
0x1800041d4  jge     short loc_18000420A
0x1800041d6  mov     edx, r8d
0x1800041d9  mov     rcx, rax
0x1800041dc  call    cs:__imp_?SkipTo@@YAPEAGPEAGG@Z; SkipTo(ushort *,ushort)
0x1800041e3  nop     dword ptr [rax+rax+00h]
0x1800041e8  test    rax, rax
0x1800041eb  jz      short loc_1800041F5
0x1800041ed  add     rax, 2
0x1800041f1  inc     ebx
0x1800041f3  jmp     short loc_1800041CB
0x1800041f5  cmp     ebx, 2
0x1800041f8  jz      short loc_180004204
0x1800041fa  mov     ebx, 80070003h
0x1800041ff  jmp     loc_18000437A
0x180004204  mov     r8d, 2Fh ; '/'
0x18000420a  movzx   ecx, word ptr [rax]
0x18000420d  mov     rdi, rax
0x180004210  jmp     short loc_180004224
0x180004212  cmp     cx, r8w
0x180004216  jz      short loc_180004229
0x180004218  test    cx, cx
0x18000421b  jz      short loc_180004229
0x18000421d  add     rdi, 2
0x180004221  movzx   ecx, word ptr [rdi]
0x180004224  test    cx, cx
0x180004227  jnz     short loc_180004212
0x180004229  mov     r8, rdi
0x18000422c  lea     rcx, [rsp+330h+var_2C0]
0x180004231  sub     r8, rax
0x180004234  mov     rdx, rax
0x180004237  sar     r8, 1
0x18000423a  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180004241  nop     dword ptr [rax+rax+00h]
0x180004246  mov     ebx, eax
0x180004248  test    eax, eax
0x18000424a  js      loc_180004378
0x180004250  mov     rax, [rsp+330h+var_2D0]
0x180004255  mov     rcx, [rax]
0x180004258  mov     rbx, [rcx+28h]
0x18000425c  lea     rcx, [rsp+330h+var_2C0]
0x180004261  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004268  nop     dword ptr [rax+rax+00h]
0x18000426d  xor     edx, edx
0x18000426f  lea     rcx, [rsp+330h+var_2D8]
0x180004274  mov     [rsp+330h+var_2F8], rdx
0x180004279  xor     r9d, r9d
0x18000427c  mov     [rsp+330h+var_300], rcx
0x180004281  mov     r8, rdi
0x180004284  mov     rcx, [rsp+330h+var_2D0]
0x180004289  mov     [rsp+330h+var_308], rdx
0x18000428e  mov     [rsp+330h+var_310], rdx
0x180004293  mov     rdx, rax
0x180004296  mov     rax, rbx
0x180004299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000429e  xor     edi, edi
0x1800042a0  mov     ebx, eax
0x1800042a2  test    eax, eax
0x1800042a4  js      loc_18000437A
0x1800042aa  mov     rcx, [rsp+330h+var_2D8]
0x1800042af  lea     r8, [rsp+330h+var_2E0]
0x1800042b4  xor     r9d, r9d
0x1800042b7  mov     [rsp+330h+var_310], rdi
0x1800042bc  lea     rdx, aServiceautosta; "serviceAutoStartEnabled"
0x1800042c3  mov     rax, [rcx]
0x1800042c6  mov     rax, [rax+48h]
0x1800042ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042cf  mov     ebx, eax
0x1800042d1  test    eax, eax
0x1800042d3  js      loc_18000437A
0x1800042d9  mov     eax, [rsp+330h+var_2E0]
0x1800042dd  mov     [r12], eax
0x1800042e1  test    eax, eax
0x1800042e3  jnz     short loc_1800042F6
0x1800042e5  test    rsi, rsi
0x1800042e8  jz      loc_18000437A
0x1800042ee  mov     [rsi], rdi
0x1800042f1  jmp     loc_18000437A
0x1800042f6  test    rsi, rsi
0x1800042f9  jz      short loc_18000436E
0x1800042fb  mov     rcx, [rsp+330h+var_2D8]
0x180004300  lea     r8, [rsp+330h+var_2C8]
0x180004305  xor     r9d, r9d
0x180004308  mov     [rsp+330h+var_310], rdi
0x18000430d  lea     rdx, aServiceautosta_0; "serviceAutoStartProvider"
0x180004314  mov     rax, [rcx]
0x180004317  mov     rax, [rax+40h]
0x18000431b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004320  mov     ebx, eax
0x180004322  test    eax, eax
0x180004324  js      short loc_18000437A
0x180004326  mov     r8, [rsp+330h+var_2C8]; unsigned __int16 *
0x18000432b  lea     r9, [rbp+230h+var_288]; struct STRU *
0x18000432f  mov     rdx, r15; unsigned __int16 *
0x180004332  mov     rcx, r13; this
0x180004335  call    ?GetPreloadProvider@W3WP_HOST@@QEAAJPEBG0PEAVSTRU@@@Z; W3WP_HOST::GetPreloadProvider(ushort const *,ushort const *,STRU *)
0x18000433a  mov     ebx, eax
0x18000433c  test    eax, eax
0x18000433e  js      short loc_18000437A
0x180004340  lea     rcx, [rbp+230h+var_288]
0x180004344  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000434b  nop     dword ptr [rax+rax+00h]
0x180004350  mov     rcx, rax; psz
0x180004353  call    cs:__imp_SysAllocString
0x18000435a  nop     dword ptr [rax+rax+00h]
0x18000435f  test    rax, rax
0x180004362  jnz     short loc_18000436B
0x180004364  mov     ebx, 8007000Eh
0x180004369  jmp     short loc_18000437A
0x18000436b  mov     [rsi], rax
0x18000436e  test    r14, r14
0x180004371  jz      short loc_18000437A
0x180004373  mov     [r14], rdi
0x180004376  jmp     short loc_18000437A
0x180004378  xor     edi, edi
0x18000437a  mov     rcx, [rsp+330h+var_2D8]
0x18000437f  test    rcx, rcx
0x180004382  jz      short loc_180004395
0x180004384  mov     rax, [rcx]
0x180004387  mov     rax, [rax+10h]
0x18000438b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004390  mov     [rsp+330h+var_2D8], rdi
0x180004395  mov     rcx, [rsp+330h+var_2D0]
0x18000439a  test    rcx, rcx
0x18000439d  jz      short loc_1800043B0
0x18000439f  mov     rax, [rcx]
0x1800043a2  mov     rax, [rax+10h]
0x1800043a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043ab  mov     [rsp+330h+var_2D0], rdi
0x1800043b0  lea     rcx, [rsp+330h+var_2C0]
0x1800043b5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800043bc  nop     dword ptr [rax+rax+00h]
0x1800043c1  lea     rcx, [rbp+230h+var_288]
0x1800043c5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800043cc  nop     dword ptr [rax+rax+00h]
0x1800043d1  mov     eax, ebx
0x1800043d3  mov     rcx, [rbp+230h+var_50]
0x1800043da  xor     rcx, rsp; StackCookie
0x1800043dd  call    __security_check_cookie
0x1800043e2  add     rsp, 2F8h
0x1800043e9  pop     r15
0x1800043eb  pop     r14
0x1800043ed  pop     r13
0x1800043ef  pop     r12
0x1800043f1  pop     rdi
0x1800043f2  pop     rsi
0x1800043f3  pop     rbx
0x1800043f4  pop     rbp
0x1800043f5  retn
```
