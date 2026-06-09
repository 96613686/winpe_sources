# EXLATEOBJ::bInitXlateObj(void *,long,XEPALOBJ,XEPALOBJ,XEPALOBJ,XEPALOBJ,ulong,ulong,ulong,ulong)

- ea: `0x14007a930`
- end: `0x14007aec4`
- name: `?bInitXlateObj@EXLATEOBJ@@QEAAHPEAXJVXEPALOBJ@@111KKKK@Z`
- size: `1428`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `30`
- callee_count: `5`
- tags: ``

## callers

- `0x14006bfc0`
- `0x14006dc00`
- `0x14007870c`
- `0x140079e6c`
- `0x14007be5c`
- `0x1400883f8`
- `0x14008da64`
- `0x1400f61f0`
- `0x1401269c8`
- `0x1401290b4`
- `0x1401347e0`
- `0x140137c54`
- `0x14013b990`
- `0x14013c30c`
- `0x1401566f0`
- `0x140156f80`
- `0x140157830`
- `0x140158120`
- `0x140158e20`
- `0x140159a48`
- `0x14015a3b8`
- `0x140165348`
- `0x140168564`
- `0x1401a0740`
- `0x14020fb30`
- `0x140306698`
- `0x14030823c`
- `0x14030a250`
- `0x14030a880`
- `0x14030f788`

## callees

- `0x14007a930`
- `0x14007aed0`
- `0x14007ba10`
- `0x14007bb1c`
- `0x1403420d0`

## import_xrefs

- `ntoskrnl!KeIsAttachedProcess` at `0x14007acfc`
- `ntoskrnl!KeIsAttachedProcess` at `0x14007acfc`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14007ae74`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14007ae74`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14007ae66`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14007ae83`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14007ae66`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14007ae83`
- `ntoskrnl!PsGetCurrentProcess` at `0x14007ae57`
- `ntoskrnl!PsGetCurrentProcess` at `0x14007ae57`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14007ad13`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14007ad13`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14007aa53`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14007ac01`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14007ac54`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14007aa53`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14007ac01`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14007ac54`
- `win32kbase!PopThreadGuardedObject` at `0x14007aacd`
- `win32kbase!PopThreadGuardedObject` at `0x14007aacd`
- `win32kbase!FreeThreadBufferWithTag` at `0x14007aab9`
- `win32kbase!FreeThreadBufferWithTag` at `0x14007aab9`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14007ad45`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14007ad45`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14007ace7`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14007ace7`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x14007aa74`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x14007ac78`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x14007aa74`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x14007ac78`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x14007ad51`

## pseudocode

```c
__int64 __fastcall EXLATEOBJ::bInitXlateObj(
        Gre::Base *a1,
        void *a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        int a8,
        int a9,
        int a10,
        int a11)
{
  __int64 v11; // r13
  __int64 v13; // rbp
  Gre::Base *v15; // r12
  __int64 v16; // r9
  __int64 v17; // rax
  int v18; // edx
  __int64 v19; // rax
  int v20; // edi
  __int64 v21; // rsi
  __int64 result; // rax
  Gre::Base *v23; // rcx
  struct Gre::Base::SESSION_GLOBALS *v24; // rdi
  unsigned int j; // edx
  unsigned int v26; // r8d
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rax
  unsigned int v32; // edi
  struct Gre::Base::SESSION_GLOBALS *v33; // rsi
  HSEMAPHORE v34; // r14
  __int64 v35; // r11
  unsigned int i; // r8d
  __int64 v37; // rdx
  struct _KTHREAD *CurrentThread; // rsi
  __int64 ThreadWin32Thread; // rax
  _QWORD *v40; // rdx
  __int64 v42; // rcx
  char *v43; // rdx
  __int64 v44; // rax
  _DWORD *v45; // r9
  int v46; // r10d
  int v47; // r10d
  __int64 v48; // rax
  __int64 CurrentProcess; // rax
  int ProcessSessionId; // edi
  __int64 CurrentThreadProcess; // rax
  void *v52; // [rsp+98h] [rbp+10h]
  HSEMAPHORE v53; // [rsp+A8h] [rbp+20h] BYREF

  v52 = a2;
  v11 = a7;
  v13 = a5;
  v15 = a1;
  if ( a4 )
  {
    if ( a5 )
    {
      v16 = *(_QWORD *)(a4 + 120);
      v17 = a4;
      a1 = *(Gre::Base **)(a5 + 120);
      if ( v16 != a4 )
        v17 = v16;
      v18 = *(_DWORD *)(v17 + 32);
      v19 = a5;
      if ( a1 != (Gre::Base *)a5 )
        v19 = *(_QWORD *)(a5 + 120);
      if ( v18 != *(_DWORD *)(v19 + 32) )
      {
        a2 = v52;
        goto LABEL_9;
      }
LABEL_37:
      *(_QWORD *)v15 = (char *)Gre::Base::Globals(a1) + 4664;
      return 1;
    }
    if ( (*(_DWORD *)(a4 + 24) & 0x800) != 0 )
    {
      v30 = *(_QWORD *)(a7 + 80);
      if ( !v30 || v30 == *(_QWORD *)(a7 + 72) )
        goto LABEL_37;
    }
  }
  else
  {
    if ( !a5 )
      goto LABEL_37;
    if ( (*(_DWORD *)(a5 + 24) & 0x800) != 0 )
    {
      v31 = *(_QWORD *)(a7 + 80);
      if ( !v31 || v31 == *(_QWORD *)(a7 + 72) )
        goto LABEL_37;
    }
  }
LABEL_9:
  if ( (a3 & 7) != 0 && a2 )
  {
    v20 = 0;
    goto LABEL_12;
  }
  v20 = 1;
  if ( a4 && a5 )
  {
    v32 = *(_DWORD *)(a4 + 56);
    v33 = Gre::Base::Globals(a1);
    v34 = (HSEMAPHORE)(*(_QWORD *)v33 + 312LL);
    v53 = v34;
    GreAcquireSemaphoreInternal(v34);
    GrepAcquireLockValidate<13>();
    v35 = a6;
    for ( i = 0; ; ++i )
    {
      if ( i >= 8 )
      {
        *(_QWORD *)v15 = 0;
        if ( v34 )
        {
          EtwTraceGreLockReleaseSemaphore(L"Palette", v34);
          CurrentThread = KeGetCurrentThread();
          if ( !(unsigned __int8)KeIsAttachedProcess()
            || (CurrentProcess = PsGetCurrentProcess(),
                ProcessSessionId = PsGetProcessSessionIdEx(CurrentProcess),
                CurrentThreadProcess = PsGetCurrentThreadProcess(),
                ProcessSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
          {
            ThreadWin32Thread = PsGetThreadWin32Thread(CurrentThread);
            if ( ThreadWin32Thread )
            {
              if ( *(_QWORD *)ThreadWin32Thread )
              {
                v40 = (_QWORD *)(*(_QWORD *)ThreadWin32Thread + 8LL);
                if ( *(_QWORD *)ThreadWin32Thread != -8 )
                {
                  if ( (*(_BYTE *)(*(_QWORD *)ThreadWin32Thread + 29LL))-- == 1 )
                    *v40 &= ~0x2000uLL;
                  if ( !*v40 )
                    GrepOnAllLocksReleased();
                }
              }
            }
          }
          ((void (__fastcall *)(HSEMAPHORE))GreReleaseSemaphoreExclusiveInternal)(v34);
        }
        v20 = 1;
        break;
      }
      v37 = a4;
      if ( *(_QWORD *)(a4 + 120) != a4 )
        v37 = *(_QWORD *)(a4 + 120);
      if ( *((_DWORD *)v33 + 8 * v32 + 1104) == *(_DWORD *)(v37 + 32) )
      {
        v42 = v13;
        if ( *(_QWORD *)(v13 + 120) != v13 )
          v42 = *(_QWORD *)(v13 + 120);
        v43 = (char *)v33 + 32 * v32;
        if ( *((_DWORD *)v43 + 1105) == *(_DWORD *)(v42 + 32) )
        {
          v44 = v11;
          if ( *(_QWORD *)(v11 + 120) != v11 )
            v44 = *(_QWORD *)(v11 + 120);
          if ( *((_DWORD *)v43 + 1107) == *(_DWORD *)(v44 + 32) )
          {
            v45 = (_DWORD *)*((_QWORD *)v43 + 551);
            *(_QWORD *)v15 = v45;
            v46 = v45[19];
            if ( (v46 & 0x6000) == a11 )
            {
              v47 = v46 & 0x100;
              if ( (v45[1] & 4) == 0 )
              {
                if ( !v47 )
                  goto LABEL_80;
LABEL_73:
                if ( a8 == v45[7] && a9 == v45[8] )
                  goto LABEL_80;
                goto LABEL_48;
              }
              if ( a10 == v45[6] )
              {
                v48 = v35;
                if ( *(_QWORD *)(v35 + 120) != v35 )
                  v48 = *(_QWORD *)(v35 + 120);
                if ( *((_DWORD *)v43 + 1106) == *(_DWORD *)(v48 + 32) )
                {
LABEL_80:
                  _InterlockedIncrement((volatile signed __int32 *)v43 + 1100);
                  *(_DWORD *)(a4 + 56) = v32;
                  goto LABEL_31;
                }
              }
              if ( v47 )
                goto LABEL_73;
            }
          }
        }
      }
LABEL_48:
      v32 = ((_BYTE)v32 + 1) & 7;
    }
  }
LABEL_12:
  v21 = a6;
  result = (__int64)CreateXlateObject(v52, a3, a4, v13, a6, v11, a8, a9, a10, a11);
  *(_QWORD *)v15 = result;
  if ( result )
  {
    if ( v20 && a4 && v13 && (*(_DWORD *)(result + 76) & 0x200) == 0 )
    {
      v24 = Gre::Base::Globals(v23);
      v53 = (HSEMAPHORE)(*(_QWORD *)v24 + 312LL);
      GreAcquireSemaphoreInternal(v53);
      GrepAcquireLockValidate<13>();
      for ( j = 0; j < 8; ++j )
      {
        v26 = *((_DWORD *)v24 + 1164);
        v27 = 32LL * v26;
        v28 = *(_QWORD *)((char *)v24 + v27 + 4408);
        if ( !v28 )
          goto LABEL_22;
        if ( !*(_DWORD *)((char *)v24 + v27 + 4400) )
        {
          FreeThreadBufferWithTag(v28);
LABEL_22:
          PopThreadGuardedObject(*(_QWORD *)v15 - 32LL);
          v29 = a4;
          *((_DWORD *)v24 + 8 * *((unsigned int *)v24 + 1164) + 1100) = 1;
          *((_QWORD *)v24 + 4 * *((unsigned int *)v24 + 1164) + 551) = *(_QWORD *)v15;
          if ( *(_QWORD *)(a4 + 120) != a4 )
            v29 = *(_QWORD *)(a4 + 120);
          *((_DWORD *)v24 + 8 * *((unsigned int *)v24 + 1164) + 1104) = *(_DWORD *)(v29 + 32);
          if ( *(_QWORD *)(v13 + 120) != v13 )
            v13 = *(_QWORD *)(v13 + 120);
          *((_DWORD *)v24 + 8 * *((unsigned int *)v24 + 1164) + 1105) = *(_DWORD *)(v13 + 32);
          if ( *(_QWORD *)(v21 + 120) != v21 )
            v21 = *(_QWORD *)(v21 + 120);
          *((_DWORD *)v24 + 8 * *((unsigned int *)v24 + 1164) + 1106) = *(_DWORD *)(v21 + 32);
          if ( *(_QWORD *)(v11 + 120) != v11 )
            v11 = *(_QWORD *)(v11 + 120);
          *((_DWORD *)v24 + 8 * *((unsigned int *)v24 + 1164) + 1107) = *(_DWORD *)(v11 + 32);
          *(_DWORD *)(*(_QWORD *)v15 + 36LL) = *((_DWORD *)v24 + 1164);
          *(_DWORD *)(a4 + 56) = *((_DWORD *)v24 + 1164);
          *((_DWORD *)v24 + 1164) = ((unsigned __int8)*((_DWORD *)v24 + 1164) + 1) & 7;
          break;
        }
        *((_DWORD *)v24 + 1164) = ((_BYTE)v26 + 1) & 7;
      }
LABEL_31:
      SEMOBJ<13>::vUnlock(&v53);
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x14007a930  mov     [rsp+arg_8], rdx
0x14007a935  push    rbx
0x14007a936  push    rbp
0x14007a937  push    r12
0x14007a939  push    r13
0x14007a93b  push    r15
0x14007a93d  sub     rsp, 60h
0x14007a941  mov     r13, [rsp+88h+arg_30]
0x14007a949  mov     rbx, r9
0x14007a94c  mov     rbp, [rsp+88h+arg_20]
0x14007a954  mov     r15d, r8d
0x14007a957  mov     r12, rcx
0x14007a95a  test    r9, r9
0x14007a95d  jz      loc_14007AC2A
0x14007a963  test    rbp, rbp
0x14007a966  jz      loc_14007ABE0
0x14007a96c  mov     r9, [r9+78h]
0x14007a970  mov     rax, rbx
0x14007a973  mov     rcx, [rbp+78h]
0x14007a977  cmp     r9, rbx
0x14007a97a  cmovnz  rax, r9
0x14007a97e  cmp     rcx, rbp
0x14007a981  mov     edx, [rax+20h]
0x14007a984  mov     rax, rbp
0x14007a987  cmovnz  rax, rcx
0x14007a98b  cmp     edx, [rax+20h]
0x14007a98e  jz      loc_14007AC01
0x14007a994  mov     rdx, [rsp+88h+arg_8]
0x14007a99c  mov     [rsp+88h+arg_0], rsi
0x14007a9a4  mov     [rsp+88h+var_30], rdi
0x14007a9a9  mov     [rsp+88h+var_38], r14
0x14007a9ae  test    r15b, 7
0x14007a9b2  jnz     loc_14007AEB4
0x14007a9b8  mov     edi, 1
0x14007a9bd  test    rbx, rbx
0x14007a9c0  jz      short loc_14007A9CB
0x14007a9c2  test    rbp, rbp
0x14007a9c5  jnz     loc_14007AC51
0x14007a9cb  mov     eax, [rsp+88h+arg_50]
0x14007a9d2  mov     r9, rbp
0x14007a9d5  mov     rsi, [rsp+88h+arg_28]
0x14007a9dd  mov     r8, rbx
0x14007a9e0  mov     rcx, [rsp+88h+arg_8]
0x14007a9e8  mov     edx, r15d
0x14007a9eb  mov     [rsp+88h+var_40], eax
0x14007a9ef  mov     eax, [rsp+88h+arg_48]
0x14007a9f6  mov     [rsp+88h+var_48], eax
0x14007a9fa  mov     eax, [rsp+88h+arg_40]
0x14007aa01  mov     [rsp+88h+var_50], eax
0x14007aa05  mov     eax, [rsp+88h+arg_38]
0x14007aa0c  mov     [rsp+88h+var_58], eax
0x14007aa10  mov     [rsp+88h+var_60], r13
0x14007aa15  mov     [rsp+88h+var_68], rsi
0x14007aa1a  call    ?CreateXlateObject@@YAPEAVXLATE@@PEAXJVXEPALOBJ@@111KKKK@Z; CreateXlateObject(void *,long,XEPALOBJ,XEPALOBJ,XEPALOBJ,XEPALOBJ,ulong,ulong,ulong,ulong)
0x14007aa1f  mov     [r12], rax
0x14007aa23  test    rax, rax
0x14007aa26  jz      loc_14007ABC0
0x14007aa2c  test    edi, edi
0x14007aa2e  jz      loc_14007ABBB
0x14007aa34  test    rbx, rbx
0x14007aa37  jz      loc_14007ABBB
0x14007aa3d  test    rbp, rbp
0x14007aa40  jz      loc_14007ABBB
0x14007aa46  test    dword ptr [rax+4Ch], 200h
0x14007aa4d  jnz     loc_14007ABBB
0x14007aa53  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14007aa5a  nop     dword ptr [rax+rax+00h]
0x14007aa5f  mov     rdi, rax
0x14007aa62  mov     rcx, [rax]
0x14007aa65  add     rcx, 138h
0x14007aa6c  mov     [rsp+88h+arg_18], rcx
0x14007aa74  call    cs:__imp_?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x14007aa7b  nop     dword ptr [rax+rax+00h]
0x14007aa80  call    ??$GrepAcquireLockValidate@$0N@@@YAXXZ; GrepAcquireLockValidate<13>(void)
0x14007aa85  xor     edx, edx
0x14007aa87  cmp     edx, 8
0x14007aa8a  jnb     loc_14007ABAE
0x14007aa90  mov     r8d, [rdi+1230h]
0x14007aa97  mov     eax, r8d
0x14007aa9a  shl     rax, 5
0x14007aa9e  mov     rcx, [rax+rdi+1138h]
0x14007aaa6  test    rcx, rcx
0x14007aaa9  jz      short loc_14007AAC5
0x14007aaab  cmp     dword ptr [rax+rdi+1130h], 0
0x14007aab3  jnz     loc_14007AE43
0x14007aab9  call    cs:__imp_FreeThreadBufferWithTag
0x14007aac0  nop     dword ptr [rax+rax+00h]
0x14007aac5  mov     rcx, [r12]
0x14007aac9  sub     rcx, 20h ; ' '
0x14007aacd  call    cs:__imp_PopThreadGuardedObject
0x14007aad4  nop     dword ptr [rax+rax+00h]
0x14007aad9  mov     eax, [rdi+1230h]
0x14007aadf  mov     rdx, rbx
0x14007aae2  shl     rax, 5
0x14007aae6  mov     dword ptr [rax+rdi+1130h], 1
0x14007aaf1  mov     ecx, [rdi+1230h]
0x14007aaf7  mov     rax, [r12]
0x14007aafb  shl     rcx, 5
0x14007aaff  mov     [rcx+rdi+1138h], rax
0x14007ab07  mov     rax, [rbx+78h]
0x14007ab0b  mov     ecx, [rdi+1230h]
0x14007ab11  cmp     rax, rbx
0x14007ab14  cmovnz  rdx, rax
0x14007ab18  add     rcx, 8Ah
0x14007ab1f  shl     rcx, 5
0x14007ab23  mov     eax, [rdx+20h]
0x14007ab26  mov     [rcx+rdi], eax
0x14007ab29  mov     rax, [rbp+78h]
0x14007ab2d  mov     ecx, [rdi+1230h]
0x14007ab33  cmp     rax, rbp
0x14007ab36  cmovnz  rbp, rax
0x14007ab3a  shl     rcx, 5
0x14007ab3e  mov     eax, [rbp+20h]
0x14007ab41  mov     [rcx+rdi+1144h], eax
0x14007ab48  mov     rax, [rsi+78h]
0x14007ab4c  mov     ecx, [rdi+1230h]
0x14007ab52  cmp     rax, rsi
0x14007ab55  cmovnz  rsi, rax
0x14007ab59  shl     rcx, 5
0x14007ab5d  mov     eax, [rsi+20h]
0x14007ab60  mov     [rcx+rdi+1148h], eax
0x14007ab67  mov     rax, [r13+78h]
0x14007ab6b  mov     ecx, [rdi+1230h]
0x14007ab71  cmp     rax, r13
0x14007ab74  cmovnz  r13, rax
0x14007ab78  shl     rcx, 5
0x14007ab7c  mov     eax, [r13+20h]
0x14007ab80  mov     [rcx+rdi+114Ch], eax
0x14007ab87  mov     eax, [rdi+1230h]
0x14007ab8d  mov     rcx, [r12]
0x14007ab91  mov     [rcx+24h], eax
0x14007ab94  mov     eax, [rdi+1230h]
0x14007ab9a  mov     [rbx+38h], eax
0x14007ab9d  mov     eax, [rdi+1230h]
0x14007aba3  inc     eax
0x14007aba5  and     eax, 7
0x14007aba8  mov     [rdi+1230h], eax
0x14007abae  lea     rcx, [rsp+88h+arg_18]
0x14007abb6  call    ?vUnlock@?$SEMOBJ@$0N@@@QEAAXXZ; SEMOBJ<13>::vUnlock(void)
0x14007abbb  mov     eax, 1
0x14007abc0  mov     rdi, [rsp+88h+var_30]
0x14007abc5  mov     rsi, [rsp+88h+arg_0]
0x14007abcd  mov     r14, [rsp+88h+var_38]
0x14007abd2  add     rsp, 60h
0x14007abd6  pop     r15
0x14007abd8  pop     r13
0x14007abda  pop     r12
0x14007abdc  pop     rbp
0x14007abdd  pop     rbx
0x14007abde  retn
0x14007abe0  test    dword ptr [r9+18h], 800h
0x14007abe8  jz      loc_14007A99C
0x14007abee  mov     rax, [r13+50h]
0x14007abf2  test    rax, rax
0x14007abf5  jz      short loc_14007AC01
0x14007abf7  cmp     rax, [r13+48h]
0x14007abfb  jnz     loc_14007A99C
0x14007ac01  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14007ac08  nop     dword ptr [rax+rax+00h]
0x14007ac0d  add     rax, 1238h
0x14007ac13  mov     [r12], rax
0x14007ac17  mov     eax, 1
0x14007ac1c  add     rsp, 60h
0x14007ac20  pop     r15
0x14007ac22  pop     r13
0x14007ac24  pop     r12
0x14007ac26  pop     rbp
0x14007ac27  pop     rbx
0x14007ac28  retn
0x14007ac2a  test    rbp, rbp
0x14007ac2d  jz      short loc_14007AC01
0x14007ac2f  test    dword ptr [rbp+18h], 800h
0x14007ac36  jz      loc_14007A99C
0x14007ac3c  mov     rax, [r13+50h]
0x14007ac40  test    rax, rax
0x14007ac43  jz      short loc_14007AC01
0x14007ac45  cmp     rax, [r13+48h]
0x14007ac49  jnz     loc_14007A99C
0x14007ac4f  jmp     short loc_14007AC01
0x14007ac51  mov     edi, [rbx+38h]
0x14007ac54  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14007ac5b  nop     dword ptr [rax+rax+00h]
0x14007ac60  mov     rsi, rax
0x14007ac63  mov     r14, [rax]
0x14007ac66  add     r14, 138h
0x14007ac6d  mov     rcx, r14
0x14007ac70  mov     [rsp+88h+arg_18], r14
0x14007ac78  call    cs:__imp_?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x14007ac7f  nop     dword ptr [rax+rax+00h]
0x14007ac84  call    ??$GrepAcquireLockValidate@$0N@@@YAXXZ; GrepAcquireLockValidate<13>(void)
0x14007ac89  mov     r11, [rsp+88h+arg_28]
0x14007ac91  xor     r8d, r8d
0x14007ac94  cmp     r8d, 8
0x14007ac98  jnb     short loc_14007ACCC
0x14007ac9a  mov     rax, [rbx+78h]
0x14007ac9e  mov     rdx, rbx
0x14007aca1  cmp     rax, rbx
0x14007aca4  mov     r9d, edi
0x14007aca7  cmovnz  rdx, rax
0x14007acab  lea     rcx, [r9+8Ah]
0x14007acb2  shl     rcx, 5
0x14007acb6  mov     eax, [rdx+20h]
0x14007acb9  cmp     [rcx+rsi], eax
0x14007acbc  jz      loc_14007AD6A
0x14007acc2  inc     edi
0x14007acc4  and     edi, 7
0x14007acc7  inc     r8d
0x14007acca  jmp     short loc_14007AC94
0x14007accc  mov     qword ptr [r12], 0
0x14007acd4  test    r14, r14
0x14007acd7  jz      loc_14007AD60
0x14007acdd  mov     rdx, r14
0x14007ace0  lea     rcx, aPalette; "Palette"
0x14007ace7  call    cs:__imp_EtwTraceGreLockReleaseSemaphore
0x14007acee  nop     dword ptr [rax+rax+00h]
0x14007acf3  mov     rsi, gs:188h
0x14007acfc  call    cs:__imp_KeIsAttachedProcess
0x14007ad03  nop     dword ptr [rax+rax+00h]
0x14007ad08  test    al, al
0x14007ad0a  jnz     loc_14007AE57
0x14007ad10  mov     rcx, rsi
0x14007ad13  call    cs:__imp_PsGetThreadWin32Thread
0x14007ad1a  nop     dword ptr [rax+rax+00h]
0x14007ad1f  test    rax, rax
0x14007ad22  jz      short loc_14007AD51
0x14007ad24  mov     rdx, [rax]
0x14007ad27  test    rdx, rdx
0x14007ad2a  jz      short loc_14007AD51
0x14007ad2c  add     rdx, 8
0x14007ad30  jz      short loc_14007AD51
0x14007ad32  add     byte ptr [rdx+15h], 0FFh
0x14007ad36  jnz     short loc_14007AD3F
0x14007ad38  and     qword ptr [rdx], 0FFFFFFFFFFFFDFFFh
0x14007ad3f  cmp     qword ptr [rdx], 0
0x14007ad43  jnz     short loc_14007AD51
0x14007ad45  call    cs:__imp_?GrepOnAllLocksReleased@@YAXXZ; GrepOnAllLocksReleased(void)
0x14007ad4c  nop     dword ptr [rax+rax+00h]
0x14007ad51  mov     rax, cs:__imp_?GreReleaseSemaphoreExclusiveInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreExclusiveInternal(HSEMAPHORE__ *)
0x14007ad58  mov     rcx, r14
0x14007ad5b  call    _guard_dispatch_icall
0x14007ad60  mov     edi, 1
0x14007ad65  jmp     loc_14007A9CB
0x14007ad6a  mov     rax, [rbp+78h]
0x14007ad6e  mov     rcx, rbp
0x14007ad71  cmp     rax, rbp
0x14007ad74  cmovnz  rcx, rax
0x14007ad78  shl     r9, 5
0x14007ad7c  mov     eax, [rcx+20h]
0x14007ad7f  lea     rdx, [r9+rsi]
0x14007ad83  cmp     [rdx+1144h], eax
0x14007ad89  jnz     loc_14007ACC2
0x14007ad8f  mov     rcx, [r13+78h]
0x14007ad93  mov     rax, r13
0x14007ad96  cmp     rcx, r13
0x14007ad99  cmovnz  rax, rcx
0x14007ad9d  mov     eax, [rax+20h]
0x14007ada0  cmp     [rdx+114Ch], eax
0x14007ada6  jnz     loc_14007ACC2
0x14007adac  mov     r9, [rdx+1138h]
0x14007adb3  mov     [r12], r9
0x14007adb7  mov     r10d, [r9+4Ch]
0x14007adbb  mov     eax, r10d
0x14007adbe  and     eax, 6000h
0x14007adc3  cmp     eax, [rsp+88h+arg_50]
0x14007adca  jnz     loc_14007ACC2
0x14007add0  mov     eax, [r9+4]
0x14007add4  and     r10d, 100h
0x14007addb  test    al, 4
0x14007addd  jz      loc_14007AE9C
0x14007ade3  mov     eax, [rsp+88h+arg_48]
0x14007adea  cmp     eax, [r9+18h]
0x14007adee  jnz     short loc_14007AE09
0x14007adf0  mov     rcx, [r11+78h]
0x14007adf4  mov     rax, r11
0x14007adf7  cmp     rcx, r11
0x14007adfa  cmovnz  rax, rcx
0x14007adfe  mov     eax, [rax+20h]
0x14007ae01  cmp     [rdx+1148h], eax
0x14007ae07  jz      short loc_14007AE34
0x14007ae09  test    r10d, r10d
0x14007ae0c  jz      loc_14007ACC2
0x14007ae12  mov     eax, [rsp+88h+arg_38]
0x14007ae19  cmp     eax, [r9+1Ch]
0x14007ae1d  jnz     loc_14007ACC2
0x14007ae23  mov     eax, [rsp+88h+arg_40]
0x14007ae2a  cmp     eax, [r9+20h]
0x14007ae2e  jnz     loc_14007ACC2
0x14007ae34  lock inc dword ptr [rdx+1130h]
0x14007ae3b  mov     [rbx+38h], edi
0x14007ae3e  jmp     loc_14007ABAE
0x14007ae43  lea     eax, [r8+1]
0x14007ae47  and     eax, 7
0x14007ae4a  mov     [rdi+1230h], eax
0x14007ae50  inc     edx
0x14007ae52  jmp     loc_14007AA87
0x14007ae57  call    cs:__imp_PsGetCurrentProcess
0x14007ae5e  nop     dword ptr [rax+rax+00h]
0x14007ae63  mov     rcx, rax
0x14007ae66  call    cs:__imp_PsGetProcessSessionIdEx
0x14007ae6d  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
