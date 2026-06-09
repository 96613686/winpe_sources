# TpmKsrCallback

- ea: `0x14001e130`
- end: `0x14001e38b`
- name: `TpmKsrCallback`
- size: `603`
- prototype: `DRIVER_NOTIFICATION_CALLBACK_ROUTINE`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callees

- `0x14001c75c`
- `0x14001d44c`
- `0x14001e130`
- `0x140039740`
- `0x140039780`

## import_xrefs

- `ntoskrnl!IoWriteKsrPersistentMemory` at `0x14001e277`
- `ntoskrnl!IoWriteKsrPersistentMemory` at `0x14001e277`
- `ntoskrnl!IoReserveKsrPersistentMemory` at `0x14001e239`
- `ntoskrnl!IoReserveKsrPersistentMemory` at `0x14001e239`
- `ntoskrnl!IoFreeKsrPersistentMemory` at `0x14001e2b6`
- `ntoskrnl!IoFreeKsrPersistentMemory` at `0x14001e33b`
- `ntoskrnl!IoFreeKsrPersistentMemory` at `0x14001e2b6`
- `ntoskrnl!IoFreeKsrPersistentMemory` at `0x14001e33b`

## pseudocode

```c
__int64 __fastcall TpmKsrCallback(char *NotificationStructure, PVOID Context)
{
  TpmStack *v3; // rax
  TpmStack *v4; // rsi
  __int64 v5; // rcx
  char v6; // al
  int v7; // ecx
  int v8; // r8d
  __int64 v9; // rax
  int v10; // eax
  int v11; // ecx
  int v12; // r8d
  int v13; // ebp
  char v14; // al
  int v15; // ecx
  int v16; // r8d
  char v17; // al
  int v18; // ecx
  int v19; // r8d
  __int64 v20; // rax
  char IsNextRebootKsr; // al
  int v22; // ecx
  int v23; // r8d
  char v24; // al
  int v25; // ecx
  int v26; // r8d
  __int64 v28; // [rsp+30h] [rbp-28h]
  _DWORD v29[4]; // [rsp+38h] [rbp-20h] BYREF

  if ( *(_WORD *)NotificationStructure == 1 && *((_WORD *)NotificationStructure + 1) >= 0x14u )
  {
    v3 = (TpmStack *)(*((__int64 (__fastcall **)(PKDPC, PVOID, void *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 202))(
                       WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                       Context,
                       off_140047018);
    v4 = v3;
    v28 = *((_QWORD *)v3 + 7);
    v5 = *(_QWORD *)(NotificationStructure + 4) - *(_QWORD *)&GUID_KERNEL_SOFT_RESTART_PREPARE.Data1;
    if ( !v5 )
      v5 = *(_QWORD *)(NotificationStructure + 12) - *(_QWORD *)GUID_KERNEL_SOFT_RESTART_PREPARE.Data4;
    if ( v5 )
    {
      v20 = *(_QWORD *)(NotificationStructure + 4) - *(_QWORD *)&GUID_KERNEL_SOFT_RESTART_CANCEL.Data1;
      if ( !v20 )
        v20 = *(_QWORD *)(NotificationStructure + 12) - *(_QWORD *)GUID_KERNEL_SOFT_RESTART_CANCEL.Data4;
      if ( !v20 )
      {
        IsNextRebootKsr = TpmStack::SetIsNextRebootKsr(v4, 0);
        if ( (TPMEnableBits & 2) != 0 )
          McTemplateK0zq_EtwWriteTransfer(
            v22,
            (unsigned int)TPM_KSR_INFORMATION,
            v23,
            (unsigned int)L"KSR cancel: SetIsNextRebootKsr(false)",
            IsNextRebootKsr);
        if ( v28 )
        {
          v24 = ((__int64 (*)(void))IoFreeKsrPersistentMemory)();
          if ( (TPMEnableBits & 2) != 0 )
            McTemplateK0zq_EtwWriteTransfer(
              v25,
              (unsigned int)TPM_KSR_INFORMATION,
              v26,
              (unsigned int)L"KSR cancel: IoFreeKsrPersistentMemory",
              v24);
          *((_QWORD *)v4 + 7) = 0;
        }
      }
    }
    else
    {
      v6 = TpmStack::SetIsNextRebootKsr(v3, 1);
      if ( (TPMEnableBits & 2) != 0 )
        McTemplateK0zq_EtwWriteTransfer(
          v7,
          (unsigned int)TPM_KSR_INFORMATION,
          v8,
          (unsigned int)L"KSR prepare: SetIsNextRebootKsr(true)",
          v6);
      v29[0] = *((_DWORD *)v4 + 12);
      v29[1] = TpmTransportType::m_Version;
      v29[2] = WPP_MAIN_CB.DeviceExtension;
      v29[3] = TpmTransportType::m_TalkingToTpmSimulator;
      v9 = (*((__int64 (__fastcall **)(PKDPC, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 118))(
             WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
             *(_QWORD *)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc);
      v10 = IoReserveKsrPersistentMemory(v9, 0, 16);
      v13 = v10;
      if ( (TPMEnableBits & 2) != 0 )
        McTemplateK0zq_EtwWriteTransfer(
          v11,
          (unsigned int)TPM_KSR_INFORMATION,
          v12,
          (unsigned int)L"KSR prepare: IoReserveKsrPersistentMemory",
          v10);
      if ( v13 < 0 )
      {
        if ( v28 )
        {
          v17 = IoFreeKsrPersistentMemory(v28);
          if ( (TPMEnableBits & 2) != 0 )
            McTemplateK0zq_EtwWriteTransfer(
              v18,
              (unsigned int)TPM_KSR_INFORMATION,
              v19,
              (unsigned int)L"KSR prepare: IoFreeKsrPersistentMemory",
              v17);
        }
      }
      else
      {
        v14 = IoWriteKsrPersistentMemory(v28, v29, 16);
        if ( (TPMEnableBits & 2) != 0 )
          McTemplateK0zq_EtwWriteTransfer(
            v15,
            (unsigned int)TPM_KSR_INFORMATION,
            v16,
            (unsigned int)L"KSR prepare: IoReserveKsrPersistentMemory",
            v14);
        *((_QWORD *)v4 + 7) = v28;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14001e130  mov     [rsp+arg_0], rbx
0x14001e135  mov     [rsp+arg_10], rbp
0x14001e13a  push    rsi
0x14001e13b  sub     rsp, 50h
0x14001e13f  mov     rax, cs:__security_cookie
0x14001e146  xor     rax, rsp
0x14001e149  mov     [rsp+58h+var_10], rax
0x14001e14e  cmp     word ptr [rcx], 1
0x14001e152  mov     rbx, rcx
0x14001e155  jnz     loc_14001E36B
0x14001e15b  cmp     word ptr [rcx+2], 14h
0x14001e160  jb      loc_14001E36B
0x14001e166  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14001e16d  mov     r8, cs:off_140047018
0x14001e174  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14001e17b  mov     rax, [rax+650h]
0x14001e182  call    _guard_dispatch_icall
0x14001e187  mov     rsi, rax
0x14001e18a  mov     rcx, [rax+38h]
0x14001e18e  mov     [rsp+58h+var_28], rcx
0x14001e193  mov     rcx, [rbx+4]
0x14001e197  sub     rcx, qword ptr cs:GUID_KERNEL_SOFT_RESTART_PREPARE.Data1
0x14001e19e  jnz     short loc_14001E1AB
0x14001e1a0  mov     rcx, [rbx+0Ch]
0x14001e1a4  sub     rcx, qword ptr cs:GUID_KERNEL_SOFT_RESTART_PREPARE.Data4
0x14001e1ab  test    rcx, rcx
0x14001e1ae  jnz     loc_14001E2E7
0x14001e1b4  mov     dl, 1; bool
0x14001e1b6  mov     rcx, rsi; this
0x14001e1b9  call    ?SetIsNextRebootKsr@TpmStack@@QEAAJ_N@Z; TpmStack::SetIsNextRebootKsr(bool)
0x14001e1be  test    cs:TPMEnableBits, 2
0x14001e1c5  lea     rbx, TPM_KSR_INFORMATION
0x14001e1cc  jz      short loc_14001E1E1
0x14001e1ce  lea     r9, aKsrPrepareSeti; "KSR prepare: SetIsNextRebootKsr(true)"
0x14001e1d5  mov     dword ptr [rsp+58h+var_38], eax
0x14001e1d9  mov     rdx, rbx
0x14001e1dc  call    McTemplateK0zq_EtwWriteTransfer
0x14001e1e1  mov     eax, [rsi+30h]
0x14001e1e4  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14001e1eb  mov     [rsp+58h+var_20], eax
0x14001e1ef  mov     eax, cs:?m_Version@TpmTransportType@@0W4VERSION@1@A; TpmTransportType::VERSION TpmTransportType::m_Version
0x14001e1f5  mov     [rsp+58h+var_1C], eax
0x14001e1f9  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceExtension
0x14001e1ff  mov     [rsp+58h+var_18], eax
0x14001e203  mov     eax, cs:?m_TalkingToTpmSimulator@TpmTransportType@@0HA; int TpmTransportType::m_TalkingToTpmSimulator
0x14001e209  mov     [rsp+58h+var_14], eax
0x14001e20d  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14001e214  mov     rdx, [rcx]
0x14001e217  mov     rax, [rax+3B0h]
0x14001e21e  call    _guard_dispatch_icall
0x14001e223  xor     r9d, r9d
0x14001e226  lea     rcx, [rsp+58h+var_28]
0x14001e22b  mov     [rsp+58h+var_38], rcx
0x14001e230  xor     edx, edx
0x14001e232  mov     rcx, rax
0x14001e235  lea     r8d, [r9+10h]
0x14001e239  call    cs:__imp_IoReserveKsrPersistentMemory
0x14001e240  nop     dword ptr [rax+rax+00h]
0x14001e245  test    cs:TPMEnableBits, 2
0x14001e24c  mov     ebp, eax
0x14001e24e  jz      short loc_14001E263
0x14001e250  lea     r9, aKsrPrepareIore; "KSR prepare: IoReserveKsrPersistentMemo"...
0x14001e257  mov     dword ptr [rsp+58h+var_38], eax
0x14001e25b  mov     rdx, rbx
0x14001e25e  call    McTemplateK0zq_EtwWriteTransfer
0x14001e263  mov     rcx, [rsp+58h+var_28]
0x14001e268  test    ebp, ebp
0x14001e26a  js      short loc_14001E2AD
0x14001e26c  mov     r8d, 10h
0x14001e272  lea     rdx, [rsp+58h+var_20]
0x14001e277  call    cs:__imp_IoWriteKsrPersistentMemory
0x14001e27e  nop     dword ptr [rax+rax+00h]
0x14001e283  test    cs:TPMEnableBits, 2
0x14001e28a  jz      short loc_14001E29F
0x14001e28c  lea     r9, aKsrPrepareIore; "KSR prepare: IoReserveKsrPersistentMemo"...
0x14001e293  mov     dword ptr [rsp+58h+var_38], eax
0x14001e297  mov     rdx, rbx
0x14001e29a  call    McTemplateK0zq_EtwWriteTransfer
0x14001e29f  mov     rax, [rsp+58h+var_28]
0x14001e2a4  mov     [rsi+38h], rax
0x14001e2a8  jmp     loc_14001E36B
0x14001e2ad  test    rcx, rcx
0x14001e2b0  jz      loc_14001E36B
0x14001e2b6  call    cs:__imp_IoFreeKsrPersistentMemory
0x14001e2bd  nop     dword ptr [rax+rax+00h]
0x14001e2c2  test    cs:TPMEnableBits, 2
0x14001e2c9  jz      loc_14001E36B
0x14001e2cf  lea     r9, aKsrPrepareIofr; "KSR prepare: IoFreeKsrPersistentMemory"
0x14001e2d6  mov     dword ptr [rsp+58h+var_38], eax
0x14001e2da  mov     rdx, rbx
0x14001e2dd  call    McTemplateK0zq_EtwWriteTransfer
0x14001e2e2  jmp     loc_14001E36B
0x14001e2e7  mov     rax, [rbx+4]
0x14001e2eb  sub     rax, qword ptr cs:GUID_KERNEL_SOFT_RESTART_CANCEL.Data1
0x14001e2f2  jnz     short loc_14001E2FF
0x14001e2f4  mov     rax, [rbx+0Ch]
0x14001e2f8  sub     rax, qword ptr cs:GUID_KERNEL_SOFT_RESTART_CANCEL.Data4
0x14001e2ff  test    rax, rax
0x14001e302  jnz     short loc_14001E36B
0x14001e304  xor     edx, edx; bool
0x14001e306  mov     rcx, rsi; this
0x14001e309  call    ?SetIsNextRebootKsr@TpmStack@@QEAAJ_N@Z; TpmStack::SetIsNextRebootKsr(bool)
0x14001e30e  test    cs:TPMEnableBits, 2
0x14001e315  lea     rbx, TPM_KSR_INFORMATION
0x14001e31c  jz      short loc_14001E331
0x14001e31e  lea     r9, aKsrCancelSetis; "KSR cancel: SetIsNextRebootKsr(false)"
0x14001e325  mov     dword ptr [rsp+58h+var_38], eax
0x14001e329  mov     rdx, rbx
0x14001e32c  call    McTemplateK0zq_EtwWriteTransfer
0x14001e331  mov     rcx, [rsp+58h+var_28]
0x14001e336  test    rcx, rcx
0x14001e339  jz      short loc_14001E36B
0x14001e33b  call    cs:__imp_IoFreeKsrPersistentMemory
0x14001e342  nop     dword ptr [rax+rax+00h]
0x14001e347  test    cs:TPMEnableBits, 2
0x14001e34e  jz      short loc_14001E363
0x14001e350  lea     r9, aKsrCancelIofre; "KSR cancel: IoFreeKsrPersistentMemory"
0x14001e357  mov     dword ptr [rsp+58h+var_38], eax
0x14001e35b  mov     rdx, rbx
0x14001e35e  call    McTemplateK0zq_EtwWriteTransfer
0x14001e363  mov     qword ptr [rsi+38h], 0
0x14001e36b  xor     eax, eax
0x14001e36d  mov     rcx, [rsp+58h+var_10]
0x14001e372  xor     rcx, rsp; StackCookie
0x14001e375  call    __security_check_cookie
0x14001e37a  mov     rbx, [rsp+58h+arg_0]
0x14001e37f  mov     rbp, [rsp+58h+arg_10]
0x14001e384  add     rsp, 50h
0x14001e388  pop     rsi
0x14001e389  retn
```
