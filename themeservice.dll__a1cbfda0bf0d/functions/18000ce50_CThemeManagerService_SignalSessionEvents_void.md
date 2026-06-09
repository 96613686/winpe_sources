# CThemeManagerService::SignalSessionEvents(void *)

- ea: `0x18000ce50`
- end: `0x18000cf15`
- name: `?SignalSessionEvents@CThemeManagerService@@SAKPEAX@Z`
- size: `197`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000cf20`

## callees

- `0x180001de4`
- `0x180007f50`
- `0x18000ce50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ced4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ced4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cedd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cedd`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeMemory` at `0x18000cef7`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeMemory` at `0x18000cef7`
- `ext-ms-win-session-winsta-l1-1-0!WinStationEnumerateW` at `0x18000ce9b`
- `ext-ms-win-session-winsta-l1-1-0!WinStationEnumerateW` at `0x18000ce9b`
- `ext-ms-win-session-winsta-l1-1-0!WinStationOpenServerW` at `0x18000ce6b`
- `ext-ms-win-session-winsta-l1-1-0!WinStationOpenServerW` at `0x18000ce6b`
- `WINSTA!WinStationCloseServer` at `0x18000cf00`
- `WINSTA!WinStationCloseServer` at `0x18000cf00`

## pseudocode

```c
__int64 __fastcall CThemeManagerService::SignalSessionEvents(PVOID Parameter)
{
  __int64 v1; // rax
  __int64 v2; // rsi
  unsigned int *v3; // rbx
  unsigned int v4; // edi
  void *started; // rax
  void *v6; // rbp
  unsigned int v8; // [rsp+48h] [rbp+10h] BYREF
  unsigned int *v9; // [rsp+50h] [rbp+18h] BYREF

  if ( (unsigned __int8)IsWinStationOpenServerWPresent(Parameter) )
  {
    v1 = WinStationOpenServerW(0);
    v2 = v1;
    if ( v1 )
    {
      v8 = 0;
      v9 = 0;
      if ( (unsigned __int8)WinStationEnumerateW(v1, &v9, &v8) )
      {
        v3 = v9;
        v4 = 0;
        if ( v8 )
        {
          do
          {
            if ( *v3 && (v3[18] <= 2 || v3[18] == 4) )
            {
              started = CThemeManagerService::OpenStartEvent(*v3);
              v6 = started;
              if ( started )
              {
                SetEvent(started);
                CloseHandle(v6);
              }
            }
            ++v4;
            v3 += 19;
          }
          while ( v4 < v8 );
          v3 = v9;
        }
        WinStationFreeMemory(v3);
      }
      WinStationCloseServer(v2);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000ce50  mov     [rsp+arg_0], rbx
0x18000ce55  push    rbp
0x18000ce56  push    rsi
0x18000ce57  push    rdi
0x18000ce58  sub     rsp, 20h
0x18000ce5c  call    IsWinStationOpenServerWPresent
0x18000ce61  test    al, al
0x18000ce63  jz      loc_18000CF06
0x18000ce69  xor     ecx, ecx
0x18000ce6b  call    cs:__imp_WinStationOpenServerW
0x18000ce71  mov     rsi, rax
0x18000ce74  test    rax, rax
0x18000ce77  jz      loc_18000CF06
0x18000ce7d  lea     r8, [rsp+38h+arg_8]
0x18000ce82  mov     [rsp+38h+arg_8], 0
0x18000ce8a  lea     rdx, [rsp+38h+arg_10]
0x18000ce8f  mov     [rsp+38h+arg_10], 0
0x18000ce98  mov     rcx, rax
0x18000ce9b  call    cs:__imp_WinStationEnumerateW
0x18000cea1  test    al, al
0x18000cea3  jz      short loc_18000CEFD
0x18000cea5  mov     rbx, [rsp+38h+arg_10]
0x18000ceaa  xor     edi, edi
0x18000ceac  cmp     [rsp+38h+arg_8], edi
0x18000ceb0  jbe     short loc_18000CEF4
0x18000ceb2  mov     ecx, [rbx]; unsigned int
0x18000ceb4  test    ecx, ecx
0x18000ceb6  jz      short loc_18000CEE3
0x18000ceb8  cmp     dword ptr [rbx+48h], 2
0x18000cebc  jbe     short loc_18000CEC4
0x18000cebe  cmp     dword ptr [rbx+48h], 4
0x18000cec2  jnz     short loc_18000CEE3
0x18000cec4  call    ?OpenStartEvent@CThemeManagerService@@SAPEAXKK@Z; CThemeManagerService::OpenStartEvent(ulong,ulong)
0x18000cec9  mov     rbp, rax
0x18000cecc  test    rax, rax
0x18000cecf  jz      short loc_18000CEE3
0x18000ced1  mov     rcx, rax; hEvent
0x18000ced4  call    cs:__imp_SetEvent
0x18000ceda  mov     rcx, rbp; hObject
0x18000cedd  call    cs:__imp_CloseHandle
0x18000cee3  inc     edi
0x18000cee5  add     rbx, 4Ch ; 'L'
0x18000cee9  cmp     edi, [rsp+38h+arg_8]
0x18000ceed  jb      short loc_18000CEB2
0x18000ceef  mov     rbx, [rsp+38h+arg_10]
0x18000cef4  mov     rcx, rbx
0x18000cef7  call    cs:__imp_WinStationFreeMemory
0x18000cefd  mov     rcx, rsi
0x18000cf00  call    cs:__imp_WinStationCloseServer
0x18000cf06  mov     rbx, [rsp+38h+arg_0]
0x18000cf0b  xor     eax, eax
0x18000cf0d  add     rsp, 20h
0x18000cf11  pop     rdi
0x18000cf12  pop     rsi
0x18000cf13  pop     rbp
0x18000cf14  retn
```
