# WdipSendSyncMessage

- ea: `0x1800041a0`
- end: `0x1800042b7`
- name: `WdipSendSyncMessage`
- size: `279`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int16)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005fa0`
- `0x18000a280`
- `0x18000a744`
- `0x18000a9b0`
- `0x18000ae18`

## callees

- `0x180002ba0`
- `0x1800041a0`

## import_xrefs

- `ntdll!NtAlpcSendWaitReceivePort` at `0x180004251`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180004251`
- `ntdll!RtlNtStatusToDosError` at `0x180004262`
- `ntdll!RtlNtStatusToDosError` at `0x180004262`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x18000421f`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x18000421f`

## string_xrefs

- `0x1800041e7`: `clientcore\base\diagnosis\pdi\wdi\framework\library\communicationcli.cpp`
- `0x180004290`: `clientcore\base\diagnosis\pdi\wdi\framework\library\communicationcli.cpp`

## pseudocode

```c
__int64 __fastcall WdipSendSyncMessage(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int16 a5)
{
  __int16 v10; // cx
  NTSTATUS v11; // eax
  signed int Args; // ebx
  signed int v13; // eax
  __int64 v14; // [rsp+60h] [rbp+8h] BYREF

  v14 = 0;
  if ( a1 )
  {
    *(_DWORD *)(a1 + 24) = 0;
    *(_DWORD *)(a1 + 4) = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
    v10 = a5;
    *(_WORD *)(a1 + 2) = a5;
    *(_WORD *)a1 = v10 - 40;
    v14 = AlpcMaxAllowedMessageLength();
    v11 = NtAlpcSendWaitReceivePort(a4, 0x20000, a1, a3, a2, &v14, 0, 0);
    if ( v11 < 0 )
    {
      v13 = RtlNtStatusToDosError(v11);
      Args = v13;
      if ( v13 > 0 )
        Args = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
      Args = 0;
    }
    if ( Args < 0 )
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\communicationcli.cpp",
        (int)L"WdipSendSyncMessage",
        214,
        (int)L"Error = %d",
        Args);
    return (unsigned int)Args;
  }
  else
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\communicationcli.cpp",
      (int)L"WdipSendSyncMessage",
      190,
      (int)L"Error = %d",
      87);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800041a0  mov     [rsp+arg_8], rbx
0x1800041a5  mov     [rsp+arg_10], rbp
0x1800041aa  push    rsi
0x1800041ab  push    rdi
0x1800041ac  push    r14
0x1800041ae  sub     rsp, 40h
0x1800041b2  xor     r14d, r14d
0x1800041b5  mov     rdi, r9
0x1800041b8  mov     [rsp+58h+arg_0], r14
0x1800041bd  mov     rsi, r8
0x1800041c0  mov     rbp, rdx
0x1800041c3  mov     rbx, rcx
0x1800041c6  test    rcx, rcx
0x1800041c9  jnz     short loc_1800041FD
0x1800041cb  lea     r9, aErrorD_0; "Error = %d"
0x1800041d2  mov     dword ptr [rsp+58h+Args], 57h ; 'W'; Args
0x1800041da  mov     r8d, 0BEh; int
0x1800041e0  lea     rdx, aWdipsendsyncme; "WdipSendSyncMessage"
0x1800041e7  lea     rcx, aClientcoreBase; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800041ee  call    WdipTraceError
0x1800041f3  mov     eax, 80070057h
0x1800041f8  jmp     loc_1800042A4
0x1800041fd  mov     [rcx+18h], r14d
0x180004201  mov     [rcx+4], r14d
0x180004205  mov     [rcx+8], r14
0x180004209  mov     [rcx+10h], r14
0x18000420d  movzx   ecx, [rsp+58h+arg_20]
0x180004215  mov     [rbx+2], cx
0x180004219  lea     eax, [rcx-28h]
0x18000421c  mov     [rbx], ax
0x18000421f  call    cs:__imp_AlpcMaxAllowedMessageLength
0x180004225  mov     [rsp+58h+var_20], r14
0x18000422a  mov     r9, rsi
0x18000422d  mov     [rsp+58h+arg_0], rax
0x180004232  mov     r8, rbx
0x180004235  lea     rax, [rsp+58h+arg_0]
0x18000423a  mov     [rsp+58h+var_28], r14
0x18000423f  mov     [rsp+58h+var_30], rax
0x180004244  mov     edx, 20000h
0x180004249  mov     rcx, rdi
0x18000424c  mov     qword ptr [rsp+58h+Args], rbp
0x180004251  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180004257  test    eax, eax
0x180004259  js      short loc_180004260
0x18000425b  mov     ebx, r14d
0x18000425e  jmp     short loc_180004277
0x180004260  mov     ecx, eax; Status
0x180004262  call    cs:__imp_RtlNtStatusToDosError
0x180004268  mov     ebx, eax
0x18000426a  test    eax, eax
0x18000426c  jle     short loc_180004277
0x18000426e  movzx   ebx, ax
0x180004271  or      ebx, 80070000h
0x180004277  test    ebx, ebx
0x180004279  jns     short loc_1800042A2
0x18000427b  movzx   ecx, bx
0x18000427e  lea     r9, aErrorD_0; "Error = %d"
0x180004285  mov     dword ptr [rsp+58h+Args], ecx; Args
0x180004289  lea     rdx, aWdipsendsyncme; "WdipSendSyncMessage"
0x180004290  lea     rcx, aClientcoreBase; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180004297  mov     r8d, 0D6h; int
0x18000429d  call    WdipTraceError
0x1800042a2  mov     eax, ebx
0x1800042a4  mov     rbx, [rsp+58h+arg_8]
0x1800042a9  mov     rbp, [rsp+58h+arg_10]
0x1800042ae  add     rsp, 40h
0x1800042b2  pop     r14
0x1800042b4  pop     rdi
0x1800042b5  pop     rsi
0x1800042b6  retn
```
