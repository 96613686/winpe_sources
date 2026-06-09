# UbpmpTerminateNonHostedTask

- ea: `0x180017e88`
- end: `0x18001824b`
- name: `UbpmpTerminateNonHostedTask`
- size: `963`
- prototype: `__int64 __fastcall(struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)`
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, service_task`

## callers

- `0x180002fcc`
- `0x180008f30`

## callees

- `0x18000a014`
- `0x18000a570`
- `0x18000a6e0`
- `0x180017e88`
- `0x180018afc`
- `0x180019d90`
- `0x18001fd00`
- `0x180021060`
- `0x180023e04`
- `0x180023f68`
- `0x180030cec`
- `0x180032e38`
- `0x18003cbc0`
- `0x18003d7de`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180017f47`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018033`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180017f47`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018033`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800181a7`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800181a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800181d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800181d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018240`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018240`

## pseudocode

```c
__int64 __fastcall UbpmpTerminateNonHostedTask(struct _UBPM_TASK_HOST_CONTEXT_BLOCK *a1, __int64 a2)
{
  unsigned int v4; // esi
  __int64 v5; // r12
  __int64 v6; // r13
  bool v7; // zf
  void *v8; // r14
  int v9; // eax
  __int64 v10; // rax
  void **v11; // rdx
  int v12; // ecx
  int v13; // eax
  DWORD LastError; // eax
  int v16; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v19; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v20; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v21; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v22; // [rsp+68h] [rbp-98h] BYREF
  struct _UBPM_TASK_HOST_TASK_CONTEXT *v23; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v24[7]; // [rsp+80h] [rbp-80h] BYREF
  int v25; // [rsp+B8h] [rbp-48h]
  __int64 v26; // [rsp+C0h] [rbp-40h]
  __int64 v27; // [rsp+C8h] [rbp-38h]
  int v28; // [rsp+D0h] [rbp-30h]
  int v29; // [rsp+D4h] [rbp-2Ch]
  _QWORD v30[3]; // [rsp+130h] [rbp+30h] BYREF
  int v31; // [rsp+14Ch] [rbp+4Ch]
  int v32; // [rsp+150h] [rbp+50h]
  char v33; // [rsp+154h] [rbp+54h]

  v19 = 0;
  v4 = 87;
  v23 = 0;
  v21 = 0;
  v22 = 0;
  v5 = 0;
  hObject = 0;
  v20 = 0;
  v6 = 0;
  memset_0(v24, 0, 0xA8u);
  memset_0(v30, 0, 0x68u);
  v7 = (*((_BYTE *)a1 + 104) & 0x10) == 0;
  v17 = 0;
  v16 = 0;
  if ( v7 )
  {
    v8 = 0;
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)((char *)a1 + 64));
    if ( *((_WORD *)a1 + 138) != 1 )
    {
      *((_WORD *)a1 + 138) = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 186);
    }
    *((_DWORD *)a1 + 18) = 0;
    RtlReleaseSRWLockExclusive((char *)a1 + 64);
    v9 = UbpmpReadContextBlock((__int64)a1, &v16, &v21, &v22, &hObject, &v17, &v20);
    v5 = v21;
    v6 = v22;
    if ( !v9 )
    {
      v24[3] = v20;
      v25 = v16;
      v10 = *(_QWORD *)(a2 + 32);
      v24[0] = a2;
      v26 = v21;
      v27 = v22;
      v29 = v10 ? *(_DWORD *)(v10 + 20) : 0;
      v28 = v17;
      v11 = (void **)((unsigned __int64)&hObject & -(__int64)(hObject != 0));
      v12 = **(_DWORD **)(a2 + 24);
      v19 = 0;
      v23 = 0;
      if ( (unsigned int)(v12 - 1) > 1 )
        v13 = v12 == 3 ? UbpmLaunchTaskSignal((__int64)v24, v11) : UbpmLaunchTaskPublish((__int64)v24, v11);
      else
        v13 = UbpmpHostLaunchTaskExe((struct _UBPM_TASK_LAUNCH_INPUT_PARAMS *)v24, v11, &v19, &v23);
      if ( v13 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          187,
          WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
          *((unsigned int *)a1 + 8),
          v13);
    }
    v4 = 0;
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)((char *)a1 + 64));
    if ( (*((_BYTE *)a1 + 104) & 4) == 0 )
    {
      v31 = 0;
      v30[0] = UbpmpDelayedTerminateProcessCallback;
      v30[1] = *((_QWORD *)a1 + 3);
      v33 = 0;
      v32 = 1;
      v4 = UbpmUtilsSubmitThreadPoolTimer((struct _UBPM_UTILS_TIMER_INPARAMS *)v30, 0);
      if ( v4 )
      {
        if ( TerminateProcess(*((HANDLE *)a1 + 3), 0x42Bu) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              189,
              WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
              *((unsigned int *)a1 + 8));
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            188,
            WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
            *((unsigned int *)a1 + 8),
            LastError);
        }
      }
      else
      {
        *((_QWORD *)a1 + 3) = 0;
      }
      v8 = (void *)*((_QWORD *)a1 + 5);
      *((_QWORD *)a1 + 5) = 0;
    }
    *((_DWORD *)a1 + 18) = 0;
    RtlReleaseSRWLockExclusive((char *)a1 + 64);
    if ( v8 )
      UbpmpTaskHostTerminationCleanup(a1, v8);
    if ( v19 )
      UbpmpHostCloseTaskHostContext();
    if ( hObject )
      CloseHandle(hObject);
  }
  UBPM_MIDL_user_free(v5);
  UBPM_MIDL_user_free(v6);
  UBPM_MIDL_user_free(v20);
  return v4;
}

```

## disassembly

```asm
0x180017e88  mov     [rsp-8+arg_10], rbx
0x180017e8d  push    rbp
0x180017e8e  push    rsi
0x180017e8f  push    rdi
0x180017e90  push    r12
0x180017e92  push    r13
0x180017e94  push    r14
0x180017e96  push    r15
0x180017e98  lea     rbp, [rsp-0B0h]
0x180017ea0  sub     rsp, 1B0h
0x180017ea7  mov     rax, cs:__security_cookie
0x180017eae  xor     rax, rsp
0x180017eb1  mov     [rbp+0E0h+var_40], rax
0x180017eb8  xor     edi, edi
0x180017eba  mov     r15, rdx
0x180017ebd  mov     rbx, rcx
0x180017ec0  mov     [rsp+1E0h+var_190], rdi
0x180017ec5  mov     esi, 57h ; 'W'
0x180017eca  mov     [rsp+1E0h+var_170], rdi
0x180017ecf  xor     edx, edx; Val
0x180017ed1  mov     [rsp+1E0h+var_180], rdi
0x180017ed6  lea     rcx, [rbp+0E0h+var_160]; void *
0x180017eda  mov     [rsp+1E0h+var_178], rdi
0x180017edf  mov     r12d, edi
0x180017ee2  mov     [rsp+1E0h+hObject], rdi
0x180017ee7  lea     r8d, [rsi+51h]; Size
0x180017eeb  mov     [rsp+1E0h+var_188], rdi
0x180017ef0  mov     r13d, edi
0x180017ef3  call    memset_0
0x180017ef8  xor     edx, edx; Val
0x180017efa  lea     r8d, [rsi+11h]; Size
0x180017efe  lea     rcx, [rbp+0E0h+var_B0]; void *
0x180017f02  call    memset_0
0x180017f07  test    byte ptr [rbx+68h], 10h
0x180017f0b  mov     [rsp+1E0h+var_19C], edi
0x180017f0f  mov     [rsp+1E0h+var_1A0], edi
0x180017f13  jnz     loc_180018066
0x180017f19  mov     r14d, edi
0x180017f1c  lea     rdi, [rbx+40h]
0x180017f20  mov     rcx, rdi; struct _UBPM_SRWLOCK *
0x180017f23  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x180017f28  lea     eax, [r14+1]
0x180017f2c  lea     rsi, WPP_GLOBAL_Control
0x180017f33  cmp     [rbx+114h], ax
0x180017f3a  jnz     loc_1800180FC
0x180017f40  mov     rcx, rdi
0x180017f43  mov     [rdi+8], r12d
0x180017f47  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180017f4d  lea     rax, [rsp+1E0h+var_188]
0x180017f52  mov     rcx, rbx
0x180017f55  mov     [rsp+1E0h+var_1B0], rax
0x180017f5a  lea     r9, [rsp+1E0h+var_178]
0x180017f5f  lea     rax, [rsp+1E0h+var_19C]
0x180017f64  mov     [rsp+1E0h+var_1B8], rax
0x180017f69  lea     r8, [rsp+1E0h+var_180]
0x180017f6e  lea     rax, [rsp+1E0h+hObject]
0x180017f73  lea     rdx, [rsp+1E0h+var_1A0]
0x180017f78  mov     [rsp+1E0h+var_1C0], rax
0x180017f7d  call    UbpmpReadContextBlock
0x180017f82  mov     r12, [rsp+1E0h+var_180]
0x180017f87  mov     r13, [rsp+1E0h+var_178]
0x180017f8c  test    eax, eax
0x180017f8e  jnz     loc_1800180F4
0x180017f94  mov     rax, [rsp+1E0h+var_188]
0x180017f99  mov     [rbp+0E0h+var_148], rax
0x180017f9d  mov     eax, [rsp+1E0h+var_1A0]
0x180017fa1  mov     [rbp+0E0h+var_128], eax
0x180017fa4  mov     rax, [r15+20h]
0x180017fa8  mov     [rbp+0E0h+var_160], r15
0x180017fac  mov     [rbp+0E0h+var_120], r12
0x180017fb0  mov     [rbp+0E0h+var_118], r13
0x180017fb4  test    rax, rax
0x180017fb7  jz      loc_18001814F
0x180017fbd  mov     eax, [rax+14h]
0x180017fc0  mov     [rbp+0E0h+var_10C], eax
0x180017fc3  mov     eax, [rsp+1E0h+var_19C]
0x180017fc7  mov     [rbp+0E0h+var_110], eax
0x180017fca  mov     rax, [rsp+1E0h+hObject]
0x180017fcf  neg     rax
0x180017fd2  lea     rax, [rsp+1E0h+hObject]
0x180017fd7  sbb     rdx, rdx
0x180017fda  and     rdx, rax; void **
0x180017fdd  mov     rax, [r15+18h]
0x180017fe1  xor     r15d, r15d
0x180017fe4  mov     ecx, [rax]
0x180017fe6  mov     [rsp+1E0h+var_190], r15
0x180017feb  mov     [rsp+1E0h+var_170], r15
0x180017ff0  lea     eax, [rcx-1]
0x180017ff3  cmp     eax, 1
0x180017ff6  ja      loc_18001813C
0x180017ffc  lea     r9, [rsp+1E0h+var_170]; struct _UBPM_TASK_HOST_TASK_CONTEXT **
0x180018001  lea     r8, [rsp+1E0h+var_190]; struct _UBPM_TASK_HOST_CONTEXT_BLOCK **
0x180018006  lea     rcx, [rbp+0E0h+var_160]; struct _UBPM_TASK_LAUNCH_INPUT_PARAMS *
0x18001800a  call    ?UbpmpHostLaunchTaskExe@@YAKPEAU_UBPM_TASK_LAUNCH_INPUT_PARAMS@@PEAPEAXPEAPEAU_UBPM_TASK_HOST_CONTEXT_BLOCK@@PEAPEAU_UBPM_TASK_HOST_TASK_CONTEXT@@@Z; UbpmpHostLaunchTaskExe(_UBPM_TASK_LAUNCH_INPUT_PARAMS *,void * *,_UBPM_TASK_HOST_CONTEXT_BLOCK * *,_UBPM_TASK_HOST_TASK_CONTEXT * *)
0x18001800f  test    eax, eax
0x180018011  jnz     loc_180018162
0x180018017  mov     rcx, rdi; struct _UBPM_SRWLOCK *
0x18001801a  mov     esi, r15d
0x18001801d  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x180018022  test    byte ptr [rbx+68h], 4
0x180018026  jz      loc_1800180AC
0x18001802c  mov     rcx, rdi
0x18001802f  mov     [rdi+8], r15d
0x180018033  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180018039  test    r14, r14
0x18001803c  jz      short loc_180018049
0x18001803e  mov     rdx, r14; WaitHandle
0x180018041  mov     rcx, rbx; struct _UBPM_TASK_HOST_CONTEXT_BLOCK *
0x180018044  call    ?UbpmpTaskHostTerminationCleanup@@YAXPEAU_UBPM_TASK_HOST_CONTEXT_BLOCK@@PEAX@Z; UbpmpTaskHostTerminationCleanup(_UBPM_TASK_HOST_CONTEXT_BLOCK *,void *)
0x180018049  mov     rcx, [rsp+1E0h+var_190]
0x18001804e  test    rcx, rcx
0x180018051  jz      short loc_180018058
0x180018053  call    UbpmpHostCloseTaskHostContext
0x180018058  mov     rcx, [rsp+1E0h+hObject]; hObject
0x18001805d  test    rcx, rcx
0x180018060  jnz     loc_180018240
0x180018066  mov     rcx, r12
0x180018069  call    UBPM_MIDL_user_free
0x18001806e  mov     rcx, r13
0x180018071  call    UBPM_MIDL_user_free
0x180018076  mov     rcx, [rsp+1E0h+var_188]
0x18001807b  call    UBPM_MIDL_user_free
0x180018080  mov     eax, esi
0x180018082  mov     rcx, [rbp+0E0h+var_40]
0x180018089  xor     rcx, rsp; StackCookie
0x18001808c  call    __security_check_cookie
0x180018091  mov     rbx, [rsp+1E0h+arg_10]
0x180018099  add     rsp, 1B0h
0x1800180a0  pop     r15
0x1800180a2  pop     r14
0x1800180a4  pop     r13
0x1800180a6  pop     r12
0x1800180a8  pop     rdi
0x1800180a9  pop     rsi
0x1800180aa  pop     rbp
0x1800180ab  retn
0x1800180ac  lea     rax, UbpmpDelayedTerminateProcessCallback
0x1800180b3  mov     [rbp+0E0h+var_94], r15d
0x1800180b7  mov     [rbp+0E0h+var_B0], rax
0x1800180bb  lea     rcx, [rbp+0E0h+var_B0]; struct _UBPM_UTILS_TIMER_INPARAMS *
0x1800180bf  mov     rax, [rbx+18h]
0x1800180c3  xor     edx, edx; void **
0x1800180c5  mov     [rbp+0E0h+var_A8], rax
0x1800180c9  mov     [rbp+0E0h+var_8C], r15b
0x1800180cd  mov     [rbp+0E0h+var_90], 1
0x1800180d4  call    ?UbpmUtilsSubmitThreadPoolTimer@@YAKPEAU_UBPM_UTILS_TIMER_INPARAMS@@PEAPEAX@Z; UbpmUtilsSubmitThreadPoolTimer(_UBPM_UTILS_TIMER_INPARAMS *,void * *)
0x1800180d9  mov     esi, eax
0x1800180db  test    eax, eax
0x1800180dd  jnz     loc_18001819E
0x1800180e3  mov     [rbx+18h], r15
0x1800180e7  mov     r14, [rbx+28h]
0x1800180eb  mov     [rbx+28h], r15
0x1800180ef  jmp     loc_18001802C
0x1800180f4  xor     r15d, r15d
0x1800180f7  jmp     loc_180018017
0x1800180fc  xor     eax, eax
0x1800180fe  mov     [rbx+114h], ax
0x180018105  mov     rcx, cs:WPP_GLOBAL_Control
0x18001810c  cmp     rcx, rsi
0x18001810f  jz      loc_180017F40
0x180018115  test    byte ptr [rcx+1Ch], 80h
0x180018119  jz      loc_180017F40
0x18001811f  mov     eax, [rbx+20h]
0x180018122  mov     edx, 0BAh
0x180018127  mov     rcx, [rcx+10h]
0x18001812b  mov     r9, rbx
0x18001812e  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x180018132  call    WPP_SF_qd
0x180018137  jmp     loc_180017F40
0x18001813c  cmp     ecx, 3
0x18001813f  lea     rcx, [rbp+0E0h+var_160]
0x180018143  jnz     short loc_180018158
0x180018145  call    UbpmLaunchTaskSignal
0x18001814a  jmp     loc_18001800F
0x18001814f  mov     [rbp+0E0h+var_10C], r14d
0x180018153  jmp     loc_180017FC3
0x180018158  call    UbpmLaunchTaskPublish
0x18001815d  jmp     loc_18001800F
0x180018162  mov     rcx, cs:WPP_GLOBAL_Control
0x180018169  cmp     rcx, rsi
0x18001816c  jz      loc_180018017
0x180018172  test    byte ptr [rcx+1Ch], 2
0x180018176  jz      loc_180018017
0x18001817c  mov     r9d, [rbx+20h]
0x180018180  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180018187  mov     rcx, [rcx+10h]
0x18001818b  mov     edx, 0BBh
0x180018190  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x180018194  call    WPP_SF_dd
0x180018199  jmp     loc_180018017
0x18001819e  mov     rcx, [rbx+18h]; hProcess
0x1800181a2  mov     edx, 42Bh; uExitCode
0x1800181a7  call    cs:__imp_TerminateProcess
0x1800181ad  test    eax, eax
0x1800181af  jnz     short loc_180018201
0x1800181b1  mov     rax, cs:WPP_GLOBAL_Control
0x1800181b8  lea     rdx, WPP_GLOBAL_Control
0x1800181bf  cmp     rax, rdx
0x1800181c2  jz      loc_1800180E7
0x1800181c8  test    byte ptr [rax+1Ch], 2
0x1800181cc  jz      loc_1800180E7
0x1800181d2  call    cs:__imp_GetLastError
0x1800181d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800181df  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x1800181e6  mov     r9d, [rbx+20h]
0x1800181ea  mov     edx, 0BCh
0x1800181ef  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x1800181f3  mov     rcx, [rcx+10h]
0x1800181f7  call    WPP_SF_dd
0x1800181fc  jmp     loc_1800180E7
0x180018201  mov     rcx, cs:WPP_GLOBAL_Control
0x180018208  lea     rdx, WPP_GLOBAL_Control
0x18001820f  cmp     rcx, rdx
0x180018212  jz      loc_1800180E7
0x180018218  test    byte ptr [rcx+1Ch], 80h
0x18001821c  jz      loc_1800180E7
0x180018222  mov     r9d, [rbx+20h]
0x180018226  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18001822d  mov     rcx, [rcx+10h]
0x180018231  mov     edx, 0BDh
0x180018236  call    WPP_SF_d
0x18001823b  jmp     loc_1800180E7
0x180018240  call    cs:__imp_CloseHandle
0x180018246  jmp     loc_180018066
```
