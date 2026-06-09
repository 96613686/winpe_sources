# PlugPlayServiceMain

- ea: `0x180015f80`
- end: `0x18001604a`
- name: `PlugPlayServiceMain`
- size: `202`
- prototype: `DWORD()`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x1800117d4`
- `0x180011964`
- `0x180015f80`
- `0x180016050`
- `0x1800160dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015fe9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015fe9`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180015fd7`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180015fd7`

## pseudocode

```c
DWORD PlugPlayServiceMain()
{
  void *v0; // rcx
  __int64 v1; // rcx
  DWORD result; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  DWORD v6; // ebx
  void *v7; // rcx
  __int64 v8; // rcx

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_240d98e9dfc731e5b4648e232cb969e2_Traceguids);
  PlugPlayServiceStatusUpdate(v0, 2);
  PlugPlayServiceStatusHandle = RegisterServiceCtrlHandlerExW(
                                  L"PlugPlay",
                                  (LPHANDLER_FUNCTION_EX)PlugPlayServiceControlHandlerEx,
                                  0);
  if ( PlugPlayServiceStatusHandle )
  {
    PlugPlayServiceStatusUpdate(v1, 2);
    return PlugPlayServiceStatusUpdate(v8, 4);
  }
  else
  {
    result = GetLastError();
    v6 = result;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      result = WPP_SF_d(
                 *((_QWORD *)WPP_GLOBAL_Control + 2),
                 12,
                 WPP_240d98e9dfc731e5b4648e232cb969e2_Traceguids,
                 result);
    if ( v6 )
      return PlugPlayServiceStop(v7, v3, v4, v5);
  }
  return result;
}

```

## disassembly

```asm
0x180015f80  mov     [rsp+arg_0], rbx
0x180015f85  push    rdi
0x180015f86  sub     rsp, 20h
0x180015f8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f91  lea     rdi, WPP_GLOBAL_Control
0x180015f98  cmp     rcx, rdi
0x180015f9b  jz      short loc_180015FB8
0x180015f9d  test    byte ptr [rcx+1Ch], 8
0x180015fa1  jz      short loc_180015FB8
0x180015fa3  mov     rcx, [rcx+10h]
0x180015fa7  lea     r8, WPP_240d98e9dfc731e5b4648e232cb969e2_Traceguids
0x180015fae  mov     edx, 0Bh
0x180015fb3  call    WPP_SF_
0x180015fb8  xor     r8d, r8d
0x180015fbb  lea     ebx, [r8+2]
0x180015fbf  mov     edx, ebx
0x180015fc1  call    PlugPlayServiceStatusUpdate
0x180015fc6  xor     r8d, r8d; lpContext
0x180015fc9  lea     rdx, PlugPlayServiceControlHandlerEx; lpHandlerProc
0x180015fd0  lea     rcx, aPlugplay; "PlugPlay"
0x180015fd7  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180015fdd  mov     cs:PlugPlayServiceStatusHandle, rax
0x180015fe4  test    rax, rax
0x180015fe7  jnz     short loc_180016026
0x180015fe9  call    cs:__imp_GetLastError
0x180015fef  mov     ebx, eax
0x180015ff1  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ff8  cmp     rcx, rdi
0x180015ffb  jz      short loc_18001601B
0x180015ffd  test    byte ptr [rcx+1Ch], 1
0x180016001  jz      short loc_18001601B
0x180016003  mov     rcx, [rcx+10h]
0x180016007  lea     r8, WPP_240d98e9dfc731e5b4648e232cb969e2_Traceguids
0x18001600e  mov     edx, 0Ch
0x180016013  mov     r9d, eax
0x180016016  call    WPP_SF_d
0x18001601b  test    ebx, ebx
0x18001601d  jz      short loc_18001603F
0x18001601f  call    PlugPlayServiceStop
0x180016024  jmp     short loc_18001603F
0x180016026  mov     r8d, 1
0x18001602c  mov     edx, ebx
0x18001602e  call    PlugPlayServiceStatusUpdate
0x180016033  xor     r8d, r8d
0x180016036  lea     edx, [r8+4]
0x18001603a  call    PlugPlayServiceStatusUpdate
0x18001603f  mov     rbx, [rsp+28h+arg_0]
0x180016044  add     rsp, 20h
0x180016048  pop     rdi
0x180016049  retn
```
