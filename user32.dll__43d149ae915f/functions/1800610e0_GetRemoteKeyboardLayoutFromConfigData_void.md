# GetRemoteKeyboardLayoutFromConfigData(void)

- ea: `0x1800610e0`
- end: `0x180061182`
- name: `?GetRemoteKeyboardLayoutFromConfigData@@YAKXZ`
- size: `162`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800565e0`

## callees

- `0x1800610e0`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `ntdll!RtlGetActiveConsoleId` at `0x18006117a`
- `ntdll!RtlGetActiveConsoleId` at `0x18006117a`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180061124`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180061124`
- `WINSTA!WinStationQueryInformationW` at `0x180061150`
- `WINSTA!WinStationQueryInformationW` at `0x180061150`

## pseudocode

```c
__int64 GetRemoteKeyboardLayoutFromConfigData(void)
{
  ULONG SessionId; // ebx
  char v1; // al
  _DWORD v3[4]; // [rsp+30h] [rbp-A98h] BYREF
  _BYTE v4[1392]; // [rsp+40h] [rbp-A88h] BYREF
  int v5; // [rsp+5B0h] [rbp-518h]

  memset_0(v4, 0, 0xA68u);
  v3[0] = 0;
  SessionId = NtCurrentPeb()->SessionId;
  if ( SessionId != (unsigned int)WTSGetServiceSessionId() )
    RtlGetActiveConsoleId();
  v1 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, _BYTE *, int, _DWORD *))WinStationQueryInformationW)(
         0,
         0xFFFFFFFFLL,
         1,
         v4,
         2664,
         v3);
  return v5 & (unsigned int)-(v1 != 0);
}

```

## disassembly

```asm
0x1800610e0  push    rbx
0x1800610e2  sub     rsp, 0AC0h
0x1800610e9  mov     rax, cs:__security_cookie
0x1800610f0  xor     rax, rsp
0x1800610f3  mov     [rsp+0AC8h+var_18], rax
0x1800610fb  xor     edx, edx; Val
0x1800610fd  lea     rcx, [rsp+0AC8h+var_A88]; void *
0x180061102  mov     r8d, 0A68h; Size
0x180061108  call    memset_0
0x18006110d  mov     [rsp+0AC8h+var_A98], 0
0x180061115  mov     rax, gs:60h
0x18006111e  mov     ebx, [rax+2C0h]
0x180061124  call    cs:__imp_WTSGetServiceSessionId
0x18006112a  cmp     ebx, eax
0x18006112c  jnz     short loc_18006117A
0x18006112e  lea     rax, [rsp+0AC8h+var_A98]
0x180061133  mov     r8d, 1
0x180061139  mov     [rsp+0AC8h+var_AA0], rax
0x18006113e  lea     r9, [rsp+0AC8h+var_A88]
0x180061143  or      edx, 0FFFFFFFFh
0x180061146  mov     [rsp+0AC8h+var_AA8], 0A68h
0x18006114e  xor     ecx, ecx
0x180061150  call    cs:__imp_WinStationQueryInformationW
0x180061156  neg     al
0x180061158  sbb     eax, eax
0x18006115a  and     eax, [rsp+0AC8h+var_518]
0x180061161  mov     rcx, [rsp+0AC8h+var_18]
0x180061169  xor     rcx, rsp; StackCookie
0x18006116c  call    __security_check_cookie
0x180061171  add     rsp, 0AC0h
0x180061178  pop     rbx
0x180061179  retn
0x18006117a  call    cs:__imp_RtlGetActiveConsoleId
0x180061180  jmp     short loc_18006112E
```
