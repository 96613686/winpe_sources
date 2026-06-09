# xxxRedrawHungWindow(tagWND *,HRGN__ *)

- ea: `0x1402d90b4`
- end: `0x1402d96aa`
- name: `?xxxRedrawHungWindow@@YAXPEAUtagWND@@PEAUHRGN__@@@Z`
- size: `1526`
- prototype: `void __fastcall(struct tagWND *, HRGN)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401a9dbc`

## callees

- `0x14000b370`
- `0x1400172b0`
- `0x1400192c8`
- `0x14001cc54`
- `0x1400209c0`
- `0x1400291d0`
- `0x1400292ec`
- `0x140059150`
- `0x1400af078`
- `0x1400b5444`
- `0x1400bcaa0`
- `0x1400c79ac`
- `0x1400d6bf0`
- `0x140198928`
- `0x1402913f0`
- `0x1402d90b4`
- `0x14031780c`
- `0x140341ff0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x1402d9597`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1402d9597`
- `ntoskrnl!KeBugCheckEx` at `0x1402d9530`
- `ntoskrnl!KeBugCheckEx` at `0x1402d9530`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1402d94be`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1402d94be`
- `win32kbase!_GetDCEx` at `0x1402d923d`
- `win32kbase!_GetDCEx` at `0x1402d9368`
- `win32kbase!_GetDCEx` at `0x1402d923d`
- `win32kbase!_GetDCEx` at `0x1402d9368`
- `win32kbase!_ReleaseDC` at `0x1402d9290`
- `win32kbase!_ReleaseDC` at `0x1402d9635`
- `win32kbase!_ReleaseDC` at `0x1402d9290`
- `win32kbase!_ReleaseDC` at `0x1402d9635`
- `win32kbase!GreGetRgnBox` at `0x1402d9431`
- `win32kbase!GreGetRgnBox` at `0x1402d9431`
- `win32kbase!GreGetObjectOwner` at `0x1402d9581`
- `win32kbase!GreGetObjectOwner` at `0x1402d9581`
- `win32kbase!GreGetBrushColor` at `0x1402d95aa`
- `win32kbase!GreGetBrushColor` at `0x1402d95d7`
- `win32kbase!GreGetBrushColor` at `0x1402d95aa`
- `win32kbase!GreGetBrushColor` at `0x1402d95d7`
- `win32kbase!GreSetSolidBrush` at `0x1402d95fa`
- `win32kbase!GreSetSolidBrush` at `0x1402d95fa`
- `win32kbase!GreCreateRectRgnIndirect` at `0x1402d91cb`
- `win32kbase!GreCreateRectRgnIndirect` at `0x1402d91cb`
- `win32kbase!SetRectRgnIndirect` at `0x1402d92e0`
- `win32kbase!SetRectRgnIndirect` at `0x1402d92e0`
- `win32kbase!CreateEmptyRgn` at `0x1402d916f`
- `win32kbase!CreateEmptyRgn` at `0x1402d916f`
- `win32kbase!GreCombineRgn` at `0x1402d919a`
- `win32kbase!GreCombineRgn` at `0x1402d91f7`
- `win32kbase!GreCombineRgn` at `0x1402d9311`
- `win32kbase!GreCombineRgn` at `0x1402d919a`
- `win32kbase!GreCombineRgn` at `0x1402d91f7`
- `win32kbase!GreCombineRgn` at `0x1402d9311`
- `win32kbase!GreDeleteObject` at `0x1402d91ad`
- `win32kbase!GreDeleteObject` at `0x1402d920b`
- `win32kbase!GreDeleteObject` at `0x1402d9331`
- `win32kbase!GreDeleteObject` at `0x1402d93f2`
- `win32kbase!GreDeleteObject` at `0x1402d94fa`
- `win32kbase!GreDeleteObject` at `0x1402d91ad`
- `win32kbase!GreDeleteObject` at `0x1402d920b`
- `win32kbase!GreDeleteObject` at `0x1402d9331`
- `win32kbase!GreDeleteObject` at `0x1402d93f2`
- `win32kbase!GreDeleteObject` at `0x1402d94fa`
- `WIN32K!W32GetUserSessionState` at `0x1402d9256`
- `WIN32K!W32GetUserSessionState` at `0x1402d92c9`
- `WIN32K!W32GetUserSessionState` at `0x1402d92f5`
- `WIN32K!W32GetUserSessionState` at `0x1402d93cf`
- `WIN32K!W32GetUserSessionState` at `0x1402d94a3`
- `WIN32K!W32GetUserSessionState` at `0x1402d9543`
- `WIN32K!W32GetUserSessionState` at `0x1402d955f`
- `WIN32K!W32GetUserSessionState` at `0x1402d95bd`
- `WIN32K!W32GetUserSessionState` at `0x1402d95e5`
- `WIN32K!W32GetUserSessionState` at `0x1402d9606`
- `WIN32K!W32GetUserSessionState` at `0x1402d9256`
- `WIN32K!W32GetUserSessionState` at `0x1402d92c9`
- `WIN32K!W32GetUserSessionState` at `0x1402d92f5`
- `WIN32K!W32GetUserSessionState` at `0x1402d93cf`
- `WIN32K!W32GetUserSessionState` at `0x1402d94a3`
- `WIN32K!W32GetUserSessionState` at `0x1402d9543`
- `WIN32K!W32GetUserSessionState` at `0x1402d955f`
- `WIN32K!W32GetUserSessionState` at `0x1402d95bd`
- `WIN32K!W32GetUserSessionState` at `0x1402d95e5`
- `WIN32K!W32GetUserSessionState` at `0x1402d9606`

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
  __int64 v13; // rcx
  HDC v14; // rsi
  __int64 v15; // rcx
  __int64 UserSessionState; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // r8
  HDC v21; // r14
  __int64 v22; // r8
  RECT v23; // xmm0
  int v24; // edx
  int v25; // ecx
  int v26; // edx
  __int64 v27; // rcx
  HBRUSH v28; // rbx
  __int64 v29; // rcx
  __int64 v30; // rcx
  struct tagWND *i; // rsi
  __int64 v32; // r8
  int v33; // r14d
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 CurrentThreadWin32Thread; // rax
  HRGN v37; // rdx
  int ObjectOwner; // esi
  __int64 v39; // rcx
  unsigned int BrushColor; // ebx
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rcx
  HRGN v44; // [rsp+30h] [rbp-50h] BYREF
  char v45[8]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v46; // [rsp+40h] [rbp-40h]
  __int128 v47; // [rsp+48h] [rbp-38h] BYREF
  ULONG_PTR BugCheckParameter3[2]; // [rsp+58h] [rbp-28h] BYREF
  RECT v49; // [rsp+68h] [rbp-18h] BYREF

  v49 = 0;
  if ( *((_QWORD *)PtiCurrent() + 61) )
  {
    v5 = **(_QWORD **)(*((_QWORD *)PtiCurrent() + 61) + 8LL);
    if ( (*(_DWORD *)(v5 + 64) & 1) != 0 )
    {
      LODWORD(v44) = 0x20000;
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1985);
    }
  }
  v8 = *((_QWORD *)a1 + 5);
  v9 = *(_QWORD *)(v8 + 136);
  if ( v9 && (*(_BYTE *)(v8 + 31) & 0x10) != 0 && (!a2 || !GetStyleWindow(a1, 2568)) )
  {
    if ( v9 <= 1 )
    {
      v49 = *(RECT *)(v8 + 88);
      v11 = GreCreateRectRgnIndirect(&v49);
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
    Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(BugCheckParameter3);
    if ( !(unsigned int)IsInsideUserApiHook() )
    {
      DCEx = _GetDCEx(a1, v11, 328833);
      v13 = *((_QWORD *)a1 + 5);
      v14 = (HDC)DCEx;
      if ( (*(_BYTE *)(v13 + 16) & 0x40) != 0 )
        W32GetUserSessionState(v13);
      xxxDrawWindowFrame(a1, v14);
      _ReleaseDC(v14);
    }
    xxxInternalInvalidate(a1, (HRGN)v11, 0x485u);
    v49 = *(RECT *)(*((_QWORD *)a1 + 5) + 88LL);
    xxxCalcClientRect(a1);
    UserSessionState = W32GetUserSessionState(v15);
    SetRectRgnIndirect(*(_QWORD *)(UserSessionState + 63136), &v49);
    if ( v11 <= 1 )
    {
      if ( !v11 )
        goto LABEL_27;
    }
    else
    {
      v18 = W32GetUserSessionState(v17);
      v19 = GreCombineRgn(v11, v11, *(_QWORD *)(v18 + 63136), 1);
      if ( v19 )
      {
        if ( v19 == 1 )
        {
          GreDeleteObject(v11);
          v11 = 0;
LABEL_27:
          v20 = (4 * (*(_BYTE *)(*((_QWORD *)a1 + 5) + 31LL) & 4)) | 0x8Bu;
          if ( (*(_BYTE *)(*((_QWORD *)a1 + 5) + 31LL) & 2) == 0 )
            v20 = (4 * (*(_BYTE *)(*((_QWORD *)a1 + 5) + 31LL) & 4)) | 0x83u;
          v21 = (HDC)_GetDCEx(a1, v11, v20);
          GreWatchVisRgnChange(v21);
          v22 = *((_QWORD *)a1 + 5);
          v49 = *(RECT *)(v22 + 88);
          v23 = v49;
          v24 = *(_DWORD *)(v22 + 92);
          v25 = -*(_DWORD *)(v22 + 88);
          v49.right -= *(_DWORD *)(v22 + 88);
          v26 = -v24;
          v49.bottom += v26;
          v49.top += v26;
          v49.left = v25 + _mm_cvtsi128_si32((__m128i)v23);
          v27 = *(_QWORD *)(*((_QWORD *)a1 + 17) + 8LL);
          v28 = *(HBRUSH *)(v27 + 72);
          if ( v28 )
          {
            if ( (unsigned __int64)v28 <= 0x1F )
              v28 = *(HBRUSH *)(*(_QWORD *)(W32GetUserSessionState(v27) + 19704) + 8LL * (_QWORD)v28 + 4688);
          }
          else if ( (*(_BYTE *)(v22 + 18) & 1) != 0 )
          {
            v28 = *(HBRUSH *)(*(_QWORD *)(W32GetUserSessionState(v27) + 19704) + 4816LL);
          }
          else
          {
            v28 = *(HBRUSH *)(*(_QWORD *)(W32GetUserSessionState(v27) + 19704) + 4736LL);
          }
          ObjectOwner = GreGetObjectOwner(v28, 16);
          if ( ObjectOwner && ObjectOwner != (unsigned int)PsGetCurrentProcessId() )
          {
            BrushColor = GreGetBrushColor(v28);
            if ( BrushColor == -1 )
            {
              v41 = W32GetUserSessionState(v39);
              BrushColor = GreGetBrushColor(*(_QWORD *)(*(_QWORD *)(v41 + 19704) + 4736LL));
            }
            v42 = W32GetUserSessionState(v39);
            GreSetSolidBrush(*(_QWORD *)(v42 + 42840), BrushColor);
            v28 = *(HBRUSH *)(W32GetUserSessionState(v43) + 42840);
          }
          FillRect(v21, &v49, v28);
          GreWatchVisRgnChange(v21);
          _ReleaseDC(v21);
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
    v29 = *((_QWORD *)a1 + 5);
    if ( (*(_BYTE *)(v29 + 31) & 2) == 0 )
    {
      v30 = *(_QWORD *)(v29 + 136);
      v47 = 0;
      if ( v30 == 1 || !(unsigned int)GreGetRgnBox(v30, &v49) )
        v49 = *(RECT *)(*((_QWORD *)a1 + 5) + 88LL);
      for ( i = (struct tagWND *)*((_QWORD *)a1 + 14); i; i = (struct tagWND *)*((_QWORD *)i + 11) )
      {
        v32 = *((_QWORD *)i + 5);
        if ( (*(_BYTE *)(v32 + 31) & 0x10) != 0
          && ((*(_BYTE *)(v32 + 20) & 4) != 0 || !*(_QWORD *)(v32 + 136))
          && (unsigned int)IntersectRect(&v47, &v49, v32 + 88) )
        {
          v44 = (HRGN)v11;
          v33 = PhysicalToLogicalInPlaceRgn(i, &v44);
          if ( !*(_QWORD *)W32GetUserSessionState(v34) || !IS_USERCRIT_OWNED_AT_ALL() )
            KeBugCheckEx(0x164u, 0x2Au, 0, 0, 0);
          CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread(v35);
          v37 = v44;
          v46 = CurrentThreadWin32Thread;
          v45[0] = 1;
          ++*(_DWORD *)(CurrentThreadWin32Thread + 28);
          xxxInternalInvalidate(i, v37, 0x485u);
          AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v45);
          if ( v33 )
            GreDeleteObject(v44);
        }
      }
    }
    goto LABEL_27;
  }
}

```

## disassembly

```asm
0x1402d90b4  mov     [rsp-28h+arg_10], rbx
0x1402d90b9  push    rbp
0x1402d90ba  push    rsi
0x1402d90bb  push    rdi
0x1402d90bc  push    r12
0x1402d90be  push    r14
0x1402d90c0  mov     rbp, rsp
0x1402d90c3  sub     rsp, 80h
0x1402d90ca  mov     rax, cs:__security_cookie
0x1402d90d1  xor     rax, rsp
0x1402d90d4  mov     [rbp+var_8], rax
0x1402d90d8  xorps   xmm0, xmm0
0x1402d90db  mov     rsi, rdx
0x1402d90de  movups  xmmword ptr [rbp+var_18.left], xmm0
0x1402d90e2  mov     rdi, rcx
0x1402d90e5  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1402d90ea  mov     r12d, 1
0x1402d90f0  cmp     qword ptr [rax+1E8h], 0
0x1402d90f8  jz      short loc_1402D9131
0x1402d90fa  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1402d90ff  mov     rcx, [rax+1E8h]
0x1402d9106  mov     rax, [rcx+8]
0x1402d910a  mov     rcx, [rax]
0x1402d910d  mov     eax, [rcx+40h]
0x1402d9110  test    r12b, al
0x1402d9113  jz      short loc_1402D9131
0x1402d9115  mov     dword ptr [rbp+var_50], 20000h
0x1402d911c  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1402d9123  mov     edx, dword ptr [rbp+var_50]
0x1402d9126  mov     r8d, 7C1h
0x1402d912c  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1402d9131  mov     rbx, [rdi+28h]
0x1402d9135  mov     r14, [rbx+88h]
0x1402d913c  test    r14, r14
0x1402d913f  jz      loc_1402D9686
0x1402d9145  test    byte ptr [rbx+1Fh], 10h
0x1402d9149  jz      loc_1402D9686
0x1402d914f  test    rsi, rsi
0x1402d9152  jz      short loc_1402D916A
0x1402d9154  mov     edx, 0A08h
0x1402d9159  mov     rcx, rdi
0x1402d915c  call    GetStyleWindow
0x1402d9161  test    rax, rax
0x1402d9164  jnz     loc_1402D9686
0x1402d916a  cmp     r14, r12
0x1402d916d  jbe     short loc_1402D91BE
0x1402d916f  call    cs:__imp_CreateEmptyRgn
0x1402d9176  nop     dword ptr [rax+rax+00h]
0x1402d917b  mov     rbx, rax
0x1402d917e  test    rax, rax
0x1402d9181  jz      short loc_1402D91B9
0x1402d9183  mov     rdx, [rdi+28h]
0x1402d9187  mov     r9d, 5
0x1402d918d  xor     r8d, r8d
0x1402d9190  mov     rcx, rax
0x1402d9193  mov     rdx, [rdx+88h]
0x1402d919a  call    cs:__imp_GreCombineRgn
0x1402d91a1  nop     dword ptr [rax+rax+00h]
0x1402d91a6  test    eax, eax
0x1402d91a8  jnz     short loc_1402D91E1
0x1402d91aa  mov     rcx, rbx
0x1402d91ad  call    cs:__imp_GreDeleteObject
0x1402d91b4  nop     dword ptr [rax+rax+00h]
0x1402d91b9  mov     rbx, r12
0x1402d91bc  jmp     short loc_1402D91E1
0x1402d91be  movups  xmm0, xmmword ptr [rbx+58h]
0x1402d91c2  lea     rcx, [rbp+var_18]
0x1402d91c6  movdqu  xmmword ptr [rbp+var_18.left], xmm0
0x1402d91cb  call    cs:__imp_GreCreateRectRgnIndirect
0x1402d91d2  nop     dword ptr [rax+rax+00h]
0x1402d91d7  test    rax, rax
0x1402d91da  mov     rbx, rax
0x1402d91dd  cmovz   rbx, r12
0x1402d91e1  test    rsi, rsi
0x1402d91e4  jz      short loc_1402D921C
0x1402d91e6  cmp     rbx, r12
0x1402d91e9  jz      short loc_1402D921C
0x1402d91eb  mov     r9d, r12d
0x1402d91ee  mov     r8, rsi
0x1402d91f1  mov     rdx, rbx
0x1402d91f4  mov     rcx, rbx
0x1402d91f7  call    cs:__imp_GreCombineRgn
0x1402d91fe  nop     dword ptr [rax+rax+00h]
0x1402d9203  cmp     eax, r12d
0x1402d9206  jnz     short loc_1402D921C
0x1402d9208  mov     rcx, rbx
0x1402d920b  call    cs:__imp_GreDeleteObject
0x1402d9212  nop     dword ptr [rax+rax+00h]
0x1402d9217  jmp     loc_1402D9686
0x1402d921c  mov     rdx, rdi
0x1402d921f  lea     rcx, [rbp+BugCheckParameter3]
0x1402d9223  call    ??0?$Win32HMThreadLockBase@UtagMENU@@$00$0A@@@QEAA@PEAUtagMENU@@@Z; Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(tagMENU *)
0x1402d9228  call    ?IsInsideUserApiHook@@YAHXZ; IsInsideUserApiHook(void)
0x1402d922d  test    eax, eax
0x1402d922f  jnz     short loc_1402D929C
0x1402d9231  mov     r8d, 50481h
0x1402d9237  mov     rdx, rbx
0x1402d923a  mov     rcx, rdi
0x1402d923d  call    cs:__imp__GetDCEx
0x1402d9244  nop     dword ptr [rax+rax+00h]
0x1402d9249  mov     rcx, [rdi+28h]
0x1402d924d  mov     rsi, rax
0x1402d9250  test    byte ptr [rcx+10h], 40h
0x1402d9254  jz      short loc_1402D927C
0x1402d9256  call    cs:__imp_W32GetUserSessionState
0x1402d925d  nop     dword ptr [rax+rax+00h]
0x1402d9262  mov     rcx, [rdi+10h]
0x1402d9266  mov     r8d, 2001h
0x1402d926c  mov     rdx, [rax+4A18h]
0x1402d9273  cmp     [rcx+1D0h], rdx
0x1402d927a  jz      short loc_1402D9282
0x1402d927c  mov     r8d, 2000h
0x1402d9282  mov     rdx, rsi; HDC
0x1402d9285  mov     rcx, rdi; struct tagWND *
0x1402d9288  call    xxxDrawWindowFrame
0x1402d928d  mov     rcx, rsi
0x1402d9290  call    cs:__imp__ReleaseDC
0x1402d9297  nop     dword ptr [rax+rax+00h]
0x1402d929c  mov     r8d, 485h
0x1402d92a2  mov     rdx, rbx
0x1402d92a5  mov     rcx, rdi
0x1402d92a8  call    xxxInternalInvalidate
0x1402d92ad  mov     rax, [rdi+28h]
0x1402d92b1  lea     rdx, [rbp+var_18]
0x1402d92b5  mov     r8d, r12d
0x1402d92b8  mov     rcx, rdi; struct tagWND *
0x1402d92bb  movups  xmm0, xmmword ptr [rax+58h]
0x1402d92bf  movdqu  xmmword ptr [rbp+var_18.left], xmm0
0x1402d92c4  call    xxxCalcClientRect
0x1402d92c9  call    cs:__imp_W32GetUserSessionState
0x1402d92d0  nop     dword ptr [rax+rax+00h]
0x1402d92d5  lea     rdx, [rbp+var_18]
0x1402d92d9  mov     rcx, [rax+0F6A0h]
0x1402d92e0  call    cs:__imp_SetRectRgnIndirect
0x1402d92e7  nop     dword ptr [rax+rax+00h]
0x1402d92ec  cmp     rbx, r12
0x1402d92ef  jbe     loc_1402D9403
0x1402d92f5  call    cs:__imp_W32GetUserSessionState
0x1402d92fc  nop     dword ptr [rax+rax+00h]
0x1402d9301  mov     r9d, r12d
0x1402d9304  mov     rdx, rbx
0x1402d9307  mov     rcx, rbx
0x1402d930a  mov     r8, [rax+0F6A0h]
0x1402d9311  call    cs:__imp_GreCombineRgn
0x1402d9318  nop     dword ptr [rax+rax+00h]
0x1402d931d  test    eax, eax
0x1402d931f  jz      loc_1402D93EF
0x1402d9325  cmp     eax, r12d
0x1402d9328  jnz     loc_1402D940C
0x1402d932e  mov     rcx, rbx
0x1402d9331  call    cs:__imp_GreDeleteObject
0x1402d9338  nop     dword ptr [rax+rax+00h]
0x1402d933d  xor     ebx, ebx
0x1402d933f  mov     rax, [rdi+28h]
0x1402d9343  mov     rdx, rbx
0x1402d9346  movzx   ecx, byte ptr [rax+1Fh]
0x1402d934a  mov     eax, ecx
0x1402d934c  and     eax, 4
0x1402d934f  shl     eax, 2
0x1402d9352  or      eax, 83h
0x1402d9357  mov     r8d, eax
0x1402d935a  or      r8d, 8
0x1402d935e  test    cl, 2
0x1402d9361  mov     rcx, rdi
0x1402d9364  cmovz   r8d, eax
0x1402d9368  call    cs:__imp__GetDCEx
0x1402d936f  nop     dword ptr [rax+rax+00h]
0x1402d9374  mov     rcx, rax; HDC
0x1402d9377  mov     edx, r12d
0x1402d937a  mov     r14, rax
0x1402d937d  call    GreWatchVisRgnChange
0x1402d9382  mov     r8, [rdi+28h]
0x1402d9386  movups  xmm0, xmmword ptr [r8+58h]
0x1402d938b  movups  xmmword ptr [rbp+var_18.left], xmm0
0x1402d938f  mov     ecx, [r8+58h]
0x1402d9393  mov     edx, [r8+5Ch]
0x1402d9397  neg     ecx
0x1402d9399  add     [rbp+var_18.right], ecx
0x1402d939c  neg     edx
0x1402d939e  add     [rbp+var_18.bottom], edx
0x1402d93a1  add     [rbp+var_18.top], edx
0x1402d93a4  movd    eax, xmm0
0x1402d93a8  add     eax, ecx
0x1402d93aa  mov     [rbp+var_18.left], eax
0x1402d93ad  mov     rax, [rdi+88h]
0x1402d93b4  mov     rcx, [rax+8]
0x1402d93b8  mov     rbx, [rcx+48h]
0x1402d93bc  test    rbx, rbx
0x1402d93bf  jz      loc_1402D953D
0x1402d93c5  cmp     rbx, 1Fh
0x1402d93c9  ja      loc_1402D9579
0x1402d93cf  call    cs:__imp_W32GetUserSessionState
0x1402d93d6  nop     dword ptr [rax+rax+00h]
0x1402d93db  mov     rcx, [rax+4CF8h]
0x1402d93e2  mov     rbx, [rcx+rbx*8+1250h]
0x1402d93ea  jmp     loc_1402D9579
0x1402d93ef  mov     rcx, rbx
0x1402d93f2  call    cs:__imp_GreDeleteObject
0x1402d93f9  nop     dword ptr [rax+rax+00h]
0x1402d93fe  mov     rbx, r12
0x1402d9401  jmp     short loc_1402D940C
0x1402d9403  test    rbx, rbx
0x1402d9406  jz      loc_1402D933F
0x1402d940c  mov     rcx, [rdi+28h]
0x1402d9410  test    byte ptr [rcx+1Fh], 2
0x1402d9414  jnz     loc_1402D933F
0x1402d941a  mov     rcx, [rcx+88h]
0x1402d9421  xorps   xmm0, xmm0
0x1402d9424  movups  [rbp+var_38], xmm0
0x1402d9428  cmp     rcx, r12
0x1402d942b  jz      short loc_1402D9441
0x1402d942d  lea     rdx, [rbp+var_18]
0x1402d9431  call    cs:__imp_GreGetRgnBox
0x1402d9438  nop     dword ptr [rax+rax+00h]
0x1402d943d  test    eax, eax
0x1402d943f  jnz     short loc_1402D944E
0x1402d9441  mov     rax, [rdi+28h]
0x1402d9445  movups  xmm0, xmmword ptr [rax+58h]
0x1402d9449  movdqu  xmmword ptr [rbp+var_18.left], xmm0
0x1402d944e  mov     rsi, [rdi+70h]
0x1402d9452  jmp     loc_1402D950A
0x1402d9457  mov     r8, [rsi+28h]
0x1402d945b  test    byte ptr [r8+1Fh], 10h
0x1402d9460  jz      loc_1402D9506
0x1402d9466  test    byte ptr [r8+14h], 4
0x1402d946b  jnz     short loc_1402D947B
0x1402d946d  cmp     qword ptr [r8+88h], 0
0x1402d9475  jnz     loc_1402D9506
0x1402d947b  add     r8, 58h ; 'X'
0x1402d947f  lea     rdx, [rbp+var_18]
0x1402d9483  lea     rcx, [rbp+var_38]
0x1402d9487  call    IntersectRect
0x1402d948c  test    eax, eax
0x1402d948e  jz      short loc_1402D9506
0x1402d9490  lea     rdx, [rbp+var_50]
0x1402d9494  mov     [rbp+var_50], rbx
0x1402d9498  mov     rcx, rsi
0x1402d949b  call    PhysicalToLogicalInPlaceRgn
0x1402d94a0  mov     r14d, eax
0x1402d94a3  call    cs:__imp_W32GetUserSessionState
0x1402d94aa  nop     dword ptr [rax+rax+00h]
0x1402d94af  cmp     qword ptr [rax], 0
0x1402d94b3  jz      short loc_1402D9518
0x1402d94b5  call    ?IS_USERCRIT_OWNED_AT_ALL@@YA_NXZ; IS_USERCRIT_OWNED_AT_ALL(void)
0x1402d94ba  test    al, al
0x1402d94bc  jz      short loc_1402D9518
0x1402d94be  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1402d94c5  nop     dword ptr [rax+rax+00h]
0x1402d94ca  mov     rdx, [rbp+var_50]
0x1402d94ce  mov     r8d, 485h
0x1402d94d4  mov     rcx, rsi
0x1402d94d7  mov     [rbp+var_40], rax
0x1402d94db  mov     [rbp+var_48], r12b
0x1402d94df  add     [rax+1Ch], r12d
0x1402d94e3  call    xxxInternalInvalidate
0x1402d94e8  lea     rcx, [rbp+var_48]; this
0x1402d94ec  call    ?Disarm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Disarm(void)
0x1402d94f1  test    r14d, r14d
0x1402d94f4  jz      short loc_1402D9506
0x1402d94f6  mov     rcx, [rbp+var_50]
0x1402d94fa  call    cs:__imp_GreDeleteObject
0x1402d9501  nop     dword ptr [rax+rax+00h]
0x1402d9506  mov     rsi, [rsi+58h]
0x1402d950a  test    rsi, rsi
0x1402d950d  jnz     loc_1402D9457
0x1402d9513  jmp     loc_1402D933F
0x1402d9518  xor     r9d, r9d; BugCheckParameter3
0x1402d951b  mov     [rsp+80h+BugCheckParameter4], 0; BugCheckParameter4
0x1402d9524  xor     r8d, r8d; BugCheckParameter2
0x1402d9527  mov     ecx, 164h; BugCheckCode
0x1402d952c  lea     edx, [r9+2Ah]; BugCheckParameter1
0x1402d9530  call    cs:__imp_KeBugCheckEx
0x1402d953d  test    [r8+12h], r12b
0x1402d9541  jz      short loc_1402D955F
0x1402d9543  call    cs:__imp_W32GetUserSessionState
0x1402d954a  nop     dword ptr [rax+rax+00h]
0x1402d954f  mov     rcx, [rax+4CF8h]
0x1402d9556  mov     rbx, [rcx+12D0h]
0x1402d955d  jmp     short loc_1402D9579
0x1402d955f  call    cs:__imp_W32GetUserSessionState
0x1402d9566  nop     dword ptr [rax+rax+00h]
0x1402d956b  mov     rcx, [rax+4CF8h]
0x1402d9572  mov     rbx, [rcx+1280h]
0x1402d9579  mov     edx, 10h
0x1402d957e  mov     rcx, rbx
0x1402d9581  call    cs:__imp_GreGetObjectOwner
0x1402d9588  nop     dword ptr [rax+rax+00h]
0x1402d958d  mov     esi, eax
0x1402d958f  test    eax, eax
0x1402d9591  jz      loc_1402D9619
0x1402d9597  call    cs:__imp_PsGetCurrentProcessId
0x1402d959e  nop     dword ptr [rax+rax+00h]
0x1402d95a3  cmp     esi, eax
0x1402d95a5  jz      short loc_1402D9619
0x1402d95a7  mov     rcx, rbx
0x1402d95aa  call    cs:__imp_GreGetBrushColor
0x1402d95b1  nop     dword ptr [rax+rax+00h]
0x1402d95b6  mov     ebx, eax
0x1402d95b8  cmp     eax, 0FFFFFFFFh
0x1402d95bb  jnz     short loc_1402D95E5
  ... truncated ...
```
