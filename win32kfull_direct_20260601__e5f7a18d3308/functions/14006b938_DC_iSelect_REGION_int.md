# DC::iSelect(REGION *,int)

- ea: `0x14006b938`
- end: `0x14006bd24`
- name: `?iSelect@DC@@QEAAHPEAVREGION@@H@Z`
- size: `1004`
- prototype: `__int64 __fastcall(DC *__hidden this, struct REGION *, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140069c70`
- `0x14006b5c4`
- `0x14022b650`

## callees

- `0x1400684f8`
- `0x140069bc8`
- `0x14006b938`
- `0x14008e384`
- `0x14018f558`
- `0x1401ad190`
- `0x1401d737c`
- `0x140342fa0`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14006b968`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14006b968`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x14006bcdc`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14006bc2b`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14006bc2b`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x14006bc1b`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x14006bc1b`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14006ba39`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14006bb66`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14006bb7f`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14006ba39`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14006bb66`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14006bb7f`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14006bb56`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14006bb56`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14006bb20`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14006bb20`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14006ba6e`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14006ba6e`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x14006b9b7`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x14006b9b7`
- `win32kbase!?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z` at `0x14006baa0`
- `win32kbase!?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z` at `0x14006bb3b`
- `win32kbase!?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z` at `0x14006baa0`
- `win32kbase!?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z` at `0x14006bb3b`
- `win32kbase!??0RGNMEMOBJ@@QEAA@K@Z` at `0x14006bb9f`
- `win32kbase!??0RGNMEMOBJ@@QEAA@K@Z` at `0x14006bb9f`
- `win32kbase!?vCopy@RGNOBJ@@QEAAXAEAV1@@Z` at `0x14006bbbd`
- `win32kbase!?vCopy@RGNOBJ@@QEAAXAEAV1@@Z` at `0x14006bbbd`
- `win32kbase!?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z` at `0x14006b9e4`
- `win32kbase!?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z` at `0x14006bacf`
- `win32kbase!?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z` at `0x14006bbed`
- `win32kbase!?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z` at `0x14006bd13`
- `win32kbase!?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z` at `0x14006b9e4`
- `win32kbase!?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z` at `0x14006bacf`
- `win32kbase!?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z` at `0x14006bbed`
- `win32kbase!?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z` at `0x14006bd13`

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
          SEMOBJSHARED<1>::SEMOBJSHARED<1>(&v30);
          if ( (v26[5].x & 0x20000) != 0 && *(int *)(*((_QWORD *)this + 62) + 144LL) < 0 )
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
0x14006b938  mov     [rsp-28h+arg_8], rbx
0x14006b93d  mov     [rsp-28h+arg_18], rsi
0x14006b942  push    rbp
0x14006b943  push    rdi
0x14006b944  push    r12
0x14006b946  push    r14
0x14006b948  push    r15
0x14006b94a  mov     rbp, rsp
0x14006b94d  sub     rsp, 60h
0x14006b951  mov     rax, cs:__security_cookie
0x14006b958  xor     rax, rsp
0x14006b95b  mov     [rbp+var_10], rax
0x14006b95f  mov     r12d, r8d
0x14006b962  mov     rbx, rdx
0x14006b965  mov     rdi, rcx
0x14006b968  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14006b96f  nop     dword ptr [rax+rax+00h]
0x14006b974  mov     rsi, [rdi+0A0h]
0x14006b97b  xor     r14d, r14d
0x14006b97e  mov     r15, rax
0x14006b981  cmp     r12d, 5
0x14006b985  jnz     loc_14006BA52
0x14006b98b  test    rbx, rbx
0x14006b98e  jz      loc_14006BA19
0x14006b994  mov     [rbp+var_30], rbx
0x14006b998  mov     [rbp+var_40], rsi
0x14006b99c  test    rsi, rsi
0x14006b99f  jz      loc_14006BB90
0x14006b9a5  cmp     dword ptr [rsi+4Ch], 1
0x14006b9a9  jnz     loc_14006BB90
0x14006b9af  lea     rdx, [rbp+var_30]
0x14006b9b3  lea     rcx, [rbp+var_40]
0x14006b9b7  call    cs:__imp_?bCopy@RGNOBJ@@QEAAHAEAV1@@Z; RGNOBJ::bCopy(RGNOBJ &)
0x14006b9be  nop     dword ptr [rax+rax+00h]
0x14006b9c3  test    eax, eax
0x14006b9c5  jz      short loc_14006B9F0
0x14006b9c7  mov     rbx, [rbp+var_40]
0x14006b9cb  lea     rcx, [rbp+var_40]; this
0x14006b9cf  call    ?iComplexity@RGNOBJ@@QEBAJXZ; RGNOBJ::iComplexity(void)
0x14006b9d4  mov     r14d, eax
0x14006b9d7  mov     [rdi+0A0h], rbx
0x14006b9de  mov     rdx, r15
0x14006b9e1  mov     rcx, rdi
0x14006b9e4  call    cs:__imp_?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::vReleaseRao(Gre::Base::SESSION_GLOBALS &)
0x14006b9eb  nop     dword ptr [rax+rax+00h]
0x14006b9f0  mov     eax, r14d
0x14006b9f3  mov     rcx, [rbp+var_10]
0x14006b9f7  xor     rcx, rsp; StackCookie
0x14006b9fa  call    __security_check_cookie
0x14006b9ff  lea     r11, [rsp+60h+var_s0]
0x14006ba04  mov     rbx, [r11+38h]
0x14006ba08  mov     rsi, [r11+48h]
0x14006ba0c  mov     rsp, r11
0x14006ba0f  pop     r15
0x14006ba11  pop     r14
0x14006ba13  pop     r12
0x14006ba15  pop     rdi
0x14006ba16  pop     rbp
0x14006ba17  retn
0x14006ba19  mov     r14d, 2
0x14006ba1f  test    rsi, rsi
0x14006ba22  jz      short loc_14006B9F0
0x14006ba24  mov     [rbp+var_30], rsi
0x14006ba28  dec     dword ptr [rsi+4Ch]
0x14006ba2b  mov     rax, [rbp+var_30]
0x14006ba2f  cmp     dword ptr [rax+4Ch], 0
0x14006ba33  jnz     short loc_14006BA45
0x14006ba35  lea     rcx, [rbp+var_30]
0x14006ba39  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14006ba40  nop     dword ptr [rax+rax+00h]
0x14006ba45  mov     qword ptr [rdi+0A0h], 0
0x14006ba50  jmp     short loc_14006B9DE
0x14006ba52  cmp     r12d, 1
0x14006ba56  jnz     short loc_14006BA66
0x14006ba58  test    rbx, rbx
0x14006ba5b  jz      short loc_14006BA66
0x14006ba5d  test    rsi, rsi
0x14006ba60  jz      loc_14006B994
0x14006ba66  lea     rcx, [rbp+var_38]
0x14006ba6a  mov     [rbp+var_30], rbx
0x14006ba6e  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x14006ba75  nop     dword ptr [rax+rax+00h]
0x14006ba7a  cmp     [rbp+var_38], r14
0x14006ba7e  jz      loc_14006B9F0
0x14006ba84  test    rsi, rsi
0x14006ba87  jz      loc_14006BC0E
0x14006ba8d  mov     r9d, r12d
0x14006ba90  mov     [rbp+var_40], rsi
0x14006ba94  lea     r8, [rbp+var_30]
0x14006ba98  lea     rdx, [rbp+var_40]
0x14006ba9c  lea     rcx, [rbp+var_38]
0x14006baa0  call    cs:__imp_?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z; RGNOBJ::iCombine(RGNOBJ &,RGNOBJ &,long)
0x14006baa7  nop     dword ptr [rax+rax+00h]
0x14006baac  mov     r14d, eax
0x14006baaf  test    eax, eax
0x14006bab1  jz      loc_14006BB7B
0x14006bab7  mov     rdx, [rbp+var_38]
0x14006babb  mov     rcx, rdi
0x14006babe  inc     dword ptr [rdx+4Ch]
0x14006bac1  mov     rdx, [rbp+var_38]
0x14006bac5  mov     [rdi+0A0h], rdx
0x14006bacc  mov     rdx, r15
0x14006bacf  call    cs:__imp_?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::vReleaseRao(Gre::Base::SESSION_GLOBALS &)
0x14006bad6  nop     dword ptr [rax+rax+00h]
0x14006badb  mov     rcx, [rbp+var_40]
0x14006badf  dec     dword ptr [rcx+4Ch]
0x14006bae2  mov     rax, [rbp+var_40]
0x14006bae6  cmp     dword ptr [rax+4Ch], 0
0x14006baea  jnz     loc_14006B9F0
0x14006baf0  lea     rcx, [rbp+var_40]
0x14006baf4  jmp     loc_14006BB7F
0x14006baf9  mov     ecx, [r10]
0x14006bafc  sub     eax, ecx
0x14006bafe  sub     r8d, ecx
0x14006bb01  mov     [rbp+var_18], eax
0x14006bb04  mov     eax, [r10+4]
0x14006bb08  lea     rcx, [rbp+var_40]
0x14006bb0c  sub     edx, eax
0x14006bb0e  mov     dword ptr [rbp+var_20], r8d
0x14006bb12  mov     [rbp+var_14], edx
0x14006bb15  sub     r9d, eax
0x14006bb18  lea     rdx, [rbp+var_20]
0x14006bb1c  mov     dword ptr [rbp+var_20+4], r9d
0x14006bb20  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x14006bb27  nop     dword ptr [rax+rax+00h]
0x14006bb2c  mov     r9d, r12d
0x14006bb2f  lea     r8, [rbp+var_30]
0x14006bb33  lea     rdx, [rbp+var_40]
0x14006bb37  lea     rcx, [rbp+var_38]
0x14006bb3b  call    cs:__imp_?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z; RGNOBJ::iCombine(RGNOBJ &,RGNOBJ &,long)
0x14006bb42  nop     dword ptr [rax+rax+00h]
0x14006bb47  mov     r14d, eax
0x14006bb4a  test    eax, eax
0x14006bb4c  jnz     loc_14006BCFB
0x14006bb52  lea     rcx, [rbp+var_40]
0x14006bb56  call    cs:__imp_?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPopThreadGuardedObject(void)
0x14006bb5d  nop     dword ptr [rax+rax+00h]
0x14006bb62  lea     rcx, [rbp+var_40]
0x14006bb66  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14006bb6d  nop     dword ptr [rax+rax+00h]
0x14006bb72  test    r14d, r14d
0x14006bb75  jnz     loc_14006B9F0
0x14006bb7b  lea     rcx, [rbp+var_38]
0x14006bb7f  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14006bb86  nop     dword ptr [rax+rax+00h]
0x14006bb8b  jmp     loc_14006B9F0
0x14006bb90  lea     rcx, [rbx+18h]; this
0x14006bb94  call    ?get_sizeScan@REGION_CORE@@IEBAKXZ; REGION_CORE::get_sizeScan(void)
0x14006bb99  mov     edx, eax
0x14006bb9b  lea     rcx, [rbp+var_38]
0x14006bb9f  call    cs:__imp_??0RGNMEMOBJ@@QEAA@K@Z; RGNMEMOBJ::RGNMEMOBJ(ulong)
0x14006bba6  nop     dword ptr [rax+rax+00h]
0x14006bbab  cmp     [rbp+var_38], r14
0x14006bbaf  jz      loc_14006B9F0
0x14006bbb5  lea     rdx, [rbp+var_30]
0x14006bbb9  lea     rcx, [rbp+var_38]
0x14006bbbd  call    cs:__imp_?vCopy@RGNOBJ@@QEAAXAEAV1@@Z; RGNOBJ::vCopy(RGNOBJ &)
0x14006bbc4  nop     dword ptr [rax+rax+00h]
0x14006bbc9  mov     rax, [rbp+var_38]
0x14006bbcd  lea     rcx, [rbp+var_38]; this
0x14006bbd1  inc     dword ptr [rax+4Ch]
0x14006bbd4  mov     rbx, [rbp+var_38]
0x14006bbd8  call    ?iComplexity@RGNOBJ@@QEBAJXZ; RGNOBJ::iComplexity(void)
0x14006bbdd  mov     rdx, r15
0x14006bbe0  mov     [rdi+0A0h], rbx
0x14006bbe7  mov     rcx, rdi
0x14006bbea  mov     r14d, eax
0x14006bbed  call    cs:__imp_?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::vReleaseRao(Gre::Base::SESSION_GLOBALS &)
0x14006bbf4  nop     dword ptr [rax+rax+00h]
0x14006bbf9  test    rsi, rsi
0x14006bbfc  jz      loc_14006B9F0
0x14006bc02  mov     rax, [rbp+var_40]
0x14006bc06  dec     dword ptr [rax+4Ch]
0x14006bc09  jmp     loc_14006BAE2
0x14006bc0e  mov     edx, 70h ; 'p'
0x14006bc13  mov     [rbp+var_40], r14
0x14006bc17  lea     rcx, [rbp+var_40]
0x14006bc1b  call    cs:__imp_?vInitialize@RGNMEMOBJ@@QEAAXK@Z; RGNMEMOBJ::vInitialize(ulong)
0x14006bc22  nop     dword ptr [rax+rax+00h]
0x14006bc27  lea     rcx, [rbp+var_40]
0x14006bc2b  call    cs:__imp_?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPushThreadGuardedObject(void)
0x14006bc32  nop     dword ptr [rax+rax+00h]
0x14006bc37  cmp     [rbp+var_40], r14
0x14006bc3b  jz      loc_14006BB52
0x14006bc41  mov     rcx, rdi; this
0x14006bc44  call    ?bDpiScaledSurface@DC@@QEBAHXZ; DC::bDpiScaledSurface(void)
0x14006bc49  lea     rcx, [rdi+214h]
0x14006bc50  test    eax, eax
0x14006bc52  jz      short loc_14006BC96
0x14006bc54  mov     rax, [rcx]
0x14006bc57  xor     r8d, r8d
0x14006bc5a  mov     rdx, rax
0x14006bc5d  mov     [rbp+var_20], r8
0x14006bc61  shr     rdx, 20h
0x14006bc65  xor     r9d, r9d
0x14006bc68  mov     [rbp+var_18], eax
0x14006bc6b  mov     [rbp+var_14], edx
0x14006bc6e  cmp     [rdi+1F0h], r8
0x14006bc75  jnz     short loc_14006BC9F
0x14006bc77  mov     ecx, [rdi+28h]
0x14006bc7a  lea     r10, [rdi+400h]
0x14006bc81  test    cl, 1
0x14006bc84  jnz     loc_14006BAF9
0x14006bc8a  lea     r10, [rdi+3F8h]
0x14006bc91  jmp     loc_14006BAF9
0x14006bc96  lea     rcx, [rdi+200h]
0x14006bc9d  jmp     short loc_14006BC54
0x14006bc9f  mov     rbx, [rdi+30h]
0x14006bca3  lea     rcx, [rbp+var_28]
0x14006bca7  call    ??0?$SEMOBJSHARED@$00@@QEAA@XZ; SEMOBJSHARED<1>::SEMOBJSHARED<1>(void)
0x14006bcac  test    dword ptr [rbx+28h], 20000h
0x14006bcb3  jz      short loc_14006BCD8
0x14006bcb5  mov     rax, [rdi+1F0h]
0x14006bcbc  cmp     [rax+90h], r14d
0x14006bcc3  jge     short loc_14006BCD8
0x14006bcc5  lea     rdx, [rbx+0A10h]; struct _POINTL *
0x14006bccc  xor     r8d, r8d; int
0x14006bccf  lea     rcx, [rbp+var_20]; this
0x14006bcd3  call    ?bOffsetAdd@ERECTL@@QEAAHAEBU_POINTL@@H@Z; ERECTL::bOffsetAdd(_POINTL const &,int)
0x14006bcd8  mov     rdx, [rbp+var_28]
0x14006bcdc  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14006bce3  call    ??$GreReleaseSemaphoreCommon@$00P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x14006bce8  mov     edx, [rbp+var_14]
0x14006bceb  mov     eax, [rbp+var_18]
0x14006bcee  mov     r9d, dword ptr [rbp+var_20+4]
0x14006bcf2  mov     r8d, dword ptr [rbp+var_20]
0x14006bcf6  jmp     loc_14006BC77
0x14006bcfb  mov     rax, [rbp+var_38]
0x14006bcff  mov     rdx, r15
0x14006bd02  mov     rcx, rdi
0x14006bd05  inc     dword ptr [rax+4Ch]
0x14006bd08  mov     rax, [rbp+var_38]
0x14006bd0c  mov     [rdi+0A0h], rax
0x14006bd13  call    cs:__imp_?vReleaseRao@DC@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::vReleaseRao(Gre::Base::SESSION_GLOBALS &)
0x14006bd1a  nop     dword ptr [rax+rax+00h]
0x14006bd1f  jmp     loc_14006BB52
```
