# vSpComputeNoPresentRegion(_SPRITESTATE *,int)

- ea: `0x14008c480`
- end: `0x14008c784`
- name: `?vSpComputeNoPresentRegion@@YAXPEAU_SPRITESTATE@@H@Z`
- size: `772`
- prototype: `void __fastcall(struct _SPRITESTATE *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14008caa0`
- `0x140119920`

## callees

- `0x140069bc8`
- `0x140077348`
- `0x140079b44`
- `0x1400876f0`
- `0x14008beb4`
- `0x14008c480`
- `0x1402b1394`
- `0x14030ad88`
- `0x140342fa0`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008c4bc`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008c4bc`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14008c52c`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14008c569`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14008c74a`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14008c52c`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14008c569`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14008c74a`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14008c5b6`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14008c5ca`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14008c669`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14008c5b6`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14008c5ca`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14008c669`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14008c6d6`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14008c6d6`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14008c549`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14008c549`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x14008c6ee`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x14008c6ee`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x14008c64a`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x14008c693`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x14008c6a7`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x14008c64a`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x14008c693`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x14008c6a7`
- `win32kbase!?vStamp@REGION@@AEAAXXZ` at `0x14008c724`
- `win32kbase!?vStamp@REGION@@AEAAXXZ` at `0x14008c724`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x14008c60d`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x14008c60d`
- `win32kbase!?bDeleteRGNOBJAPI@RGNOBJAPI@@QEAAHXZ` at `0x14008c6fe`
- `win32kbase!?bDeleteRGNOBJAPI@RGNOBJAPI@@QEAAHXZ` at `0x14008c6fe`

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
0x14008c480  mov     [rsp-8+arg_8], rbx
0x14008c485  mov     [rsp-8+arg_10], rsi
0x14008c48a  push    rbp
0x14008c48b  push    rdi
0x14008c48c  push    r14
0x14008c48e  lea     rbp, [rsp-47h]
0x14008c493  sub     rsp, 0B0h
0x14008c49a  mov     rax, cs:__security_cookie
0x14008c4a1  xor     rax, rsp
0x14008c4a4  mov     [rbp+57h+var_20], rax
0x14008c4a8  mov     rbx, [rcx]
0x14008c4ab  xorps   xmm0, xmm0
0x14008c4ae  movups  [rbp+57h+var_40], xmm0
0x14008c4b2  mov     [rbp+57h+var_88], rbx
0x14008c4b6  mov     r14d, edx
0x14008c4b9  mov     rdi, rcx
0x14008c4bc  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14008c4c3  nop     dword ptr [rax+rax+00h]
0x14008c4c8  mov     rax, [rdi+420h]
0x14008c4cf  test    rax, rax
0x14008c4d2  jnz     loc_14008C742
0x14008c4d8  test    r14d, r14d
0x14008c4db  jz      short loc_14008C518
0x14008c4dd  mov     rsi, [rdi+50h]
0x14008c4e1  test    rsi, rsi
0x14008c4e4  jnz     short loc_14008C545
0x14008c4e6  test    r14d, r14d
0x14008c4e9  jnz     short loc_14008C4F3
0x14008c4eb  mov     rcx, rdi; struct _SPRITESTATE *
0x14008c4ee  call    ?vSpComputeUnlockedRegion@@YAXPEAU_SPRITESTATE@@@Z; vSpComputeUnlockedRegion(_SPRITESTATE *)
0x14008c4f3  mov     rcx, [rbp+57h+var_20]
0x14008c4f7  xor     rcx, rsp; StackCookie
0x14008c4fa  call    __security_check_cookie
0x14008c4ff  lea     r11, [rsp+0C0h+var_10]
0x14008c507  mov     rbx, [r11+28h]
0x14008c50b  mov     rsi, [r11+30h]
0x14008c50f  mov     rsp, r11
0x14008c512  pop     r14
0x14008c514  pop     rdi
0x14008c515  pop     rbp
0x14008c516  retn
0x14008c518  mov     rax, [rdi+418h]
0x14008c51f  test    rax, rax
0x14008c522  jz      short loc_14008C4DD
0x14008c524  lea     rcx, [rbp+57h+var_90]
0x14008c528  mov     [rbp+57h+var_90], rax
0x14008c52c  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14008c533  nop     dword ptr [rax+rax+00h]
0x14008c538  mov     qword ptr [rdi+418h], 0
0x14008c543  jmp     short loc_14008C4DD
0x14008c545  lea     rcx, [rbp+57h+var_98]
0x14008c549  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x14008c550  nop     dword ptr [rax+rax+00h]
0x14008c555  lea     rcx, [rbp+57h+var_90]; this
0x14008c559  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x14008c55e  cmp     [rbp+57h+var_98], 0
0x14008c563  jnz     short loc_14008C57A
0x14008c565  lea     rcx, [rbp+57h+var_98]
0x14008c569  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14008c570  nop     dword ptr [rax+rax+00h]
0x14008c575  jmp     loc_14008C776
0x14008c57a  cmp     [rbp+57h+var_90], 0
0x14008c57f  jz      short loc_14008C565
0x14008c581  lea     rdx, [rbp+57h+var_A0]
0x14008c585  mov     qword ptr [rbp+57h+var_40], 0
0x14008c58d  lea     rcx, [rbp+57h+var_88]; this
0x14008c591  call    ?sizl@PDEVOBJ@@QEAA?AUtagSIZE@@XZ; PDEVOBJ::sizl(void)
0x14008c596  lea     rdx, [rbp+57h+var_A0]
0x14008c59a  mov     ecx, [rax]
0x14008c59c  mov     dword ptr [rbp+57h+var_40+8], ecx
0x14008c59f  lea     rcx, [rbp+57h+var_88]; this
0x14008c5a3  call    ?sizl@PDEVOBJ@@QEAA?AUtagSIZE@@XZ; PDEVOBJ::sizl(void)
0x14008c5a8  lea     rdx, [rbp+57h+var_40]
0x14008c5ac  mov     ecx, [rax+4]
0x14008c5af  mov     dword ptr [rbp+57h+var_40+0Ch], ecx
0x14008c5b2  lea     rcx, [rbp+57h+var_98]
0x14008c5b6  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x14008c5bd  nop     dword ptr [rax+rax+00h]
0x14008c5c2  lea     rdx, [rbp+57h+var_40]
0x14008c5c6  lea     rcx, [rbp+57h+var_90]
0x14008c5ca  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x14008c5d1  nop     dword ptr [rax+rax+00h]
0x14008c5d6  lea     rcx, [rbp+57h+var_80]; this
0x14008c5da  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x14008c5df  cmp     [rbp+57h+var_80], 0
0x14008c5e4  jz      loc_14008C720
0x14008c5ea  xorps   xmm0, xmm0
0x14008c5ed  lea     rdx, [rbp+57h+var_30]
0x14008c5f1  movups  [rbp+57h+var_30], xmm0
0x14008c5f5  mov     rcx, [rsi]
0x14008c5f8  xor     r8d, r8d
0x14008c5fb  call    UserGetClientRgn
0x14008c600  xor     r9d, r9d
0x14008c603  lea     rcx, [rbp+57h+var_78]
0x14008c607  xor     r8d, r8d
0x14008c60a  mov     rdx, rax
0x14008c60d  call    cs:__imp_??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x14008c614  nop     dword ptr [rax+rax+00h]
0x14008c619  cmp     [rbp+57h+var_78], 0
0x14008c61e  jz      loc_14008C70A
0x14008c624  mov     [rbp+57h+var_A0], 0
0x14008c62c  lea     rdx, [rbp+57h+var_A0]
0x14008c630  mov     eax, [rbx+0A10h]
0x14008c636  lea     rcx, [rbp+57h+var_78]
0x14008c63a  neg     eax
0x14008c63c  mov     dword ptr [rbp+57h+var_A0], eax
0x14008c63f  mov     eax, [rbx+0A14h]
0x14008c645  neg     eax
0x14008c647  mov     dword ptr [rbp+57h+var_A0+4], eax
0x14008c64a  call    cs:__imp_?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z; RGNOBJ::bOffset(_POINTL const *)
0x14008c651  nop     dword ptr [rax+rax+00h]
0x14008c656  mov     rax, [rdi+2C8h]
0x14008c65d  lea     rdx, [rbp+57h+var_30]
0x14008c661  lea     rcx, [rbp+57h+var_88]
0x14008c665  mov     [rbp+57h+var_88], rax
0x14008c669  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x14008c670  nop     dword ptr [rax+rax+00h]
0x14008c675  mov     eax, [rbx+0A10h]
0x14008c67b  lea     rdx, [rbp+57h+var_A0]
0x14008c67f  neg     eax
0x14008c681  lea     rcx, [rbp+57h+var_78]
0x14008c685  mov     dword ptr [rbp+57h+var_A0], eax
0x14008c688  mov     eax, [rbx+0A14h]
0x14008c68e  neg     eax
0x14008c690  mov     dword ptr [rbp+57h+var_A0+4], eax
0x14008c693  call    cs:__imp_?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z; RGNOBJ::bOffset(_POINTL const *)
0x14008c69a  nop     dword ptr [rax+rax+00h]
0x14008c69f  lea     rdx, [rbp+57h+var_A0]
0x14008c6a3  lea     rcx, [rbp+57h+var_88]
0x14008c6a7  call    cs:__imp_?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z; RGNOBJ::bOffset(_POINTL const *)
0x14008c6ae  nop     dword ptr [rax+rax+00h]
0x14008c6b3  lea     rcx, [rbp+57h+var_78]; this
0x14008c6b7  call    ?iComplexity@RGNOBJ@@QEBAJXZ; RGNOBJ::iComplexity(void)
0x14008c6bc  cmp     eax, 1
0x14008c6bf  lea     rcx, [rbp+57h+var_78]
0x14008c6c3  lea     r8, [rbp+57h+var_88]
0x14008c6c7  mov     r9b, 4
0x14008c6ca  cmovnz  r8, rcx
0x14008c6ce  lea     rdx, [rbp+57h+var_98]
0x14008c6d2  lea     rcx, [rbp+57h+var_80]
0x14008c6d6  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x14008c6dd  nop     dword ptr [rax+rax+00h]
0x14008c6e2  test    eax, eax
0x14008c6e4  jz      short loc_14008C6FA
0x14008c6e6  lea     rdx, [rbp+57h+var_98]
0x14008c6ea  lea     rcx, [rbp+57h+var_80]
0x14008c6ee  call    cs:__imp_?vSwap@RGNOBJ@@QEAAXPEAV1@@Z; RGNOBJ::vSwap(RGNOBJ *)
0x14008c6f5  nop     dword ptr [rax+rax+00h]
0x14008c6fa  lea     rcx, [rbp+57h+var_78]
0x14008c6fe  call    cs:__imp_?bDeleteRGNOBJAPI@RGNOBJAPI@@QEAAHXZ; RGNOBJAPI::bDeleteRGNOBJAPI(void)
0x14008c705  nop     dword ptr [rax+rax+00h]
0x14008c70a  mov     rsi, [rsi+8]
0x14008c70e  lea     rcx, [rbp+57h+var_78]; this
0x14008c712  call    ??1RGNOBJAPI@@QEAA@XZ; RGNOBJAPI::~RGNOBJAPI(void)
0x14008c717  test    rsi, rsi
0x14008c71a  jnz     loc_14008C5EA
0x14008c720  mov     rcx, [rbp+57h+var_98]
0x14008c724  call    cs:__imp_?vStamp@REGION@@AEAAXXZ; REGION::vStamp(void)
0x14008c72b  nop     dword ptr [rax+rax+00h]
0x14008c730  mov     rax, [rbp+57h+var_98]
0x14008c734  test    r14d, r14d
0x14008c737  jz      short loc_14008C766
0x14008c739  mov     [rdi+420h], rax
0x14008c740  jmp     short loc_14008C76D
0x14008c742  lea     rcx, [rbp+57h+var_90]
0x14008c746  mov     [rbp+57h+var_90], rax
0x14008c74a  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14008c751  nop     dword ptr [rax+rax+00h]
0x14008c756  mov     qword ptr [rdi+420h], 0
0x14008c761  jmp     loc_14008C4D8
0x14008c766  mov     [rdi+418h], rax
0x14008c76d  lea     rcx, [rbp+57h+var_80]; this
0x14008c771  call    ??1RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::~RGNMEMOBJTMP(void)
0x14008c776  lea     rcx, [rbp+57h+var_90]; this
0x14008c77a  call    ??1RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::~RGNMEMOBJTMP(void)
0x14008c77f  jmp     loc_14008C4E6
```
