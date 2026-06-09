# NtMITSynthesizeKeyboardInput

- ea: `0x1400a3730`
- end: `0x1400a3a5b`
- name: `NtMITSynthesizeKeyboardInput`
- size: `811`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update`

## callees

- `0x14001bdf0`
- `0x1400325a4`
- `0x140033268`
- `0x140077af0`
- `0x140077f50`
- `0x140078090`
- `0x140078120`
- `0x1400a1e60`
- `0x1400a3730`
- `0x1401263a4`
- `0x1401a3600`
- `0x1401c6028`
- `0x140238160`
- `0x1402382c0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a377e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a377e`
- `ntoskrnl!ProbeForWrite` at `0x1400a390e`
- `ntoskrnl!ProbeForWrite` at `0x1400a390e`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400a38ed`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400a38ed`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1400a3a16`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1400a3a16`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400a376f`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400a376f`
- `WIN32K!W32GetUserSessionState` at `0x1400a3760`
- `WIN32K!W32GetUserSessionState` at `0x1400a3946`
- `WIN32K!W32GetUserSessionState` at `0x1400a3977`
- `WIN32K!W32GetUserSessionState` at `0x1400a3760`
- `WIN32K!W32GetUserSessionState` at `0x1400a3946`
- `WIN32K!W32GetUserSessionState` at `0x1400a3977`

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
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 CurrentProcessWow64Process; // rax
  int v16; // eax
  int v17; // esi
  int v18; // r15d
  int v19; // r12d
  unsigned __int64 v20; // r13
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rax
  _OWORD v25[4]; // [rsp+88h] [rbp-C0h] BYREF
  _OWORD v26[4]; // [rsp+D0h] [rbp-78h] BYREF

  v5 = a1;
  UserSessionState = W32GetUserSessionState(a1, a2, a3);
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
  memset(v26, 0, sizeof(v26));
  if ( (unsigned __int8)IsInputThread() )
  {
    memset(v25, 0, sizeof(v25));
    RtlCopyFromUser(v25, a2, 0x40u);
    v26[0] = v25[0];
    v26[1] = v25[1];
    v26[2] = v25[2];
    v26[3] = v25[3];
    if ( v5 == 4 )
    {
      xxxUpdateGlobalsAndSendKeyEvent(
        DWORD2(v25[0]),
        v25[0],
        HIDWORD(v25[0]),
        0,
        *((__int64 *)&v25[2] + 1),
        0,
        v25[1],
        DWORD1(v25[0]) != 0,
        0,
        0,
        0,
        (__int64)&v26[3]);
      if ( a3 )
      {
        CurrentProcessWow64Process = PsGetCurrentProcessWow64Process();
        ProbeForWrite(a3, 0x100u, CurrentProcessWow64Process != 0 ? 1 : 4);
        LOBYTE(v16) = 0;
        v17 = 0;
        v18 = 0;
        while ( v17 < 256 )
        {
          v19 = v16 & 3;
          v20 = (unsigned __int64)(unsigned __int8)v16 >> 2;
          LOBYTE(v21) = *(_BYTE *)(W32GetUserSessionState(v13, v12, v14) + v20 + 14280);
          if ( ((unsigned __int8)v21 & (unsigned __int8)(1 << (2 * v19))) != 0 )
            *((_BYTE *)a3 + v18) = *((_BYTE *)a3 + v17) | 0x80;
          LOBYTE(v12) = *(_BYTE *)(W32GetUserSessionState((unsigned int)(2 * v19), v21, v22) + v20 + 14280);
          v13 = (unsigned int)(2 * v19 + 1);
          if ( ((unsigned __int8)v12 & (unsigned __int8)(1 << (2 * v19 + 1))) != 0 )
          {
            LOBYTE(v13) = *((_BYTE *)a3 + v17) | 1;
            *((_BYTE *)a3 + v18) = v13;
          }
          v16 = v17 + 1;
          v17 = v16;
          v18 = v16;
        }
      }
    }
    else
    {
      v11 = 0;
      if ( v5 != 8 )
        goto LABEL_25;
      LOBYTE(v12) = 19;
      v23 = HMValidateHandleWithDescriptor(*((_QWORD *)&v25[2] + 1), v12, 0);
      if ( *((_QWORD *)&v26[2] + 1) && !v23 )
      {
        v10 = 6;
        goto LABEL_8;
      }
      ProcessKeyboardInjectedInput(v26, v23, &v26[3]);
    }
    v11 = 1;
    goto LABEL_25;
  }
  v10 = 5;
LABEL_8:
  v11 = 0;
  UserSetLastError(v10);
LABEL_25:
  UserSessionSwitchLeaveCritWithNonPaged(v13, v12, v14);
  return v11;
}

```

## disassembly

```asm
0x1400a3730  mov     [rsp+arg_0], rbx
0x1400a3735  push    rsi
0x1400a3736  push    r12
0x1400a3738  push    r13
0x1400a373a  push    r14
0x1400a373c  push    r15
0x1400a373e  sub     rsp, 120h
0x1400a3745  mov     rax, cs:__security_cookie
0x1400a374c  xor     rax, rsp
0x1400a374f  mov     [rsp+148h+var_38], rax
0x1400a3757  mov     r14, r8
0x1400a375a  mov     r12, rdx
0x1400a375d  mov     r15d, ecx
0x1400a3760  call    cs:__imp_W32GetUserSessionState
0x1400a3767  nop     dword ptr [rax+rax+00h]
0x1400a376c  mov     rsi, rax
0x1400a376f  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400a3776  nop     dword ptr [rax+rax+00h]
0x1400a377b  mov     rbx, rax
0x1400a377e  call    cs:__imp_KeEnterCriticalRegion
0x1400a3785  nop     dword ptr [rax+rax+00h]
0x1400a378a  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x1400a378d  mov     rcx, [rsi]; struct _FAST_ERESOURCE *
0x1400a3790  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1400a3795  mov     rdx, [rbx]
0x1400a3798  xor     r13d, r13d
0x1400a379b  test    rdx, rdx
0x1400a379e  jnz     short loc_1400A37A5
0x1400a37a0  mov     edx, r13d
0x1400a37a3  jmp     short loc_1400A37AC
0x1400a37a5  mov     byte ptr [rdx+6ACh], 1
0x1400a37ac  mov     [rsi+10h], rdx
0x1400a37b0  test    rdx, rdx
0x1400a37b3  jz      short loc_1400A37D6
0x1400a37b5  lea     rbx, [rsi+4C40h]
0x1400a37bc  mov     rcx, rbx
0x1400a37bf  call    DestroySharedUserCritDeferredUnlockList
0x1400a37c4  lea     rcx, [rbx+38h]
0x1400a37c8  call    DestroyDeferredUnlockObjectAssignmentList
0x1400a37cd  lea     rcx, [rbx+28h]
0x1400a37d1  call    DestroyDeferredUnlockObjectAssignmentList
0x1400a37d6  mov     ebx, 40h ; '@'
0x1400a37db  mov     r8d, ebx; Size
0x1400a37de  xor     edx, edx; Val
0x1400a37e0  lea     rcx, [rsp+148h+var_78]; void *
0x1400a37e8  call    memset
0x1400a37ed  call    IsInputThread
0x1400a37f2  test    al, al
0x1400a37f4  jnz     short loc_1400A3806
0x1400a37f6  lea     ecx, [rbx-3Bh]
0x1400a37f9  mov     ebx, r13d
0x1400a37fc  call    UserSetLastError
0x1400a3801  jmp     loc_1400A3A2A
0x1400a3806  mov     r8, rbx; Size
0x1400a3809  xor     edx, edx; Val
0x1400a380b  lea     rcx, [rsp+148h+var_C0]; void *
0x1400a3813  call    memset
0x1400a3818  mov     r8, rbx; Size
0x1400a381b  mov     rdx, r12; Src
0x1400a381e  lea     rcx, [rsp+148h+var_C0]; void *
0x1400a3826  call    RtlCopyFromUser
0x1400a382b  movups  xmm0, [rsp+148h+var_C0]
0x1400a3833  movaps  [rsp+148h+var_78], xmm0
0x1400a383b  movups  xmm1, [rsp+148h+var_B0]
0x1400a3843  movaps  [rsp+148h+var_68], xmm1
0x1400a384b  movups  xmm0, [rsp+148h+var_A0]
0x1400a3853  movaps  [rsp+148h+var_58], xmm0
0x1400a385b  movups  xmm1, [rsp+148h+var_90]
0x1400a3863  movaps  [rsp+148h+var_48], xmm1
0x1400a386b  cmp     r15d, 4
0x1400a386f  jnz     loc_1400A39C1
0x1400a3875  mov     [rsp+148h+var_D4], r13d
0x1400a387a  mov     rdx, qword ptr [rsp+148h+var_C0]
0x1400a3882  mov     rax, rdx
0x1400a3885  shr     rax, 20h
0x1400a3889  test    eax, eax
0x1400a388b  setnz   al
0x1400a388e  mov     rcx, qword ptr [rsp+148h+var_C0+8]
0x1400a3896  mov     r8, rcx
0x1400a3899  shr     r8, 20h
0x1400a389d  lea     r9, [rsp+148h+var_48]
0x1400a38a5  mov     [rsp+148h+var_F0], r9
0x1400a38aa  mov     [rsp+148h+var_F8], r13
0x1400a38af  mov     [rsp+148h+var_100], r13
0x1400a38b4  mov     [rsp+148h+var_108], r13b
0x1400a38b9  mov     [rsp+148h+var_110], al
0x1400a38bd  movzx   eax, word ptr [rsp+148h+var_B0]
0x1400a38c5  mov     [rsp+148h+var_118], ax
0x1400a38ca  mov     [rsp+148h+var_120], r13
0x1400a38cf  mov     rax, qword ptr [rsp+148h+var_A0+8]
0x1400a38d7  mov     [rsp+148h+var_128], rax
0x1400a38dc  xor     r9d, r9d
0x1400a38df  call    xxxUpdateGlobalsAndSendKeyEvent
0x1400a38e4  test    r14, r14
0x1400a38e7  jz      loc_1400A3A0B
0x1400a38ed  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1400a38f4  nop     dword ptr [rax+rax+00h]
0x1400a38f9  neg     rax
0x1400a38fc  sbb     r8d, r8d
0x1400a38ff  and     r8d, 0FFFFFFFDh
0x1400a3903  add     r8d, r15d; Alignment
0x1400a3906  mov     edx, 100h; Length
0x1400a390b  mov     rcx, r14; Address
0x1400a390e  call    cs:__imp_ProbeForWrite
0x1400a3915  nop     dword ptr [rax+rax+00h]
0x1400a391a  mov     eax, r13d
0x1400a391d  mov     esi, r13d
0x1400a3920  mov     r15d, r13d
0x1400a3923  mov     [rsp+148h+var_E8], eax
0x1400a3927  cmp     esi, 100h
0x1400a392d  jge     loc_1400A39B9
0x1400a3933  movzx   r12d, al
0x1400a3937  and     r12d, 3
0x1400a393b  movzx   r13d, al
0x1400a393f  shr     r13, 2
0x1400a3943  movsxd  rbx, esi
0x1400a3946  call    cs:__imp_W32GetUserSessionState
0x1400a394d  nop     dword ptr [rax+rax+00h]
0x1400a3952  mov     dl, [rax+r13+37C8h]
0x1400a395a  lea     ecx, [r12+r12]
0x1400a395e  mov     eax, 1
0x1400a3963  shl     eax, cl
0x1400a3965  test    al, dl
0x1400a3967  jz      short loc_1400A3977
0x1400a3969  mov     cl, [rbx+r14]
0x1400a396d  or      cl, 80h
0x1400a3970  movsxd  rax, r15d
0x1400a3973  mov     [rax+r14], cl
0x1400a3977  call    cs:__imp_W32GetUserSessionState
0x1400a397e  nop     dword ptr [rax+rax+00h]
0x1400a3983  mov     dl, [rax+r13+37C8h]
0x1400a398b  lea     ecx, ds:1[r12*2]
0x1400a3993  mov     eax, 1
0x1400a3998  shl     eax, cl
0x1400a399a  test    al, dl
0x1400a399c  jz      short loc_1400A39AC
0x1400a399e  mov     cl, [r14+rbx]
0x1400a39a2  or      cl, 1
0x1400a39a5  movsxd  rax, r15d
0x1400a39a8  mov     [rax+r14], cl
0x1400a39ac  lea     eax, [rsi+1]
0x1400a39af  mov     esi, eax
0x1400a39b1  mov     r15d, eax
0x1400a39b4  jmp     loc_1400A3923
0x1400a39b9  jmp     short loc_1400A3A0B
0x1400a39bb  mov     ebx, [rsp+148h+var_D4]
0x1400a39bf  jmp     short loc_1400A3A2A
0x1400a39c1  mov     ebx, r13d
0x1400a39c4  cmp     r15d, 8
0x1400a39c8  jnz     short loc_1400A3A2A
0x1400a39ca  xor     r8d, r8d
0x1400a39cd  mov     dl, 13h
0x1400a39cf  mov     rcx, qword ptr [rsp+148h+var_A0+8]
0x1400a39d7  call    HMValidateHandleWithDescriptor
0x1400a39dc  cmp     qword ptr [rsp+148h+var_58+8], r13
0x1400a39e4  jz      short loc_1400A39F3
0x1400a39e6  test    rax, rax
0x1400a39e9  jnz     short loc_1400A39F3
0x1400a39eb  lea     ecx, [rax+6]
0x1400a39ee  jmp     loc_1400A37F9
0x1400a39f3  lea     r8, [rsp+148h+var_48]
0x1400a39fb  mov     rdx, rax
0x1400a39fe  lea     rcx, [rsp+148h+var_78]
0x1400a3a06  call    ProcessKeyboardInjectedInput
0x1400a3a0b  mov     ebx, 1
0x1400a3a10  jmp     short loc_1400A3A2A
0x1400a3a12  xor     ebx, ebx
0x1400a3a14  mov     ecx, eax; Status
0x1400a3a16  call    cs:__imp_RtlNtStatusToDosError
0x1400a3a1d  nop     dword ptr [rax+rax+00h]
0x1400a3a22  mov     ecx, eax
0x1400a3a24  call    UserSetLastError
0x1400a3a29  nop
0x1400a3a2a  call    UserSessionSwitchLeaveCritWithNonPaged
0x1400a3a2f  mov     eax, ebx
0x1400a3a31  mov     rcx, [rsp+148h+var_38]
0x1400a3a39  xor     rcx, rsp; StackCookie
0x1400a3a3c  call    __security_check_cookie
0x1400a3a41  mov     rbx, [rsp+148h+arg_0]
0x1400a3a49  add     rsp, 120h
0x1400a3a50  pop     r15
0x1400a3a52  pop     r14
0x1400a3a54  pop     r13
0x1400a3a56  pop     r12
0x1400a3a58  pop     rsi
0x1400a3a59  retn
0x140239087  push    rbp
0x140239089  sub     rsp, 60h
0x14023908d  mov     rbp, rdx
0x140239090  mov     rax, [rcx]
0x140239093  mov     ecx, [rax]
0x140239095  mov     [rbp+78h], ecx
0x140239098  mov     ecx, [rbp+78h]
0x14023909b  call    SetLastNtError
0x1402390a0  mov     dword ptr [rbp+80h], 1
0x1402390aa  mov     eax, [rbp+80h]
0x1402390b0  add     rsp, 60h
0x1402390b4  pop     rbp
0x1402390b5  retn
0x1402390b7  push    rbp
0x1402390b9  sub     rsp, 60h
0x1402390bd  mov     rbp, rdx
0x1402390c0  mov     rax, [rcx]
0x1402390c3  mov     ecx, [rax]
0x1402390c5  mov     [rbp+68h], ecx
0x1402390c8  mov     ecx, [rbp+68h]
0x1402390cb  call    SetLastNtError
0x1402390d0  mov     dword ptr [rbp+70h], 1
0x1402390d7  mov     eax, [rbp+70h]
0x1402390da  add     rsp, 60h
0x1402390de  pop     rbp
0x1402390df  retn
```
