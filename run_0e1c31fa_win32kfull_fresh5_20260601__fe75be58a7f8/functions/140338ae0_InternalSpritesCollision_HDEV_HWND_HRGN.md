# InternalSpritesCollision(HDEV__ *,HWND__ *,HRGN__ *)

- ea: `0x140338ae0`
- end: `0x140338eac`
- name: `?InternalSpritesCollision@@YAHPEAUHDEV__@@PEAUHWND__@@PEAUHRGN__@@@Z`
- size: `972`
- prototype: `__int64 __fastcall(HDEV, HWND, HRGN)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140339160`

## callees

- `0x14006ec10`
- `0x14006f19c`
- `0x14006f530`
- `0x14006f70c`
- `0x140093570`
- `0x140183ad8`
- `0x14019d9d0`
- `0x1401a40cc`
- `0x140306bcc`
- `0x140306eb8`
- `0x140338ae0`
- `0x140341ff0`

## import_xrefs

- `win32kbase!GreGetRgnBox` at `0x140338d77`
- `win32kbase!GreGetRgnBox` at `0x140338d77`
- `win32kbase!?bInside@RGNOBJ@@QEAAHPEAU_RECTL@@@Z` at `0x140338b5d`
- `win32kbase!?bInside@RGNOBJ@@QEAAHPEAU_RECTL@@@Z` at `0x140338b5d`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x140338b25`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x140338caa`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x140338cc5`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x140338b25`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x140338caa`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x140338cc5`
- `win32kbase!?iCombine@RGNOBJAPI@@QEAAJAEAVRGNOBJ@@0J@Z` at `0x140338cfa`
- `win32kbase!?iCombine@RGNOBJAPI@@QEAAJAEAVRGNOBJ@@0J@Z` at `0x140338cfa`
- `win32kbase!GreCreateRectRgn` at `0x140338ba1`
- `win32kbase!GreCreateRectRgn` at `0x140338bc3`
- `win32kbase!GreCreateRectRgn` at `0x140338bdd`
- `win32kbase!GreCreateRectRgn` at `0x140338bf6`
- `win32kbase!GreCreateRectRgn` at `0x140338ba1`
- `win32kbase!GreCreateRectRgn` at `0x140338bc3`
- `win32kbase!GreCreateRectRgn` at `0x140338bdd`
- `win32kbase!GreCreateRectRgn` at `0x140338bf6`
- `win32kbase!GreSetRectRgn` at `0x140338c41`
- `win32kbase!GreSetRectRgn` at `0x140338d50`
- `win32kbase!GreSetRectRgn` at `0x140338c41`
- `win32kbase!GreSetRectRgn` at `0x140338d50`
- `win32kbase!GreCombineRgn` at `0x140338d9d`
- `win32kbase!GreCombineRgn` at `0x140338def`
- `win32kbase!GreCombineRgn` at `0x140338d9d`
- `win32kbase!GreCombineRgn` at `0x140338def`
- `win32kbase!GreOffsetRgn` at `0x140338dcd`
- `win32kbase!GreOffsetRgn` at `0x140338dcd`
- `win32kbase!GreDeleteObject` at `0x140338e3e`
- `win32kbase!GreDeleteObject` at `0x140338e52`
- `win32kbase!GreDeleteObject` at `0x140338e66`
- `win32kbase!GreDeleteObject` at `0x140338e75`
- `win32kbase!GreDeleteObject` at `0x140338e3e`
- `win32kbase!GreDeleteObject` at `0x140338e52`
- `win32kbase!GreDeleteObject` at `0x140338e66`
- `win32kbase!GreDeleteObject` at `0x140338e75`
- `WIN32K!W32GetSessionState` at `0x140338c64`
- `WIN32K!W32GetSessionState` at `0x140338d27`
- `WIN32K!W32GetSessionState` at `0x140338c64`
- `WIN32K!W32GetSessionState` at `0x140338d27`

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
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // ebx
  __int64 v15; // r13
  HRGN v16; // rax
  HRGN v17; // [rsp+30h] [rbp-79h]
  _QWORD v20[7]; // [rsp+48h] [rbp-61h] BYREF
  _QWORD v21[7]; // [rsp+80h] [rbp-29h] BYREF
  struct _RECTL v22; // [rsp+B8h] [rbp+Fh] BYREF

  RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)v20, a3, 0, 0);
  if ( !v20[0]
    || (v22 = *(struct _RECTL *)(a1 + 30),
        ERECTL::bOffsetAdd((ERECTL *)&v22, (const struct _POINTL *)a1 + 322, 0),
        RGNOBJ::bInside((RGNOBJ *)v20, &v22) == 2) )
  {
    v5 = 0;
    RGNOBJAPI::~RGNOBJAPI((RGNOBJAPI *)v20);
    if ( *((_DWORD *)a1 + 34) )
    {
      RectRgn = (HRGN)GreCreateRectRgn(0, 0, 0, 0);
      if ( RectRgn )
      {
        v17 = (HRGN)GreCreateRectRgn(0, 0, 0, 0);
        v7 = (HRGN)GreCreateRectRgn(0, 0, 0, 0);
        v8 = GreCreateRectRgn(0, 0, 0, 0);
        v9 = v17;
        v10 = (HRGN)v8;
        if ( v17 )
        {
          if ( v7
            && v8
            && (unsigned int)GreSetRectRgn(
                               v17,
                               *((unsigned int *)a1 + 30),
                               *((unsigned int *)a1 + 31),
                               *((unsigned int *)a1 + 32),
                               *((_DWORD *)a1 + 33)) )
          {
            v11 = 0;
            SPRITERANGELOCK::vLockExclusive((SPRITERANGELOCK *)(a1 + 50));
            if ( *(_DWORD *)(*(_QWORD *)(W32GetSessionState(v12) + 96) + 136LL) == 1 && *((_QWORD *)a1 + 141) )
              vSpComputeUncoveredRegion((struct _SPRITESTATE *)(a1 + 20), 0);
            SPRITERANGELOCK::vUnlockExclusive((SPRITERANGELOCK *)(a1 + 50));
            RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)v21, RectRgn, 0, 0);
            RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)v20, v17, 1, 0);
            *(_QWORD *)&v22.left = *((_QWORD *)a1 + 98);
            if ( v21[0] && v20[0] )
              v11 = RGNOBJAPI::iCombine((RGNOBJAPI *)v21, (struct RGNOBJ *)v20, (struct RGNOBJ *)&v22, 4);
            RGNOBJAPI::~RGNOBJAPI((RGNOBJAPI *)v20);
            RGNOBJAPI::~RGNOBJAPI((RGNOBJAPI *)v21);
            if ( v11 > 1 )
            {
              v14 = 0;
              v15 = *(_QWORD *)(W32GetSessionState(v13) + 96);
              if ( *(_DWORD *)(v15 + 136) == 1 )
              {
                GreSetRectRgn(v7, 0, 0, 0, 0);
                if ( !(unsigned int)IsDwmActive() )
                  GdiGetSpriteClipRgns(a1, v7);
                GreGetRgnBox(v7, &v22);
                if ( !(unsigned int)ERECTL::bEmpty((ERECTL *)&v22)
                  && (unsigned int)GreCombineRgn(v10, RectRgn, v7, 1) > 1 )
                {
                  v16 = RectRgn;
                  v14 = 1;
                  RectRgn = v10;
                  v10 = v16;
                }
              }
              if ( (unsigned int)GreOffsetRgn(RectRgn, *((unsigned int *)a1 + 644), *((unsigned int *)a1 + 645)) > 1 )
              {
                if ( (unsigned int)GreCombineRgn(v17, RectRgn, a3, 1) > 1 )
                  v5 = 1;
                if ( *(_DWORD *)(v15 + 136) == 1 )
                {
                  if ( v5 )
                  {
                    GreDeleteSpriteOverlapPresent(a1);
                  }
                  else if ( v14 )
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
            v9 = v17;
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
    RGNOBJAPI::~RGNOBJAPI((RGNOBJAPI *)v20);
    return 0;
  }
}

```

## disassembly

```asm
0x140338ae0  mov     [rsp-8+arg_18], rbx
0x140338ae5  push    rbp
0x140338ae6  push    rsi
0x140338ae7  push    rdi
0x140338ae8  push    r12
0x140338aea  push    r13
0x140338aec  push    r14
0x140338aee  push    r15
0x140338af0  lea     rbp, [rsp-27h]
0x140338af5  sub     rsp, 0D0h
0x140338afc  mov     rax, cs:__security_cookie
0x140338b03  xor     rax, rsp
0x140338b06  mov     [rbp+57h+var_38], rax
0x140338b0a  mov     rax, r8
0x140338b0d  mov     [rbp+57h+var_C8], rdx
0x140338b11  mov     r15, rcx
0x140338b14  mov     [rbp+57h+var_C0], rax
0x140338b18  mov     rdx, rax
0x140338b1b  lea     rcx, [rbp+57h+var_B8]
0x140338b1f  xor     r9d, r9d
0x140338b22  xor     r8d, r8d
0x140338b25  call    cs:__imp_??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x140338b2c  nop     dword ptr [rax+rax+00h]
0x140338b31  cmp     [rbp+57h+var_B8], 0
0x140338b36  jz      short loc_140338B7E
0x140338b38  movups  xmm0, xmmword ptr [r15+78h]
0x140338b3d  lea     rdx, [r15+0A10h]; struct _POINTL *
0x140338b44  xor     r8d, r8d; int
0x140338b47  lea     rcx, [rbp+57h+var_48]; this
0x140338b4b  movdqu  [rbp+57h+var_48], xmm0
0x140338b50  call    ?bOffsetAdd@ERECTL@@QEAAHAEBU_POINTL@@H@Z; ERECTL::bOffsetAdd(_POINTL const &,int)
0x140338b55  lea     rdx, [rbp+57h+var_48]
0x140338b59  lea     rcx, [rbp+57h+var_B8]
0x140338b5d  call    cs:__imp_?bInside@RGNOBJ@@QEAAHPEAU_RECTL@@@Z; RGNOBJ::bInside(_RECTL *)
0x140338b64  nop     dword ptr [rax+rax+00h]
0x140338b69  cmp     eax, 2
0x140338b6c  jz      short loc_140338B7E
0x140338b6e  lea     rcx, [rbp+57h+var_B8]; this
0x140338b72  call    ??1RGNOBJAPI@@QEAA@XZ; RGNOBJAPI::~RGNOBJAPI(void)
0x140338b77  xor     eax, eax
0x140338b79  jmp     loc_140338E84
0x140338b7e  lea     rcx, [rbp+57h+var_B8]; this
0x140338b82  xor     r14d, r14d
0x140338b85  call    ??1RGNOBJAPI@@QEAA@XZ; RGNOBJAPI::~RGNOBJAPI(void)
0x140338b8a  cmp     [r15+88h], r14d
0x140338b91  jz      loc_140338E81
0x140338b97  xor     r9d, r9d
0x140338b9a  xor     r8d, r8d
0x140338b9d  xor     edx, edx
0x140338b9f  xor     ecx, ecx
0x140338ba1  call    cs:__imp_GreCreateRectRgn
0x140338ba8  nop     dword ptr [rax+rax+00h]
0x140338bad  mov     rsi, rax
0x140338bb0  test    rax, rax
0x140338bb3  jz      loc_140338E81
0x140338bb9  xor     r9d, r9d
0x140338bbc  xor     r8d, r8d
0x140338bbf  xor     edx, edx
0x140338bc1  xor     ecx, ecx
0x140338bc3  call    cs:__imp_GreCreateRectRgn
0x140338bca  nop     dword ptr [rax+rax+00h]
0x140338bcf  xor     r9d, r9d
0x140338bd2  xor     r8d, r8d
0x140338bd5  xor     edx, edx
0x140338bd7  mov     [rbp+57h+var_D0], rax
0x140338bdb  xor     ecx, ecx
0x140338bdd  call    cs:__imp_GreCreateRectRgn
0x140338be4  nop     dword ptr [rax+rax+00h]
0x140338be9  xor     r9d, r9d
0x140338bec  xor     r8d, r8d
0x140338bef  xor     edx, edx
0x140338bf1  xor     ecx, ecx
0x140338bf3  mov     rdi, rax
0x140338bf6  call    cs:__imp_GreCreateRectRgn
0x140338bfd  nop     dword ptr [rax+rax+00h]
0x140338c02  mov     r13, [rbp+57h+var_D0]
0x140338c06  mov     r12, rax
0x140338c09  test    r13, r13
0x140338c0c  jz      loc_140338E4A
0x140338c12  test    rdi, rdi
0x140338c15  jz      loc_140338E3B
0x140338c1b  test    rax, rax
0x140338c1e  jz      loc_140338E3B
0x140338c24  mov     ecx, [r15+84h]
0x140338c2b  mov     r9d, [r15+80h]
0x140338c32  mov     r8d, [r15+7Ch]
0x140338c36  mov     edx, [r15+78h]
0x140338c3a  mov     [rsp+100h+var_E0], ecx
0x140338c3e  mov     rcx, r13
0x140338c41  call    cs:__imp_GreSetRectRgn
0x140338c48  nop     dword ptr [rax+rax+00h]
0x140338c4d  test    eax, eax
0x140338c4f  jz      loc_140338E3B
0x140338c55  lea     rcx, [r15+0C8h]; this
0x140338c5c  xor     r13d, r13d
0x140338c5f  call    ?vLockExclusive@SPRITERANGELOCK@@QEAAXXZ; SPRITERANGELOCK::vLockExclusive(void)
0x140338c64  call    cs:__imp_W32GetSessionState
0x140338c6b  nop     dword ptr [rax+rax+00h]
0x140338c70  mov     rcx, [rax+60h]
0x140338c74  cmp     dword ptr [rcx+88h], 1
0x140338c7b  jnz     short loc_140338C91
0x140338c7d  cmp     [r15+468h], r13
0x140338c84  jz      short loc_140338C91
0x140338c86  xor     edx, edx; int
0x140338c88  lea     rcx, [r15+50h]; struct _SPRITESTATE *
0x140338c8c  call    ?vSpComputeUncoveredRegion@@YAXPEAU_SPRITESTATE@@H@Z; vSpComputeUncoveredRegion(_SPRITESTATE *,int)
0x140338c91  lea     rcx, [r15+0C8h]; this
0x140338c98  call    ?vUnlockExclusive@SPRITERANGELOCK@@QEAAXXZ; SPRITERANGELOCK::vUnlockExclusive(void)
0x140338c9d  xor     r9d, r9d
0x140338ca0  lea     rcx, [rbp+57h+var_80]
0x140338ca4  xor     r8d, r8d
0x140338ca7  mov     rdx, rsi
0x140338caa  call    cs:__imp_??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x140338cb1  nop     dword ptr [rax+rax+00h]
0x140338cb6  mov     rdx, [rbp+57h+var_D0]
0x140338cba  lea     rcx, [rbp+57h+var_B8]
0x140338cbe  xor     r9d, r9d
0x140338cc1  lea     r8d, [r9+1]
0x140338cc5  call    cs:__imp_??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x140338ccc  nop     dword ptr [rax+rax+00h]
0x140338cd1  mov     rax, [r15+310h]
0x140338cd8  mov     qword ptr [rbp+57h+var_48], rax
0x140338cdc  cmp     [rbp+57h+var_80], r13
0x140338ce0  jz      short loc_140338D09
0x140338ce2  cmp     [rbp+57h+var_B8], r13
0x140338ce6  jz      short loc_140338D09
0x140338ce8  mov     r9d, 4
0x140338cee  lea     r8, [rbp+57h+var_48]
0x140338cf2  lea     rdx, [rbp+57h+var_B8]
0x140338cf6  lea     rcx, [rbp+57h+var_80]
0x140338cfa  call    cs:__imp_?iCombine@RGNOBJAPI@@QEAAJAEAVRGNOBJ@@0J@Z; RGNOBJAPI::iCombine(RGNOBJ &,RGNOBJ &,long)
0x140338d01  nop     dword ptr [rax+rax+00h]
0x140338d06  mov     r13d, eax
0x140338d09  lea     rcx, [rbp+57h+var_B8]; this
0x140338d0d  call    ??1RGNOBJAPI@@QEAA@XZ; RGNOBJAPI::~RGNOBJAPI(void)
0x140338d12  lea     rcx, [rbp+57h+var_80]; this
0x140338d16  call    ??1RGNOBJAPI@@QEAA@XZ; RGNOBJAPI::~RGNOBJAPI(void)
0x140338d1b  cmp     r13d, 1
0x140338d1f  jbe     loc_140338E37
0x140338d25  xor     ebx, ebx
0x140338d27  call    cs:__imp_W32GetSessionState
0x140338d2e  nop     dword ptr [rax+rax+00h]
0x140338d33  mov     r13, [rax+60h]
0x140338d37  cmp     dword ptr [r13+88h], 1
0x140338d3f  jnz     short loc_140338DBC
0x140338d41  xor     r9d, r9d
0x140338d44  mov     [rsp+100h+var_E0], ebx
0x140338d48  xor     r8d, r8d
0x140338d4b  xor     edx, edx
0x140338d4d  mov     rcx, rdi
0x140338d50  call    cs:__imp_GreSetRectRgn
0x140338d57  nop     dword ptr [rax+rax+00h]
0x140338d5c  call    IsDwmActive
0x140338d61  test    eax, eax
0x140338d63  jnz     short loc_140338D70
0x140338d65  mov     rdx, rdi; HRGN
0x140338d68  mov     rcx, r15; HDEV
0x140338d6b  call    ?GdiGetSpriteClipRgns@@YAHPEAUHDEV__@@PEAUHRGN__@@@Z; GdiGetSpriteClipRgns(HDEV__ *,HRGN__ *)
0x140338d70  lea     rdx, [rbp+57h+var_48]
0x140338d74  mov     rcx, rdi
0x140338d77  call    cs:__imp_GreGetRgnBox
0x140338d7e  nop     dword ptr [rax+rax+00h]
0x140338d83  lea     rcx, [rbp+57h+var_48]; this
0x140338d87  call    ?bEmpty@ERECTL@@QEBAHXZ; ERECTL::bEmpty(void)
0x140338d8c  test    eax, eax
0x140338d8e  jnz     short loc_140338DBC
0x140338d90  lea     r9d, [rax+1]
0x140338d94  mov     r8, rdi
0x140338d97  mov     rdx, rsi
0x140338d9a  mov     rcx, r12
0x140338d9d  call    cs:__imp_GreCombineRgn
0x140338da4  nop     dword ptr [rax+rax+00h]
0x140338da9  cmp     eax, 1
0x140338dac  jbe     short loc_140338DBC
0x140338dae  mov     rax, rsi
0x140338db1  mov     ebx, 1
0x140338db6  mov     rsi, r12
0x140338db9  mov     r12, rax
0x140338dbc  mov     r8d, [r15+0A14h]
0x140338dc3  mov     rcx, rsi
0x140338dc6  mov     edx, [r15+0A10h]
0x140338dcd  call    cs:__imp_GreOffsetRgn
0x140338dd4  nop     dword ptr [rax+rax+00h]
0x140338dd9  cmp     eax, 1
0x140338ddc  jbe     short loc_140338E37
0x140338dde  mov     r8, [rbp+57h+var_C0]
0x140338de2  mov     r9d, 1
0x140338de8  mov     rcx, [rbp+57h+var_D0]
0x140338dec  mov     rdx, rsi
0x140338def  call    cs:__imp_GreCombineRgn
0x140338df6  nop     dword ptr [rax+rax+00h]
0x140338dfb  mov     ecx, 1
0x140338e00  cmp     eax, ecx
0x140338e02  cmova   r14d, ecx
0x140338e06  cmp     [r13+88h], ecx
0x140338e0d  jnz     short loc_140338E34
0x140338e0f  test    r14d, r14d
0x140338e12  jnz     short loc_140338E26
0x140338e14  test    ebx, ebx
0x140338e16  jz      short loc_140338E37
0x140338e18  mov     rdx, [rbp+57h+var_C8]; HWND
0x140338e1c  mov     rcx, r15; HDEV
0x140338e1f  call    ?GreAddSpriteOverlapPresent@@YAHPEAUHDEV__@@PEAUHWND__@@@Z; GreAddSpriteOverlapPresent(HDEV__ *,HWND__ *)
0x140338e24  jmp     short loc_140338E37
0x140338e26  mov     rdx, [rbp+57h+var_C8]
0x140338e2a  mov     rcx, r15; HDEV
0x140338e2d  call    GreDeleteSpriteOverlapPresent
0x140338e32  jmp     short loc_140338E37
0x140338e34  mov     r14d, ecx
0x140338e37  mov     r13, [rbp+57h+var_D0]
0x140338e3b  mov     rcx, r13
0x140338e3e  call    cs:__imp_GreDeleteObject
0x140338e45  nop     dword ptr [rax+rax+00h]
0x140338e4a  test    rdi, rdi
0x140338e4d  jz      short loc_140338E5E
0x140338e4f  mov     rcx, rdi
0x140338e52  call    cs:__imp_GreDeleteObject
0x140338e59  nop     dword ptr [rax+rax+00h]
0x140338e5e  test    r12, r12
0x140338e61  jz      short loc_140338E72
0x140338e63  mov     rcx, r12
0x140338e66  call    cs:__imp_GreDeleteObject
0x140338e6d  nop     dword ptr [rax+rax+00h]
0x140338e72  mov     rcx, rsi
0x140338e75  call    cs:__imp_GreDeleteObject
0x140338e7c  nop     dword ptr [rax+rax+00h]
0x140338e81  mov     eax, r14d
0x140338e84  mov     rcx, [rbp+57h+var_38]
0x140338e88  xor     rcx, rsp; StackCookie
0x140338e8b  call    __security_check_cookie
0x140338e90  mov     rbx, [rsp+100h+arg_18]
0x140338e98  add     rsp, 0D0h
0x140338e9f  pop     r15
0x140338ea1  pop     r14
0x140338ea3  pop     r13
0x140338ea5  pop     r12
0x140338ea7  pop     rdi
0x140338ea8  pop     rsi
0x140338ea9  pop     rbp
0x140338eaa  retn
```
