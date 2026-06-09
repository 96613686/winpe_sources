# CVdsService::RemoveFSPropertiesFromMap(IUnknown *)

- ea: `0x14003bca8`
- end: `0x14003bde5`
- name: `?RemoveFSPropertiesFromMap@CVdsService@@QEAAHPEAUIUnknown@@@Z`
- size: `317`
- prototype: `__int64 __fastcall(CVdsService *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x140040e30`

## callees

- `0x14003bca8`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003bd79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003bdb4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003bd79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003bdb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003bd2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003bd2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003bd63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003bd91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003bd63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003bd91`
- `vdsutil!?FindPtr@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAPEAV2@@Z` at `0x14003bd48`
- `vdsutil!?FindPtr@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAPEAV2@@Z` at `0x14003bd48`
- `vdsutil!?Remove@CRtlMap@@QEAAHAEAVCRtlEntry@@@Z` at `0x14003bd59`
- `vdsutil!?Remove@CRtlMap@@QEAAHAEAVCRtlEntry@@@Z` at `0x14003bd59`
- `vdsutil!VdsTraceEx` at `0x14003bd19`
- `vdsutil!VdsTraceEx` at `0x14003bda6`
- `vdsutil!VdsTraceEx` at `0x14003bd19`
- `vdsutil!VdsTraceEx` at `0x14003bda6`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003bcde`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003bcde`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003bd84`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003bdbf`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003bd84`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003bdbf`

## string_xrefs

- `0x14003bcce`: `RemoveFSPropertiesFromMap`
- `0x14003bd0d`: `CVdsService::RemoveFSPropertiesFromMap, 1, pObject=%p`
- `0x14003bd69`: `CVdsService::RemoveFSPropertiesFromMap, 2, error = %ld`
- `0x14003bd97`: `CVdsService::RemoveFSPropertiesFromMap, 3, error = %ld`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsService::RemoveFSPropertiesFromMap(CVdsService *this, struct IUnknown *a2)
{
  DWORD LastError; // eax
  DWORD v6; // eax
  _BYTE v7[16]; // [rsp+20h] [rbp-50h] BYREF
  struct CRtlEntry *v8; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v9[5]; // [rsp+38h] [rbp-38h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v7, 0x5Eu, "RemoveFSPropertiesFromMap");
  v9[0] = 0;
  v9[1] = 0;
  v9[3] = 0;
  v8 = 0;
  if ( a2 )
  {
    v9[2] = a2;
    EnterCriticalSection(&g_GlobalCriticalSection);
    if ( CRtlMap::FindPtr((CVdsService *)((char *)this + 304), (struct CRtlEntry *)v9, &v8) )
    {
      if ( CRtlMap::Remove((CVdsService *)((char *)this + 304), (struct CRtlEntry *)v9) )
      {
        LeaveCriticalSection(&g_GlobalCriticalSection);
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v7);
        return 1;
      }
      LastError = GetLastError();
      VdsTraceEx(94, 0, "CVdsService::RemoveFSPropertiesFromMap, 2, error = %ld", LastError);
    }
    else
    {
      v6 = GetLastError();
      VdsTraceEx(94, 0, "CVdsService::RemoveFSPropertiesFromMap, 3, error = %ld", v6);
    }
    LeaveCriticalSection(&g_GlobalCriticalSection);
  }
  else
  {
    VdsTraceEx(94, 0, "CVdsService::RemoveFSPropertiesFromMap, 1, pObject=%p", 0);
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v7);
  return 0;
}

```

## disassembly

```asm
0x14003bca8  mov     [rsp-8+arg_10], rbx
0x14003bcad  mov     [rsp-8+arg_18], rdi
0x14003bcb2  push    rbp
0x14003bcb3  mov     rbp, rsp
0x14003bcb6  sub     rsp, 70h
0x14003bcba  mov     rax, cs:__security_cookie
0x14003bcc1  xor     rax, rsp
0x14003bcc4  mov     [rbp+var_10], rax
0x14003bcc8  mov     rbx, rdx
0x14003bccb  mov     rdi, rcx
0x14003bcce  lea     r8, aRemovefsproper; "RemoveFSPropertiesFromMap"
0x14003bcd5  mov     edx, 5Eh ; '^'
0x14003bcda  lea     rcx, [rbp+var_50]
0x14003bcde  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14003bce4  nop
0x14003bce5  mov     [rbp+var_38], 0
0x14003bced  mov     [rbp+var_30], 0
0x14003bcf5  mov     [rbp+var_20], 0
0x14003bcfd  mov     [rbp+var_40], 0
0x14003bd05  test    rbx, rbx
0x14003bd08  jnz     short loc_14003BD24
0x14003bd0a  xor     r9d, r9d
0x14003bd0d  lea     r8, aCvdsserviceRem_10; "CVdsService::RemoveFSPropertiesFromMap,"...
0x14003bd14  xor     edx, edx
0x14003bd16  lea     ecx, [rbx+5Eh]
0x14003bd19  call    cs:__imp_VdsTraceEx
0x14003bd1f  jmp     loc_14003BDBB
0x14003bd24  mov     [rbp+var_28], rbx
0x14003bd28  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003bd2f  call    cs:__imp_EnterCriticalSection
0x14003bd35  nop
0x14003bd36  lea     rbx, [rdi+130h]
0x14003bd3d  lea     r8, [rbp+var_40]
0x14003bd41  lea     rdx, [rbp+var_38]
0x14003bd45  mov     rcx, rbx
0x14003bd48  call    cs:__imp_?FindPtr@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAPEAV2@@Z; CRtlMap::FindPtr(CRtlEntry &,CRtlEntry * *)
0x14003bd4e  test    eax, eax
0x14003bd50  jz      short loc_14003BD91
0x14003bd52  lea     rdx, [rbp+var_38]
0x14003bd56  mov     rcx, rbx
0x14003bd59  call    cs:__imp_?Remove@CRtlMap@@QEAAHAEAVCRtlEntry@@@Z; CRtlMap::Remove(CRtlEntry &)
0x14003bd5f  test    eax, eax
0x14003bd61  jnz     short loc_14003BD72
0x14003bd63  call    cs:__imp_GetLastError
0x14003bd69  lea     r8, aCvdsserviceRem_26; "CVdsService::RemoveFSPropertiesFromMap,"...
0x14003bd70  jmp     short loc_14003BD9E
0x14003bd72  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003bd79  call    cs:__imp_LeaveCriticalSection
0x14003bd7f  nop
0x14003bd80  lea     rcx, [rbp+var_50]
0x14003bd84  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14003bd8a  mov     eax, 1
0x14003bd8f  jmp     short loc_14003BDC7
0x14003bd91  call    cs:__imp_GetLastError
0x14003bd97  lea     r8, aCvdsserviceRem_28; "CVdsService::RemoveFSPropertiesFromMap,"...
0x14003bd9e  mov     r9d, eax
0x14003bda1  xor     edx, edx
0x14003bda3  lea     ecx, [rdx+5Eh]
0x14003bda6  call    cs:__imp_VdsTraceEx
0x14003bdac  nop
0x14003bdad  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003bdb4  call    cs:__imp_LeaveCriticalSection
0x14003bdba  nop
0x14003bdbb  lea     rcx, [rbp+var_50]
0x14003bdbf  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14003bdc5  xor     eax, eax
0x14003bdc7  mov     rcx, [rbp+var_10]
0x14003bdcb  xor     rcx, rsp; StackCookie
0x14003bdce  call    __security_check_cookie
0x14003bdd3  lea     r11, [rsp+70h+var_s0]
0x14003bdd8  mov     rbx, [r11+20h]
0x14003bddc  mov     rdi, [r11+28h]
0x14003bde0  mov     rsp, r11
0x14003bde3  pop     rbp
0x14003bde4  retn
```
