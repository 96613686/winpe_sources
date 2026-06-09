# DC::iSelect(REGION *,int)

- ea: `0x140081a54`
- end: `0x140081e40`
- name: `?iSelect@DC@@QEAAHPEAVREGION@@H@Z`
- size: `1004`
- prototype: `__int64 __fastcall(DC *__hidden this, struct REGION *, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140061980`
- `0x1400816d0`
- `0x14022a830`

## callees

- `0x140016204`
- `0x1400620a8`
- `0x140062bf4`
- `0x140081a54`
- `0x14016cabc`
- `0x140183ad8`
- `0x1401d906c`
- `0x140341ff0`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140081a84`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140081a84`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x140081df8`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140081d47`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140081d47`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x140081d37`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x140081d37`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140081b55`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140081c82`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140081c9b`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140081b55`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140081c82`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140081c9b`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140081c72`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140081c72`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140081c3c`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140081c3c`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x140081b8a`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x140081b8a`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x140081ad3`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x140081ad3`
- `win32kbase!?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z` at `0x140081bbc`
- `win32kbase!?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z` at `0x140081c57`
- `win32kbase!?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z` at `0x140081bbc`
- `win32kbase!?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z` at `0x140081c57`
- `win32kbase!??0RGNMEMOBJ@@QEAA@K@Z` at `0x140081cbb`
- `win32kbase!??0RGNMEMOBJ@@QEAA@K@Z` at `0x140081cbb`
- `win32kbase!?vCopy@RGNOBJ@@QEAAXAEAV1@@Z` at `0x140081cd9`
- `win32kbase!?vCopy@RGNOBJ@@QEAAXAEAV1@@Z` at `0x140081cd9`
- `win32kbase!?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z` at `0x140081b00`
- `win32kbase!?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z` at `0x140081beb`
- `win32kbase!?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z` at `0x140081d09`
- `win32kbase!?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z` at `0x140081e2f`
- `win32kbase!?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z` at `0x140081b00`
- `win32kbase!?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z` at `0x140081beb`
- `win32kbase!?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z` at `0x140081d09`
- `win32kbase!?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z` at `0x140081e2f`

## pseudocode

```c
__int64 __fastcall DC::iSelect(DC *this, struct REGION *a2, int a3)
{
  struct Gre::Base::SESSION_GLOBALS *v6; // rax
  __int64 v7; // rsi
  unsigned int v8; // r14d
  struct Gre::Base::SESSION_GLOBALS *v9; // r15
  __int64 v10; // rbx
  RGNOBJ *v12; // rcx
  LONG v13; // r8d
  int v14; // eax
  unsigned int sizeScan; // eax
  __int64 v16; // rbx
  unsigned int v17; // eax
  int v18; // eax
  char *v19; // rcx
  __int64 v20; // rax
  LONG left; // r8d
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // rdx
  LONG top; // r9d
  char *v25; // r10
  const struct _POINTL *v26; // rbx
  __int64 v27; // [rsp+20h] [rbp-40h] BYREF
  __int64 v28; // [rsp+28h] [rbp-38h] BYREF
  struct REGION *v29; // [rsp+30h] [rbp-30h] BYREF
  __int64 v30; // [rsp+38h] [rbp-28h] BYREF
  struct _RECTL v31; // [rsp+40h] [rbp-20h] BYREF

  v6 = Gre::Base::Globals(this);
  v7 = *((_QWORD *)this + 20);
  v8 = 0;
  v9 = v6;
  if ( a3 == 5 )
  {
    if ( !a2 )
    {
      v8 = 2;
      if ( !v7 )
        return v8;
      v29 = (struct REGION *)*((_QWORD *)this + 20);
      --*(_DWORD *)(v7 + 76);
      if ( !*((_DWORD *)v29 + 19) )
        RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v29);
      *((_QWORD *)this + 20) = 0;
      goto LABEL_7;
    }
  }
  else if ( a3 != 1 || !a2 || v7 )
  {
    v29 = a2;
    RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v28);
    if ( !v28 )
      return v8;
    if ( v7 )
    {
      v27 = v7;
      v8 = RGNOBJ::iCombine((RGNOBJ *)&v28, (struct RGNOBJ *)&v27, (struct RGNOBJ *)&v29, a3);
      if ( v8 )
      {
        ++*(_DWORD *)(v28 + 76);
        *((_QWORD *)this + 20) = v28;
        DC::vReleaseRao(this, v9);
        --*(_DWORD *)(v27 + 76);
LABEL_20:
        if ( *(_DWORD *)(v27 + 76) )
          return v8;
        v12 = (RGNOBJ *)&v27;
LABEL_26:
        RGNOBJ::vDeleteRGNOBJ(v12);
        return v8;
      }
    }
    else
    {
      v27 = 0;
      RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v27, 0x70u);
      RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v27);
      if ( v27 )
      {
        v18 = DC::bDpiScaledSurface(this);
        v19 = (char *)this + 532;
        if ( !v18 )
          v19 = (char *)this + 512;
        v20 = *(_QWORD *)v19;
        left = 0;
        v22 = *(_QWORD *)v19;
        *(_QWORD *)&v31.left = 0;
        v23 = HIDWORD(v22);
        top = 0;
        v31.right = v20;
        v31.bottom = v23;
        if ( *((_QWORD *)this + 62) )
        {
          v26 = (const struct _POINTL *)*((_QWORD *)this + 6);
          SEMOBJSHARED<1>::SEMOBJSHARED<1>(&v30, v23, 0, 0);
          if ( (v26[5].x & 0x20000) != 0 && *(int *)(*((_QWORD *)this + 62) + 160LL) < 0 )
            ERECTL::bOffsetAdd((ERECTL *)&v31, v26 + 322, 0);
          GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v30);
          LODWORD(v23) = v31.bottom;
          LODWORD(v20) = v31.right;
          top = v31.top;
          left = v31.left;
        }
        v25 = (char *)this + 1024;
        if ( (*((_DWORD *)this + 10) & 1) == 0 )
          v25 = (char *)this + 1016;
        v13 = left - *(_DWORD *)v25;
        v31.right = v20 - *(_DWORD *)v25;
        v14 = *((_DWORD *)v25 + 1);
        v31.left = v13;
        v31.bottom = v23 - v14;
        v31.top = top - v14;
        RGNOBJ::vSet((RGNOBJ *)&v27, &v31);
        v8 = RGNOBJ::iCombine((RGNOBJ *)&v28, (struct RGNOBJ *)&v27, (struct RGNOBJ *)&v29, a3);
        if ( v8 )
        {
          ++*(_DWORD *)(v28 + 76);
          *((_QWORD *)this + 20) = v28;
          DC::vReleaseRao(this, v9);
        }
      }
      RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v27);
      RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v27);
      if ( v8 )
        return v8;
    }
    v12 = (RGNOBJ *)&v28;
    goto LABEL_26;
  }
  v29 = a2;
  v27 = v7;
  if ( !v7 || *(_DWORD *)(v7 + 76) != 1 )
  {
    sizeScan = REGION_CORE::get_sizeScan((struct REGION *)((char *)a2 + 24));
    RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v28, sizeScan);
    if ( !v28 )
      return v8;
    RGNOBJ::vCopy((RGNOBJ *)&v28, (struct RGNOBJ *)&v29);
    ++*(_DWORD *)(v28 + 76);
    v16 = v28;
    v17 = RGNOBJ::iComplexity((RGNOBJ *)&v28);
    *((_QWORD *)this + 20) = v16;
    v8 = v17;
    DC::vReleaseRao(this, v9);
    if ( !v7 )
      return v8;
    --*(_DWORD *)(v27 + 76);
    goto LABEL_20;
  }
  if ( RGNOBJ::bCopy((RGNOBJ *)&v27, (struct RGNOBJ *)&v29) )
  {
    v10 = v27;
    v8 = RGNOBJ::iComplexity((RGNOBJ *)&v27);
    *((_QWORD *)this + 20) = v10;
LABEL_7:
    DC::vReleaseRao(this, v9);
  }
  return v8;
}

```

## disassembly

```asm
0x140081a54  mov     [rsp-28h+arg_8], rbx
0x140081a59  mov     [rsp-28h+arg_18], rsi
0x140081a5e  push    rbp
0x140081a5f  push    rdi
0x140081a60  push    r12
0x140081a62  push    r14
0x140081a64  push    r15
0x140081a66  mov     rbp, rsp
0x140081a69  sub     rsp, 60h
0x140081a6d  mov     rax, cs:__security_cookie
0x140081a74  xor     rax, rsp
0x140081a77  mov     [rbp+var_10], rax
0x140081a7b  mov     r12d, r8d
0x140081a7e  mov     rbx, rdx
0x140081a81  mov     rdi, rcx
0x140081a84  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140081a8b  nop     dword ptr [rax+rax+00h]
0x140081a90  mov     rsi, [rdi+0A0h]
0x140081a97  xor     r14d, r14d
0x140081a9a  mov     r15, rax
0x140081a9d  cmp     r12d, 5
0x140081aa1  jnz     loc_140081B6E
0x140081aa7  test    rbx, rbx
0x140081aaa  jz      loc_140081B35
0x140081ab0  mov     [rbp+var_30], rbx
0x140081ab4  mov     [rbp+var_40], rsi
0x140081ab8  test    rsi, rsi
0x140081abb  jz      loc_140081CAC
0x140081ac1  cmp     dword ptr [rsi+4Ch], 1
0x140081ac5  jnz     loc_140081CAC
0x140081acb  lea     rdx, [rbp+var_30]
0x140081acf  lea     rcx, [rbp+var_40]
0x140081ad3  call    cs:__imp_?bCopy@RGNOBJ@@QEAAHAEAV1@@Z; RGNOBJ::bCopy(RGNOBJ &)
0x140081ada  nop     dword ptr [rax+rax+00h]
0x140081adf  test    eax, eax
0x140081ae1  jz      short loc_140081B0C
0x140081ae3  mov     rbx, [rbp+var_40]
0x140081ae7  lea     rcx, [rbp+var_40]; this
0x140081aeb  call    ?iComplexity@RGNOBJ@@QEBAJXZ; RGNOBJ::iComplexity(void)
0x140081af0  mov     r14d, eax
0x140081af3  mov     [rdi+0A0h], rbx
0x140081afa  mov     rdx, r15
0x140081afd  mov     rcx, rdi
0x140081b00  call    cs:__imp_?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::vReleaseRao(Gre::Base::SESSION_GLOBALS &)
0x140081b07  nop     dword ptr [rax+rax+00h]
0x140081b0c  mov     eax, r14d
0x140081b0f  mov     rcx, [rbp+var_10]
0x140081b13  xor     rcx, rsp; StackCookie
0x140081b16  call    __security_check_cookie
0x140081b1b  lea     r11, [rsp+60h+var_s0]
0x140081b20  mov     rbx, [r11+38h]
0x140081b24  mov     rsi, [r11+48h]
0x140081b28  mov     rsp, r11
0x140081b2b  pop     r15
0x140081b2d  pop     r14
0x140081b2f  pop     r12
0x140081b31  pop     rdi
0x140081b32  pop     rbp
0x140081b33  retn
0x140081b35  mov     r14d, 2
0x140081b3b  test    rsi, rsi
0x140081b3e  jz      short loc_140081B0C
0x140081b40  mov     [rbp+var_30], rsi
0x140081b44  dec     dword ptr [rsi+4Ch]
0x140081b47  mov     rax, [rbp+var_30]
0x140081b4b  cmp     dword ptr [rax+4Ch], 0
0x140081b4f  jnz     short loc_140081B61
0x140081b51  lea     rcx, [rbp+var_30]
0x140081b55  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x140081b5c  nop     dword ptr [rax+rax+00h]
0x140081b61  mov     qword ptr [rdi+0A0h], 0
0x140081b6c  jmp     short loc_140081AFA
0x140081b6e  cmp     r12d, 1
0x140081b72  jnz     short loc_140081B82
0x140081b74  test    rbx, rbx
0x140081b77  jz      short loc_140081B82
0x140081b79  test    rsi, rsi
0x140081b7c  jz      loc_140081AB0
0x140081b82  lea     rcx, [rbp+var_38]
0x140081b86  mov     [rbp+var_30], rbx
0x140081b8a  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x140081b91  nop     dword ptr [rax+rax+00h]
0x140081b96  cmp     [rbp+var_38], r14
0x140081b9a  jz      loc_140081B0C
0x140081ba0  test    rsi, rsi
0x140081ba3  jz      loc_140081D2A
0x140081ba9  mov     r9d, r12d
0x140081bac  mov     [rbp+var_40], rsi
0x140081bb0  lea     r8, [rbp+var_30]
0x140081bb4  lea     rdx, [rbp+var_40]
0x140081bb8  lea     rcx, [rbp+var_38]
0x140081bbc  call    cs:__imp_?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z; RGNOBJ::iCombine(RGNOBJ &,RGNOBJ &,long)
0x140081bc3  nop     dword ptr [rax+rax+00h]
0x140081bc8  mov     r14d, eax
0x140081bcb  test    eax, eax
0x140081bcd  jz      loc_140081C97
0x140081bd3  mov     rdx, [rbp+var_38]
0x140081bd7  mov     rcx, rdi
0x140081bda  inc     dword ptr [rdx+4Ch]
0x140081bdd  mov     rdx, [rbp+var_38]
0x140081be1  mov     [rdi+0A0h], rdx
0x140081be8  mov     rdx, r15
0x140081beb  call    cs:__imp_?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::vReleaseRao(Gre::Base::SESSION_GLOBALS &)
0x140081bf2  nop     dword ptr [rax+rax+00h]
0x140081bf7  mov     rcx, [rbp+var_40]
0x140081bfb  dec     dword ptr [rcx+4Ch]
0x140081bfe  mov     rax, [rbp+var_40]
0x140081c02  cmp     dword ptr [rax+4Ch], 0
0x140081c06  jnz     loc_140081B0C
0x140081c0c  lea     rcx, [rbp+var_40]
0x140081c10  jmp     loc_140081C9B
0x140081c15  mov     ecx, [r10]
0x140081c18  sub     eax, ecx
0x140081c1a  sub     r8d, ecx
0x140081c1d  mov     [rbp+var_18], eax
0x140081c20  mov     eax, [r10+4]
0x140081c24  lea     rcx, [rbp+var_40]
0x140081c28  sub     edx, eax
0x140081c2a  mov     dword ptr [rbp+var_20], r8d
0x140081c2e  mov     [rbp+var_14], edx
0x140081c31  sub     r9d, eax
0x140081c34  lea     rdx, [rbp+var_20]
0x140081c38  mov     dword ptr [rbp+var_20+4], r9d
0x140081c3c  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x140081c43  nop     dword ptr [rax+rax+00h]
0x140081c48  mov     r9d, r12d
0x140081c4b  lea     r8, [rbp+var_30]
0x140081c4f  lea     rdx, [rbp+var_40]
0x140081c53  lea     rcx, [rbp+var_38]
0x140081c57  call    cs:__imp_?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z; RGNOBJ::iCombine(RGNOBJ &,RGNOBJ &,long)
0x140081c5e  nop     dword ptr [rax+rax+00h]
0x140081c63  mov     r14d, eax
0x140081c66  test    eax, eax
0x140081c68  jnz     loc_140081E17
0x140081c6e  lea     rcx, [rbp+var_40]
0x140081c72  call    cs:__imp_?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPopThreadGuardedObject(void)
0x140081c79  nop     dword ptr [rax+rax+00h]
0x140081c7e  lea     rcx, [rbp+var_40]
0x140081c82  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x140081c89  nop     dword ptr [rax+rax+00h]
0x140081c8e  test    r14d, r14d
0x140081c91  jnz     loc_140081B0C
0x140081c97  lea     rcx, [rbp+var_38]
0x140081c9b  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x140081ca2  nop     dword ptr [rax+rax+00h]
0x140081ca7  jmp     loc_140081B0C
0x140081cac  lea     rcx, [rbx+18h]; this
0x140081cb0  call    ?get_sizeScan@REGION_CORE@@IEBAKXZ; REGION_CORE::get_sizeScan(void)
0x140081cb5  mov     edx, eax
0x140081cb7  lea     rcx, [rbp+var_38]
0x140081cbb  call    cs:__imp_??0RGNMEMOBJ@@QEAA@K@Z; RGNMEMOBJ::RGNMEMOBJ(ulong)
0x140081cc2  nop     dword ptr [rax+rax+00h]
0x140081cc7  cmp     [rbp+var_38], r14
0x140081ccb  jz      loc_140081B0C
0x140081cd1  lea     rdx, [rbp+var_30]
0x140081cd5  lea     rcx, [rbp+var_38]
0x140081cd9  call    cs:__imp_?vCopy@RGNOBJ@@QEAAXAEAV1@@Z; RGNOBJ::vCopy(RGNOBJ &)
0x140081ce0  nop     dword ptr [rax+rax+00h]
0x140081ce5  mov     rax, [rbp+var_38]
0x140081ce9  lea     rcx, [rbp+var_38]; this
0x140081ced  inc     dword ptr [rax+4Ch]
0x140081cf0  mov     rbx, [rbp+var_38]
0x140081cf4  call    ?iComplexity@RGNOBJ@@QEBAJXZ; RGNOBJ::iComplexity(void)
0x140081cf9  mov     rdx, r15
0x140081cfc  mov     [rdi+0A0h], rbx
0x140081d03  mov     rcx, rdi
0x140081d06  mov     r14d, eax
0x140081d09  call    cs:__imp_?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::vReleaseRao(Gre::Base::SESSION_GLOBALS &)
0x140081d10  nop     dword ptr [rax+rax+00h]
0x140081d15  test    rsi, rsi
0x140081d18  jz      loc_140081B0C
0x140081d1e  mov     rax, [rbp+var_40]
0x140081d22  dec     dword ptr [rax+4Ch]
0x140081d25  jmp     loc_140081BFE
0x140081d2a  mov     edx, 70h ; 'p'
0x140081d2f  mov     [rbp+var_40], r14
0x140081d33  lea     rcx, [rbp+var_40]
0x140081d37  call    cs:__imp_?vInitialize@RGNMEMOBJ@@QEAAXK@Z; RGNMEMOBJ::vInitialize(ulong)
0x140081d3e  nop     dword ptr [rax+rax+00h]
0x140081d43  lea     rcx, [rbp+var_40]
0x140081d47  call    cs:__imp_?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPushThreadGuardedObject(void)
0x140081d4e  nop     dword ptr [rax+rax+00h]
0x140081d53  cmp     [rbp+var_40], r14
0x140081d57  jz      loc_140081C6E
0x140081d5d  mov     rcx, rdi; this
0x140081d60  call    ?bDpiScaledSurface@DC@@QEBAHXZ; DC::bDpiScaledSurface(void)
0x140081d65  lea     rcx, [rdi+214h]
0x140081d6c  test    eax, eax
0x140081d6e  jz      short loc_140081DB2
0x140081d70  mov     rax, [rcx]
0x140081d73  xor     r8d, r8d
0x140081d76  mov     rdx, rax
0x140081d79  mov     [rbp+var_20], r8
0x140081d7d  shr     rdx, 20h
0x140081d81  xor     r9d, r9d
0x140081d84  mov     [rbp+var_18], eax
0x140081d87  mov     [rbp+var_14], edx
0x140081d8a  cmp     [rdi+1F0h], r8
0x140081d91  jnz     short loc_140081DBB
0x140081d93  mov     ecx, [rdi+28h]
0x140081d96  lea     r10, [rdi+400h]
0x140081d9d  test    cl, 1
0x140081da0  jnz     loc_140081C15
0x140081da6  lea     r10, [rdi+3F8h]
0x140081dad  jmp     loc_140081C15
0x140081db2  lea     rcx, [rdi+200h]
0x140081db9  jmp     short loc_140081D70
0x140081dbb  mov     rbx, [rdi+30h]
0x140081dbf  lea     rcx, [rbp+var_28]
0x140081dc3  call    ??0?$SEMOBJSHARED@$00@@QEAA@XZ; SEMOBJSHARED<1>::SEMOBJSHARED<1>(void)
0x140081dc8  test    dword ptr [rbx+28h], 20000h
0x140081dcf  jz      short loc_140081DF4
0x140081dd1  mov     rax, [rdi+1F0h]
0x140081dd8  cmp     [rax+0A0h], r14d
0x140081ddf  jge     short loc_140081DF4
0x140081de1  lea     rdx, [rbx+0A10h]; struct _POINTL *
0x140081de8  xor     r8d, r8d; int
0x140081deb  lea     rcx, [rbp+var_20]; this
0x140081def  call    ?bOffsetAdd@ERECTL@@QEAAHAEBU_POINTL@@H@Z; ERECTL::bOffsetAdd(_POINTL const &,int)
0x140081df4  mov     rdx, [rbp+var_28]
0x140081df8  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140081dff  call    ??$GreReleaseSemaphoreCommon@$00P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140081e04  mov     edx, [rbp+var_14]
0x140081e07  mov     eax, [rbp+var_18]
0x140081e0a  mov     r9d, dword ptr [rbp+var_20+4]
0x140081e0e  mov     r8d, dword ptr [rbp+var_20]
0x140081e12  jmp     loc_140081D93
0x140081e17  mov     rax, [rbp+var_38]
0x140081e1b  mov     rdx, r15
0x140081e1e  mov     rcx, rdi
0x140081e21  inc     dword ptr [rax+4Ch]
0x140081e24  mov     rax, [rbp+var_38]
0x140081e28  mov     [rdi+0A0h], rax
0x140081e2f  call    cs:__imp_?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::vReleaseRao(Gre::Base::SESSION_GLOBALS &)
0x140081e36  nop     dword ptr [rax+rax+00h]
0x140081e3b  jmp     loc_140081C6E
```
