# InputTransform::OnInput(tagWND *,unsigned __int64)

- ea: `0x140198c8c`
- end: `0x1401990b0`
- name: `?OnInput@InputTransform@@YAHPEAUtagWND@@_K@Z`
- size: `1060`
- prototype: `__int64 __fastcall(InputTransform *__hidden this, struct tagWND *, unsigned __int64)`
- caller_count: `4`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14013aa68`
- `0x1401989f0`
- `0x140198a40`
- `0x1402b2820`

## callees

- `0x1400a3af0`
- `0x1400dd43c`
- `0x1400e2cb0`
- `0x140139984`
- `0x140198c8c`
- `0x1401990c0`
- `0x1401991bc`
- `0x140199544`
- `0x1401998fc`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140198e00`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140198e00`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140198e0c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140198e0c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140198d8b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140198d8b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140198d9c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140198d9c`
- `win32kbase!?gqpcAgeLimit@@3_KA` at `0x140198e86`
- `win32kbase!EtwTraceTransformAgeDecay` at `0x140198f4c`
- `win32kbase!EtwTraceTransformAgeDecay` at `0x140198f4c`
- `win32kbase!?UnlockAndRelease@CInputSink@@QEBA_NXZ` at `0x140198d37`
- `win32kbase!?UnlockAndRelease@CInputSink@@QEBA_NXZ` at `0x140198d37`
- `win32kbase!?LockForRead@CompositionInputObject@@QEBAJPEAPEBVCInputSink@@@Z` at `0x140198d0a`
- `win32kbase!?LockForRead@CompositionInputObject@@QEBAJPEAPEBVCInputSink@@@Z` at `0x140198d0a`
- `win32kbase!EtwTraceOnInputXformUpdate` at `0x140198dd7`
- `win32kbase!EtwTraceOnInputXformUpdate` at `0x140198e50`
- `win32kbase!EtwTraceOnInputXformUpdate` at `0x140199095`
- `win32kbase!EtwTraceOnInputXformUpdate` at `0x140198dd7`
- `win32kbase!EtwTraceOnInputXformUpdate` at `0x140198e50`
- `win32kbase!EtwTraceOnInputXformUpdate` at `0x140199095`
- `win32kbase!IsInputThread` at `0x140198cc5`
- `win32kbase!IsInputThread` at `0x140198cc5`
- `win32kbase!Win32AllocPoolZInit` at `0x140198f87`
- `win32kbase!Win32AllocPoolZInit` at `0x140198f87`
- `WIN32K!W32GetUserSessionState` at `0x140198e68`
- `WIN32K!W32GetUserSessionState` at `0x140198f0e`
- `WIN32K!W32GetUserSessionState` at `0x14019902e`
- `WIN32K!W32GetUserSessionState` at `0x140198e68`
- `WIN32K!W32GetUserSessionState` at `0x140198f0e`
- `WIN32K!W32GetUserSessionState` at `0x14019902e`

## pseudocode

```c
__int64 __fastcall InputTransform::OnInput(InputTransform *this, struct tagWND *a2)
{
  InputTransform *v3; // r15
  __int64 v4; // rax
  CompositionInputObject *v5; // rcx
  __int128 v6; // xmm6
  __int128 v7; // xmm7
  __int128 v8; // xmm8
  __int128 v9; // xmm9
  unsigned __int64 *v10; // r9
  __int64 v11; // rdi
  __int64 *v12; // rsi
  struct tagHID_PAGEONLY_REQUEST **v13; // r14
  bool v14; // r9
  struct tagTHREADINFO *v16; // rbx
  __int64 v17; // rdx
  __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  struct tagHID_PAGEONLY_REQUEST *i; // rcx
  struct tagHID_PAGEONLY_REQUEST *v21; // r13
  struct MOVESIZEDATA *v22; // rcx
  bool v23; // al
  __int64 v24; // rbx
  __int64 UserSessionState; // rax
  int v26; // r8d
  int v27; // edx
  __int64 v28; // rax
  __int64 v29; // rcx
  bool v30; // bl
  bool v31; // r14
  __int64 v32; // rax
  int v33; // r8d
  int v34; // edx
  int v35; // [rsp+20h] [rbp-F8h]
  int v36; // [rsp+28h] [rbp-F0h]
  int v37; // [rsp+30h] [rbp-E8h]
  int v38; // [rsp+38h] [rbp-E0h]
  _OWORD v39[8]; // [rsp+50h] [rbp-C8h] BYREF
  struct tagWND *v41; // [rsp+128h] [rbp+10h] BYREF
  const struct CInputSink *v42; // [rsp+130h] [rbp+18h] BYREF
  bool v43; // [rsp+138h] [rbp+20h]

  v41 = a2;
  v3 = this;
  if ( (unsigned __int8)IsInputThread()
    || (v16 = PtiCurrent(), v16 == *(struct tagTHREADINFO **)(W32GetUserSessionState(v18, v17) + 18912)) )
  {
    v4 = *((_QWORD *)v3 + 34);
    if ( v4 )
    {
      v5 = *(CompositionInputObject **)(v4 + 96);
      if ( v5 )
      {
        v42 = 0;
        if ( (int)CompositionInputObject::LockForRead(v5, &v42) >= 0 )
        {
          v6 = *(_OWORD *)((char *)v42 + 88);
          v7 = *(_OWORD *)((char *)v42 + 104);
          v8 = *(_OWORD *)((char *)v42 + 120);
          v9 = *(_OWORD *)((char *)v42 + 136);
          CInputSink::UnlockAndRelease(v42);
          v39[0] = v6;
          v39[1] = v7;
          v39[2] = v8;
          v39[3] = v9;
          MagpRemoveTransformOutputMagFac(v39);
          InputTransform::StoreTransform(v3, (struct tagWND *)v39, (const struct tagINPUT_TRANSFORM *)&v41, v10);
        }
      }
    }
  }
  v11 = *((_QWORD *)v3 + 34);
  if ( v11 )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(v11, 0);
    v12 = (__int64 *)(v11 + 8);
    v13 = *(struct tagHID_PAGEONLY_REQUEST ***)(v11 + 8);
    if ( v13 != (struct tagHID_PAGEONLY_REQUEST **)(v11 + 8) && v13 != *(struct tagHID_PAGEONLY_REQUEST ***)(v11 + 16) )
    {
      v19 = gqpcAgeLimit;
      if ( gqpcAgeLimit )
      {
        for ( i = *v13;
              i != (struct tagHID_PAGEONLY_REQUEST *)v12 && a2 - v13[2] <= gqpcAgeLimit;
              i = *(struct tagHID_PAGEONLY_REQUEST **)i )
        {
          v13 = (struct tagHID_PAGEONLY_REQUEST **)i;
        }
        v21 = *v13;
        if ( *v13 != (struct tagHID_PAGEONLY_REQUEST *)v12 )
        {
          do
          {
            v22 = WPP_GLOBAL_Control;
            v23 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
               && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80000) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
            LOBYTE(v42) = v23;
            v43 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
            if ( v23 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v24 = *((_QWORD *)v21 + 2);
              LOBYTE(v22) = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
              UserSessionState = W32GetUserSessionState(v22, v19);
              LOBYTE(v26) = v43;
              LOBYTE(v27) = (_BYTE)v42;
              WPP_RECORDER_AND_TRACE_SF_i(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v27,
                v26,
                *(_QWORD *)(UserSessionState + 69152),
                v35,
                v36,
                v37,
                v38,
                v24);
            }
            EtwTraceTransformAgeDecay(v11, *((_QWORD *)v21 + 2));
            FreeHidPageOnlyRequest(v21);
            *(_DWORD *)(v11 + 88) |= 2u;
            v21 = *v13;
          }
          while ( *v13 != (struct tagHID_PAGEONLY_REQUEST *)v12 );
          v3 = this;
        }
      }
      else
      {
        v30 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80000) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
        v31 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
        if ( v30 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v32 = W32GetUserSessionState(WPP_GLOBAL_Control, 0);
          LOBYTE(v33) = v31;
          LOBYTE(v34) = v30;
          WPP_RECORDER_AND_TRACE_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v34,
            v33,
            *(_QWORD *)(v32 + 69152),
            4,
            20,
            11,
            (__int64)WPP_c988c3f99a353e6ffe2381605806c7a5_Traceguids);
        }
      }
    }
    if ( (*(_DWORD *)(v11 + 88) & 1) == 0 )
      goto LABEL_10;
    v28 = Win32AllocPoolZInit(88, 2020176725);
    if ( v28 )
    {
      *(_QWORD *)(v28 + 16) = a2;
      *(_OWORD *)(v28 + 24) = *(_OWORD *)(v11 + 24);
      *(_OWORD *)(v28 + 40) = *(_OWORD *)(v11 + 40);
      *(_OWORD *)(v28 + 56) = *(_OWORD *)(v11 + 56);
      *(_OWORD *)(v28 + 72) = *(_OWORD *)(v11 + 72);
      v29 = *v12;
      if ( *(__int64 **)(*v12 + 8) != v12 )
        __fastfail(3u);
      *(_QWORD *)v28 = v29;
      *(_QWORD *)(v28 + 8) = v12;
      *(_QWORD *)(v29 + 8) = v28;
      *v12 = v28;
      *(_DWORD *)(v11 + 88) &= ~1u;
LABEL_10:
      EtwTraceOnInputXformUpdate(*(_QWORD *)v3, a2, 1);
      InputTraceLogging::InputSink::OnInput(
        (unsigned __int64)a2,
        *(HWND *)v3,
        *(const struct CompositionInputObject **)(v11 + 96),
        v14,
        (const struct tagINPUT_TRANSFORM *)(v11 + 24));
      ExReleasePushLockExclusiveEx(v11, 0);
      KeLeaveCriticalRegion();
      return 1;
    }
    EtwTraceOnInputXformUpdate(*(_QWORD *)v3, a2, 0);
    W32ReleasePushLockExclusiveEx((struct W32_PUSH_LOCK *)v11, 0);
  }
  else
  {
    EtwTraceOnInputXformUpdate(*(_QWORD *)v3, a2, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x140198c8c  mov     rax, rsp
0x140198c8f  mov     [rax+10h], rdx
0x140198c93  mov     [rax+8], rcx
0x140198c97  push    rbx
0x140198c98  push    rbp
0x140198c99  push    rsi
0x140198c9a  push    rdi
0x140198c9b  push    r12
0x140198c9d  push    r13
0x140198c9f  push    r14
0x140198ca1  push    r15
0x140198ca3  sub     rsp, 0D8h
0x140198caa  movaps  xmmword ptr [rax-58h], xmm6
0x140198cae  mov     rbp, rdx
0x140198cb1  movaps  xmmword ptr [rax-68h], xmm7
0x140198cb5  mov     r15, rcx
0x140198cb8  movaps  xmmword ptr [rax-78h], xmm8
0x140198cbd  movaps  xmmword ptr [rax-88h], xmm9
0x140198cc5  call    cs:__imp_IsInputThread
0x140198ccc  nop     dword ptr [rax+rax+00h]
0x140198cd1  test    al, al
0x140198cd3  jz      loc_140198E60
0x140198cd9  mov     rax, [r15+110h]
0x140198ce0  test    rax, rax
0x140198ce3  jz      loc_140198D7B
0x140198ce9  mov     rcx, [rax+60h]
0x140198ced  test    rcx, rcx
0x140198cf0  jz      loc_140198D7B
0x140198cf6  lea     rdx, [rsp+118h+arg_10]
0x140198cfe  mov     [rsp+118h+arg_10], 0
0x140198d0a  call    cs:__imp_?LockForRead@CompositionInputObject@@QEBAJPEAPEBVCInputSink@@@Z; CompositionInputObject::LockForRead(CInputSink const * *)
0x140198d11  nop     dword ptr [rax+rax+00h]
0x140198d16  test    eax, eax
0x140198d18  js      short loc_140198D7B
0x140198d1a  mov     rcx, [rsp+118h+arg_10]
0x140198d22  movups  xmm6, xmmword ptr [rcx+58h]
0x140198d26  movups  xmm7, xmmword ptr [rcx+68h]
0x140198d2a  movups  xmm8, xmmword ptr [rcx+78h]
0x140198d2f  movups  xmm9, xmmword ptr [rcx+88h]
0x140198d37  call    cs:__imp_?UnlockAndRelease@CInputSink@@QEBA_NXZ; CInputSink::UnlockAndRelease(void)
0x140198d3e  nop     dword ptr [rax+rax+00h]
0x140198d43  lea     rcx, [rsp+118h+var_C8]
0x140198d48  movaps  [rsp+118h+var_C8], xmm6
0x140198d4d  movaps  [rsp+118h+var_B8], xmm7
0x140198d52  movaps  [rsp+118h+var_A8], xmm8
0x140198d58  movaps  [rsp+118h+var_98], xmm9
0x140198d61  call    MagpRemoveTransformOutputMagFac
0x140198d66  lea     r8, [rsp+118h+arg_8]; struct tagINPUT_TRANSFORM *
0x140198d6e  mov     rcx, r15; this
0x140198d71  lea     rdx, [rsp+118h+var_C8]; struct tagWND *
0x140198d76  call    ?StoreTransform@InputTransform@@YAHPEAUtagWND@@PEBUtagINPUT_TRANSFORM@@PEA_K@Z; InputTransform::StoreTransform(tagWND *,tagINPUT_TRANSFORM const *,unsigned __int64 *)
0x140198d7b  mov     rdi, [r15+110h]
0x140198d82  test    rdi, rdi
0x140198d85  jz      loc_140198E47
0x140198d8b  call    cs:__imp_KeEnterCriticalRegion
0x140198d92  nop     dword ptr [rax+rax+00h]
0x140198d97  xor     edx, edx
0x140198d99  mov     rcx, rdi
0x140198d9c  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140198da3  nop     dword ptr [rax+rax+00h]
0x140198da8  lea     rsi, [rdi+8]
0x140198dac  mov     r14, [rsi]
0x140198daf  cmp     r14, rsi
0x140198db2  jz      short loc_140198DBE
0x140198db4  cmp     r14, [rsi+8]
0x140198db8  jnz     loc_140198E86
0x140198dbe  mov     eax, [rdi+58h]
0x140198dc1  mov     ebx, 1
0x140198dc6  test    bl, al
0x140198dc8  jnz     loc_140198F7D
0x140198dce  mov     rcx, [r15]
0x140198dd1  mov     r8d, ebx
0x140198dd4  mov     rdx, rbp
0x140198dd7  call    cs:__imp_EtwTraceOnInputXformUpdate
0x140198dde  nop     dword ptr [rax+rax+00h]
0x140198de3  mov     r8, [rdi+60h]; struct CompositionInputObject *
0x140198de7  lea     rcx, [rdi+18h]
0x140198deb  mov     rdx, [r15]; HWND
0x140198dee  mov     [rsp+118h+var_F8], rcx; struct tagINPUT_TRANSFORM *
0x140198df3  mov     rcx, rbp; unsigned __int64
0x140198df6  call    ?OnInput@InputSink@InputTraceLogging@@SAX_KPEAUHWND__@@PEBUCompositionInputObject@@_NAEBUtagINPUT_TRANSFORM@@@Z; InputTraceLogging::InputSink::OnInput(unsigned __int64,HWND__ *,CompositionInputObject const *,bool,tagINPUT_TRANSFORM const &)
0x140198dfb  xor     edx, edx
0x140198dfd  mov     rcx, rdi
0x140198e00  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140198e07  nop     dword ptr [rax+rax+00h]
0x140198e0c  call    cs:__imp_KeLeaveCriticalRegion
0x140198e13  nop     dword ptr [rax+rax+00h]
0x140198e18  mov     eax, ebx
0x140198e1a  lea     r11, [rsp+118h+var_40]
0x140198e22  movaps  xmm6, xmmword ptr [r11-18h]
0x140198e27  movaps  xmm7, xmmword ptr [r11-28h]
0x140198e2c  movaps  xmm8, xmmword ptr [r11-38h]
0x140198e31  movaps  xmm9, xmmword ptr [r11-48h]
0x140198e36  mov     rsp, r11
0x140198e39  pop     r15
0x140198e3b  pop     r14
0x140198e3d  pop     r13
0x140198e3f  pop     r12
0x140198e41  pop     rdi
0x140198e42  pop     rsi
0x140198e43  pop     rbp
0x140198e44  pop     rbx
0x140198e45  retn
0x140198e47  mov     rcx, [r15]
0x140198e4a  xor     r8d, r8d
0x140198e4d  mov     rdx, rbp
0x140198e50  call    cs:__imp_EtwTraceOnInputXformUpdate
0x140198e57  nop     dword ptr [rax+rax+00h]
0x140198e5c  xor     eax, eax
0x140198e5e  jmp     short loc_140198E1A
0x140198e60  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140198e65  mov     rbx, rax
0x140198e68  call    cs:__imp_W32GetUserSessionState
0x140198e6f  nop     dword ptr [rax+rax+00h]
0x140198e74  cmp     rbx, [rax+49E0h]
0x140198e7b  jnz     loc_140198D7B
0x140198e81  jmp     loc_140198CD9
0x140198e86  mov     rax, cs:__imp_?gqpcAgeLimit@@3_KA; unsigned __int64 gqpcAgeLimit
0x140198e8d  mov     rdx, [rax]
0x140198e90  test    rdx, rdx
0x140198e93  jz      loc_140198FE7
0x140198e99  mov     rcx, [r14]
0x140198e9c  jmp     short loc_140198EB0
0x140198e9e  mov     rax, rbp
0x140198ea1  sub     rax, [r14+10h]
0x140198ea5  cmp     rax, rdx
0x140198ea8  ja      short loc_140198EB5
0x140198eaa  mov     r14, rcx
0x140198ead  mov     rcx, [rcx]
0x140198eb0  cmp     rcx, rsi
0x140198eb3  jnz     short loc_140198E9E
0x140198eb5  mov     r13, [r14]
0x140198eb8  cmp     r13, rsi
0x140198ebb  jz      loc_140198DBE
0x140198ec1  lea     r12, WPP_GLOBAL_Control
0x140198ec8  lea     r15, WPP_RECORDER_INITIALIZED
0x140198ecf  mov     rcx, cs:WPP_GLOBAL_Control
0x140198ed6  cmp     rcx, r12
0x140198ed9  jz      short loc_140198EE8
0x140198edb  test    dword ptr [rcx+2Ch], 80000h
0x140198ee2  jnz     loc_14019907B
0x140198ee8  xor     al, al
0x140198eea  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140198ef1  mov     byte ptr [rsp+118h+arg_10], al
0x140198ef8  setnz   cl
0x140198efb  mov     [rsp+118h+arg_18], cl
0x140198f02  test    al, al
0x140198f04  jnz     short loc_140198F0A
0x140198f06  test    cl, cl
0x140198f08  jz      short loc_140198F45
0x140198f0a  mov     rbx, [r13+10h]
0x140198f0e  call    cs:__imp_W32GetUserSessionState
0x140198f15  nop     dword ptr [rax+rax+00h]
0x140198f1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140198f21  mov     r8b, [rsp+118h+arg_18]
0x140198f29  mov     dl, byte ptr [rsp+118h+arg_10]
0x140198f30  mov     r9, [rax+10E20h]
0x140198f37  mov     rcx, [rcx+18h]
0x140198f3b  mov     [rsp+118h+var_D8], rbx
0x140198f40  call    WPP_RECORDER_AND_TRACE_SF_i
0x140198f45  mov     rdx, [r13+10h]
0x140198f49  mov     rcx, rdi
0x140198f4c  call    cs:__imp_EtwTraceTransformAgeDecay
0x140198f53  nop     dword ptr [rax+rax+00h]
0x140198f58  mov     rcx, r13; struct tagHID_PAGEONLY_REQUEST *
0x140198f5b  call    ?FreeHidPageOnlyRequest@@YAXPEAUtagHID_PAGEONLY_REQUEST@@@Z; FreeHidPageOnlyRequest(tagHID_PAGEONLY_REQUEST *)
0x140198f60  or      dword ptr [rdi+58h], 2
0x140198f64  mov     r13, [r14]
0x140198f67  cmp     r13, rsi
0x140198f6a  jnz     loc_140198ECF
0x140198f70  mov     r15, [rsp+118h+arg_0]
0x140198f78  jmp     loc_140198DBE
0x140198f7d  mov     edx, 78697355h
0x140198f82  mov     ecx, 58h ; 'X'
0x140198f87  call    cs:__imp_Win32AllocPoolZInit
0x140198f8e  nop     dword ptr [rax+rax+00h]
0x140198f93  test    rax, rax
0x140198f96  jz      loc_14019908C
0x140198f9c  mov     [rax+10h], rbp
0x140198fa0  movups  xmm0, xmmword ptr [rdi+18h]
0x140198fa4  movups  xmmword ptr [rax+18h], xmm0
0x140198fa8  movups  xmm1, xmmword ptr [rdi+28h]
0x140198fac  movups  xmmword ptr [rax+28h], xmm1
0x140198fb0  movups  xmm0, xmmword ptr [rdi+38h]
0x140198fb4  movups  xmmword ptr [rax+38h], xmm0
0x140198fb8  movups  xmm1, xmmword ptr [rdi+48h]
0x140198fbc  movups  xmmword ptr [rax+48h], xmm1
0x140198fc0  mov     rcx, [rsi]
0x140198fc3  cmp     [rcx+8], rsi
0x140198fc7  jz      short loc_140198FD0
0x140198fc9  mov     ecx, 3
0x140198fce  int     29h; Win8: RtlFailFast(ecx)
0x140198fd0  mov     [rax], rcx
0x140198fd3  mov     [rax+8], rsi
0x140198fd7  mov     [rcx+8], rax
0x140198fdb  mov     [rsi], rax
0x140198fde  and     dword ptr [rdi+58h], 0FFFFFFFEh
0x140198fe2  jmp     loc_140198DCE
0x140198fe7  mov     rcx, cs:WPP_GLOBAL_Control
0x140198fee  lea     r12, WPP_GLOBAL_Control
0x140198ff5  cmp     rcx, r12
0x140198ff8  jz      short loc_14019900D
0x140198ffa  test    dword ptr [rcx+2Ch], 80000h
0x140199001  jz      short loc_14019900D
0x140199003  cmp     byte ptr [rcx+29h], 4
0x140199007  jb      short loc_14019900D
0x140199009  mov     bl, 1
0x14019900b  jmp     short loc_14019900F
0x14019900d  xor     bl, bl
0x14019900f  lea     rax, WPP_RECORDER_INITIALIZED
0x140199016  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14019901d  setnz   r14b
0x140199021  test    bl, bl
0x140199023  jnz     short loc_14019902E
0x140199025  test    r14b, r14b
0x140199028  jz      loc_140198DBE
0x14019902e  call    cs:__imp_W32GetUserSessionState
0x140199035  nop     dword ptr [rax+rax+00h]
0x14019903a  mov     rcx, cs:WPP_GLOBAL_Control
0x140199041  mov     r8b, r14b
0x140199044  mov     dl, bl
0x140199046  mov     r9, [rax+10E20h]
0x14019904d  lea     rax, WPP_c988c3f99a353e6ffe2381605806c7a5_Traceguids
0x140199054  mov     rcx, [rcx+18h]
0x140199058  mov     [rsp+118h+var_E0], rax
0x14019905d  mov     [rsp+118h+var_E8], 0Bh
0x140199064  mov     [rsp+118h+var_F0], 14h
0x14019906c  mov     byte ptr [rsp+118h+var_F8], 4
0x140199071  call    WPP_RECORDER_AND_TRACE_SF_
0x140199076  jmp     loc_140198DBE
0x14019907b  cmp     byte ptr [rcx+29h], 4
0x14019907f  jb      loc_140198EE8
0x140199085  mov     al, 1
0x140199087  jmp     loc_140198EEA
0x14019908c  mov     rcx, [r15]
0x14019908f  xor     r8d, r8d
0x140199092  mov     rdx, rbp
0x140199095  call    cs:__imp_EtwTraceOnInputXformUpdate
0x14019909c  nop     dword ptr [rax+rax+00h]
0x1401990a1  xor     edx, edx; unsigned int
0x1401990a3  mov     rcx, rdi; struct W32_PUSH_LOCK *
0x1401990a6  call    ?W32ReleasePushLockExclusiveEx@@YAXPEAVW32_PUSH_LOCK@@K@Z; W32ReleasePushLockExclusiveEx(W32_PUSH_LOCK *,ulong)
0x1401990ab  jmp     loc_140198E5C
```
