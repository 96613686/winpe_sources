# GrepSfmGetDirtyRgn(SFMLOGICALSURFACE *,unsigned __int64,HRGN__ * *,HRGN__ * *,HRGN__ * *,HRGN__ * *,_POINTL *,int *,int *)

- ea: `0x140181e44`
- end: `0x140182206`
- name: `?GrepSfmGetDirtyRgn@@YAJPEAVSFMLOGICALSURFACE@@_KPEAPEAUHRGN__@@222PEAU_POINTL@@PEAH4@Z`
- size: `962`
- prototype: `__int64 __fastcall(struct _POINTL *this, int *, HRGN *, HRGN *, HRGN *, HRGN *, struct _POINTL *, int *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1400198b0`

## callees

- `0x14011f5e4`
- `0x140181e44`
- `0x14018220c`
- `0x14019f928`

## import_xrefs

- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14018206d`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14018206d`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x14018205d`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x14018205d`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401820d7`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401821f5`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401820d7`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401821f5`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1401820c7`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1401820c7`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14018209c`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14018209c`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x140181f23`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x140181f23`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x1401820b7`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x1401820b7`
- `win32kbase!GreReleasePushLockExclusive` at `0x140181fce`
- `win32kbase!GreReleasePushLockExclusive` at `0x140181fce`
- `win32kbase!GreAcquirePushLockExclusive` at `0x140181e83`
- `win32kbase!GreAcquirePushLockExclusive` at `0x140181e83`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x140181f76`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x1401821dd`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x140181f76`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x1401821dd`
- `win32kbase!EtwTraceMoveRegion` at `0x14018214d`
- `win32kbase!EtwTraceMoveRegion` at `0x14018214d`
- `win32kbase!EtwTraceDWMGetDirtyRegion` at `0x14018200a`
- `win32kbase!EtwTraceDWMGetDirtyRegion` at `0x14018200a`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x140181f96`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x140181f96`
- `win32kbase!EtwTranslationUpdateOffsetDWM` at `0x140182131`
- `win32kbase!EtwTranslationUpdateOffsetDWM` at `0x140182131`

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
0x140181e44  mov     [rsp-38h+arg_8], rbx
0x140181e49  mov     [rsp-38h+arg_18], r9
0x140181e4e  push    rbp
0x140181e4f  push    rsi
0x140181e50  push    rdi
0x140181e51  push    r12
0x140181e53  push    r13
0x140181e55  push    r14
0x140181e57  push    r15
0x140181e59  mov     rbp, rsp
0x140181e5c  sub     rsp, 30h
0x140181e60  lea     rsi, [rcx+100h]
0x140181e67  xor     r12d, r12d
0x140181e6a  mov     r15, r9
0x140181e6d  mov     r13, r8
0x140181e70  mov     r14, rdx
0x140181e73  mov     rbx, rcx
0x140181e76  mov     edi, 0C000000Dh
0x140181e7b  test    rsi, rsi
0x140181e7e  jz      short loc_140181E8F
0x140181e80  mov     rcx, rsi
0x140181e83  call    cs:__imp_?GreAcquirePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreAcquirePushLockExclusive(W32_PUSH_LOCK *)
0x140181e8a  nop     dword ptr [rax+rax+00h]
0x140181e8f  mov     rcx, [rbp+arg_40]
0x140181e96  mov     [rcx], r12d
0x140181e99  cmp     [rbx+0B8h], r12
0x140181ea0  jz      loc_140181FC6
0x140181ea6  lea     rdi, [rbx+80h]
0x140181ead  mov     eax, [rdi+28h]
0x140181eb0  mov     [rcx], eax
0x140181eb2  cmp     dword ptr [rbx+0A8h], 1
0x140181eb9  jz      loc_14018218F
0x140181ebf  mov     rax, [rbp+arg_28]
0x140181ec3  test    rax, rax
0x140181ec6  jnz     loc_1401821CA
0x140181ecc  mov     rcx, [rbp+arg_38]
0x140181ed0  test    rcx, rcx
0x140181ed3  jz      short loc_140181EE3
0x140181ed5  mov     eax, [rbx+0FCh]
0x140181edb  shr     eax, 4
0x140181ede  and     eax, 1
0x140181ee1  mov     [rcx], eax
0x140181ee3  test    r13, r13
0x140181ee6  jz      short loc_140181F05
0x140181ee8  mov     rax, [rbx+0B8h]
0x140181eef  test    rax, rax
0x140181ef2  jz      loc_1401820F6
0x140181ef8  mov     rax, [rax+8]
0x140181efc  cmp     rax, r14
0x140181eff  jz      loc_140181FF2
0x140181f05  test    r15, r15
0x140181f08  jz      loc_140181FC3
0x140181f0e  mov     eax, [rbx+0FCh]
0x140181f14  test    al, 4
0x140181f16  jz      loc_1401820E8
0x140181f1c  lea     rcx, [rbp+arg_40]
0x140181f23  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x140181f2a  nop     dword ptr [rax+rax+00h]
0x140181f2f  mov     r8, [rbx+58h]
0x140181f33  mov     rdx, [rbx+50h]
0x140181f37  mov     [rbp+var_8], r8
0x140181f3b  mov     [rbp+var_10], rdx
0x140181f3f  cmp     [rbp+arg_40], r12
0x140181f46  jz      short loc_140181FC3
0x140181f48  test    rdx, rdx
0x140181f4b  mov     ecx, r12d
0x140181f4e  mov     eax, r12d
0x140181f51  setnz   cl
0x140181f54  test    r8, r8
0x140181f57  setnz   al
0x140181f5a  cmp     eax, ecx
0x140181f5c  jz      loc_14018203E
0x140181f62  test    rdx, rdx
0x140181f65  lea     rcx, [rbp+arg_40]
0x140181f6c  lea     rdx, [rbp+var_10]
0x140181f70  jnz     short loc_140181F76
0x140181f72  lea     rdx, [rbp+var_8]
0x140181f76  call    cs:__imp_?bCopy@RGNOBJ@@QEAAHAEAV1@@Z; RGNOBJ::bCopy(RGNOBJ &)
0x140181f7d  nop     dword ptr [rax+rax+00h]
0x140181f82  cmp     [rbp+var_10], r12
0x140181f86  jz      short loc_140181FA2
0x140181f88  mov     eax, [rbx+0FCh]
0x140181f8e  test    al, 10h
0x140181f90  jz      short loc_140181FA2
0x140181f92  lea     rcx, [rbp+var_10]
0x140181f96  call    cs:__imp_?vSet@RGNOBJ@@QEAAXXZ; RGNOBJ::vSet(void)
0x140181f9d  nop     dword ptr [rax+rax+00h]
0x140181fa2  cmp     [rbp+arg_40], r12
0x140181fa9  jz      short loc_140181FC3
0x140181fab  lea     rcx, [rbp+arg_40]; this
0x140181fb2  call    ?hrgnAssociate@RGNOBJ@@QEAAPEAUHRGN__@@XZ; RGNOBJ::hrgnAssociate(void)
0x140181fb7  mov     [r15], rax
0x140181fba  test    rax, rax
0x140181fbd  jz      loc_1401821EE
0x140181fc3  mov     edi, r12d
0x140181fc6  test    rsi, rsi
0x140181fc9  jz      short loc_140181FDA
0x140181fcb  mov     rcx, rsi
0x140181fce  call    cs:__imp_?GreReleasePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreReleasePushLockExclusive(W32_PUSH_LOCK *)
0x140181fd5  nop     dword ptr [rax+rax+00h]
0x140181fda  mov     rbx, [rsp+30h+arg_8]
0x140181fdf  mov     eax, edi
0x140181fe1  add     rsp, 30h
0x140181fe5  pop     r15
0x140181fe7  pop     r14
0x140181fe9  pop     r13
0x140181feb  pop     r12
0x140181fed  pop     rdi
0x140181fee  pop     rsi
0x140181fef  pop     rbp
0x140181ff0  retn
0x140181ff2  mov     r8, [rdi]
0x140181ff5  mov     [rbp+arg_40], r8
0x140181ffc  test    r8, r8
0x140181fff  jz      loc_140181F05
0x140182005  mov     rcx, [rbx]
0x140182008  xor     edx, edx
0x14018200a  call    cs:__imp_EtwTraceDWMGetDirtyRegion
0x140182011  nop     dword ptr [rax+rax+00h]
0x140182016  lea     rcx, [rbp+arg_40]; this
0x14018201d  call    ?hrgnAssociate@RGNOBJ@@QEAAPEAUHRGN__@@XZ; RGNOBJ::hrgnAssociate(void)
0x140182022  mov     [r13+0], rax
0x140182026  test    rax, rax
0x140182029  jz      loc_140181F05
0x14018202f  mov     [rdi], r12
0x140182032  and     dword ptr [rbx+0FCh], 0FFFFFFFDh
0x140182039  jmp     loc_140181F05
0x14018203e  test    r8, r8
0x140182041  jz      loc_140181F82
0x140182047  test    rdx, rdx
0x14018204a  jz      loc_140181F82
0x140182050  mov     edx, 70h ; 'p'
0x140182055  mov     [rbp+arg_0], r12
0x140182059  lea     rcx, [rbp+arg_0]
0x14018205d  call    cs:__imp_?vInitialize@RGNMEMOBJ@@QEAAXK@Z; RGNMEMOBJ::vInitialize(ulong)
0x140182064  nop     dword ptr [rax+rax+00h]
0x140182069  lea     rcx, [rbp+arg_0]
0x14018206d  call    cs:__imp_?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPushThreadGuardedObject(void)
0x140182074  nop     dword ptr [rax+rax+00h]
0x140182079  mov     eax, [rbx+0FCh]
0x14018207f  test    al, 4
0x140182081  jz      loc_1401821D2
0x140182087  cmp     [rbp+arg_0], r12
0x14018208b  jz      short loc_1401820C3
0x14018208d  mov     r9b, 8
0x140182090  lea     r8, [rbp+var_10]
0x140182094  lea     rdx, [rbp+var_8]
0x140182098  lea     rcx, [rbp+arg_0]
0x14018209c  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x1401820a3  nop     dword ptr [rax+rax+00h]
0x1401820a8  test    eax, eax
0x1401820aa  jz      short loc_1401820C3
0x1401820ac  lea     rdx, [rbp+arg_40]
0x1401820b3  lea     rcx, [rbp+arg_0]
0x1401820b7  call    cs:__imp_?vSwap@RGNOBJ@@QEAAXPEAV1@@Z; RGNOBJ::vSwap(RGNOBJ *)
0x1401820be  nop     dword ptr [rax+rax+00h]
0x1401820c3  lea     rcx, [rbp+arg_0]
0x1401820c7  call    cs:__imp_?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPopThreadGuardedObject(void)
0x1401820ce  nop     dword ptr [rax+rax+00h]
0x1401820d3  lea     rcx, [rbp+arg_0]
0x1401820d7  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x1401820de  nop     dword ptr [rax+rax+00h]
0x1401820e3  jmp     loc_140181F82
0x1401820e8  test    r14, r14
0x1401820eb  jz      loc_140181F1C
0x1401820f1  jmp     loc_140181FC3
0x1401820f6  mov     rax, r12
0x1401820f9  jmp     loc_140181EFC
0x1401820fe  mov     rax, [rbx+90h]
0x140182105  test    rax, rax
0x140182108  jz      short loc_140182120
0x14018210a  lea     rcx, [rbp+arg_40]; this
0x140182111  mov     [rbp+arg_40], rax
0x140182118  call    ?hrgnAssociate@RGNOBJ@@QEAAPEAUHRGN__@@XZ; RGNOBJ::hrgnAssociate(void)
0x14018211d  mov     [r15], rax
0x140182120  mov     rdx, [rbx+98h]
0x140182127  mov     rcx, [rbx]
0x14018212a  mov     r8, rdx
0x14018212d  shr     r8, 20h
0x140182131  call    cs:__imp_EtwTranslationUpdateOffsetDWM
0x140182138  nop     dword ptr [rax+rax+00h]
0x14018213d  mov     r9, [rbx+0A0h]
0x140182144  xor     edx, edx
0x140182146  mov     rcx, [rbx]
0x140182149  lea     r8d, [rdx+6]
0x14018214d  call    cs:__imp_EtwTraceMoveRegion
0x140182154  nop     dword ptr [rax+rax+00h]
0x140182159  lea     rcx, [rbp+arg_0]; this
0x14018215d  call    ?hrgnAssociate@RGNOBJ@@QEAAPEAUHRGN__@@XZ; RGNOBJ::hrgnAssociate(void)
0x140182162  mov     rcx, [rbp+arg_30]
0x140182166  mov     [r12], rax
0x14018216a  xor     r12d, r12d
0x14018216d  test    rcx, rcx
0x140182170  jz      short loc_14018217C
0x140182172  mov     rax, [rbx+98h]
0x140182179  mov     [rcx], rax
0x14018217c  xor     edx, edx; int
0x14018217e  mov     rcx, rdi; this
0x140182181  call    ?vClearMoveData@METAREGION@@QEAAXH@Z; METAREGION::vClearMoveData(int)
0x140182186  mov     r15, [rbp+arg_18]
0x14018218a  jmp     loc_140181ECC
0x14018218f  mov     rcx, rbx; this
0x140182192  call    ?uiCookie@SFMLOGICALSURFACE@@QEBA_KXZ; SFMLOGICALSURFACE::uiCookie(void)
0x140182197  cmp     rax, r14
0x14018219a  jnz     loc_140181EBF
0x1401821a0  mov     r12, [rbp+arg_28]
0x1401821a4  test    r12, r12
0x1401821a7  jz      loc_140181ECC
0x1401821ad  mov     r15, [rbp+arg_20]
0x1401821b1  mov     rax, [rbx+0A0h]
0x1401821b8  mov     [rbp+arg_0], rax
0x1401821bc  test    r15, r15
0x1401821bf  jz      loc_140182120
0x1401821c5  jmp     loc_1401820FE
0x1401821ca  mov     [rax], r12
0x1401821cd  jmp     loc_140181ECC
0x1401821d2  lea     rdx, [rbp+var_8]
0x1401821d6  lea     rcx, [rbp+arg_40]
0x1401821dd  call    cs:__imp_?bCopy@RGNOBJ@@QEAAHAEAV1@@Z; RGNOBJ::bCopy(RGNOBJ &)
0x1401821e4  nop     dword ptr [rax+rax+00h]
0x1401821e9  jmp     loc_1401820C3
0x1401821ee  lea     rcx, [rbp+arg_40]
0x1401821f5  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x1401821fc  nop     dword ptr [rax+rax+00h]
0x140182201  jmp     loc_140181FC3
```
