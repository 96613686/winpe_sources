# NdrpGetDisableClientHardeningAndLog(void)

- ea: `0x1800a3aa4`
- end: `0x1800a3b4b`
- name: `?NdrpGetDisableClientHardeningAndLog@@YAHXZ`
- size: `167`
- prototype: `__int64(void)`
- caller_count: `8`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180004874`
- `0x180005360`
- `0x18003aac0`
- `0x18003b7f0`
- `0x18003c3d0`
- `0x18006eaf0`
- `0x18006ee10`
- `0x1800be650`

## callees

- `0x1800a3aa4`
- `0x1800c005c`
- `0x1800ca140`

## import_xrefs

- `ntdll!RtlIntegerToUnicodeString` at `0x1800a3ae2`
- `ntdll!RtlIntegerToUnicodeString` at `0x1800a3ae2`
- `ntdll!WinSqmIncrementDWORD` at `0x1800a3b1f`
- `ntdll!WinSqmIncrementDWORD` at `0x1800a3b1f`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800a3af1`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800a3af1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a3ad3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a3ad3`

## pseudocode

```c
__int64 __fastcall NdrpGetDisableClientHardeningAndLog(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  ULONG CurrentProcessId; // eax
  LPWSTR CommandLineW; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  struct _UNICODE_STRING String; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v10[24]; // [rsp+30h] [rbp-28h] BYREF

  if ( !byte_1800FA464 )
  {
    *(_QWORD *)&String.Length = 1441792;
    String.Buffer = (PWSTR)v10;
    CurrentProcessId = GetCurrentProcessId();
    RtlIntegerToUnicodeString(CurrentProcessId, 0, &String);
    if ( (Microsoft_Windows_RPC_EventsEnableBits & 2) != 0 )
    {
      CommandLineW = GetCommandLineW();
      McTemplateU0zz_EtwEventWriteTransfer(v7, v6, CommandLineW, v10, *(_QWORD *)&String.Length, String.Buffer);
    }
    byte_1800FA464 = 1;
  }
  if ( g_SqmEnabled )
    WinSqmIncrementDWORD(0, 1559, 1, a4);
  return NtCurrentPeb()->AppCompatFlags.LowPart & 0x800;
}

```

## disassembly

```asm
0x1800a3aa4  sub     rsp, 58h
0x1800a3aa8  mov     rax, cs:__security_cookie
0x1800a3aaf  xor     rax, rsp
0x1800a3ab2  mov     [rsp+58h+var_10], rax
0x1800a3ab7  cmp     cs:byte_1800FA464, 0
0x1800a3abe  jnz     short loc_1800A3B0B
0x1800a3ac0  lea     rax, [rsp+58h+var_28]
0x1800a3ac5  mov     qword ptr [rsp+58h+String.Length], 160000h
0x1800a3ace  mov     [rsp+58h+String.Buffer], rax
0x1800a3ad3  call    cs:__imp_GetCurrentProcessId
0x1800a3ad9  lea     r8, [rsp+58h+String]; String
0x1800a3ade  xor     edx, edx; Base
0x1800a3ae0  mov     ecx, eax; Value
0x1800a3ae2  call    cs:__imp_RtlIntegerToUnicodeString
0x1800a3ae8  test    cs:Microsoft_Windows_RPC_EventsEnableBits, 2
0x1800a3aef  jz      short loc_1800A3B04
0x1800a3af1  call    cs:__imp_GetCommandLineW
0x1800a3af7  mov     r8, rax
0x1800a3afa  lea     r9, [rsp+58h+var_28]
0x1800a3aff  call    McTemplateU0zz_EtwEventWriteTransfer
0x1800a3b04  mov     cs:byte_1800FA464, 1
0x1800a3b0b  cmp     cs:?g_SqmEnabled@@3HA, 0; int g_SqmEnabled
0x1800a3b12  jz      short loc_1800A3B25
0x1800a3b14  xor     ecx, ecx
0x1800a3b16  mov     edx, 617h
0x1800a3b1b  lea     r8d, [rcx+1]
0x1800a3b1f  call    cs:__imp_WinSqmIncrementDWORD
0x1800a3b25  mov     rax, gs:60h
0x1800a3b2e  mov     eax, [rax+2C8h]
0x1800a3b34  and     eax, 800h
0x1800a3b39  mov     rcx, [rsp+58h+var_10]
0x1800a3b3e  xor     rcx, rsp; StackCookie
0x1800a3b41  call    __security_check_cookie
0x1800a3b46  add     rsp, 58h
0x1800a3b4a  retn
```
