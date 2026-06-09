# TmpRegisterForLogManagement

- ea: `0x14001d690`
- end: `0x14001da07`
- name: `TmpRegisterForLogManagement`
- size: `887`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14001ec00`

## callees

- `0x140001618`
- `0x1400024e0`
- `0x14001d690`

## import_xrefs

- `CLFS!ClfsMgmtDeregisterManagedClient` at `0x14001d9f2`
- `CLFS!ClfsMgmtDeregisterManagedClient` at `0x140021638`
- `CLFS!ClfsMgmtDeregisterManagedClient` at `0x14001d9f2`
- `CLFS!ClfsMgmtDeregisterManagedClient` at `0x140021638`
- `CLFS!ClfsMgmtRegisterManagedClient` at `0x14001d752`
- `CLFS!ClfsMgmtRegisterManagedClient` at `0x14001d752`
- `CLFS!ClfsMgmtInstallPolicy` at `0x14001d7c2`
- `CLFS!ClfsMgmtInstallPolicy` at `0x14001d837`
- `CLFS!ClfsMgmtInstallPolicy` at `0x14001d8af`
- `CLFS!ClfsMgmtInstallPolicy` at `0x14001d7c2`
- `CLFS!ClfsMgmtInstallPolicy` at `0x14001d837`
- `CLFS!ClfsMgmtInstallPolicy` at `0x14001d8af`
- `CLFS!ClfsMgmtSetLogFileSize` at `0x14001d8ef`
- `CLFS!ClfsMgmtSetLogFileSize` at `0x14001d8ef`

## pseudocode

```c
__int64 __fastcall TmpRegisterForLogManagement(unsigned __int64 a1)
{
  NTSTATUS v2; // edi
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  void *v6; // rcx
  unsigned __int64 NewSizeInContainers; // [rsp+38h] [rbp-A0h] BYREF
  _CLFS_MGMT_CLIENT_REGISTRATION RegistrationData; // [rsp+40h] [rbp-98h] BYREF
  unsigned __int64 ResultingSizeInContainers[2]; // [rsp+78h] [rbp-60h] BYREF
  _CLFS_MGMT_POLICY Policy; // [rsp+88h] [rbp-50h] BYREF

  ResultingSizeInContainers[1] = a1;
  NewSizeInContainers = 0;
  ResultingSizeInContainers[0] = 0;
  memset(&Policy, 0, sizeof(Policy));
  *(_QWORD *)(a1 + 168) = 0;
  *(&RegistrationData.Version + 1) = 0;
  RegistrationData.Version = 1;
  RegistrationData.AdvanceTailCallback = (PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK)TmpAdvanceBaseLsnRequiredNotification;
  RegistrationData.AdvanceTailCallbackData = (PVOID)a1;
  RegistrationData.LogGrowthCompleteCallback = (PCLFS_CLIENT_LFF_HANDLER_COMPLETE_CALLBACK)TmpLogGrowthCompletedNotification;
  RegistrationData.LogGrowthCompleteCallbackData = (PVOID)a1;
  RegistrationData.LogUnpinnedCallback = (PCLFS_CLIENT_LOG_UNPINNED_CALLBACK)&TmpLogUnpinnedNotification;
  RegistrationData.LogUnpinnedCallbackData = (PVOID)a1;
  v2 = ClfsMgmtRegisterManagedClient(*(PLOG_FILE_OBJECT *)(a1 + 152), &RegistrationData, (PCLFS_MGMT_CLIENT)(a1 + 168));
  if ( v2 < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
    {
      v4 = 43;
      goto LABEL_18;
    }
  }
  else
  {
    Policy.PolicyFlags = 0;
    Policy.Version = 1;
    Policy.LengthInBytes = 24;
    Policy.PolicyType = ClfsMgmtPolicyMinimumSize;
    Policy.PolicyParameters.NewContainerSuffix.NextContainerSuffix = 2;
    v2 = ClfsMgmtInstallPolicy(*(PLOG_FILE_OBJECT *)(a1 + 152), &Policy, 0x18u);
    if ( v2 == -1072037868 || v2 >= 0 )
    {
      Policy.PolicyFlags = 0;
      Policy.Version = 1;
      Policy.LengthInBytes = 24;
      Policy.PolicyType = ClfsMgmtPolicyMaximumSize;
      Policy.PolicyParameters.NewContainerSuffix.NextContainerSuffix = 10;
      v2 = ClfsMgmtInstallPolicy(*(PLOG_FILE_OBJECT *)(a1 + 152), &Policy, 0x18u);
      if ( v2 == -1072037868 || v2 >= 0 )
      {
        Policy.PolicyFlags = 0;
        Policy.Version = 1;
        Policy.LengthInBytes = 24;
        Policy.PolicyType = ClfsMgmtPolicyNewContainerSize;
        Policy.PolicyParameters.NewContainerSuffix.NextContainerSuffix = 0x80000;
        v2 = ClfsMgmtInstallPolicy(*(PLOG_FILE_OBJECT *)(a1 + 152), &Policy, 0x18u);
        if ( v2 == -1072037868 || v2 >= 0 )
        {
          NewSizeInContainers = 0;
          v2 = ClfsMgmtSetLogFileSize(
                 *(PLOG_FILE_OBJECT *)(a1 + 152),
                 &NewSizeInContainers,
                 ResultingSizeInContainers,
                 0,
                 0);
        }
        else
        {
          v3 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
          {
            v4 = 46;
            goto LABEL_18;
          }
        }
      }
      else
      {
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
        {
          v4 = 45;
          goto LABEL_18;
        }
      }
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
      {
        v4 = 44;
LABEL_18:
        WPP_SF_qD(v3[3], v4, WPP_b60b885ff4cd344d6813b01a736c9140_Traceguids, a1, v2);
      }
    }
  }
  if ( v2 < 0 )
  {
    v6 = *(void **)(a1 + 168);
    if ( v6 )
    {
      ClfsMgmtDeregisterManagedClient(v6);
      *(_QWORD *)(a1 + 168) = 0;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14001d690  mov     r11, rsp
0x14001d693  push    rbx
0x14001d694  push    rsi
0x14001d695  push    rdi
0x14001d696  push    r14
0x14001d698  sub     rsp, 0B8h
0x14001d69f  mov     rax, cs:__security_cookie
0x14001d6a6  xor     rax, rsp
0x14001d6a9  mov     [rsp+0D8h+var_38], rax
0x14001d6b1  mov     rbx, rcx
0x14001d6b4  mov     [rsp+0D8h+var_58], rcx
0x14001d6bc  xor     r14d, r14d
0x14001d6bf  mov     [rsp+0D8h+var_A8], r14d
0x14001d6c4  mov     [rsp+0D8h+NewSizeInContainers], r14
0x14001d6c9  mov     [r11-60h], r14
0x14001d6cd  xor     eax, eax
0x14001d6cf  xorps   xmm0, xmm0
0x14001d6d2  movups  xmmword ptr [rsp+0D8h+RegistrationData.Version], xmm0
0x14001d6d7  movups  xmmword ptr [rsp+0D8h+RegistrationData.AdvanceTailCallbackData], xmm0
0x14001d6dc  movups  xmmword ptr [rsp+0D8h+RegistrationData.LogGrowthCompleteCallbackData], xmm0
0x14001d6e1  mov     dword ptr [rsp+0D8h+RegistrationData.LogUnpinnedCallbackData], eax
0x14001d6e5  movups  xmmword ptr [r11-50h], xmm0
0x14001d6ea  mov     [r11-40h], rax
0x14001d6ee  mov     [rcx+0A8h], r14
0x14001d6f5  movups  xmmword ptr [rsp+0D8h+RegistrationData.Version], xmm0
0x14001d6fa  movups  xmmword ptr [rsp+0D8h+RegistrationData.AdvanceTailCallbackData], xmm0
0x14001d6ff  movups  xmmword ptr [rsp+0D8h+RegistrationData.LogGrowthCompleteCallbackData], xmm0
0x14001d704  mov     [r11-68h], rax
0x14001d708  mov     [rsp+0D8h+RegistrationData.Version], 1
0x14001d710  lea     rax, TmpAdvanceBaseLsnRequiredNotification
0x14001d717  mov     [rsp+0D8h+RegistrationData.AdvanceTailCallback], rax
0x14001d71c  mov     [rsp+0D8h+RegistrationData.AdvanceTailCallbackData], rcx
0x14001d721  lea     rax, TmpLogGrowthCompletedNotification
0x14001d728  mov     [r11-80h], rax
0x14001d72c  mov     [r11-78h], rcx
0x14001d730  lea     rax, TmpLogUnpinnedNotification
0x14001d737  mov     [r11-70h], rax
0x14001d73b  mov     [r11-68h], rcx
0x14001d73f  lea     r8, [rcx+0A8h]; ClientCookie
0x14001d746  lea     rdx, [rsp+0D8h+RegistrationData]; RegistrationData
0x14001d74b  mov     rcx, [rcx+98h]; LogFile
0x14001d752  call    cs:__imp_ClfsMgmtRegisterManagedClient
0x14001d759  nop     dword ptr [rax+rax+00h]
0x14001d75e  mov     edi, eax
0x14001d760  mov     [rsp+0D8h+var_A8], eax
0x14001d764  test    eax, eax
0x14001d766  js      loc_14001D9A0
0x14001d76c  xorps   xmm0, xmm0
0x14001d76f  xor     eax, eax
0x14001d771  movups  xmmword ptr [rsp+0D8h+Policy.Version], xmm0
0x14001d779  mov     qword ptr [rsp+0D8h+Policy.PolicyParameters], rax
0x14001d781  mov     [rsp+0D8h+Policy.Version], 1
0x14001d78c  mov     [rsp+0D8h+Policy.LengthInBytes], 18h
0x14001d797  mov     [rsp+0D8h+Policy.PolicyType], 1
0x14001d7a2  mov     dword ptr [rsp+0D8h+Policy.PolicyParameters], 2
0x14001d7ad  mov     r8d, 18h; PolicyLength
0x14001d7b3  lea     rdx, [rsp+0D8h+Policy]; Policy
0x14001d7bb  mov     rcx, [rbx+98h]; LogFile
0x14001d7c2  call    cs:__imp_ClfsMgmtInstallPolicy
0x14001d7c9  nop     dword ptr [rax+rax+00h]
0x14001d7ce  mov     edi, eax
0x14001d7d0  mov     [rsp+0D8h+var_A8], eax
0x14001d7d4  cmp     eax, 0C01A0014h
0x14001d7d9  jnz     loc_14001D906
0x14001d7df  mov     [rsp+0D8h+var_A8], r14d
0x14001d7e4  xorps   xmm0, xmm0
0x14001d7e7  xor     eax, eax
0x14001d7e9  movups  xmmword ptr [rsp+0D8h+Policy.Version], xmm0
0x14001d7f1  mov     qword ptr [rsp+0D8h+Policy.PolicyParameters], rax
0x14001d7f9  mov     [rsp+0D8h+Policy.Version], 1
0x14001d804  mov     [rsp+0D8h+Policy.LengthInBytes], 18h
0x14001d80f  mov     [rsp+0D8h+Policy.PolicyType], r14d
0x14001d817  mov     dword ptr [rsp+0D8h+Policy.PolicyParameters], 0Ah
0x14001d822  mov     r8d, 18h; PolicyLength
0x14001d828  lea     rdx, [rsp+0D8h+Policy]; Policy
0x14001d830  mov     rcx, [rbx+98h]; LogFile
0x14001d837  call    cs:__imp_ClfsMgmtInstallPolicy
0x14001d83e  nop     dword ptr [rax+rax+00h]
0x14001d843  mov     edi, eax
0x14001d845  mov     [rsp+0D8h+var_A8], eax
0x14001d849  cmp     eax, 0C01A0014h
0x14001d84e  jnz     loc_14001D937
0x14001d854  mov     [rsp+0D8h+var_A8], r14d
0x14001d859  xorps   xmm0, xmm0
0x14001d85c  xor     eax, eax
0x14001d85e  movups  xmmword ptr [rsp+0D8h+Policy.Version], xmm0
0x14001d866  mov     qword ptr [rsp+0D8h+Policy.PolicyParameters], rax
0x14001d86e  mov     [rsp+0D8h+Policy.Version], 1
0x14001d879  mov     [rsp+0D8h+Policy.LengthInBytes], 18h
0x14001d884  mov     [rsp+0D8h+Policy.PolicyType], 2
0x14001d88f  mov     dword ptr [rsp+0D8h+Policy.PolicyParameters], 80000h
0x14001d89a  mov     r8d, 18h; PolicyLength
0x14001d8a0  lea     rdx, [rsp+0D8h+Policy]; Policy
0x14001d8a8  mov     rcx, [rbx+98h]; LogFile
0x14001d8af  call    cs:__imp_ClfsMgmtInstallPolicy
0x14001d8b6  nop     dword ptr [rax+rax+00h]
0x14001d8bb  mov     edi, eax
0x14001d8bd  mov     [rsp+0D8h+var_A8], eax
0x14001d8c1  cmp     eax, 0C01A0014h
0x14001d8c6  jnz     loc_14001D960
0x14001d8cc  mov     [rsp+0D8h+var_A8], r14d
0x14001d8d1  mov     [rsp+0D8h+NewSizeInContainers], r14
0x14001d8d6  mov     [rsp+0D8h+CompletionRoutineData], r14; CompletionRoutineData
0x14001d8db  xor     r9d, r9d; CompletionRoutine
0x14001d8de  lea     r8, [rsp+0D8h+ResultingSizeInContainers]; ResultingSizeInContainers
0x14001d8e3  lea     rdx, [rsp+0D8h+NewSizeInContainers]; NewSizeInContainers
0x14001d8e8  mov     rcx, [rbx+98h]; LogFile
0x14001d8ef  call    cs:__imp_ClfsMgmtSetLogFileSize
0x14001d8f6  nop     dword ptr [rax+rax+00h]
0x14001d8fb  mov     edi, eax
0x14001d8fd  mov     [rsp+0D8h+var_A8], eax
0x14001d901  jmp     loc_14001D9C2
0x14001d906  test    edi, edi
0x14001d908  jns     loc_14001D7E4
0x14001d90e  lea     rax, WPP_GLOBAL_Control
0x14001d915  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d91c  cmp     rcx, rax
0x14001d91f  jz      loc_14001D9C2
0x14001d925  mov     eax, [rcx+2Ch]
0x14001d928  test    al, 8
0x14001d92a  jz      loc_14001D9C2
0x14001d930  mov     edx, 2Ch ; ','
0x14001d935  jmp     short loc_14001D987
0x14001d937  test    edi, edi
0x14001d939  jns     loc_14001D859
0x14001d93f  lea     rax, WPP_GLOBAL_Control
0x14001d946  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d94d  cmp     rcx, rax
0x14001d950  jz      short loc_14001D9C2
0x14001d952  mov     eax, [rcx+2Ch]
0x14001d955  test    al, 8
0x14001d957  jz      short loc_14001D9C2
0x14001d959  mov     edx, 2Dh ; '-'
0x14001d95e  jmp     short loc_14001D987
0x14001d960  test    edi, edi
0x14001d962  jns     loc_14001D8D1
0x14001d968  lea     rax, WPP_GLOBAL_Control
0x14001d96f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d976  cmp     rcx, rax
0x14001d979  jz      short loc_14001D9C2
0x14001d97b  mov     eax, [rcx+2Ch]
0x14001d97e  test    al, 8
0x14001d980  jz      short loc_14001D9C2
0x14001d982  mov     edx, 2Eh ; '.'
0x14001d987  mov     dword ptr [rsp+0D8h+CompletionRoutineData], edi
0x14001d98b  mov     r9, rbx
0x14001d98e  lea     r8, WPP_b60b885ff4cd344d6813b01a736c9140_Traceguids
0x14001d995  mov     rcx, [rcx+18h]
0x14001d999  call    WPP_SF_qD
0x14001d99e  jmp     short loc_14001D9C2
0x14001d9a0  lea     rax, WPP_GLOBAL_Control
0x14001d9a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d9ae  cmp     rcx, rax
0x14001d9b1  jz      short loc_14001D9C2
0x14001d9b3  mov     edx, [rcx+2Ch]
0x14001d9b6  test    dl, 8
0x14001d9b9  jz      short loc_14001D9C2
0x14001d9bb  mov     edx, 2Bh ; '+'
0x14001d9c0  jmp     short loc_14001D987
0x14001d9c2  test    edi, edi
0x14001d9c4  js      short loc_14001D9E6
0x14001d9c6  mov     eax, edi
0x14001d9c8  mov     rcx, [rsp+0D8h+var_38]
0x14001d9d0  xor     rcx, rsp; StackCookie
0x14001d9d3  call    __security_check_cookie
0x14001d9d8  add     rsp, 0B8h
0x14001d9df  pop     r14
0x14001d9e1  pop     rdi
0x14001d9e2  pop     rsi
0x14001d9e3  pop     rbx
0x14001d9e4  retn
0x14001d9e6  mov     rcx, [rbx+0A8h]; ClientCookie
0x14001d9ed  test    rcx, rcx
0x14001d9f0  jz      short loc_14001D9C6
0x14001d9f2  call    cs:__imp_ClfsMgmtDeregisterManagedClient
0x14001d9f9  nop     dword ptr [rax+rax+00h]
0x14001d9fe  mov     [rbx+0A8h], r14
0x14001da05  jmp     short loc_14001D9C6
0x140021610  push    rbx
0x140021612  push    rbp
0x140021613  sub     rsp, 38h
0x140021617  mov     rbp, rdx
0x14002161a  cmp     dword ptr [rbp+30h], 0
0x14002161e  jge     short loc_14002164F
0x140021620  mov     rbx, [rbp+80h]
0x140021627  cmp     qword ptr [rbx+0A8h], 0
0x14002162f  jz      short loc_14002164F
0x140021631  mov     rcx, [rbx+0A8h]; ClientCookie
0x140021638  call    cs:__imp_ClfsMgmtDeregisterManagedClient
0x14002163f  nop     dword ptr [rax+rax+00h]
0x140021644  mov     qword ptr [rbx+0A8h], 0
0x14002164f  add     rsp, 38h
0x140021653  pop     rbp
0x140021654  pop     rbx
0x140021655  retn
```
