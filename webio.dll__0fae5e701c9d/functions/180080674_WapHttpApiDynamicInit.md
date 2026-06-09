# WapHttpApiDynamicInit

- ea: `0x180080674`
- end: `0x180080829`
- name: `WapHttpApiDynamicInit`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800780f4`

## callees

- `0x1800722f0`
- `0x180080674`
- `0x180092564`
- `0x1800971ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800806bb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800806bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800806d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800806e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800806d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800806e3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800806f2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800806f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800807a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800807e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800807a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800807e0`
- `HTTPAPI!HttpTerminate` at `0x1800807b3`
- `HTTPAPI!HttpTerminate` at `0x1800807b3`
- `HTTPAPI!HttpInitialize` at `0x18008071b`
- `HTTPAPI!HttpInitialize` at `0x18008071b`
- `HTTPAPI!HttpGetExtension` at `0x18008076c`
- `HTTPAPI!HttpGetExtension` at `0x18008076c`

## pseudocode

```c
__int64 WapHttpApiDynamicInit()
{
  ULONG v0; // ebx
  ULONG v1; // eax
  ULONG Extension; // eax
  __int64 Buffer; // [rsp+28h] [rbp-20h] BYREF

  v0 = 0;
  Buffer = 0;
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_(1050, 19, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids);
  AcquireSRWLockShared(&WaHttpApiLock);
  if ( WaHttpApiInitialized )
  {
    ReleaseSRWLockShared(&WaHttpApiLock);
    goto LABEL_15;
  }
  ReleaseSRWLockShared(&WaHttpApiLock);
  AcquireSRWLockExclusive(&WaHttpApiLock);
  if ( WaHttpApiInitialized )
    goto LABEL_14;
  v1 = HttpInitialize((HTTPAPI_VERSION)2, 0, 0);
  v0 = v1;
  if ( v1 )
  {
    if ( (BYTE3(xmmword_1800AD710) & 4) != 0 )
      WPP_SF_d(538, 20, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, v1);
    goto LABEL_14;
  }
  Extension = HttpGetExtension((HTTPAPI_VERSION)2, 0x89Bu, &Buffer, 8u);
  v0 = Extension;
  if ( !Extension )
  {
    WaHttpClientVTable = Buffer;
    Buffer = 0;
    WaHttpApiInitialized = 1;
LABEL_14:
    ReleaseSRWLockExclusive(&WaHttpApiLock);
    goto LABEL_15;
  }
  if ( (BYTE3(xmmword_1800AD710) & 4) != 0 )
    WPP_SF_d(538, 21, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, Extension);
  ReleaseSRWLockExclusive(&WaHttpApiLock);
  HttpTerminate(0, 0);
LABEL_15:
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_d(1050, 22, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, v0);
  return v0;
}

```

## disassembly

```asm
0x180080674  mov     [rsp+arg_0], rbx
0x180080679  push    rdi
0x18008067a  sub     rsp, 40h
0x18008067e  mov     rax, cs:__security_cookie
0x180080685  xor     rax, rsp
0x180080688  mov     [rsp+48h+var_18], rax
0x18008068d  xor     ebx, ebx
0x18008068f  mov     [rsp+48h+Buffer], rbx
0x180080694  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18008069b  jz      short loc_1800806B1
0x18008069d  lea     edx, [rbx+13h]
0x1800806a0  mov     ecx, 41Ah
0x1800806a5  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x1800806ac  call    WPP_SF_
0x1800806b1  lea     rdi, WaHttpApiLock
0x1800806b8  mov     rcx, rdi; SRWLock
0x1800806bb  call    cs:__imp_AcquireSRWLockShared
0x1800806c2  nop     dword ptr [rax+rax+00h]
0x1800806c7  cmp     cs:WaHttpApiInitialized, bl
0x1800806cd  mov     rcx, rdi; SRWLock
0x1800806d0  jz      short loc_1800806E3
0x1800806d2  call    cs:__imp_ReleaseSRWLockShared
0x1800806d9  nop     dword ptr [rax+rax+00h]
0x1800806de  jmp     loc_1800807EC
0x1800806e3  call    cs:__imp_ReleaseSRWLockShared
0x1800806ea  nop     dword ptr [rax+rax+00h]
0x1800806ef  mov     rcx, rdi; SRWLock
0x1800806f2  call    cs:__imp_AcquireSRWLockExclusive
0x1800806f9  nop     dword ptr [rax+rax+00h]
0x1800806fe  cmp     cs:WaHttpApiInitialized, bl
0x180080704  jnz     loc_1800807DD
0x18008070a  mov     dword ptr [rsp+48h+Version.HttpApiMajorVersion], 2
0x180080712  xor     r8d, r8d; pReserved
0x180080715  mov     ecx, dword ptr [rsp+48h+Version.HttpApiMajorVersion]; Version
0x180080719  xor     edx, edx; Flags
0x18008071b  call    cs:__imp_HttpInitialize
0x180080722  nop     dword ptr [rax+rax+00h]
0x180080727  mov     ebx, eax
0x180080729  test    eax, eax
0x18008072b  jz      short loc_180080758
0x18008072d  test    byte ptr cs:xmmword_1800AD710+3, 4
0x180080734  jz      loc_1800807DD
0x18008073a  mov     edx, 14h
0x18008073f  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x180080746  mov     ecx, 21Ah
0x18008074b  mov     r9d, eax
0x18008074e  call    WPP_SF_d
0x180080753  jmp     loc_1800807DD
0x180080758  mov     ecx, dword ptr [rsp+48h+Version.HttpApiMajorVersion]; Version
0x18008075c  lea     r8, [rsp+48h+Buffer]; Buffer
0x180080761  mov     r9d, 8; BufferSize
0x180080767  mov     edx, 89Bh; Extension
0x18008076c  call    cs:__imp_HttpGetExtension
0x180080773  nop     dword ptr [rax+rax+00h]
0x180080778  mov     ebx, eax
0x18008077a  test    eax, eax
0x18008077c  jz      short loc_1800807C1
0x18008077e  test    byte ptr cs:xmmword_1800AD710+3, 4
0x180080785  jz      short loc_1800807A0
0x180080787  mov     edx, 15h
0x18008078c  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x180080793  mov     ecx, 21Ah
0x180080798  mov     r9d, eax
0x18008079b  call    WPP_SF_d
0x1800807a0  mov     rcx, rdi; SRWLock
0x1800807a3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800807aa  nop     dword ptr [rax+rax+00h]
0x1800807af  xor     edx, edx; pReserved
0x1800807b1  xor     ecx, ecx; Flags
0x1800807b3  call    cs:__imp_HttpTerminate
0x1800807ba  nop     dword ptr [rax+rax+00h]
0x1800807bf  jmp     short loc_1800807EC
0x1800807c1  mov     rax, [rsp+48h+Buffer]
0x1800807c6  mov     cs:WaHttpClientVTable, rax
0x1800807cd  mov     [rsp+48h+Buffer], 0
0x1800807d6  mov     cs:WaHttpApiInitialized, 1
0x1800807dd  mov     rcx, rdi; SRWLock
0x1800807e0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800807e7  nop     dword ptr [rax+rax+00h]
0x1800807ec  test    byte ptr cs:xmmword_1800AD720+3, 4
0x1800807f3  jz      short loc_18008080E
0x1800807f5  mov     edx, 16h
0x1800807fa  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x180080801  mov     ecx, 41Ah
0x180080806  mov     r9d, ebx
0x180080809  call    WPP_SF_d
0x18008080e  mov     eax, ebx
0x180080810  mov     rcx, [rsp+48h+var_18]
0x180080815  xor     rcx, rsp; StackCookie
0x180080818  call    __security_check_cookie
0x18008081d  mov     rbx, [rsp+48h+arg_0]
0x180080822  add     rsp, 40h
0x180080826  pop     rdi
0x180080827  retn
```
