# UbpmSystemInterfaceCleanup(void)

- ea: `0x180029e14`
- end: `0x180029fb4`
- name: `?UbpmSystemInterfaceCleanup@@YAXXZ`
- size: `416`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180029c70`

## callees

- `0x1800284b4`
- `0x180029e14`
- `0x1800347bc`
- `0x1800347e4`
- `0x180034844`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180029eca`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180029eca`
- `ntdll!RtlNtStatusToDosError` at `0x180029ed6`
- `ntdll!RtlNtStatusToDosError` at `0x180029ed6`
- `api-ms-win-oobe-notification-l1-1-0!UnregisterWaitUntilOOBECompleted` at `0x180029e2a`
- `api-ms-win-oobe-notification-l1-1-0!UnregisterWaitUntilOOBECompleted` at `0x180029e2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029f45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029f45`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180029e5b`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180029e5b`

## pseudocode

```c
void UbpmSystemInterfaceCleanup(void)
{
  PVOID *v0; // rcx
  __int64 i; // rbx
  DWORD v2; // eax
  __int64 v3; // rdi
  __int64 v4; // rbx
  NTSTATUS v5; // eax
  ULONG v6; // eax
  __int64 v7; // r8

  if ( qword_18004CA68 )
    UnregisterWaitUntilOOBECompleted();
  v0 = (PVOID *)WPP_GLOBAL_Control;
  for ( i = 0; i != 2; ++i )
  {
    if ( !*(&g_PoSubscriptions + 3 * i) )
      continue;
    v2 = PowerSettingUnregisterNotification(*(&g_PoSubscriptions + 3 * i));
    if ( !v2 )
    {
      *(&g_PoSubscriptions + 3 * i) = 0;
      goto LABEL_10;
    }
    v0 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF__guid_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        &WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids,
        *((_QWORD *)&off_18004C048 + 3 * i),
        v2);
LABEL_10:
      v0 = (PVOID *)WPP_GLOBAL_Control;
      continue;
    }
  }
  v3 = 0;
  v4 = 0;
  do
  {
    if ( !*(struct _UBPM_WNF_SUBSCRIPTION near **)((char *)&g_WnfSubscriptions + v4 * 8) )
      goto LABEL_20;
    v5 = RtlUnsubscribeWnfNotificationWaitForCompletion(*(struct _UBPM_WNF_SUBSCRIPTION near **)((char *)&g_WnfSubscriptions
                                                                                               + v4 * 8));
    if ( v5 >= 0 )
    {
      *(struct _UBPM_WNF_SUBSCRIPTION near **)((char *)&g_WnfSubscriptions + v4 * 8) = 0;
      goto LABEL_19;
    }
    v6 = RtlNtStatusToDosError(v5);
    v0 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_DDd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        v7,
        LODWORD(qword_18004C188[v4]),
        HIDWORD(qword_18004C188[v4]),
        v6);
LABEL_19:
      v0 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_20:
    ++v3;
    v4 += 3;
  }
  while ( v3 != 3 );
  if ( hObject )
  {
    CloseHandle(hObject);
    v0 = (PVOID *)WPP_GLOBAL_Control;
    hObject = 0;
  }
  if ( qword_18004C008 )
  {
    UbpmUtilsRegCloseKey(qword_18004C008);
    v0 = (PVOID *)WPP_GLOBAL_Control;
    qword_18004C008 = 0;
  }
  LOBYTE(g_RegSubscriptions) = 0;
  if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 4) != 0 )
    WPP_SF_(v0[2], 19, &WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids);
}

```

## disassembly

```asm
0x180029e14  push    rbx
0x180029e16  push    rbp
0x180029e17  push    rdi
0x180029e18  push    r14
0x180029e1a  sub     rsp, 38h
0x180029e1e  mov     rcx, cs:qword_18004CA68
0x180029e25  test    rcx, rcx
0x180029e28  jz      short loc_180029E30
0x180029e2a  call    cs:__imp_UnregisterWaitUntilOOBECompleted
0x180029e30  mov     rcx, cs:WPP_GLOBAL_Control
0x180029e37  lea     r14, __ImageBase
0x180029e3e  xor     ebx, ebx
0x180029e40  lea     rbp, WPP_GLOBAL_Control
0x180029e47  lea     rdi, [rbx+rbx*2]
0x180029e4b  mov     rax, rva ?g_PoSubscriptions@@3PAU_UBPM_POWER_SUBSCRIPTION@@A[r14+rdi*8]; _UBPM_POWER_SUBSCRIPTION near * g_PoSubscriptions ...
0x180029e53  test    rax, rax
0x180029e56  jz      short loc_180029EAD
0x180029e58  mov     rcx, rax; RegistrationHandle
0x180029e5b  call    cs:__imp_PowerSettingUnregisterNotification
0x180029e61  test    eax, eax
0x180029e63  jz      short loc_180029E9A
0x180029e65  mov     rcx, cs:WPP_GLOBAL_Control
0x180029e6c  cmp     rcx, rbp
0x180029e6f  jz      short loc_180029EAD
0x180029e71  test    byte ptr [rcx+1Ch], 1
0x180029e75  jz      short loc_180029EAD
0x180029e77  mov     r9, rva off_18004C048[r14+rdi*8]
0x180029e7f  lea     r8, WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids
0x180029e86  mov     rcx, [rcx+10h]
0x180029e8a  mov     edx, 11h
0x180029e8f  mov     [rsp+58h+var_38], eax
0x180029e93  call    WPP_SF__guid_d
0x180029e98  jmp     short loc_180029EA6
0x180029e9a  mov     rva ?g_PoSubscriptions@@3PAU_UBPM_POWER_SUBSCRIPTION@@A[r14+rdi*8], 0; _UBPM_POWER_SUBSCRIPTION near * g_PoSubscriptions ...
0x180029ea6  mov     rcx, cs:WPP_GLOBAL_Control
0x180029ead  inc     rbx
0x180029eb0  cmp     rbx, 2
0x180029eb4  jnz     short loc_180029E47
0x180029eb6  xor     edi, edi
0x180029eb8  xor     ebx, ebx
0x180029eba  mov     rax, [rbx+r14+4C180h]
0x180029ec2  test    rax, rax
0x180029ec5  jz      short loc_180029F29
0x180029ec7  mov     rcx, rax
0x180029eca  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180029ed0  test    eax, eax
0x180029ed2  jns     short loc_180029F16
0x180029ed4  mov     ecx, eax; Status
0x180029ed6  call    cs:__imp_RtlNtStatusToDosError
0x180029edc  mov     rcx, cs:WPP_GLOBAL_Control
0x180029ee3  cmp     rcx, rbp
0x180029ee6  jz      short loc_180029F29
0x180029ee8  test    byte ptr [rcx+1Ch], 1
0x180029eec  jz      short loc_180029F29
0x180029eee  mov     r9d, [rbx+r14+4C188h]
0x180029ef6  mov     edx, 12h
0x180029efb  mov     rcx, [rcx+10h]
0x180029eff  mov     [rsp+58h+var_30], eax
0x180029f03  mov     eax, [rbx+r14+4C18Ch]
0x180029f0b  mov     [rsp+58h+var_38], eax
0x180029f0f  call    WPP_SF_DDd
0x180029f14  jmp     short loc_180029F22
0x180029f16  mov     qword ptr [rbx+r14+4C180h], 0
0x180029f22  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f29  inc     rdi
0x180029f2c  add     rbx, 18h
0x180029f30  cmp     rdi, 3
0x180029f34  jnz     short loc_180029EBA
0x180029f36  mov     rax, cs:hObject
0x180029f3d  test    rax, rax
0x180029f40  jz      short loc_180029F5D
0x180029f42  mov     rcx, rax; hObject
0x180029f45  call    cs:__imp_CloseHandle
0x180029f4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f52  mov     cs:hObject, 0
0x180029f5d  mov     rax, cs:qword_18004C008
0x180029f64  test    rax, rax
0x180029f67  jz      short loc_180029F83
0x180029f69  mov     rcx, rax; void *
0x180029f6c  call    ?UbpmUtilsRegCloseKey@@YAXPEAX@Z; UbpmUtilsRegCloseKey(void *)
0x180029f71  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f78  mov     cs:qword_18004C008, 0
0x180029f83  mov     cs:?g_RegSubscriptions@@3PAU_UBPM_REGISTRY_SUBSCRIPTION@@A, 0; _UBPM_REGISTRY_SUBSCRIPTION near * g_RegSubscriptions
0x180029f8a  cmp     rcx, rbp
0x180029f8d  jz      short loc_180029FAA
0x180029f8f  test    byte ptr [rcx+1Ch], 4
0x180029f93  jz      short loc_180029FAA
0x180029f95  mov     rcx, [rcx+10h]
0x180029f99  lea     r8, WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids
0x180029fa0  mov     edx, 13h
0x180029fa5  call    WPP_SF_
0x180029faa  add     rsp, 38h
0x180029fae  pop     r14
0x180029fb0  pop     rdi
0x180029fb1  pop     rbp
0x180029fb2  pop     rbx
0x180029fb3  retn
```
