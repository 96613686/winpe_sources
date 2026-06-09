# W3WP_HOST::GetApplicationPreloadInfo(ushort const *,int *,ushort * *,tagSAFEARRAY * *)

- ea: `0x180003df0`
- end: `0x1800040a9`
- name: `?GetApplicationPreloadInfo@W3WP_HOST@@UEAAJPEBGPEAHPEAPEAGPEAPEAUtagSAFEARRAY@@@Z`
- size: `697`
- prototype: `__int64 __fastcall(W3WP_HOST *this, unsigned __int16 *, int *, unsigned __int16 **, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task`

## callees

- `0x180003df0`
- `0x1800043d8`
- `0x18000c39e`
- `0x18000c3d0`
- `0x18000d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180004018`
- `OLEAUT32!__imp_SysAllocString` at `0x180004018`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003f39`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000400f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003f39`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000400f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003e45`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003e45`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003e6f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003e6f`
- `iisutil!SkipTo` at `0x180003ec0`
- `iisutil!SkipTo` at `0x180003ec0`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180003f18`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180003f18`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004074`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000407e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004074`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000407e`

## string_xrefs

- `0x180003f8e`: `serviceAutoStartEnabled`
- `0x180003fd8`: `serviceAutoStartProvider`

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
0x180003df0  push    rbp
0x180003df2  push    rbx
0x180003df3  push    rsi
0x180003df4  push    rdi
0x180003df5  push    r12
0x180003df7  push    r13
0x180003df9  push    r14
0x180003dfb  push    r15
0x180003dfd  lea     rbp, [rsp-1F8h]
0x180003e05  sub     rsp, 2F8h
0x180003e0c  mov     rax, cs:__security_cookie
0x180003e13  xor     rax, rsp
0x180003e16  mov     [rbp+230h+var_50], rax
0x180003e1d  mov     r14, [rbp+230h+arg_20]
0x180003e24  xor     edi, edi
0x180003e26  mov     rbx, rcx
0x180003e29  mov     [rsp+330h+var_2D0], rdi
0x180003e2e  lea     rcx, [rbp+230h+var_288]
0x180003e32  mov     [rsp+330h+var_2D8], rdi
0x180003e37  mov     [rsp+330h+var_2C8], rdi
0x180003e3c  mov     rsi, r9
0x180003e3f  mov     r12, r8
0x180003e42  mov     r15, rdx
0x180003e45  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003e4b  xor     edx, edx; Val
0x180003e4d  mov     [rsp+330h+var_2E0], edi
0x180003e51  mov     r8d, 200h; Size
0x180003e57  lea     rcx, [rbp+230h+var_250]; void *
0x180003e5b  call    memset_0
0x180003e60  mov     r8d, 100h
0x180003e66  lea     rdx, [rbp+230h+var_250]
0x180003e6a  lea     rcx, [rsp+330h+var_2C0]
0x180003e6f  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180003e75  test    r12, r12
0x180003e78  jnz     short loc_180003E84
0x180003e7a  mov     ebx, 80070057h
0x180003e7f  jmp     loc_18000406F
0x180003e84  lea     r13, [rbx-38h]
0x180003e88  mov     rcx, [r13+0C0h]
0x180003e8f  lea     rdx, [rsp+330h+var_2D0]
0x180003e94  mov     rax, [rcx]
0x180003e97  mov     rax, [rax+38h]
0x180003e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ea0  mov     ebx, eax
0x180003ea2  test    eax, eax
0x180003ea4  js      loc_180004039
0x180003eaa  mov     rax, r15
0x180003ead  mov     ebx, edi
0x180003eaf  mov     r8d, 2Fh ; '/'
0x180003eb5  cmp     ebx, 3
0x180003eb8  jge     short loc_180003EE8
0x180003eba  mov     edx, r8d
0x180003ebd  mov     rcx, rax
0x180003ec0  call    cs:__imp_?SkipTo@@YAPEAGPEAGG@Z; SkipTo(ushort *,ushort)
0x180003ec6  test    rax, rax
0x180003ec9  jz      short loc_180003ED3
0x180003ecb  add     rax, 2
0x180003ecf  inc     ebx
0x180003ed1  jmp     short loc_180003EAF
0x180003ed3  cmp     ebx, 2
0x180003ed6  jz      short loc_180003EE2
0x180003ed8  mov     ebx, 80070003h
0x180003edd  jmp     loc_180004039
0x180003ee2  mov     r8d, 2Fh ; '/'
0x180003ee8  movzx   ecx, word ptr [rax]
0x180003eeb  mov     rdi, rax
0x180003eee  jmp     short loc_180003F02
0x180003ef0  cmp     cx, r8w
0x180003ef4  jz      short loc_180003F07
0x180003ef6  test    cx, cx
0x180003ef9  jz      short loc_180003F07
0x180003efb  add     rdi, 2
0x180003eff  movzx   ecx, word ptr [rdi]
0x180003f02  test    cx, cx
0x180003f05  jnz     short loc_180003EF0
0x180003f07  mov     r8, rdi
0x180003f0a  lea     rcx, [rsp+330h+var_2C0]
0x180003f0f  sub     r8, rax
0x180003f12  mov     rdx, rax
0x180003f15  sar     r8, 1
0x180003f18  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180003f1e  mov     ebx, eax
0x180003f20  test    eax, eax
0x180003f22  js      loc_180004037
0x180003f28  mov     rax, [rsp+330h+var_2D0]
0x180003f2d  mov     rcx, [rax]
0x180003f30  mov     rbx, [rcx+28h]
0x180003f34  lea     rcx, [rsp+330h+var_2C0]
0x180003f39  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180003f3f  xor     edx, edx
0x180003f41  lea     rcx, [rsp+330h+var_2D8]
0x180003f46  mov     [rsp+330h+var_2F8], rdx
0x180003f4b  xor     r9d, r9d
0x180003f4e  mov     [rsp+330h+var_300], rcx
0x180003f53  mov     r8, rdi
0x180003f56  mov     rcx, [rsp+330h+var_2D0]
0x180003f5b  mov     [rsp+330h+var_308], rdx
0x180003f60  mov     [rsp+330h+var_310], rdx
0x180003f65  mov     rdx, rax
0x180003f68  mov     rax, rbx
0x180003f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f70  xor     edi, edi
0x180003f72  mov     ebx, eax
0x180003f74  test    eax, eax
0x180003f76  js      loc_180004039
0x180003f7c  mov     rcx, [rsp+330h+var_2D8]
0x180003f81  lea     r8, [rsp+330h+var_2E0]
0x180003f86  xor     r9d, r9d
0x180003f89  mov     [rsp+330h+var_310], rdi
0x180003f8e  lea     rdx, aServiceautosta; "serviceAutoStartEnabled"
0x180003f95  mov     rax, [rcx]
0x180003f98  mov     rax, [rax+48h]
0x180003f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fa1  mov     ebx, eax
0x180003fa3  test    eax, eax
0x180003fa5  js      loc_180004039
0x180003fab  mov     eax, [rsp+330h+var_2E0]
0x180003faf  mov     [r12], eax
0x180003fb3  test    eax, eax
0x180003fb5  jnz     short loc_180003FC1
0x180003fb7  test    rsi, rsi
0x180003fba  jz      short loc_180004039
0x180003fbc  mov     [rsi], rdi
0x180003fbf  jmp     short loc_180004039
0x180003fc1  test    rsi, rsi
0x180003fc4  jz      short loc_18000402D
0x180003fc6  mov     rcx, [rsp+330h+var_2D8]
0x180003fcb  lea     r8, [rsp+330h+var_2C8]
0x180003fd0  xor     r9d, r9d
0x180003fd3  mov     [rsp+330h+var_310], rdi
0x180003fd8  lea     rdx, aServiceautosta_0; "serviceAutoStartProvider"
0x180003fdf  mov     rax, [rcx]
0x180003fe2  mov     rax, [rax+40h]
0x180003fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003feb  mov     ebx, eax
0x180003fed  test    eax, eax
0x180003fef  js      short loc_180004039
0x180003ff1  mov     r8, [rsp+330h+var_2C8]; unsigned __int16 *
0x180003ff6  lea     r9, [rbp+230h+var_288]; struct STRU *
0x180003ffa  mov     rdx, r15; unsigned __int16 *
0x180003ffd  mov     rcx, r13; this
0x180004000  call    ?GetPreloadProvider@W3WP_HOST@@QEAAJPEBG0PEAVSTRU@@@Z; W3WP_HOST::GetPreloadProvider(ushort const *,ushort const *,STRU *)
0x180004005  mov     ebx, eax
0x180004007  test    eax, eax
0x180004009  js      short loc_180004039
0x18000400b  lea     rcx, [rbp+230h+var_288]
0x18000400f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004015  mov     rcx, rax; psz
0x180004018  call    cs:__imp_SysAllocString
0x18000401e  test    rax, rax
0x180004021  jnz     short loc_18000402A
0x180004023  mov     ebx, 8007000Eh
0x180004028  jmp     short loc_180004039
0x18000402a  mov     [rsi], rax
0x18000402d  test    r14, r14
0x180004030  jz      short loc_180004039
0x180004032  mov     [r14], rdi
0x180004035  jmp     short loc_180004039
0x180004037  xor     edi, edi
0x180004039  mov     rcx, [rsp+330h+var_2D8]
0x18000403e  test    rcx, rcx
0x180004041  jz      short loc_180004054
0x180004043  mov     rax, [rcx]
0x180004046  mov     rax, [rax+10h]
0x18000404a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000404f  mov     [rsp+330h+var_2D8], rdi
0x180004054  mov     rcx, [rsp+330h+var_2D0]
0x180004059  test    rcx, rcx
0x18000405c  jz      short loc_18000406F
0x18000405e  mov     rax, [rcx]
0x180004061  mov     rax, [rax+10h]
0x180004065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000406a  mov     [rsp+330h+var_2D0], rdi
0x18000406f  lea     rcx, [rsp+330h+var_2C0]
0x180004074  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000407a  lea     rcx, [rbp+230h+var_288]
0x18000407e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004084  mov     eax, ebx
0x180004086  mov     rcx, [rbp+230h+var_50]
0x18000408d  xor     rcx, rsp; StackCookie
0x180004090  call    __security_check_cookie
0x180004095  add     rsp, 2F8h
0x18000409c  pop     r15
0x18000409e  pop     r14
0x1800040a0  pop     r13
0x1800040a2  pop     r12
0x1800040a4  pop     rdi
0x1800040a5  pop     rsi
0x1800040a6  pop     rbx
0x1800040a7  pop     rbp
0x1800040a8  retn
```
