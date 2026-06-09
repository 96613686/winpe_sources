# xxxSnapWindow

- ea: `0x14028f2ac`
- end: `0x14028f7c4`
- name: `xxxSnapWindow`
- size: `1304`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x1401ca020`

## callees

- `0x140012790`
- `0x1400240e0`
- `0x1400241fc`
- `0x140027cfc`
- `0x140033e08`
- `0x140035d14`
- `0x140060630`
- `0x140094860`
- `0x1400a9a54`
- `0x1400e2cb0`
- `0x1400e8f88`
- `0x14013e750`
- `0x14013eafc`
- `0x14013eb50`
- `0x14018c8d0`
- `0x1401ba5f4`
- `0x1401bab8c`
- `0x1401bbc30`
- `0x140214aac`
- `0x14021ebdc`
- `0x14027ed18`
- `0x14027ee88`
- `0x14028f2ac`
- `0x1402a71e8`
- `0x1402d78b8`
- `0x1402ea5ac`
- `0x1403394e0`

## import_xrefs

- `win32kbase!GreCreateCompatibleDC` at `0x14028f4d1`
- `win32kbase!GreCreateCompatibleDC` at `0x14028f4d1`
- `win32kbase!_GetDCEx` at `0x14028f4b6`
- `win32kbase!_GetDCEx` at `0x14028f4b6`
- `win32kbase!_ReleaseDC` at `0x14028f753`
- `win32kbase!_ReleaseDC` at `0x14028f753`
- `win32kbase!GreDeleteDC` at `0x14028f77f`
- `win32kbase!GreDeleteDC` at `0x14028f77f`
- `win32kbase!UserIsCurrentProcessImmersiveAppContainer` at `0x14028f5c6`
- `win32kbase!UserIsCurrentProcessImmersiveAppContainer` at `0x14028f5c6`
- `win32kbase!GreSelectBitmap` at `0x14028f59b`
- `win32kbase!GreSelectBitmap` at `0x14028f6a3`
- `win32kbase!GreSelectBitmap` at `0x14028f59b`
- `win32kbase!GreSelectBitmap` at `0x14028f6a3`
- `win32kbase!IsWindowDesktopComposed` at `0x14028f5ea`
- `win32kbase!IsWindowDesktopComposed` at `0x14028f5ea`
- `win32kbase!GreDeleteObject` at `0x14028f6bf`
- `win32kbase!GreDeleteObject` at `0x14028f6bf`
- `win32kbase!Win32FreePool` at `0x14028f733`
- `win32kbase!Win32FreePool` at `0x14028f733`
- `win32kbase!HMAssignmentUnlock` at `0x14028f76b`
- `win32kbase!HMAssignmentUnlock` at `0x14028f76b`
- `win32kbase!ReferenceDwmApiPort` at `0x14028f3bb`
- `win32kbase!ReferenceDwmApiPort` at `0x14028f3bb`
- `win32kbase!GreCreateBitmap` at `0x14028f555`
- `win32kbase!GreCreateBitmap` at `0x14028f57d`
- `win32kbase!GreCreateBitmap` at `0x14028f555`
- `win32kbase!GreCreateBitmap` at `0x14028f57d`
- `WIN32K!W32GetUserSessionState` at `0x14028f300`
- `WIN32K!W32GetUserSessionState` at `0x14028f313`
- `WIN32K!W32GetUserSessionState` at `0x14028f4e9`
- `WIN32K!W32GetUserSessionState` at `0x14028f529`
- `WIN32K!W32GetUserSessionState` at `0x14028f6e2`
- `WIN32K!W32GetUserSessionState` at `0x14028f300`
- `WIN32K!W32GetUserSessionState` at `0x14028f313`
- `WIN32K!W32GetUserSessionState` at `0x14028f4e9`
- `WIN32K!W32GetUserSessionState` at `0x14028f529`
- `WIN32K!W32GetUserSessionState` at `0x14028f6e2`

## pseudocode

```c
__int64 __fastcall xxxSnapWindow(__int64 a1, __int64 a2)
{
  _QWORD *v2; // rdi
  struct tagTHREADINFO *v3; // rsi
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  struct tagWINDOWSTATION *v16; // r13
  __int64 v17; // rdx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  void *v22; // rax
  __int64 v23; // rdx
  unsigned int v24; // ebx
  __int64 v25; // rbx
  __int64 v26; // rdx
  Gre::Base *CompatibleDC; // rsi
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rdx
  unsigned int v32; // ebx
  unsigned int v33; // r12d
  unsigned __int64 v34; // kr00_8
  int v35; // edx
  __int64 v36; // rcx
  int v37; // r8d
  __int64 DCEx; // rax
  Gre::Base *v39; // r15
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // r8
  __int64 v47; // r9
  HBITMAP Bitmap; // rax
  __int64 UserSessionState; // rax
  char *v50; // r14
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  __int64 v54; // rdx
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // r8
  __int64 v58; // r9
  __int64 v59; // rdx
  ULONG_PTR BugCheckParameter3[2]; // [rsp+68h] [rbp-21h] BYREF
  ULONG_PTR v61[2]; // [rsp+78h] [rbp-11h] BYREF
  __int128 v62; // [rsp+88h] [rbp-1h] BYREF
  ULONG_PTR BugCheckParameter2[2]; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v64; // [rsp+A8h] [rbp+1Fh]
  int v65; // [rsp+F8h] [rbp+6Fh]
  ULONG_PTR v66; // [rsp+100h] [rbp+77h] BYREF
  struct tagTHREADINFO *v67; // [rsp+108h] [rbp+7Fh] BYREF

  v65 = a2;
  v66 = 0;
  v64 = -1;
  *(_OWORD *)BugCheckParameter2 = 0;
  v61[1] = 0;
  v2 = (_QWORD *)a1;
  v61[0] = -1;
  v3 = PtiCurrent(a1, a2);
  v67 = v3;
  v8 = *(_QWORD *)(W32GetUserSessionState(v5, v4, v6, v7) + 19216);
  if ( v8 == *(_QWORD *)(W32GetUserSessionState(v10, v9, v11, v12) + 62744)
    || ReferenceWindowStation(KeGetCurrentThread(), 0, 0x200u, &v66, 1) < 0
    || (v16 = (struct tagWINDOWSTATION *)v66, (*(_DWORD *)(v66 + 32) & 4) != 0)
    || *(_QWORD *)(v2[3] + 40LL) != v66 )
  {
LABEL_5:
    Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>(v61, v13);
    if ( v64 != -1 )
      PopAndFreeW32ThreadLock((__int64)BugCheckParameter2, v17);
    return 0;
  }
  while ( (*(_BYTE *)(v2[5] + 31LL) & 0x40) != 0 )
    v2 = (_QWORD *)v2[13];
  if ( !IsToplevelWindowDesktopComposed((__int64)v2, v13, v14, v15) )
  {
    Win32HMThreadLockBase<tagMENU,1,1>::ManualLock<void>((__int64 *)v61, (__int64)v2);
    Win32RawLockedNtObject<tagWINDOWSTATION>::ManualLock(BugCheckParameter2, (ULONG_PTR)v16);
    v25 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v3 + 61) + 8LL) + 24LL);
    Win32HM_LockIntoThread<1>((__int64)v3, v25, (__int64 *)BugCheckParameter3);
    LODWORD(v25) = OpenClipboard(v25, 0);
    Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((__int64 *)BugCheckParameter3, v26);
    if ( !(_DWORD)v25 )
      goto LABEL_5;
    CompatibleDC = 0;
    xxxEmptyClipboard((__int64)v16, v13);
    *(_OWORD *)BugCheckParameter3 = *(_OWORD *)(v2[5] + 88LL);
    v62 = *GetPhysicalScreenRect(&v62, v28, v29, v30);
    if ( !(unsigned int)IntersectRect(BugCheckParameter3, (int *)BugCheckParameter3, (int *)&v62) )
    {
      v24 = 0;
LABEL_43:
      xxxCloseClipboard(v16, v31);
      HMAssignmentUnlock((char *)v16 + 80);
      if ( CompatibleDC )
        GreDeleteDC(CompatibleDC);
      Win32RawLockedItemBase<tagWINDOWSTATION,&void UserDereferenceObject(void *),1,1,1>::UnlockWorker(
        (ULONG_PTR)BugCheckParameter2,
        0);
      goto LABEL_46;
    }
    v32 = LODWORD(BugCheckParameter3[1]) - LODWORD(BugCheckParameter3[0]);
    v33 = HIDWORD(BugCheckParameter3[1]) - HIDWORD(BugCheckParameter3[0]);
    v34 = BugCheckParameter3[0];
    if ( v2 != (_QWORD *)GetDesktopWindow((__int64)v2) )
      v34 = __PAIR64__(v37 - *(_DWORD *)(v2[5] + 92LL), v35 - *(_DWORD *)(v2[5] + 88LL));
    DCEx = _GetDCEx(v36, 0, 65537);
    v39 = (Gre::Base *)DCEx;
    if ( DCEx
      && (CompatibleDC = (Gre::Base *)GreCreateCompatibleDC(DCEx)) != 0
      && ((v45 = *(_QWORD *)(W32GetUserSessionState(v41, v40, v42, v43) + 19704), !*(_DWORD *)(v45 + 2220))
        ? (UserSessionState = W32GetUserSessionState(v45, v44, v46, v47),
           Bitmap = (HBITMAP)GreCreateBitmap(
                               v32,
                               v33,
                               1,
                               *(unsigned __int16 *)(*(_QWORD *)(UserSessionState + 56744) + 128LL),
                               0))
        : (Bitmap = GreCreateCompatibleBitmapEx(v39, v32, v33, 0, 0, 0)),
          (v50 = (char *)Bitmap) != 0 || (v50 = (char *)GreCreateBitmap(v32, v33, 1, 1, 0)) != 0) )
    {
      BugCheckParameter3[0] = GreSelectBitmap(CompatibleDC, v50);
      if ( !v65
        && (v51 = *(_QWORD *)(*((_QWORD *)v67 + 61) + 8LL), v2 == *(_QWORD **)(v51 + 24))
        && (unsigned int)UserIsCurrentProcessImmersiveAppContainer() )
      {
        LOBYTE(v66) = 1;
        GreEnableAppContainerRestriction(0, v51);
      }
      else
      {
        LOBYTE(v66) = 0;
      }
      if ( (unsigned int)IsWindowDesktopComposed(v2, v51, v52, v53) )
      {
        LeaveEnterCrit::LeaveEnterCrit((LeaveEnterCrit *)&v67);
        v24 = GreBitBltInternal(CompatibleDC, 0, 0, v32, v33, (__int64)v39, v34, SHIDWORD(v34), 0x40CC0020u, 0, 4u);
        LeaveEnterCrit::~LeaveEnterCrit((LeaveEnterCrit *)&v67);
      }
      else
      {
        v24 = GreBitBltInternal(CompatibleDC, 0, 0, v32, v33, (__int64)v39, v34, SHIDWORD(v34), 0x40CC0020u, 0, 0);
      }
      if ( (_BYTE)v66 )
        GreEnableAppContainerRestriction(1, v54);
      GreSelectBitmap(CompatibleDC, BugCheckParameter3[0]);
      if ( v24 )
      {
        SetClipboardData(2u, v50, 0, 1);
        if ( (*(_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v56, v55, v57, v58) + 19704) + 7004LL) & 1) != 0 )
        {
          v67 = 0;
          v66 = 0;
          if ( (int)CreateScreenPalette((HDC)v39) >= 0 )
          {
            SetClipboardData(9u, (char *)v66, 0, 1);
            Win32FreePool(v67);
          }
        }
        v24 = 1;
      }
      else if ( v50 )
      {
        GreDeleteObject(v50);
      }
    }
    else
    {
      ClientNoMemoryPopup();
      v24 = 0;
      if ( !v39 )
        goto LABEL_43;
    }
    _ReleaseDC(v39);
    goto LABEL_43;
  }
  v22 = (void *)ReferenceDwmApiPort(v20, v19, v21);
  v24 = (int)DwmAsyncSnapshotWindow(v22) >= 0;
LABEL_46:
  if ( v24 )
    xxxPlayEventSound(13, v23);
  Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>(v61, v23);
  if ( v64 != -1 )
    PopAndFreeW32ThreadLock((__int64)BugCheckParameter2, v59);
  return v24;
}

```

## disassembly

```asm
0x14028f2ac  mov     [rsp-8+arg_0], rbx
0x14028f2b1  mov     [rsp-8+arg_8], edx
0x14028f2b5  push    rbp
0x14028f2b6  push    rsi
0x14028f2b7  push    rdi
0x14028f2b8  push    r12
0x14028f2ba  push    r13
0x14028f2bc  push    r14
0x14028f2be  push    r15
0x14028f2c0  lea     rbp, [rsp-27h]
0x14028f2c5  sub     rsp, 0B0h
0x14028f2cc  xorps   xmm0, xmm0
0x14028f2cf  mov     [rbp+57h+arg_10], 0
0x14028f2d7  xor     eax, eax
0x14028f2d9  mov     [rbp+57h+var_38], 0FFFFFFFFFFFFFFFFh
0x14028f2e1  movups  xmmword ptr [rbp+57h+BugCheckParameter2], xmm0
0x14028f2e5  mov     [rbp+57h+var_60], rax
0x14028f2e9  mov     rdi, rcx
0x14028f2ec  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFFh
0x14028f2f4  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14028f2f9  mov     rsi, rax
0x14028f2fc  mov     [rbp+57h+arg_18], rax
0x14028f300  call    cs:__imp_W32GetUserSessionState
0x14028f307  nop     dword ptr [rax+rax+00h]
0x14028f30c  mov     rbx, [rax+4B10h]
0x14028f313  call    cs:__imp_W32GetUserSessionState
0x14028f31a  nop     dword ptr [rax+rax+00h]
0x14028f31f  cmp     rbx, [rax+0F518h]
0x14028f326  jz      short loc_14028F367
0x14028f328  mov     rcx, gs:188h
0x14028f331  lea     r9, [rbp+57h+arg_10]
0x14028f335  mov     r14d, 1
0x14028f33b  xor     edx, edx
0x14028f33d  mov     r8d, 200h
0x14028f343  mov     [rsp+0E0h+var_C0], r14d
0x14028f348  call    ReferenceWindowStation
0x14028f34d  test    eax, eax
0x14028f34f  js      short loc_14028F367
0x14028f351  mov     r13, [rbp+57h+arg_10]
0x14028f355  mov     eax, [r13+20h]
0x14028f359  test    al, 4
0x14028f35b  jnz     short loc_14028F367
0x14028f35d  mov     rax, [rdi+18h]
0x14028f361  cmp     [rax+28h], r13
0x14028f365  jz      short loc_14028F3A2
0x14028f367  lea     rcx, [rbp+57h+var_68]; BugCheckParameter3
0x14028f36b  call    ??1?$Win32HMOptionalThreadLock@UtagHOOK@@@@QEAA@XZ; Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>(void)
0x14028f370  cmp     [rbp+57h+var_38], 0FFFFFFFFFFFFFFFFh
0x14028f375  jz      short loc_14028F380
0x14028f377  lea     rcx, [rbp+57h+BugCheckParameter2]
0x14028f37b  call    PopAndFreeW32ThreadLock
0x14028f380  xor     eax, eax
0x14028f382  mov     rbx, [rsp+0E0h+arg_0]
0x14028f38a  add     rsp, 0B0h
0x14028f391  pop     r15
0x14028f393  pop     r14
0x14028f395  pop     r13
0x14028f397  pop     r12
0x14028f399  pop     rdi
0x14028f39a  pop     rsi
0x14028f39b  pop     rbp
0x14028f39c  retn
0x14028f39e  mov     rdi, [rdi+68h]
0x14028f3a2  mov     rax, [rdi+28h]
0x14028f3a6  test    byte ptr [rax+1Fh], 40h
0x14028f3aa  jnz     short loc_14028F39E
0x14028f3ac  mov     rcx, rdi
0x14028f3af  call    IsToplevelWindowDesktopComposed
0x14028f3b4  test    eax, eax
0x14028f3b6  jz      short loc_14028F3DE
0x14028f3b8  mov     rbx, [rdi]
0x14028f3bb  call    cs:__imp_ReferenceDwmApiPort
0x14028f3c2  nop     dword ptr [rax+rax+00h]
0x14028f3c7  mov     rcx, rax; Object
0x14028f3ca  mov     rdx, rbx
0x14028f3cd  call    DwmAsyncSnapshotWindow
0x14028f3d2  mov     ebx, eax
0x14028f3d4  not     ebx
0x14028f3d6  shr     ebx, 1Fh
0x14028f3d9  jmp     loc_14028F796
0x14028f3de  mov     rdx, rdi
0x14028f3e1  lea     rcx, [rbp+57h+var_68]
0x14028f3e5  call    ??$ManualLock@X@?$Win32HMThreadLockBase@UtagMENU@@$00$00@@QEAAXPEAUtagMENU@@@Z; Win32HMThreadLockBase<tagMENU,1,1>::ManualLock<void>(tagMENU *)
0x14028f3ea  mov     rdx, r13; BugCheckParameter3
0x14028f3ed  lea     rcx, [rbp+57h+BugCheckParameter2]; BugCheckParameter2
0x14028f3f1  call    ?ManualLock@?$Win32RawLockedNtObject@UtagWINDOWSTATION@@@@QEAAXPEAUtagWINDOWSTATION@@@Z; Win32RawLockedNtObject<tagWINDOWSTATION>::ManualLock(tagWINDOWSTATION *)
0x14028f3f6  mov     rax, [rsi+1E8h]
0x14028f3fd  lea     r8, [rbp+57h+BugCheckParameter3]
0x14028f401  mov     rcx, [rax+8]
0x14028f405  mov     rbx, [rcx+18h]
0x14028f409  mov     rcx, rsi
0x14028f40c  mov     rdx, rbx
0x14028f40f  call    ??$Win32HM_LockIntoThread@$00@@YAXPEAUtagTHREADINFO@@PEAU_HEAD@@PEAU_Win32HMThreadLockItem@@@Z; Win32HM_LockIntoThread<1>(tagTHREADINFO *,_HEAD *,_Win32HMThreadLockItem *)
0x14028f414  xor     edx, edx
0x14028f416  mov     rcx, rbx
0x14028f419  call    _OpenClipboard
0x14028f41e  lea     rcx, [rbp+57h+BugCheckParameter3]; BugCheckParameter3
0x14028f422  mov     ebx, eax
0x14028f424  call    ??1?$Win32HMThreadLock@UtagCURSOR@@@@QEAA@XZ; Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>(void)
0x14028f429  test    ebx, ebx
0x14028f42b  jz      loc_14028F367
0x14028f431  mov     rcx, r13; BugCheckParameter3
0x14028f434  xor     esi, esi
0x14028f436  call    xxxEmptyClipboard
0x14028f43b  mov     rax, [rdi+28h]
0x14028f43f  lea     rcx, [rbp+57h+var_58]
0x14028f443  movups  xmm0, xmmword ptr [rax+58h]
0x14028f447  movdqu  xmmword ptr [rbp+57h+BugCheckParameter3], xmm0
0x14028f44c  call    GetPhysicalScreenRect
0x14028f451  lea     r8, [rbp+57h+var_58]
0x14028f455  lea     rdx, [rbp+57h+BugCheckParameter3]
0x14028f459  lea     rcx, [rbp+57h+BugCheckParameter3]
0x14028f45d  movups  xmm0, xmmword ptr [rax]
0x14028f460  movdqu  [rbp+57h+var_58], xmm0
0x14028f465  call    IntersectRect
0x14028f46a  test    eax, eax
0x14028f46c  jnz     short loc_14028F475
0x14028f46e  xor     ebx, ebx
0x14028f470  jmp     loc_14028F75F
0x14028f475  mov     edx, dword ptr [rbp+57h+BugCheckParameter3]
0x14028f478  mov     rcx, rdi
0x14028f47b  mov     r8d, dword ptr [rbp+57h+BugCheckParameter3+4]
0x14028f47f  mov     ebx, dword ptr [rbp+57h+BugCheckParameter3+8]
0x14028f482  mov     r12d, dword ptr [rbp+57h+BugCheckParameter3+0Ch]
0x14028f486  sub     ebx, edx
0x14028f488  sub     r12d, r8d
0x14028f48b  mov     [rbp+57h+var_7C], edx
0x14028f48e  mov     [rbp+57h+var_80], r8d
0x14028f492  call    _GetDesktopWindow
0x14028f497  cmp     rdi, rax
0x14028f49a  jz      short loc_14028F4AE
0x14028f49c  mov     rax, [rdi+28h]
0x14028f4a0  sub     edx, [rax+58h]
0x14028f4a3  sub     r8d, [rax+5Ch]
0x14028f4a7  mov     [rbp+57h+var_80], r8d
0x14028f4ab  mov     [rbp+57h+var_7C], edx
0x14028f4ae  xor     edx, edx
0x14028f4b0  mov     r8d, 10001h
0x14028f4b6  call    cs:__imp__GetDCEx
0x14028f4bd  nop     dword ptr [rax+rax+00h]
0x14028f4c2  mov     r15, rax
0x14028f4c5  test    rax, rax
0x14028f4c8  jz      loc_14028F744
0x14028f4ce  mov     rcx, rax
0x14028f4d1  call    cs:__imp_GreCreateCompatibleDC
0x14028f4d8  nop     dword ptr [rax+rax+00h]
0x14028f4dd  mov     rsi, rax
0x14028f4e0  test    rax, rax
0x14028f4e3  jz      loc_14028F744
0x14028f4e9  call    cs:__imp_W32GetUserSessionState
0x14028f4f0  nop     dword ptr [rax+rax+00h]
0x14028f4f5  mov     rcx, [rax+4CF8h]
0x14028f4fc  cmp     dword ptr [rcx+8ACh], 0
0x14028f503  jz      short loc_14028F529
0x14028f505  mov     [rsp+0E0h+var_B8], 0
0x14028f50e  xor     r9d, r9d
0x14028f511  mov     r8d, r12d
0x14028f514  mov     qword ptr [rsp+0E0h+var_C0], 0
0x14028f51d  mov     edx, ebx
0x14028f51f  mov     rcx, r15
0x14028f522  call    GreCreateCompatibleBitmapEx
0x14028f527  jmp     short loc_14028F561
0x14028f529  call    cs:__imp_W32GetUserSessionState
0x14028f530  nop     dword ptr [rax+rax+00h]
0x14028f535  mov     r8d, r14d
0x14028f538  mov     qword ptr [rsp+0E0h+var_C0], 0
0x14028f541  mov     edx, r12d
0x14028f544  mov     rcx, [rax+0DDA8h]
0x14028f54b  movzx   r9d, word ptr [rcx+80h]
0x14028f553  mov     ecx, ebx
0x14028f555  call    cs:__imp_GreCreateBitmap
0x14028f55c  nop     dword ptr [rax+rax+00h]
0x14028f561  mov     r14, rax
0x14028f564  test    rax, rax
0x14028f567  jnz     short loc_14028F595
0x14028f569  mov     qword ptr [rsp+0E0h+var_C0], rax
0x14028f56e  mov     edx, r12d
0x14028f571  lea     eax, [r14+1]
0x14028f575  mov     ecx, ebx
0x14028f577  mov     r9d, eax
0x14028f57a  mov     r8d, eax
0x14028f57d  call    cs:__imp_GreCreateBitmap
0x14028f584  nop     dword ptr [rax+rax+00h]
0x14028f589  mov     r14, rax
0x14028f58c  test    rax, rax
0x14028f58f  jz      loc_14028F744
0x14028f595  mov     rdx, r14
0x14028f598  mov     rcx, rsi
0x14028f59b  call    cs:__imp_GreSelectBitmap
0x14028f5a2  nop     dword ptr [rax+rax+00h]
0x14028f5a7  cmp     [rbp+57h+arg_8], 0
0x14028f5ab  mov     [rbp+57h+BugCheckParameter3], rax
0x14028f5af  jnz     short loc_14028F5E3
0x14028f5b1  mov     rcx, [rbp+57h+arg_18]
0x14028f5b5  mov     rcx, [rcx+1E8h]
0x14028f5bc  mov     rdx, [rcx+8]
0x14028f5c0  cmp     rdi, [rdx+18h]
0x14028f5c4  jnz     short loc_14028F5E3
0x14028f5c6  call    cs:__imp_UserIsCurrentProcessImmersiveAppContainer
0x14028f5cd  nop     dword ptr [rax+rax+00h]
0x14028f5d2  test    eax, eax
0x14028f5d4  jz      short loc_14028F5E3
0x14028f5d6  xor     ecx, ecx
0x14028f5d8  mov     byte ptr [rbp+57h+arg_10], 1
0x14028f5dc  call    GreEnableAppContainerRestriction
0x14028f5e1  jmp     short loc_14028F5E7
0x14028f5e3  mov     byte ptr [rbp+57h+arg_10], 0
0x14028f5e7  mov     rcx, rdi
0x14028f5ea  call    cs:__imp_IsWindowDesktopComposed
0x14028f5f1  nop     dword ptr [rax+rax+00h]
0x14028f5f6  xor     edi, edi
0x14028f5f8  test    eax, eax
0x14028f5fa  jz      short loc_14028F64E
0x14028f5fc  lea     rcx, [rbp+57h+arg_18]; this
0x14028f600  call    ??0LeaveEnterCrit@@QEAA@XZ; LeaveEnterCrit::LeaveEnterCrit(void)
0x14028f605  mov     eax, [rbp+57h+var_80]
0x14028f608  mov     r9d, ebx
0x14028f60b  mov     [rsp+0E0h+var_90], 4
0x14028f613  xor     r8d, r8d
0x14028f616  mov     [rsp+0E0h+var_98], edi
0x14028f61a  xor     edx, edx
0x14028f61c  mov     [rsp+0E0h+var_A0], 40CC0020h
0x14028f624  mov     rcx, rsi
0x14028f627  mov     [rsp+0E0h+var_A8], eax
0x14028f62b  mov     eax, [rbp+57h+var_7C]
0x14028f62e  mov     [rsp+0E0h+var_B0], eax
0x14028f632  mov     [rsp+0E0h+var_B8], r15
0x14028f637  mov     [rsp+0E0h+var_C0], r12d
0x14028f63c  call    GreBitBltInternal
0x14028f641  lea     rcx, [rbp+57h+arg_18]; this
0x14028f645  mov     ebx, eax
0x14028f647  call    ??1LeaveEnterCrit@@QEAA@XZ; LeaveEnterCrit::~LeaveEnterCrit(void)
0x14028f64c  jmp     short loc_14028F688
0x14028f64e  mov     eax, [rbp+57h+var_80]
0x14028f651  mov     r9d, ebx
0x14028f654  mov     [rsp+0E0h+var_90], edi
0x14028f658  xor     r8d, r8d
0x14028f65b  mov     [rsp+0E0h+var_98], edi
0x14028f65f  xor     edx, edx
0x14028f661  mov     [rsp+0E0h+var_A0], 40CC0020h
0x14028f669  mov     rcx, rsi
0x14028f66c  mov     [rsp+0E0h+var_A8], eax
0x14028f670  mov     eax, [rbp+57h+var_7C]
0x14028f673  mov     [rsp+0E0h+var_B0], eax
0x14028f677  mov     [rsp+0E0h+var_B8], r15
0x14028f67c  mov     [rsp+0E0h+var_C0], r12d
0x14028f681  call    GreBitBltInternal
0x14028f686  mov     ebx, eax
0x14028f688  mov     r12d, 1
0x14028f68e  cmp     byte ptr [rbp+57h+arg_10], dil
0x14028f692  jz      short loc_14028F69C
0x14028f694  mov     ecx, r12d
0x14028f697  call    GreEnableAppContainerRestriction
0x14028f69c  mov     rdx, [rbp+57h+BugCheckParameter3]
0x14028f6a0  mov     rcx, rsi
0x14028f6a3  call    cs:__imp_GreSelectBitmap
0x14028f6aa  nop     dword ptr [rax+rax+00h]
0x14028f6af  test    ebx, ebx
0x14028f6b1  jnz     short loc_14028F6D0
0x14028f6b3  test    r14, r14
0x14028f6b6  jz      loc_14028F750
0x14028f6bc  mov     rcx, r14
0x14028f6bf  call    cs:__imp_GreDeleteObject
0x14028f6c6  nop     dword ptr [rax+rax+00h]
0x14028f6cb  jmp     loc_14028F750
0x14028f6d0  xor     r8d, r8d; int
0x14028f6d3  mov     r9d, r12d; int
0x14028f6d6  mov     rdx, r14; void *
0x14028f6d9  lea     ecx, [r8+2]; unsigned int
0x14028f6dd  call    _SetClipboardData
0x14028f6e2  call    cs:__imp_W32GetUserSessionState
0x14028f6e9  nop     dword ptr [rax+rax+00h]
0x14028f6ee  mov     rcx, [rax+4CF8h]
0x14028f6f5  mov     eax, [rcx+1B5Ch]
0x14028f6fb  test    r12b, al
0x14028f6fe  jz      short loc_14028F73F
0x14028f700  lea     r8, [rbp+57h+arg_10]
0x14028f704  mov     [rbp+57h+arg_18], rdi
0x14028f708  lea     rdx, [rbp+57h+arg_18]
0x14028f70c  mov     [rbp+57h+arg_10], rdi
0x14028f710  mov     rcx, r15; HDC
0x14028f713  call    CreateScreenPalette
0x14028f718  test    eax, eax
0x14028f71a  js      short loc_14028F73F
0x14028f71c  mov     rdx, [rbp+57h+arg_10]; void *
0x14028f720  xor     r8d, r8d; int
0x14028f723  mov     r9d, r12d; int
0x14028f726  lea     ecx, [r8+9]; unsigned int
0x14028f72a  call    _SetClipboardData
0x14028f72f  mov     rcx, [rbp+57h+arg_18]
0x14028f733  call    cs:__imp_Win32FreePool
0x14028f73a  nop     dword ptr [rax+rax+00h]
0x14028f73f  mov     ebx, r12d
0x14028f742  jmp     short loc_14028F750
0x14028f744  call    ClientNoMemoryPopup
0x14028f749  xor     ebx, ebx
0x14028f74b  test    r15, r15
0x14028f74e  jz      short loc_14028F75F
0x14028f750  mov     rcx, r15
0x14028f753  call    cs:__imp__ReleaseDC
  ... truncated ...
```
