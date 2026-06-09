# InputTransform::OnInput(tagWND *,unsigned __int64)

- ea: `0x140195d9c`
- end: `0x1401961c0`
- name: `?OnInput@InputTransform@@YAHPEAUtagWND@@_K@Z`
- size: `1060`
- prototype: `__int64 __fastcall(InputTransform *__hidden this, struct tagWND *, unsigned __int64)`
- caller_count: `4`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140144aa8`
- `0x140195b00`
- `0x140195b50`
- `0x1402b0e70`

## callees

- `0x140076e00`
- `0x1400b71ac`
- `0x1400bcaa0`
- `0x1401439c4`
- `0x140195d9c`
- `0x1401961d0`
- `0x1401962cc`
- `0x140196654`
- `0x140196a0c`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140195f10`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140195f10`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140195f1c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140195f1c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140195e9b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140195e9b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140195eac`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140195eac`
- `win32kbase!?gqpcAgeLimit@@3_KA` at `0x140195f96`
- `win32kbase!EtwTraceTransformAgeDecay` at `0x14019605c`
- `win32kbase!EtwTraceTransformAgeDecay` at `0x14019605c`
- `win32kbase!?UnlockAndRelease@CInputSink@@QEBA_NXZ` at `0x140195e47`
- `win32kbase!?UnlockAndRelease@CInputSink@@QEBA_NXZ` at `0x140195e47`
- `win32kbase!?LockForRead@CompositionInputObject@@QEBAJPEAPEBVCInputSink@@@Z` at `0x140195e1a`
- `win32kbase!?LockForRead@CompositionInputObject@@QEBAJPEAPEBVCInputSink@@@Z` at `0x140195e1a`
- `win32kbase!EtwTraceOnInputXformUpdate` at `0x140195ee7`
- `win32kbase!EtwTraceOnInputXformUpdate` at `0x140195f60`
- `win32kbase!EtwTraceOnInputXformUpdate` at `0x1401961a5`
- `win32kbase!EtwTraceOnInputXformUpdate` at `0x140195ee7`
- `win32kbase!EtwTraceOnInputXformUpdate` at `0x140195f60`
- `win32kbase!EtwTraceOnInputXformUpdate` at `0x1401961a5`
- `win32kbase!IsInputThread` at `0x140195dd5`
- `win32kbase!IsInputThread` at `0x140195dd5`
- `win32kbase!Win32AllocPoolZInit` at `0x140196097`
- `win32kbase!Win32AllocPoolZInit` at `0x140196097`
- `WIN32K!W32GetUserSessionState` at `0x140195f78`
- `WIN32K!W32GetUserSessionState` at `0x14019601e`
- `WIN32K!W32GetUserSessionState` at `0x14019613e`
- `WIN32K!W32GetUserSessionState` at `0x140195f78`
- `WIN32K!W32GetUserSessionState` at `0x14019601e`
- `WIN32K!W32GetUserSessionState` at `0x14019613e`

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
  __int64 v17; // rcx
  struct tagHID_PAGEONLY_REQUEST *i; // rcx
  struct tagHID_PAGEONLY_REQUEST *v19; // r13
  struct MOVESIZEDATA *v20; // rcx
  bool v21; // al
  __int64 v22; // rbx
  __int64 UserSessionState; // rax
  int v24; // r8d
  int v25; // edx
  __int64 v26; // rax
  __int64 v27; // rcx
  bool v28; // bl
  bool v29; // r14
  __int64 v30; // rax
  int v31; // r8d
  int v32; // edx
  int v33; // [rsp+20h] [rbp-F8h]
  int v34; // [rsp+28h] [rbp-F0h]
  int v35; // [rsp+30h] [rbp-E8h]
  int v36; // [rsp+38h] [rbp-E0h]
  _OWORD v37[8]; // [rsp+50h] [rbp-C8h] BYREF
  struct tagWND *v39; // [rsp+128h] [rbp+10h] BYREF
  const struct CInputSink *v40; // [rsp+130h] [rbp+18h] BYREF
  bool v41; // [rsp+138h] [rbp+20h]

  v39 = a2;
  v3 = this;
  if ( (unsigned __int8)IsInputThread()
    || (v16 = PtiCurrent(), v16 == *(struct tagTHREADINFO **)(W32GetUserSessionState(v17) + 18912)) )
  {
    v4 = *((_QWORD *)v3 + 34);
    if ( v4 )
    {
      v5 = *(CompositionInputObject **)(v4 + 96);
      if ( v5 )
      {
        v40 = 0;
        if ( (int)CompositionInputObject::LockForRead(v5, &v40) >= 0 )
        {
          v6 = *(_OWORD *)((char *)v40 + 88);
          v7 = *(_OWORD *)((char *)v40 + 104);
          v8 = *(_OWORD *)((char *)v40 + 120);
          v9 = *(_OWORD *)((char *)v40 + 136);
          CInputSink::UnlockAndRelease(v40);
          v37[0] = v6;
          v37[1] = v7;
          v37[2] = v8;
          v37[3] = v9;
          MagpRemoveTransformOutputMagFac(v37);
          InputTransform::StoreTransform(v3, (struct tagWND *)v37, (const struct tagINPUT_TRANSFORM *)&v39, v10);
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
      if ( gqpcAgeLimit )
      {
        for ( i = *v13;
              i != (struct tagHID_PAGEONLY_REQUEST *)v12 && a2 - v13[2] <= gqpcAgeLimit;
              i = *(struct tagHID_PAGEONLY_REQUEST **)i )
        {
          v13 = (struct tagHID_PAGEONLY_REQUEST **)i;
        }
        v19 = *v13;
        if ( *v13 != (struct tagHID_PAGEONLY_REQUEST *)v12 )
        {
          do
          {
            v20 = WPP_GLOBAL_Control;
            v21 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
               && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80000) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
            LOBYTE(v40) = v21;
            v41 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
            if ( v21 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v22 = *((_QWORD *)v19 + 2);
              LOBYTE(v20) = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
              UserSessionState = W32GetUserSessionState(v20);
              LOBYTE(v24) = v41;
              LOBYTE(v25) = (_BYTE)v40;
              WPP_RECORDER_AND_TRACE_SF_i(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v25,
                v24,
                *(_QWORD *)(UserSessionState + 69152),
                v33,
                v34,
                v35,
                v36,
                v22);
            }
            EtwTraceTransformAgeDecay(v11, *((_QWORD *)v19 + 2));
            FreeHidPageOnlyRequest(v19);
            *(_DWORD *)(v11 + 88) |= 2u;
            v19 = *v13;
          }
          while ( *v13 != (struct tagHID_PAGEONLY_REQUEST *)v12 );
          v3 = this;
        }
      }
      else
      {
        v28 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80000) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
        v29 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
        if ( v28 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v30 = W32GetUserSessionState(WPP_GLOBAL_Control);
          LOBYTE(v31) = v29;
          LOBYTE(v32) = v28;
          WPP_RECORDER_AND_TRACE_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v32,
            v31,
            *(_QWORD *)(v30 + 69152),
            4,
            20,
            11,
            (__int64)WPP_c988c3f99a353e6ffe2381605806c7a5_Traceguids);
        }
      }
    }
    if ( (*(_DWORD *)(v11 + 88) & 1) == 0 )
      goto LABEL_10;
    v26 = Win32AllocPoolZInit(88, 2020176725);
    if ( v26 )
    {
      *(_QWORD *)(v26 + 16) = a2;
      *(_OWORD *)(v26 + 24) = *(_OWORD *)(v11 + 24);
      *(_OWORD *)(v26 + 40) = *(_OWORD *)(v11 + 40);
      *(_OWORD *)(v26 + 56) = *(_OWORD *)(v11 + 56);
      *(_OWORD *)(v26 + 72) = *(_OWORD *)(v11 + 72);
      v27 = *v12;
      if ( *(__int64 **)(*v12 + 8) != v12 )
        __fastfail(3u);
      *(_QWORD *)v26 = v27;
      *(_QWORD *)(v26 + 8) = v12;
      *(_QWORD *)(v27 + 8) = v26;
      *v12 = v26;
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
0x140195d9c  mov     rax, rsp
0x140195d9f  mov     [rax+10h], rdx
0x140195da3  mov     [rax+8], rcx
0x140195da7  push    rbx
0x140195da8  push    rbp
0x140195da9  push    rsi
0x140195daa  push    rdi
0x140195dab  push    r12
0x140195dad  push    r13
0x140195daf  push    r14
0x140195db1  push    r15
0x140195db3  sub     rsp, 0D8h
0x140195dba  movaps  xmmword ptr [rax-58h], xmm6
0x140195dbe  mov     rbp, rdx
0x140195dc1  movaps  xmmword ptr [rax-68h], xmm7
0x140195dc5  mov     r15, rcx
0x140195dc8  movaps  xmmword ptr [rax-78h], xmm8
0x140195dcd  movaps  xmmword ptr [rax-88h], xmm9
0x140195dd5  call    cs:__imp_IsInputThread
0x140195ddc  nop     dword ptr [rax+rax+00h]
0x140195de1  test    al, al
0x140195de3  jz      loc_140195F70
0x140195de9  mov     rax, [r15+110h]
0x140195df0  test    rax, rax
0x140195df3  jz      loc_140195E8B
0x140195df9  mov     rcx, [rax+60h]
0x140195dfd  test    rcx, rcx
0x140195e00  jz      loc_140195E8B
0x140195e06  lea     rdx, [rsp+118h+arg_10]
0x140195e0e  mov     [rsp+118h+arg_10], 0
0x140195e1a  call    cs:__imp_?LockForRead@CompositionInputObject@@QEBAJPEAPEBVCInputSink@@@Z; CompositionInputObject::LockForRead(CInputSink const * *)
0x140195e21  nop     dword ptr [rax+rax+00h]
0x140195e26  test    eax, eax
0x140195e28  js      short loc_140195E8B
0x140195e2a  mov     rcx, [rsp+118h+arg_10]
0x140195e32  movups  xmm6, xmmword ptr [rcx+58h]
0x140195e36  movups  xmm7, xmmword ptr [rcx+68h]
0x140195e3a  movups  xmm8, xmmword ptr [rcx+78h]
0x140195e3f  movups  xmm9, xmmword ptr [rcx+88h]
0x140195e47  call    cs:__imp_?UnlockAndRelease@CInputSink@@QEBA_NXZ; CInputSink::UnlockAndRelease(void)
0x140195e4e  nop     dword ptr [rax+rax+00h]
0x140195e53  lea     rcx, [rsp+118h+var_C8]
0x140195e58  movaps  [rsp+118h+var_C8], xmm6
0x140195e5d  movaps  [rsp+118h+var_B8], xmm7
0x140195e62  movaps  [rsp+118h+var_A8], xmm8
0x140195e68  movaps  [rsp+118h+var_98], xmm9
0x140195e71  call    MagpRemoveTransformOutputMagFac
0x140195e76  lea     r8, [rsp+118h+arg_8]; struct tagINPUT_TRANSFORM *
0x140195e7e  mov     rcx, r15; this
0x140195e81  lea     rdx, [rsp+118h+var_C8]; struct tagWND *
0x140195e86  call    ?StoreTransform@InputTransform@@YAHPEAUtagWND@@PEBUtagINPUT_TRANSFORM@@PEA_K@Z; InputTransform::StoreTransform(tagWND *,tagINPUT_TRANSFORM const *,unsigned __int64 *)
0x140195e8b  mov     rdi, [r15+110h]
0x140195e92  test    rdi, rdi
0x140195e95  jz      loc_140195F57
0x140195e9b  call    cs:__imp_KeEnterCriticalRegion
0x140195ea2  nop     dword ptr [rax+rax+00h]
0x140195ea7  xor     edx, edx
0x140195ea9  mov     rcx, rdi
0x140195eac  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140195eb3  nop     dword ptr [rax+rax+00h]
0x140195eb8  lea     rsi, [rdi+8]
0x140195ebc  mov     r14, [rsi]
0x140195ebf  cmp     r14, rsi
0x140195ec2  jz      short loc_140195ECE
0x140195ec4  cmp     r14, [rsi+8]
0x140195ec8  jnz     loc_140195F96
0x140195ece  mov     eax, [rdi+58h]
0x140195ed1  mov     ebx, 1
0x140195ed6  test    bl, al
0x140195ed8  jnz     loc_14019608D
0x140195ede  mov     rcx, [r15]
0x140195ee1  mov     r8d, ebx
0x140195ee4  mov     rdx, rbp
0x140195ee7  call    cs:__imp_EtwTraceOnInputXformUpdate
0x140195eee  nop     dword ptr [rax+rax+00h]
0x140195ef3  mov     r8, [rdi+60h]; struct CompositionInputObject *
0x140195ef7  lea     rcx, [rdi+18h]
0x140195efb  mov     rdx, [r15]; HWND
0x140195efe  mov     [rsp+118h+var_F8], rcx; struct tagINPUT_TRANSFORM *
0x140195f03  mov     rcx, rbp; unsigned __int64
0x140195f06  call    ?OnInput@InputSink@InputTraceLogging@@SAX_KPEAUHWND__@@PEBUCompositionInputObject@@_NAEBUtagINPUT_TRANSFORM@@@Z; InputTraceLogging::InputSink::OnInput(unsigned __int64,HWND__ *,CompositionInputObject const *,bool,tagINPUT_TRANSFORM const &)
0x140195f0b  xor     edx, edx
0x140195f0d  mov     rcx, rdi
0x140195f10  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140195f17  nop     dword ptr [rax+rax+00h]
0x140195f1c  call    cs:__imp_KeLeaveCriticalRegion
0x140195f23  nop     dword ptr [rax+rax+00h]
0x140195f28  mov     eax, ebx
0x140195f2a  lea     r11, [rsp+118h+var_40]
0x140195f32  movaps  xmm6, xmmword ptr [r11-18h]
0x140195f37  movaps  xmm7, xmmword ptr [r11-28h]
0x140195f3c  movaps  xmm8, xmmword ptr [r11-38h]
0x140195f41  movaps  xmm9, xmmword ptr [r11-48h]
0x140195f46  mov     rsp, r11
0x140195f49  pop     r15
0x140195f4b  pop     r14
0x140195f4d  pop     r13
0x140195f4f  pop     r12
0x140195f51  pop     rdi
0x140195f52  pop     rsi
0x140195f53  pop     rbp
0x140195f54  pop     rbx
0x140195f55  retn
0x140195f57  mov     rcx, [r15]
0x140195f5a  xor     r8d, r8d
0x140195f5d  mov     rdx, rbp
0x140195f60  call    cs:__imp_EtwTraceOnInputXformUpdate
0x140195f67  nop     dword ptr [rax+rax+00h]
0x140195f6c  xor     eax, eax
0x140195f6e  jmp     short loc_140195F2A
0x140195f70  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140195f75  mov     rbx, rax
0x140195f78  call    cs:__imp_W32GetUserSessionState
0x140195f7f  nop     dword ptr [rax+rax+00h]
0x140195f84  cmp     rbx, [rax+49E0h]
0x140195f8b  jnz     loc_140195E8B
0x140195f91  jmp     loc_140195DE9
0x140195f96  mov     rax, cs:__imp_?gqpcAgeLimit@@3_KA; unsigned __int64 gqpcAgeLimit
0x140195f9d  mov     rdx, [rax]
0x140195fa0  test    rdx, rdx
0x140195fa3  jz      loc_1401960F7
0x140195fa9  mov     rcx, [r14]
0x140195fac  jmp     short loc_140195FC0
0x140195fae  mov     rax, rbp
0x140195fb1  sub     rax, [r14+10h]
0x140195fb5  cmp     rax, rdx
0x140195fb8  ja      short loc_140195FC5
0x140195fba  mov     r14, rcx
0x140195fbd  mov     rcx, [rcx]
0x140195fc0  cmp     rcx, rsi
0x140195fc3  jnz     short loc_140195FAE
0x140195fc5  mov     r13, [r14]
0x140195fc8  cmp     r13, rsi
0x140195fcb  jz      loc_140195ECE
0x140195fd1  lea     r12, WPP_GLOBAL_Control
0x140195fd8  lea     r15, WPP_RECORDER_INITIALIZED
0x140195fdf  mov     rcx, cs:WPP_GLOBAL_Control
0x140195fe6  cmp     rcx, r12
0x140195fe9  jz      short loc_140195FF8
0x140195feb  test    dword ptr [rcx+2Ch], 80000h
0x140195ff2  jnz     loc_14019618B
0x140195ff8  xor     al, al
0x140195ffa  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140196001  mov     byte ptr [rsp+118h+arg_10], al
0x140196008  setnz   cl
0x14019600b  mov     [rsp+118h+arg_18], cl
0x140196012  test    al, al
0x140196014  jnz     short loc_14019601A
0x140196016  test    cl, cl
0x140196018  jz      short loc_140196055
0x14019601a  mov     rbx, [r13+10h]
0x14019601e  call    cs:__imp_W32GetUserSessionState
0x140196025  nop     dword ptr [rax+rax+00h]
0x14019602a  mov     rcx, cs:WPP_GLOBAL_Control
0x140196031  mov     r8b, [rsp+118h+arg_18]
0x140196039  mov     dl, byte ptr [rsp+118h+arg_10]
0x140196040  mov     r9, [rax+10E20h]
0x140196047  mov     rcx, [rcx+18h]
0x14019604b  mov     [rsp+118h+var_D8], rbx
0x140196050  call    WPP_RECORDER_AND_TRACE_SF_i
0x140196055  mov     rdx, [r13+10h]
0x140196059  mov     rcx, rdi
0x14019605c  call    cs:__imp_EtwTraceTransformAgeDecay
0x140196063  nop     dword ptr [rax+rax+00h]
0x140196068  mov     rcx, r13; struct tagHID_PAGEONLY_REQUEST *
0x14019606b  call    ?FreeHidPageOnlyRequest@@YAXPEAUtagHID_PAGEONLY_REQUEST@@@Z; FreeHidPageOnlyRequest(tagHID_PAGEONLY_REQUEST *)
0x140196070  or      dword ptr [rdi+58h], 2
0x140196074  mov     r13, [r14]
0x140196077  cmp     r13, rsi
0x14019607a  jnz     loc_140195FDF
0x140196080  mov     r15, [rsp+118h+arg_0]
0x140196088  jmp     loc_140195ECE
0x14019608d  mov     edx, 78697355h
0x140196092  mov     ecx, 58h ; 'X'
0x140196097  call    cs:__imp_Win32AllocPoolZInit
0x14019609e  nop     dword ptr [rax+rax+00h]
0x1401960a3  test    rax, rax
0x1401960a6  jz      loc_14019619C
0x1401960ac  mov     [rax+10h], rbp
0x1401960b0  movups  xmm0, xmmword ptr [rdi+18h]
0x1401960b4  movups  xmmword ptr [rax+18h], xmm0
0x1401960b8  movups  xmm1, xmmword ptr [rdi+28h]
0x1401960bc  movups  xmmword ptr [rax+28h], xmm1
0x1401960c0  movups  xmm0, xmmword ptr [rdi+38h]
0x1401960c4  movups  xmmword ptr [rax+38h], xmm0
0x1401960c8  movups  xmm1, xmmword ptr [rdi+48h]
0x1401960cc  movups  xmmword ptr [rax+48h], xmm1
0x1401960d0  mov     rcx, [rsi]
0x1401960d3  cmp     [rcx+8], rsi
0x1401960d7  jz      short loc_1401960E0
0x1401960d9  mov     ecx, 3
0x1401960de  int     29h; Win8: RtlFailFast(ecx)
0x1401960e0  mov     [rax], rcx
0x1401960e3  mov     [rax+8], rsi
0x1401960e7  mov     [rcx+8], rax
0x1401960eb  mov     [rsi], rax
0x1401960ee  and     dword ptr [rdi+58h], 0FFFFFFFEh
0x1401960f2  jmp     loc_140195EDE
0x1401960f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1401960fe  lea     r12, WPP_GLOBAL_Control
0x140196105  cmp     rcx, r12
0x140196108  jz      short loc_14019611D
0x14019610a  test    dword ptr [rcx+2Ch], 80000h
0x140196111  jz      short loc_14019611D
0x140196113  cmp     byte ptr [rcx+29h], 4
0x140196117  jb      short loc_14019611D
0x140196119  mov     bl, 1
0x14019611b  jmp     short loc_14019611F
0x14019611d  xor     bl, bl
0x14019611f  lea     rax, WPP_RECORDER_INITIALIZED
0x140196126  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14019612d  setnz   r14b
0x140196131  test    bl, bl
0x140196133  jnz     short loc_14019613E
0x140196135  test    r14b, r14b
0x140196138  jz      loc_140195ECE
0x14019613e  call    cs:__imp_W32GetUserSessionState
0x140196145  nop     dword ptr [rax+rax+00h]
0x14019614a  mov     rcx, cs:WPP_GLOBAL_Control
0x140196151  mov     r8b, r14b
0x140196154  mov     dl, bl
0x140196156  mov     r9, [rax+10E20h]
0x14019615d  lea     rax, WPP_c988c3f99a353e6ffe2381605806c7a5_Traceguids
0x140196164  mov     rcx, [rcx+18h]
0x140196168  mov     [rsp+118h+var_E0], rax
0x14019616d  mov     [rsp+118h+var_E8], 0Bh
0x140196174  mov     [rsp+118h+var_F0], 14h
0x14019617c  mov     byte ptr [rsp+118h+var_F8], 4
0x140196181  call    WPP_RECORDER_AND_TRACE_SF_
0x140196186  jmp     loc_140195ECE
0x14019618b  cmp     byte ptr [rcx+29h], 4
0x14019618f  jb      loc_140195FF8
0x140196195  mov     al, 1
0x140196197  jmp     loc_140195FFA
0x14019619c  mov     rcx, [r15]
0x14019619f  xor     r8d, r8d
0x1401961a2  mov     rdx, rbp
0x1401961a5  call    cs:__imp_EtwTraceOnInputXformUpdate
0x1401961ac  nop     dword ptr [rax+rax+00h]
0x1401961b1  xor     edx, edx; unsigned int
0x1401961b3  mov     rcx, rdi; struct W32_PUSH_LOCK *
0x1401961b6  call    ?W32ReleasePushLockExclusiveEx@@YAXPEAVW32_PUSH_LOCK@@K@Z; W32ReleasePushLockExclusiveEx(W32_PUSH_LOCK *,ulong)
0x1401961bb  jmp     loc_140195F6C
```
