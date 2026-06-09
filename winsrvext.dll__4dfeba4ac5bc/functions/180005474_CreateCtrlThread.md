# CreateCtrlThread

- ea: `0x180005474`
- end: `0x180005875`
- name: `CreateCtrlThread`
- size: `1025`
- prototype: `__int64 __fastcall(unsigned int *, HWND, char, unsigned int, char, int ProcessInformation)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180007eb0`

## callees

- `0x180005474`
- `0x180006d88`
- `0x180006f80`
- `0x1800070ac`
- `0x180007374`
- `0x180008c10`
- `0x18000b9a8`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x1800054e0`
- `ntdll!NtQueryInformationProcess` at `0x1800054e0`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800056e2`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800056e2`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800056ce`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800056ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057d2`
- `BASESRV!BaseGetProcessCrtlRoutine` at `0x1800054f3`
- `BASESRV!BaseGetProcessCrtlRoutine` at `0x1800054f3`
- `CSRSRV!CsrUnlockProcess` at `0x18000582d`
- `CSRSRV!CsrUnlockProcess` at `0x18000582d`
- `CSRSRV!CsrLockProcessByClientId` at `0x180005803`
- `CSRSRV!CsrLockProcessByClientId` at `0x180005803`
- `win32u!NtUserSetInformationThread` at `0x180005645`
- `win32u!NtUserSetInformationThread` at `0x18000568f`
- `win32u!NtUserSetInformationThread` at `0x18000576c`
- `win32u!NtUserSetInformationThread` at `0x1800057b6`
- `win32u!NtUserSetInformationThread` at `0x180005645`
- `win32u!NtUserSetInformationThread` at `0x18000568f`
- `win32u!NtUserSetInformationThread` at `0x18000576c`
- `win32u!NtUserSetInformationThread` at `0x1800057b6`

## pseudocode

```c
__int64 __fastcall CreateCtrlThread(
        unsigned int *a1,
        HWND a2,
        char a3,
        unsigned int a4,
        char a5,
        int ProcessInformation)
{
  HANDLE v6; // r14
  __int64 v7; // r13
  int v8; // r12d
  __int64 v10; // r15
  int v11; // ebx
  BOOL v12; // esi
  PVOID v13; // rdx
  BOOL v14; // edi
  int v15; // eax
  unsigned int v16; // ebx
  HANDLE v17; // r13
  int v18; // r14d
  __int64 v19; // rdx
  int v20; // eax
  int v21; // eax
  __int64 v22; // rcx
  DWORD v24; // [rsp+48h] [rbp-39h] BYREF
  BOOL v25; // [rsp+4Ch] [rbp-35h]
  HANDLE hProcess; // [rsp+50h] [rbp-31h]
  PVOID Reserved5; // [rsp+58h] [rbp-29h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-21h] BYREF
  __int64 v29; // [rsp+68h] [rbp-19h] BYREF
  __int128 v30; // [rsp+70h] [rbp-11h] BYREF
  __int64 v31; // [rsp+80h] [rbp-1h]
  int v35; // [rsp+E8h] [rbp+67h]
  DWORD ExitCode; // [rsp+F0h] [rbp+6Fh] BYREF

  v6 = (HANDLE)*((_QWORD *)a1 + 10);
  v7 = *a1;
  v8 = 0;
  v10 = a4;
  hObject = 0;
  v11 = a5 & 8;
  v12 = 1;
  Reserved5 = 0;
  v29 = v7;
  hProcess = v6;
  ProcessInformation = -1;
  NtQueryInformationProcess(v6, ProcessSessionInformation, &ProcessInformation, 4u, 0);
  if ( (int)BaseGetProcessCrtlRoutine(a1, &Reserved5) >= 0 )
  {
    v13 = Reserved5;
  }
  else
  {
    v13 = 0;
    Reserved5 = 0;
  }
  v25 = (unsigned int)v10 < 2;
  v14 = v11 || (a3 & 1) != 0 || !gfAllowBlockingApps;
  v15 = a3 & 0xC;
  ExitCode = 0;
  v35 = v15;
  if ( v15 )
    v14 = 1;
  v24 = 0;
  LOBYTE(v8) = v15 == 0;
  if ( v13 )
  {
    if ( InternalCreateCallbackThread(v6, v13, (PVOID)(v10 | -(__int64)(v15 != 0) & 0x80000000LL), &hObject) >= 0 )
    {
      v16 = gCmsWaitToKillTimeout;
      if ( a5 < 0 && gCmsWaitToKillTimeout > (unsigned int)gCmsQuickAppShutdownTimeout )
        v16 = gCmsQuickAppShutdownTimeout;
      switch ( (_DWORD)v10 )
      {
        case 2:
          v16 = gCmsHungAppTimeout;
          goto LABEL_22;
        case 5:
LABEL_22:
          v17 = hObject;
          while ( 1 )
          {
            v18 = BoostHardError(v29, v14);
            if ( !v18 || (v19 = 1000, !v14) )
              v19 = v16;
            v20 = InternalWaitCancel(v17, v19);
            if ( v20 != 258 )
              break;
            if ( !v18 || !v14 )
            {
              if ( !v14 )
              {
                v31 = 0;
                v30 = 0;
                *(_QWORD *)&v30 = *((_QWORD *)NtCurrentTeb()->CsrClientThread + 8);
                if ( (int)NtUserSetInformationThread(-2, 8, &v30) < 0 )
                {
                  v12 = 0;
                }
                else
                {
                  v12 = ThreadShutdownNotify(0x20u, (__int64)v17, a2, 0xFFFFFFFF, 0, 0, 0) != 4;
                  NtUserSetInformationThread(-2, 9, &v30);
                }
              }
              goto LABEL_32;
            }
          }
          if ( v20 )
          {
LABEL_32:
            v6 = hProcess;
            goto LABEL_33;
          }
          ExitCode = 0;
          GetExitCodeThread(v17, &ExitCode);
          GetExitCodeProcess(hProcess, &v24);
          if ( !v18 && (ExitCode != (_DWORD)v10 || v24 != 259) )
          {
            v8 = 0;
            goto LABEL_32;
          }
          if ( v14 )
            goto LABEL_32;
          v6 = hProcess;
          v21 = InternalWaitCancel(hProcess, 1000);
          if ( v21 )
          {
            if ( v21 == 258 )
            {
              v31 = 0;
              v30 = 0;
              *(_QWORD *)&v30 = *((_QWORD *)NtCurrentTeb()->CsrClientThread + 8);
              if ( (int)NtUserSetInformationThread(-2, 8, &v30) < 0 )
              {
                v12 = 0;
              }
              else
              {
                v12 = ThreadShutdownNotify(0x20u, (__int64)v6, a2, 0xFFFFFFFF, 0, 0, 0) != 4;
                NtUserSetInformationThread(-2, 9, &v30);
              }
            }
          }
          else
          {
            v8 = 0;
          }
LABEL_33:
          CloseHandle(v17);
          v7 = v29;
          goto LABEL_48;
        case 6:
          if ( ProcessInformation == gServiceSessionId )
            v16 = gdwServicesWaitToKillTimeout;
          goto LABEL_22;
      }
      CloseHandle(hObject);
      v8 = 0;
    }
LABEL_48:
    v15 = v35;
  }
  if ( !v25 && !v15 && v12 )
  {
    v29 = 0;
    if ( (int)CsrLockProcessByClientId(v7, &v29) >= 0 )
    {
      if ( (a5 & 0x40) != 0 )
        RegisterApplicationRestartCL(v6);
      v22 = v29;
      a1[23] |= 0x40u;
      CsrUnlockProcess(v22);
    }
    if ( v8 )
      KillProcess(v6);
    else
      BoostHardError(v7, 1);
  }
  return !v12 ? 0xC0000001 : 0;
}

```

## disassembly

```asm
0x180005474  mov     rax, rsp
0x180005477  mov     [rax+18h], r8d
0x18000547b  mov     [rax+10h], rdx
0x18000547f  mov     [rax+8], rcx
0x180005483  push    rbp
0x180005484  push    rbx
0x180005485  push    rsi
0x180005486  push    rdi
0x180005487  push    r12
0x180005489  push    r13
0x18000548b  push    r14
0x18000548d  push    r15
0x18000548f  lea     rbp, [rax-4Fh]
0x180005493  sub     rsp, 88h
0x18000549a  mov     r14, [rcx+50h]
0x18000549e  lea     r8, [rbp+47h+ProcessInformation]; ProcessInformation
0x1800054a2  mov     r13d, [rcx]
0x1800054a5  xor     r12d, r12d
0x1800054a8  mov     ebx, dword ptr [rbp+47h+arg_20]
0x1800054ab  mov     rdi, rcx
0x1800054ae  mov     r15d, r9d
0x1800054b1  mov     rcx, r14; ProcessHandle
0x1800054b4  mov     [rbp+47h+hObject], r12
0x1800054b8  and     ebx, 8
0x1800054bb  lea     esi, [r12+1]
0x1800054c0  mov     [rbp+47h+Reserved5], r12
0x1800054c4  lea     edx, [rsi+17h]; ProcessInformationClass
0x1800054c7  mov     [rbp+47h+var_60], r13
0x1800054cb  lea     r9d, [r12+4]; ProcessInformationLength
0x1800054d0  mov     [rbp+47h+hProcess], r14
0x1800054d4  mov     [rbp+47h+ProcessInformation], 0FFFFFFFFh
0x1800054db  mov     [rsp+0C0h+ReturnLength], r12; ReturnLength
0x1800054e0  call    cs:__imp_NtQueryInformationProcess
0x1800054e7  nop     dword ptr [rax+rax+00h]
0x1800054ec  lea     rdx, [rbp+47h+Reserved5]
0x1800054f0  mov     rcx, rdi
0x1800054f3  call    cs:__imp_BaseGetProcessCrtlRoutine
0x1800054fa  nop     dword ptr [rax+rax+00h]
0x1800054ff  test    eax, eax
0x180005501  jns     short loc_18000550C
0x180005503  mov     edx, r12d
0x180005506  mov     [rbp+47h+Reserved5], rdx
0x18000550a  jmp     short loc_180005510
0x18000550c  mov     rdx, [rbp+47h+Reserved5]; Reserved5
0x180005510  mov     eax, r12d
0x180005513  cmp     r15d, 2
0x180005517  setb    al
0x18000551a  test    ebx, ebx
0x18000551c  mov     [rbp+47h+var_7C], eax
0x18000551f  mov     ebx, esi
0x180005521  mov     eax, [rbp+47h+arg_10]
0x180005524  jnz     short loc_180005537
0x180005526  test    bl, al
0x180005528  jnz     short loc_180005537
0x18000552a  cmp     cs:gfAllowBlockingApps, r12d
0x180005531  jz      short loc_180005537
0x180005533  xor     edi, edi
0x180005535  jmp     short loc_180005539
0x180005537  mov     edi, ebx
0x180005539  and     eax, 0Ch
0x18000553c  mov     [rbp+47h+ExitCode], 0
0x180005543  mov     [rbp+47h+arg_10], eax
0x180005546  cmovnz  edi, ebx
0x180005549  mov     [rbp+47h+var_80], 0
0x180005550  test    eax, eax
0x180005552  setz    r12b
0x180005556  test    rdx, rdx
0x180005559  jz      loc_1800057E6
0x18000555f  neg     eax
0x180005561  lea     r9, [rbp+47h+hObject]
0x180005565  mov     eax, 80000000h
0x18000556a  mov     rcx, r14; ThreadContext
0x18000556d  sbb     r8, r8
0x180005570  and     r8, rax
0x180005573  or      r8, r15; Reserved6
0x180005576  call    InternalCreateCallbackThread
0x18000557b  test    eax, eax
0x18000557d  js      loc_1800057E3
0x180005583  test    [rbp+47h+arg_20], 80h
0x180005587  mov     ebx, cs:gCmsWaitToKillTimeout
0x18000558d  jz      short loc_18000559C
0x18000558f  cmp     ebx, cs:gCmsQuickAppShutdownTimeout
0x180005595  cmova   ebx, cs:gCmsQuickAppShutdownTimeout
0x18000559c  cmp     r15d, 2
0x1800055a0  jnz     short loc_1800055AA
0x1800055a2  mov     ebx, cs:gCmsHungAppTimeout
0x1800055a8  jmp     short loc_1800055CA
0x1800055aa  cmp     r15d, 5
0x1800055ae  jz      short loc_1800055CA
0x1800055b0  cmp     r15d, 6
0x1800055b4  jnz     loc_1800057CE
0x1800055ba  mov     eax, cs:gServiceSessionId
0x1800055c0  cmp     [rbp+47h+ProcessInformation], eax
0x1800055c3  cmovz   ebx, cs:gdwServicesWaitToKillTimeout
0x1800055ca  mov     r13, [rbp+47h+hObject]
0x1800055ce  mov     rcx, [rbp+47h+var_60]
0x1800055d2  mov     edx, edi
0x1800055d4  call    BoostHardError
0x1800055d9  mov     r14d, eax
0x1800055dc  test    eax, eax
0x1800055de  jz      short loc_1800055E9
0x1800055e0  mov     edx, 3E8h
0x1800055e5  test    edi, edi
0x1800055e7  jnz     short loc_1800055EB
0x1800055e9  mov     edx, ebx
0x1800055eb  mov     rcx, r13
0x1800055ee  call    InternalWaitCancel
0x1800055f3  cmp     eax, 102h
0x1800055f8  jnz     loc_1800056C0
0x1800055fe  test    r14d, r14d
0x180005601  jz      short loc_180005607
0x180005603  test    edi, edi
0x180005605  jnz     short loc_1800055CE
0x180005607  test    edi, edi
0x180005609  jnz     loc_18000569B
0x18000560f  xor     eax, eax
0x180005611  lea     r15d, [rdi+18h]
0x180005615  mov     [rbp+47h+var_48], rax
0x180005619  lea     r8, [rbp+47h+var_58]
0x18000561d  xorps   xmm0, xmm0
0x180005620  lea     edx, [rdi+8]
0x180005623  movups  [rbp+47h+var_58], xmm0
0x180005627  mov     rax, gs:70h
0x180005630  mov     rbx, 0FFFFFFFFFFFFFFFEh
0x180005637  mov     r9d, r15d
0x18000563a  mov     rcx, [rax+40h]
0x18000563e  mov     qword ptr [rbp+47h+var_58], rcx
0x180005642  mov     rcx, rbx
0x180005645  call    cs:__imp_NtUserSetInformationThread
0x18000564c  nop     dword ptr [rax+rax+00h]
0x180005651  xor     edi, edi
0x180005653  test    eax, eax
0x180005655  js      short loc_1800056BC
0x180005657  mov     r8, [rbp+47h+arg_8]
0x18000565b  lea     ecx, [rbx+22h]
0x18000565e  mov     [rsp+30h], rdi
0x180005663  or      r9d, 0FFFFFFFFh
0x180005667  mov     [rsp+0C0h+var_98], rdi
0x18000566c  mov     rdx, r13
0x18000566f  mov     [rsp+0C0h+ReturnLength], rdi
0x180005674  call    ThreadShutdownNotify
0x180005679  cmp     eax, 4
0x18000567c  lea     r8, [rbp+47h+var_58]
0x180005680  mov     esi, edi
0x180005682  lea     edx, [rbx+0Bh]
0x180005685  mov     r9d, r15d
0x180005688  mov     rcx, rbx
0x18000568b  setnz   sil
0x18000568f  call    cs:__imp_NtUserSetInformationThread
0x180005696  nop     dword ptr [rax+rax+00h]
0x18000569b  mov     r14, [rbp+47h+hProcess]
0x18000569f  mov     rcx, r13; hObject
0x1800056a2  call    cs:__imp_CloseHandle
0x1800056a9  nop     dword ptr [rax+rax+00h]
0x1800056ae  mov     r13, [rbp+47h+var_60]
0x1800056b2  mov     ebx, 1
0x1800056b7  jmp     loc_1800057E3
0x1800056bc  xor     esi, esi
0x1800056be  jmp     short loc_18000569B
0x1800056c0  test    eax, eax
0x1800056c2  jnz     short loc_18000569B
0x1800056c4  lea     rdx, [rbp+47h+ExitCode]; lpExitCode
0x1800056c8  mov     [rbp+47h+ExitCode], eax
0x1800056cb  mov     rcx, r13; hThread
0x1800056ce  call    cs:__imp_GetExitCodeThread
0x1800056d5  nop     dword ptr [rax+rax+00h]
0x1800056da  mov     rcx, [rbp+47h+hProcess]; hProcess
0x1800056de  lea     rdx, [rbp+47h+var_80]; lpExitCode
0x1800056e2  call    cs:__imp_GetExitCodeProcess
0x1800056e9  nop     dword ptr [rax+rax+00h]
0x1800056ee  test    r14d, r14d
0x1800056f1  jnz     short loc_180005707
0x1800056f3  cmp     [rbp+47h+ExitCode], r15d
0x1800056f7  jnz     short loc_180005702
0x1800056f9  cmp     [rbp+47h+var_80], 103h
0x180005700  jz      short loc_180005707
0x180005702  xor     r12d, r12d
0x180005705  jmp     short loc_18000569B
0x180005707  test    edi, edi
0x180005709  jnz     short loc_18000569B
0x18000570b  mov     r14, [rbp+47h+hProcess]
0x18000570f  mov     edx, 3E8h
0x180005714  mov     rcx, r14
0x180005717  call    InternalWaitCancel
0x18000571c  test    eax, eax
0x18000571e  jnz     short loc_180005728
0x180005720  xor     r12d, r12d
0x180005723  jmp     loc_18000569F
0x180005728  cmp     eax, 102h
0x18000572d  jnz     loc_18000569F
0x180005733  xor     eax, eax
0x180005735  lea     r8, [rbp+47h+var_58]
0x180005739  mov     [rbp+47h+var_48], rax
0x18000573d  xorps   xmm0, xmm0
0x180005740  movups  [rbp+47h+var_58], xmm0
0x180005744  mov     rax, gs:70h
0x18000574d  mov     r15d, 18h
0x180005753  mov     rbx, 0FFFFFFFFFFFFFFFEh
0x18000575a  mov     r9d, r15d
0x18000575d  mov     rcx, [rax+40h]
0x180005761  lea     edx, [r15-10h]
0x180005765  mov     qword ptr [rbp+47h+var_58], rcx
0x180005769  mov     rcx, rbx
0x18000576c  call    cs:__imp_NtUserSetInformationThread
0x180005773  nop     dword ptr [rax+rax+00h]
0x180005778  xor     edi, edi
0x18000577a  test    eax, eax
0x18000577c  js      short loc_1800057C7
0x18000577e  mov     r8, [rbp+47h+arg_8]
0x180005782  lea     ecx, [rbx+22h]
0x180005785  mov     [rsp+30h], rdi
0x18000578a  or      r9d, 0FFFFFFFFh
0x18000578e  mov     [rsp+0C0h+var_98], rdi
0x180005793  mov     rdx, r14
0x180005796  mov     [rsp+0C0h+ReturnLength], rdi
0x18000579b  call    ThreadShutdownNotify
0x1800057a0  cmp     eax, 4
0x1800057a3  lea     r8, [rbp+47h+var_58]
0x1800057a7  mov     esi, edi
0x1800057a9  lea     edx, [rbx+0Bh]
0x1800057ac  mov     r9d, r15d
0x1800057af  mov     rcx, rbx
0x1800057b2  setnz   sil
0x1800057b6  call    cs:__imp_NtUserSetInformationThread
0x1800057bd  nop     dword ptr [rax+rax+00h]
0x1800057c2  jmp     loc_18000569F
0x1800057c7  xor     esi, esi
0x1800057c9  jmp     loc_18000569F
0x1800057ce  mov     rcx, [rbp+47h+hObject]; hObject
0x1800057d2  call    cs:__imp_CloseHandle
0x1800057d9  nop     dword ptr [rax+rax+00h]
0x1800057de  xor     r12d, r12d
0x1800057e1  mov     ebx, esi
0x1800057e3  mov     eax, [rbp+47h+arg_10]
0x1800057e6  cmp     [rbp+47h+var_7C], 0
0x1800057ea  jnz     short loc_180005855
0x1800057ec  test    eax, eax
0x1800057ee  jnz     short loc_180005855
0x1800057f0  test    esi, esi
0x1800057f2  jz      short loc_180005855
0x1800057f4  lea     rdx, [rbp+47h+var_60]
0x1800057f8  mov     [rbp+47h+var_60], 0
0x180005800  mov     rcx, r13
0x180005803  call    cs:__imp_CsrLockProcessByClientId
0x18000580a  nop     dword ptr [rax+rax+00h]
0x18000580f  test    eax, eax
0x180005811  js      short loc_180005839
0x180005813  test    [rbp+47h+arg_20], 40h
0x180005817  jz      short loc_180005821
0x180005819  mov     rcx, r14; hProcess
0x18000581c  call    RegisterApplicationRestartCL
0x180005821  mov     rax, [rbp+47h+arg_0]
0x180005825  mov     rcx, [rbp+47h+var_60]
0x180005829  or      dword ptr [rax+5Ch], 40h
0x18000582d  call    cs:__imp_CsrUnlockProcess
0x180005834  nop     dword ptr [rax+rax+00h]
0x180005839  test    r12d, r12d
0x18000583c  jz      short loc_18000584B
0x18000583e  mov     rdx, r13
0x180005841  mov     rcx, r14; Handle
0x180005844  call    KillProcess
0x180005849  jmp     short loc_180005855
0x18000584b  mov     edx, ebx
0x18000584d  mov     rcx, r13
0x180005850  call    BoostHardError
0x180005855  neg     esi
0x180005857  sbb     eax, eax
0x180005859  not     eax
0x18000585b  and     eax, 0C0000001h
0x180005860  add     rsp, 88h
0x180005867  pop     r15
0x180005869  pop     r14
0x18000586b  pop     r13
0x18000586d  pop     r12
0x18000586f  pop     rdi
0x180005870  pop     rsi
0x180005871  pop     rbx
0x180005872  pop     rbp
0x180005873  retn
```
