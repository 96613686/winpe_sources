# UbpmSystemInterfaceCleanup(void)

- ea: `0x180001bf4`
- end: `0x180001db7`
- name: `?UbpmSystemInterfaceCleanup@@YAXXZ`
- size: `451`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001a3c`

## callees

- `0x180001bf4`
- `0x18002a420`
- `0x180036c60`
- `0x180036c90`
- `0x180036cf8`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180001cb6`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180001cb6`
- `ntdll!RtlNtStatusToDosError` at `0x180001cc8`
- `ntdll!RtlNtStatusToDosError` at `0x180001cc8`
- `api-ms-win-oobe-notification-l1-1-0!UnregisterWaitUntilOOBECompleted` at `0x180001c0a`
- `api-ms-win-oobe-notification-l1-1-0!UnregisterWaitUntilOOBECompleted` at `0x180001c0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d41`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180001c41`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180001c41`

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

  if ( qword_18004FB68 )
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
        *((_QWORD *)&off_18004F048 + 3 * i),
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
        LODWORD(qword_18004F188[v4]),
        HIDWORD(qword_18004F188[v4]),
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
  if ( qword_18004F008 )
  {
    UbpmUtilsRegCloseKey(qword_18004F008);
    v0 = (PVOID *)WPP_GLOBAL_Control;
    qword_18004F008 = 0;
  }
  LOBYTE(g_RegSubscriptions) = 0;
  if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 4) != 0 )
    WPP_SF_(v0[2], 19, &WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids);
}

```

## disassembly

```asm
0x180001bf4  push    rbx
0x180001bf6  push    rbp
0x180001bf7  push    rdi
0x180001bf8  push    r14
0x180001bfa  sub     rsp, 38h
0x180001bfe  mov     rcx, cs:qword_18004FB68
0x180001c05  test    rcx, rcx
0x180001c08  jz      short loc_180001C16
0x180001c0a  call    cs:__imp_UnregisterWaitUntilOOBECompleted
0x180001c11  nop     dword ptr [rax+rax+00h]
0x180001c16  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c1d  lea     r14, __ImageBase
0x180001c24  xor     ebx, ebx
0x180001c26  lea     rbp, WPP_GLOBAL_Control
0x180001c2d  lea     rdi, [rbx+rbx*2]
0x180001c31  mov     rax, rva ?g_PoSubscriptions@@3PAU_UBPM_POWER_SUBSCRIPTION@@A[r14+rdi*8]; _UBPM_POWER_SUBSCRIPTION near * g_PoSubscriptions ...
0x180001c39  test    rax, rax
0x180001c3c  jz      short loc_180001C99
0x180001c3e  mov     rcx, rax; RegistrationHandle
0x180001c41  call    cs:__imp_PowerSettingUnregisterNotification
0x180001c48  nop     dword ptr [rax+rax+00h]
0x180001c4d  test    eax, eax
0x180001c4f  jz      short loc_180001C86
0x180001c51  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c58  cmp     rcx, rbp
0x180001c5b  jz      short loc_180001C99
0x180001c5d  test    byte ptr [rcx+1Ch], 1
0x180001c61  jz      short loc_180001C99
0x180001c63  mov     r9, rva off_18004F048[r14+rdi*8]
0x180001c6b  lea     r8, WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids
0x180001c72  mov     rcx, [rcx+10h]
0x180001c76  mov     edx, 11h
0x180001c7b  mov     [rsp+58h+var_38], eax
0x180001c7f  call    WPP_SF__guid_d
0x180001c84  jmp     short loc_180001C92
0x180001c86  mov     rva ?g_PoSubscriptions@@3PAU_UBPM_POWER_SUBSCRIPTION@@A[r14+rdi*8], 0; _UBPM_POWER_SUBSCRIPTION near * g_PoSubscriptions ...
0x180001c92  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c99  inc     rbx
0x180001c9c  cmp     rbx, 2
0x180001ca0  jnz     short loc_180001C2D
0x180001ca2  xor     edi, edi
0x180001ca4  xor     ebx, ebx
0x180001ca6  mov     rax, [rbx+r14+4F180h]
0x180001cae  test    rax, rax
0x180001cb1  jz      short loc_180001D21
0x180001cb3  mov     rcx, rax
0x180001cb6  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180001cbd  nop     dword ptr [rax+rax+00h]
0x180001cc2  test    eax, eax
0x180001cc4  jns     short loc_180001D0E
0x180001cc6  mov     ecx, eax; Status
0x180001cc8  call    cs:__imp_RtlNtStatusToDosError
0x180001ccf  nop     dword ptr [rax+rax+00h]
0x180001cd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180001cdb  cmp     rcx, rbp
0x180001cde  jz      short loc_180001D21
0x180001ce0  test    byte ptr [rcx+1Ch], 1
0x180001ce4  jz      short loc_180001D21
0x180001ce6  mov     r9d, [rbx+r14+4F188h]
0x180001cee  mov     edx, 12h
0x180001cf3  mov     rcx, [rcx+10h]
0x180001cf7  mov     [rsp+58h+var_30], eax
0x180001cfb  mov     eax, [rbx+r14+4F18Ch]
0x180001d03  mov     [rsp+58h+var_38], eax
0x180001d07  call    WPP_SF_DDd
0x180001d0c  jmp     short loc_180001D1A
0x180001d0e  mov     qword ptr [rbx+r14+4F180h], 0
0x180001d1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d21  inc     rdi
0x180001d24  add     rbx, 18h
0x180001d28  cmp     rdi, 3
0x180001d2c  jnz     loc_180001CA6
0x180001d32  mov     rax, cs:hObject
0x180001d39  test    rax, rax
0x180001d3c  jz      short loc_180001D5F
0x180001d3e  mov     rcx, rax; hObject
0x180001d41  call    cs:__imp_CloseHandle
0x180001d48  nop     dword ptr [rax+rax+00h]
0x180001d4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d54  mov     cs:hObject, 0
0x180001d5f  mov     rax, cs:qword_18004F008
0x180001d66  test    rax, rax
0x180001d69  jz      short loc_180001D85
0x180001d6b  mov     rcx, rax; void *
0x180001d6e  call    ?UbpmUtilsRegCloseKey@@YAXPEAX@Z; UbpmUtilsRegCloseKey(void *)
0x180001d73  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d7a  mov     cs:qword_18004F008, 0
0x180001d85  mov     cs:?g_RegSubscriptions@@3PAU_UBPM_REGISTRY_SUBSCRIPTION@@A, 0; _UBPM_REGISTRY_SUBSCRIPTION near * g_RegSubscriptions
0x180001d8c  cmp     rcx, rbp
0x180001d8f  jz      short loc_180001DAC
0x180001d91  test    byte ptr [rcx+1Ch], 4
0x180001d95  jz      short loc_180001DAC
0x180001d97  mov     rcx, [rcx+10h]
0x180001d9b  lea     r8, WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids
0x180001da2  mov     edx, 13h
0x180001da7  call    WPP_SF_
0x180001dac  add     rsp, 38h
0x180001db0  pop     r14
0x180001db2  pop     rdi
0x180001db3  pop     rbp
0x180001db4  pop     rbx
0x180001db5  retn
```
