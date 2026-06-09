# NtMITSynthesizeKeyboardInput

- ea: `0x1400ee930`
- end: `0x1400eec5b`
- name: `NtMITSynthesizeKeyboardInput`
- size: `811`
- prototype: `__int64 __fastcall(__int64, void *, volatile void *)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update`

## callees

- `0x140029710`
- `0x14004ef20`
- `0x14004f380`
- `0x14004f4c0`
- `0x14004f550`
- `0x14006f3a4`
- `0x1400700d8`
- `0x1400ccd24`
- `0x1400ed060`
- `0x1400ee930`
- `0x1401a4458`
- `0x1401c7158`
- `0x1402388e0`
- `0x140238a40`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ee97e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ee97e`
- `ntoskrnl!ProbeForWrite` at `0x1400eeb0e`
- `ntoskrnl!ProbeForWrite` at `0x1400eeb0e`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400eeaed`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400eeaed`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1400eec16`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1400eec16`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ee96f`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ee96f`
- `WIN32K!W32GetUserSessionState` at `0x1400ee960`
- `WIN32K!W32GetUserSessionState` at `0x1400eeb46`
- `WIN32K!W32GetUserSessionState` at `0x1400eeb77`
- `WIN32K!W32GetUserSessionState` at `0x1400ee960`
- `WIN32K!W32GetUserSessionState` at `0x1400eeb46`
- `WIN32K!W32GetUserSessionState` at `0x1400eeb77`

## pseudocode

```c
__int64 __fastcall NtMITSynthesizeKeyboardInput(__int64 a1, void *a2, volatile void *a3)
{
  int v5; // r15d
  __int64 UserSessionState; // rsi
  struct _W32THREADNONPAGED *CurrentThreadWin32Thread; // rbx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 CurrentProcessWow64Process; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  int v17; // eax
  int v18; // esi
  int v19; // r15d
  int v20; // r12d
  unsigned __int64 v21; // r13
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rax
  _OWORD v26[4]; // [rsp+88h] [rbp-C0h] BYREF
  _OWORD v27[4]; // [rsp+D0h] [rbp-78h] BYREF

  v5 = a1;
  UserSessionState = W32GetUserSessionState(a1, a2, a3);
  CurrentThreadWin32Thread = (struct _W32THREADNONPAGED *)PsGetCurrentThreadWin32Thread();
  KeEnterCriticalRegion();
  _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(
    *(struct _FAST_ERESOURCE **)UserSessionState,
    CurrentThreadWin32Thread);
  v8 = *(_QWORD *)CurrentThreadWin32Thread;
  if ( *(_QWORD *)CurrentThreadWin32Thread )
    *(_BYTE *)(v8 + 1708) = 1;
  else
    v8 = 0;
  *(_QWORD *)(UserSessionState + 16) = v8;
  if ( v8 )
  {
    DestroySharedUserCritDeferredUnlockList(UserSessionState + 19520);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
  }
  memset(v27, 0, sizeof(v27));
  if ( (unsigned __int8)IsInputThread(v9) )
  {
    memset(v26, 0, sizeof(v26));
    RtlCopyFromUser(v26, a2, 0x40u);
    v27[0] = v26[0];
    v27[1] = v26[1];
    v27[2] = v26[2];
    v27[3] = v26[3];
    if ( v5 == 4 )
    {
      xxxUpdateGlobalsAndSendKeyEvent(
        DWORD2(v26[0]),
        v26[0],
        HIDWORD(v26[0]),
        0,
        *((__int64 *)&v26[2] + 1),
        0,
        v26[1],
        DWORD1(v26[0]) != 0,
        0,
        0,
        0,
        (__int64)&v27[3]);
      if ( a3 )
      {
        CurrentProcessWow64Process = PsGetCurrentProcessWow64Process();
        ProbeForWrite(a3, 0x100u, CurrentProcessWow64Process != 0 ? 1 : 4);
        LOBYTE(v17) = 0;
        v18 = 0;
        v19 = 0;
        while ( v18 < 256 )
        {
          v20 = v17 & 3;
          v21 = (unsigned __int64)(unsigned __int8)v17 >> 2;
          LOBYTE(v22) = *(_BYTE *)(W32GetUserSessionState(v12, v15, v16) + v21 + 14280);
          if ( ((unsigned __int8)v22 & (unsigned __int8)(1 << (2 * v20))) != 0 )
            *((_BYTE *)a3 + v19) = *((_BYTE *)a3 + v18) | 0x80;
          LOBYTE(v15) = *(_BYTE *)(W32GetUserSessionState((unsigned int)(2 * v20), v22, v23) + v21 + 14280);
          v12 = (unsigned int)(2 * v20 + 1);
          if ( ((unsigned __int8)v15 & (unsigned __int8)(1 << (2 * v20 + 1))) != 0 )
          {
            LOBYTE(v12) = *((_BYTE *)a3 + v18) | 1;
            *((_BYTE *)a3 + v19) = v12;
          }
          v17 = v18 + 1;
          v18 = v17;
          v19 = v17;
        }
      }
    }
    else
    {
      v11 = 0;
      if ( v5 != 8 )
        goto LABEL_25;
      LOBYTE(v13) = 19;
      v24 = HMValidateHandleWithDescriptor(*((_QWORD *)&v26[2] + 1), v13, 0);
      if ( *((_QWORD *)&v27[2] + 1) && !v24 )
      {
        v10 = 6;
        goto LABEL_8;
      }
      ProcessKeyboardInjectedInput(v27, v24, &v27[3]);
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
0x1400ee930  mov     [rsp+arg_0], rbx
0x1400ee935  push    rsi
0x1400ee936  push    r12
0x1400ee938  push    r13
0x1400ee93a  push    r14
0x1400ee93c  push    r15
0x1400ee93e  sub     rsp, 120h
0x1400ee945  mov     rax, cs:__security_cookie
0x1400ee94c  xor     rax, rsp
0x1400ee94f  mov     [rsp+148h+var_38], rax
0x1400ee957  mov     r14, r8
0x1400ee95a  mov     r12, rdx
0x1400ee95d  mov     r15d, ecx
0x1400ee960  call    cs:__imp_W32GetUserSessionState
0x1400ee967  nop     dword ptr [rax+rax+00h]
0x1400ee96c  mov     rsi, rax
0x1400ee96f  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400ee976  nop     dword ptr [rax+rax+00h]
0x1400ee97b  mov     rbx, rax
0x1400ee97e  call    cs:__imp_KeEnterCriticalRegion
0x1400ee985  nop     dword ptr [rax+rax+00h]
0x1400ee98a  mov     rdx, rbx; struct _W32THREADNONPAGED *
0x1400ee98d  mov     rcx, [rsi]; struct _FAST_ERESOURCE *
0x1400ee990  call    ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1400ee995  mov     rdx, [rbx]
0x1400ee998  xor     r13d, r13d
0x1400ee99b  test    rdx, rdx
0x1400ee99e  jnz     short loc_1400EE9A5
0x1400ee9a0  mov     edx, r13d
0x1400ee9a3  jmp     short loc_1400EE9AC
0x1400ee9a5  mov     byte ptr [rdx+6ACh], 1
0x1400ee9ac  mov     [rsi+10h], rdx
0x1400ee9b0  test    rdx, rdx
0x1400ee9b3  jz      short loc_1400EE9D6
0x1400ee9b5  lea     rbx, [rsi+4C40h]
0x1400ee9bc  mov     rcx, rbx
0x1400ee9bf  call    DestroySharedUserCritDeferredUnlockList
0x1400ee9c4  lea     rcx, [rbx+38h]
0x1400ee9c8  call    DestroyDeferredUnlockObjectAssignmentList
0x1400ee9cd  lea     rcx, [rbx+28h]
0x1400ee9d1  call    DestroyDeferredUnlockObjectAssignmentList
0x1400ee9d6  mov     ebx, 40h ; '@'
0x1400ee9db  mov     r8d, ebx; Size
0x1400ee9de  xor     edx, edx; Val
0x1400ee9e0  lea     rcx, [rsp+148h+var_78]; void *
0x1400ee9e8  call    memset
0x1400ee9ed  call    IsInputThread
0x1400ee9f2  test    al, al
0x1400ee9f4  jnz     short loc_1400EEA06
0x1400ee9f6  lea     ecx, [rbx-3Bh]
0x1400ee9f9  mov     ebx, r13d
0x1400ee9fc  call    UserSetLastError
0x1400eea01  jmp     loc_1400EEC2A
0x1400eea06  mov     r8, rbx; Size
0x1400eea09  xor     edx, edx; Val
0x1400eea0b  lea     rcx, [rsp+148h+var_C0]; void *
0x1400eea13  call    memset
0x1400eea18  mov     r8, rbx; Size
0x1400eea1b  mov     rdx, r12; Src
0x1400eea1e  lea     rcx, [rsp+148h+var_C0]; void *
0x1400eea26  call    RtlCopyFromUser
0x1400eea2b  movups  xmm0, [rsp+148h+var_C0]
0x1400eea33  movaps  [rsp+148h+var_78], xmm0
0x1400eea3b  movups  xmm1, [rsp+148h+var_B0]
0x1400eea43  movaps  [rsp+148h+var_68], xmm1
0x1400eea4b  movups  xmm0, [rsp+148h+var_A0]
0x1400eea53  movaps  [rsp+148h+var_58], xmm0
0x1400eea5b  movups  xmm1, [rsp+148h+var_90]
0x1400eea63  movaps  [rsp+148h+var_48], xmm1
0x1400eea6b  cmp     r15d, 4
0x1400eea6f  jnz     loc_1400EEBC1
0x1400eea75  mov     [rsp+148h+var_D4], r13d
0x1400eea7a  mov     rdx, qword ptr [rsp+148h+var_C0]
0x1400eea82  mov     rax, rdx
0x1400eea85  shr     rax, 20h
0x1400eea89  test    eax, eax
0x1400eea8b  setnz   al
0x1400eea8e  mov     rcx, qword ptr [rsp+148h+var_C0+8]
0x1400eea96  mov     r8, rcx
0x1400eea99  shr     r8, 20h
0x1400eea9d  lea     r9, [rsp+148h+var_48]
0x1400eeaa5  mov     [rsp+148h+var_F0], r9
0x1400eeaaa  mov     [rsp+148h+var_F8], r13
0x1400eeaaf  mov     [rsp+148h+var_100], r13
0x1400eeab4  mov     [rsp+148h+var_108], r13b
0x1400eeab9  mov     [rsp+148h+var_110], al
0x1400eeabd  movzx   eax, word ptr [rsp+148h+var_B0]
0x1400eeac5  mov     [rsp+148h+var_118], ax
0x1400eeaca  mov     [rsp+148h+var_120], r13
0x1400eeacf  mov     rax, qword ptr [rsp+148h+var_A0+8]
0x1400eead7  mov     [rsp+148h+var_128], rax
0x1400eeadc  xor     r9d, r9d
0x1400eeadf  call    xxxUpdateGlobalsAndSendKeyEvent
0x1400eeae4  test    r14, r14
0x1400eeae7  jz      loc_1400EEC0B
0x1400eeaed  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1400eeaf4  nop     dword ptr [rax+rax+00h]
0x1400eeaf9  neg     rax
0x1400eeafc  sbb     r8d, r8d
0x1400eeaff  and     r8d, 0FFFFFFFDh
0x1400eeb03  add     r8d, r15d; Alignment
0x1400eeb06  mov     edx, 100h; Length
0x1400eeb0b  mov     rcx, r14; Address
0x1400eeb0e  call    cs:__imp_ProbeForWrite
0x1400eeb15  nop     dword ptr [rax+rax+00h]
0x1400eeb1a  mov     eax, r13d
0x1400eeb1d  mov     esi, r13d
0x1400eeb20  mov     r15d, r13d
0x1400eeb23  mov     [rsp+148h+var_E8], eax
0x1400eeb27  cmp     esi, 100h
0x1400eeb2d  jge     loc_1400EEBB9
0x1400eeb33  movzx   r12d, al
0x1400eeb37  and     r12d, 3
0x1400eeb3b  movzx   r13d, al
0x1400eeb3f  shr     r13, 2
0x1400eeb43  movsxd  rbx, esi
0x1400eeb46  call    cs:__imp_W32GetUserSessionState
0x1400eeb4d  nop     dword ptr [rax+rax+00h]
0x1400eeb52  mov     dl, [rax+r13+37C8h]
0x1400eeb5a  lea     ecx, [r12+r12]
0x1400eeb5e  mov     eax, 1
0x1400eeb63  shl     eax, cl
0x1400eeb65  test    al, dl
0x1400eeb67  jz      short loc_1400EEB77
0x1400eeb69  mov     cl, [rbx+r14]
0x1400eeb6d  or      cl, 80h
0x1400eeb70  movsxd  rax, r15d
0x1400eeb73  mov     [rax+r14], cl
0x1400eeb77  call    cs:__imp_W32GetUserSessionState
0x1400eeb7e  nop     dword ptr [rax+rax+00h]
0x1400eeb83  mov     dl, [rax+r13+37C8h]
0x1400eeb8b  lea     ecx, ds:1[r12*2]
0x1400eeb93  mov     eax, 1
0x1400eeb98  shl     eax, cl
0x1400eeb9a  test    al, dl
0x1400eeb9c  jz      short loc_1400EEBAC
0x1400eeb9e  mov     cl, [r14+rbx]
0x1400eeba2  or      cl, 1
0x1400eeba5  movsxd  rax, r15d
0x1400eeba8  mov     [rax+r14], cl
0x1400eebac  lea     eax, [rsi+1]
0x1400eebaf  mov     esi, eax
0x1400eebb1  mov     r15d, eax
0x1400eebb4  jmp     loc_1400EEB23
0x1400eebb9  jmp     short loc_1400EEC0B
0x1400eebbb  mov     ebx, [rsp+148h+var_D4]
0x1400eebbf  jmp     short loc_1400EEC2A
0x1400eebc1  mov     ebx, r13d
0x1400eebc4  cmp     r15d, 8
0x1400eebc8  jnz     short loc_1400EEC2A
0x1400eebca  xor     r8d, r8d
0x1400eebcd  mov     dl, 13h
0x1400eebcf  mov     rcx, qword ptr [rsp+148h+var_A0+8]
0x1400eebd7  call    HMValidateHandleWithDescriptor
0x1400eebdc  cmp     qword ptr [rsp+148h+var_58+8], r13
0x1400eebe4  jz      short loc_1400EEBF3
0x1400eebe6  test    rax, rax
0x1400eebe9  jnz     short loc_1400EEBF3
0x1400eebeb  lea     ecx, [rax+6]
0x1400eebee  jmp     loc_1400EE9F9
0x1400eebf3  lea     r8, [rsp+148h+var_48]
0x1400eebfb  mov     rdx, rax
0x1400eebfe  lea     rcx, [rsp+148h+var_78]
0x1400eec06  call    ProcessKeyboardInjectedInput
0x1400eec0b  mov     ebx, 1
0x1400eec10  jmp     short loc_1400EEC2A
0x1400eec12  xor     ebx, ebx
0x1400eec14  mov     ecx, eax; Status
0x1400eec16  call    cs:__imp_RtlNtStatusToDosError
0x1400eec1d  nop     dword ptr [rax+rax+00h]
0x1400eec22  mov     ecx, eax
0x1400eec24  call    UserSetLastError
0x1400eec29  nop
0x1400eec2a  call    UserSessionSwitchLeaveCritWithNonPaged
0x1400eec2f  mov     eax, ebx
0x1400eec31  mov     rcx, [rsp+148h+var_38]
0x1400eec39  xor     rcx, rsp; StackCookie
0x1400eec3c  call    __security_check_cookie
0x1400eec41  mov     rbx, [rsp+148h+arg_0]
0x1400eec49  add     rsp, 120h
0x1400eec50  pop     r15
0x1400eec52  pop     r14
0x1400eec54  pop     r13
0x1400eec56  pop     r12
0x1400eec58  pop     rsi
0x1400eec59  retn
0x1402398ba  push    rbp
0x1402398bc  sub     rsp, 60h
0x1402398c0  mov     rbp, rdx
0x1402398c3  mov     rax, [rcx]
0x1402398c6  mov     ecx, [rax]
0x1402398c8  mov     [rbp+78h], ecx
0x1402398cb  mov     ecx, [rbp+78h]
0x1402398ce  call    SetLastNtError
0x1402398d3  mov     dword ptr [rbp+80h], 1
0x1402398dd  mov     eax, [rbp+80h]
0x1402398e3  add     rsp, 60h
0x1402398e7  pop     rbp
0x1402398e8  retn
0x1402398ea  push    rbp
0x1402398ec  sub     rsp, 60h
0x1402398f0  mov     rbp, rdx
0x1402398f3  mov     rax, [rcx]
0x1402398f6  mov     ecx, [rax]
0x1402398f8  mov     [rbp+68h], ecx
0x1402398fb  mov     ecx, [rbp+68h]
0x1402398fe  call    SetLastNtError
0x140239903  mov     dword ptr [rbp+70h], 1
0x14023990a  mov     eax, [rbp+70h]
0x14023990d  add     rsp, 60h
0x140239911  pop     rbp
0x140239912  retn
```
