# TpmTaskTrigger::NotifyProvisioningRequired_Thread(void *)

- ea: `0x140005370`
- end: `0x1400055d6`
- name: `?NotifyProvisioningRequired_Thread@TpmTaskTrigger@@CAXPEAX@Z`
- size: `614`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x140005370`
- `0x1400055dc`
- `0x1400078b8`
- `0x14001a95c`
- `0x14001b1ac`
- `0x1400220b8`
- `0x140044f7c`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x14000552d`
- `ntoskrnl!KeClearEvent` at `0x14000552d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400053d1`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400053d1`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14000545b`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14000545b`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140005589`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140005589`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400055a1`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400055a1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400054f5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400054f5`
- `ntoskrnl!ObfDereferenceObject` at `0x1400055b5`
- `ntoskrnl!ObfDereferenceObject` at `0x1400055b5`
- `ntoskrnl!IoCreateNotificationEvent` at `0x140005509`
- `ntoskrnl!IoCreateNotificationEvent` at `0x140005509`

## pseudocode

```c
void __fastcall TpmTaskTrigger::NotifyProvisioningRequired_Thread(char *a1)
{
  int v1; // edi
  unsigned int v2; // ebx
  void **v4; // r14
  int v5; // eax
  void *v6; // rax
  PVOID v7; // rbx
  int v8; // eax
  int v9; // ecx
  int v10; // r8d
  struct _KEVENT *v11; // rax
  int v12; // ecx
  int v13; // r8d
  PVOID Object[2]; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-10h] BYREF
  PVOID v16; // [rsp+90h] [rbp+30h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+98h] [rbp+38h] BYREF
  void *EventHandle; // [rsp+A0h] [rbp+40h] BYREF

  v16 = 0;
  v1 = 0;
  EventHandle = 0;
  *(_OWORD *)Object = 0;
  v2 = 0;
  DestinationString = 0;
  *((_DWORD *)a1 + 6) = 1;
  while ( v2 < 0x1E )
  {
    Timeout.QuadPart = -100000000;
    v4 = (void **)(a1 + 8);
    v1 = KeWaitForSingleObject(*((PVOID *)a1 + 1), Executive, 0, 0, &Timeout);
    if ( v1 < 1 )
      goto LABEL_24;
    v5 = NamedEvent::Initialize((NamedEvent *)&v16, *((const unsigned __int16 **)a1 + 2));
    v1 = v5;
    if ( v5 >= 0 )
      goto LABEL_10;
    if ( v5 != -1073741772 && v5 != -1073741766 )
      goto LABEL_24;
    ++v2;
  }
  if ( v1 < 0 )
  {
LABEL_24:
    v7 = v16;
    goto LABEL_25;
  }
  v4 = (void **)(a1 + 8);
LABEL_10:
  v6 = *v4;
  v7 = v16;
  *((_DWORD *)a1 + 6) = 2;
  Object[0] = v6;
  Object[1] = v7;
  v1 = KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, 0, 0);
  if ( v1 == 1 )
  {
    v8 = TpmEnsureWindowsAIKPathExists();
    v1 = v8;
    if ( v8 < 0 && (TPMEnableBits & 1) != 0 )
      McTemplateK0dqq_EtwWriteTransfer(v9, (unsigned int)TPM_WINDOWS_AIK_DIR_CREATE_FAILED, v10, 20, 173, v8);
    TpmRegistry::DeleteKeyValue(3, L"LastPPIResponseHandled");
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_dc38ef50cff43ef467b61332d5081cb1_Traceguids);
    RtlInitUnicodeString(&DestinationString, L"\\BaseNamedObjects\\TpmProvisioningEvent");
    v11 = IoCreateNotificationEvent(&DestinationString, &EventHandle);
    if ( v11 )
    {
      KeClearEvent(v11);
    }
    else if ( (TPMEnableBits & 1) != 0 )
    {
      McTemplateK0dq_EtwWriteTransfer();
    }
    if ( (TPMEnableBits & 2) != 0 )
      McTemplateK0dqq_EtwWriteTransfer(v12, (unsigned int)TPM_PROVISIONING_REQUIRED, v13, 20, 217, 0);
    ZwUpdateWnfStateData(&WNF_TPM_PROVISION_TRIGGER, 0, 0, 0, 0, 0, 0);
    *((_DWORD *)a1 + 6) = 3;
  }
LABEL_25:
  PsTerminateSystemThread(v1);
  if ( v7 )
    ObfDereferenceObject(v7);
}

```

## disassembly

```asm
0x140005370  mov     [rsp-28h+arg_18], rbx
0x140005375  push    rbp
0x140005376  push    rsi
0x140005377  push    rdi
0x140005378  push    r14
0x14000537a  push    r15
0x14000537c  mov     rbp, rsp
0x14000537f  sub     rsp, 60h
0x140005383  xorps   xmm0, xmm0
0x140005386  mov     [rbp+arg_0], 0
0x14000538e  xor     edi, edi
0x140005390  mov     [rbp+EventHandle], 0
0x140005398  movups  xmmword ptr [rbp+Object], xmm0
0x14000539c  xor     ebx, ebx
0x14000539e  mov     rsi, rcx
0x1400053a1  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400053a5  mov     dword ptr [rcx+18h], 1
0x1400053ac  cmp     ebx, 1Eh
0x1400053af  jnb     short loc_140005411
0x1400053b1  lea     rax, [rbp+arg_8]
0x1400053b5  mov     qword ptr [rbp+arg_8], 0FFFFFFFFFA0A1F00h
0x1400053bd  lea     r14, [rsi+8]
0x1400053c1  mov     [rsp+60h+Timeout], rax; Timeout
0x1400053c6  mov     rcx, [r14]; Object
0x1400053c9  xor     r9d, r9d; Alertable
0x1400053cc  xor     r8d, r8d; WaitMode
0x1400053cf  xor     edx, edx; WaitReason
0x1400053d1  call    cs:__imp_KeWaitForSingleObject
0x1400053d8  nop     dword ptr [rax+rax+00h]
0x1400053dd  mov     edi, eax
0x1400053df  cmp     eax, 1
0x1400053e2  jl      loc_14000559B
0x1400053e8  mov     rdx, [rsi+10h]; unsigned __int16 *
0x1400053ec  lea     rcx, [rbp+arg_0]; this
0x1400053f0  call    ?Initialize@NamedEvent@@QEAAJPEBG@Z; NamedEvent::Initialize(ushort const *)
0x1400053f5  mov     edi, eax
0x1400053f7  test    eax, eax
0x1400053f9  jns     short loc_14000541D
0x1400053fb  cmp     eax, 0C0000034h
0x140005400  jz      short loc_14000540D
0x140005402  cmp     eax, 0C000003Ah
0x140005407  jnz     loc_14000559B
0x14000540d  inc     ebx
0x14000540f  jmp     short loc_1400053AC
0x140005411  test    edi, edi
0x140005413  js      loc_14000559B
0x140005419  lea     r14, [rsi+8]
0x14000541d  mov     rax, [r14]
0x140005420  lea     rdx, [rbp+Object]; Object
0x140005424  mov     rbx, [rbp+arg_0]
0x140005428  mov     ecx, 2; Count
0x14000542d  mov     [rsp+60h+WaitBlockArray], 0; WaitBlockArray
0x140005436  xor     r9d, r9d; WaitReason
0x140005439  mov     [rsp+60h+var_30], 0; Timeout
0x140005442  mov     [rsp+60h+Alertable], 0; Alertable
0x140005447  lea     r8d, [rcx-1]; WaitType
0x14000544b  mov     [rsi+18h], ecx
0x14000544e  mov     [rbp+Object], rax
0x140005452  mov     [rbp+Object+8], rbx
0x140005456  mov     byte ptr [rsp+60h+Timeout], 0; WaitMode
0x14000545b  call    cs:__imp_KeWaitForMultipleObjects
0x140005462  nop     dword ptr [rax+rax+00h]
0x140005467  mov     edi, eax
0x140005469  cmp     eax, 1
0x14000546c  jnz     loc_14000559F
0x140005472  call    ?TpmEnsureWindowsAIKPathExists@@YAJXZ; TpmEnsureWindowsAIKPathExists(void)
0x140005477  mov     edi, eax
0x140005479  mov     r14d, 14h
0x14000547f  test    eax, eax
0x140005481  jns     short loc_1400054A7
0x140005483  test    cs:TPMEnableBits, 1
0x14000548a  jz      short loc_1400054A7
0x14000548c  mov     dword ptr [rsp+60h+Alertable], eax
0x140005490  lea     rdx, TPM_WINDOWS_AIK_DIR_CREATE_FAILED
0x140005497  mov     r9d, r14d
0x14000549a  mov     dword ptr [rsp+60h+Timeout], 0ADh
0x1400054a2  call    McTemplateK0dqq_EtwWriteTransfer
0x1400054a7  mov     r15d, 3
0x1400054ad  lea     rdx, aLastppirespons; "LastPPIResponseHandled"
0x1400054b4  mov     ecx, r15d
0x1400054b7  call    ?DeleteKeyValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBG@Z; TpmRegistry::DeleteKeyValue(TpmRegistry::KEY_VALUES,ushort const *)
0x1400054bc  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400054c3  lea     rax, WPP_GLOBAL_Control
0x1400054ca  cmp     rcx, rax
0x1400054cd  jz      short loc_1400054EA
0x1400054cf  mov     eax, [rcx+2Ch]
0x1400054d2  test    al, 4
0x1400054d4  jz      short loc_1400054EA
0x1400054d6  mov     rcx, [rcx+18h]
0x1400054da  lea     edx, [r15+7]
0x1400054de  lea     r8, WPP_dc38ef50cff43ef467b61332d5081cb1_Traceguids
0x1400054e5  call    WPP_SF_
0x1400054ea  lea     rdx, SourceString; "\\BaseNamedObjects\\TpmProvisioningEven"...
0x1400054f1  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400054f5  call    cs:__imp_RtlInitUnicodeString
0x1400054fc  nop     dword ptr [rax+rax+00h]
0x140005501  lea     rdx, [rbp+EventHandle]; EventHandle
0x140005505  lea     rcx, [rbp+DestinationString]; EventName
0x140005509  call    cs:__imp_IoCreateNotificationEvent
0x140005510  nop     dword ptr [rax+rax+00h]
0x140005515  test    rax, rax
0x140005518  jnz     short loc_14000552A
0x14000551a  test    cs:TPMEnableBits, 1
0x140005521  jz      short loc_140005539
0x140005523  call    McTemplateK0dq_EtwWriteTransfer
0x140005528  jmp     short loc_140005539
0x14000552a  mov     rcx, rax; Event
0x14000552d  call    cs:__imp_KeClearEvent
0x140005534  nop     dword ptr [rax+rax+00h]
0x140005539  test    cs:TPMEnableBits, 2
0x140005540  jz      short loc_140005561
0x140005542  mov     dword ptr [rsp+60h+Alertable], 0
0x14000554a  lea     rdx, TPM_PROVISIONING_REQUIRED
0x140005551  mov     r9d, r14d
0x140005554  mov     dword ptr [rsp+60h+Timeout], 0D9h
0x14000555c  call    McTemplateK0dqq_EtwWriteTransfer
0x140005561  mov     dword ptr [rsp+60h+var_30], 0
0x140005569  lea     rcx, WNF_TPM_PROVISION_TRIGGER
0x140005570  mov     dword ptr [rsp+60h+Alertable], 0
0x140005578  xor     r9d, r9d
0x14000557b  xor     r8d, r8d
0x14000557e  mov     [rsp+60h+Timeout], 0
0x140005587  xor     edx, edx
0x140005589  call    cs:__imp_ZwUpdateWnfStateData
0x140005590  nop     dword ptr [rax+rax+00h]
0x140005595  mov     [rsi+18h], r15d
0x140005599  jmp     short loc_14000559F
0x14000559b  mov     rbx, [rbp+arg_0]
0x14000559f  mov     ecx, edi; ExitStatus
0x1400055a1  call    cs:__imp_PsTerminateSystemThread
0x1400055a8  nop     dword ptr [rax+rax+00h]
0x1400055ad  test    rbx, rbx
0x1400055b0  jz      short loc_1400055C1
0x1400055b2  mov     rcx, rbx; Object
0x1400055b5  call    cs:__imp_ObfDereferenceObject
0x1400055bc  nop     dword ptr [rax+rax+00h]
0x1400055c1  mov     rbx, [rsp+60h+arg_18]
0x1400055c9  add     rsp, 60h
0x1400055cd  pop     r15
0x1400055cf  pop     r14
0x1400055d1  pop     rdi
0x1400055d2  pop     rsi
0x1400055d3  pop     rbp
0x1400055d4  retn
```
