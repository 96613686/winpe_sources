# CVdsDiskLun::Online(void)

- ea: `0x140049b00`
- end: `0x140049d02`
- name: `?Online@CVdsDiskLun@@UEAAJXZ`
- size: `514`
- prototype: `__int64 __fastcall(CVdsDiskLun *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003710`
- `0x140004360`
- `0x140005630`
- `0x140025a6c`
- `0x14002e123`
- `0x140049b00`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140049cc4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140049cc4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140049b79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140049b79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049c53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049c6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049c81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049c98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049caf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049c53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049c6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049c81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049c98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049caf`
- `vdsutil!VdsTraceExW` at `0x140049c08`
- `vdsutil!VdsTraceExW` at `0x140049c44`
- `vdsutil!VdsTraceExW` at `0x140049c08`
- `vdsutil!VdsTraceExW` at `0x140049c44`
- `vdsutil!VdsTraceEx` at `0x140049b9e`
- `vdsutil!VdsTraceEx` at `0x140049be6`
- `vdsutil!VdsTraceEx` at `0x140049b9e`
- `vdsutil!VdsTraceEx` at `0x140049be6`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140049b38`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140049b38`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140049cd9`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140049cd9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVdsDiskLun::Online(CVdsDiskLun *this)
{
  signed int v2; // ebx
  int v3; // eax
  int v4; // eax
  CVdsDiskLun *v5; // rcx
  LPWSTR pwszDevicePath; // r9
  __int64 v8; // [rsp+30h] [rbp-59h] BYREF
  int v9; // [rsp+38h] [rbp-51h]
  _BYTE v10[16]; // [rsp+40h] [rbp-49h] BYREF
  struct _VDS_DISK_PROP v11; // [rsp+50h] [rbp-39h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v10, 0x5Eu, "CVdsDiskLun::Online()");
  memset_0(&v11, 0, sizeof(v11));
  v8 = 0;
  v9 = 0;
  v2 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v8);
  if ( v2 >= 0 )
  {
    EnterCriticalSection(&g_GlobalCriticalSection);
    v3 = CVdsDiskLun::ValidateDiskInterfaces((CVdsDiskLun *)((char *)this - 24));
    v2 = v3;
    if ( v3 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD, struct _VDS_DISK_PROP *))(**((_QWORD **)this + 25) + 24LL))(
             *((_QWORD *)this + 25),
             &v11);
      v2 = v4;
      if ( v4 >= 0 )
      {
        if ( v11.status == VDS_DS_ONLINE )
        {
          v2 = -2147211883;
          VdsTraceExW(96, 0, L"CVdsDiskLun::Online, 3, hr=%lX", 2147755413LL);
        }
        else
        {
          v2 = CVdsDiskLun::DoOfflineOnline(v5, &v11, 0);
          if ( v2 < 0 )
          {
            pwszDevicePath = L"UNKNOWN";
            if ( v11.pwszDevicePath )
              pwszDevicePath = v11.pwszDevicePath;
            VdsTraceExW(94, 0, L"CVdsDiskLun::Online, 4 Name=%s, hr=%lX", pwszDevicePath, v2);
          }
        }
      }
      else
      {
        VdsTraceEx(94, 0, "CVdsDiskLun::Online, 2, hr=%lX", v4);
      }
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::Online, 1, hr=%lX", v3);
      if ( v2 == -2147212283 )
        v2 = -2147212277;
    }
    if ( v11.pwszDiskAddress )
    {
      CoTaskMemFree(v11.pwszDiskAddress);
      v11.pwszDiskAddress = 0;
    }
    if ( v11.pwszFriendlyName )
    {
      CoTaskMemFree(v11.pwszFriendlyName);
      v11.pwszFriendlyName = 0;
    }
    if ( v11.pwszAdaptorName )
    {
      CoTaskMemFree(v11.pwszAdaptorName);
      v11.pwszAdaptorName = 0;
    }
    if ( v11.pwszDevicePath )
    {
      CoTaskMemFree(v11.pwszDevicePath);
      v11.pwszDevicePath = 0;
    }
    if ( v11.pwszName )
    {
      CoTaskMemFree(v11.pwszName);
      v11.pwszName = 0;
    }
    LeaveCriticalSection(&g_GlobalCriticalSection);
  }
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v8);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v10);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140049b00  mov     [rsp-8+arg_8], rbx
0x140049b05  mov     [rsp-8+arg_10], rdi
0x140049b0a  push    rbp
0x140049b0b  lea     rbp, [rsp-57h]
0x140049b10  sub     rsp, 0E0h
0x140049b17  mov     rax, cs:__security_cookie
0x140049b1e  xor     rax, rsp
0x140049b21  mov     [rbp+57h+var_8], rax
0x140049b25  mov     rdi, rcx
0x140049b28  lea     r8, aCvdsdisklunOnl_3; "CVdsDiskLun::Online()"
0x140049b2f  mov     edx, 5Eh ; '^'
0x140049b34  lea     rcx, [rbp+57h+var_A0]
0x140049b38  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140049b3e  nop
0x140049b3f  xor     edx, edx; Val
0x140049b41  mov     r8d, 80h; Size
0x140049b47  lea     rcx, [rbp+57h+var_90]; void *
0x140049b4b  call    memset_0
0x140049b50  mov     [rbp+57h+var_B0], 0
0x140049b58  mov     [rbp+57h+var_A8], 0
0x140049b5f  lea     rcx, [rbp+57h+var_B0]; this
0x140049b63  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140049b68  mov     ebx, eax
0x140049b6a  test    eax, eax
0x140049b6c  js      loc_140049CCB
0x140049b72  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140049b79  call    cs:__imp_EnterCriticalSection
0x140049b7f  nop
0x140049b80  lea     rcx, [rdi-18h]; this
0x140049b84  call    ?ValidateDiskInterfaces@CVdsDiskLun@@AEAAJXZ; CVdsDiskLun::ValidateDiskInterfaces(void)
0x140049b89  mov     ebx, eax
0x140049b8b  test    eax, eax
0x140049b8d  jns     short loc_140049BBA
0x140049b8f  mov     r9d, eax
0x140049b92  lea     r8, aCvdsdisklunOnl_1; "CVdsDiskLun::Online, 1, hr=%lX"
0x140049b99  xor     edx, edx
0x140049b9b  lea     ecx, [rdx+5Eh]
0x140049b9e  call    cs:__imp_VdsTraceEx
0x140049ba4  cmp     ebx, 80042405h
0x140049baa  jnz     loc_140049C4A
0x140049bb0  mov     ebx, 8004240Bh
0x140049bb5  jmp     loc_140049C4A
0x140049bba  mov     rcx, [rdi+0C8h]
0x140049bc1  mov     rax, [rcx]
0x140049bc4  lea     rdx, [rbp+57h+var_90]
0x140049bc8  mov     rax, [rax+18h]
0x140049bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049bd1  mov     ebx, eax
0x140049bd3  test    eax, eax
0x140049bd5  jns     short loc_140049BEE
0x140049bd7  mov     r9d, eax
0x140049bda  lea     r8, aCvdsdisklunOnl_0; "CVdsDiskLun::Online, 2, hr=%lX"
0x140049be1  xor     edx, edx
0x140049be3  lea     ecx, [rdx+5Eh]
0x140049be6  call    cs:__imp_VdsTraceEx
0x140049bec  jmp     short loc_140049C4A
0x140049bee  cmp     [rbp+57h+var_90.status], 1
0x140049bf2  jnz     short loc_140049C10
0x140049bf4  mov     ebx, 80042595h
0x140049bf9  mov     r9d, ebx
0x140049bfc  lea     r8, aCvdsdisklunOnl; "CVdsDiskLun::Online, 3, hr=%lX"
0x140049c03  xor     edx, edx
0x140049c05  lea     ecx, [rdx+60h]
0x140049c08  call    cs:__imp_VdsTraceExW
0x140049c0e  jmp     short loc_140049C4A
0x140049c10  xor     r8d, r8d; unsigned __int8
0x140049c13  lea     rdx, [rbp+57h+var_90]; struct _VDS_DISK_PROP *
0x140049c17  call    ?DoOfflineOnline@CVdsDiskLun@@AEAAJPEAU_VDS_DISK_PROP@@E@Z; CVdsDiskLun::DoOfflineOnline(_VDS_DISK_PROP *,uchar)
0x140049c1c  mov     ebx, eax
0x140049c1e  test    eax, eax
0x140049c20  jns     short loc_140049C4A
0x140049c22  lea     r9, aUnknown_0; "UNKNOWN"
0x140049c29  mov     rax, [rbp+57h+var_90.pwszDevicePath]
0x140049c2d  test    rax, rax
0x140049c30  cmovnz  r9, rax
0x140049c34  mov     [rsp+0E0h+var_C0], ebx
0x140049c38  lea     r8, aCvdsdisklunOnl_2; "CVdsDiskLun::Online, 4 Name=%s, hr=%lX"
0x140049c3f  xor     edx, edx
0x140049c41  lea     ecx, [rdx+5Eh]
0x140049c44  call    cs:__imp_VdsTraceExW
0x140049c4a  mov     rcx, [rbp+57h+var_90.pwszDiskAddress]; pv
0x140049c4e  test    rcx, rcx
0x140049c51  jz      short loc_140049C61
0x140049c53  call    cs:__imp_CoTaskMemFree
0x140049c59  mov     [rbp+57h+var_90.pwszDiskAddress], 0
0x140049c61  mov     rcx, [rbp+57h+var_90.pwszFriendlyName]; pv
0x140049c65  test    rcx, rcx
0x140049c68  jz      short loc_140049C78
0x140049c6a  call    cs:__imp_CoTaskMemFree
0x140049c70  mov     [rbp+57h+var_90.pwszFriendlyName], 0
0x140049c78  mov     rcx, [rbp+57h+var_90.pwszAdaptorName]; pv
0x140049c7c  test    rcx, rcx
0x140049c7f  jz      short loc_140049C8F
0x140049c81  call    cs:__imp_CoTaskMemFree
0x140049c87  mov     [rbp+57h+var_90.pwszAdaptorName], 0
0x140049c8f  mov     rcx, [rbp+57h+var_90.pwszDevicePath]; pv
0x140049c93  test    rcx, rcx
0x140049c96  jz      short loc_140049CA6
0x140049c98  call    cs:__imp_CoTaskMemFree
0x140049c9e  mov     [rbp+57h+var_90.pwszDevicePath], 0
0x140049ca6  mov     rcx, [rbp+57h+var_90.pwszName]; pv
0x140049caa  test    rcx, rcx
0x140049cad  jz      short loc_140049CBD
0x140049caf  call    cs:__imp_CoTaskMemFree
0x140049cb5  mov     [rbp+57h+var_90.pwszName], 0
0x140049cbd  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140049cc4  call    cs:__imp_LeaveCriticalSection
0x140049cca  nop
0x140049ccb  lea     rcx, [rbp+57h+var_B0]; this
0x140049ccf  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140049cd4  nop
0x140049cd5  lea     rcx, [rbp+57h+var_A0]
0x140049cd9  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140049cdf  mov     eax, ebx
0x140049ce1  mov     rcx, [rbp+57h+var_8]
0x140049ce5  xor     rcx, rsp; StackCookie
0x140049ce8  call    __security_check_cookie
0x140049ced  lea     r11, [rsp+0E0h+var_s0]
0x140049cf5  mov     rbx, [r11+18h]
0x140049cf9  mov     rdi, [r11+20h]
0x140049cfd  mov     rsp, r11
0x140049d00  pop     rbp
0x140049d01  retn
```
