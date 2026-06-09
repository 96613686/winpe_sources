# WdipSendASyncMessage

- ea: `0x180004100`
- end: `0x180004193`
- name: `WdipSendASyncMessage`
- size: `147`
- prototype: `__int64 __fastcall(_WORD *, __int64, __int64, __int64, __int16)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003420`
- `0x180008c84`
- `0x18000a160`
- `0x18000a420`
- `0x18000ab6c`

## callees

- `0x180002ba0`
- `0x180004100`

## import_xrefs

- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000413f`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000413f`
- `ntdll!RtlNtStatusToDosError` at `0x18000414b`
- `ntdll!RtlNtStatusToDosError` at `0x18000414b`

## string_xrefs

- `0x180004179`: `clientcore\base\diagnosis\pdi\wdi\framework\library\communicationcli.cpp`

## pseudocode

```c
__int64 __fastcall WdipSendASyncMessage(_WORD *a1, __int64 a2, __int64 a3, __int64 a4, __int16 a5)
{
  signed int Args; // ebx
  NTSTATUS v6; // eax
  signed int v7; // eax

  Args = 0;
  a1[1] = a5;
  *a1 = a5 - 40;
  v6 = NtAlpcSendWaitReceivePort(a4, 0x10000, a1, a2, 0, 0, 0, 0);
  if ( v6 < 0 )
  {
    v7 = RtlNtStatusToDosError(v6);
    Args = v7;
    if ( v7 > 0 )
      Args = (unsigned __int16)v7 | 0x80070000;
  }
  if ( Args < 0 )
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\communicationcli.cpp",
      (int)L"WdipSendASyncMessage",
      264,
      (int)L"Error = %d",
      Args);
  return (unsigned int)Args;
}

```

## disassembly

```asm
0x180004100  push    rbx
0x180004102  sub     rsp, 40h
0x180004106  movzx   r8d, [rsp+48h+arg_20]
0x18000410c  xor     ebx, ebx
0x18000410e  mov     r10, r9
0x180004111  mov     [rcx+2], r8w
0x180004116  mov     [rsp+48h+var_10], rbx
0x18000411b  mov     r9, rdx
0x18000411e  mov     [rsp+48h+var_18], rbx
0x180004123  mov     edx, 10000h
0x180004128  lea     eax, [r8-28h]
0x18000412c  mov     [rsp+48h+var_20], rbx
0x180004131  mov     [rcx], ax
0x180004134  mov     r8, rcx
0x180004137  mov     rcx, r10
0x18000413a  mov     qword ptr [rsp+48h+Args], rbx
0x18000413f  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180004145  test    eax, eax
0x180004147  jns     short loc_180004160
0x180004149  mov     ecx, eax; Status
0x18000414b  call    cs:__imp_RtlNtStatusToDosError
0x180004151  mov     ebx, eax
0x180004153  test    eax, eax
0x180004155  jle     short loc_180004160
0x180004157  movzx   ebx, ax
0x18000415a  or      ebx, 80070000h
0x180004160  test    ebx, ebx
0x180004162  jns     short loc_18000418B
0x180004164  movzx   ecx, bx
0x180004167  lea     r9, aErrorD_0; "Error = %d"
0x18000416e  mov     dword ptr [rsp+48h+Args], ecx; Args
0x180004172  lea     rdx, aWdipsendasyncm; "WdipSendASyncMessage"
0x180004179  lea     rcx, aClientcoreBase; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180004180  mov     r8d, 108h; int
0x180004186  call    WdipTraceError
0x18000418b  mov     eax, ebx
0x18000418d  add     rsp, 40h
0x180004191  pop     rbx
0x180004192  retn
```
