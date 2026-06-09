# GetUncApplicationToken(INativeConfigurationSystem *,ulong,ushort const *,void * *)

- ea: `0x1800043c8`
- end: `0x1800045f4`
- name: `?GetUncApplicationToken@@YAJPEAVINativeConfigurationSystem@@KPEBGPEAPEAX@Z`
- size: `556`
- prototype: `__int64 __fastcall(struct INativeConfigurationSystem *, unsigned int, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x180003b80`

## callees

- `0x180004230`
- `0x1800042e0`
- `0x1800043c8`
- `0x180004842`
- `0x180004880`
- `0x180005010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004557`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004557`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800045cb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800045cb`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800045c1`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800045c1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004429`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004429`

## pseudocode

```c
__int64 __fastcall GetUncApplicationToken(
        struct INativeConfigurationSystem *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        void **a4)
{
  int ApplicationSiteName; // ebx
  const wchar_t *v9; // rdi
  const unsigned __int16 *v10; // r8
  unsigned int v11; // r9d
  __int64 v13; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v14; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v15; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpszPassword; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v17[32]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD *v18; // [rsp+90h] [rbp-70h]
  int v19; // [rsp+98h] [rbp-68h]
  __int16 v20; // [rsp+9Ch] [rbp-64h]
  _BYTE v21[32]; // [rsp+A0h] [rbp-60h] BYREF
  LPCWSTR lpszDomain; // [rsp+C0h] [rbp-40h]
  int v23; // [rsp+D0h] [rbp-30h]
  _OWORD v24[2]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 v25[64]; // [rsp+100h] [rbp+0h] BYREF

  v15 = 0;
  lpszPassword = 0;
  memset_0(v25, 0, sizeof(v25));
  STRU::STRU((STRU *)v21, v25, 0x40u);
  v19 = 32;
  v20 = 256;
  v18 = v24;
  v13 = 0;
  v14 = 0;
  memset(v24, 0, sizeof(v24));
  ApplicationSiteName = GetApplicationSiteName(a1, a2, (struct BUFFER *)v17);
  if ( ApplicationSiteName < 0 )
    goto LABEL_17;
  v9 = L"/";
  if ( *a3 )
    v9 = a3;
  ApplicationSiteName = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, __int64 *))(*(_QWORD *)a1 + 56LL))(
                          a1,
                          &v13);
  if ( ApplicationSiteName < 0 )
    goto LABEL_13;
  ApplicationSiteName = (*(__int64 (__fastcall **)(__int64, _OWORD *, const wchar_t *, _QWORD, _QWORD, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v13 + 40LL))(
                          v13,
                          v18,
                          v9,
                          0,
                          0,
                          &v14,
                          0,
                          0);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  v13 = 0;
  if ( ApplicationSiteName >= 0 )
  {
    ApplicationSiteName = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v14 + 64LL))(
                            v14,
                            L"userName",
                            &v15,
                            0,
                            0);
    if ( ApplicationSiteName >= 0 )
    {
      ApplicationSiteName = (*(__int64 (__fastcall **)(__int64, const wchar_t *, LPCWSTR *, _QWORD, _QWORD))(*(_QWORD *)v14 + 64LL))(
                              v14,
                              L"password",
                              &lpszPassword,
                              0,
                              0);
      if ( ApplicationSiteName >= 0 )
      {
        if ( !v15 || (ApplicationSiteName = STRU::Copy((STRU *)v21, v15), ApplicationSiteName >= 0) )
        {
          if ( v23 )
          {
            ApplicationSiteName = CreateToken(lpszDomain, lpszPassword, v10, v11, a4);
          }
          else
          {
            *a4 = 0;
            ApplicationSiteName = 0;
          }
        }
      }
    }
LABEL_13:
    if ( v13 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      v13 = 0;
    }
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
LABEL_17:
  BUFFER::~BUFFER((BUFFER *)v17);
  STRU::~STRU((STRU *)v21);
  return (unsigned int)ApplicationSiteName;
}

```

## disassembly

```asm
0x1800043c8  push    rbp
0x1800043ca  push    rbx
0x1800043cb  push    rsi
0x1800043cc  push    rdi
0x1800043cd  push    r12
0x1800043cf  push    r14
0x1800043d1  push    r15
0x1800043d3  lea     rbp, [rsp-90h]
0x1800043db  sub     rsp, 190h
0x1800043e2  mov     rax, cs:__security_cookie
0x1800043e9  xor     rax, rsp
0x1800043ec  mov     [rbp+0C0h+var_40], rax
0x1800043f3  mov     r15, r8
0x1800043f6  mov     ebx, edx
0x1800043f8  mov     r14, rcx
0x1800043fb  xor     r12d, r12d
0x1800043fe  xor     edx, edx; Val
0x180004400  mov     [rsp+1C0h+var_160], r12
0x180004405  mov     r8d, 80h; Size
0x18000440b  mov     [rsp+1C0h+lpszPassword], r12
0x180004410  lea     rcx, [rbp+0C0h+var_C0]; void *
0x180004414  mov     rsi, r9
0x180004417  call    memset_0
0x18000441c  lea     r8d, [r12+40h]
0x180004421  lea     rdx, [rbp+0C0h+var_C0]
0x180004425  lea     rcx, [rbp+0C0h+var_120]
0x180004429  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000442f  xorps   xmm0, xmm0
0x180004432  mov     [rbp+0C0h+var_128], 20h ; ' '
0x180004439  lea     rax, [rbp+0C0h+var_E8]
0x18000443d  mov     [rbp+0C0h+var_124], 100h
0x180004443  lea     r8, [rsp+1C0h+var_150]; struct BUFFER *
0x180004448  mov     [rbp+0C0h+var_130], rax
0x18000444c  mov     edx, ebx; unsigned int
0x18000444e  mov     [rsp+1C0h+var_170], r12
0x180004453  mov     rcx, r14; struct INativeConfigurationSystem *
0x180004456  mov     [rsp+1C0h+var_168], r12
0x18000445b  movups  [rbp+0C0h+var_E8], xmm0
0x18000445f  movups  [rbp+0C0h+var_D8], xmm0
0x180004463  call    ?GetApplicationSiteName@@YAJPEAVINativeConfigurationSystem@@KPEAVBUFFER@@@Z; GetApplicationSiteName(INativeConfigurationSystem *,ulong,BUFFER *)
0x180004468  mov     ebx, eax
0x18000446a  test    eax, eax
0x18000446c  js      loc_1800045BC
0x180004472  mov     rax, [r14]
0x180004475  lea     rdi, asc_1800066D0; "/"
0x18000447c  cmp     [r15], r12w
0x180004480  lea     rdx, [rsp+1C0h+var_170]
0x180004485  mov     rcx, r14
0x180004488  cmovnz  rdi, r15
0x18000448c  mov     rax, [rax+38h]
0x180004490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004495  mov     ebx, eax
0x180004497  test    eax, eax
0x180004499  js      loc_180004586
0x18000449f  mov     rcx, [rsp+1C0h+var_170]
0x1800044a4  lea     rdx, [rsp+1C0h+var_168]
0x1800044a9  mov     [rsp+1C0h+var_188], r12
0x1800044ae  xor     r9d, r9d
0x1800044b1  mov     [rsp+1C0h+var_190], r12
0x1800044b6  mov     r8, rdi
0x1800044b9  mov     [rsp+1C0h+var_198], rdx
0x1800044be  mov     rax, [rcx]
0x1800044c1  mov     rdx, [rbp+0C0h+var_130]
0x1800044c5  mov     [rsp+1C0h+var_1A0], r12
0x1800044ca  mov     rax, [rax+28h]
0x1800044ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044d3  mov     rcx, [rsp+1C0h+var_170]
0x1800044d8  mov     ebx, eax
0x1800044da  mov     rax, [rcx]
0x1800044dd  mov     rax, [rax+10h]
0x1800044e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044e6  mov     [rsp+1C0h+var_170], r12
0x1800044eb  test    ebx, ebx
0x1800044ed  js      loc_1800045A1
0x1800044f3  mov     rcx, [rsp+1C0h+var_168]
0x1800044f8  lea     r8, [rsp+1C0h+var_160]
0x1800044fd  xor     r9d, r9d
0x180004500  mov     [rsp+1C0h+var_1A0], r12
0x180004505  lea     rdx, aUsername; "userName"
0x18000450c  mov     rax, [rcx]
0x18000450f  mov     rax, [rax+40h]
0x180004513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004518  mov     ebx, eax
0x18000451a  test    eax, eax
0x18000451c  js      short loc_180004586
0x18000451e  mov     rcx, [rsp+1C0h+var_168]
0x180004523  lea     r8, [rsp+1C0h+lpszPassword]
0x180004528  xor     r9d, r9d
0x18000452b  mov     [rsp+1C0h+var_1A0], r12
0x180004530  lea     rdx, aPassword; "password"
0x180004537  mov     rax, [rcx]
0x18000453a  mov     rax, [rax+40h]
0x18000453e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004543  mov     ebx, eax
0x180004545  test    eax, eax
0x180004547  js      short loc_180004586
0x180004549  mov     rdx, [rsp+1C0h+var_160]
0x18000454e  test    rdx, rdx
0x180004551  jz      short loc_180004563
0x180004553  lea     rcx, [rbp+0C0h+var_120]
0x180004557  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000455d  mov     ebx, eax
0x18000455f  test    eax, eax
0x180004561  js      short loc_180004586
0x180004563  cmp     [rbp+0C0h+var_F0], r12d
0x180004567  jnz     short loc_180004571
0x180004569  mov     [rsi], r12
0x18000456c  mov     ebx, r12d
0x18000456f  jmp     short loc_180004586
0x180004571  mov     rdx, [rsp+1C0h+lpszPassword]; lpszPassword
0x180004576  mov     rcx, [rbp+0C0h+lpszDomain]; lpszDomain
0x18000457a  mov     [rsp+1C0h+var_1A0], rsi; void **
0x18000457f  call    ?CreateToken@@YAJPEAGPEBG1KPEAPEAX@Z; CreateToken(ushort *,ushort const *,ushort const *,ulong,void * *)
0x180004584  mov     ebx, eax
0x180004586  mov     rcx, [rsp+1C0h+var_170]
0x18000458b  test    rcx, rcx
0x18000458e  jz      short loc_1800045A1
0x180004590  mov     rax, [rcx]
0x180004593  mov     rax, [rax+10h]
0x180004597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000459c  mov     [rsp+1C0h+var_170], r12
0x1800045a1  mov     rcx, [rsp+1C0h+var_168]
0x1800045a6  test    rcx, rcx
0x1800045a9  jz      short loc_1800045BC
0x1800045ab  mov     rax, [rcx]
0x1800045ae  mov     rax, [rax+10h]
0x1800045b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045b7  mov     [rsp+1C0h+var_168], r12
0x1800045bc  lea     rcx, [rsp+1C0h+var_150]
0x1800045c1  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800045c7  lea     rcx, [rbp+0C0h+var_120]
0x1800045cb  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800045d1  mov     eax, ebx
0x1800045d3  mov     rcx, [rbp+0C0h+var_40]
0x1800045da  xor     rcx, rsp; StackCookie
0x1800045dd  call    __security_check_cookie
0x1800045e2  add     rsp, 190h
0x1800045e9  pop     r15
0x1800045eb  pop     r14
0x1800045ed  pop     r12
0x1800045ef  pop     rdi
0x1800045f0  pop     rsi
0x1800045f1  pop     rbx
0x1800045f2  pop     rbp
0x1800045f3  retn
```
