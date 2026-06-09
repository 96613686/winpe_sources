# WerStartSystemErrorHandler

- ea: `0x14000ce68`
- end: `0x14000cfa0`
- name: `WerStartSystemErrorHandler`
- size: `312`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x1400011a0`
- `0x1400100f4`

## callees

- `0x140002750`
- `0x14000ce68`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x14000ceec`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14000ceec`
- `ntoskrnl!ZwQueryWnfStateNameInformation` at `0x14000cebb`
- `ntoskrnl!ZwQueryWnfStateNameInformation` at `0x14000cebb`
- `ntoskrnl!EtwUnregister` at `0x14000cf69`
- `ntoskrnl!EtwUnregister` at `0x14000cf69`
- `ntoskrnl!EtwWrite` at `0x14000cf53`
- `ntoskrnl!EtwWrite` at `0x14000cf53`
- `ntoskrnl!EtwRegister` at `0x14000cf0d`
- `ntoskrnl!EtwRegister` at `0x14000cf0d`
- `ntoskrnl!EtwEventEnabled` at `0x14000cf2c`
- `ntoskrnl!EtwEventEnabled` at `0x14000cf2c`

## pseudocode

```c
__int64 WerStartSystemErrorHandler()
{
  int v0; // ebx
  __int64 result; // rax
  int v2; // [rsp+40h] [rbp-30h] BYREF
  ULONGLONG RegHandle; // [rsp+48h] [rbp-28h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-20h] BYREF

  RegHandle = 0;
  v0 = 0;
  v2 = 0;
  EventDescriptor = 0;
  if ( (int)ZwQueryWnfStateNameInformation(&WNF_WER_SERVICE_START, 1, 0, &v2, 4) >= 0 && v2 )
    v0 = (int)ZwUpdateWnfStateData(&WNF_WER_SERVICE_START, 0, 0, 0, 0, 0, 0) >= 0;
  if ( EtwRegister(&ProviderId, 0, 0, &RegHandle) >= 0 )
  {
    EventDescriptor = 0;
    if ( EtwEventEnabled(RegHandle, &EventDescriptor) && EtwWrite(RegHandle, &EventDescriptor, 0, 0, 0) >= 0 )
      ++v0;
    EtwUnregister(RegHandle);
  }
  result = 0;
  if ( !v0 )
    return 3221225600LL;
  return result;
}

```

## disassembly

```asm
0x14000ce68  mov     [rsp-8+arg_0], rbx
0x14000ce6d  mov     [rsp-8+arg_8], rsi
0x14000ce72  push    rbp
0x14000ce73  mov     rbp, rsp
0x14000ce76  sub     rsp, 70h
0x14000ce7a  mov     rax, cs:__security_cookie
0x14000ce81  xor     rax, rsp
0x14000ce84  mov     [rbp+var_10], rax
0x14000ce88  xorps   xmm0, xmm0
0x14000ce8b  mov     [rbp+RegHandle], 0
0x14000ce93  xor     ebx, ebx
0x14000ce95  mov     [rbp+var_30], 0
0x14000ce9c  lea     r9, [rbp+var_30]
0x14000cea0  mov     dword ptr [rsp+70h+UserData], 4
0x14000cea8  xor     r8d, r8d
0x14000ceab  lea     rcx, WNF_WER_SERVICE_START
0x14000ceb2  movups  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x14000ceb6  lea     esi, [rbx+1]
0x14000ceb9  mov     edx, esi
0x14000cebb  call    cs:__imp_ZwQueryWnfStateNameInformation
0x14000cec2  nop     dword ptr [rax+rax+00h]
0x14000cec7  test    eax, eax
0x14000cec9  js      short loc_14000CEFD
0x14000cecb  cmp     [rbp+var_30], ebx
0x14000cece  jz      short loc_14000CEFD
0x14000ced0  mov     [rsp+70h+var_40], ebx
0x14000ced4  lea     rcx, WNF_WER_SERVICE_START
0x14000cedb  mov     [rsp+70h+var_48], ebx
0x14000cedf  xor     r9d, r9d
0x14000cee2  xor     r8d, r8d
0x14000cee5  mov     [rsp+70h+UserData], rbx
0x14000ceea  xor     edx, edx
0x14000ceec  call    cs:__imp_ZwUpdateWnfStateData
0x14000cef3  nop     dword ptr [rax+rax+00h]
0x14000cef8  test    eax, eax
0x14000cefa  cmovns  ebx, esi
0x14000cefd  lea     r9, [rbp+RegHandle]; RegHandle
0x14000cf01  xor     r8d, r8d; CallbackContext
0x14000cf04  xor     edx, edx; EnableCallback
0x14000cf06  lea     rcx, ProviderId; ProviderId
0x14000cf0d  call    cs:__imp_EtwRegister
0x14000cf14  nop     dword ptr [rax+rax+00h]
0x14000cf19  test    eax, eax
0x14000cf1b  js      short loc_14000CF75
0x14000cf1d  mov     rcx, [rbp+RegHandle]; RegHandle
0x14000cf21  lea     rdx, [rbp+EventDescriptor]; EventDescriptor
0x14000cf25  xorps   xmm0, xmm0
0x14000cf28  movups  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x14000cf2c  call    cs:__imp_EtwEventEnabled
0x14000cf33  nop     dword ptr [rax+rax+00h]
0x14000cf38  test    al, al
0x14000cf3a  jz      short loc_14000CF65
0x14000cf3c  mov     rcx, [rbp+RegHandle]; RegHandle
0x14000cf40  lea     rdx, [rbp+EventDescriptor]; EventDescriptor
0x14000cf44  xor     r9d, r9d; UserDataCount
0x14000cf47  mov     [rsp+70h+UserData], 0; UserData
0x14000cf50  xor     r8d, r8d; ActivityId
0x14000cf53  call    cs:__imp_EtwWrite
0x14000cf5a  nop     dword ptr [rax+rax+00h]
0x14000cf5f  test    eax, eax
0x14000cf61  js      short loc_14000CF65
0x14000cf63  add     ebx, esi
0x14000cf65  mov     rcx, [rbp+RegHandle]; RegHandle
0x14000cf69  call    cs:__imp_EtwUnregister
0x14000cf70  nop     dword ptr [rax+rax+00h]
0x14000cf75  xor     eax, eax
0x14000cf77  mov     ecx, 0C0000080h
0x14000cf7c  test    ebx, ebx
0x14000cf7e  cmovz   eax, ecx
0x14000cf81  mov     rcx, [rbp+var_10]
0x14000cf85  xor     rcx, rsp; StackCookie
0x14000cf88  call    __security_check_cookie
0x14000cf8d  lea     r11, [rsp+70h+var_s0]
0x14000cf92  mov     rbx, [r11+10h]
0x14000cf96  mov     rsi, [r11+18h]
0x14000cf9a  mov     rsp, r11
0x14000cf9d  pop     rbp
0x14000cf9e  retn
```
