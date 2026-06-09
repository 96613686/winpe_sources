# UmpoTraceSendKernelPowerPolicyNotification

- ea: `0x180015f78`
- end: `0x180016039`
- name: `UmpoTraceSendKernelPowerPolicyNotification`
- size: `193`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180004e60`
- `0x180008640`

## callees

- `0x18000c04c`
- `0x18000d6cc`
- `0x180010070`
- `0x180015f78`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001601e`
- `ntdll!EtwEventWrite` at `0x18001601e`

## pseudocode

```c
__int64 __fastcall UmpoTraceSendKernelPowerPolicyNotification(int a1)
{
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9
  int v5; // [rsp+30h] [rbp-19h] BYREF
  __int64 v6; // [rsp+38h] [rbp-11h] BYREF
  _QWORD v7[2]; // [rsp+40h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+50h] [rbp+7h] BYREF
  __int64 *v9; // [rsp+70h] [rbp+27h]
  __int64 v10; // [rsp+78h] [rbp+2Fh]
  int *v11; // [rsp+80h] [rbp+37h]
  __int64 v12; // [rsp+88h] [rbp+3Fh]
  int v13; // [rsp+B0h] [rbp+67h] BYREF

  v13 = a1;
  if ( (unsigned int)dword_180024190 > 5 && tlgKeywordOn() )
  {
    v6 = 0x1000000;
    v9 = &v6;
    v5 = v13;
    v11 = &v5;
    v10 = 8;
    v12 = 4;
    tlgWriteTransfer_EventWriteTransfer(v1, (unsigned __int8 *)&word_18001FB0E, v2, v3, 4u, &v8);
  }
  v7[0] = &v13;
  v7[1] = 4;
  return EtwEventWrite(UmpoProviderHandle, UMPO_EVT_SEND_KERNEL_POWER_POLICY_NOTIFICATION_FAILED, 1, v7);
}

```

## disassembly

```asm
0x180015f78  mov     [rsp-8+arg_0], ecx
0x180015f7c  push    rbp
0x180015f7d  lea     rbp, [rsp-57h]
0x180015f82  sub     rsp, 0A0h
0x180015f89  mov     rax, cs:__security_cookie
0x180015f90  xor     rax, rsp
0x180015f93  mov     [rbp+57h+var_10], rax
0x180015f97  mov     eax, cs:dword_180024190
0x180015f9d  cmp     eax, 5
0x180015fa0  jbe     short loc_180015FF6
0x180015fa2  call    _tlgKeywordOn
0x180015fa7  test    al, al
0x180015fa9  jz      short loc_180015FF6
0x180015fab  lea     rax, [rbp+57h+var_68]
0x180015faf  mov     [rbp+57h+var_68], 1000000h
0x180015fb7  mov     [rbp+57h+var_30], rax
0x180015fbb  lea     rdx, word_18001FB0E; int
0x180015fc2  mov     eax, [rbp+57h+arg_0]
0x180015fc5  mov     [rbp+57h+var_70], eax
0x180015fc8  lea     rax, [rbp+57h+var_70]
0x180015fcc  mov     [rbp+57h+var_20], rax
0x180015fd0  lea     rax, [rbp+57h+var_50]
0x180015fd4  mov     [rsp+0A0h+var_78], rax; __int64
0x180015fd9  mov     [rsp+0A0h+var_80], 4; ULONG
0x180015fe1  mov     [rbp+57h+var_28], 8
0x180015fe9  mov     [rbp+57h+var_18], 4
0x180015ff1  call    _tlgWriteTransfer_EventWriteTransfer
0x180015ff6  mov     rcx, cs:UmpoProviderHandle
0x180015ffd  lea     rax, [rbp+57h+arg_0]
0x180016001  lea     r9, [rbp+57h+var_60]
0x180016005  mov     [rbp+57h+var_60], rax
0x180016009  mov     r8d, 1
0x18001600f  mov     [rbp+57h+var_58], 4
0x180016017  lea     rdx, UMPO_EVT_SEND_KERNEL_POWER_POLICY_NOTIFICATION_FAILED
0x18001601e  call    cs:__imp_EtwEventWrite
0x180016024  mov     rcx, [rbp+57h+var_10]
0x180016028  xor     rcx, rsp; StackCookie
0x18001602b  call    __security_check_cookie
0x180016030  add     rsp, 0A0h
0x180016037  pop     rbp
0x180016038  retn
```
