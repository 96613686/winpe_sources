# TrkUnregisterWait(void *,void *)

- ea: `0x18000ed38`
- end: `0x18000ed69`
- name: `?TrkUnregisterWait@@YAHPEAX0@Z`
- size: `49`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001588`
- `0x1800019c8`
- `0x180001b64`
- `0x18000a4b8`
- `0x18000c4f8`
- `0x18000ed70`

## callees

- `0x18000ed38`

## import_xrefs

- `ntdll!RtlDeregisterWaitEx` at `0x18000ed3e`
- `ntdll!RtlDeregisterWaitEx` at `0x18000ed3e`
- `ntdll!RtlNtStatusToDosError` at `0x18000ed53`
- `ntdll!RtlNtStatusToDosError` at `0x18000ed53`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ed5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ed5b`

## pseudocode

```c
__int64 __fastcall TrkUnregisterWait(void *a1, void *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  DWORD v4; // eax

  v2 = RtlDeregisterWaitEx(a1, a2);
  if ( v2 < 0 )
  {
    v3 = 0;
    v4 = RtlNtStatusToDosError(v2);
    SetLastError(v4);
  }
  else
  {
    return 1;
  }
  return v3;
}

```

## disassembly

```asm
0x18000ed38  push    rbx
0x18000ed3a  sub     rsp, 20h
0x18000ed3e  call    cs:__imp_RtlDeregisterWaitEx
0x18000ed44  test    eax, eax
0x18000ed46  js      short loc_18000ED4F
0x18000ed48  mov     ebx, 1
0x18000ed4d  jmp     short loc_18000ED61
0x18000ed4f  mov     ecx, eax; Status
0x18000ed51  xor     ebx, ebx
0x18000ed53  call    cs:__imp_RtlNtStatusToDosError
0x18000ed59  mov     ecx, eax; dwErrCode
0x18000ed5b  call    cs:__imp_SetLastError
0x18000ed61  mov     eax, ebx
0x18000ed63  add     rsp, 20h
0x18000ed67  pop     rbx
0x18000ed68  retn
```
