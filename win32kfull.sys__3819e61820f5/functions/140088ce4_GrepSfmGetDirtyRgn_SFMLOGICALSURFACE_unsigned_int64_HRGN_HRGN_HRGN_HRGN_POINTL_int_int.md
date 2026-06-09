# GrepSfmGetDirtyRgn(SFMLOGICALSURFACE *,unsigned __int64,HRGN__ * *,HRGN__ * *,HRGN__ * *,HRGN__ * *,_POINTL *,int *,int *)

- ea: `0x140088ce4`
- end: `0x1400890a6`
- name: `?GrepSfmGetDirtyRgn@@YAJPEAVSFMLOGICALSURFACE@@_KPEAPEAUHRGN__@@222PEAU_POINTL@@PEAH4@Z`
- size: `962`
- prototype: `__int64 __usercall@<rax>(struct SFMLOGICALSURFACE *this@<rcx>, unsigned __int64@<rdx>, HRGN *@<r8>, HRGN *@<r9>, HRGN *, HRGN *, struct _POINTL *, int *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14008821c`

## callees

- `0x140088ce4`
- `0x1400890ac`
- `0x14008bacc`
- `0x14019de6c`

## import_xrefs

- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140088f0d`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140088f0d`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x140088efd`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x140088efd`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140088f77`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140089095`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140088f77`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140089095`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140088f67`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140088f67`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140088f3c`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140088f3c`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x140088dc3`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x140088dc3`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x140088f57`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x140088f57`
- `win32kbase!GreReleasePushLockExclusive` at `0x140088e6e`
- `win32kbase!GreReleasePushLockExclusive` at `0x140088e6e`
- `win32kbase!GreAcquirePushLockExclusive` at `0x140088d23`
- `win32kbase!GreAcquirePushLockExclusive` at `0x140088d23`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x140088e16`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x14008907d`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x140088e16`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x14008907d`
- `win32kbase!EtwTraceMoveRegion` at `0x140088fed`
- `win32kbase!EtwTraceMoveRegion` at `0x140088fed`
- `win32kbase!EtwTraceDWMGetDirtyRegion` at `0x140088eaa`
- `win32kbase!EtwTraceDWMGetDirtyRegion` at `0x140088eaa`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x140088e36`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x140088e36`
- `win32kbase!EtwTranslationUpdateOffsetDWM` at `0x140088fd1`
- `win32kbase!EtwTranslationUpdateOffsetDWM` at `0x140088fd1`

## pseudocode

```c
__int64 __fastcall GrepSfmGetDirtyRgn(
        struct _POINTL *this,
        int *a2,
        HRGN *a3,
        HRGN *a4,
        HRGN *a5,
        HRGN *a6,
        struct _POINTL *a7,
        int *a8,
        int *a9)
{
  struct W32_PUSH_LOCK *v9; // rsi
  int *v10; // r12
  HRGN *v11; // r15
  unsigned int v15; // edi
  int *v16; // rcx
  int **v17; // rdi
  struct _POINTL v18; // rax
  int *v19; // rax
  struct _POINTL v20; // r8
  int *v21; // rdx
  int v22; // ecx
  int v23; // eax
  bool v24; // zf
  struct RGNOBJ *v25; // rdx
  HRGN v26; // rax
  HRGN v28; // rax
  HRGN v29; // rax
  struct _POINTL *v30; // rcx
  HRGN *v31; // r15
  int *v32; // [rsp+20h] [rbp-10h] BYREF
  struct _POINTL v33; // [rsp+28h] [rbp-8h] BYREF
  int *v34; // [rsp+70h] [rbp+40h] BYREF
  HRGN *v35; // [rsp+88h] [rbp+58h]

  v35 = a4;
  v9 = (struct W32_PUSH_LOCK *)&this[32];
  v10 = 0;
  v11 = a4;
  v15 = -1073741811;
  if ( this != (struct _POINTL *)-256LL )
    GreAcquirePushLockExclusive((struct W32_PUSH_LOCK *)&this[32]);
  v16 = a9;
  *a9 = 0;
  if ( this[23] )
  {
    v17 = (int **)&this[16];
    *v16 = this[21].x;
    if ( this[21].x == 1 && (int *)SFMLOGICALSURFACE::uiCookie((SFMLOGICALSURFACE *)this) == a2 )
    {
      v10 = (int *)a6;
      if ( a6 )
      {
        v31 = a5;
        v34 = (int *)this[20];
        if ( a5 && *(_QWORD *)&this[18] )
        {
          a9 = (int *)this[18];
          *v31 = RGNOBJ::hrgnAssociate((RGNOBJ *)&a9);
        }
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))EtwTranslationUpdateOffsetDWM)(
          *this,
          *(_QWORD *)&this[19],
          HIDWORD(*(_QWORD *)&this[19]));
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))EtwTraceMoveRegion)(*this, 0, 6, *(_QWORD *)&this[20]);
        v29 = RGNOBJ::hrgnAssociate((RGNOBJ *)&v34);
        v30 = a7;
        *(_QWORD *)v10 = v29;
        v10 = 0;
        if ( v30 )
          *v30 = this[19];
        METAREGION::vClearMoveData((METAREGION *)&this[16], 0);
        v11 = v35;
      }
    }
    else if ( a6 )
    {
      *a6 = 0;
    }
    if ( a8 )
      *a8 = ((unsigned int)this[31].y >> 4) & 1;
    if ( a3 )
    {
      v18 = this[23];
      v19 = v18 ? *(int **)(*(_QWORD *)&v18 + 8LL) : v10;
      if ( v19 == a2 )
      {
        a9 = *v17;
        if ( a9 )
        {
          ((void (__fastcall *)(_QWORD, _QWORD))EtwTraceDWMGetDirtyRegion)(*this, 0);
          v28 = RGNOBJ::hrgnAssociate((RGNOBJ *)&a9);
          *a3 = v28;
          if ( v28 )
          {
            *v17 = v10;
            this[31].y &= ~2u;
          }
        }
      }
    }
    if ( v11 && ((this[31].y & 4) != 0 || !a2) )
    {
      RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&a9);
      v20 = this[11];
      v21 = (int *)this[10];
      v33 = v20;
      v32 = v21;
      if ( a9 != v10 )
      {
        v22 = (int)v10;
        v23 = (int)v10;
        LOBYTE(v22) = v21 != 0;
        LOBYTE(v23) = v20 != 0;
        if ( v23 == v22 )
        {
          if ( *(_QWORD *)&v20 && v21 )
          {
            v34 = v10;
            RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v34, 0x70u);
            RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v34);
            if ( (this[31].y & 4) != 0 )
            {
              if ( v34 != v10 && RGNOBJ::bMerge((RGNOBJ *)&v34, (struct RGNOBJ *)&v33, (struct RGNOBJ *)&v32, 8u) )
                RGNOBJ::vSwap((RGNOBJ *)&v34, (struct RGNOBJ *)&a9);
            }
            else
            {
              RGNOBJ::bCopy((RGNOBJ *)&a9, (struct RGNOBJ *)&v33);
            }
            RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v34);
            RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v34);
          }
        }
        else
        {
          v24 = v21 == 0;
          v25 = (struct RGNOBJ *)&v32;
          if ( v24 )
            v25 = (struct RGNOBJ *)&v33;
          RGNOBJ::bCopy((RGNOBJ *)&a9, v25);
        }
        if ( v32 != v10 && (this[31].y & 0x10) != 0 )
          RGNOBJ::vSet((RGNOBJ *)&v32);
        if ( a9 != v10 )
        {
          v26 = RGNOBJ::hrgnAssociate((RGNOBJ *)&a9);
          *v11 = v26;
          if ( !v26 )
            RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&a9);
        }
      }
    }
    v15 = (unsigned int)v10;
  }
  if ( v9 )
    GreReleasePushLockExclusive(v9);
  return v15;
}

```

## disassembly

```asm
0x140088ce4  mov     [rsp-38h+arg_8], rbx
0x140088ce9  mov     [rsp-38h+arg_18], r9
0x140088cee  push    rbp
0x140088cef  push    rsi
0x140088cf0  push    rdi
0x140088cf1  push    r12
0x140088cf3  push    r13
0x140088cf5  push    r14
0x140088cf7  push    r15
0x140088cf9  mov     rbp, rsp
0x140088cfc  sub     rsp, 30h
0x140088d00  lea     rsi, [rcx+100h]
0x140088d07  xor     r12d, r12d
0x140088d0a  mov     r15, r9
0x140088d0d  mov     r13, r8
0x140088d10  mov     r14, rdx
0x140088d13  mov     rbx, rcx
0x140088d16  mov     edi, 0C000000Dh
0x140088d1b  test    rsi, rsi
0x140088d1e  jz      short loc_140088D2F
0x140088d20  mov     rcx, rsi
0x140088d23  call    cs:__imp_?GreAcquirePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreAcquirePushLockExclusive(W32_PUSH_LOCK *)
0x140088d2a  nop     dword ptr [rax+rax+00h]
0x140088d2f  mov     rcx, [rbp+arg_40]
0x140088d36  mov     [rcx], r12d
0x140088d39  cmp     [rbx+0B8h], r12
0x140088d40  jz      loc_140088E66
0x140088d46  lea     rdi, [rbx+80h]
0x140088d4d  mov     eax, [rdi+28h]
0x140088d50  mov     [rcx], eax
0x140088d52  cmp     dword ptr [rbx+0A8h], 1
0x140088d59  jz      loc_14008902F
0x140088d5f  mov     rax, [rbp+arg_28]
0x140088d63  test    rax, rax
0x140088d66  jnz     loc_14008906A
0x140088d6c  mov     rcx, [rbp+arg_38]
0x140088d70  test    rcx, rcx
0x140088d73  jz      short loc_140088D83
0x140088d75  mov     eax, [rbx+0FCh]
0x140088d7b  shr     eax, 4
0x140088d7e  and     eax, 1
0x140088d81  mov     [rcx], eax
0x140088d83  test    r13, r13
0x140088d86  jz      short loc_140088DA5
0x140088d88  mov     rax, [rbx+0B8h]
0x140088d8f  test    rax, rax
0x140088d92  jz      loc_140088F96
0x140088d98  mov     rax, [rax+8]
0x140088d9c  cmp     rax, r14
0x140088d9f  jz      loc_140088E92
0x140088da5  test    r15, r15
0x140088da8  jz      loc_140088E63
0x140088dae  mov     eax, [rbx+0FCh]
0x140088db4  test    al, 4
0x140088db6  jz      loc_140088F88
0x140088dbc  lea     rcx, [rbp+arg_40]
0x140088dc3  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x140088dca  nop     dword ptr [rax+rax+00h]
0x140088dcf  mov     r8, [rbx+58h]
0x140088dd3  mov     rdx, [rbx+50h]
0x140088dd7  mov     [rbp+var_8], r8
0x140088ddb  mov     [rbp+var_10], rdx
0x140088ddf  cmp     [rbp+arg_40], r12
0x140088de6  jz      short loc_140088E63
0x140088de8  test    rdx, rdx
0x140088deb  mov     ecx, r12d
0x140088dee  mov     eax, r12d
0x140088df1  setnz   cl
0x140088df4  test    r8, r8
0x140088df7  setnz   al
0x140088dfa  cmp     eax, ecx
0x140088dfc  jz      loc_140088EDE
0x140088e02  test    rdx, rdx
0x140088e05  lea     rcx, [rbp+arg_40]
0x140088e0c  lea     rdx, [rbp+var_10]
0x140088e10  jnz     short loc_140088E16
0x140088e12  lea     rdx, [rbp+var_8]
0x140088e16  call    cs:__imp_?bCopy@RGNOBJ@@QEAAHAEAV1@@Z; RGNOBJ::bCopy(RGNOBJ &)
0x140088e1d  nop     dword ptr [rax+rax+00h]
0x140088e22  cmp     [rbp+var_10], r12
0x140088e26  jz      short loc_140088E42
0x140088e28  mov     eax, [rbx+0FCh]
0x140088e2e  test    al, 10h
0x140088e30  jz      short loc_140088E42
0x140088e32  lea     rcx, [rbp+var_10]
0x140088e36  call    cs:__imp_?vSet@RGNOBJ@@QEAAXXZ; RGNOBJ::vSet(void)
0x140088e3d  nop     dword ptr [rax+rax+00h]
0x140088e42  cmp     [rbp+arg_40], r12
0x140088e49  jz      short loc_140088E63
0x140088e4b  lea     rcx, [rbp+arg_40]; this
0x140088e52  call    ?hrgnAssociate@RGNOBJ@@QEAAPEAUHRGN__@@XZ; RGNOBJ::hrgnAssociate(void)
0x140088e57  mov     [r15], rax
0x140088e5a  test    rax, rax
0x140088e5d  jz      loc_14008908E
0x140088e63  mov     edi, r12d
0x140088e66  test    rsi, rsi
0x140088e69  jz      short loc_140088E7A
0x140088e6b  mov     rcx, rsi
0x140088e6e  call    cs:__imp_?GreReleasePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreReleasePushLockExclusive(W32_PUSH_LOCK *)
0x140088e75  nop     dword ptr [rax+rax+00h]
0x140088e7a  mov     rbx, [rsp+30h+arg_8]
0x140088e7f  mov     eax, edi
0x140088e81  add     rsp, 30h
0x140088e85  pop     r15
0x140088e87  pop     r14
0x140088e89  pop     r13
0x140088e8b  pop     r12
0x140088e8d  pop     rdi
0x140088e8e  pop     rsi
0x140088e8f  pop     rbp
0x140088e90  retn
0x140088e92  mov     r8, [rdi]
0x140088e95  mov     [rbp+arg_40], r8
0x140088e9c  test    r8, r8
0x140088e9f  jz      loc_140088DA5
0x140088ea5  mov     rcx, [rbx]
0x140088ea8  xor     edx, edx
0x140088eaa  call    cs:__imp_EtwTraceDWMGetDirtyRegion
0x140088eb1  nop     dword ptr [rax+rax+00h]
0x140088eb6  lea     rcx, [rbp+arg_40]; this
0x140088ebd  call    ?hrgnAssociate@RGNOBJ@@QEAAPEAUHRGN__@@XZ; RGNOBJ::hrgnAssociate(void)
0x140088ec2  mov     [r13+0], rax
0x140088ec6  test    rax, rax
0x140088ec9  jz      loc_140088DA5
0x140088ecf  mov     [rdi], r12
0x140088ed2  and     dword ptr [rbx+0FCh], 0FFFFFFFDh
0x140088ed9  jmp     loc_140088DA5
0x140088ede  test    r8, r8
0x140088ee1  jz      loc_140088E22
0x140088ee7  test    rdx, rdx
0x140088eea  jz      loc_140088E22
0x140088ef0  mov     edx, 70h ; 'p'
0x140088ef5  mov     [rbp+arg_0], r12
0x140088ef9  lea     rcx, [rbp+arg_0]
0x140088efd  call    cs:__imp_?vInitialize@RGNMEMOBJ@@QEAAXK@Z; RGNMEMOBJ::vInitialize(ulong)
0x140088f04  nop     dword ptr [rax+rax+00h]
0x140088f09  lea     rcx, [rbp+arg_0]
0x140088f0d  call    cs:__imp_?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPushThreadGuardedObject(void)
0x140088f14  nop     dword ptr [rax+rax+00h]
0x140088f19  mov     eax, [rbx+0FCh]
0x140088f1f  test    al, 4
0x140088f21  jz      loc_140089072
0x140088f27  cmp     [rbp+arg_0], r12
0x140088f2b  jz      short loc_140088F63
0x140088f2d  mov     r9b, 8
0x140088f30  lea     r8, [rbp+var_10]
0x140088f34  lea     rdx, [rbp+var_8]
0x140088f38  lea     rcx, [rbp+arg_0]
0x140088f3c  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x140088f43  nop     dword ptr [rax+rax+00h]
0x140088f48  test    eax, eax
0x140088f4a  jz      short loc_140088F63
0x140088f4c  lea     rdx, [rbp+arg_40]
0x140088f53  lea     rcx, [rbp+arg_0]
0x140088f57  call    cs:__imp_?vSwap@RGNOBJ@@QEAAXPEAV1@@Z; RGNOBJ::vSwap(RGNOBJ *)
0x140088f5e  nop     dword ptr [rax+rax+00h]
0x140088f63  lea     rcx, [rbp+arg_0]
0x140088f67  call    cs:__imp_?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPopThreadGuardedObject(void)
0x140088f6e  nop     dword ptr [rax+rax+00h]
0x140088f73  lea     rcx, [rbp+arg_0]
0x140088f77  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x140088f7e  nop     dword ptr [rax+rax+00h]
0x140088f83  jmp     loc_140088E22
0x140088f88  test    r14, r14
0x140088f8b  jz      loc_140088DBC
0x140088f91  jmp     loc_140088E63
0x140088f96  mov     rax, r12
0x140088f99  jmp     loc_140088D9C
0x140088f9e  mov     rax, [rbx+90h]
0x140088fa5  test    rax, rax
0x140088fa8  jz      short loc_140088FC0
0x140088faa  lea     rcx, [rbp+arg_40]; this
0x140088fb1  mov     [rbp+arg_40], rax
0x140088fb8  call    ?hrgnAssociate@RGNOBJ@@QEAAPEAUHRGN__@@XZ; RGNOBJ::hrgnAssociate(void)
0x140088fbd  mov     [r15], rax
0x140088fc0  mov     rdx, [rbx+98h]
0x140088fc7  mov     rcx, [rbx]
0x140088fca  mov     r8, rdx
0x140088fcd  shr     r8, 20h
0x140088fd1  call    cs:__imp_EtwTranslationUpdateOffsetDWM
0x140088fd8  nop     dword ptr [rax+rax+00h]
0x140088fdd  mov     r9, [rbx+0A0h]
0x140088fe4  xor     edx, edx
0x140088fe6  mov     rcx, [rbx]
0x140088fe9  lea     r8d, [rdx+6]
0x140088fed  call    cs:__imp_EtwTraceMoveRegion
0x140088ff4  nop     dword ptr [rax+rax+00h]
0x140088ff9  lea     rcx, [rbp+arg_0]; this
0x140088ffd  call    ?hrgnAssociate@RGNOBJ@@QEAAPEAUHRGN__@@XZ; RGNOBJ::hrgnAssociate(void)
0x140089002  mov     rcx, [rbp+arg_30]
0x140089006  mov     [r12], rax
0x14008900a  xor     r12d, r12d
0x14008900d  test    rcx, rcx
0x140089010  jz      short loc_14008901C
0x140089012  mov     rax, [rbx+98h]
0x140089019  mov     [rcx], rax
0x14008901c  xor     edx, edx; int
0x14008901e  mov     rcx, rdi; this
0x140089021  call    ?vClearMoveData@METAREGION@@QEAAXH@Z; METAREGION::vClearMoveData(int)
0x140089026  mov     r15, [rbp+arg_18]
0x14008902a  jmp     loc_140088D6C
0x14008902f  mov     rcx, rbx; this
0x140089032  call    ?uiCookie@SFMLOGICALSURFACE@@QEBA_KXZ; SFMLOGICALSURFACE::uiCookie(void)
0x140089037  cmp     rax, r14
0x14008903a  jnz     loc_140088D5F
0x140089040  mov     r12, [rbp+arg_28]
0x140089044  test    r12, r12
0x140089047  jz      loc_140088D6C
0x14008904d  mov     r15, [rbp+arg_20]
0x140089051  mov     rax, [rbx+0A0h]
0x140089058  mov     [rbp+arg_0], rax
0x14008905c  test    r15, r15
0x14008905f  jz      loc_140088FC0
0x140089065  jmp     loc_140088F9E
0x14008906a  mov     [rax], r12
0x14008906d  jmp     loc_140088D6C
0x140089072  lea     rdx, [rbp+var_8]
0x140089076  lea     rcx, [rbp+arg_40]
0x14008907d  call    cs:__imp_?bCopy@RGNOBJ@@QEAAHAEAV1@@Z; RGNOBJ::bCopy(RGNOBJ &)
0x140089084  nop     dword ptr [rax+rax+00h]
0x140089089  jmp     loc_140088F63
0x14008908e  lea     rcx, [rbp+arg_40]
0x140089095  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14008909c  nop     dword ptr [rax+rax+00h]
0x1400890a1  jmp     loc_140088E63
```
