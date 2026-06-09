# UmpoTraceSmartPresenceTimeUpdate

- ea: `0x18000f948`
- end: `0x18000f9a2`
- name: `UmpoTraceSmartPresenceTimeUpdate`
- size: `90`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c8d0`

## callees

- `0x180010070`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000f98a`
- `ntdll!EtwEventWrite` at `0x18000f98a`

## pseudocode

```c
__int64 __fastcall UmpoTraceSmartPresenceTimeUpdate(__int64 a1)
{
  _QWORD v2[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v3; // [rsp+50h] [rbp+8h] BYREF

  v3 = a1;
  v2[0] = &v3;
  v2[1] = 8;
  return EtwEventWrite(UmpoProviderHandle, UMPO_EVT_SMART_USER_PRESENCE_TIME_UPDATE, 1, v2);
}

```

## disassembly

```asm
0x18000f948  mov     r11, rsp
0x18000f94b  mov     [r11+8], rcx
0x18000f94f  sub     rsp, 48h
0x18000f953  mov     rax, cs:__security_cookie
0x18000f95a  xor     rax, rsp
0x18000f95d  mov     [rsp+48h+var_18], rax
0x18000f962  mov     rcx, cs:UmpoProviderHandle
0x18000f969  lea     rax, [r11+8]
0x18000f96d  lea     r9, [r11-28h]
0x18000f971  mov     [r11-28h], rax
0x18000f975  mov     r8d, 1
0x18000f97b  mov     qword ptr [r11-20h], 8
0x18000f983  lea     rdx, UMPO_EVT_SMART_USER_PRESENCE_TIME_UPDATE
0x18000f98a  call    cs:__imp_EtwEventWrite
0x18000f990  mov     rcx, [rsp+48h+var_18]
0x18000f995  xor     rcx, rsp; StackCookie
0x18000f998  call    __security_check_cookie
0x18000f99d  add     rsp, 48h
0x18000f9a1  retn
```
