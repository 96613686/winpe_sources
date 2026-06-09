# BaseSetLastNTError

- ea: `0x14001cabc`
- end: `0x14001cada`
- name: `BaseSetLastNTError`
- size: `30`
- prototype: ``
- caller_count: `12`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140019154`
- `0x140019244`
- `0x14001997c`
- `0x14001a090`
- `0x14001a1a0`
- `0x14001a254`
- `0x14001a3fc`
- `0x14001ac48`
- `0x14001b67c`
- `0x14001ba7c`
- `0x14001bb50`
- `0x14001c0a0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x14001cac2`
- `ntdll!RtlNtStatusToDosError` at `0x14001cac2`
- `ntdll!RtlSetLastWin32Error` at `0x14001cacc`
- `ntdll!RtlSetLastWin32Error` at `0x14001cacc`

## pseudocode

```c
__int64 __fastcall BaseSetLastNTError(NTSTATUS a1)
{
  ULONG v1; // ebx

  v1 = RtlNtStatusToDosError(a1);
  RtlSetLastWin32Error(v1);
  return v1;
}

```

## disassembly

```asm
0x14001cabc  push    rbx
0x14001cabe  sub     rsp, 20h
0x14001cac2  call    cs:__imp_RtlNtStatusToDosError
0x14001cac8  mov     ecx, eax; LastError
0x14001caca  mov     ebx, eax
0x14001cacc  call    cs:__imp_RtlSetLastWin32Error
0x14001cad2  mov     eax, ebx
0x14001cad4  add     rsp, 20h
0x14001cad8  pop     rbx
0x14001cad9  retn
```
