# UbpmpTerminateNonHostedTask

- ea: `0x18000d9bc`
- end: `0x18000dd9e`
- name: `UbpmpTerminateNonHostedTask`
- size: `994`
- prototype: `__int64 __fastcall(struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)`
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, service_task`

## callers

- `0x1800033b0`
- `0x180009a30`

## callees

- `0x18000480c`
- `0x18000d9bc`
- `0x18000e6bc`
- `0x18000fbf0`
- `0x180010220`
- `0x1800103c0`
- `0x18001bf54`
- `0x18001c3f0`
- `0x18001da20`
- `0x18002ce98`
- `0x180032f78`
- `0x1800351ec`
- `0x18003f5b4`
- `0x18004022e`
- `0x180040260`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000da7b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000db6d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000da7b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000db6d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000dce8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000dce8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dd8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dd8d`

## pseudocode

```c
__int64 __fastcall UbpmpTerminateNonHostedTask(struct _UBPM_TASK_HOST_CONTEXT_BLOCK *a1, __int64 a2)
{
  unsigned int v4; // esi
  __int64 v5; // r12
  __int64 v6; // r13
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  bool v10; // zf
  void *v11; // r14
  __int64 v12; // r8
  int v13; // eax
  __int64 v14; // r8
  __int64 v15; // rax
  void **v16; // rdx
  int v17; // ecx
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  int v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v29; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v30; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h] BYREF
  struct _UBPM_TASK_HOST_TASK_CONTEXT *v33; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v34[7]; // [rsp+80h] [rbp-80h] BYREF
  int v35; // [rsp+B8h] [rbp-48h]
  __int64 v36; // [rsp+C0h] [rbp-40h]
  __int64 v37; // [rsp+C8h] [rbp-38h]
  int v38; // [rsp+D0h] [rbp-30h]
  int v39; // [rsp+D4h] [rbp-2Ch]
  _QWORD v40[3]; // [rsp+130h] [rbp+30h] BYREF
  int v41; // [rsp+14Ch] [rbp+4Ch]
  int v42; // [rsp+150h] [rbp+50h]
  char v43; // [rsp+154h] [rbp+54h]

  v29 = 0;
  v4 = 87;
  v33 = 0;
  v31 = 0;
  v32 = 0;
  v5 = 0;
  hObject = 0;
  v30 = 0;
  v6 = 0;
  memset_0(v34, 0, 0xA8u);
  memset_0(v40, 0, 0x68u);
  v10 = (*((_BYTE *)a1 + 104) & 0x10) == 0;
  v27 = 0;
  v26 = 0;
  if ( v10 )
  {
    v11 = 0;
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)((char *)a1 + 64));
    if ( *((_WORD *)a1 + 138) != 1 )
    {
      *((_WORD *)a1 + 138) = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 186, v12, a1, *((_DWORD *)a1 + 8));
    }
    *((_DWORD *)a1 + 18) = 0;
    RtlReleaseSRWLockExclusive((char *)a1 + 64);
    v13 = UbpmpReadContextBlock((__int64)a1, &v26, &v31, &v32, &hObject, &v27, &v30);
    v5 = v31;
    v6 = v32;
    if ( !v13 )
    {
      v34[3] = v30;
      v35 = v26;
      v15 = *(_QWORD *)(a2 + 32);
      v34[0] = a2;
      v36 = v31;
      v37 = v32;
      v39 = v15 ? *(_DWORD *)(v15 + 20) : 0;
      v38 = v27;
      v16 = (void **)((unsigned __int64)&hObject & -(__int64)(hObject != 0));
      v17 = **(_DWORD **)(a2 + 24);
      v29 = 0;
      v33 = 0;
      if ( (unsigned int)(v17 - 1) > 1 )
        v18 = v17 == 3 ? UbpmLaunchTaskSignal(v34, v16, v14) : UbpmLaunchTaskPublish(v34, v16, v14);
      else
        v18 = UbpmpHostLaunchTaskExe((struct _UBPM_TASK_LAUNCH_INPUT_PARAMS *)v34, v16, &v29, &v33);
      if ( v18 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          187,
          WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
          *((unsigned int *)a1 + 8));
    }
    v4 = 0;
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)((char *)a1 + 64));
    if ( (*((_BYTE *)a1 + 104) & 4) == 0 )
    {
      v41 = 0;
      v40[0] = UbpmpDelayedTerminateProcessCallback;
      v40[1] = *((_QWORD *)a1 + 3);
      v43 = 0;
      v42 = 1;
      v4 = UbpmUtilsSubmitThreadPoolTimer((struct _UBPM_UTILS_TIMER_INPARAMS *)v40, 0);
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
          GetLastError();
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            188,
            WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
            *((unsigned int *)a1 + 8));
        }
      }
      else
      {
        *((_QWORD *)a1 + 3) = 0;
      }
      v11 = (void *)*((_QWORD *)a1 + 5);
      *((_QWORD *)a1 + 5) = 0;
    }
    *((_DWORD *)a1 + 18) = 0;
    RtlReleaseSRWLockExclusive((char *)a1 + 64);
    if ( v11 )
      UbpmpTaskHostTerminationCleanup(a1, v11);
    if ( v29 )
      UbpmpHostCloseTaskHostContext(v29);
    if ( hObject )
      CloseHandle(hObject);
  }
  UBPM_MIDL_user_free(v5, v7, v8, v9);
  UBPM_MIDL_user_free(v6, v19, v20, v21);
  UBPM_MIDL_user_free(v30, v22, v23, v24);
  return v4;
}

```

## disassembly

```asm
0x18000d9bc  mov     [rsp-8+arg_10], rbx
0x18000d9c1  push    rbp
0x18000d9c2  push    rsi
0x18000d9c3  push    rdi
0x18000d9c4  push    r12
0x18000d9c6  push    r13
0x18000d9c8  push    r14
0x18000d9ca  push    r15
0x18000d9cc  lea     rbp, [rsp-0B0h]
0x18000d9d4  sub     rsp, 1B0h
0x18000d9db  mov     rax, cs:__security_cookie
0x18000d9e2  xor     rax, rsp
0x18000d9e5  mov     [rbp+0E0h+var_40], rax
0x18000d9ec  xor     edi, edi
0x18000d9ee  mov     r15, rdx
0x18000d9f1  mov     rbx, rcx
0x18000d9f4  mov     [rsp+1E0h+var_190], rdi
0x18000d9f9  mov     esi, 57h ; 'W'
0x18000d9fe  mov     [rsp+1E0h+var_170], rdi
0x18000da03  xor     edx, edx; Val
0x18000da05  mov     [rsp+1E0h+var_180], rdi
0x18000da0a  lea     rcx, [rbp+0E0h+var_160]; void *
0x18000da0e  mov     [rsp+1E0h+var_178], rdi
0x18000da13  mov     r12d, edi
0x18000da16  mov     [rsp+1E0h+hObject], rdi
0x18000da1b  lea     r8d, [rsi+51h]; Size
0x18000da1f  mov     [rsp+1E0h+var_188], rdi
0x18000da24  mov     r13d, edi
0x18000da27  call    memset_0
0x18000da2c  xor     edx, edx; Val
0x18000da2e  lea     r8d, [rsi+11h]; Size
0x18000da32  lea     rcx, [rbp+0E0h+var_B0]; void *
0x18000da36  call    memset_0
0x18000da3b  test    byte ptr [rbx+68h], 10h
0x18000da3f  mov     [rsp+1E0h+var_19C], edi
0x18000da43  mov     [rsp+1E0h+var_1A0], edi
0x18000da47  jnz     loc_18000DBA6
0x18000da4d  mov     r14d, edi
0x18000da50  lea     rdi, [rbx+40h]
0x18000da54  mov     rcx, rdi; struct _UBPM_SRWLOCK *
0x18000da57  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18000da5c  lea     eax, [r14+1]
0x18000da60  lea     rsi, WPP_GLOBAL_Control
0x18000da67  cmp     [rbx+114h], ax
0x18000da6e  jnz     loc_18000DC3D
0x18000da74  mov     rcx, rdi
0x18000da77  mov     [rdi+8], r12d
0x18000da7b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000da82  nop     dword ptr [rax+rax+00h]
0x18000da87  lea     rax, [rsp+1E0h+var_188]
0x18000da8c  mov     rcx, rbx
0x18000da8f  mov     [rsp+1E0h+var_1B0], rax
0x18000da94  lea     r9, [rsp+1E0h+var_178]
0x18000da99  lea     rax, [rsp+1E0h+var_19C]
0x18000da9e  mov     [rsp+1E0h+var_1B8], rax
0x18000daa3  lea     r8, [rsp+1E0h+var_180]
0x18000daa8  lea     rax, [rsp+1E0h+hObject]
0x18000daad  lea     rdx, [rsp+1E0h+var_1A0]
0x18000dab2  mov     [rsp+1E0h+var_1C0], rax
0x18000dab7  call    UbpmpReadContextBlock
0x18000dabc  mov     r12, [rsp+1E0h+var_180]
0x18000dac1  mov     r13, [rsp+1E0h+var_178]
0x18000dac6  test    eax, eax
0x18000dac8  jnz     loc_18000DC35
0x18000dace  mov     rax, [rsp+1E0h+var_188]
0x18000dad3  mov     [rbp+0E0h+var_148], rax
0x18000dad7  mov     eax, [rsp+1E0h+var_1A0]
0x18000dadb  mov     [rbp+0E0h+var_128], eax
0x18000dade  mov     rax, [r15+20h]
0x18000dae2  mov     [rbp+0E0h+var_160], r15
0x18000dae6  mov     [rbp+0E0h+var_120], r12
0x18000daea  mov     [rbp+0E0h+var_118], r13
0x18000daee  test    rax, rax
0x18000daf1  jz      loc_18000DC90
0x18000daf7  mov     eax, [rax+14h]
0x18000dafa  mov     [rbp+0E0h+var_10C], eax
0x18000dafd  mov     eax, [rsp+1E0h+var_19C]
0x18000db01  mov     [rbp+0E0h+var_110], eax
0x18000db04  mov     rax, [rsp+1E0h+hObject]
0x18000db09  neg     rax
0x18000db0c  lea     rax, [rsp+1E0h+hObject]
0x18000db11  sbb     rdx, rdx
0x18000db14  and     rdx, rax; void **
0x18000db17  mov     rax, [r15+18h]
0x18000db1b  xor     r15d, r15d
0x18000db1e  mov     ecx, [rax]
0x18000db20  mov     [rsp+1E0h+var_190], r15
0x18000db25  mov     [rsp+1E0h+var_170], r15
0x18000db2a  lea     eax, [rcx-1]
0x18000db2d  cmp     eax, 1
0x18000db30  ja      loc_18000DC7D
0x18000db36  lea     r9, [rsp+1E0h+var_170]; struct _UBPM_TASK_HOST_TASK_CONTEXT **
0x18000db3b  lea     r8, [rsp+1E0h+var_190]; struct _UBPM_TASK_HOST_CONTEXT_BLOCK **
0x18000db40  lea     rcx, [rbp+0E0h+var_160]; struct _UBPM_TASK_LAUNCH_INPUT_PARAMS *
0x18000db44  call    ?UbpmpHostLaunchTaskExe@@YAKPEAU_UBPM_TASK_LAUNCH_INPUT_PARAMS@@PEAPEAXPEAPEAU_UBPM_TASK_HOST_CONTEXT_BLOCK@@PEAPEAU_UBPM_TASK_HOST_TASK_CONTEXT@@@Z; UbpmpHostLaunchTaskExe(_UBPM_TASK_LAUNCH_INPUT_PARAMS *,void * *,_UBPM_TASK_HOST_CONTEXT_BLOCK * *,_UBPM_TASK_HOST_TASK_CONTEXT * *)
0x18000db49  test    eax, eax
0x18000db4b  jnz     loc_18000DCA3
0x18000db51  mov     rcx, rdi; struct _UBPM_SRWLOCK *
0x18000db54  mov     esi, r15d
0x18000db57  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18000db5c  test    byte ptr [rbx+68h], 4
0x18000db60  jz      loc_18000DBED
0x18000db66  mov     rcx, rdi
0x18000db69  mov     [rdi+8], r15d
0x18000db6d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000db74  nop     dword ptr [rax+rax+00h]
0x18000db79  test    r14, r14
0x18000db7c  jz      short loc_18000DB89
0x18000db7e  mov     rdx, r14; WaitHandle
0x18000db81  mov     rcx, rbx; struct _UBPM_TASK_HOST_CONTEXT_BLOCK *
0x18000db84  call    ?UbpmpTaskHostTerminationCleanup@@YAXPEAU_UBPM_TASK_HOST_CONTEXT_BLOCK@@PEAX@Z; UbpmpTaskHostTerminationCleanup(_UBPM_TASK_HOST_CONTEXT_BLOCK *,void *)
0x18000db89  mov     rcx, [rsp+1E0h+var_190]
0x18000db8e  test    rcx, rcx
0x18000db91  jz      short loc_18000DB98
0x18000db93  call    UbpmpHostCloseTaskHostContext
0x18000db98  mov     rcx, [rsp+1E0h+hObject]; hObject
0x18000db9d  test    rcx, rcx
0x18000dba0  jnz     loc_18000DD8D
0x18000dba6  mov     rcx, r12
0x18000dba9  call    UBPM_MIDL_user_free
0x18000dbae  mov     rcx, r13
0x18000dbb1  call    UBPM_MIDL_user_free
0x18000dbb6  mov     rcx, [rsp+1E0h+var_188]
0x18000dbbb  call    UBPM_MIDL_user_free
0x18000dbc0  mov     eax, esi
0x18000dbc2  mov     rcx, [rbp+0E0h+var_40]
0x18000dbc9  xor     rcx, rsp; StackCookie
0x18000dbcc  call    __security_check_cookie
0x18000dbd1  mov     rbx, [rsp+1E0h+arg_10]
0x18000dbd9  add     rsp, 1B0h
0x18000dbe0  pop     r15
0x18000dbe2  pop     r14
0x18000dbe4  pop     r13
0x18000dbe6  pop     r12
0x18000dbe8  pop     rdi
0x18000dbe9  pop     rsi
0x18000dbea  pop     rbp
0x18000dbeb  retn
0x18000dbed  lea     rax, UbpmpDelayedTerminateProcessCallback
0x18000dbf4  mov     [rbp+0E0h+var_94], r15d
0x18000dbf8  mov     [rbp+0E0h+var_B0], rax
0x18000dbfc  lea     rcx, [rbp+0E0h+var_B0]; struct _UBPM_UTILS_TIMER_INPARAMS *
0x18000dc00  mov     rax, [rbx+18h]
0x18000dc04  xor     edx, edx; void **
0x18000dc06  mov     [rbp+0E0h+var_A8], rax
0x18000dc0a  mov     [rbp+0E0h+var_8C], r15b
0x18000dc0e  mov     [rbp+0E0h+var_90], 1
0x18000dc15  call    ?UbpmUtilsSubmitThreadPoolTimer@@YAKPEAU_UBPM_UTILS_TIMER_INPARAMS@@PEAPEAX@Z; UbpmUtilsSubmitThreadPoolTimer(_UBPM_UTILS_TIMER_INPARAMS *,void * *)
0x18000dc1a  mov     esi, eax
0x18000dc1c  test    eax, eax
0x18000dc1e  jnz     loc_18000DCDF
0x18000dc24  mov     [rbx+18h], r15
0x18000dc28  mov     r14, [rbx+28h]
0x18000dc2c  mov     [rbx+28h], r15
0x18000dc30  jmp     loc_18000DB66
0x18000dc35  xor     r15d, r15d
0x18000dc38  jmp     loc_18000DB51
0x18000dc3d  xor     eax, eax
0x18000dc3f  mov     [rbx+114h], ax
0x18000dc46  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc4d  cmp     rcx, rsi
0x18000dc50  jz      loc_18000DA74
0x18000dc56  test    byte ptr [rcx+1Ch], 80h
0x18000dc5a  jz      loc_18000DA74
0x18000dc60  mov     eax, [rbx+20h]
0x18000dc63  mov     edx, 0BAh
0x18000dc68  mov     rcx, [rcx+10h]
0x18000dc6c  mov     r9, rbx
0x18000dc6f  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x18000dc73  call    WPP_SF_qd
0x18000dc78  jmp     loc_18000DA74
0x18000dc7d  cmp     ecx, 3
0x18000dc80  lea     rcx, [rbp+0E0h+var_160]
0x18000dc84  jnz     short loc_18000DC99
0x18000dc86  call    UbpmLaunchTaskSignal
0x18000dc8b  jmp     loc_18000DB49
0x18000dc90  mov     [rbp+0E0h+var_10C], r14d
0x18000dc94  jmp     loc_18000DAFD
0x18000dc99  call    UbpmLaunchTaskPublish
0x18000dc9e  jmp     loc_18000DB49
0x18000dca3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcaa  cmp     rcx, rsi
0x18000dcad  jz      loc_18000DB51
0x18000dcb3  test    byte ptr [rcx+1Ch], 2
0x18000dcb7  jz      loc_18000DB51
0x18000dcbd  mov     r9d, [rbx+20h]
0x18000dcc1  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18000dcc8  mov     rcx, [rcx+10h]
0x18000dccc  mov     edx, 0BBh
0x18000dcd1  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x18000dcd5  call    WPP_SF_dd
0x18000dcda  jmp     loc_18000DB51
0x18000dcdf  mov     rcx, [rbx+18h]; hProcess
0x18000dce3  mov     edx, 42Bh; uExitCode
0x18000dce8  call    cs:__imp_TerminateProcess
0x18000dcef  nop     dword ptr [rax+rax+00h]
0x18000dcf4  test    eax, eax
0x18000dcf6  jnz     short loc_18000DD4E
0x18000dcf8  mov     rax, cs:WPP_GLOBAL_Control
0x18000dcff  lea     rdx, WPP_GLOBAL_Control
0x18000dd06  cmp     rax, rdx
0x18000dd09  jz      loc_18000DC28
0x18000dd0f  test    byte ptr [rax+1Ch], 2
0x18000dd13  jz      loc_18000DC28
0x18000dd19  call    cs:__imp_GetLastError
0x18000dd20  nop     dword ptr [rax+rax+00h]
0x18000dd25  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd2c  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18000dd33  mov     r9d, [rbx+20h]
0x18000dd37  mov     edx, 0BCh
0x18000dd3c  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x18000dd40  mov     rcx, [rcx+10h]
0x18000dd44  call    WPP_SF_dd
0x18000dd49  jmp     loc_18000DC28
0x18000dd4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd55  lea     rdx, WPP_GLOBAL_Control
0x18000dd5c  cmp     rcx, rdx
0x18000dd5f  jz      loc_18000DC28
0x18000dd65  test    byte ptr [rcx+1Ch], 80h
0x18000dd69  jz      loc_18000DC28
0x18000dd6f  mov     r9d, [rbx+20h]
0x18000dd73  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18000dd7a  mov     rcx, [rcx+10h]
0x18000dd7e  mov     edx, 0BDh
0x18000dd83  call    WPP_SF_d
0x18000dd88  jmp     loc_18000DC28
0x18000dd8d  call    cs:__imp_CloseHandle
0x18000dd94  nop     dword ptr [rax+rax+00h]
0x18000dd99  jmp     loc_18000DBA6
```
