# TrkRegisterWaitForSingleObjectEx(void *,void (*)(void *,uchar),void *,ulong,ulong)

- ea: `0x18000a038`
- end: `0x18000a094`
- name: `?TrkRegisterWaitForSingleObjectEx@@YAPEAXPEAXP6AX0E@Z0KK@Z`
- size: `92`
- prototype: `void *__fastcall(HANDLE hObject, void (*)(void *, unsigned __int8), void *, __int64, ULONG ulFlags)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009698`
- `0x180009800`
- `0x18000a27c`
- `0x18000a4b8`
- `0x18000a880`

## callees

- `0x18000a038`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000a078`
- `ntdll!RtlNtStatusToDosError` at `0x18000a078`
- `ntdll!RtlRegisterWait` at `0x18000a06c`
- `ntdll!RtlRegisterWait` at `0x18000a06c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a080`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a080`

## pseudocode

```c
void *__fastcall TrkRegisterWaitForSingleObjectEx(
        HANDLE hObject,
        void (*a2)(void *, unsigned __int8),
        void *a3,
        __int64 a4,
        ULONG ulFlags)
{
  int v5; // eax
  DWORD v6; // eax
  void *phNewWaitObject; // [rsp+48h] [rbp+10h] BYREF

  phNewWaitObject = 0;
  v5 = RtlRegisterWait(
         &phNewWaitObject,
         hObject,
         (WAITORTIMERCALLBACKFUNC)ThreadPoolCallbackFunction,
         a3,
         0xFFFFFFFF,
         ulFlags);
  if ( v5 >= 0 )
    return phNewWaitObject;
  v6 = RtlNtStatusToDosError(v5);
  SetLastError(v6);
  return 0;
}

```

## disassembly

```asm
0x18000a038  mov     [rsp+phNewWaitObject], rdx
0x18000a03d  sub     rsp, 38h
0x18000a041  mov     eax, [rsp+38h+arg_20]
0x18000a045  mov     r9, r8; pvContext
0x18000a048  mov     rdx, rcx; hObject
0x18000a04b  mov     [rsp+38h+ulFlags], eax; ulFlags
0x18000a04f  lea     r8, ?ThreadPoolCallbackFunction@@YAXPEAXE@Z; Callback
0x18000a056  mov     [rsp+38h+ulMilliseconds], 0FFFFFFFFh; ulMilliseconds
0x18000a05e  lea     rcx, [rsp+38h+phNewWaitObject]; phNewWaitObject
0x18000a063  mov     [rsp+38h+phNewWaitObject], 0
0x18000a06c  call    cs:__imp_RtlRegisterWait
0x18000a072  test    eax, eax
0x18000a074  jns     short loc_18000A08A
0x18000a076  mov     ecx, eax; Status
0x18000a078  call    cs:__imp_RtlNtStatusToDosError
0x18000a07e  mov     ecx, eax; dwErrCode
0x18000a080  call    cs:__imp_SetLastError
0x18000a086  xor     eax, eax
0x18000a088  jmp     short loc_18000A08F
0x18000a08a  mov     rax, [rsp+38h+phNewWaitObject]
0x18000a08f  add     rsp, 38h
0x18000a093  retn
```
