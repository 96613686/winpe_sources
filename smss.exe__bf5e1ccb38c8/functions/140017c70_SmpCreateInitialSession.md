# SmpCreateInitialSession

- ea: `0x140017c70`
- end: `0x140017d55`
- name: `SmpCreateInitialSession`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1400036d0`
- `0x14000d4c0`
- `0x140017c70`
- `0x140017d5c`
- `0x140017e28`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140017cfc`
- `ntdll!RtlInitUnicodeString` at `0x140017cfc`

## string_xrefs

- `0x140017d1c`: `SmpCreateInitialSession`

## pseudocode

```c
__int64 SmpCreateInitialSession()
{
  __int64 result; // rax
  unsigned int v1; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-190h] BYREF
  unsigned __int64 Parameters[3]; // [rsp+38h] [rbp-180h] BYREF
  _BYTE v4[8]; // [rsp+50h] [rbp-168h] BYREF
  __int64 v5; // [rsp+58h] [rbp-160h]
  int v6; // [rsp+78h] [rbp-140h]
  int v7; // [rsp+80h] [rbp-138h]
  int v8; // [rsp+84h] [rbp-134h]

  memset_0(v4, 0, 0x148u);
  DestinationString = 0;
  v7 = -1;
  v8 = 0;
  v6 = 5;
  v5 = SmpUniqueProcessId;
  result = SmpStartCsr((__int64)v4);
  v1 = result;
  if ( (int)result < 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"Session Manager Core Session failure");
    Parameters[0] = (unsigned __int64)&DestinationString;
    Parameters[1] = (int)v1;
    SmpLogFailure("SmpCreateInitialSession", 824, v1);
    SmpTerminate(Parameters, 1u, 2u);
  }
  return result;
}

```

## disassembly

```asm
0x140017c70  push    rbx
0x140017c72  sub     rsp, 1B0h
0x140017c79  mov     rax, cs:__security_cookie
0x140017c80  xor     rax, rsp
0x140017c83  mov     [rsp+1B8h+var_18], rax
0x140017c8b  xor     edx, edx; Val
0x140017c8d  mov     r8d, 148h; Size
0x140017c93  lea     rcx, [rsp+1B8h+var_168]; void *
0x140017c98  call    memset_0
0x140017c9d  xorps   xmm0, xmm0
0x140017ca0  movups  xmmword ptr [rsp+1B8h+DestinationString.Length], xmm0
0x140017ca5  mov     [rsp+1B8h+var_138], 0FFFFFFFFh
0x140017cb0  mov     [rsp+1B8h+var_134], 0
0x140017cbb  mov     [rsp+1B8h+var_140], 5
0x140017cc3  mov     rax, cs:SmpUniqueProcessId
0x140017cca  mov     [rsp+1B8h+var_160], rax
0x140017ccf  xor     r8d, r8d
0x140017cd2  xor     edx, edx
0x140017cd4  lea     rcx, [rsp+1B8h+var_168]
0x140017cd9  call    SmpStartCsr
0x140017cde  mov     ebx, eax
0x140017ce0  mov     [rsp+1B8h+var_198], eax
0x140017ce4  jmp     short loc_140017CEC
0x140017ce6  mov     ebx, eax
0x140017ce8  mov     [rsp+1B8h+var_198], eax
0x140017cec  test    ebx, ebx
0x140017cee  jns     short loc_140017D3C
0x140017cf0  lea     rdx, aSessionManager; "Session Manager Core Session failure"
0x140017cf7  lea     rcx, [rsp+1B8h+DestinationString]; DestinationString
0x140017cfc  call    cs:__imp_RtlInitUnicodeString
0x140017d02  lea     rax, [rsp+1B8h+DestinationString]
0x140017d07  mov     [rsp+1B8h+Parameters], rax
0x140017d0c  movsxd  rax, ebx
0x140017d0f  mov     [rsp+1B8h+var_178], rax
0x140017d14  mov     r8d, ebx
0x140017d17  mov     edx, 338h
0x140017d1c  lea     rcx, aSmpcreateiniti; "SmpCreateInitialSession"
0x140017d23  call    SmpLogFailure
0x140017d28  mov     edx, 1; UnicodeStringParameterMask
0x140017d2d  lea     r8d, [rdx+1]; NumberOfParameters
0x140017d31  lea     rcx, [rsp+1B8h+Parameters]; Parameters
0x140017d36  call    SmpTerminate
0x140017d3c  mov     rcx, [rsp+1B8h+var_18]
0x140017d44  xor     rcx, rsp; StackCookie
0x140017d47  call    __security_check_cookie
0x140017d4c  add     rsp, 1B0h
0x140017d53  pop     rbx
0x140017d54  retn
0x14001cf9d  push    rbp
0x14001cf9f  sub     rsp, 20h
0x14001cfa3  mov     rbp, rdx
0x14001cfa6  call    SmpUnhandledExceptionFilter
0x14001cfab  nop
0x14001cfac  add     rsp, 20h
0x14001cfb0  pop     rbp
0x14001cfb1  retn
```
