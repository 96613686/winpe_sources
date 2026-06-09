# xxxRedrawHungWindow(tagWND *,HRGN__ *)

- ea: `0x1402daf74`
- end: `0x1402db56a`
- name: `?xxxRedrawHungWindow@@YAXPEAUtagWND@@PEAUHRGN__@@@Z`
- size: `1526`
- prototype: `void __fastcall(struct tagWND *, HRGN)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401a76ac`

## callees

- `0x140005a18`
- `0x14001af00`
- `0x1400240e0`
- `0x1400241fc`
- `0x1400399ac`
- `0x14008f430`
- `0x140091448`
- `0x140094974`
- `0x1400bbd30`
- `0x1400cf450`
- `0x1400db6d4`
- `0x1400e2cb0`
- `0x1400edccc`
- `0x14010dc20`
- `0x1402938dc`
- `0x1402daf74`
- `0x140319358`
- `0x140342fa0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x1402db457`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1402db457`
- `ntoskrnl!KeBugCheckEx` at `0x1402db3f0`
- `ntoskrnl!KeBugCheckEx` at `0x1402db3f0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1402db37e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1402db37e`
- `win32kbase!_GetDCEx` at `0x1402db0fd`
- `win32kbase!_GetDCEx` at `0x1402db228`
- `win32kbase!_GetDCEx` at `0x1402db0fd`
- `win32kbase!_GetDCEx` at `0x1402db228`
- `win32kbase!_ReleaseDC` at `0x1402db150`
- `win32kbase!_ReleaseDC` at `0x1402db4f5`
- `win32kbase!_ReleaseDC` at `0x1402db150`
- `win32kbase!_ReleaseDC` at `0x1402db4f5`
- `win32kbase!GreGetRgnBox` at `0x1402db2f1`
- `win32kbase!GreGetRgnBox` at `0x1402db2f1`
- `win32kbase!GreGetObjectOwner` at `0x1402db441`
- `win32kbase!GreGetObjectOwner` at `0x1402db441`
- `win32kbase!GreGetBrushColor` at `0x1402db46a`
- `win32kbase!GreGetBrushColor` at `0x1402db497`
- `win32kbase!GreGetBrushColor` at `0x1402db46a`
- `win32kbase!GreGetBrushColor` at `0x1402db497`
- `win32kbase!GreSetSolidBrush` at `0x1402db4ba`
- `win32kbase!GreSetSolidBrush` at `0x1402db4ba`
- `win32kbase!GreCreateRectRgnIndirect` at `0x1402db08b`
- `win32kbase!GreCreateRectRgnIndirect` at `0x1402db08b`
- `win32kbase!SetRectRgnIndirect` at `0x1402db1a0`
- `win32kbase!SetRectRgnIndirect` at `0x1402db1a0`
- `win32kbase!CreateEmptyRgn` at `0x1402db02f`
- `win32kbase!CreateEmptyRgn` at `0x1402db02f`
- `win32kbase!GreCombineRgn` at `0x1402db05a`
- `win32kbase!GreCombineRgn` at `0x1402db0b7`
- `win32kbase!GreCombineRgn` at `0x1402db1d1`
- `win32kbase!GreCombineRgn` at `0x1402db05a`
- `win32kbase!GreCombineRgn` at `0x1402db0b7`
- `win32kbase!GreCombineRgn` at `0x1402db1d1`
- `win32kbase!GreDeleteObject` at `0x1402db06d`
- `win32kbase!GreDeleteObject` at `0x1402db0cb`
- `win32kbase!GreDeleteObject` at `0x1402db1f1`
- `win32kbase!GreDeleteObject` at `0x1402db2b2`
- `win32kbase!GreDeleteObject` at `0x1402db3ba`
- `win32kbase!GreDeleteObject` at `0x1402db06d`
- `win32kbase!GreDeleteObject` at `0x1402db0cb`
- `win32kbase!GreDeleteObject` at `0x1402db1f1`
- `win32kbase!GreDeleteObject` at `0x1402db2b2`
- `win32kbase!GreDeleteObject` at `0x1402db3ba`
- `WIN32K!W32GetUserSessionState` at `0x1402db116`
- `WIN32K!W32GetUserSessionState` at `0x1402db189`
- `WIN32K!W32GetUserSessionState` at `0x1402db1b5`
- `WIN32K!W32GetUserSessionState` at `0x1402db28f`
- `WIN32K!W32GetUserSessionState` at `0x1402db363`
- `WIN32K!W32GetUserSessionState` at `0x1402db403`
- `WIN32K!W32GetUserSessionState` at `0x1402db41f`
- `WIN32K!W32GetUserSessionState` at `0x1402db47d`
- `WIN32K!W32GetUserSessionState` at `0x1402db4a5`
- `WIN32K!W32GetUserSessionState` at `0x1402db4c6`
- `WIN32K!W32GetUserSessionState` at `0x1402db116`
- `WIN32K!W32GetUserSessionState` at `0x1402db189`
- `WIN32K!W32GetUserSessionState` at `0x1402db1b5`
- `WIN32K!W32GetUserSessionState` at `0x1402db28f`
- `WIN32K!W32GetUserSessionState` at `0x1402db363`
- `WIN32K!W32GetUserSessionState` at `0x1402db403`
- `WIN32K!W32GetUserSessionState` at `0x1402db41f`
- `WIN32K!W32GetUserSessionState` at `0x1402db47d`
- `WIN32K!W32GetUserSessionState` at `0x1402db4a5`
- `WIN32K!W32GetUserSessionState` at `0x1402db4c6`

## pseudocode

```c
void __fastcall xxxRedrawHungWindow(struct tagWND *a1, HRGN a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rbx
  unsigned __int64 v9; // r14
  __int64 EmptyRgn; // rax
  unsigned __int64 v11; // rbx
  __int64 DCEx; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rsi
  __int64 UserSessionState; // rax
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // r8
  HDC v26; // r14
  __int64 v27; // r8
  RECT v28; // xmm0
  int v29; // edx
  int v30; // ecx
  __int64 v31; // rdx
  __int64 v32; // rcx
  HBRUSH v33; // rbx
  __int64 v34; // rcx
  __int64 v35; // rcx
  struct tagWND *i; // rsi
  __int64 v37; // r8
  int v38; // r14d
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 CurrentThreadWin32Thread; // rax
  HRGN v43; // rdx
  int ObjectOwner; // esi
  __int64 v45; // rdx
  __int64 v46; // rcx
  unsigned int BrushColor; // ebx
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rdx
  __int64 v51; // rcx
  HRGN v52; // [rsp+30h] [rbp-50h] BYREF
  char v53[8]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v54; // [rsp+40h] [rbp-40h]
  __int128 v55; // [rsp+48h] [rbp-38h] BYREF
  ULONG_PTR BugCheckParameter3[2]; // [rsp+58h] [rbp-28h] BYREF
  RECT v57; // [rsp+68h] [rbp-18h] BYREF

  v57 = 0;
  if ( *((_QWORD *)PtiCurrent() + 61) )
  {
    v5 = **(_QWORD **)(*((_QWORD *)PtiCurrent() + 61) + 8LL);
    if ( (*(_DWORD *)(v5 + 64) & 1) != 0 )
    {
      LODWORD(v52) = 0x20000;
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1985);
    }
  }
  v8 = *((_QWORD *)a1 + 5);
  v9 = *(_QWORD *)(v8 + 136);
  if ( v9 && (*(_BYTE *)(v8 + 31) & 0x10) != 0 && (!a2 || !GetStyleWindow(a1, 2568)) )
  {
    if ( v9 <= 1 )
    {
      v57 = *(RECT *)(v8 + 88);
      v11 = GreCreateRectRgnIndirect(&v57);
      if ( !v11 )
        v11 = 1;
    }
    else
    {
      EmptyRgn = CreateEmptyRgn(v5, v4, v6, v7);
      v11 = EmptyRgn;
      if ( !EmptyRgn )
      {
LABEL_12:
        v11 = 1;
        goto LABEL_15;
      }
      if ( !(unsigned int)GreCombineRgn(EmptyRgn, *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL), 0, 5) )
      {
        GreDeleteObject(v11);
        goto LABEL_12;
      }
    }
LABEL_15:
    if ( a2 && v11 != 1 && (unsigned int)GreCombineRgn(v11, v11, a2, 1) == 1 )
    {
      GreDeleteObject(v11);
      return;
    }
    Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(BugCheckParameter3, a1);
    if ( !(unsigned int)IsInsideUserApiHook() )
    {
      DCEx = _GetDCEx(a1, v11, 328833);
      v14 = *((_QWORD *)a1 + 5);
      v15 = DCEx;
      if ( (*(_BYTE *)(v14 + 16) & 0x40) == 0
        || (UserSessionState = W32GetUserSessionState(v14, v13),
            v17 = 8193,
            *(_QWORD *)(*((_QWORD *)a1 + 2) + 464LL) != *(_QWORD *)(UserSessionState + 18968)) )
      {
        v17 = 0x2000;
      }
      xxxDrawWindowFrame(a1, v15, v17);
      _ReleaseDC(v15);
    }
    xxxInternalInvalidate(a1, (HRGN)v11, 0x485u);
    v57 = *(RECT *)(*((_QWORD *)a1 + 5) + 88LL);
    xxxCalcClientRect(a1);
    v20 = W32GetUserSessionState(v19, v18);
    SetRectRgnIndirect(*(_QWORD *)(v20 + 63136), &v57);
    if ( v11 <= 1 )
    {
      if ( !v11 )
        goto LABEL_28;
    }
    else
    {
      v23 = W32GetUserSessionState(v22, v21);
      v24 = GreCombineRgn(v11, v11, *(_QWORD *)(v23 + 63136), 1);
      if ( v24 )
      {
        if ( v24 == 1 )
        {
          GreDeleteObject(v11);
          v11 = 0;
LABEL_28:
          v25 = (4 * (*(_BYTE *)(*((_QWORD *)a1 + 5) + 31LL) & 4)) | 0x8Bu;
          if ( (*(_BYTE *)(*((_QWORD *)a1 + 5) + 31LL) & 2) == 0 )
            v25 = (4 * (*(_BYTE *)(*((_QWORD *)a1 + 5) + 31LL) & 4)) | 0x83u;
          v26 = (HDC)_GetDCEx(a1, v11, v25);
          GreWatchVisRgnChange(v26);
          v27 = *((_QWORD *)a1 + 5);
          v57 = *(RECT *)(v27 + 88);
          v28 = v57;
          v29 = *(_DWORD *)(v27 + 92);
          v30 = -*(_DWORD *)(v27 + 88);
          v57.right -= *(_DWORD *)(v27 + 88);
          v31 = (unsigned int)-v29;
          v57.bottom += v31;
          v57.top += v31;
          v57.left = v30 + _mm_cvtsi128_si32((__m128i)v28);
          v32 = *(_QWORD *)(*((_QWORD *)a1 + 17) + 8LL);
          v33 = *(HBRUSH *)(v32 + 72);
          if ( v33 )
          {
            if ( (unsigned __int64)v33 <= 0x1F )
              v33 = *(HBRUSH *)(*(_QWORD *)(W32GetUserSessionState(v32, v31) + 19704) + 8LL * (_QWORD)v33 + 4688);
          }
          else if ( (*(_BYTE *)(v27 + 18) & 1) != 0 )
          {
            v33 = *(HBRUSH *)(*(_QWORD *)(W32GetUserSessionState(v32, v31) + 19704) + 4816LL);
          }
          else
          {
            v33 = *(HBRUSH *)(*(_QWORD *)(W32GetUserSessionState(v32, v31) + 19704) + 4736LL);
          }
          ObjectOwner = GreGetObjectOwner(v33, 16);
          if ( ObjectOwner && ObjectOwner != (unsigned int)PsGetCurrentProcessId() )
          {
            BrushColor = GreGetBrushColor(v33);
            if ( BrushColor == -1 )
            {
              v48 = W32GetUserSessionState(v46, v45);
              BrushColor = GreGetBrushColor(*(_QWORD *)(*(_QWORD *)(v48 + 19704) + 4736LL));
            }
            v49 = W32GetUserSessionState(v46, v45);
            GreSetSolidBrush(*(_QWORD *)(v49 + 42840), BrushColor);
            v33 = *(HBRUSH *)(W32GetUserSessionState(v51, v50) + 42840);
          }
          FillRect(v26, &v57, v33);
          GreWatchVisRgnChange(v26);
          _ReleaseDC(v26);
          SetOrClrWF(1, a1, 264, 1);
          SetOrClrWF(1, a1, 258, 1);
          SetOrClrWF(1, a1, 288, 1);
          Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)BugCheckParameter3);
          return;
        }
      }
      else
      {
        GreDeleteObject(v11);
        v11 = 1;
      }
    }
    v34 = *((_QWORD *)a1 + 5);
    if ( (*(_BYTE *)(v34 + 31) & 2) == 0 )
    {
      v35 = *(_QWORD *)(v34 + 136);
      v55 = 0;
      if ( v35 == 1 || !(unsigned int)GreGetRgnBox(v35, &v57) )
        v57 = *(RECT *)(*((_QWORD *)a1 + 5) + 88LL);
      for ( i = (struct tagWND *)*((_QWORD *)a1 + 14); i; i = (struct tagWND *)*((_QWORD *)i + 11) )
      {
        v37 = *((_QWORD *)i + 5);
        if ( (*(_BYTE *)(v37 + 31) & 0x10) != 0
          && ((*(_BYTE *)(v37 + 20) & 4) != 0 || !*(_QWORD *)(v37 + 136))
          && (unsigned int)IntersectRect(&v55, &v57, v37 + 88) )
        {
          v52 = (HRGN)v11;
          v38 = PhysicalToLogicalInPlaceRgn(i, &v52);
          if ( !*(_QWORD *)W32GetUserSessionState(v40, v39) || !IS_USERCRIT_OWNED_AT_ALL() )
            KeBugCheckEx(0x164u, 0x2Au, 0, 0, 0);
          CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread(v41);
          v43 = v52;
          v54 = CurrentThreadWin32Thread;
          v53[0] = 1;
          ++*(_DWORD *)(CurrentThreadWin32Thread + 28);
          xxxInternalInvalidate(i, v43, 0x485u);
          AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v53);
          if ( v38 )
            GreDeleteObject(v52);
        }
      }
    }
    goto LABEL_28;
  }
}

```

## disassembly

```asm
0x1402daf74  mov     [rsp-28h+arg_10], rbx
0x1402daf79  push    rbp
0x1402daf7a  push    rsi
0x1402daf7b  push    rdi
0x1402daf7c  push    r12
0x1402daf7e  push    r14
0x1402daf80  mov     rbp, rsp
0x1402daf83  sub     rsp, 80h
0x1402daf8a  mov     rax, cs:__security_cookie
0x1402daf91  xor     rax, rsp
0x1402daf94  mov     [rbp+var_8], rax
0x1402daf98  xorps   xmm0, xmm0
0x1402daf9b  mov     rsi, rdx
0x1402daf9e  movups  xmmword ptr [rbp+var_18.left], xmm0
0x1402dafa2  mov     rdi, rcx
0x1402dafa5  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1402dafaa  mov     r12d, 1
0x1402dafb0  cmp     qword ptr [rax+1E8h], 0
0x1402dafb8  jz      short loc_1402DAFF1
0x1402dafba  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1402dafbf  mov     rcx, [rax+1E8h]
0x1402dafc6  mov     rax, [rcx+8]
0x1402dafca  mov     rcx, [rax]
0x1402dafcd  mov     eax, [rcx+40h]
0x1402dafd0  test    r12b, al
0x1402dafd3  jz      short loc_1402DAFF1
0x1402dafd5  mov     dword ptr [rbp+var_50], 20000h
0x1402dafdc  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1402dafe3  mov     edx, dword ptr [rbp+var_50]
0x1402dafe6  mov     r8d, 7C1h
0x1402dafec  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1402daff1  mov     rbx, [rdi+28h]
0x1402daff5  mov     r14, [rbx+88h]
0x1402daffc  test    r14, r14
0x1402dafff  jz      loc_1402DB546
0x1402db005  test    byte ptr [rbx+1Fh], 10h
0x1402db009  jz      loc_1402DB546
0x1402db00f  test    rsi, rsi
0x1402db012  jz      short loc_1402DB02A
0x1402db014  mov     edx, 0A08h
0x1402db019  mov     rcx, rdi
0x1402db01c  call    GetStyleWindow
0x1402db021  test    rax, rax
0x1402db024  jnz     loc_1402DB546
0x1402db02a  cmp     r14, r12
0x1402db02d  jbe     short loc_1402DB07E
0x1402db02f  call    cs:__imp_CreateEmptyRgn
0x1402db036  nop     dword ptr [rax+rax+00h]
0x1402db03b  mov     rbx, rax
0x1402db03e  test    rax, rax
0x1402db041  jz      short loc_1402DB079
0x1402db043  mov     rdx, [rdi+28h]
0x1402db047  mov     r9d, 5
0x1402db04d  xor     r8d, r8d
0x1402db050  mov     rcx, rax
0x1402db053  mov     rdx, [rdx+88h]
0x1402db05a  call    cs:__imp_GreCombineRgn
0x1402db061  nop     dword ptr [rax+rax+00h]
0x1402db066  test    eax, eax
0x1402db068  jnz     short loc_1402DB0A1
0x1402db06a  mov     rcx, rbx
0x1402db06d  call    cs:__imp_GreDeleteObject
0x1402db074  nop     dword ptr [rax+rax+00h]
0x1402db079  mov     rbx, r12
0x1402db07c  jmp     short loc_1402DB0A1
0x1402db07e  movups  xmm0, xmmword ptr [rbx+58h]
0x1402db082  lea     rcx, [rbp+var_18]
0x1402db086  movdqu  xmmword ptr [rbp+var_18.left], xmm0
0x1402db08b  call    cs:__imp_GreCreateRectRgnIndirect
0x1402db092  nop     dword ptr [rax+rax+00h]
0x1402db097  test    rax, rax
0x1402db09a  mov     rbx, rax
0x1402db09d  cmovz   rbx, r12
0x1402db0a1  test    rsi, rsi
0x1402db0a4  jz      short loc_1402DB0DC
0x1402db0a6  cmp     rbx, r12
0x1402db0a9  jz      short loc_1402DB0DC
0x1402db0ab  mov     r9d, r12d
0x1402db0ae  mov     r8, rsi
0x1402db0b1  mov     rdx, rbx
0x1402db0b4  mov     rcx, rbx
0x1402db0b7  call    cs:__imp_GreCombineRgn
0x1402db0be  nop     dword ptr [rax+rax+00h]
0x1402db0c3  cmp     eax, r12d
0x1402db0c6  jnz     short loc_1402DB0DC
0x1402db0c8  mov     rcx, rbx
0x1402db0cb  call    cs:__imp_GreDeleteObject
0x1402db0d2  nop     dword ptr [rax+rax+00h]
0x1402db0d7  jmp     loc_1402DB546
0x1402db0dc  mov     rdx, rdi
0x1402db0df  lea     rcx, [rbp+BugCheckParameter3]
0x1402db0e3  call    ??0?$Win32HMThreadLockBase@UtagMENU@@$00$0A@@@QEAA@PEAUtagMENU@@@Z; Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(tagMENU *)
0x1402db0e8  call    ?IsInsideUserApiHook@@YAHXZ; IsInsideUserApiHook(void)
0x1402db0ed  test    eax, eax
0x1402db0ef  jnz     short loc_1402DB15C
0x1402db0f1  mov     r8d, 50481h
0x1402db0f7  mov     rdx, rbx
0x1402db0fa  mov     rcx, rdi
0x1402db0fd  call    cs:__imp__GetDCEx
0x1402db104  nop     dword ptr [rax+rax+00h]
0x1402db109  mov     rcx, [rdi+28h]
0x1402db10d  mov     rsi, rax
0x1402db110  test    byte ptr [rcx+10h], 40h
0x1402db114  jz      short loc_1402DB13C
0x1402db116  call    cs:__imp_W32GetUserSessionState
0x1402db11d  nop     dword ptr [rax+rax+00h]
0x1402db122  mov     rcx, [rdi+10h]
0x1402db126  mov     r8d, 2001h
0x1402db12c  mov     rdx, [rax+4A18h]
0x1402db133  cmp     [rcx+1D0h], rdx
0x1402db13a  jz      short loc_1402DB142
0x1402db13c  mov     r8d, 2000h
0x1402db142  mov     rdx, rsi
0x1402db145  mov     rcx, rdi
0x1402db148  call    xxxDrawWindowFrame
0x1402db14d  mov     rcx, rsi
0x1402db150  call    cs:__imp__ReleaseDC
0x1402db157  nop     dword ptr [rax+rax+00h]
0x1402db15c  mov     r8d, 485h
0x1402db162  mov     rdx, rbx
0x1402db165  mov     rcx, rdi
0x1402db168  call    xxxInternalInvalidate
0x1402db16d  mov     rax, [rdi+28h]
0x1402db171  lea     rdx, [rbp+var_18]
0x1402db175  mov     r8d, r12d
0x1402db178  mov     rcx, rdi; struct tagWND *
0x1402db17b  movups  xmm0, xmmword ptr [rax+58h]
0x1402db17f  movdqu  xmmword ptr [rbp+var_18.left], xmm0
0x1402db184  call    xxxCalcClientRect
0x1402db189  call    cs:__imp_W32GetUserSessionState
0x1402db190  nop     dword ptr [rax+rax+00h]
0x1402db195  lea     rdx, [rbp+var_18]
0x1402db199  mov     rcx, [rax+0F6A0h]
0x1402db1a0  call    cs:__imp_SetRectRgnIndirect
0x1402db1a7  nop     dword ptr [rax+rax+00h]
0x1402db1ac  cmp     rbx, r12
0x1402db1af  jbe     loc_1402DB2C3
0x1402db1b5  call    cs:__imp_W32GetUserSessionState
0x1402db1bc  nop     dword ptr [rax+rax+00h]
0x1402db1c1  mov     r9d, r12d
0x1402db1c4  mov     rdx, rbx
0x1402db1c7  mov     rcx, rbx
0x1402db1ca  mov     r8, [rax+0F6A0h]
0x1402db1d1  call    cs:__imp_GreCombineRgn
0x1402db1d8  nop     dword ptr [rax+rax+00h]
0x1402db1dd  test    eax, eax
0x1402db1df  jz      loc_1402DB2AF
0x1402db1e5  cmp     eax, r12d
0x1402db1e8  jnz     loc_1402DB2CC
0x1402db1ee  mov     rcx, rbx
0x1402db1f1  call    cs:__imp_GreDeleteObject
0x1402db1f8  nop     dword ptr [rax+rax+00h]
0x1402db1fd  xor     ebx, ebx
0x1402db1ff  mov     rax, [rdi+28h]
0x1402db203  mov     rdx, rbx
0x1402db206  movzx   ecx, byte ptr [rax+1Fh]
0x1402db20a  mov     eax, ecx
0x1402db20c  and     eax, 4
0x1402db20f  shl     eax, 2
0x1402db212  or      eax, 83h
0x1402db217  mov     r8d, eax
0x1402db21a  or      r8d, 8
0x1402db21e  test    cl, 2
0x1402db221  mov     rcx, rdi
0x1402db224  cmovz   r8d, eax
0x1402db228  call    cs:__imp__GetDCEx
0x1402db22f  nop     dword ptr [rax+rax+00h]
0x1402db234  mov     rcx, rax; HDC
0x1402db237  mov     edx, r12d
0x1402db23a  mov     r14, rax
0x1402db23d  call    GreWatchVisRgnChange
0x1402db242  mov     r8, [rdi+28h]
0x1402db246  movups  xmm0, xmmword ptr [r8+58h]
0x1402db24b  movups  xmmword ptr [rbp+var_18.left], xmm0
0x1402db24f  mov     ecx, [r8+58h]
0x1402db253  mov     edx, [r8+5Ch]
0x1402db257  neg     ecx
0x1402db259  add     [rbp+var_18.right], ecx
0x1402db25c  neg     edx
0x1402db25e  add     [rbp+var_18.bottom], edx
0x1402db261  add     [rbp+var_18.top], edx
0x1402db264  movd    eax, xmm0
0x1402db268  add     eax, ecx
0x1402db26a  mov     [rbp+var_18.left], eax
0x1402db26d  mov     rax, [rdi+88h]
0x1402db274  mov     rcx, [rax+8]
0x1402db278  mov     rbx, [rcx+48h]
0x1402db27c  test    rbx, rbx
0x1402db27f  jz      loc_1402DB3FD
0x1402db285  cmp     rbx, 1Fh
0x1402db289  ja      loc_1402DB439
0x1402db28f  call    cs:__imp_W32GetUserSessionState
0x1402db296  nop     dword ptr [rax+rax+00h]
0x1402db29b  mov     rcx, [rax+4CF8h]
0x1402db2a2  mov     rbx, [rcx+rbx*8+1250h]
0x1402db2aa  jmp     loc_1402DB439
0x1402db2af  mov     rcx, rbx
0x1402db2b2  call    cs:__imp_GreDeleteObject
0x1402db2b9  nop     dword ptr [rax+rax+00h]
0x1402db2be  mov     rbx, r12
0x1402db2c1  jmp     short loc_1402DB2CC
0x1402db2c3  test    rbx, rbx
0x1402db2c6  jz      loc_1402DB1FF
0x1402db2cc  mov     rcx, [rdi+28h]
0x1402db2d0  test    byte ptr [rcx+1Fh], 2
0x1402db2d4  jnz     loc_1402DB1FF
0x1402db2da  mov     rcx, [rcx+88h]
0x1402db2e1  xorps   xmm0, xmm0
0x1402db2e4  movups  [rbp+var_38], xmm0
0x1402db2e8  cmp     rcx, r12
0x1402db2eb  jz      short loc_1402DB301
0x1402db2ed  lea     rdx, [rbp+var_18]
0x1402db2f1  call    cs:__imp_GreGetRgnBox
0x1402db2f8  nop     dword ptr [rax+rax+00h]
0x1402db2fd  test    eax, eax
0x1402db2ff  jnz     short loc_1402DB30E
0x1402db301  mov     rax, [rdi+28h]
0x1402db305  movups  xmm0, xmmword ptr [rax+58h]
0x1402db309  movdqu  xmmword ptr [rbp+var_18.left], xmm0
0x1402db30e  mov     rsi, [rdi+70h]
0x1402db312  jmp     loc_1402DB3CA
0x1402db317  mov     r8, [rsi+28h]
0x1402db31b  test    byte ptr [r8+1Fh], 10h
0x1402db320  jz      loc_1402DB3C6
0x1402db326  test    byte ptr [r8+14h], 4
0x1402db32b  jnz     short loc_1402DB33B
0x1402db32d  cmp     qword ptr [r8+88h], 0
0x1402db335  jnz     loc_1402DB3C6
0x1402db33b  add     r8, 58h ; 'X'
0x1402db33f  lea     rdx, [rbp+var_18]
0x1402db343  lea     rcx, [rbp+var_38]
0x1402db347  call    IntersectRect
0x1402db34c  test    eax, eax
0x1402db34e  jz      short loc_1402DB3C6
0x1402db350  lea     rdx, [rbp+var_50]
0x1402db354  mov     [rbp+var_50], rbx
0x1402db358  mov     rcx, rsi
0x1402db35b  call    PhysicalToLogicalInPlaceRgn
0x1402db360  mov     r14d, eax
0x1402db363  call    cs:__imp_W32GetUserSessionState
0x1402db36a  nop     dword ptr [rax+rax+00h]
0x1402db36f  cmp     qword ptr [rax], 0
0x1402db373  jz      short loc_1402DB3D8
0x1402db375  call    ?IS_USERCRIT_OWNED_AT_ALL@@YA_NXZ; IS_USERCRIT_OWNED_AT_ALL(void)
0x1402db37a  test    al, al
0x1402db37c  jz      short loc_1402DB3D8
0x1402db37e  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1402db385  nop     dword ptr [rax+rax+00h]
0x1402db38a  mov     rdx, [rbp+var_50]
0x1402db38e  mov     r8d, 485h
0x1402db394  mov     rcx, rsi
0x1402db397  mov     [rbp+var_40], rax
0x1402db39b  mov     [rbp+var_48], r12b
0x1402db39f  add     [rax+1Ch], r12d
0x1402db3a3  call    xxxInternalInvalidate
0x1402db3a8  lea     rcx, [rbp+var_48]; this
0x1402db3ac  call    ?Disarm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Disarm(void)
0x1402db3b1  test    r14d, r14d
0x1402db3b4  jz      short loc_1402DB3C6
0x1402db3b6  mov     rcx, [rbp+var_50]
0x1402db3ba  call    cs:__imp_GreDeleteObject
0x1402db3c1  nop     dword ptr [rax+rax+00h]
0x1402db3c6  mov     rsi, [rsi+58h]
0x1402db3ca  test    rsi, rsi
0x1402db3cd  jnz     loc_1402DB317
0x1402db3d3  jmp     loc_1402DB1FF
0x1402db3d8  xor     r9d, r9d; BugCheckParameter3
0x1402db3db  mov     [rsp+80h+BugCheckParameter4], 0; BugCheckParameter4
0x1402db3e4  xor     r8d, r8d; BugCheckParameter2
0x1402db3e7  mov     ecx, 164h; BugCheckCode
0x1402db3ec  lea     edx, [r9+2Ah]; BugCheckParameter1
0x1402db3f0  call    cs:__imp_KeBugCheckEx
0x1402db3fd  test    [r8+12h], r12b
0x1402db401  jz      short loc_1402DB41F
0x1402db403  call    cs:__imp_W32GetUserSessionState
0x1402db40a  nop     dword ptr [rax+rax+00h]
0x1402db40f  mov     rcx, [rax+4CF8h]
0x1402db416  mov     rbx, [rcx+12D0h]
0x1402db41d  jmp     short loc_1402DB439
0x1402db41f  call    cs:__imp_W32GetUserSessionState
0x1402db426  nop     dword ptr [rax+rax+00h]
0x1402db42b  mov     rcx, [rax+4CF8h]
0x1402db432  mov     rbx, [rcx+1280h]
0x1402db439  mov     edx, 10h
0x1402db43e  mov     rcx, rbx
0x1402db441  call    cs:__imp_GreGetObjectOwner
0x1402db448  nop     dword ptr [rax+rax+00h]
0x1402db44d  mov     esi, eax
0x1402db44f  test    eax, eax
0x1402db451  jz      loc_1402DB4D9
0x1402db457  call    cs:__imp_PsGetCurrentProcessId
0x1402db45e  nop     dword ptr [rax+rax+00h]
0x1402db463  cmp     esi, eax
0x1402db465  jz      short loc_1402DB4D9
0x1402db467  mov     rcx, rbx
0x1402db46a  call    cs:__imp_GreGetBrushColor
0x1402db471  nop     dword ptr [rax+rax+00h]
0x1402db476  mov     ebx, eax
0x1402db478  cmp     eax, 0FFFFFFFFh
0x1402db47b  jnz     short loc_1402DB4A5
  ... truncated ...
```
