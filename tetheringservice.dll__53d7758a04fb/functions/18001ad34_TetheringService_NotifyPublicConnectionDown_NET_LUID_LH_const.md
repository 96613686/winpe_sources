# TetheringService::NotifyPublicConnectionDown(_NET_LUID_LH const &)

- ea: `0x18001ad34`
- end: `0x18001ae68`
- name: `?NotifyPublicConnectionDown@TetheringService@@QEAAXAEBT_NET_LUID_LH@@@Z`
- size: `308`
- prototype: `void __fastcall(TetheringService *this, const union _NET_LUID_LH *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180019fe0`

## callees

- `0x180002590`
- `0x18000bf4c`
- `0x18001ad34`
- `0x18002b1f0`
- `0x18002bad8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ae42`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ae42`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x18001adc0`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x18001adc0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18001adfb`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18001adfb`

## pseudocode

```c
void __fastcall TetheringService::NotifyPublicConnectionDown(TetheringService *this, const union _NET_LUID_LH *a2)
{
  int v4; // ebp
  void *v5; // rbx
  _DWORD *SettingValueWithGuidInternal; // rax
  GUID InterfaceGuid; // [rsp+28h] [rbp-30h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 296, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  v4 = 20;
  v5 = 0;
  if ( (unsigned __int16)(*((_WORD *)&a2->Info + 3) - 243) <= 1u )
  {
    InterfaceGuid = 0;
    if ( ConvertInterfaceLuidToGuid(a2, &InterfaceGuid) < 0 )
      goto LABEL_10;
    SettingValueWithGuidInternal = (_DWORD *)TetheringSettingsGetSettingValueWithGuidInternal(0, &InterfaceGuid);
  }
  else
  {
    SettingValueWithGuidInternal = (_DWORD *)TetheringSettingsGetSettingValueGlobalInternal(0);
  }
  v5 = SettingValueWithGuidInternal;
  if ( SettingValueWithGuidInternal )
    v4 = *SettingValueWithGuidInternal;
LABEL_10:
  if ( ChangeTimerQueueTimer(*((HANDLE *)this + 201), *((HANDLE *)this + 200), 60000 * v4, 0xFFFFFFFF) )
  {
    *((_DWORD *)this + 404) = 60000 * v4;
    *((_BYTE *)this + 1620) = 1;
  }
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 297, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  if ( v5 )
    free(v5);
}

```

## disassembly

```asm
0x18001ad34  mov     [rsp+arg_10], rbx
0x18001ad39  mov     [rsp+arg_18], rbp
0x18001ad3e  push    rsi
0x18001ad3f  push    rdi
0x18001ad40  push    r14
0x18001ad42  sub     rsp, 40h
0x18001ad46  mov     rax, cs:__security_cookie
0x18001ad4d  xor     rax, rsp
0x18001ad50  mov     [rsp+58h+var_20], rax
0x18001ad55  mov     rsi, rdx
0x18001ad58  mov     rdi, rcx
0x18001ad5b  lea     r14, WPP_GLOBAL_Control
0x18001ad62  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad69  cmp     rcx, r14
0x18001ad6c  jz      short loc_18001AD89
0x18001ad6e  test    byte ptr [rcx+1Ch], 8
0x18001ad72  jz      short loc_18001AD89
0x18001ad74  mov     edx, 128h
0x18001ad79  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001ad80  mov     rcx, [rcx+10h]
0x18001ad84  call    WPP_SF_
0x18001ad89  mov     ebp, 14h
0x18001ad8e  xor     ebx, ebx
0x18001ad90  mov     [rsp+58h+var_38], rbx
0x18001ad95  mov     ecx, 0F3h
0x18001ad9a  movzx   eax, word ptr [rsi+6]
0x18001ad9e  sub     ax, cx
0x18001ada1  cmp     ax, 1
0x18001ada5  jbe     short loc_18001ADB0
0x18001ada7  xor     ecx, ecx
0x18001ada9  call    ?TetheringSettingsGetSettingValueGlobalInternal@@YAPEAXW4TetheringSettingGlobal@@@Z; TetheringSettingsGetSettingValueGlobalInternal(TetheringSettingGlobal)
0x18001adae  jmp     short loc_18001ADD6
0x18001adb0  xorps   xmm0, xmm0
0x18001adb3  movups  xmmword ptr [rsp+58h+InterfaceGuid.Data1], xmm0
0x18001adb8  lea     rdx, [rsp+58h+InterfaceGuid]; InterfaceGuid
0x18001adbd  mov     rcx, rsi; InterfaceLuid
0x18001adc0  call    cs:__imp_ConvertInterfaceLuidToGuid
0x18001adc6  test    eax, eax
0x18001adc8  js      short loc_18001ADE0
0x18001adca  lea     rdx, [rsp+58h+InterfaceGuid]
0x18001adcf  xor     ecx, ecx
0x18001add1  call    ?TetheringSettingsGetSettingValueWithGuidInternal@@YAPEAXW4TetheringSettingPerIccid@@AEBU_GUID@@@Z; TetheringSettingsGetSettingValueWithGuidInternal(TetheringSettingPerIccid,_GUID const &)
0x18001add6  mov     rbx, rax
0x18001add9  test    rax, rax
0x18001addc  jz      short loc_18001ADE0
0x18001adde  mov     ebp, [rax]
0x18001ade0  imul    esi, ebp, 0EA60h
0x18001ade6  or      r9d, 0FFFFFFFFh; Period
0x18001adea  mov     r8d, esi; DueTime
0x18001aded  mov     rdx, [rdi+640h]; Timer
0x18001adf4  mov     rcx, [rdi+648h]; TimerQueue
0x18001adfb  call    cs:__imp_ChangeTimerQueueTimer
0x18001ae01  test    eax, eax
0x18001ae03  jz      short loc_18001AE12
0x18001ae05  mov     [rdi+650h], esi
0x18001ae0b  mov     byte ptr [rdi+654h], 1
0x18001ae12  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae19  cmp     rcx, r14
0x18001ae1c  jz      short loc_18001AE3A
0x18001ae1e  test    byte ptr [rcx+1Ch], 8
0x18001ae22  jz      short loc_18001AE3A
0x18001ae24  mov     edx, 129h
0x18001ae29  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001ae30  mov     rcx, [rcx+10h]
0x18001ae34  call    WPP_SF_
0x18001ae39  nop
0x18001ae3a  test    rbx, rbx
0x18001ae3d  jz      short loc_18001AE48
0x18001ae3f  mov     rcx, rbx; Block
0x18001ae42  call    cs:__imp_free
0x18001ae48  mov     rcx, [rsp+58h+var_20]
0x18001ae4d  xor     rcx, rsp; StackCookie
0x18001ae50  call    __security_check_cookie
0x18001ae55  mov     rbx, [rsp+58h+arg_10]
0x18001ae5a  mov     rbp, [rsp+58h+arg_18]
0x18001ae5f  add     rsp, 40h
0x18001ae63  pop     r14
0x18001ae65  pop     rdi
0x18001ae66  pop     rsi
0x18001ae67  retn
```
