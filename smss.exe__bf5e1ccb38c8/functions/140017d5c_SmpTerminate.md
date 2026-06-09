# SmpTerminate

- ea: `0x140017d5c`
- end: `0x140017e1f`
- name: `SmpTerminate`
- size: `195`
- prototype: `void __fastcall __noreturn(PULONG_PTR Parameters, ULONG UnicodeStringParameterMask, ULONG NumberOfParameters)`
- caller_count: `10`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140001e40`
- `0x140002bb0`
- `0x1400031b0`
- `0x140005ac4`
- `0x140005f64`
- `0x140008470`
- `0x140014f30`
- `0x140016018`
- `0x140017c70`
- `0x140017e28`

## callees

- `0x140017d5c`

## import_xrefs

- `ntdll!NtPowerInformation` at `0x140017db0`
- `ntdll!NtPowerInformation` at `0x140017db0`
- `ntdll!RtlAdjustPrivilege` at `0x140017dc9`
- `ntdll!RtlAdjustPrivilege` at `0x140017de7`
- `ntdll!RtlAdjustPrivilege` at `0x140017dc9`
- `ntdll!RtlAdjustPrivilege` at `0x140017de7`
- `ntdll!NtTerminateProcess` at `0x140017e18`
- `ntdll!NtTerminateProcess` at `0x140017e18`
- `ntdll!NtRaiseHardError` at `0x140017e0c`
- `ntdll!NtRaiseHardError` at `0x140017e0c`

## pseudocode

```c
void __fastcall __noreturn SmpTerminate(
        PULONG_PTR Parameters,
        ULONG UnicodeStringParameterMask,
        ULONG NumberOfParameters)
{
  NTSTATUS v6; // eax
  ULONG Response; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v8[6]; // [rsp+38h] [rbp-30h] BYREF
  unsigned __int8 OldValue; // [rsp+88h] [rbp+20h] BYREF

  v8[3] = 23;
  v8[1] = 3592;
  Response = 0;
  OldValue = 0;
  v8[2] = 0;
  v8[0] = SmpBlackboxBuffer;
  NtPowerInformation(TraceApplicationPowerMessage|0x40, v8, 0x20u, 0, 0);
  if ( RtlAdjustPrivilege(0x13u, 1u, 1u, &OldValue) == -1073741700 )
    RtlAdjustPrivilege(0x13u, 1u, 0, &OldValue);
  v6 = NtRaiseHardError(-1073741286, NumberOfParameters, UnicodeStringParameterMask, Parameters, 6u, &Response);
  NtTerminateProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, v6);
  JUMPOUT(0x140017E1ELL);
}

```

## disassembly

```asm
0x140017d5c  mov     r11, rsp
0x140017d5f  mov     [r11+8], rbx
0x140017d63  mov     [r11+10h], rsi
0x140017d67  push    rdi
0x140017d68  sub     rsp, 60h
0x140017d6c  mov     rsi, rcx
0x140017d6f  mov     qword ptr [r11-18h], 17h
0x140017d77  xor     ecx, ecx
0x140017d79  mov     qword ptr [r11-28h], 0E08h
0x140017d81  xor     r9d, r9d; OutputBuffer
0x140017d84  mov     [rsp+68h+var_38], ecx
0x140017d88  mov     ebx, r8d
0x140017d8b  mov     [r11+20h], cl
0x140017d8f  mov     edi, edx
0x140017d91  mov     [r11-20h], rcx
0x140017d95  lea     r8d, [rcx+20h]; InputBufferLength
0x140017d99  mov     [rsp+68h+OutputBufferLength], ecx; OutputBufferLength
0x140017d9d  lea     rax, SmpBlackboxBuffer
0x140017da4  lea     ecx, [r9+5Eh]; InformationLevel
0x140017da8  mov     [r11-30h], rax
0x140017dac  lea     rdx, [r11-30h]; InputBuffer
0x140017db0  call    cs:__imp_NtPowerInformation
0x140017db6  mov     r8b, 1; ForThread
0x140017db9  lea     r9, [rsp+68h+OldValue]; OldValue
0x140017dc1  mov     dl, r8b; NewValue
0x140017dc4  mov     ecx, 13h; Privilege
0x140017dc9  call    cs:__imp_RtlAdjustPrivilege
0x140017dcf  cmp     eax, 0C000007Ch
0x140017dd4  jnz     short loc_140017DED
0x140017dd6  xor     r8d, r8d; ForThread
0x140017dd9  lea     r9, [rsp+68h+OldValue]; OldValue
0x140017de1  mov     dl, 1; NewValue
0x140017de3  lea     ecx, [r8+13h]; Privilege
0x140017de7  call    cs:__imp_RtlAdjustPrivilege
0x140017ded  lea     rax, [rsp+68h+var_38]
0x140017df2  mov     r9, rsi; Parameters
0x140017df5  mov     [rsp+68h+Response], rax; Response
0x140017dfa  mov     r8d, edi; UnicodeStringParameterMask
0x140017dfd  mov     edx, ebx; NumberOfParameters
0x140017dff  mov     [rsp+68h+OutputBufferLength], 6; ValidResponseOptions
0x140017e07  mov     ecx, 0C000021Ah; ErrorStatus
0x140017e0c  call    cs:__imp_NtRaiseHardError
0x140017e12  mov     edx, eax; ExitStatus
0x140017e14  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140017e18  call    cs:__imp_NtTerminateProcess
```
