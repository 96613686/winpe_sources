# vSpComputeNoPresentRegion(_SPRITESTATE *,int)

- ea: `0x1401a3348`
- end: `0x1401a364c`
- name: `?vSpComputeNoPresentRegion@@YAXPEAU_SPRITESTATE@@H@Z`
- size: `772`
- prototype: `void __fastcall(struct _SPRITESTATE *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14006e710`
- `0x1401a3310`

## callees

- `0x1400620a8`
- `0x1400f8e58`
- `0x1400fb65c`
- `0x14019d9d0`
- `0x1401a3348`
- `0x1401a3654`
- `0x1402af9e4`
- `0x1403090a0`
- `0x140341ff0`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401a3384`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401a3384`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401a33f4`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401a3431`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401a3612`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401a33f4`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401a3431`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401a3612`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1401a347e`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1401a3492`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1401a3531`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1401a347e`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1401a3492`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1401a3531`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1401a359e`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1401a359e`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x1401a3411`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x1401a3411`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x1401a35b6`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x1401a35b6`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x1401a3512`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x1401a355b`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x1401a356f`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x1401a3512`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x1401a355b`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x1401a356f`
- `win32kbase!?vStamp@REGION@@AEAAXXZ` at `0x1401a35ec`
- `win32kbase!?vStamp@REGION@@AEAAXXZ` at `0x1401a35ec`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x1401a34d5`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x1401a34d5`
- `win32kbase!?bDeleteRGNOBJAPI@RGNOBJAPI@@QEAAHXZ` at `0x1401a35c6`
- `win32kbase!?bDeleteRGNOBJAPI@RGNOBJAPI@@QEAAHXZ` at `0x1401a35c6`

## pseudocode

```c
void __fastcall vSpComputeNoPresentRegion(struct _SPRITESTATE *a1, int a2)
{
  __int64 v2; // rbx
  _QWORD *v5; // rsi
  HRGN ClientRgn; // rax
  int v7; // eax
  struct RGNOBJ *v8; // r8
  struct _POINTL v9; // [rsp+20h] [rbp-49h] BYREF
  REGION *v10; // [rsp+28h] [rbp-41h] BYREF
  __int64 v11; // [rsp+30h] [rbp-39h] BYREF
  __int64 v12; // [rsp+38h] [rbp-31h] BYREF
  __int64 v13; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v14[7]; // [rsp+48h] [rbp-21h] BYREF
  struct _RECTL v15; // [rsp+80h] [rbp+17h] BYREF
  struct _RECTL v16; // [rsp+90h] [rbp+27h] BYREF

  v2 = *(_QWORD *)a1;
  v15 = 0;
  v12 = v2;
  Gre::Base::Globals(a1);
  if ( *((_QWORD *)a1 + 132) )
  {
    v11 = *((_QWORD *)a1 + 132);
    RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v11);
    *((_QWORD *)a1 + 132) = 0;
  }
  if ( !a2 && *((_QWORD *)a1 + 131) )
  {
    v11 = *((_QWORD *)a1 + 131);
    RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v11);
    *((_QWORD *)a1 + 131) = 0;
  }
  v5 = (_QWORD *)*((_QWORD *)a1 + 10);
  if ( v5 )
  {
    RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v10);
    RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v11);
    if ( v10 && v11 )
    {
      *(_QWORD *)&v15.left = 0;
      *(_QWORD *)&v15.right = **(_QWORD **)&PDEVOBJ::sizl((PDEVOBJ *)&v12);
      RGNOBJ::vSet((RGNOBJ *)&v10, &v15);
      RGNOBJ::vSet((RGNOBJ *)&v11, &v15);
      RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v13);
      if ( v13 )
      {
        do
        {
          v16 = 0;
          ClientRgn = (HRGN)UserGetClientRgn(*v5, &v16, 0);
          RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)v14, ClientRgn, 0, 0);
          if ( v14[0] )
          {
            v9 = 0;
            v9.x = -*(_DWORD *)(v2 + 2576);
            v9.y = -*(_DWORD *)(v2 + 2580);
            RGNOBJ::bOffset((RGNOBJ *)v14, &v9);
            v12 = *((_QWORD *)a1 + 89);
            RGNOBJ::vSet((RGNOBJ *)&v12, &v16);
            v9.x = -*(_DWORD *)(v2 + 2576);
            v9.y = -*(_DWORD *)(v2 + 2580);
            RGNOBJ::bOffset((RGNOBJ *)v14, &v9);
            RGNOBJ::bOffset((RGNOBJ *)&v12, &v9);
            v7 = RGNOBJ::iComplexity((RGNOBJ *)v14);
            v8 = (struct RGNOBJ *)&v12;
            if ( v7 != 1 )
              v8 = (struct RGNOBJ *)v14;
            if ( RGNOBJ::bMerge((RGNOBJ *)&v13, (struct RGNOBJ *)&v10, v8, 4u) )
              RGNOBJ::vSwap((RGNOBJ *)&v13, (struct RGNOBJ *)&v10);
            RGNOBJAPI::bDeleteRGNOBJAPI((RGNOBJAPI *)v14);
          }
          v5 = (_QWORD *)v5[1];
          RGNOBJAPI::~RGNOBJAPI((RGNOBJAPI *)v14);
        }
        while ( v5 );
      }
      REGION::vStamp(v10);
      if ( a2 )
        *((_QWORD *)a1 + 132) = v10;
      else
        *((_QWORD *)a1 + 131) = v10;
      RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v13);
    }
    else
    {
      RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v10);
    }
    RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v11);
  }
  if ( !a2 )
    vSpComputeUnlockedRegion((HDEV *)a1);
}

```

## disassembly

```asm
0x1401a3348  mov     [rsp-8+arg_8], rbx
0x1401a334d  mov     [rsp-8+arg_10], rsi
0x1401a3352  push    rbp
0x1401a3353  push    rdi
0x1401a3354  push    r14
0x1401a3356  lea     rbp, [rsp-47h]
0x1401a335b  sub     rsp, 0B0h
0x1401a3362  mov     rax, cs:__security_cookie
0x1401a3369  xor     rax, rsp
0x1401a336c  mov     [rbp+57h+var_20], rax
0x1401a3370  mov     rbx, [rcx]
0x1401a3373  xorps   xmm0, xmm0
0x1401a3376  movups  [rbp+57h+var_40], xmm0
0x1401a337a  mov     [rbp+57h+var_88], rbx
0x1401a337e  mov     r14d, edx
0x1401a3381  mov     rdi, rcx
0x1401a3384  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1401a338b  nop     dword ptr [rax+rax+00h]
0x1401a3390  mov     rax, [rdi+420h]
0x1401a3397  test    rax, rax
0x1401a339a  jnz     loc_1401A360A
0x1401a33a0  test    r14d, r14d
0x1401a33a3  jz      short loc_1401A33E0
0x1401a33a5  mov     rsi, [rdi+50h]
0x1401a33a9  test    rsi, rsi
0x1401a33ac  jnz     short loc_1401A340D
0x1401a33ae  test    r14d, r14d
0x1401a33b1  jnz     short loc_1401A33BB
0x1401a33b3  mov     rcx, rdi; struct _SPRITESTATE *
0x1401a33b6  call    ?vSpComputeUnlockedRegion@@YAXPEAU_SPRITESTATE@@@Z; vSpComputeUnlockedRegion(_SPRITESTATE *)
0x1401a33bb  mov     rcx, [rbp+57h+var_20]
0x1401a33bf  xor     rcx, rsp; StackCookie
0x1401a33c2  call    __security_check_cookie
0x1401a33c7  lea     r11, [rsp+0C0h+var_10]
0x1401a33cf  mov     rbx, [r11+28h]
0x1401a33d3  mov     rsi, [r11+30h]
0x1401a33d7  mov     rsp, r11
0x1401a33da  pop     r14
0x1401a33dc  pop     rdi
0x1401a33dd  pop     rbp
0x1401a33de  retn
0x1401a33e0  mov     rax, [rdi+418h]
0x1401a33e7  test    rax, rax
0x1401a33ea  jz      short loc_1401A33A5
0x1401a33ec  lea     rcx, [rbp+57h+var_90]
0x1401a33f0  mov     [rbp+57h+var_90], rax
0x1401a33f4  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x1401a33fb  nop     dword ptr [rax+rax+00h]
0x1401a3400  mov     qword ptr [rdi+418h], 0
0x1401a340b  jmp     short loc_1401A33A5
0x1401a340d  lea     rcx, [rbp+57h+var_98]
0x1401a3411  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x1401a3418  nop     dword ptr [rax+rax+00h]
0x1401a341d  lea     rcx, [rbp+57h+var_90]; this
0x1401a3421  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x1401a3426  cmp     [rbp+57h+var_98], 0
0x1401a342b  jnz     short loc_1401A3442
0x1401a342d  lea     rcx, [rbp+57h+var_98]
0x1401a3431  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x1401a3438  nop     dword ptr [rax+rax+00h]
0x1401a343d  jmp     loc_1401A363E
0x1401a3442  cmp     [rbp+57h+var_90], 0
0x1401a3447  jz      short loc_1401A342D
0x1401a3449  lea     rdx, [rbp+57h+var_A0]
0x1401a344d  mov     qword ptr [rbp+57h+var_40], 0
0x1401a3455  lea     rcx, [rbp+57h+var_88]; this
0x1401a3459  call    ?sizl@PDEVOBJ@@QEAA?AUtagSIZE@@XZ; PDEVOBJ::sizl(void)
0x1401a345e  lea     rdx, [rbp+57h+var_A0]
0x1401a3462  mov     ecx, [rax]
0x1401a3464  mov     dword ptr [rbp+57h+var_40+8], ecx
0x1401a3467  lea     rcx, [rbp+57h+var_88]; this
0x1401a346b  call    ?sizl@PDEVOBJ@@QEAA?AUtagSIZE@@XZ; PDEVOBJ::sizl(void)
0x1401a3470  lea     rdx, [rbp+57h+var_40]
0x1401a3474  mov     ecx, [rax+4]
0x1401a3477  mov     dword ptr [rbp+57h+var_40+0Ch], ecx
0x1401a347a  lea     rcx, [rbp+57h+var_98]
0x1401a347e  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x1401a3485  nop     dword ptr [rax+rax+00h]
0x1401a348a  lea     rdx, [rbp+57h+var_40]
0x1401a348e  lea     rcx, [rbp+57h+var_90]
0x1401a3492  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x1401a3499  nop     dword ptr [rax+rax+00h]
0x1401a349e  lea     rcx, [rbp+57h+var_80]; this
0x1401a34a2  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x1401a34a7  cmp     [rbp+57h+var_80], 0
0x1401a34ac  jz      loc_1401A35E8
0x1401a34b2  xorps   xmm0, xmm0
0x1401a34b5  lea     rdx, [rbp+57h+var_30]
0x1401a34b9  movups  [rbp+57h+var_30], xmm0
0x1401a34bd  mov     rcx, [rsi]
0x1401a34c0  xor     r8d, r8d
0x1401a34c3  call    UserGetClientRgn
0x1401a34c8  xor     r9d, r9d
0x1401a34cb  lea     rcx, [rbp+57h+var_78]
0x1401a34cf  xor     r8d, r8d
0x1401a34d2  mov     rdx, rax
0x1401a34d5  call    cs:__imp_??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x1401a34dc  nop     dword ptr [rax+rax+00h]
0x1401a34e1  cmp     [rbp+57h+var_78], 0
0x1401a34e6  jz      loc_1401A35D2
0x1401a34ec  mov     [rbp+57h+var_A0], 0
0x1401a34f4  lea     rdx, [rbp+57h+var_A0]
0x1401a34f8  mov     eax, [rbx+0A10h]
0x1401a34fe  lea     rcx, [rbp+57h+var_78]
0x1401a3502  neg     eax
0x1401a3504  mov     dword ptr [rbp+57h+var_A0], eax
0x1401a3507  mov     eax, [rbx+0A14h]
0x1401a350d  neg     eax
0x1401a350f  mov     dword ptr [rbp+57h+var_A0+4], eax
0x1401a3512  call    cs:__imp_?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z; RGNOBJ::bOffset(_POINTL const *)
0x1401a3519  nop     dword ptr [rax+rax+00h]
0x1401a351e  mov     rax, [rdi+2C8h]
0x1401a3525  lea     rdx, [rbp+57h+var_30]
0x1401a3529  lea     rcx, [rbp+57h+var_88]
0x1401a352d  mov     [rbp+57h+var_88], rax
0x1401a3531  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x1401a3538  nop     dword ptr [rax+rax+00h]
0x1401a353d  mov     eax, [rbx+0A10h]
0x1401a3543  lea     rdx, [rbp+57h+var_A0]
0x1401a3547  neg     eax
0x1401a3549  lea     rcx, [rbp+57h+var_78]
0x1401a354d  mov     dword ptr [rbp+57h+var_A0], eax
0x1401a3550  mov     eax, [rbx+0A14h]
0x1401a3556  neg     eax
0x1401a3558  mov     dword ptr [rbp+57h+var_A0+4], eax
0x1401a355b  call    cs:__imp_?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z; RGNOBJ::bOffset(_POINTL const *)
0x1401a3562  nop     dword ptr [rax+rax+00h]
0x1401a3567  lea     rdx, [rbp+57h+var_A0]
0x1401a356b  lea     rcx, [rbp+57h+var_88]
0x1401a356f  call    cs:__imp_?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z; RGNOBJ::bOffset(_POINTL const *)
0x1401a3576  nop     dword ptr [rax+rax+00h]
0x1401a357b  lea     rcx, [rbp+57h+var_78]; this
0x1401a357f  call    ?iComplexity@RGNOBJ@@QEBAJXZ; RGNOBJ::iComplexity(void)
0x1401a3584  cmp     eax, 1
0x1401a3587  lea     rcx, [rbp+57h+var_78]
0x1401a358b  lea     r8, [rbp+57h+var_88]
0x1401a358f  mov     r9b, 4
0x1401a3592  cmovnz  r8, rcx
0x1401a3596  lea     rdx, [rbp+57h+var_98]
0x1401a359a  lea     rcx, [rbp+57h+var_80]
0x1401a359e  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x1401a35a5  nop     dword ptr [rax+rax+00h]
0x1401a35aa  test    eax, eax
0x1401a35ac  jz      short loc_1401A35C2
0x1401a35ae  lea     rdx, [rbp+57h+var_98]
0x1401a35b2  lea     rcx, [rbp+57h+var_80]
0x1401a35b6  call    cs:__imp_?vSwap@RGNOBJ@@QEAAXPEAV1@@Z; RGNOBJ::vSwap(RGNOBJ *)
0x1401a35bd  nop     dword ptr [rax+rax+00h]
0x1401a35c2  lea     rcx, [rbp+57h+var_78]
0x1401a35c6  call    cs:__imp_?bDeleteRGNOBJAPI@RGNOBJAPI@@QEAAHXZ; RGNOBJAPI::bDeleteRGNOBJAPI(void)
0x1401a35cd  nop     dword ptr [rax+rax+00h]
0x1401a35d2  mov     rsi, [rsi+8]
0x1401a35d6  lea     rcx, [rbp+57h+var_78]; this
0x1401a35da  call    ??1RGNOBJAPI@@QEAA@XZ; RGNOBJAPI::~RGNOBJAPI(void)
0x1401a35df  test    rsi, rsi
0x1401a35e2  jnz     loc_1401A34B2
0x1401a35e8  mov     rcx, [rbp+57h+var_98]
0x1401a35ec  call    cs:__imp_?vStamp@REGION@@AEAAXXZ; REGION::vStamp(void)
0x1401a35f3  nop     dword ptr [rax+rax+00h]
0x1401a35f8  mov     rax, [rbp+57h+var_98]
0x1401a35fc  test    r14d, r14d
0x1401a35ff  jz      short loc_1401A362E
0x1401a3601  mov     [rdi+420h], rax
0x1401a3608  jmp     short loc_1401A3635
0x1401a360a  lea     rcx, [rbp+57h+var_90]
0x1401a360e  mov     [rbp+57h+var_90], rax
0x1401a3612  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x1401a3619  nop     dword ptr [rax+rax+00h]
0x1401a361e  mov     qword ptr [rdi+420h], 0
0x1401a3629  jmp     loc_1401A33A0
0x1401a362e  mov     [rdi+418h], rax
0x1401a3635  lea     rcx, [rbp+57h+var_80]; this
0x1401a3639  call    ??1RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::~RGNMEMOBJTMP(void)
0x1401a363e  lea     rcx, [rbp+57h+var_90]; this
0x1401a3642  call    ??1RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::~RGNMEMOBJTMP(void)
0x1401a3647  jmp     loc_1401A33AE
```
