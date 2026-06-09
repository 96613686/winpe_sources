# xxxSnapWindow

- ea: `0x14028cdbc`
- end: `0x14028d2d4`
- name: `xxxSnapWindow`
- size: `1304`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x1401cdc10`

## callees

- `0x14001cb40`
- `0x1400291d0`
- `0x1400292ec`
- `0x14002cdbc`
- `0x1400646b4`
- `0x140093450`
- `0x1400a5ec0`
- `0x1400a82e0`
- `0x1400ba610`
- `0x1400bcaa0`
- `0x1400c2dd8`
- `0x1400df540`
- `0x140148790`
- `0x140148b3c`
- `0x140148b90`
- `0x1401751f4`
- `0x14017f430`
- `0x140207bd4`
- `0x140207fbc`
- `0x14021d5cc`
- `0x14027cb58`
- `0x14027ccc8`
- `0x14028cdbc`
- `0x1402a4da8`
- `0x1402d59f8`
- `0x1402e86ec`
- `0x1403380d0`

## import_xrefs

- `win32kbase!GreCreateCompatibleDC` at `0x14028cfe1`
- `win32kbase!GreCreateCompatibleDC` at `0x14028cfe1`
- `win32kbase!_GetDCEx` at `0x14028cfc6`
- `win32kbase!_GetDCEx` at `0x14028cfc6`
- `win32kbase!_ReleaseDC` at `0x14028d263`
- `win32kbase!_ReleaseDC` at `0x14028d263`
- `win32kbase!GreDeleteDC` at `0x14028d28f`
- `win32kbase!GreDeleteDC` at `0x14028d28f`
- `win32kbase!UserIsCurrentProcessImmersiveAppContainer` at `0x14028d0d6`
- `win32kbase!UserIsCurrentProcessImmersiveAppContainer` at `0x14028d0d6`
- `win32kbase!GreSelectBitmap` at `0x14028d0ab`
- `win32kbase!GreSelectBitmap` at `0x14028d1b3`
- `win32kbase!GreSelectBitmap` at `0x14028d0ab`
- `win32kbase!GreSelectBitmap` at `0x14028d1b3`
- `win32kbase!IsWindowDesktopComposed` at `0x14028d0fa`
- `win32kbase!IsWindowDesktopComposed` at `0x14028d0fa`
- `win32kbase!GreDeleteObject` at `0x14028d1cf`
- `win32kbase!GreDeleteObject` at `0x14028d1cf`
- `win32kbase!Win32FreePool` at `0x14028d243`
- `win32kbase!Win32FreePool` at `0x14028d243`
- `win32kbase!HMAssignmentUnlock` at `0x14028d27b`
- `win32kbase!HMAssignmentUnlock` at `0x14028d27b`
- `win32kbase!ReferenceDwmApiPort` at `0x14028cecb`
- `win32kbase!ReferenceDwmApiPort` at `0x14028cecb`
- `win32kbase!GreCreateBitmap` at `0x14028d065`
- `win32kbase!GreCreateBitmap` at `0x14028d08d`
- `win32kbase!GreCreateBitmap` at `0x14028d065`
- `win32kbase!GreCreateBitmap` at `0x14028d08d`
- `WIN32K!W32GetUserSessionState` at `0x14028ce10`
- `WIN32K!W32GetUserSessionState` at `0x14028ce23`
- `WIN32K!W32GetUserSessionState` at `0x14028cff9`
- `WIN32K!W32GetUserSessionState` at `0x14028d039`
- `WIN32K!W32GetUserSessionState` at `0x14028d1f2`
- `WIN32K!W32GetUserSessionState` at `0x14028ce10`
- `WIN32K!W32GetUserSessionState` at `0x14028ce23`
- `WIN32K!W32GetUserSessionState` at `0x14028cff9`
- `WIN32K!W32GetUserSessionState` at `0x14028d039`
- `WIN32K!W32GetUserSessionState` at `0x14028d1f2`

## pseudocode

```c
__int64 __fastcall xxxSnapWindow(_QWORD *a1, int a2)
{
  struct tagTHREADINFO *v3; // rsi
  __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rcx
  struct tagWINDOWSTATION *v7; // r13
  void *v9; // rax
  unsigned int v10; // ebx
  __int64 v11; // rbx
  Gre::Base *CompatibleDC; // rsi
  __int64 v13; // r9
  unsigned int v14; // ebx
  unsigned int v15; // r12d
  unsigned __int64 v16; // kr00_8
  int v17; // edx
  __int64 v18; // rcx
  int v19; // r8d
  __int64 DCEx; // rax
  HDC v21; // r15
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 Bitmap; // rax
  __int64 UserSessionState; // rax
  void *v26; // r14
  __int64 v27; // rcx
  ULONG_PTR BugCheckParameter3[2]; // [rsp+68h] [rbp-21h] BYREF
  ULONG_PTR v29[2]; // [rsp+78h] [rbp-11h] BYREF
  __int128 v30; // [rsp+88h] [rbp-1h] BYREF
  ULONG_PTR BugCheckParameter2[2]; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v32; // [rsp+A8h] [rbp+1Fh]
  ULONG_PTR v34; // [rsp+100h] [rbp+77h] BYREF
  struct tagTHREADINFO *v35; // [rsp+108h] [rbp+7Fh] BYREF

  v34 = 0;
  v32 = -1;
  *(_OWORD *)BugCheckParameter2 = 0;
  v29[1] = 0;
  v29[0] = -1;
  v3 = PtiCurrent();
  v35 = v3;
  v5 = *(_QWORD *)(W32GetUserSessionState(v4) + 19216);
  if ( v5 == *(_QWORD *)(W32GetUserSessionState(v6) + 62744)
    || (int)ReferenceWindowStation(KeGetCurrentThread(), 0, 512, &v34, 1) < 0
    || (v7 = (struct tagWINDOWSTATION *)v34, (*(_DWORD *)(v34 + 32) & 4) != 0)
    || *(_QWORD *)(a1[3] + 40LL) != v34 )
  {
LABEL_5:
    Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v29);
    if ( v32 != -1 )
      PopAndFreeW32ThreadLock(BugCheckParameter2);
    return 0;
  }
  while ( (*(_BYTE *)(a1[5] + 31LL) & 0x40) != 0 )
    a1 = (_QWORD *)a1[13];
  if ( !(unsigned int)IsToplevelWindowDesktopComposed(a1) )
  {
    Win32HMThreadLockBase<tagMENU,1,1>::ManualLock<void>(v29, a1);
    Win32RawLockedNtObject<tagWINDOWSTATION>::ManualLock((ULONG_PTR)BugCheckParameter2, (ULONG_PTR)v7);
    v11 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v3 + 61) + 8LL) + 24LL);
    Win32HM_LockIntoThread<1>(v3, v11, BugCheckParameter3);
    LODWORD(v11) = OpenClipboard(v11, 0);
    Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)BugCheckParameter3);
    if ( !(_DWORD)v11 )
      goto LABEL_5;
    CompatibleDC = 0;
    xxxEmptyClipboard((ULONG_PTR)v7);
    *(_OWORD *)BugCheckParameter3 = *(_OWORD *)(a1[5] + 88LL);
    v30 = *(_OWORD *)GetPhysicalScreenRect(&v30);
    if ( !(unsigned int)IntersectRect(BugCheckParameter3, BugCheckParameter3, &v30) )
    {
      v10 = 0;
LABEL_43:
      xxxCloseClipboard(v7);
      HMAssignmentUnlock((char *)v7 + 80);
      if ( CompatibleDC )
        GreDeleteDC(CompatibleDC);
      Win32RawLockedItemBase<tagWINDOWSTATION,&void UserDereferenceObject(void *),1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
      goto LABEL_46;
    }
    v14 = LODWORD(BugCheckParameter3[1]) - LODWORD(BugCheckParameter3[0]);
    v15 = HIDWORD(BugCheckParameter3[1]) - HIDWORD(BugCheckParameter3[0]);
    v16 = BugCheckParameter3[0];
    if ( a1 != (_QWORD *)GetDesktopWindow(a1, LODWORD(BugCheckParameter3[0]), HIDWORD(BugCheckParameter3[0]), v13) )
      v16 = __PAIR64__(v19 - *(_DWORD *)(a1[5] + 92LL), v17 - *(_DWORD *)(a1[5] + 88LL));
    DCEx = _GetDCEx(v18, 0, 65537);
    v21 = (HDC)DCEx;
    if ( DCEx
      && (CompatibleDC = (Gre::Base *)GreCreateCompatibleDC(DCEx)) != 0
      && ((v23 = *(_QWORD *)(W32GetUserSessionState(v22) + 19704), !*(_DWORD *)(v23 + 2220))
        ? (UserSessionState = W32GetUserSessionState(v23),
           Bitmap = GreCreateBitmap(
                      v14,
                      v15,
                      1,
                      *(unsigned __int16 *)(*(_QWORD *)(UserSessionState + 56744) + 128LL),
                      0))
        : (Bitmap = GreCreateCompatibleBitmapEx(v21, v14, v15, 0, 0, 0)),
          (v26 = (void *)Bitmap) != 0 || (v26 = (void *)GreCreateBitmap(v14, v15, 1, 1, 0)) != 0) )
    {
      BugCheckParameter3[0] = GreSelectBitmap(CompatibleDC, v26);
      if ( !a2
        && a1 == *(_QWORD **)(*(_QWORD *)(*((_QWORD *)v35 + 61) + 8LL) + 24LL)
        && (unsigned int)UserIsCurrentProcessImmersiveAppContainer() )
      {
        LOBYTE(v34) = 1;
        GreEnableAppContainerRestriction(0);
      }
      else
      {
        LOBYTE(v34) = 0;
      }
      if ( (unsigned int)IsWindowDesktopComposed(a1) )
      {
        LeaveEnterCrit::LeaveEnterCrit((LeaveEnterCrit *)&v35);
        v10 = GreBitBltInternal(CompatibleDC, 0, 0, v14, v15, (__int64)v21, v16, SHIDWORD(v16), 0x40CC0020u, 0, 4);
        LeaveEnterCrit::~LeaveEnterCrit((LeaveEnterCrit *)&v35);
      }
      else
      {
        v10 = GreBitBltInternal(CompatibleDC, 0, 0, v14, v15, (__int64)v21, v16, SHIDWORD(v16), 0x40CC0020u, 0, 0);
      }
      if ( (_BYTE)v34 )
        GreEnableAppContainerRestriction(1);
      GreSelectBitmap(CompatibleDC, BugCheckParameter3[0]);
      if ( v10 )
      {
        SetClipboardData(2u, v26, 0, 1);
        if ( (*(_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v27) + 19704) + 7004LL) & 1) != 0 )
        {
          v35 = 0;
          v34 = 0;
          if ( (int)CreateScreenPalette(v21) >= 0 )
          {
            SetClipboardData(9u, (void *)v34, 0, 1);
            Win32FreePool(v35);
          }
        }
        v10 = 1;
      }
      else if ( v26 )
      {
        GreDeleteObject(v26);
      }
    }
    else
    {
      ClientNoMemoryPopup();
      v10 = 0;
      if ( !v21 )
        goto LABEL_43;
    }
    _ReleaseDC(v21);
    goto LABEL_43;
  }
  v9 = (void *)ReferenceDwmApiPort();
  v10 = (int)DwmAsyncSnapshotWindow(v9) >= 0;
LABEL_46:
  if ( v10 )
    xxxPlayEventSound(0xDu);
  Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>((ULONG_PTR)v29);
  if ( v32 != -1 )
    PopAndFreeW32ThreadLock(BugCheckParameter2);
  return v10;
}

```

## disassembly

```asm
0x14028cdbc  mov     [rsp-8+arg_0], rbx
0x14028cdc1  mov     [rsp-8+arg_8], edx
0x14028cdc5  push    rbp
0x14028cdc6  push    rsi
0x14028cdc7  push    rdi
0x14028cdc8  push    r12
0x14028cdca  push    r13
0x14028cdcc  push    r14
0x14028cdce  push    r15
0x14028cdd0  lea     rbp, [rsp-27h]
0x14028cdd5  sub     rsp, 0B0h
0x14028cddc  xorps   xmm0, xmm0
0x14028cddf  mov     [rbp+57h+arg_10], 0
0x14028cde7  xor     eax, eax
0x14028cde9  mov     [rbp+57h+var_38], 0FFFFFFFFFFFFFFFFh
0x14028cdf1  movups  xmmword ptr [rbp+57h+BugCheckParameter2], xmm0
0x14028cdf5  mov     [rbp+57h+var_60], rax
0x14028cdf9  mov     rdi, rcx
0x14028cdfc  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFFh
0x14028ce04  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14028ce09  mov     rsi, rax
0x14028ce0c  mov     [rbp+57h+arg_18], rax
0x14028ce10  call    cs:__imp_W32GetUserSessionState
0x14028ce17  nop     dword ptr [rax+rax+00h]
0x14028ce1c  mov     rbx, [rax+4B10h]
0x14028ce23  call    cs:__imp_W32GetUserSessionState
0x14028ce2a  nop     dword ptr [rax+rax+00h]
0x14028ce2f  cmp     rbx, [rax+0F518h]
0x14028ce36  jz      short loc_14028CE77
0x14028ce38  mov     rcx, gs:188h
0x14028ce41  lea     r9, [rbp+57h+arg_10]
0x14028ce45  mov     r14d, 1
0x14028ce4b  xor     edx, edx
0x14028ce4d  mov     r8d, 200h
0x14028ce53  mov     [rsp+0E0h+var_C0], r14d
0x14028ce58  call    ReferenceWindowStation
0x14028ce5d  test    eax, eax
0x14028ce5f  js      short loc_14028CE77
0x14028ce61  mov     r13, [rbp+57h+arg_10]
0x14028ce65  mov     eax, [r13+20h]
0x14028ce69  test    al, 4
0x14028ce6b  jnz     short loc_14028CE77
0x14028ce6d  mov     rax, [rdi+18h]
0x14028ce71  cmp     [rax+28h], r13
0x14028ce75  jz      short loc_14028CEB2
0x14028ce77  lea     rcx, [rbp+57h+var_68]; BugCheckParameter3
0x14028ce7b  call    ??1?$Win32HMOptionalThreadLock@UtagHOOK@@@@QEAA@XZ; Win32HMOptionalThreadLock<tagHOOK>::~Win32HMOptionalThreadLock<tagHOOK>(void)
0x14028ce80  cmp     [rbp+57h+var_38], 0FFFFFFFFFFFFFFFFh
0x14028ce85  jz      short loc_14028CE90
0x14028ce87  lea     rcx, [rbp+57h+BugCheckParameter2]
0x14028ce8b  call    PopAndFreeW32ThreadLock
0x14028ce90  xor     eax, eax
0x14028ce92  mov     rbx, [rsp+0E0h+arg_0]
0x14028ce9a  add     rsp, 0B0h
0x14028cea1  pop     r15
0x14028cea3  pop     r14
0x14028cea5  pop     r13
0x14028cea7  pop     r12
0x14028cea9  pop     rdi
0x14028ceaa  pop     rsi
0x14028ceab  pop     rbp
0x14028ceac  retn
0x14028ceae  mov     rdi, [rdi+68h]
0x14028ceb2  mov     rax, [rdi+28h]
0x14028ceb6  test    byte ptr [rax+1Fh], 40h
0x14028ceba  jnz     short loc_14028CEAE
0x14028cebc  mov     rcx, rdi
0x14028cebf  call    IsToplevelWindowDesktopComposed
0x14028cec4  test    eax, eax
0x14028cec6  jz      short loc_14028CEEE
0x14028cec8  mov     rbx, [rdi]
0x14028cecb  call    cs:__imp_ReferenceDwmApiPort
0x14028ced2  nop     dword ptr [rax+rax+00h]
0x14028ced7  mov     rcx, rax; Object
0x14028ceda  mov     rdx, rbx
0x14028cedd  call    DwmAsyncSnapshotWindow
0x14028cee2  mov     ebx, eax
0x14028cee4  not     ebx
0x14028cee6  shr     ebx, 1Fh
0x14028cee9  jmp     loc_14028D2A6
0x14028ceee  mov     rdx, rdi
0x14028cef1  lea     rcx, [rbp+57h+var_68]
0x14028cef5  call    ??$ManualLock@X@?$Win32HMThreadLockBase@UtagMENU@@$00$00@@QEAAXPEAUtagMENU@@@Z; Win32HMThreadLockBase<tagMENU,1,1>::ManualLock<void>(tagMENU *)
0x14028cefa  mov     rdx, r13; BugCheckParameter3
0x14028cefd  lea     rcx, [rbp+57h+BugCheckParameter2]; BugCheckParameter2
0x14028cf01  call    ?ManualLock@?$Win32RawLockedNtObject@UtagWINDOWSTATION@@@@QEAAXPEAUtagWINDOWSTATION@@@Z; Win32RawLockedNtObject<tagWINDOWSTATION>::ManualLock(tagWINDOWSTATION *)
0x14028cf06  mov     rax, [rsi+1E8h]
0x14028cf0d  lea     r8, [rbp+57h+BugCheckParameter3]
0x14028cf11  mov     rcx, [rax+8]
0x14028cf15  mov     rbx, [rcx+18h]
0x14028cf19  mov     rcx, rsi
0x14028cf1c  mov     rdx, rbx
0x14028cf1f  call    ??$Win32HM_LockIntoThread@$00@@YAXPEAUtagTHREADINFO@@PEAU_HEAD@@PEAU_Win32HMThreadLockItem@@@Z; Win32HM_LockIntoThread<1>(tagTHREADINFO *,_HEAD *,_Win32HMThreadLockItem *)
0x14028cf24  xor     edx, edx
0x14028cf26  mov     rcx, rbx
0x14028cf29  call    _OpenClipboard
0x14028cf2e  lea     rcx, [rbp+57h+BugCheckParameter3]; BugCheckParameter3
0x14028cf32  mov     ebx, eax
0x14028cf34  call    ??1?$Win32HMThreadLock@UtagCURSOR@@@@QEAA@XZ; Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>(void)
0x14028cf39  test    ebx, ebx
0x14028cf3b  jz      loc_14028CE77
0x14028cf41  mov     rcx, r13; BugCheckParameter3
0x14028cf44  xor     esi, esi
0x14028cf46  call    xxxEmptyClipboard
0x14028cf4b  mov     rax, [rdi+28h]
0x14028cf4f  lea     rcx, [rbp+57h+var_58]
0x14028cf53  movups  xmm0, xmmword ptr [rax+58h]
0x14028cf57  movdqu  xmmword ptr [rbp+57h+BugCheckParameter3], xmm0
0x14028cf5c  call    GetPhysicalScreenRect
0x14028cf61  lea     r8, [rbp+57h+var_58]
0x14028cf65  lea     rdx, [rbp+57h+BugCheckParameter3]
0x14028cf69  lea     rcx, [rbp+57h+BugCheckParameter3]
0x14028cf6d  movups  xmm0, xmmword ptr [rax]
0x14028cf70  movdqu  [rbp+57h+var_58], xmm0
0x14028cf75  call    IntersectRect
0x14028cf7a  test    eax, eax
0x14028cf7c  jnz     short loc_14028CF85
0x14028cf7e  xor     ebx, ebx
0x14028cf80  jmp     loc_14028D26F
0x14028cf85  mov     edx, dword ptr [rbp+57h+BugCheckParameter3]
0x14028cf88  mov     rcx, rdi
0x14028cf8b  mov     r8d, dword ptr [rbp+57h+BugCheckParameter3+4]
0x14028cf8f  mov     ebx, dword ptr [rbp+57h+BugCheckParameter3+8]
0x14028cf92  mov     r12d, dword ptr [rbp+57h+BugCheckParameter3+0Ch]
0x14028cf96  sub     ebx, edx
0x14028cf98  sub     r12d, r8d
0x14028cf9b  mov     [rbp+57h+var_7C], edx
0x14028cf9e  mov     [rbp+57h+var_80], r8d
0x14028cfa2  call    _GetDesktopWindow
0x14028cfa7  cmp     rdi, rax
0x14028cfaa  jz      short loc_14028CFBE
0x14028cfac  mov     rax, [rdi+28h]
0x14028cfb0  sub     edx, [rax+58h]
0x14028cfb3  sub     r8d, [rax+5Ch]
0x14028cfb7  mov     [rbp+57h+var_80], r8d
0x14028cfbb  mov     [rbp+57h+var_7C], edx
0x14028cfbe  xor     edx, edx
0x14028cfc0  mov     r8d, 10001h
0x14028cfc6  call    cs:__imp__GetDCEx
0x14028cfcd  nop     dword ptr [rax+rax+00h]
0x14028cfd2  mov     r15, rax
0x14028cfd5  test    rax, rax
0x14028cfd8  jz      loc_14028D254
0x14028cfde  mov     rcx, rax
0x14028cfe1  call    cs:__imp_GreCreateCompatibleDC
0x14028cfe8  nop     dword ptr [rax+rax+00h]
0x14028cfed  mov     rsi, rax
0x14028cff0  test    rax, rax
0x14028cff3  jz      loc_14028D254
0x14028cff9  call    cs:__imp_W32GetUserSessionState
0x14028d000  nop     dword ptr [rax+rax+00h]
0x14028d005  mov     rcx, [rax+4CF8h]
0x14028d00c  cmp     dword ptr [rcx+8ACh], 0
0x14028d013  jz      short loc_14028D039
0x14028d015  mov     [rsp+0E0h+var_B8], 0
0x14028d01e  xor     r9d, r9d
0x14028d021  mov     r8d, r12d
0x14028d024  mov     qword ptr [rsp+0E0h+var_C0], 0
0x14028d02d  mov     edx, ebx
0x14028d02f  mov     rcx, r15
0x14028d032  call    GreCreateCompatibleBitmapEx
0x14028d037  jmp     short loc_14028D071
0x14028d039  call    cs:__imp_W32GetUserSessionState
0x14028d040  nop     dword ptr [rax+rax+00h]
0x14028d045  mov     r8d, r14d
0x14028d048  mov     qword ptr [rsp+0E0h+var_C0], 0
0x14028d051  mov     edx, r12d
0x14028d054  mov     rcx, [rax+0DDA8h]
0x14028d05b  movzx   r9d, word ptr [rcx+80h]
0x14028d063  mov     ecx, ebx
0x14028d065  call    cs:__imp_GreCreateBitmap
0x14028d06c  nop     dword ptr [rax+rax+00h]
0x14028d071  mov     r14, rax
0x14028d074  test    rax, rax
0x14028d077  jnz     short loc_14028D0A5
0x14028d079  mov     qword ptr [rsp+0E0h+var_C0], rax
0x14028d07e  mov     edx, r12d
0x14028d081  lea     eax, [r14+1]
0x14028d085  mov     ecx, ebx
0x14028d087  mov     r9d, eax
0x14028d08a  mov     r8d, eax
0x14028d08d  call    cs:__imp_GreCreateBitmap
0x14028d094  nop     dword ptr [rax+rax+00h]
0x14028d099  mov     r14, rax
0x14028d09c  test    rax, rax
0x14028d09f  jz      loc_14028D254
0x14028d0a5  mov     rdx, r14
0x14028d0a8  mov     rcx, rsi
0x14028d0ab  call    cs:__imp_GreSelectBitmap
0x14028d0b2  nop     dword ptr [rax+rax+00h]
0x14028d0b7  cmp     [rbp+57h+arg_8], 0
0x14028d0bb  mov     [rbp+57h+BugCheckParameter3], rax
0x14028d0bf  jnz     short loc_14028D0F3
0x14028d0c1  mov     rcx, [rbp+57h+arg_18]
0x14028d0c5  mov     rcx, [rcx+1E8h]
0x14028d0cc  mov     rdx, [rcx+8]
0x14028d0d0  cmp     rdi, [rdx+18h]
0x14028d0d4  jnz     short loc_14028D0F3
0x14028d0d6  call    cs:__imp_UserIsCurrentProcessImmersiveAppContainer
0x14028d0dd  nop     dword ptr [rax+rax+00h]
0x14028d0e2  test    eax, eax
0x14028d0e4  jz      short loc_14028D0F3
0x14028d0e6  xor     ecx, ecx
0x14028d0e8  mov     byte ptr [rbp+57h+arg_10], 1
0x14028d0ec  call    GreEnableAppContainerRestriction
0x14028d0f1  jmp     short loc_14028D0F7
0x14028d0f3  mov     byte ptr [rbp+57h+arg_10], 0
0x14028d0f7  mov     rcx, rdi
0x14028d0fa  call    cs:__imp_IsWindowDesktopComposed
0x14028d101  nop     dword ptr [rax+rax+00h]
0x14028d106  xor     edi, edi
0x14028d108  test    eax, eax
0x14028d10a  jz      short loc_14028D15E
0x14028d10c  lea     rcx, [rbp+57h+arg_18]; this
0x14028d110  call    ??0LeaveEnterCrit@@QEAA@XZ; LeaveEnterCrit::LeaveEnterCrit(void)
0x14028d115  mov     eax, [rbp+57h+var_80]
0x14028d118  mov     r9d, ebx
0x14028d11b  mov     [rsp+0E0h+var_90], 4
0x14028d123  xor     r8d, r8d
0x14028d126  mov     [rsp+0E0h+var_98], edi
0x14028d12a  xor     edx, edx
0x14028d12c  mov     [rsp+0E0h+var_A0], 40CC0020h
0x14028d134  mov     rcx, rsi
0x14028d137  mov     [rsp+0E0h+var_A8], eax
0x14028d13b  mov     eax, [rbp+57h+var_7C]
0x14028d13e  mov     [rsp+0E0h+var_B0], eax
0x14028d142  mov     [rsp+0E0h+var_B8], r15
0x14028d147  mov     [rsp+0E0h+var_C0], r12d
0x14028d14c  call    GreBitBltInternal
0x14028d151  lea     rcx, [rbp+57h+arg_18]; this
0x14028d155  mov     ebx, eax
0x14028d157  call    ??1LeaveEnterCrit@@QEAA@XZ; LeaveEnterCrit::~LeaveEnterCrit(void)
0x14028d15c  jmp     short loc_14028D198
0x14028d15e  mov     eax, [rbp+57h+var_80]
0x14028d161  mov     r9d, ebx
0x14028d164  mov     [rsp+0E0h+var_90], edi
0x14028d168  xor     r8d, r8d
0x14028d16b  mov     [rsp+0E0h+var_98], edi
0x14028d16f  xor     edx, edx
0x14028d171  mov     [rsp+0E0h+var_A0], 40CC0020h
0x14028d179  mov     rcx, rsi
0x14028d17c  mov     [rsp+0E0h+var_A8], eax
0x14028d180  mov     eax, [rbp+57h+var_7C]
0x14028d183  mov     [rsp+0E0h+var_B0], eax
0x14028d187  mov     [rsp+0E0h+var_B8], r15
0x14028d18c  mov     [rsp+0E0h+var_C0], r12d
0x14028d191  call    GreBitBltInternal
0x14028d196  mov     ebx, eax
0x14028d198  mov     r12d, 1
0x14028d19e  cmp     byte ptr [rbp+57h+arg_10], dil
0x14028d1a2  jz      short loc_14028D1AC
0x14028d1a4  mov     ecx, r12d
0x14028d1a7  call    GreEnableAppContainerRestriction
0x14028d1ac  mov     rdx, [rbp+57h+BugCheckParameter3]
0x14028d1b0  mov     rcx, rsi
0x14028d1b3  call    cs:__imp_GreSelectBitmap
0x14028d1ba  nop     dword ptr [rax+rax+00h]
0x14028d1bf  test    ebx, ebx
0x14028d1c1  jnz     short loc_14028D1E0
0x14028d1c3  test    r14, r14
0x14028d1c6  jz      loc_14028D260
0x14028d1cc  mov     rcx, r14
0x14028d1cf  call    cs:__imp_GreDeleteObject
0x14028d1d6  nop     dword ptr [rax+rax+00h]
0x14028d1db  jmp     loc_14028D260
0x14028d1e0  xor     r8d, r8d; int
0x14028d1e3  mov     r9d, r12d; int
0x14028d1e6  mov     rdx, r14; void *
0x14028d1e9  lea     ecx, [r8+2]; unsigned int
0x14028d1ed  call    _SetClipboardData
0x14028d1f2  call    cs:__imp_W32GetUserSessionState
0x14028d1f9  nop     dword ptr [rax+rax+00h]
0x14028d1fe  mov     rcx, [rax+4CF8h]
0x14028d205  mov     eax, [rcx+1B5Ch]
0x14028d20b  test    r12b, al
0x14028d20e  jz      short loc_14028D24F
0x14028d210  lea     r8, [rbp+57h+arg_10]
0x14028d214  mov     [rbp+57h+arg_18], rdi
0x14028d218  lea     rdx, [rbp+57h+arg_18]
0x14028d21c  mov     [rbp+57h+arg_10], rdi
0x14028d220  mov     rcx, r15; HDC
0x14028d223  call    CreateScreenPalette
0x14028d228  test    eax, eax
0x14028d22a  js      short loc_14028D24F
0x14028d22c  mov     rdx, [rbp+57h+arg_10]; void *
0x14028d230  xor     r8d, r8d; int
0x14028d233  mov     r9d, r12d; int
0x14028d236  lea     ecx, [r8+9]; unsigned int
0x14028d23a  call    _SetClipboardData
0x14028d23f  mov     rcx, [rbp+57h+arg_18]
0x14028d243  call    cs:__imp_Win32FreePool
0x14028d24a  nop     dword ptr [rax+rax+00h]
0x14028d24f  mov     ebx, r12d
0x14028d252  jmp     short loc_14028D260
0x14028d254  call    ClientNoMemoryPopup
0x14028d259  xor     ebx, ebx
0x14028d25b  test    r15, r15
0x14028d25e  jz      short loc_14028D26F
0x14028d260  mov     rcx, r15
0x14028d263  call    cs:__imp__ReleaseDC
  ... truncated ...
```
