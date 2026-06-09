# UbpmParams::CreateHostedSidFromCapabilityName(ushort const *)

- ea: `0x180079d0c`
- end: `0x180079dcd`
- name: `?CreateHostedSidFromCapabilityName@UbpmParams@@AEAAPEAXPEBG@Z`
- size: `193`
- prototype: `__int64 __fastcall(UbpmParams *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180079ae4`

## callees

- `0x18005790c`
- `0x180079c78`
- `0x180079d0c`
- `0x18007e6d0`

## import_xrefs

- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180079d4c`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180079d4c`
- `ntdll!RtlInitUnicodeString` at `0x180079d3a`
- `ntdll!RtlInitUnicodeString` at `0x180079d3a`
- `ntdll!RtlNtStatusToDosError` at `0x180079d58`
- `ntdll!RtlNtStatusToDosError` at `0x180079d58`

## pseudocode

```c
__int64 __fastcall UbpmParams::CreateHostedSidFromCapabilityName(UbpmParams *this, const unsigned __int16 *a2)
{
  NTSTATUS v3; // eax
  ULONG v4; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-59h] BYREF
  void **pExceptionObject; // [rsp+30h] [rbp-49h] BYREF
  char v8; // [rsp+38h] [rbp-41h]
  const unsigned __int16 *v9; // [rsp+40h] [rbp-39h]
  __int64 v10; // [rsp+48h] [rbp-31h]
  __int64 v11; // [rsp+50h] [rbp-29h]
  ULONG v12; // [rsp+58h] [rbp-21h]
  __int64 v13; // [rsp+5Ch] [rbp-1Dh]
  char v14[48]; // [rsp+68h] [rbp-11h] BYREF
  _BYTE v15[48]; // [rsp+98h] [rbp+1Fh] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  v3 = RtlDeriveCapabilitySidsFromName(&DestinationString, v15, v14);
  if ( v3 < 0 )
  {
    v4 = RtlNtStatusToDosError(v3);
    v8 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v10 = 0;
    v9 = &qword_1800A4718;
    v11 = 0;
    v12 = v4;
    v13 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  return UbpmParams::CreateHostedSid(this, v14);
}

```

## disassembly

```asm
0x180079d0c  mov     [rsp-8+arg_10], rbx
0x180079d11  push    rbp
0x180079d12  lea     rbp, [rsp-57h]
0x180079d17  sub     rsp, 0D0h
0x180079d1e  mov     rax, cs:__security_cookie
0x180079d25  xor     rax, rsp
0x180079d28  mov     [rbp+57h+var_8], rax
0x180079d2c  mov     rbx, rcx
0x180079d2f  xorps   xmm0, xmm0
0x180079d32  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180079d36  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180079d3a  call    cs:__imp_RtlInitUnicodeString
0x180079d40  lea     r8, [rbp+57h+var_68]
0x180079d44  lea     rdx, [rbp+57h+var_38]
0x180079d48  lea     rcx, [rbp+57h+DestinationString]
0x180079d4c  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x180079d52  test    eax, eax
0x180079d54  jns     short loc_180079DA4
0x180079d56  mov     ecx, eax; Status
0x180079d58  call    cs:__imp_RtlNtStatusToDosError
0x180079d5e  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180079d65  mov     [rbp+57h+var_98], 0
0x180079d69  mov     [rbp+57h+pExceptionObject], rcx
0x180079d6d  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180079d74  lea     rcx, qword_1800A4718
0x180079d7b  mov     [rbp+57h+var_88], 0
0x180079d83  mov     [rbp+57h+var_90], rcx
0x180079d87  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180079d8b  mov     [rbp+57h+var_80], 0
0x180079d93  mov     [rbp+57h+var_78], eax
0x180079d96  mov     [rbp+57h+var_74], 0FFFFFFFFFFFFFFFFh
0x180079d9e  call    _CxxThrowException_0
0x180079da4  lea     rdx, [rbp+57h+var_68]; void *
0x180079da8  mov     rcx, rbx; this
0x180079dab  call    ?CreateHostedSid@UbpmParams@@AEAAPEAXQEAX@Z; UbpmParams::CreateHostedSid(void * const)
0x180079db0  mov     rcx, [rbp+57h+var_8]
0x180079db4  xor     rcx, rsp; StackCookie
0x180079db7  call    __security_check_cookie
0x180079dbc  mov     rbx, [rsp+0D0h+arg_10]
0x180079dc4  add     rsp, 0D0h
0x180079dcb  pop     rbp
0x180079dcc  retn
```
