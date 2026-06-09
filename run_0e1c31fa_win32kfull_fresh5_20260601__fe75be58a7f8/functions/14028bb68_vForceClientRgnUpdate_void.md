# vForceClientRgnUpdate(void)

- ea: `0x14028bb68`
- end: `0x14028bfec`
- name: `?vForceClientRgnUpdate@@YAXXZ`
- size: `1156`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140133f4c`
- `0x140304fa8`
- `0x1403266d0`

## callees

- `0x14005def4`
- `0x140097e80`
- `0x1400f8e58`
- `0x1400fb65c`
- `0x140183ad8`
- `0x14019d9d0`
- `0x1401f30d4`
- `0x14028b370`
- `0x14028ba1c`
- `0x14028ba70`
- `0x14028bb34`
- `0x14028bb68`
- `0x14028bff4`
- `0x1402af9e4`
- `0x14030c6b0`
- `0x140341ff0`
- `0x1403420d0`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14028bb89`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14028bb89`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14028bee8`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14028bf53`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14028bfb6`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14028bee8`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14028bf53`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14028bfb6`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14028bec3`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14028bf2e`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14028bf91`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14028bec3`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14028bf2e`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14028bf91`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14028bd26`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14028bd26`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x14028be06`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x14028be06`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x14028bd3a`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x14028bdcb`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x14028bd3a`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x14028bdcb`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x14028bef4`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x14028bf5f`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x14028bfc2`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x14028bce2`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x14028bce2`
- `win32kbase!?vStamp@REGION@@AEAAXXZ` at `0x14028be37`
- `win32kbase!?vStamp@REGION@@AEAAXXZ` at `0x14028be37`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x14028bc72`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x14028bc72`
- `win32kbase!?bSwap@RGNOBJAPI@@QEAAHPEAVRGNOBJ@@@Z` at `0x14028bd88`
- `win32kbase!?bSwap@RGNOBJAPI@@QEAAHPEAVRGNOBJ@@@Z` at `0x14028be28`
- `win32kbase!?bSwap@RGNOBJAPI@@QEAAHPEAVRGNOBJ@@@Z` at `0x14028bd88`
- `win32kbase!?bSwap@RGNOBJAPI@@QEAAHPEAVRGNOBJ@@@Z` at `0x14028be28`
- `win32kbase!?bDeleteRGNOBJAPI@RGNOBJAPI@@QEAAHXZ` at `0x14028be5f`
- `win32kbase!?bDeleteRGNOBJAPI@RGNOBJAPI@@QEAAHXZ` at `0x14028be5f`
- `win32kbase!?iCombine@RGNOBJAPI@@QEAAJAEAVRGNOBJ@@0J@Z` at `0x14028bd55`
- `win32kbase!?iCombine@RGNOBJAPI@@QEAAJAEAVRGNOBJ@@0J@Z` at `0x14028bd55`
- `win32kbase!?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z` at `0x14028bd70`
- `win32kbase!?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z` at `0x14028bd70`
- `win32kbase!GreCreateRectRgnIndirect` at `0x14028bc3c`
- `win32kbase!GreCreateRectRgnIndirect` at `0x14028bc3c`
- `win32kbase!GreSetRegionOwner` at `0x14028bc59`
- `win32kbase!GreSetRegionOwner` at `0x14028bc59`
- `WIN32K!W32GetSessionState` at `0x14028bba1`
- `WIN32K!W32GetSessionState` at `0x14028bba1`

## pseudocode

```c
void __fastcall vForceClientRgnUpdate(Gre::Base *a1)
{
  struct Gre::Base::SESSION_GLOBALS *v1; // rax
  __int64 v2; // rcx
  __int64 i; // rsi
  int v4; // eax
  __int64 j; // rdi
  int v6; // r8d
  unsigned int v7; // r8d
  __int64 v8; // rcx
  __int64 ClientRgn; // rax
  HRGN v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rcx
  LONG v13; // edx
  BOOL v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // rbx
  __int64 GlobalLockName; // rax
  struct _GRETHREAD *v18; // rax
  bool v19; // zf
  __int64 v20; // rbx
  __int64 v21; // rax
  struct _GRETHREAD *v22; // rax
  __int64 v23; // rbx
  __int64 v24; // rax
  struct _GRETHREAD *v25; // rax
  __int64 v26; // [rsp+20h] [rbp-59h] BYREF
  __int64 v27; // [rsp+28h] [rbp-51h] BYREF
  __int64 v28; // [rsp+30h] [rbp-49h] BYREF
  __int64 v29; // [rsp+38h] [rbp-41h] BYREF
  struct _POINTL v30[2]; // [rsp+40h] [rbp-39h] BYREF
  _QWORD v31[8]; // [rsp+50h] [rbp-29h] BYREF
  __int128 v32; // [rsp+90h] [rbp+17h] BYREF

  v1 = Gre::Base::Globals(a1);
  SEMOBJ<33>::SEMOBJ<33>(&v28, v1);
  for ( i = *(_QWORD *)(*(_QWORD *)(W32GetSessionState(v2) + 96) + 4816LL); i; i = *(_QWORD *)(i + 8) )
  {
    v4 = *(_DWORD *)(i + 48);
    if ( (v4 & 0x40000000) != 0 )
    {
      *(_DWORD *)(i + 48) = v4 & 0x3FFFFFFF | 0x80000000;
      for ( j = *(_QWORD *)(i + 24); j; j = *(_QWORD *)(j + 160) )
      {
        v6 = *(_DWORD *)(j + 184);
        if ( (v6 & 0x40000000) != 0 )
        {
          v7 = v6 & 0x3FFFFFFF | 0x80000000;
          *(_DWORD *)(j + 184) = v7;
          v8 = *(_QWORD *)(j + 176);
          if ( v8 )
          {
            ClientRgn = UserGetClientRgn(v8, &v32, v7 & 0x20);
          }
          else
          {
            v32 = *(_OWORD *)(i + 52);
            ClientRgn = GreCreateRectRgnIndirect(&v32);
          }
          v10 = (HRGN)ClientRgn;
          if ( !ClientRgn )
            goto LABEL_47;
          GreSetRegionOwner(ClientRgn, 0);
          RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)v31, v10, 0, 0);
          if ( v31[0] )
          {
            if ( (*(_DWORD *)(j + 184) & 0x100) == 0 )
            {
              v11 = *(_QWORD *)(*(_QWORD *)(j + 168) + 32LL);
              v12 = *(_QWORD *)(v11 + 48);
              if ( v12 )
              {
                if ( v11 == *(_QWORD *)(v12 + 2544) )
                {
                  v13 = -*(_DWORD *)(v12 + 2580);
                  v30[0].x = -*(_DWORD *)(v12 + 2576);
                  v30[0].y = v13;
                  if ( v30[0].x || v13 )
                  {
                    RGNOBJ::bOffset((RGNOBJ *)v31, v30);
                    ERECTL::bOffsetAdd((ERECTL *)&v32, v30, 0);
                  }
                }
              }
              RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v27);
              RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v26);
              if ( v27 )
              {
                if ( v26 )
                {
                  RGNOBJ::vSet((RGNOBJ *)&v26, (const struct _RECTL *const)(i + 52));
                  RGNOBJ::bCopy((RGNOBJ *)&v27, (struct RGNOBJ *)v31);
                  RGNOBJAPI::iCombine((RGNOBJAPI *)v31, (struct RGNOBJ *)&v27, (struct RGNOBJ *)&v26, 1);
                  if ( RGNOBJ::iCombine((RGNOBJ *)&v27, (struct RGNOBJ *)v31, (struct RGNOBJ *)&v26, 1) )
                    RGNOBJAPI::bSwap((RGNOBJAPI *)v31, (struct RGNOBJ *)&v27);
                }
              }
              RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v26);
              RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v27);
            }
            RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v29);
            v14 = 0;
            if ( (*(_DWORD *)(j + 184) & 0x200) != 0 && v29 )
              v14 = RGNOBJ::bCopy((RGNOBJ *)&v29, (struct RGNOBJ *)v31) != 0;
            SEMOBJ<34>::SEMOBJ<34>(&v26, j);
            if ( v14 )
            {
              v30[0] = *(struct _POINTL *)(j + 192);
              if ( v30[0] )
              {
                RGNOBJ::vSwap((RGNOBJ *)&v29, (struct RGNOBJ *)v30);
                *(struct _POINTL *)(j + 192) = v30[0];
              }
            }
            RGNOBJAPI::bSwap((RGNOBJAPI *)v31, (struct RGNOBJ *)(j + 56));
            REGION::vStamp(*(REGION **)(j + 56));
            v15 = *(_QWORD *)(j + 56);
            *(_OWORD *)&v30[0].x = v32;
            EWNDOBJ::vSetClip(j, v15, v30);
            RGNOBJAPI::bDeleteRGNOBJAPI((RGNOBJAPI *)v31);
            if ( (*(_DWORD *)(i + 48) & 1) != 0 )
              TRACKOBJ::vUpdateDrvDelta((TRACKOBJ *)i, (struct EWNDOBJ *)j, 1u);
            if ( (*(_DWORD *)(i + 48) & 2) != 0 )
              TRACKOBJ::vUpdateDrv((TRACKOBJ *)i, (struct EWNDOBJ *)j, 2u);
            vSpWndobjChange(*(HDEV *)(*(_QWORD *)(i + 32) + 48LL), (struct EWNDOBJ *)j);
            v16 = v26;
            if ( v26 )
            {
              GlobalLockName = GrepGetGlobalLockName(34);
              EtwTraceGreLockReleaseSemaphore(GlobalLockName, v16);
              v18 = GreGetCurrentThreadCrossSessionCheck();
              if ( v18 )
              {
                v19 = (*(_QWORD *)v18 & 0xFFFFFFFBFFFFFFFFuLL) == 0;
                *(_QWORD *)v18 &= ~0x400000000uLL;
                if ( v19 )
                  GrepOnAllLocksReleased();
              }
              ((void (__fastcall *)(__int64))GreReleaseSemaphoreExclusiveInternal)(v16);
            }
            RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v29);
          }
          RGNOBJAPI::~RGNOBJAPI((RGNOBJAPI *)v31);
          v20 = v28;
          if ( v28 )
          {
            v21 = GrepGetGlobalLockName(33);
            EtwTraceGreLockReleaseSemaphore(v21, v20);
            v22 = GreGetCurrentThreadCrossSessionCheck();
            if ( v22 )
            {
              v19 = (*(_QWORD *)v22 & 0xFFFFFFFDFFFFFFFFuLL) == 0;
              *(_QWORD *)v22 &= ~0x200000000uLL;
              if ( v19 )
                GrepOnAllLocksReleased();
            }
            ((void (__fastcall *)(__int64))GreReleaseSemaphoreExclusiveInternal)(v20);
          }
          GreClientRgnUpdated(1);
          return;
        }
      }
      break;
    }
  }
LABEL_47:
  v23 = v28;
  if ( v28 )
  {
    v24 = GrepGetGlobalLockName(33);
    EtwTraceGreLockReleaseSemaphore(v24, v23);
    v25 = GreGetCurrentThreadCrossSessionCheck();
    if ( v25 )
    {
      v19 = (*(_QWORD *)v25 & 0xFFFFFFFDFFFFFFFFuLL) == 0;
      *(_QWORD *)v25 &= ~0x200000000uLL;
      if ( v19 )
        GrepOnAllLocksReleased();
    }
    ((void (__fastcall *)(__int64))GreReleaseSemaphoreExclusiveInternal)(v23);
  }
}

```

## disassembly

```asm
0x14028bb68  push    rbp
0x14028bb6a  push    rbx
0x14028bb6b  push    rsi
0x14028bb6c  push    rdi
0x14028bb6d  push    r15
0x14028bb6f  lea     rbp, [rsp-37h]
0x14028bb74  sub     rsp, 0B0h
0x14028bb7b  mov     rax, cs:__security_cookie
0x14028bb82  xor     rax, rsp
0x14028bb85  mov     [rbp+57h+var_30], rax
0x14028bb89  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14028bb90  nop     dword ptr [rax+rax+00h]
0x14028bb95  mov     rdx, rax
0x14028bb98  lea     rcx, [rbp+57h+var_A0]
0x14028bb9c  call    ??0?$SEMOBJ@$0CB@@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@@Z; SEMOBJ<33>::SEMOBJ<33>(Gre::Base::SESSION_GLOBALS &)
0x14028bba1  call    cs:__imp_W32GetSessionState
0x14028bba8  nop     dword ptr [rax+rax+00h]
0x14028bbad  mov     rcx, [rax+60h]
0x14028bbb1  mov     rsi, [rcx+12D0h]
0x14028bbb8  test    rsi, rsi
0x14028bbbb  jz      loc_14028BF78
0x14028bbc1  mov     eax, [rsi+30h]
0x14028bbc4  bt      eax, 1Eh
0x14028bbc8  jb      short loc_14028BBD0
0x14028bbca  mov     rsi, [rsi+8]
0x14028bbce  jmp     short loc_14028BBB8
0x14028bbd0  mov     edx, 3FFFFFFFh
0x14028bbd5  mov     r9d, 80000000h
0x14028bbdb  and     eax, edx
0x14028bbdd  or      eax, r9d
0x14028bbe0  mov     [rsi+30h], eax
0x14028bbe3  mov     rdi, [rsi+18h]
0x14028bbe7  test    rdi, rdi
0x14028bbea  jz      loc_14028BF78
0x14028bbf0  mov     r8d, [rdi+0B8h]
0x14028bbf7  bt      r8d, 1Eh
0x14028bbfc  jb      short loc_14028BC07
0x14028bbfe  mov     rdi, [rdi+0A0h]
0x14028bc05  jmp     short loc_14028BBE7
0x14028bc07  and     r8d, edx
0x14028bc0a  or      r8d, r9d
0x14028bc0d  mov     [rdi+0B8h], r8d
0x14028bc14  mov     rcx, [rdi+0B0h]
0x14028bc1b  test    rcx, rcx
0x14028bc1e  jz      short loc_14028BC2F
0x14028bc20  and     r8d, 20h
0x14028bc24  lea     rdx, [rbp+57h+var_40]
0x14028bc28  call    UserGetClientRgn
0x14028bc2d  jmp     short loc_14028BC48
0x14028bc2f  movups  xmm0, xmmword ptr [rsi+34h]
0x14028bc33  lea     rcx, [rbp+57h+var_40]
0x14028bc37  movdqu  [rbp+57h+var_40], xmm0
0x14028bc3c  call    cs:__imp_GreCreateRectRgnIndirect
0x14028bc43  nop     dword ptr [rax+rax+00h]
0x14028bc48  mov     rbx, rax
0x14028bc4b  test    rax, rax
0x14028bc4e  jz      loc_14028BF78
0x14028bc54  xor     edx, edx
0x14028bc56  mov     rcx, rax
0x14028bc59  call    cs:__imp_GreSetRegionOwner
0x14028bc60  nop     dword ptr [rax+rax+00h]
0x14028bc65  xor     r9d, r9d
0x14028bc68  lea     rcx, [rbp+57h+var_80]
0x14028bc6c  xor     r8d, r8d
0x14028bc6f  mov     rdx, rbx
0x14028bc72  call    cs:__imp_??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x14028bc79  nop     dword ptr [rax+rax+00h]
0x14028bc7e  cmp     [rbp+57h+var_80], 0
0x14028bc83  mov     r15d, 1
0x14028bc89  jz      loc_14028BF0C
0x14028bc8f  test    dword ptr [rdi+0B8h], 100h
0x14028bc99  jnz     loc_14028BDA6
0x14028bc9f  mov     rax, [rdi+0A8h]
0x14028bca6  mov     rdx, [rax+20h]
0x14028bcaa  mov     rcx, [rdx+30h]
0x14028bcae  test    rcx, rcx
0x14028bcb1  jz      short loc_14028BCFE
0x14028bcb3  cmp     rdx, [rcx+9F0h]
0x14028bcba  jnz     short loc_14028BCFE
0x14028bcbc  mov     eax, [rcx+0A10h]
0x14028bcc2  mov     edx, [rcx+0A14h]
0x14028bcc8  neg     eax
0x14028bcca  neg     edx
0x14028bccc  mov     [rbp+57h+var_90.x], eax
0x14028bccf  mov     [rbp+57h+var_90.y], edx
0x14028bcd2  test    eax, eax
0x14028bcd4  jnz     short loc_14028BCDA
0x14028bcd6  test    edx, edx
0x14028bcd8  jz      short loc_14028BCFE
0x14028bcda  lea     rdx, [rbp+57h+var_90]
0x14028bcde  lea     rcx, [rbp+57h+var_80]
0x14028bce2  call    cs:__imp_?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z; RGNOBJ::bOffset(_POINTL const *)
0x14028bce9  nop     dword ptr [rax+rax+00h]
0x14028bcee  xor     r8d, r8d; int
0x14028bcf1  lea     rdx, [rbp+57h+var_90]; struct _POINTL *
0x14028bcf5  lea     rcx, [rbp+57h+var_40]; this
0x14028bcf9  call    ?bOffsetAdd@ERECTL@@QEAAHAEBU_POINTL@@H@Z; ERECTL::bOffsetAdd(_POINTL const &,int)
0x14028bcfe  lea     rcx, [rbp+57h+var_A8]; this
0x14028bd02  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x14028bd07  lea     rcx, [rbp+57h+var_B0]; this
0x14028bd0b  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x14028bd10  cmp     [rbp+57h+var_A8], 0
0x14028bd15  jz      short loc_14028BD94
0x14028bd17  cmp     [rbp+57h+var_B0], 0
0x14028bd1c  jz      short loc_14028BD94
0x14028bd1e  lea     rdx, [rsi+34h]
0x14028bd22  lea     rcx, [rbp+57h+var_B0]
0x14028bd26  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x14028bd2d  nop     dword ptr [rax+rax+00h]
0x14028bd32  lea     rdx, [rbp+57h+var_80]
0x14028bd36  lea     rcx, [rbp+57h+var_A8]
0x14028bd3a  call    cs:__imp_?bCopy@RGNOBJ@@QEAAHAEAV1@@Z; RGNOBJ::bCopy(RGNOBJ &)
0x14028bd41  nop     dword ptr [rax+rax+00h]
0x14028bd46  mov     r9d, r15d
0x14028bd49  lea     r8, [rbp+57h+var_B0]
0x14028bd4d  lea     rdx, [rbp+57h+var_A8]
0x14028bd51  lea     rcx, [rbp+57h+var_80]
0x14028bd55  call    cs:__imp_?iCombine@RGNOBJAPI@@QEAAJAEAVRGNOBJ@@0J@Z; RGNOBJAPI::iCombine(RGNOBJ &,RGNOBJ &,long)
0x14028bd5c  nop     dword ptr [rax+rax+00h]
0x14028bd61  mov     r9d, r15d
0x14028bd64  lea     r8, [rbp+57h+var_B0]
0x14028bd68  lea     rdx, [rbp+57h+var_80]
0x14028bd6c  lea     rcx, [rbp+57h+var_A8]
0x14028bd70  call    cs:__imp_?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z; RGNOBJ::iCombine(RGNOBJ &,RGNOBJ &,long)
0x14028bd77  nop     dword ptr [rax+rax+00h]
0x14028bd7c  test    eax, eax
0x14028bd7e  jz      short loc_14028BD94
0x14028bd80  lea     rdx, [rbp+57h+var_A8]
0x14028bd84  lea     rcx, [rbp+57h+var_80]
0x14028bd88  call    cs:__imp_?bSwap@RGNOBJAPI@@QEAAHPEAVRGNOBJ@@@Z; RGNOBJAPI::bSwap(RGNOBJ *)
0x14028bd8f  nop     dword ptr [rax+rax+00h]
0x14028bd94  lea     rcx, [rbp+57h+var_B0]; this
0x14028bd98  call    ??1RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::~RGNMEMOBJTMP(void)
0x14028bd9d  lea     rcx, [rbp+57h+var_A8]; this
0x14028bda1  call    ??1RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::~RGNMEMOBJTMP(void)
0x14028bda6  lea     rcx, [rbp+57h+var_98]; this
0x14028bdaa  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x14028bdaf  xor     ebx, ebx
0x14028bdb1  test    dword ptr [rdi+0B8h], 200h
0x14028bdbb  jz      short loc_14028BDDD
0x14028bdbd  cmp     [rbp+57h+var_98], rbx
0x14028bdc1  jz      short loc_14028BDDD
0x14028bdc3  lea     rdx, [rbp+57h+var_80]
0x14028bdc7  lea     rcx, [rbp+57h+var_98]
0x14028bdcb  call    cs:__imp_?bCopy@RGNOBJ@@QEAAHAEAV1@@Z; RGNOBJ::bCopy(RGNOBJ &)
0x14028bdd2  nop     dword ptr [rax+rax+00h]
0x14028bdd7  test    eax, eax
0x14028bdd9  cmovnz  ebx, r15d
0x14028bddd  mov     rdx, rdi
0x14028bde0  lea     rcx, [rbp+57h+var_B0]
0x14028bde4  call    ??0?$SEMOBJ@$0CC@@@QEAA@PEAVEWNDOBJ@@@Z; SEMOBJ<34>::SEMOBJ<34>(EWNDOBJ *)
0x14028bde9  cmp     ebx, r15d
0x14028bdec  jnz     short loc_14028BE1D
0x14028bdee  mov     rax, [rdi+0C0h]
0x14028bdf5  mov     qword ptr [rbp+57h+var_90.x], rax
0x14028bdf9  test    rax, rax
0x14028bdfc  jz      short loc_14028BE1D
0x14028bdfe  lea     rdx, [rbp+57h+var_90]
0x14028be02  lea     rcx, [rbp+57h+var_98]
0x14028be06  call    cs:__imp_?vSwap@RGNOBJ@@QEAAXPEAV1@@Z; RGNOBJ::vSwap(RGNOBJ *)
0x14028be0d  nop     dword ptr [rax+rax+00h]
0x14028be12  mov     rax, qword ptr [rbp+57h+var_90.x]
0x14028be16  mov     [rdi+0C0h], rax
0x14028be1d  lea     rbx, [rdi+38h]
0x14028be21  mov     rdx, rbx
0x14028be24  lea     rcx, [rbp+57h+var_80]
0x14028be28  call    cs:__imp_?bSwap@RGNOBJAPI@@QEAAHPEAVRGNOBJ@@@Z; RGNOBJAPI::bSwap(RGNOBJ *)
0x14028be2f  nop     dword ptr [rax+rax+00h]
0x14028be34  mov     rcx, [rbx]
0x14028be37  call    cs:__imp_?vStamp@REGION@@AEAAXXZ; REGION::vStamp(void)
0x14028be3e  nop     dword ptr [rax+rax+00h]
0x14028be43  movaps  xmm0, [rbp+57h+var_40]
0x14028be47  lea     r8, [rbp+57h+var_90]
0x14028be4b  mov     rdx, [rbx]
0x14028be4e  mov     rcx, rdi
0x14028be51  movdqa  xmmword ptr [rbp+57h+var_90.x], xmm0
0x14028be56  call    ?vSetClip@EWNDOBJ@@QEAAXPEAVREGION@@VERECTL@@@Z; EWNDOBJ::vSetClip(REGION *,ERECTL)
0x14028be5b  lea     rcx, [rbp+57h+var_80]
0x14028be5f  call    cs:__imp_?bDeleteRGNOBJAPI@RGNOBJAPI@@QEAAHXZ; RGNOBJAPI::bDeleteRGNOBJAPI(void)
0x14028be66  nop     dword ptr [rax+rax+00h]
0x14028be6b  mov     eax, [rsi+30h]
0x14028be6e  test    r15b, al
0x14028be71  jz      short loc_14028BE81
0x14028be73  mov     r8d, r15d; unsigned int
0x14028be76  mov     rdx, rdi; struct EWNDOBJ *
0x14028be79  mov     rcx, rsi; this
0x14028be7c  call    ?vUpdateDrvDelta@TRACKOBJ@@QEAAXPEAVEWNDOBJ@@K@Z; TRACKOBJ::vUpdateDrvDelta(EWNDOBJ *,ulong)
0x14028be81  mov     eax, [rsi+30h]
0x14028be84  mov     r8d, 2; unsigned int
0x14028be8a  test    r8b, al
0x14028be8d  jz      short loc_14028BE9A
0x14028be8f  mov     rdx, rdi; struct EWNDOBJ *
0x14028be92  mov     rcx, rsi; this
0x14028be95  call    ?vUpdateDrv@TRACKOBJ@@QEAAXPEAVEWNDOBJ@@K@Z; TRACKOBJ::vUpdateDrv(EWNDOBJ *,ulong)
0x14028be9a  mov     rcx, [rsi+20h]
0x14028be9e  mov     rdx, rdi; struct EWNDOBJ *
0x14028bea1  mov     rcx, [rcx+30h]; HDEV
0x14028bea5  call    ?vSpWndobjChange@@YAXPEAUHDEV__@@PEAVEWNDOBJ@@@Z; vSpWndobjChange(HDEV__ *,EWNDOBJ *)
0x14028beaa  mov     rbx, [rbp+57h+var_B0]
0x14028beae  test    rbx, rbx
0x14028beb1  jz      short loc_14028BF03
0x14028beb3  mov     ecx, 22h ; '"'
0x14028beb8  call    ?GrepGetGlobalLockName@@YAPEBGW4GreLockClass@@@Z; GrepGetGlobalLockName(GreLockClass)
0x14028bebd  mov     rcx, rax
0x14028bec0  mov     rdx, rbx
0x14028bec3  call    cs:__imp_EtwTraceGreLockReleaseSemaphore
0x14028beca  nop     dword ptr [rax+rax+00h]
0x14028becf  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x14028bed4  test    rax, rax
0x14028bed7  jz      short loc_14028BEF4
0x14028bed9  mov     rcx, 0FFFFFFFBFFFFFFFFh
0x14028bee3  and     [rax], rcx
0x14028bee6  jnz     short loc_14028BEF4
0x14028bee8  call    cs:__imp_?GrepOnAllLocksReleased@@YAXXZ; GrepOnAllLocksReleased(void)
0x14028beef  nop     dword ptr [rax+rax+00h]
0x14028bef4  mov     rax, cs:__imp_?GreReleaseSemaphoreExclusiveInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreExclusiveInternal(HSEMAPHORE__ *)
0x14028befb  mov     rcx, rbx
0x14028befe  call    _guard_dispatch_icall
0x14028bf03  lea     rcx, [rbp+57h+var_98]; this
0x14028bf07  call    ??1RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::~RGNMEMOBJTMP(void)
0x14028bf0c  lea     rcx, [rbp+57h+var_80]; this
0x14028bf10  call    ??1RGNOBJAPI@@QEAA@XZ; RGNOBJAPI::~RGNOBJAPI(void)
0x14028bf15  mov     rbx, [rbp+57h+var_A0]
0x14028bf19  test    rbx, rbx
0x14028bf1c  jz      short loc_14028BF6E
0x14028bf1e  mov     ecx, 21h ; '!'
0x14028bf23  call    ?GrepGetGlobalLockName@@YAPEBGW4GreLockClass@@@Z; GrepGetGlobalLockName(GreLockClass)
0x14028bf28  mov     rcx, rax
0x14028bf2b  mov     rdx, rbx
0x14028bf2e  call    cs:__imp_EtwTraceGreLockReleaseSemaphore
0x14028bf35  nop     dword ptr [rax+rax+00h]
0x14028bf3a  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x14028bf3f  test    rax, rax
0x14028bf42  jz      short loc_14028BF5F
0x14028bf44  mov     rdx, 0FFFFFFFDFFFFFFFFh
0x14028bf4e  and     [rax], rdx
0x14028bf51  jnz     short loc_14028BF5F
0x14028bf53  call    cs:__imp_?GrepOnAllLocksReleased@@YAXXZ; GrepOnAllLocksReleased(void)
0x14028bf5a  nop     dword ptr [rax+rax+00h]
0x14028bf5f  mov     rax, cs:__imp_?GreReleaseSemaphoreExclusiveInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreExclusiveInternal(HSEMAPHORE__ *)
0x14028bf66  mov     rcx, rbx
0x14028bf69  call    _guard_dispatch_icall
0x14028bf6e  mov     ecx, r15d
0x14028bf71  call    GreClientRgnUpdated
0x14028bf76  jmp     short loc_14028BFD1
0x14028bf78  mov     rbx, [rbp+57h+var_A0]
0x14028bf7c  test    rbx, rbx
0x14028bf7f  jz      short loc_14028BFD1
0x14028bf81  mov     ecx, 21h ; '!'
0x14028bf86  call    ?GrepGetGlobalLockName@@YAPEBGW4GreLockClass@@@Z; GrepGetGlobalLockName(GreLockClass)
0x14028bf8b  mov     rcx, rax
0x14028bf8e  mov     rdx, rbx
0x14028bf91  call    cs:__imp_EtwTraceGreLockReleaseSemaphore
0x14028bf98  nop     dword ptr [rax+rax+00h]
0x14028bf9d  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x14028bfa2  test    rax, rax
0x14028bfa5  jz      short loc_14028BFC2
0x14028bfa7  mov     rdx, 0FFFFFFFDFFFFFFFFh
0x14028bfb1  and     [rax], rdx
0x14028bfb4  jnz     short loc_14028BFC2
0x14028bfb6  call    cs:__imp_?GrepOnAllLocksReleased@@YAXXZ; GrepOnAllLocksReleased(void)
0x14028bfbd  nop     dword ptr [rax+rax+00h]
0x14028bfc2  mov     rax, cs:__imp_?GreReleaseSemaphoreExclusiveInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreExclusiveInternal(HSEMAPHORE__ *)
0x14028bfc9  mov     rcx, rbx
0x14028bfcc  call    _guard_dispatch_icall
0x14028bfd1  mov     rcx, [rbp+57h+var_30]
0x14028bfd5  xor     rcx, rsp; StackCookie
0x14028bfd8  call    __security_check_cookie
0x14028bfdd  add     rsp, 0B0h
0x14028bfe4  pop     r15
0x14028bfe6  pop     rdi
0x14028bfe7  pop     rsi
0x14028bfe8  pop     rbx
0x14028bfe9  pop     rbp
0x14028bfea  retn
```
