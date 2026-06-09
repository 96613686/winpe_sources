# CVdsService::Reboot(void)

- ea: `0x140020e70`
- end: `0x1400210a1`
- name: `?Reboot@CVdsService@@UEAAJXZ`
- size: `561`
- prototype: `__int64 __fastcall(CVdsService *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x140003710`
- `0x140004360`
- `0x140020e70`
- `0x140056010`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x140020f28`
- `ntdll!RtlAdjustPrivilege` at `0x140021033`
- `ntdll!RtlAdjustPrivilege` at `0x140020f28`
- `ntdll!RtlAdjustPrivilege` at `0x140021033`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140020eee`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140020eee`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140021052`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140021052`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140020f5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140020f5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020f97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020fd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020f97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020fd5`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140020f8d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140020f8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140021016`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140021016`
- `vdsutil!VdsTraceEx` at `0x140020f0c`
- `vdsutil!VdsTraceEx` at `0x140020f46`
- `vdsutil!VdsTraceEx` at `0x140020fac`
- `vdsutil!VdsTraceEx` at `0x140020ff6`
- `vdsutil!VdsTraceEx` at `0x140021048`
- `vdsutil!VdsTraceEx` at `0x14002106b`
- `vdsutil!VdsTraceEx` at `0x140020f0c`
- `vdsutil!VdsTraceEx` at `0x140020f46`
- `vdsutil!VdsTraceEx` at `0x140020fac`
- `vdsutil!VdsTraceEx` at `0x140020ff6`
- `vdsutil!VdsTraceEx` at `0x140021048`
- `vdsutil!VdsTraceEx` at `0x14002106b`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140020ea0`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140020ea0`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140021080`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140021080`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x140020fcb`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x140020fcb`

## string_xrefs

- `0x140020fe7`: `CVdsService::Reboot: failed to restart the system: %X`
- `0x140020e8c`: `CVdsService::Reboot()`
- `0x140020eff`: `CVdsService::Reboot: CoImpersonateClient failed: %X`
- `0x140020f3a`: `CVdsService::Reboot: failed to enable shutdown privilege: %X`
- `0x140020fa0`: `CVdsService::Reboot: FormatMessage failed: %X`
- `0x14002103c`: `CVdsService::Reboot: failed to disable shutdown privilege: %X`
- `0x14002105f`: `CVdsService::Reboot: CoRevertToSelf failed: %X`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsService::Reboot(CVdsService *this)
{
  int v2; // ebx
  HRESULT v3; // eax
  int v4; // esi
  NTSTATUS v5; // eax
  NTSTATUS v6; // edi
  int v7; // r14d
  HMODULE ModuleHandleW; // rax
  DWORD LastError; // eax
  DWORD v10; // eax
  int v11; // edi
  NTSTATUS v12; // eax
  HRESULT v13; // eax
  __int64 v15; // [rsp+40h] [rbp-20h] BYREF
  int v16; // [rsp+48h] [rbp-18h]
  _BYTE v17[16]; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int8 OldValue; // [rsp+90h] [rbp+30h] BYREF
  WCHAR *Buffer; // [rsp+98h] [rbp+38h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v17, 0x5Eu, "CVdsService::Reboot()");
  v2 = (*(__int64 (__fastcall **)(CVdsService *))(*(_QWORD *)this + 32LL))(this);
  if ( v2 >= 0 )
  {
    v15 = 1;
    v16 = 0;
    v2 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v15);
    if ( v2 >= 0 )
    {
      Buffer = 0;
      OldValue = 0;
      v3 = CoImpersonateClient();
      v2 = v3;
      if ( v3 >= 0 )
      {
        v4 = 1;
      }
      else
      {
        v4 = 0;
        VdsTraceEx(94, 1, "CVdsService::Reboot: CoImpersonateClient failed: %X", v3);
        v2 = 0;
      }
      v5 = RtlAdjustPrivilege(0x13u, 1u, 1u, &OldValue);
      v6 = v5;
      if ( v5 >= 0 )
      {
        v7 = 1;
        ModuleHandleW = GetModuleHandleW(0);
        if ( !FormatMessageW(0x900u, ModuleHandleW, 0x42000011u, 0, (LPWSTR)&Buffer, 0, 0) )
        {
          LastError = GetLastError();
          VdsTraceEx(94, 0, "CVdsService::Reboot: FormatMessage failed: %X", LastError);
        }
        if ( !InitiateSystemShutdownExW(0, Buffer, 0, 0, 1, 0x80020004) )
        {
          v10 = GetLastError();
          v11 = v10;
          if ( v10 != 1115 )
          {
            VdsTraceEx(94, 3, "CVdsService::Reboot: failed to restart the system: %X", v10);
            if ( v11 > 0 )
              v2 = (unsigned __int16)v11 | 0x80070000;
            else
              v2 = v11;
          }
        }
      }
      else
      {
        v7 = 0;
        VdsTraceEx(94, 0, "CVdsService::Reboot: failed to enable shutdown privilege: %X", v5);
        v2 = v6 | 0x10000000;
      }
      if ( Buffer )
        LocalFree(Buffer);
      if ( v7 && !OldValue )
      {
        v12 = RtlAdjustPrivilege(0x13u, 0, 1u, &OldValue);
        VdsTraceEx(94, 0, "CVdsService::Reboot: failed to disable shutdown privilege: %X", v12);
      }
      if ( v4 )
      {
        v13 = CoRevertToSelf();
        if ( v13 < 0 )
          VdsTraceEx(94, 0, "CVdsService::Reboot: CoRevertToSelf failed: %X", v13);
      }
    }
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v15);
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v17);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140020e70  mov     [rsp-28h+arg_10], rbx
0x140020e75  mov     [rsp-28h+arg_18], rsi
0x140020e7a  push    rbp
0x140020e7b  push    rdi
0x140020e7c  push    r12
0x140020e7e  push    r13
0x140020e80  push    r14
0x140020e82  mov     rbp, rsp
0x140020e85  sub     rsp, 60h
0x140020e89  mov     rbx, rcx
0x140020e8c  lea     r8, aCvdsserviceReb_0; "CVdsService::Reboot()"
0x140020e93  mov     r13d, 5Eh ; '^'
0x140020e99  mov     edx, r13d
0x140020e9c  lea     rcx, [rbp+var_10]
0x140020ea0  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140020ea6  nop
0x140020ea7  mov     rax, [rbx]
0x140020eaa  mov     rcx, rbx
0x140020ead  mov     rax, [rax+20h]
0x140020eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020eb6  mov     ebx, eax
0x140020eb8  test    eax, eax
0x140020eba  js      loc_14002107C
0x140020ec0  lea     r12d, [r13-5Dh]
0x140020ec4  mov     [rbp+var_20], r12
0x140020ec8  mov     [rbp+var_18], 0
0x140020ecf  lea     rcx, [rbp+var_20]; this
0x140020ed3  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140020ed8  mov     ebx, eax
0x140020eda  test    eax, eax
0x140020edc  js      loc_140021072
0x140020ee2  mov     [rbp+Buffer], 0
0x140020eea  mov     [rbp+OldValue], 0
0x140020eee  call    cs:__imp_CoImpersonateClient
0x140020ef4  mov     ebx, eax
0x140020ef6  test    eax, eax
0x140020ef8  jns     short loc_140020F16
0x140020efa  xor     esi, esi
0x140020efc  mov     r9d, eax
0x140020eff  lea     r8, aCvdsserviceReb_4; "CVdsService::Reboot: CoImpersonateClien"...
0x140020f06  mov     edx, r12d
0x140020f09  mov     ecx, r13d
0x140020f0c  call    cs:__imp_VdsTraceEx
0x140020f12  xor     ebx, ebx
0x140020f14  jmp     short loc_140020F19
0x140020f16  mov     esi, r12d
0x140020f19  lea     r9, [rbp+OldValue]; OldValue
0x140020f1d  mov     r8b, r12b; ForThread
0x140020f20  mov     dl, r12b; NewValue
0x140020f23  mov     ecx, 13h; Privilege
0x140020f28  call    cs:__imp_RtlAdjustPrivilege
0x140020f2e  mov     edi, eax
0x140020f30  test    eax, eax
0x140020f32  jns     short loc_140020F57
0x140020f34  xor     r14d, r14d
0x140020f37  mov     r9d, eax
0x140020f3a  lea     r8, aCvdsserviceReb; "CVdsService::Reboot: failed to enable s"...
0x140020f41  xor     edx, edx
0x140020f43  mov     ecx, r13d
0x140020f46  call    cs:__imp_VdsTraceEx
0x140020f4c  mov     ebx, edi
0x140020f4e  bts     ebx, 1Ch
0x140020f52  jmp     loc_14002100D
0x140020f57  mov     r14d, r12d
0x140020f5a  xor     ecx, ecx; lpModuleName
0x140020f5c  call    cs:__imp_GetModuleHandleW
0x140020f62  mov     rdx, rax; lpSource
0x140020f65  mov     [rsp+60h+Arguments], 0; Arguments
0x140020f6e  mov     [rsp+60h+nSize], 0; nSize
0x140020f76  lea     rax, [rbp+Buffer]
0x140020f7a  mov     [rsp+60h+lpBuffer], rax; lpBuffer
0x140020f7f  xor     r9d, r9d; dwLanguageId
0x140020f82  mov     ecx, 900h; dwFlags
0x140020f87  mov     r8d, 42000011h; dwMessageId
0x140020f8d  call    cs:__imp_FormatMessageW
0x140020f93  test    eax, eax
0x140020f95  jnz     short loc_140020FB2
0x140020f97  call    cs:__imp_GetLastError
0x140020f9d  mov     r9d, eax
0x140020fa0  lea     r8, aCvdsserviceReb_5; "CVdsService::Reboot: FormatMessage fail"...
0x140020fa7  xor     edx, edx
0x140020fa9  mov     ecx, r13d
0x140020fac  call    cs:__imp_VdsTraceEx
0x140020fb2  mov     [rsp+60h+nSize], 80020004h; dwReason
0x140020fba  mov     dword ptr [rsp+60h+lpBuffer], r12d; bRebootAfterShutdown
0x140020fbf  xor     r9d, r9d; bForceAppsClosed
0x140020fc2  xor     r8d, r8d; dwTimeout
0x140020fc5  mov     rdx, [rbp+Buffer]; lpMessage
0x140020fc9  xor     ecx, ecx; lpMachineName
0x140020fcb  call    cs:__imp_InitiateSystemShutdownExW
0x140020fd1  test    eax, eax
0x140020fd3  jnz     short loc_14002100D
0x140020fd5  call    cs:__imp_GetLastError
0x140020fdb  mov     edi, eax
0x140020fdd  cmp     eax, 45Bh
0x140020fe2  jz      short loc_14002100D
0x140020fe4  mov     r9d, eax
0x140020fe7  lea     r8, aCvdsserviceReb_2; "CVdsService::Reboot: failed to restart "...
0x140020fee  mov     edx, 3
0x140020ff3  mov     ecx, r13d
0x140020ff6  call    cs:__imp_VdsTraceEx
0x140020ffc  test    edi, edi
0x140020ffe  jg      short loc_140021004
0x140021000  mov     ebx, edi
0x140021002  jmp     short loc_14002100D
0x140021004  movzx   ebx, di
0x140021007  or      ebx, 80070000h
0x14002100d  mov     rcx, [rbp+Buffer]; hMem
0x140021011  test    rcx, rcx
0x140021014  jz      short loc_14002101C
0x140021016  call    cs:__imp_LocalFree
0x14002101c  test    r14d, r14d
0x14002101f  jz      short loc_14002104E
0x140021021  cmp     [rbp+OldValue], 0
0x140021025  jnz     short loc_14002104E
0x140021027  lea     r9, [rbp+OldValue]; OldValue
0x14002102b  mov     r8b, r12b; ForThread
0x14002102e  xor     edx, edx; NewValue
0x140021030  lea     ecx, [rdx+13h]; Privilege
0x140021033  call    cs:__imp_RtlAdjustPrivilege
0x140021039  mov     r9d, eax
0x14002103c  lea     r8, aCvdsserviceReb_1; "CVdsService::Reboot: failed to disable "...
0x140021043  xor     edx, edx
0x140021045  mov     ecx, r13d
0x140021048  call    cs:__imp_VdsTraceEx
0x14002104e  test    esi, esi
0x140021050  jz      short loc_140021072
0x140021052  call    cs:__imp_CoRevertToSelf
0x140021058  test    eax, eax
0x14002105a  jns     short loc_140021072
0x14002105c  mov     r9d, eax
0x14002105f  lea     r8, aCvdsserviceReb_3; "CVdsService::Reboot: CoRevertToSelf fai"...
0x140021066  xor     edx, edx
0x140021068  mov     ecx, r13d
0x14002106b  call    cs:__imp_VdsTraceEx
0x140021071  nop
0x140021072  lea     rcx, [rbp+var_20]; this
0x140021076  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x14002107b  nop
0x14002107c  lea     rcx, [rbp+var_10]
0x140021080  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140021086  mov     eax, ebx
0x140021088  lea     r11, [rsp+60h+var_s0]
0x14002108d  mov     rbx, [r11+40h]
0x140021091  mov     rsi, [r11+48h]
0x140021095  mov     rsp, r11
0x140021098  pop     r14
0x14002109a  pop     r13
0x14002109c  pop     r12
0x14002109e  pop     rdi
0x14002109f  pop     rbp
0x1400210a0  retn
```
