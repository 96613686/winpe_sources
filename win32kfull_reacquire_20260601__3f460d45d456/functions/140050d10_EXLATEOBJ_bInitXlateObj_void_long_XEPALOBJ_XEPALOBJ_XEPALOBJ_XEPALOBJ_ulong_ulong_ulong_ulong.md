# EXLATEOBJ::bInitXlateObj(void *,long,XEPALOBJ,XEPALOBJ,XEPALOBJ,XEPALOBJ,ulong,ulong,ulong,ulong)

- ea: `0x140050d10`
- end: `0x1400512a4`
- name: `?bInitXlateObj@EXLATEOBJ@@QEAAHPEAXJVXEPALOBJ@@111KKKK@Z`
- size: `1428`
- prototype: ``
- caller_count: `30`
- callee_count: `5`
- tags: ``

## callers

- `0x140015d84`
- `0x14004de48`
- `0x14004f5e4`
- `0x1400502c4`
- `0x1400571c0`
- `0x140058784`
- `0x1400746e0`
- `0x14008ad24`
- `0x14008d000`
- `0x1400fac84`
- `0x140111bbc`
- `0x140114688`
- `0x140117014`
- `0x140120ebc`
- `0x140147250`
- `0x140147b60`
- `0x140148400`
- `0x140148db0`
- `0x140149aa0`
- `0x14014a6c4`
- `0x14014b034`
- `0x1401611e0`
- `0x140161b5c`
- `0x1402102a0`
- `0x1402866c4`
- `0x140308388`
- `0x140309f24`
- `0x14030bf2c`
- `0x14030c54c`
- `0x1403113e8`

## callees

- `0x140050d10`
- `0x1400512b0`
- `0x140051df0`
- `0x140051efc`
- `0x140343080`

## import_xrefs

- `ntoskrnl!KeIsAttachedProcess` at `0x1400510dc`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400510dc`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140051254`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140051254`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140051246`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140051263`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140051246`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140051263`
- `ntoskrnl!PsGetCurrentProcess` at `0x140051237`
- `ntoskrnl!PsGetCurrentProcess` at `0x140051237`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x1400510f3`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x1400510f3`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140050e33`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140050fe1`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140051034`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140050e33`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140050fe1`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140051034`
- `win32kbase!PopThreadGuardedObject` at `0x140050ead`
- `win32kbase!PopThreadGuardedObject` at `0x140050ead`
- `win32kbase!FreeThreadBufferWithTag` at `0x140050e99`
- `win32kbase!FreeThreadBufferWithTag` at `0x140050e99`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x140051125`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x140051125`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x1400510c7`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x1400510c7`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140050e54`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140051058`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140050e54`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140051058`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x140051131`

## pseudocode

```c
__int64 __fastcall EXLATEOBJ::bInitXlateObj(
        Gre::Base *a1,
        __int64 a2,
        unsigned int a3,
        char *a4,
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
  char *v16; // r9
  char *v17; // rax
  int v18; // edx
  __int64 v19; // rax
  int v20; // edi
  __int64 v21; // rsi
  __int64 result; // rax
  Gre::Base *v23; // rcx
  struct Gre::Base::SESSION_GLOBALS *v24; // rdi
  __int64 i; // r8
  unsigned __int64 j; // rdx
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  unsigned int v30; // edi
  struct Gre::Base::SESSION_GLOBALS *v31; // rsi
  HSEMAPHORE v32; // r14
  __int64 v33; // r11
  char *v34; // rdx
  struct _KTHREAD *CurrentThread; // rsi
  __int64 ThreadWin32Thread; // rax
  _QWORD *v37; // rdx
  __int64 v39; // rcx
  __int64 v40; // rax
  _DWORD *v41; // r9
  int v42; // r10d
  int v43; // r10d
  __int64 v44; // rax
  __int64 CurrentProcess; // rax
  int ProcessSessionId; // edi
  __int64 CurrentThreadProcess; // rax
  __int64 v48; // [rsp+98h] [rbp+10h]
  HSEMAPHORE v49; // [rsp+A8h] [rbp+20h] BYREF

  v48 = a2;
  v11 = a7;
  v13 = a5;
  v15 = a1;
  if ( a4 )
  {
    if ( a5 )
    {
      v16 = (char *)*((_QWORD *)a4 + 15);
      v17 = a4;
      a1 = *(Gre::Base **)(a5 + 120);
      if ( v16 != a4 )
        v17 = v16;
      v18 = *((_DWORD *)v17 + 8);
      v19 = a5;
      if ( a1 != (Gre::Base *)a5 )
        v19 = *(_QWORD *)(a5 + 120);
      if ( v18 != *(_DWORD *)(v19 + 32) )
      {
        a2 = v48;
        goto LABEL_9;
      }
LABEL_37:
      *(_QWORD *)v15 = (char *)Gre::Base::Globals(a1) + 4664;
      return 1;
    }
    if ( (*((_DWORD *)a4 + 6) & 0x800) != 0 )
    {
      v28 = *(_QWORD *)(a7 + 80);
      if ( !v28 || v28 == *(_QWORD *)(a7 + 72) )
        goto LABEL_37;
    }
  }
  else
  {
    if ( !a5 )
      goto LABEL_37;
    if ( (*(_DWORD *)(a5 + 24) & 0x800) != 0 )
    {
      v29 = *(_QWORD *)(a7 + 80);
      if ( !v29 || v29 == *(_QWORD *)(a7 + 72) )
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
    v30 = *((_DWORD *)a4 + 14);
    v31 = Gre::Base::Globals(a1);
    v32 = (HSEMAPHORE)(*(_QWORD *)v31 + 312LL);
    v49 = v32;
    GreAcquireSemaphoreInternal(v32);
    GrepAcquireLockValidate<13>();
    v33 = a6;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= 8 )
      {
        *(_QWORD *)v15 = 0;
        if ( v32 )
        {
          EtwTraceGreLockReleaseSemaphore(L"Palette", v32);
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
                v37 = (_QWORD *)(*(_QWORD *)ThreadWin32Thread + 8LL);
                if ( *(_QWORD *)ThreadWin32Thread != -8 )
                {
                  if ( (*(_BYTE *)(*(_QWORD *)ThreadWin32Thread + 29LL))-- == 1 )
                    *v37 &= ~0x2000uLL;
                  if ( !*v37 )
                    GrepOnAllLocksReleased();
                }
              }
            }
          }
          ((void (__fastcall *)(HSEMAPHORE))GreReleaseSemaphoreExclusiveInternal)(v32);
        }
        v20 = 1;
        break;
      }
      v34 = a4;
      if ( *((char **)a4 + 15) != a4 )
        v34 = (char *)*((_QWORD *)a4 + 15);
      if ( *((_DWORD *)v31 + 8 * v30 + 1104) == *((_DWORD *)v34 + 8) )
      {
        v39 = v13;
        if ( *(_QWORD *)(v13 + 120) != v13 )
          v39 = *(_QWORD *)(v13 + 120);
        j = (unsigned __int64)v31 + 32 * v30;
        if ( *(_DWORD *)(j + 4420) == *(_DWORD *)(v39 + 32) )
        {
          v40 = v11;
          if ( *(_QWORD *)(v11 + 120) != v11 )
            v40 = *(_QWORD *)(v11 + 120);
          if ( *(_DWORD *)(j + 4428) == *(_DWORD *)(v40 + 32) )
          {
            v41 = *(_DWORD **)(j + 4408);
            *(_QWORD *)v15 = v41;
            v42 = v41[19];
            if ( (v42 & 0x6000) == a11 )
            {
              v43 = v42 & 0x100;
              if ( (v41[1] & 4) == 0 )
              {
                if ( !v43 )
                  goto LABEL_80;
LABEL_73:
                if ( a8 == v41[7] && a9 == v41[8] )
                  goto LABEL_80;
                goto LABEL_48;
              }
              if ( a10 == v41[6] )
              {
                v44 = v33;
                if ( *(_QWORD *)(v33 + 120) != v33 )
                  v44 = *(_QWORD *)(v33 + 120);
                if ( *(_DWORD *)(j + 4424) == *(_DWORD *)(v44 + 32) )
                {
LABEL_80:
                  _InterlockedIncrement((volatile signed __int32 *)(j + 4400));
                  *((_DWORD *)a4 + 14) = v30;
                  goto LABEL_31;
                }
              }
              if ( v43 )
                goto LABEL_73;
            }
          }
        }
      }
LABEL_48:
      v30 = ((_BYTE)v30 + 1) & 7;
    }
  }
LABEL_12:
  v21 = a6;
  result = CreateXlateObject(v48, a3, a4, v13, a6, v11, a8, a9, a10, a11);
  *(_QWORD *)v15 = result;
  if ( result )
  {
    if ( v20 && a4 && v13 && (*(_DWORD *)(result + 76) & 0x200) == 0 )
    {
      v24 = Gre::Base::Globals(v23);
      v49 = (HSEMAPHORE)(*(_QWORD *)v24 + 312LL);
      GreAcquireSemaphoreInternal(v49);
      GrepAcquireLockValidate<13>();
      for ( j = 0; (unsigned int)j < 8; j = (unsigned int)(j + 1) )
      {
        i = *((unsigned int *)v24 + 1164);
        v27 = *((_QWORD *)v24 + 4 * i + 551);
        if ( !v27 )
          goto LABEL_22;
        if ( !*((_DWORD *)v24 + 8 * i + 1100) )
        {
          FreeThreadBufferWithTag(v27);
LABEL_22:
          PopThreadGuardedObject(*(_QWORD *)v15 - 32LL);
          j = (unsigned __int64)a4;
          *((_DWORD *)v24 + 8 * *((unsigned int *)v24 + 1164) + 1100) = 1;
          *((_QWORD *)v24 + 4 * *((unsigned int *)v24 + 1164) + 551) = *(_QWORD *)v15;
          if ( *((char **)a4 + 15) != a4 )
            j = *((_QWORD *)a4 + 15);
          *((_DWORD *)v24 + 8 * *((unsigned int *)v24 + 1164) + 1104) = *(_DWORD *)(j + 32);
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
          *((_DWORD *)a4 + 14) = *((_DWORD *)v24 + 1164);
          *((_DWORD *)v24 + 1164) = ((unsigned __int8)*((_DWORD *)v24 + 1164) + 1) & 7;
          break;
        }
        *((_DWORD *)v24 + 1164) = ((_BYTE)i + 1) & 7;
      }
LABEL_31:
      SEMOBJ<13>::vUnlock(&v49, j, i);
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x140050d10  mov     [rsp+arg_8], rdx
0x140050d15  push    rbx
0x140050d16  push    rbp
0x140050d17  push    r12
0x140050d19  push    r13
0x140050d1b  push    r15
0x140050d1d  sub     rsp, 60h
0x140050d21  mov     r13, [rsp+88h+arg_30]
0x140050d29  mov     rbx, r9
0x140050d2c  mov     rbp, [rsp+88h+arg_20]
0x140050d34  mov     r15d, r8d
0x140050d37  mov     r12, rcx
0x140050d3a  test    r9, r9
0x140050d3d  jz      loc_14005100A
0x140050d43  test    rbp, rbp
0x140050d46  jz      loc_140050FC0
0x140050d4c  mov     r9, [r9+78h]
0x140050d50  mov     rax, rbx
0x140050d53  mov     rcx, [rbp+78h]
0x140050d57  cmp     r9, rbx
0x140050d5a  cmovnz  rax, r9
0x140050d5e  cmp     rcx, rbp
0x140050d61  mov     edx, [rax+20h]
0x140050d64  mov     rax, rbp
0x140050d67  cmovnz  rax, rcx
0x140050d6b  cmp     edx, [rax+20h]
0x140050d6e  jz      loc_140050FE1
0x140050d74  mov     rdx, [rsp+88h+arg_8]
0x140050d7c  mov     [rsp+88h+arg_0], rsi
0x140050d84  mov     [rsp+88h+var_30], rdi
0x140050d89  mov     [rsp+88h+var_38], r14
0x140050d8e  test    r15b, 7
0x140050d92  jnz     loc_140051294
0x140050d98  mov     edi, 1
0x140050d9d  test    rbx, rbx
0x140050da0  jz      short loc_140050DAB
0x140050da2  test    rbp, rbp
0x140050da5  jnz     loc_140051031
0x140050dab  mov     eax, [rsp+88h+arg_50]
0x140050db2  mov     r9, rbp
0x140050db5  mov     rsi, [rsp+88h+arg_28]
0x140050dbd  mov     r8, rbx
0x140050dc0  mov     rcx, [rsp+88h+arg_8]
0x140050dc8  mov     edx, r15d
0x140050dcb  mov     [rsp+88h+var_40], eax
0x140050dcf  mov     eax, [rsp+88h+arg_48]
0x140050dd6  mov     [rsp+88h+var_48], eax
0x140050dda  mov     eax, [rsp+88h+arg_40]
0x140050de1  mov     [rsp+88h+var_50], eax
0x140050de5  mov     eax, [rsp+88h+arg_38]
0x140050dec  mov     [rsp+88h+var_58], eax
0x140050df0  mov     [rsp+88h+var_60], r13
0x140050df5  mov     [rsp+88h+var_68], rsi
0x140050dfa  call    ?CreateXlateObject@@YAPEAVXLATE@@PEAXJVXEPALOBJ@@111KKKK@Z; CreateXlateObject(void *,long,XEPALOBJ,XEPALOBJ,XEPALOBJ,XEPALOBJ,ulong,ulong,ulong,ulong)
0x140050dff  mov     [r12], rax
0x140050e03  test    rax, rax
0x140050e06  jz      loc_140050FA0
0x140050e0c  test    edi, edi
0x140050e0e  jz      loc_140050F9B
0x140050e14  test    rbx, rbx
0x140050e17  jz      loc_140050F9B
0x140050e1d  test    rbp, rbp
0x140050e20  jz      loc_140050F9B
0x140050e26  test    dword ptr [rax+4Ch], 200h
0x140050e2d  jnz     loc_140050F9B
0x140050e33  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140050e3a  nop     dword ptr [rax+rax+00h]
0x140050e3f  mov     rdi, rax
0x140050e42  mov     rcx, [rax]
0x140050e45  add     rcx, 138h
0x140050e4c  mov     [rsp+88h+arg_18], rcx
0x140050e54  call    cs:__imp_?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x140050e5b  nop     dword ptr [rax+rax+00h]
0x140050e60  call    ??$GrepAcquireLockValidate@$0N@@@YAXXZ; GrepAcquireLockValidate<13>(void)
0x140050e65  xor     edx, edx
0x140050e67  cmp     edx, 8
0x140050e6a  jnb     loc_140050F8E
0x140050e70  mov     r8d, [rdi+1230h]
0x140050e77  mov     eax, r8d
0x140050e7a  shl     rax, 5
0x140050e7e  mov     rcx, [rax+rdi+1138h]
0x140050e86  test    rcx, rcx
0x140050e89  jz      short loc_140050EA5
0x140050e8b  cmp     dword ptr [rax+rdi+1130h], 0
0x140050e93  jnz     loc_140051223
0x140050e99  call    cs:__imp_FreeThreadBufferWithTag
0x140050ea0  nop     dword ptr [rax+rax+00h]
0x140050ea5  mov     rcx, [r12]
0x140050ea9  sub     rcx, 20h ; ' '
0x140050ead  call    cs:__imp_PopThreadGuardedObject
0x140050eb4  nop     dword ptr [rax+rax+00h]
0x140050eb9  mov     eax, [rdi+1230h]
0x140050ebf  mov     rdx, rbx
0x140050ec2  shl     rax, 5
0x140050ec6  mov     dword ptr [rax+rdi+1130h], 1
0x140050ed1  mov     ecx, [rdi+1230h]
0x140050ed7  mov     rax, [r12]
0x140050edb  shl     rcx, 5
0x140050edf  mov     [rcx+rdi+1138h], rax
0x140050ee7  mov     rax, [rbx+78h]
0x140050eeb  mov     ecx, [rdi+1230h]
0x140050ef1  cmp     rax, rbx
0x140050ef4  cmovnz  rdx, rax
0x140050ef8  add     rcx, 8Ah
0x140050eff  shl     rcx, 5
0x140050f03  mov     eax, [rdx+20h]
0x140050f06  mov     [rcx+rdi], eax
0x140050f09  mov     rax, [rbp+78h]
0x140050f0d  mov     ecx, [rdi+1230h]
0x140050f13  cmp     rax, rbp
0x140050f16  cmovnz  rbp, rax
0x140050f1a  shl     rcx, 5
0x140050f1e  mov     eax, [rbp+20h]
0x140050f21  mov     [rcx+rdi+1144h], eax
0x140050f28  mov     rax, [rsi+78h]
0x140050f2c  mov     ecx, [rdi+1230h]
0x140050f32  cmp     rax, rsi
0x140050f35  cmovnz  rsi, rax
0x140050f39  shl     rcx, 5
0x140050f3d  mov     eax, [rsi+20h]
0x140050f40  mov     [rcx+rdi+1148h], eax
0x140050f47  mov     rax, [r13+78h]
0x140050f4b  mov     ecx, [rdi+1230h]
0x140050f51  cmp     rax, r13
0x140050f54  cmovnz  r13, rax
0x140050f58  shl     rcx, 5
0x140050f5c  mov     eax, [r13+20h]
0x140050f60  mov     [rcx+rdi+114Ch], eax
0x140050f67  mov     eax, [rdi+1230h]
0x140050f6d  mov     rcx, [r12]
0x140050f71  mov     [rcx+24h], eax
0x140050f74  mov     eax, [rdi+1230h]
0x140050f7a  mov     [rbx+38h], eax
0x140050f7d  mov     eax, [rdi+1230h]
0x140050f83  inc     eax
0x140050f85  and     eax, 7
0x140050f88  mov     [rdi+1230h], eax
0x140050f8e  lea     rcx, [rsp+88h+arg_18]
0x140050f96  call    ?vUnlock@?$SEMOBJ@$0N@@@QEAAXXZ; SEMOBJ<13>::vUnlock(void)
0x140050f9b  mov     eax, 1
0x140050fa0  mov     rdi, [rsp+88h+var_30]
0x140050fa5  mov     rsi, [rsp+88h+arg_0]
0x140050fad  mov     r14, [rsp+88h+var_38]
0x140050fb2  add     rsp, 60h
0x140050fb6  pop     r15
0x140050fb8  pop     r13
0x140050fba  pop     r12
0x140050fbc  pop     rbp
0x140050fbd  pop     rbx
0x140050fbe  retn
0x140050fc0  test    dword ptr [r9+18h], 800h
0x140050fc8  jz      loc_140050D7C
0x140050fce  mov     rax, [r13+50h]
0x140050fd2  test    rax, rax
0x140050fd5  jz      short loc_140050FE1
0x140050fd7  cmp     rax, [r13+48h]
0x140050fdb  jnz     loc_140050D7C
0x140050fe1  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140050fe8  nop     dword ptr [rax+rax+00h]
0x140050fed  add     rax, 1238h
0x140050ff3  mov     [r12], rax
0x140050ff7  mov     eax, 1
0x140050ffc  add     rsp, 60h
0x140051000  pop     r15
0x140051002  pop     r13
0x140051004  pop     r12
0x140051006  pop     rbp
0x140051007  pop     rbx
0x140051008  retn
0x14005100a  test    rbp, rbp
0x14005100d  jz      short loc_140050FE1
0x14005100f  test    dword ptr [rbp+18h], 800h
0x140051016  jz      loc_140050D7C
0x14005101c  mov     rax, [r13+50h]
0x140051020  test    rax, rax
0x140051023  jz      short loc_140050FE1
0x140051025  cmp     rax, [r13+48h]
0x140051029  jnz     loc_140050D7C
0x14005102f  jmp     short loc_140050FE1
0x140051031  mov     edi, [rbx+38h]
0x140051034  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14005103b  nop     dword ptr [rax+rax+00h]
0x140051040  mov     rsi, rax
0x140051043  mov     r14, [rax]
0x140051046  add     r14, 138h
0x14005104d  mov     rcx, r14
0x140051050  mov     [rsp+88h+arg_18], r14
0x140051058  call    cs:__imp_?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x14005105f  nop     dword ptr [rax+rax+00h]
0x140051064  call    ??$GrepAcquireLockValidate@$0N@@@YAXXZ; GrepAcquireLockValidate<13>(void)
0x140051069  mov     r11, [rsp+88h+arg_28]
0x140051071  xor     r8d, r8d
0x140051074  cmp     r8d, 8
0x140051078  jnb     short loc_1400510AC
0x14005107a  mov     rax, [rbx+78h]
0x14005107e  mov     rdx, rbx
0x140051081  cmp     rax, rbx
0x140051084  mov     r9d, edi
0x140051087  cmovnz  rdx, rax
0x14005108b  lea     rcx, [r9+8Ah]
0x140051092  shl     rcx, 5
0x140051096  mov     eax, [rdx+20h]
0x140051099  cmp     [rcx+rsi], eax
0x14005109c  jz      loc_14005114A
0x1400510a2  inc     edi
0x1400510a4  and     edi, 7
0x1400510a7  inc     r8d
0x1400510aa  jmp     short loc_140051074
0x1400510ac  mov     qword ptr [r12], 0
0x1400510b4  test    r14, r14
0x1400510b7  jz      loc_140051140
0x1400510bd  mov     rdx, r14
0x1400510c0  lea     rcx, aPalette; "Palette"
0x1400510c7  call    cs:__imp_EtwTraceGreLockReleaseSemaphore
0x1400510ce  nop     dword ptr [rax+rax+00h]
0x1400510d3  mov     rsi, gs:188h
0x1400510dc  call    cs:__imp_KeIsAttachedProcess
0x1400510e3  nop     dword ptr [rax+rax+00h]
0x1400510e8  test    al, al
0x1400510ea  jnz     loc_140051237
0x1400510f0  mov     rcx, rsi
0x1400510f3  call    cs:__imp_PsGetThreadWin32Thread
0x1400510fa  nop     dword ptr [rax+rax+00h]
0x1400510ff  test    rax, rax
0x140051102  jz      short loc_140051131
0x140051104  mov     rdx, [rax]
0x140051107  test    rdx, rdx
0x14005110a  jz      short loc_140051131
0x14005110c  add     rdx, 8
0x140051110  jz      short loc_140051131
0x140051112  add     byte ptr [rdx+15h], 0FFh
0x140051116  jnz     short loc_14005111F
0x140051118  and     qword ptr [rdx], 0FFFFFFFFFFFFDFFFh
0x14005111f  cmp     qword ptr [rdx], 0
0x140051123  jnz     short loc_140051131
0x140051125  call    cs:__imp_?GrepOnAllLocksReleased@@YAXXZ; GrepOnAllLocksReleased(void)
0x14005112c  nop     dword ptr [rax+rax+00h]
0x140051131  mov     rax, cs:__imp_?GreReleaseSemaphoreExclusiveInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreExclusiveInternal(HSEMAPHORE__ *)
0x140051138  mov     rcx, r14
0x14005113b  call    _guard_dispatch_icall
0x140051140  mov     edi, 1
0x140051145  jmp     loc_140050DAB
0x14005114a  mov     rax, [rbp+78h]
0x14005114e  mov     rcx, rbp
0x140051151  cmp     rax, rbp
0x140051154  cmovnz  rcx, rax
0x140051158  shl     r9, 5
0x14005115c  mov     eax, [rcx+20h]
0x14005115f  lea     rdx, [r9+rsi]
0x140051163  cmp     [rdx+1144h], eax
0x140051169  jnz     loc_1400510A2
0x14005116f  mov     rcx, [r13+78h]
0x140051173  mov     rax, r13
0x140051176  cmp     rcx, r13
0x140051179  cmovnz  rax, rcx
0x14005117d  mov     eax, [rax+20h]
0x140051180  cmp     [rdx+114Ch], eax
0x140051186  jnz     loc_1400510A2
0x14005118c  mov     r9, [rdx+1138h]
0x140051193  mov     [r12], r9
0x140051197  mov     r10d, [r9+4Ch]
0x14005119b  mov     eax, r10d
0x14005119e  and     eax, 6000h
0x1400511a3  cmp     eax, [rsp+88h+arg_50]
0x1400511aa  jnz     loc_1400510A2
0x1400511b0  mov     eax, [r9+4]
0x1400511b4  and     r10d, 100h
0x1400511bb  test    al, 4
0x1400511bd  jz      loc_14005127C
0x1400511c3  mov     eax, [rsp+88h+arg_48]
0x1400511ca  cmp     eax, [r9+18h]
0x1400511ce  jnz     short loc_1400511E9
0x1400511d0  mov     rcx, [r11+78h]
0x1400511d4  mov     rax, r11
0x1400511d7  cmp     rcx, r11
0x1400511da  cmovnz  rax, rcx
0x1400511de  mov     eax, [rax+20h]
0x1400511e1  cmp     [rdx+1148h], eax
0x1400511e7  jz      short loc_140051214
0x1400511e9  test    r10d, r10d
0x1400511ec  jz      loc_1400510A2
0x1400511f2  mov     eax, [rsp+88h+arg_38]
0x1400511f9  cmp     eax, [r9+1Ch]
0x1400511fd  jnz     loc_1400510A2
0x140051203  mov     eax, [rsp+88h+arg_40]
0x14005120a  cmp     eax, [r9+20h]
0x14005120e  jnz     loc_1400510A2
0x140051214  lock inc dword ptr [rdx+1130h]
0x14005121b  mov     [rbx+38h], edi
0x14005121e  jmp     loc_140050F8E
0x140051223  lea     eax, [r8+1]
0x140051227  and     eax, 7
0x14005122a  mov     [rdi+1230h], eax
0x140051230  inc     edx
0x140051232  jmp     loc_140050E67
0x140051237  call    cs:__imp_PsGetCurrentProcess
0x14005123e  nop     dword ptr [rax+rax+00h]
0x140051243  mov     rcx, rax
0x140051246  call    cs:__imp_PsGetProcessSessionIdEx
0x14005124d  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
