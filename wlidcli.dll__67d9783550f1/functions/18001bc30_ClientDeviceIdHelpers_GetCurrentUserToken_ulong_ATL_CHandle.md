# ClientDeviceIdHelpers::GetCurrentUserToken(ulong,ATL::CHandle &)

- ea: `0x18001bc30`
- end: `0x18001bd2d`
- name: `?GetCurrentUserToken@ClientDeviceIdHelpers@@SAJKAEAVCHandle@ATL@@@Z`
- size: `253`
- prototype: `static int(unsigned int, struct ATL::CHandle *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18001bd34`

## callees

- `0x18000cc9c`
- `0x18000e870`
- `0x18001bc30`
- `0x1800530e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bcdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bcdf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001bc92`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001bc92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001bc7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001bc7d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001bcd5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001bcd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001bcc4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001bcc4`

## string_xrefs

- `0x18001bc52`: `ClientDeviceIdHelpers::GetCurrentUserToken`
- `0x18001bcb5`: `OpenThreadToken failed with hr = 0x%x`
- `0x18001bcf1`: `OpenProcessToken failed with hr = 0x%x`

## pseudocode

```c
__int64 __fastcall ClientDeviceIdHelpers::GetCurrentUserToken(__int64 a1, HANDLE *a2)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  const unsigned __int16 *v5; // r9
  unsigned int v6; // r8d
  HANDLE CurrentProcess; // rax
  unsigned int v8; // ebx
  const unsigned __int16 *v10; // [rsp+20h] [rbp-38h]
  __int64 v11; // [rsp+20h] [rbp-38h]
  _QWORD v12[5]; // [rsp+30h] [rbp-28h] BYREF
  signed int v13; // [rsp+60h] [rbp+8h] BYREF

  v13 = 0;
  v12[2] = 0;
  v12[3] = 0;
  v12[0] = "ClientDeviceIdHelpers::GetCurrentUserToken";
  v12[1] = &v13;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrldevicehelpers.cpp",
    "ClientDeviceIdHelpers::GetCurrentUserToken",
    (const char *)0x5F,
    0,
    v10);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xAu, 1, a2) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v5 = L"OpenThreadToken failed with hr = 0x%x";
      v6 = 105;
LABEL_10:
      LODWORD(v11) = LastError;
      v13 = LastError;
      TracePrintW(2u, "clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrldevicehelpers.cpp", v6, v5, v11);
      goto LABEL_11;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xAu, a2) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v5 = L"OpenProcessToken failed with hr = 0x%x";
      v6 = 112;
      goto LABEL_10;
    }
  }
LABEL_11:
  v8 = v13;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v12);
  return v8;
}

```

## disassembly

```asm
0x18001bc30  mov     [rsp+arg_0], ecx
0x18001bc34  mov     r11, rsp
0x18001bc37  push    rbx
0x18001bc38  sub     rsp, 50h
0x18001bc3c  xor     r9d, r9d; unsigned int
0x18001bc3f  mov     [rsp+58h+arg_0], 0
0x18001bc47  mov     rbx, rdx
0x18001bc4a  mov     qword ptr [r11-18h], 0
0x18001bc52  lea     rdx, aClientdeviceid_1; "ClientDeviceIdHelpers::GetCurrentUserTo"...
0x18001bc59  mov     qword ptr [r11-10h], 0
0x18001bc61  lea     rax, [r11+8]
0x18001bc65  mov     [r11-28h], rdx
0x18001bc69  lea     r8d, [r9+5Fh]; char *
0x18001bc6d  mov     [r11-20h], rax
0x18001bc71  lea     rcx, aClientcoreDsEx_9; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18001bc78  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18001bc7d  call    cs:__imp_GetCurrentThread
0x18001bc83  mov     edx, 0Ah; DesiredAccess
0x18001bc88  mov     r9, rbx; TokenHandle
0x18001bc8b  mov     rcx, rax; ThreadHandle
0x18001bc8e  lea     r8d, [rdx-9]; OpenAsSelf
0x18001bc92  call    cs:__imp_OpenThreadToken
0x18001bc98  test    eax, eax
0x18001bc9a  jnz     short loc_18001BD17
0x18001bc9c  call    cs:__imp_GetLastError
0x18001bca2  cmp     eax, 3F0h
0x18001bca7  jz      short loc_18001BCC4
0x18001bca9  test    eax, eax
0x18001bcab  jle     short loc_18001BCB5
0x18001bcad  movzx   eax, ax
0x18001bcb0  or      eax, 80070000h
0x18001bcb5  lea     r9, aOpenthreadtoke_0; "OpenThreadToken failed with hr = 0x%x"
0x18001bcbc  mov     r8d, 69h ; 'i'
0x18001bcc2  jmp     short loc_18001BCFE
0x18001bcc4  call    cs:__imp_GetCurrentProcess
0x18001bcca  mov     r8, rbx; TokenHandle
0x18001bccd  mov     edx, 0Ah; DesiredAccess
0x18001bcd2  mov     rcx, rax; ProcessHandle
0x18001bcd5  call    cs:__imp_OpenProcessToken
0x18001bcdb  test    eax, eax
0x18001bcdd  jnz     short loc_18001BD17
0x18001bcdf  call    cs:__imp_GetLastError
0x18001bce5  test    eax, eax
0x18001bce7  jle     short loc_18001BCF1
0x18001bce9  movzx   eax, ax
0x18001bcec  or      eax, 80070000h
0x18001bcf1  lea     r9, aOpenprocesstok_0; "OpenProcessToken failed with hr = 0x%x"
0x18001bcf8  mov     r8d, 70h ; 'p'; unsigned int
0x18001bcfe  lea     rdx, aClientcoreDsEx_9; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18001bd05  mov     [rsp+58h+var_38], eax
0x18001bd09  mov     ecx, 2; unsigned __int8
0x18001bd0e  mov     [rsp+58h+arg_0], eax
0x18001bd12  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001bd17  mov     ebx, [rsp+58h+arg_0]
0x18001bd1b  lea     rcx, [rsp+58h+var_28]
0x18001bd20  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18001bd25  mov     eax, ebx
0x18001bd27  add     rsp, 50h
0x18001bd2b  pop     rbx
0x18001bd2c  retn
```
