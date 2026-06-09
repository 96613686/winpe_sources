# NtMITSynthesizeKeyboardInput

- ea: `0x1400ac930`
- end: `0x1400acc5b`
- name: `NtMITSynthesizeKeyboardInput`
- size: `811`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update`

## callees

- `0x140012c80`
- `0x140029324`
- `0x140029fe8`
- `0x140076950`
- `0x140076db0`
- `0x140076ef0`
- `0x140076f80`
- `0x1400ab060`
- `0x1400ac930`
- `0x140126344`
- `0x1401a3b60`
- `0x1401c6588`
- `0x140238b10`
- `0x140238c40`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ac97e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ac97e`
- `ntoskrnl!ProbeForWrite` at `0x1400acb0e`
- `ntoskrnl!ProbeForWrite` at `0x1400acb0e`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400acaed`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400acaed`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1400acc16`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1400acc16`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ac96f`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ac96f`
- `WIN32K!W32GetUserSessionState` at `0x1400ac960`
- `WIN32K!W32GetUserSessionState` at `0x1400acb46`
- `WIN32K!W32GetUserSessionState` at `0x1400acb77`
- `WIN32K!W32GetUserSessionState` at `0x1400ac960`
- `WIN32K!W32GetUserSessionState` at `0x1400acb46`
- `WIN32K!W32GetUserSessionState` at `0x1400acb77`

## pseudocode

```c
__int64 __fastcall NtMITSynthesizeKeyboardInput(__int64 a1, void *a2, volatile void *a3)
{
  int v5; // r15d
  __int64 UserSessionState; // rsi
  __int64 v7; // rcx
  struct _W32THREADNONPAGED *CurrentThreadWin32Thread; // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 CurrentProcessWow64Process; // rax
  int v15; // eax
  int v16; // esi
  int v17; // r15d
  int v18; // r12d
  unsigned __int64 v19; // r13
  __int64 v20; // rax
  __int64 v21; // rax
  _OWORD v23[4]; // [rsp+88h] [rbp-C0h] BYREF
  _OWORD v24[4]; // [rsp+D0h] [rbp-78h] BYREF

  v5 = a1;
  UserSessionState = W32GetUserSessionState(a1);
  CurrentThreadWin32Thread = (struct _W32THREADNONPAGED *)PsGetCurrentThreadWin32Thread(v7);
  KeEnterCriticalRegion();
  _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
    *(struct _FAST_ERESOURCE **)UserSessionState,
    CurrentThreadWin32Thread);
  v9 = *(_QWORD *)CurrentThreadWin32Thread;
  if ( *(_QWORD *)CurrentThreadWin32Thread )
    *(_BYTE *)(v9 + 1708) = 1;
  else
    v9 = 0;
  *(_QWORD *)(UserSessionState + 16) = v9;
  if ( v9 )
  {
    DestroySharedUserCritDeferredUnlockList(UserSessionState + 19520);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
  }
  memset(v24, 0, sizeof(v24));
  if ( (unsigned __int8)IsInputThread() )
  {
    memset(v23, 0, sizeof(v23));
    RtlCopyFromUser(v23, a2, 0x40u);
    v24[0] = v23[0];
    v24[1] = v23[1];
    v24[2] = v23[2];
    v24[3] = v23[3];
    if ( v5 == 4 )
    {
      xxxUpdateGlobalsAndSendKeyEvent(
        DWORD2(v23[0]),
        v23[0],
        HIDWORD(v23[0]),
        0,
        *((__int64 *)&v23[2] + 1),
        0,
        v23[1],
        DWORD1(v23[0]) != 0,
        0,
        0,
        0,
        (__int64)&v24[3]);
      if ( a3 )
      {
        CurrentProcessWow64Process = PsGetCurrentProcessWow64Process();
        ProbeForWrite(a3, 0x100u, CurrentProcessWow64Process != 0 ? 1 : 4);
        LOBYTE(v15) = 0;
        v16 = 0;
        v17 = 0;
        while ( v16 < 256 )
        {
          v18 = v15 & 3;
          v19 = (unsigned __int64)(unsigned __int8)v15 >> 2;
          if ( (*(_BYTE *)(W32GetUserSessionState(v12) + v19 + 14280) & (unsigned __int8)(1 << (2 * v18))) != 0 )
            *((_BYTE *)a3 + v17) = *((_BYTE *)a3 + v16) | 0x80;
          v20 = W32GetUserSessionState((unsigned int)(2 * v18));
          v12 = (unsigned int)(2 * v18 + 1);
          if ( (*(_BYTE *)(v20 + v19 + 14280) & (unsigned __int8)(1 << (2 * v18 + 1))) != 0 )
          {
            LOBYTE(v12) = *((_BYTE *)a3 + v16) | 1;
            *((_BYTE *)a3 + v17) = v12;
          }
          v15 = v16 + 1;
          v16 = v15;
          v17 = v15;
        }
      }
    }
    else
    {
      v11 = 0;
      if ( v5 != 8 )
        goto LABEL_25;
      LOBYTE(v13) = 19;
      v21 = HMValidateHandleWithDescriptor(*((_QWORD *)&v23[2] + 1), v13, 0);
      if ( *((_QWORD *)&v24[2] + 1) && !v21 )
      {
        v10 = 6;
        goto LABEL_8;
      }
      ProcessKeyboardInjectedInput(v24, v21, &v24[3]);
    }
    v11 = 1;
    goto LABEL_25;
  }
  v10 = 5;
LABEL_8:
  v11 = 0;
  UserSetLastError(v10);
LABEL_25:
  UserSessionSwitchLeaveCritWithNonPaged(v12);
  return v11;
}

```

## disassembly

```asm
0x1400ac930  mov     [rsp+arg_0], rbx
0x1400ac935  push    rsi
0x1400ac936  push    r12
0x1400ac938  push    r13
0x1400ac93a  push    r14
0x1400ac93c  push    r15
0x1400ac93e  sub     rsp, 120h
0x1400ac945  mov     rax, cs:__security_cookie
0x1400ac94c  xor     rax, rsp
0x1400ac94f  mov     [rsp+148h+var_38], rax
0x1400ac957  mov     r14, r8
0x1400ac95a  mov     r12, rdx
0x1400ac95d  mov     r15d, ecx
0x1400ac960  call    cs:__imp_W32GetUserSessionState
0x1400ac967  nop     dword ptr [rax+rax+00h]
0x1400ac96c  mov     rsi, rax
0x1400ac96f  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400ac976  nop     dword ptr [rax+rax+00h]
0x1400ac97b  mov     rbx, rax
0x1400ac97e  call    cs:__imp_KeEnterCriticalRegion
0x1400ac985  nop     dword ptr [rax+rax+00h]
0x1400ac98a  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x1400ac98d  mov     rcx, [rsi]; struct _FAST_ERESOURCE *
0x1400ac990  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1400ac995  mov     rdx, [rbx]
0x1400ac998  xor     r13d, r13d
0x1400ac99b  test    rdx, rdx
0x1400ac99e  jnz     short loc_1400AC9A5
0x1400ac9a0  mov     edx, r13d
0x1400ac9a3  jmp     short loc_1400AC9AC
0x1400ac9a5  mov     byte ptr [rdx+6ACh], 1
0x1400ac9ac  mov     [rsi+10h], rdx
0x1400ac9b0  test    rdx, rdx
0x1400ac9b3  jz      short loc_1400AC9D6
0x1400ac9b5  lea     rbx, [rsi+4C40h]
0x1400ac9bc  mov     rcx, rbx
0x1400ac9bf  call    DestroySharedUserCritDeferredUnlockList
0x1400ac9c4  lea     rcx, [rbx+38h]
0x1400ac9c8  call    DestroyDeferredUnlockObjectAssignmentList
0x1400ac9cd  lea     rcx, [rbx+28h]
0x1400ac9d1  call    DestroyDeferredUnlockObjectAssignmentList
0x1400ac9d6  mov     ebx, 40h ; '@'
0x1400ac9db  mov     r8d, ebx; Size
0x1400ac9de  xor     edx, edx; Val
0x1400ac9e0  lea     rcx, [rsp+148h+var_78]; void *
0x1400ac9e8  call    memset
0x1400ac9ed  call    IsInputThread
0x1400ac9f2  test    al, al
0x1400ac9f4  jnz     short loc_1400ACA06
0x1400ac9f6  lea     ecx, [rbx-3Bh]
0x1400ac9f9  mov     ebx, r13d
0x1400ac9fc  call    UserSetLastError
0x1400aca01  jmp     loc_1400ACC2A
0x1400aca06  mov     r8, rbx; Size
0x1400aca09  xor     edx, edx; Val
0x1400aca0b  lea     rcx, [rsp+148h+var_C0]; void *
0x1400aca13  call    memset
0x1400aca18  mov     r8, rbx; Size
0x1400aca1b  mov     rdx, r12; Src
0x1400aca1e  lea     rcx, [rsp+148h+var_C0]; void *
0x1400aca26  call    RtlCopyFromUser
0x1400aca2b  movups  xmm0, [rsp+148h+var_C0]
0x1400aca33  movaps  [rsp+148h+var_78], xmm0
0x1400aca3b  movups  xmm1, [rsp+148h+var_B0]
0x1400aca43  movaps  [rsp+148h+var_68], xmm1
0x1400aca4b  movups  xmm0, [rsp+148h+var_A0]
0x1400aca53  movaps  [rsp+148h+var_58], xmm0
0x1400aca5b  movups  xmm1, [rsp+148h+var_90]
0x1400aca63  movaps  [rsp+148h+var_48], xmm1
0x1400aca6b  cmp     r15d, 4
0x1400aca6f  jnz     loc_1400ACBC1
0x1400aca75  mov     [rsp+148h+var_D4], r13d
0x1400aca7a  mov     rdx, qword ptr [rsp+148h+var_C0]
0x1400aca82  mov     rax, rdx
0x1400aca85  shr     rax, 20h
0x1400aca89  test    eax, eax
0x1400aca8b  setnz   al
0x1400aca8e  mov     rcx, qword ptr [rsp+148h+var_C0+8]
0x1400aca96  mov     r8, rcx
0x1400aca99  shr     r8, 20h
0x1400aca9d  lea     r9, [rsp+148h+var_48]
0x1400acaa5  mov     [rsp+148h+var_F0], r9
0x1400acaaa  mov     [rsp+148h+var_F8], r13
0x1400acaaf  mov     [rsp+148h+var_100], r13
0x1400acab4  mov     [rsp+148h+var_108], r13b
0x1400acab9  mov     [rsp+148h+var_110], al
0x1400acabd  movzx   eax, word ptr [rsp+148h+var_B0]
0x1400acac5  mov     [rsp+148h+var_118], ax
0x1400acaca  mov     [rsp+148h+var_120], r13
0x1400acacf  mov     rax, qword ptr [rsp+148h+var_A0+8]
0x1400acad7  mov     [rsp+148h+var_128], rax
0x1400acadc  xor     r9d, r9d
0x1400acadf  call    xxxUpdateGlobalsAndSendKeyEvent
0x1400acae4  test    r14, r14
0x1400acae7  jz      loc_1400ACC0B
0x1400acaed  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1400acaf4  nop     dword ptr [rax+rax+00h]
0x1400acaf9  neg     rax
0x1400acafc  sbb     r8d, r8d
0x1400acaff  and     r8d, 0FFFFFFFDh
0x1400acb03  add     r8d, r15d; Alignment
0x1400acb06  mov     edx, 100h; Length
0x1400acb0b  mov     rcx, r14; Address
0x1400acb0e  call    cs:__imp_ProbeForWrite
0x1400acb15  nop     dword ptr [rax+rax+00h]
0x1400acb1a  mov     eax, r13d
0x1400acb1d  mov     esi, r13d
0x1400acb20  mov     r15d, r13d
0x1400acb23  mov     [rsp+148h+var_E8], eax
0x1400acb27  cmp     esi, 100h
0x1400acb2d  jge     loc_1400ACBB9
0x1400acb33  movzx   r12d, al
0x1400acb37  and     r12d, 3
0x1400acb3b  movzx   r13d, al
0x1400acb3f  shr     r13, 2
0x1400acb43  movsxd  rbx, esi
0x1400acb46  call    cs:__imp_W32GetUserSessionState
0x1400acb4d  nop     dword ptr [rax+rax+00h]
0x1400acb52  mov     dl, [rax+r13+37C8h]
0x1400acb5a  lea     ecx, [r12+r12]
0x1400acb5e  mov     eax, 1
0x1400acb63  shl     eax, cl
0x1400acb65  test    al, dl
0x1400acb67  jz      short loc_1400ACB77
0x1400acb69  mov     cl, [rbx+r14]
0x1400acb6d  or      cl, 80h
0x1400acb70  movsxd  rax, r15d
0x1400acb73  mov     [rax+r14], cl
0x1400acb77  call    cs:__imp_W32GetUserSessionState
0x1400acb7e  nop     dword ptr [rax+rax+00h]
0x1400acb83  mov     dl, [rax+r13+37C8h]
0x1400acb8b  lea     ecx, ds:1[r12*2]
0x1400acb93  mov     eax, 1
0x1400acb98  shl     eax, cl
0x1400acb9a  test    al, dl
0x1400acb9c  jz      short loc_1400ACBAC
0x1400acb9e  mov     cl, [r14+rbx]
0x1400acba2  or      cl, 1
0x1400acba5  movsxd  rax, r15d
0x1400acba8  mov     [rax+r14], cl
0x1400acbac  lea     eax, [rsi+1]
0x1400acbaf  mov     esi, eax
0x1400acbb1  mov     r15d, eax
0x1400acbb4  jmp     loc_1400ACB23
0x1400acbb9  jmp     short loc_1400ACC0B
0x1400acbbb  mov     ebx, [rsp+148h+var_D4]
0x1400acbbf  jmp     short loc_1400ACC2A
0x1400acbc1  mov     ebx, r13d
0x1400acbc4  cmp     r15d, 8
0x1400acbc8  jnz     short loc_1400ACC2A
0x1400acbca  xor     r8d, r8d
0x1400acbcd  mov     dl, 13h
0x1400acbcf  mov     rcx, qword ptr [rsp+148h+var_A0+8]
0x1400acbd7  call    HMValidateHandleWithDescriptor
0x1400acbdc  cmp     qword ptr [rsp+148h+var_58+8], r13
0x1400acbe4  jz      short loc_1400ACBF3
0x1400acbe6  test    rax, rax
0x1400acbe9  jnz     short loc_1400ACBF3
0x1400acbeb  lea     ecx, [rax+6]
0x1400acbee  jmp     loc_1400AC9F9
0x1400acbf3  lea     r8, [rsp+148h+var_48]
0x1400acbfb  mov     rdx, rax
0x1400acbfe  lea     rcx, [rsp+148h+var_78]
0x1400acc06  call    ProcessKeyboardInjectedInput
0x1400acc0b  mov     ebx, 1
0x1400acc10  jmp     short loc_1400ACC2A
0x1400acc12  xor     ebx, ebx
0x1400acc14  mov     ecx, eax; Status
0x1400acc16  call    cs:__imp_RtlNtStatusToDosError
0x1400acc1d  nop     dword ptr [rax+rax+00h]
0x1400acc22  mov     ecx, eax
0x1400acc24  call    UserSetLastError
0x1400acc29  nop
0x1400acc2a  call    UserSessionSwitchLeaveCritWithNonPaged
0x1400acc2f  mov     eax, ebx
0x1400acc31  mov     rcx, [rsp+148h+var_38]
0x1400acc39  xor     rcx, rsp; StackCookie
0x1400acc3c  call    __security_check_cookie
0x1400acc41  mov     rbx, [rsp+148h+arg_0]
0x1400acc49  add     rsp, 120h
0x1400acc50  pop     r15
0x1400acc52  pop     r14
0x1400acc54  pop     r13
0x1400acc56  pop     r12
0x1400acc58  pop     rsi
0x1400acc59  retn
0x140239a47  push    rbp
0x140239a49  sub     rsp, 60h
0x140239a4d  mov     rbp, rdx
0x140239a50  mov     rax, [rcx]
0x140239a53  mov     ecx, [rax]
0x140239a55  mov     [rbp+78h], ecx
0x140239a58  mov     ecx, [rbp+78h]
0x140239a5b  call    SetLastNtError
0x140239a60  mov     dword ptr [rbp+80h], 1
0x140239a6a  mov     eax, [rbp+80h]
0x140239a70  add     rsp, 60h
0x140239a74  pop     rbp
0x140239a75  retn
0x140239a77  push    rbp
0x140239a79  sub     rsp, 60h
0x140239a7d  mov     rbp, rdx
0x140239a80  mov     rax, [rcx]
0x140239a83  mov     ecx, [rax]
0x140239a85  mov     [rbp+68h], ecx
0x140239a88  mov     ecx, [rbp+68h]
0x140239a8b  call    SetLastNtError
0x140239a90  mov     dword ptr [rbp+70h], 1
0x140239a97  mov     eax, [rbp+70h]
0x140239a9a  add     rsp, 60h
0x140239a9e  pop     rbp
0x140239a9f  retn
```
