# CWLIDCCHelper::CreateEventExW(ushort const *,ushort const *,ulong,ulong,void * *)

- ea: `0x180002d94`
- end: `0x180002eab`
- name: `?CreateEventExW@CWLIDCCHelper@@SAJPEBG0KKPEAPEAX@Z`
- size: `279`
- prototype: `static int(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800027e0`

## callees

- `0x180002d94`
- `0x1800061a8`
- `0x180013c8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180002e74`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180002e74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e82`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180002e19`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180002e19`

## string_xrefs

- `0x180002deb`: `CWLIDCCHelper::CreateEventExW`

## pseudocode

```c
__int64 __fastcall CWLIDCCHelper::CreateEventExW(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        void **a5)
{
  signed int v6; // ebx
  const char *v7; // rax
  unsigned int v8; // r8d
  signed int LastError; // eax
  HANDLE v10; // rax
  signed int v11; // eax
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+30h] [rbp-38h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor[4]; // [rsp+48h] [rbp-20h] BYREF

  memset(SecurityDescriptor, 0, 24);
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  if ( !a5 )
  {
    v6 = -2147024809;
    v7 = "pHandle != nullptr";
    v8 = 686;
LABEL_3:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\wlidcchelper.cpp",
      "CWLIDCCHelper::CreateEventExW",
      v8,
      v6,
      v7);
    goto LABEL_12;
  }
  v6 = 0;
  *a5 = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:P(A;;0x1F0003;;;SY)(A;;0x00100000;;;AU)",
          1u,
          SecurityDescriptor,
          0) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 < 0 )
    {
      v7 = "hr = HRESULT_FROM_WIN32(GetLastError())";
      v8 = 695;
      goto LABEL_3;
    }
  }
  EventAttributes.lpSecurityDescriptor = SecurityDescriptor[0];
  EventAttributes.nLength = 24;
  EventAttributes.bInheritHandle = 0;
  v10 = CreateEventExW(&EventAttributes, a2, 1u, 0x100000u);
  *a5 = v10;
  if ( !v10 )
  {
    v11 = GetLastError();
    v6 = v11;
    if ( v11 > 0 )
      v6 = (unsigned __int16)v11 | 0x80070000;
  }
LABEL_12:
  Auto<void *,LocalAllocFunctor<void *>,DummyContext>::~Auto<void *,LocalAllocFunctor<void *>,DummyContext>(SecurityDescriptor);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002d94  push    rbp
0x180002d96  push    rbx
0x180002d97  push    rsi
0x180002d98  push    rdi
0x180002d99  mov     rbp, rsp
0x180002d9c  sub     rsp, 68h
0x180002da0  mov     rdi, [rbp+arg_20]
0x180002da4  xor     eax, eax
0x180002da6  mov     [rbp+SecurityDescriptor], 0
0x180002dae  xorps   xmm0, xmm0
0x180002db1  mov     [rbp+var_10], 0
0x180002db9  mov     rsi, rdx
0x180002dbc  mov     [rbp+var_18], 0
0x180002dc4  mov     qword ptr [rbp+EventAttributes.bInheritHandle], rax
0x180002dc8  movups  xmmword ptr [rbp+EventAttributes.nLength], xmm0
0x180002dcc  test    rdi, rdi
0x180002dcf  jnz     short loc_180002E03
0x180002dd1  mov     ebx, 80070057h
0x180002dd6  lea     rax, aPhandleNullptr; "pHandle != nullptr"
0x180002ddd  mov     r8d, 2AEh; unsigned int
0x180002de3  mov     r9d, ebx; int
0x180002de6  mov     [rsp+68h+var_48], rax; char *
0x180002deb  lea     rdx, aCwlidcchelperC; "CWLIDCCHelper::CreateEventExW"
0x180002df2  lea     rcx, aOnecoreuapDsEx_18; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180002df9  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180002dfe  jmp     loc_180002E97
0x180002e03  xor     ebx, ebx
0x180002e05  mov     [rdi], rax
0x180002e08  xor     r9d, r9d; SecurityDescriptorSize
0x180002e0b  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180002e0f  lea     rcx, StringSecurityDescriptor; "D:P(A;;0x1F0003;;;SY)(A;;0x00100000;;;A"...
0x180002e16  lea     edx, [rbx+1]; StringSDRevision
0x180002e19  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180002e1f  test    eax, eax
0x180002e21  jnz     short loc_180002E4B
0x180002e23  call    cs:__imp_GetLastError
0x180002e29  mov     ebx, eax
0x180002e2b  test    eax, eax
0x180002e2d  jle     short loc_180002E38
0x180002e2f  movzx   ebx, ax
0x180002e32  or      ebx, 80070000h
0x180002e38  test    ebx, ebx
0x180002e3a  jns     short loc_180002E4B
0x180002e3c  lea     rax, aHrHresultFromW_2; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x180002e43  mov     r8d, 2B7h
0x180002e49  jmp     short loc_180002DE3
0x180002e4b  mov     rax, [rbp+SecurityDescriptor]
0x180002e4f  lea     rcx, [rbp+EventAttributes]; lpEventAttributes
0x180002e53  mov     r9d, 100000h; dwDesiredAccess
0x180002e59  mov     [rbp+EventAttributes.lpSecurityDescriptor], rax
0x180002e5d  mov     r8d, 1; dwFlags
0x180002e63  mov     [rbp+EventAttributes.nLength], 18h
0x180002e6a  mov     rdx, rsi; lpName
0x180002e6d  mov     [rbp+EventAttributes.bInheritHandle], 0
0x180002e74  call    cs:__imp_CreateEventExW
0x180002e7a  mov     [rdi], rax
0x180002e7d  test    rax, rax
0x180002e80  jnz     short loc_180002E97
0x180002e82  call    cs:__imp_GetLastError
0x180002e88  mov     ebx, eax
0x180002e8a  test    eax, eax
0x180002e8c  jle     short loc_180002E97
0x180002e8e  movzx   ebx, ax
0x180002e91  or      ebx, 80070000h
0x180002e97  lea     rcx, [rbp+SecurityDescriptor]
0x180002e9b  call    ??1?$Auto@PEAXV?$LocalAllocFunctor@PEAX@@VDummyContext@@@@QEAA@XZ; Auto<void *,LocalAllocFunctor<void *>,DummyContext>::~Auto<void *,LocalAllocFunctor<void *>,DummyContext>(void)
0x180002ea0  mov     eax, ebx
0x180002ea2  add     rsp, 68h
0x180002ea6  pop     rdi
0x180002ea7  pop     rsi
0x180002ea8  pop     rbx
0x180002ea9  pop     rbp
0x180002eaa  retn
```
