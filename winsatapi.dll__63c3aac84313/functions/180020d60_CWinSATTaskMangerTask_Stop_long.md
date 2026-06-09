# CWinSATTaskMangerTask::Stop(long *)

- ea: `0x180020d60`
- end: `0x180020dc4`
- name: `?Stop@CWinSATTaskMangerTask@@UEAAJPEAJ@Z`
- size: `100`
- prototype: `__int64 __fastcall(CWinSATTaskMangerTask *__hidden this, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000e6ac`
- `0x180020d60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020dab`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020dab`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020d8c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020d8c`

## string_xrefs

- `0x180020d7c`: `base\winsat\api-dll\winsattaskmangertask.cpp`

## pseudocode

```c
__int64 __fastcall CWinSATTaskMangerTask::Stop(CWinSATTaskMangerTask *this, int *a2)
{
  __int64 result; // rax
  void *v5; // rcx

  Log_Text_F((__int64)"base\\winsat\\api-dll\\winsattaskmangertask.cpp", 646, "Received STOP signal");
  if ( SetEvent(*((HANDLE *)this + 14)) )
  {
    v5 = (void *)*((_QWORD *)this + 11);
    if ( v5 )
      WaitForSingleObject(v5, 0xFFFFFFFF);
    *a2 = 0;
    return 0;
  }
  else
  {
    result = 2147500037LL;
    *a2 = -2147467259;
  }
  return result;
}

```

## disassembly

```asm
0x180020d60  mov     [rsp+arg_0], rbx
0x180020d65  push    rdi
0x180020d66  sub     rsp, 20h
0x180020d6a  mov     rbx, rdx
0x180020d6d  lea     r8, aReceivedStopSi; "Received STOP signal"
0x180020d74  mov     rdi, rcx
0x180020d77  mov     edx, 286h
0x180020d7c  lea     rcx, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180020d83  call    Log_Text_F
0x180020d88  mov     rcx, [rdi+70h]; hEvent
0x180020d8c  call    cs:__imp_SetEvent
0x180020d92  test    eax, eax
0x180020d94  jnz     short loc_180020D9F
0x180020d96  mov     eax, 80004005h
0x180020d9b  mov     [rbx], eax
0x180020d9d  jmp     short loc_180020DB9
0x180020d9f  mov     rcx, [rdi+58h]; hHandle
0x180020da3  test    rcx, rcx
0x180020da6  jz      short loc_180020DB1
0x180020da8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180020dab  call    cs:__imp_WaitForSingleObject
0x180020db1  mov     dword ptr [rbx], 0
0x180020db7  xor     eax, eax
0x180020db9  mov     rbx, [rsp+28h+arg_0]
0x180020dbe  add     rsp, 20h
0x180020dc2  pop     rdi
0x180020dc3  retn
```
