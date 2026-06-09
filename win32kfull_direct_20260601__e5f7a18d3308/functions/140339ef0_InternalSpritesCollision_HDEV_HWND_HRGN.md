# InternalSpritesCollision(HDEV__ *,HWND__ *,HRGN__ *)

- ea: `0x140339ef0`
- end: `0x14033a2bc`
- name: `?InternalSpritesCollision@@YAHPEAUHDEV__@@PEAUHWND__@@PEAUHRGN__@@@Z`
- size: `972`
- prototype: `__int64 __fastcall(HDEV, HWND, HRGN)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14033a570`

## callees

- `0x140019864`
- `0x1400876f0`
- `0x14008cfa0`
- `0x14009b5e8`
- `0x14009bea0`
- `0x1400a9b80`
- `0x14011a004`
- `0x14018f558`
- `0x1403088bc`
- `0x140308ba8`
- `0x140339ef0`
- `0x140342fa0`

## import_xrefs

- `win32kbase!GreGetRgnBox` at `0x14033a187`
- `win32kbase!GreGetRgnBox` at `0x14033a187`
- `win32kbase!?bInside@RGNOBJ@@QEAAHPEAU_RECTL@@@Z` at `0x140339f6d`
- `win32kbase!?bInside@RGNOBJ@@QEAAHPEAU_RECTL@@@Z` at `0x140339f6d`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x140339f35`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x14033a0ba`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x14033a0d5`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x140339f35`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x14033a0ba`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x14033a0d5`
- `win32kbase!?iCombine@RGNOBJAPI@@QEAAJAEAVRGNOBJ@@0J@Z` at `0x14033a10a`
- `win32kbase!?iCombine@RGNOBJAPI@@QEAAJAEAVRGNOBJ@@0J@Z` at `0x14033a10a`
- `win32kbase!GreCreateRectRgn` at `0x140339fb1`
- `win32kbase!GreCreateRectRgn` at `0x140339fd3`
- `win32kbase!GreCreateRectRgn` at `0x140339fed`
- `win32kbase!GreCreateRectRgn` at `0x14033a006`
- `win32kbase!GreCreateRectRgn` at `0x140339fb1`
- `win32kbase!GreCreateRectRgn` at `0x140339fd3`
- `win32kbase!GreCreateRectRgn` at `0x140339fed`
- `win32kbase!GreCreateRectRgn` at `0x14033a006`
- `win32kbase!GreSetRectRgn` at `0x14033a051`
- `win32kbase!GreSetRectRgn` at `0x14033a160`
- `win32kbase!GreSetRectRgn` at `0x14033a051`
- `win32kbase!GreSetRectRgn` at `0x14033a160`
- `win32kbase!GreCombineRgn` at `0x14033a1ad`
- `win32kbase!GreCombineRgn` at `0x14033a1ff`
- `win32kbase!GreCombineRgn` at `0x14033a1ad`
- `win32kbase!GreCombineRgn` at `0x14033a1ff`
- `win32kbase!GreOffsetRgn` at `0x14033a1dd`
- `win32kbase!GreOffsetRgn` at `0x14033a1dd`
- `win32kbase!GreDeleteObject` at `0x14033a24e`
- `win32kbase!GreDeleteObject` at `0x14033a262`
- `win32kbase!GreDeleteObject` at `0x14033a276`
- `win32kbase!GreDeleteObject` at `0x14033a285`
- `win32kbase!GreDeleteObject` at `0x14033a24e`
- `win32kbase!GreDeleteObject` at `0x14033a262`
- `win32kbase!GreDeleteObject` at `0x14033a276`
- `win32kbase!GreDeleteObject` at `0x14033a285`
- `WIN32K!W32GetSessionState` at `0x14033a074`
- `WIN32K!W32GetSessionState` at `0x14033a137`
- `WIN32K!W32GetSessionState` at `0x14033a074`
- `WIN32K!W32GetSessionState` at `0x14033a137`

## pseudocode

```c
__int64 __fastcall InternalSpritesCollision(HDEV a1, HWND a2, HRGN a3)
{
  unsigned int v5; // r14d
  HRGN RectRgn; // rsi
  HRGN v7; // rdi
  __int64 v8; // rax
  HRGN v9; // r13
  HRGN v10; // r12
  unsigned int v11; // r13d
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // ebx
  __int64 v21; // r13
  HRGN v22; // rax
  HRGN v23; // [rsp+30h] [rbp-79h]
  _QWORD v26[7]; // [rsp+48h] [rbp-61h] BYREF
  _QWORD v27[7]; // [rsp+80h] [rbp-29h] BYREF
  struct _RECTL v28; // [rsp+B8h] [rbp+Fh] BYREF

  RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)v26, a3, 0, 0);
  if ( !v26[0]
    || (v28 = *(struct _RECTL *)(a1 + 30),
        ERECTL::bOffsetAdd((ERECTL *)&v28, (const struct _POINTL *)a1 + 322, 0),
        RGNOBJ::bInside((RGNOBJ *)v26, &v28) == 2) )
  {
    v5 = 0;
    RGNOBJAPI::~RGNOBJAPI((RGNOBJAPI *)v26);
    if ( *((_DWORD *)a1 + 34) )
    {
      RectRgn = (HRGN)GreCreateRectRgn(0, 0, 0, 0);
      if ( RectRgn )
      {
        v23 = (HRGN)GreCreateRectRgn(0, 0, 0, 0);
        v7 = (HRGN)GreCreateRectRgn(0, 0, 0, 0);
        v8 = GreCreateRectRgn(0, 0, 0, 0);
        v9 = v23;
        v10 = (HRGN)v8;
        if ( v23 )
        {
          if ( v7
            && v8
            && (unsigned int)GreSetRectRgn(
                               v23,
                               *((unsigned int *)a1 + 30),
                               *((unsigned int *)a1 + 31),
                               *((unsigned int *)a1 + 32),
                               *((_DWORD *)a1 + 33)) )
          {
            v11 = 0;
            SPRITERANGELOCK::vLockExclusive((SPRITERANGELOCK *)(a1 + 50));
            if ( *(_DWORD *)(*(_QWORD *)(W32GetSessionState(v13, v12, v14, v15) + 96) + 136LL) == 1
              && *((_QWORD *)a1 + 141) )
            {
              vSpComputeUncoveredRegion((struct _SPRITESTATE *)(a1 + 20), 0);
            }
            SPRITERANGELOCK::vUnlockExclusive((SPRITERANGELOCK *)(a1 + 50));
            RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)v27, RectRgn, 0, 0);
            RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)v26, v23, 1, 0);
            *(_QWORD *)&v28.left = *((_QWORD *)a1 + 98);
            if ( v27[0] && v26[0] )
              v11 = RGNOBJAPI::iCombine((RGNOBJAPI *)v27, (struct RGNOBJ *)v26, (struct RGNOBJ *)&v28, 4);
            RGNOBJAPI::~RGNOBJAPI((RGNOBJAPI *)v26);
            RGNOBJAPI::~RGNOBJAPI((RGNOBJAPI *)v27);
            if ( v11 > 1 )
            {
              v20 = 0;
              v21 = *(_QWORD *)(W32GetSessionState(v17, v16, v18, v19) + 96);
              if ( *(_DWORD *)(v21 + 136) == 1 )
              {
                GreSetRectRgn(v7, 0, 0, 0, 0);
                if ( !(unsigned int)IsDwmActive() )
                  GdiGetSpriteClipRgns(a1, v7);
                GreGetRgnBox(v7, &v28);
                if ( !(unsigned int)ERECTL::bEmpty((ERECTL *)&v28)
                  && (unsigned int)GreCombineRgn(v10, RectRgn, v7, 1) > 1 )
                {
                  v22 = RectRgn;
                  v20 = 1;
                  RectRgn = v10;
                  v10 = v22;
                }
              }
              if ( (unsigned int)GreOffsetRgn(RectRgn, *((unsigned int *)a1 + 644), *((unsigned int *)a1 + 645)) > 1 )
              {
                if ( (unsigned int)GreCombineRgn(v23, RectRgn, a3, 1) > 1 )
                  v5 = 1;
                if ( *(_DWORD *)(v21 + 136) == 1 )
                {
                  if ( v5 )
                  {
                    GreDeleteSpriteOverlapPresent(a1);
                  }
                  else if ( v20 )
                  {
                    GreAddSpriteOverlapPresent(a1, a2);
                  }
                }
                else
                {
                  v5 = 1;
                }
              }
            }
            v9 = v23;
          }
          GreDeleteObject(v9);
        }
        if ( v7 )
          GreDeleteObject(v7);
        if ( v10 )
          GreDeleteObject(v10);
        GreDeleteObject(RectRgn);
      }
    }
    return v5;
  }
  else
  {
    RGNOBJAPI::~RGNOBJAPI((RGNOBJAPI *)v26);
    return 0;
  }
}

```

## disassembly

```asm
0x140339ef0  mov     [rsp-8+arg_18], rbx
0x140339ef5  push    rbp
0x140339ef6  push    rsi
0x140339ef7  push    rdi
0x140339ef8  push    r12
0x140339efa  push    r13
0x140339efc  push    r14
0x140339efe  push    r15
0x140339f00  lea     rbp, [rsp-27h]
0x140339f05  sub     rsp, 0D0h
0x140339f0c  mov     rax, cs:__security_cookie
0x140339f13  xor     rax, rsp
0x140339f16  mov     [rbp+57h+var_38], rax
0x140339f1a  mov     rax, r8
0x140339f1d  mov     [rbp+57h+var_C8], rdx
0x140339f21  mov     r15, rcx
0x140339f24  mov     [rbp+57h+var_C0], rax
0x140339f28  mov     rdx, rax
0x140339f2b  lea     rcx, [rbp+57h+var_B8]
0x140339f2f  xor     r9d, r9d
0x140339f32  xor     r8d, r8d
0x140339f35  call    cs:__imp_??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x140339f3c  nop     dword ptr [rax+rax+00h]
0x140339f41  cmp     [rbp+57h+var_B8], 0
0x140339f46  jz      short loc_140339F8E
0x140339f48  movups  xmm0, xmmword ptr [r15+78h]
0x140339f4d  lea     rdx, [r15+0A10h]; struct _POINTL *
0x140339f54  xor     r8d, r8d; int
0x140339f57  lea     rcx, [rbp+57h+var_48]; this
0x140339f5b  movdqu  [rbp+57h+var_48], xmm0
0x140339f60  call    ?bOffsetAdd@ERECTL@@QEAAHAEBU_POINTL@@H@Z; ERECTL::bOffsetAdd(_POINTL const &,int)
0x140339f65  lea     rdx, [rbp+57h+var_48]
0x140339f69  lea     rcx, [rbp+57h+var_B8]
0x140339f6d  call    cs:__imp_?bInside@RGNOBJ@@QEAAHPEAU_RECTL@@@Z; RGNOBJ::bInside(_RECTL *)
0x140339f74  nop     dword ptr [rax+rax+00h]
0x140339f79  cmp     eax, 2
0x140339f7c  jz      short loc_140339F8E
0x140339f7e  lea     rcx, [rbp+57h+var_B8]; this
0x140339f82  call    ??1RGNOBJAPI@@QEAA@XZ; RGNOBJAPI::~RGNOBJAPI(void)
0x140339f87  xor     eax, eax
0x140339f89  jmp     loc_14033A294
0x140339f8e  lea     rcx, [rbp+57h+var_B8]; this
0x140339f92  xor     r14d, r14d
0x140339f95  call    ??1RGNOBJAPI@@QEAA@XZ; RGNOBJAPI::~RGNOBJAPI(void)
0x140339f9a  cmp     [r15+88h], r14d
0x140339fa1  jz      loc_14033A291
0x140339fa7  xor     r9d, r9d
0x140339faa  xor     r8d, r8d
0x140339fad  xor     edx, edx
0x140339faf  xor     ecx, ecx
0x140339fb1  call    cs:__imp_GreCreateRectRgn
0x140339fb8  nop     dword ptr [rax+rax+00h]
0x140339fbd  mov     rsi, rax
0x140339fc0  test    rax, rax
0x140339fc3  jz      loc_14033A291
0x140339fc9  xor     r9d, r9d
0x140339fcc  xor     r8d, r8d
0x140339fcf  xor     edx, edx
0x140339fd1  xor     ecx, ecx
0x140339fd3  call    cs:__imp_GreCreateRectRgn
0x140339fda  nop     dword ptr [rax+rax+00h]
0x140339fdf  xor     r9d, r9d
0x140339fe2  xor     r8d, r8d
0x140339fe5  xor     edx, edx
0x140339fe7  mov     [rbp+57h+var_D0], rax
0x140339feb  xor     ecx, ecx
0x140339fed  call    cs:__imp_GreCreateRectRgn
0x140339ff4  nop     dword ptr [rax+rax+00h]
0x140339ff9  xor     r9d, r9d
0x140339ffc  xor     r8d, r8d
0x140339fff  xor     edx, edx
0x14033a001  xor     ecx, ecx
0x14033a003  mov     rdi, rax
0x14033a006  call    cs:__imp_GreCreateRectRgn
0x14033a00d  nop     dword ptr [rax+rax+00h]
0x14033a012  mov     r13, [rbp+57h+var_D0]
0x14033a016  mov     r12, rax
0x14033a019  test    r13, r13
0x14033a01c  jz      loc_14033A25A
0x14033a022  test    rdi, rdi
0x14033a025  jz      loc_14033A24B
0x14033a02b  test    rax, rax
0x14033a02e  jz      loc_14033A24B
0x14033a034  mov     ecx, [r15+84h]
0x14033a03b  mov     r9d, [r15+80h]
0x14033a042  mov     r8d, [r15+7Ch]
0x14033a046  mov     edx, [r15+78h]
0x14033a04a  mov     [rsp+100h+var_E0], ecx
0x14033a04e  mov     rcx, r13
0x14033a051  call    cs:__imp_GreSetRectRgn
0x14033a058  nop     dword ptr [rax+rax+00h]
0x14033a05d  test    eax, eax
0x14033a05f  jz      loc_14033A24B
0x14033a065  lea     rcx, [r15+0C8h]; this
0x14033a06c  xor     r13d, r13d
0x14033a06f  call    ?vLockExclusive@SPRITERANGELOCK@@QEAAXXZ; SPRITERANGELOCK::vLockExclusive(void)
0x14033a074  call    cs:__imp_W32GetSessionState
0x14033a07b  nop     dword ptr [rax+rax+00h]
0x14033a080  mov     rcx, [rax+60h]
0x14033a084  cmp     dword ptr [rcx+88h], 1
0x14033a08b  jnz     short loc_14033A0A1
0x14033a08d  cmp     [r15+468h], r13
0x14033a094  jz      short loc_14033A0A1
0x14033a096  xor     edx, edx; int
0x14033a098  lea     rcx, [r15+50h]; struct _SPRITESTATE *
0x14033a09c  call    ?vSpComputeUncoveredRegion@@YAXPEAU_SPRITESTATE@@H@Z; vSpComputeUncoveredRegion(_SPRITESTATE *,int)
0x14033a0a1  lea     rcx, [r15+0C8h]; this
0x14033a0a8  call    ?vUnlockExclusive@SPRITERANGELOCK@@QEAAXXZ; SPRITERANGELOCK::vUnlockExclusive(void)
0x14033a0ad  xor     r9d, r9d
0x14033a0b0  lea     rcx, [rbp+57h+var_80]
0x14033a0b4  xor     r8d, r8d
0x14033a0b7  mov     rdx, rsi
0x14033a0ba  call    cs:__imp_??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x14033a0c1  nop     dword ptr [rax+rax+00h]
0x14033a0c6  mov     rdx, [rbp+57h+var_D0]
0x14033a0ca  lea     rcx, [rbp+57h+var_B8]
0x14033a0ce  xor     r9d, r9d
0x14033a0d1  lea     r8d, [r9+1]
0x14033a0d5  call    cs:__imp_??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x14033a0dc  nop     dword ptr [rax+rax+00h]
0x14033a0e1  mov     rax, [r15+310h]
0x14033a0e8  mov     qword ptr [rbp+57h+var_48], rax
0x14033a0ec  cmp     [rbp+57h+var_80], r13
0x14033a0f0  jz      short loc_14033A119
0x14033a0f2  cmp     [rbp+57h+var_B8], r13
0x14033a0f6  jz      short loc_14033A119
0x14033a0f8  mov     r9d, 4
0x14033a0fe  lea     r8, [rbp+57h+var_48]
0x14033a102  lea     rdx, [rbp+57h+var_B8]
0x14033a106  lea     rcx, [rbp+57h+var_80]
0x14033a10a  call    cs:__imp_?iCombine@RGNOBJAPI@@QEAAJAEAVRGNOBJ@@0J@Z; RGNOBJAPI::iCombine(RGNOBJ &,RGNOBJ &,long)
0x14033a111  nop     dword ptr [rax+rax+00h]
0x14033a116  mov     r13d, eax
0x14033a119  lea     rcx, [rbp+57h+var_B8]; this
0x14033a11d  call    ??1RGNOBJAPI@@QEAA@XZ; RGNOBJAPI::~RGNOBJAPI(void)
0x14033a122  lea     rcx, [rbp+57h+var_80]; this
0x14033a126  call    ??1RGNOBJAPI@@QEAA@XZ; RGNOBJAPI::~RGNOBJAPI(void)
0x14033a12b  cmp     r13d, 1
0x14033a12f  jbe     loc_14033A247
0x14033a135  xor     ebx, ebx
0x14033a137  call    cs:__imp_W32GetSessionState
0x14033a13e  nop     dword ptr [rax+rax+00h]
0x14033a143  mov     r13, [rax+60h]
0x14033a147  cmp     dword ptr [r13+88h], 1
0x14033a14f  jnz     short loc_14033A1CC
0x14033a151  xor     r9d, r9d
0x14033a154  mov     [rsp+100h+var_E0], ebx
0x14033a158  xor     r8d, r8d
0x14033a15b  xor     edx, edx
0x14033a15d  mov     rcx, rdi
0x14033a160  call    cs:__imp_GreSetRectRgn
0x14033a167  nop     dword ptr [rax+rax+00h]
0x14033a16c  call    IsDwmActive
0x14033a171  test    eax, eax
0x14033a173  jnz     short loc_14033A180
0x14033a175  mov     rdx, rdi; HRGN
0x14033a178  mov     rcx, r15; HDEV
0x14033a17b  call    ?GdiGetSpriteClipRgns@@YAHPEAUHDEV__@@PEAUHRGN__@@@Z; GdiGetSpriteClipRgns(HDEV__ *,HRGN__ *)
0x14033a180  lea     rdx, [rbp+57h+var_48]
0x14033a184  mov     rcx, rdi
0x14033a187  call    cs:__imp_GreGetRgnBox
0x14033a18e  nop     dword ptr [rax+rax+00h]
0x14033a193  lea     rcx, [rbp+57h+var_48]; this
0x14033a197  call    ?bEmpty@ERECTL@@QEBAHXZ; ERECTL::bEmpty(void)
0x14033a19c  test    eax, eax
0x14033a19e  jnz     short loc_14033A1CC
0x14033a1a0  lea     r9d, [rax+1]
0x14033a1a4  mov     r8, rdi
0x14033a1a7  mov     rdx, rsi
0x14033a1aa  mov     rcx, r12
0x14033a1ad  call    cs:__imp_GreCombineRgn
0x14033a1b4  nop     dword ptr [rax+rax+00h]
0x14033a1b9  cmp     eax, 1
0x14033a1bc  jbe     short loc_14033A1CC
0x14033a1be  mov     rax, rsi
0x14033a1c1  mov     ebx, 1
0x14033a1c6  mov     rsi, r12
0x14033a1c9  mov     r12, rax
0x14033a1cc  mov     r8d, [r15+0A14h]
0x14033a1d3  mov     rcx, rsi
0x14033a1d6  mov     edx, [r15+0A10h]
0x14033a1dd  call    cs:__imp_GreOffsetRgn
0x14033a1e4  nop     dword ptr [rax+rax+00h]
0x14033a1e9  cmp     eax, 1
0x14033a1ec  jbe     short loc_14033A247
0x14033a1ee  mov     r8, [rbp+57h+var_C0]
0x14033a1f2  mov     r9d, 1
0x14033a1f8  mov     rcx, [rbp+57h+var_D0]
0x14033a1fc  mov     rdx, rsi
0x14033a1ff  call    cs:__imp_GreCombineRgn
0x14033a206  nop     dword ptr [rax+rax+00h]
0x14033a20b  mov     ecx, 1
0x14033a210  cmp     eax, ecx
0x14033a212  cmova   r14d, ecx
0x14033a216  cmp     [r13+88h], ecx
0x14033a21d  jnz     short loc_14033A244
0x14033a21f  test    r14d, r14d
0x14033a222  jnz     short loc_14033A236
0x14033a224  test    ebx, ebx
0x14033a226  jz      short loc_14033A247
0x14033a228  mov     rdx, [rbp+57h+var_C8]; HWND
0x14033a22c  mov     rcx, r15; HDEV
0x14033a22f  call    ?GreAddSpriteOverlapPresent@@YAHPEAUHDEV__@@PEAUHWND__@@@Z; GreAddSpriteOverlapPresent(HDEV__ *,HWND__ *)
0x14033a234  jmp     short loc_14033A247
0x14033a236  mov     rdx, [rbp+57h+var_C8]
0x14033a23a  mov     rcx, r15; HDEV
0x14033a23d  call    GreDeleteSpriteOverlapPresent
0x14033a242  jmp     short loc_14033A247
0x14033a244  mov     r14d, ecx
0x14033a247  mov     r13, [rbp+57h+var_D0]
0x14033a24b  mov     rcx, r13
0x14033a24e  call    cs:__imp_GreDeleteObject
0x14033a255  nop     dword ptr [rax+rax+00h]
0x14033a25a  test    rdi, rdi
0x14033a25d  jz      short loc_14033A26E
0x14033a25f  mov     rcx, rdi
0x14033a262  call    cs:__imp_GreDeleteObject
0x14033a269  nop     dword ptr [rax+rax+00h]
0x14033a26e  test    r12, r12
0x14033a271  jz      short loc_14033A282
0x14033a273  mov     rcx, r12
0x14033a276  call    cs:__imp_GreDeleteObject
0x14033a27d  nop     dword ptr [rax+rax+00h]
0x14033a282  mov     rcx, rsi
0x14033a285  call    cs:__imp_GreDeleteObject
0x14033a28c  nop     dword ptr [rax+rax+00h]
0x14033a291  mov     eax, r14d
0x14033a294  mov     rcx, [rbp+57h+var_38]
0x14033a298  xor     rcx, rsp; StackCookie
0x14033a29b  call    __security_check_cookie
0x14033a2a0  mov     rbx, [rsp+100h+arg_18]
0x14033a2a8  add     rsp, 0D0h
0x14033a2af  pop     r15
0x14033a2b1  pop     r14
0x14033a2b3  pop     r13
0x14033a2b5  pop     r12
0x14033a2b7  pop     rdi
0x14033a2b8  pop     rsi
0x14033a2b9  pop     rbp
0x14033a2ba  retn
```
