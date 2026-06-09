# NdrpLogMCCPEvent(void)

- ea: `0x1800a7ba8`
- end: `0x1800a7c34`
- name: `?NdrpLogMCCPEvent@@YAXXZ`
- size: `140`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800a7b5c`

## callees

- `0x1800a7ba8`
- `0x1800c4874`
- `0x1800ceda0`

## import_xrefs

- `ntdll!RtlIntegerToUnicodeString` at `0x1800a7bec`
- `ntdll!RtlIntegerToUnicodeString` at `0x1800a7bec`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800a7c01`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800a7c01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a7bd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a7bd7`

## pseudocode

```c
void NdrpLogMCCPEvent(void)
{
  ULONG CurrentProcessId; // eax
  LPWSTR CommandLineW; // rax
  __int64 v2; // rdx
  __int64 v3; // rcx
  struct _UNICODE_STRING String; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v5[24]; // [rsp+30h] [rbp-28h] BYREF

  if ( !byte_1800FF464 )
  {
    *(_QWORD *)&String.Length = 1441792;
    String.Buffer = (PWSTR)v5;
    CurrentProcessId = GetCurrentProcessId();
    RtlIntegerToUnicodeString(CurrentProcessId, 0, &String);
    if ( (Microsoft_Windows_RPC_EventsEnableBits & 2) != 0 )
    {
      CommandLineW = GetCommandLineW();
      McTemplateU0zz_EtwEventWriteTransfer(v3, v2, CommandLineW, v5, *(_QWORD *)&String.Length, String.Buffer);
    }
    byte_1800FF464 = 1;
  }
}

```

## disassembly

```asm
0x1800a7ba8  sub     rsp, 58h
0x1800a7bac  mov     rax, cs:__security_cookie
0x1800a7bb3  xor     rax, rsp
0x1800a7bb6  mov     [rsp+58h+var_10], rax
0x1800a7bbb  cmp     cs:byte_1800FF464, 0
0x1800a7bc2  jnz     short loc_1800A7C21
0x1800a7bc4  lea     rax, [rsp+58h+var_28]
0x1800a7bc9  mov     qword ptr [rsp+58h+String.Length], 160000h
0x1800a7bd2  mov     [rsp+58h+String.Buffer], rax
0x1800a7bd7  call    cs:__imp_GetCurrentProcessId
0x1800a7bde  nop     dword ptr [rax+rax+00h]
0x1800a7be3  lea     r8, [rsp+58h+String]; String
0x1800a7be8  xor     edx, edx; Base
0x1800a7bea  mov     ecx, eax; Value
0x1800a7bec  call    cs:__imp_RtlIntegerToUnicodeString
0x1800a7bf3  nop     dword ptr [rax+rax+00h]
0x1800a7bf8  test    cs:Microsoft_Windows_RPC_EventsEnableBits, 2
0x1800a7bff  jz      short loc_1800A7C1A
0x1800a7c01  call    cs:__imp_GetCommandLineW
0x1800a7c08  nop     dword ptr [rax+rax+00h]
0x1800a7c0d  mov     r8, rax
0x1800a7c10  lea     r9, [rsp+58h+var_28]
0x1800a7c15  call    McTemplateU0zz_EtwEventWriteTransfer
0x1800a7c1a  mov     cs:byte_1800FF464, 1
0x1800a7c21  mov     rcx, [rsp+58h+var_10]
0x1800a7c26  xor     rcx, rsp; StackCookie
0x1800a7c29  call    __security_check_cookie
0x1800a7c2e  add     rsp, 58h
0x1800a7c32  retn
```
