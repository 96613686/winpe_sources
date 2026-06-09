# CVdsDiskLun::GetPartitionFileSystemProperties(unsigned __int64,_VDS_FILE_SYSTEM_PROP *)

- ea: `0x140020bb0`
- end: `0x140020d9b`
- name: `?GetPartitionFileSystemProperties@CVdsDiskLun@@UEAAJ_KPEAU_VDS_FILE_SYSTEM_PROP@@@Z`
- size: `491`
- prototype: `int(CVdsDiskLun *__hidden this, unsigned __int64, struct _VDS_FILE_SYSTEM_PROP *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140003710`
- `0x140004360`
- `0x140005630`
- `0x140020bb0`
- `0x140041d58`
- `0x1400446d8`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140020d63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140020d63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140020c41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140020c41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020d4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020d4d`
- `vdsutil!OpenDevice` at `0x140020cbd`
- `vdsutil!OpenDevice` at `0x140020cbd`
- `vdsutil!VdsTraceEx` at `0x140020c66`
- `vdsutil!VdsTraceEx` at `0x140020c66`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140020bea`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140020bea`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140020d79`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140020d79`
- `vdsutil!VdsTraceW` at `0x140020ca4`
- `vdsutil!VdsTraceW` at `0x140020cd9`
- `vdsutil!VdsTraceW` at `0x140020ca4`
- `vdsutil!VdsTraceW` at `0x140020cd9`

## string_xrefs

- `0x140020cd0`: `CVdsDiskLun::GetPartitionFileSystemProperties: failed to open device (%s), error=%lX`
- `0x140020bda`: `CVdsDiskLun::GetPartitionFileSystemProperties()`
- `0x140020c5a`: `CVdsDiskLun::GetPartitionFileSystemProperties, 1, hr=%lX`
- `0x140020c98`: `CVdsDiskLun::GetPartitionFileSystemProperties, 2, hr=%lX`
- `0x140020d12`: `CVdsDiskLun::GetPartitionFileSystemProperties, 3, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVdsDiskLun::GetPartitionFileSystemProperties(
        CVdsDiskLun *this,
        __int64 a2,
        struct _VDS_FILE_SYSTEM_PROP *a3)
{
  int v6; // ebx
  int v7; // eax
  __int64 v8; // r8
  int v9; // eax
  unsigned int v10; // eax
  int FileSystemPropertiesInternal; // eax
  HANDLE hObject; // [rsp+20h] [rbp-89h] BYREF
  __int64 v14; // [rsp+28h] [rbp-81h] BYREF
  int v15; // [rsp+30h] [rbp-79h]
  _VDS_FILE_SYSTEM_PROP v16; // [rsp+38h] [rbp-71h] BYREF
  _BYTE v17[16]; // [rsp+70h] [rbp-39h] BYREF
  wchar_t Str[44]; // [rsp+80h] [rbp-29h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v17, 0x5Eu, "CVdsDiskLun::GetPartitionFileSystemProperties()");
  hObject = 0;
  *(_OWORD *)&a3->type = 0;
  *(_OWORD *)&a3->volumeId.Data4[4] = 0;
  *(_OWORD *)&a3->ullAvailableAllocationUnits = 0;
  a3->pwszLabel = 0;
  memset(&v16, 0, sizeof(v16));
  v14 = 0;
  v15 = 0;
  v6 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v14);
  if ( v6 >= 0 )
  {
    EnterCriticalSection(&g_GlobalCriticalSection);
    v7 = CVdsDiskLun::ValidateDiskInterfaces((CVdsDiskLun *)((char *)this - 64));
    v6 = v7;
    if ( v7 >= 0 )
    {
      v9 = CVdsDiskLun::BuildOEMPartitionName((CVdsDiskLun *)((char *)this - 64), a2, v8, Str);
      v6 = v9;
      if ( v9 >= 0 )
      {
        v10 = OpenDevice(Str, 0x80000000LL, &hObject);
        v6 = v10;
        if ( v10 )
        {
          VdsTraceW(
            0,
            L"CVdsDiskLun::GetPartitionFileSystemProperties: failed to open device (%s), error=%lX",
            Str,
            v10);
          if ( v6 > 0 )
            v6 = (unsigned __int16)v6 | 0x80070000;
        }
        else
        {
          v16.volumeId = GUID_NULL;
          FileSystemPropertiesInternal = CVdsVolume::GetFileSystemPropertiesInternal(hObject, Str, &v16);
          v6 = FileSystemPropertiesInternal;
          if ( FileSystemPropertiesInternal >= 0 )
          {
            *a3 = v16;
            v6 = 0;
          }
          else
          {
            VdsTraceW(
              0,
              L"CVdsDiskLun::GetPartitionFileSystemProperties, 3, hr=%lX",
              (unsigned int)FileSystemPropertiesInternal);
          }
        }
      }
      else
      {
        VdsTraceW(0, L"CVdsDiskLun::GetPartitionFileSystemProperties, 2, hr=%lX", (unsigned int)v9);
      }
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::GetPartitionFileSystemProperties, 1, hr=%lX", v7);
      if ( v6 == -2147212283 )
        v6 = -2147212277;
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    LeaveCriticalSection(&g_GlobalCriticalSection);
  }
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v14);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v17);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140020bb0  push    rbp
0x140020bb2  push    rbx
0x140020bb3  push    rsi
0x140020bb4  push    rdi
0x140020bb5  push    r14
0x140020bb7  lea     rbp, [rsp-37h]
0x140020bbc  sub     rsp, 0E0h
0x140020bc3  mov     rax, cs:__security_cookie
0x140020bca  xor     rax, rsp
0x140020bcd  mov     [rbp+57h+var_28], rax
0x140020bd1  mov     rdi, r8
0x140020bd4  mov     r14, rdx
0x140020bd7  mov     rsi, rcx
0x140020bda  lea     r8, aCvdsdisklunGet_98; "CVdsDiskLun::GetPartitionFileSystemProp"...
0x140020be1  mov     edx, 5Eh ; '^'
0x140020be6  lea     rcx, [rbp+57h+var_90]
0x140020bea  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140020bf0  nop
0x140020bf1  mov     [rsp+100h+hObject], 0
0x140020bfa  xorps   xmm0, xmm0
0x140020bfd  xor     eax, eax
0x140020bff  movups  xmmword ptr [rdi], xmm0
0x140020c02  movups  xmmword ptr [rdi+10h], xmm0
0x140020c06  movups  xmmword ptr [rdi+20h], xmm0
0x140020c0a  mov     [rdi+30h], rax
0x140020c0e  movups  xmmword ptr [rbp+57h+var_C8.type], xmm0
0x140020c12  movups  xmmword ptr [rbp+57h+var_C8.volumeId.Data4+4], xmm0
0x140020c16  movups  xmmword ptr [rbp+57h+var_C8.ullAvailableAllocationUnits], xmm0
0x140020c1a  mov     [rbp+57h+var_C8.pwszLabel], rax
0x140020c1e  mov     [rsp+100h+var_D8], rax
0x140020c23  mov     [rbp+57h+var_D0], eax
0x140020c26  lea     rcx, [rsp+100h+var_D8]; this
0x140020c2b  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140020c30  mov     ebx, eax
0x140020c32  test    eax, eax
0x140020c34  js      loc_140020D6A
0x140020c3a  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140020c41  call    cs:__imp_EnterCriticalSection
0x140020c47  nop
0x140020c48  lea     rcx, [rsi-40h]; this
0x140020c4c  call    ?ValidateDiskInterfaces@CVdsDiskLun@@AEAAJXZ; CVdsDiskLun::ValidateDiskInterfaces(void)
0x140020c51  mov     ebx, eax
0x140020c53  test    eax, eax
0x140020c55  jns     short loc_140020C82
0x140020c57  mov     r9d, eax
0x140020c5a  lea     r8, aCvdsdisklunGet_55; "CVdsDiskLun::GetPartitionFileSystemProp"...
0x140020c61  xor     edx, edx
0x140020c63  lea     ecx, [rdx+5Eh]
0x140020c66  call    cs:__imp_VdsTraceEx
0x140020c6c  cmp     ebx, 80042405h
0x140020c72  jnz     loc_140020D3E
0x140020c78  mov     ebx, 8004240Bh
0x140020c7d  jmp     loc_140020D3E
0x140020c82  lea     r9, [rbp+57h+Str]; unsigned __int16 *
0x140020c86  mov     rdx, r14; unsigned __int64
0x140020c89  lea     rcx, [rsi-40h]; this
0x140020c8d  call    ?BuildOEMPartitionName@CVdsDiskLun@@AEAAJ_KKPEAG@Z; CVdsDiskLun::BuildOEMPartitionName(unsigned __int64,ulong,ushort *)
0x140020c92  mov     ebx, eax
0x140020c94  test    eax, eax
0x140020c96  jns     short loc_140020CAF
0x140020c98  lea     rdx, aCvdsdisklunGet_88; "CVdsDiskLun::GetPartitionFileSystemProp"...
0x140020c9f  mov     r8d, eax
0x140020ca2  xor     ecx, ecx
0x140020ca4  call    cs:__imp_VdsTraceW
0x140020caa  jmp     loc_140020D3E
0x140020caf  lea     r8, [rsp+100h+hObject]
0x140020cb4  mov     edx, 80000000h
0x140020cb9  lea     rcx, [rbp+57h+Str]
0x140020cbd  call    cs:__imp_OpenDevice
0x140020cc3  mov     ebx, eax
0x140020cc5  test    eax, eax
0x140020cc7  jz      short loc_140020CEE
0x140020cc9  mov     r9d, eax
0x140020ccc  lea     r8, [rbp+57h+Str]
0x140020cd0  lea     rdx, aCvdsdisklunGet_141; "CVdsDiskLun::GetPartitionFileSystemProp"...
0x140020cd7  xor     ecx, ecx
0x140020cd9  call    cs:__imp_VdsTraceW
0x140020cdf  test    ebx, ebx
0x140020ce1  jle     short loc_140020D3E
0x140020ce3  movzx   ebx, bx
0x140020ce6  or      ebx, 80070000h
0x140020cec  jmp     short loc_140020D3E
0x140020cee  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140020cf5  movdqu  xmmword ptr [rbp+57h+var_C8.volumeId.Data1], xmm0
0x140020cfa  lea     r8, [rbp+57h+var_C8]; struct _VDS_FILE_SYSTEM_PROP *
0x140020cfe  lea     rdx, [rbp+57h+Str]; Str
0x140020d02  mov     rcx, [rsp+100h+hObject]; FileHandle
0x140020d07  call    ?GetFileSystemPropertiesInternal@CVdsVolume@@SAJPEAXPEAGPEAU_VDS_FILE_SYSTEM_PROP@@@Z; CVdsVolume::GetFileSystemPropertiesInternal(void *,ushort *,_VDS_FILE_SYSTEM_PROP *)
0x140020d0c  mov     ebx, eax
0x140020d0e  test    eax, eax
0x140020d10  jns     short loc_140020D1B
0x140020d12  lea     rdx, aCvdsdisklunGet_101; "CVdsDiskLun::GetPartitionFileSystemProp"...
0x140020d19  jmp     short loc_140020C9F
0x140020d1b  movups  xmm0, xmmword ptr [rbp+57h+var_C8.type]
0x140020d1f  movups  xmmword ptr [rdi], xmm0
0x140020d22  movups  xmm1, xmmword ptr [rbp+57h+var_C8.volumeId.Data4+4]
0x140020d26  movups  xmmword ptr [rdi+10h], xmm1
0x140020d2a  movups  xmm0, xmmword ptr [rbp+57h+var_C8.ullAvailableAllocationUnits]
0x140020d2e  movups  xmmword ptr [rdi+20h], xmm0
0x140020d32  movsd   xmm1, [rbp+57h+var_C8.pwszLabel]
0x140020d37  movsd   qword ptr [rdi+30h], xmm1
0x140020d3c  xor     ebx, ebx
0x140020d3e  mov     rcx, [rsp+100h+hObject]; hObject
0x140020d43  lea     rax, [rcx-1]
0x140020d47  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140020d4b  ja      short loc_140020D5C
0x140020d4d  call    cs:__imp_CloseHandle
0x140020d53  mov     [rsp+100h+hObject], 0
0x140020d5c  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140020d63  call    cs:__imp_LeaveCriticalSection
0x140020d69  nop
0x140020d6a  lea     rcx, [rsp+100h+var_D8]; this
0x140020d6f  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140020d74  nop
0x140020d75  lea     rcx, [rbp+57h+var_90]
0x140020d79  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140020d7f  mov     eax, ebx
0x140020d81  mov     rcx, [rbp+57h+var_28]
0x140020d85  xor     rcx, rsp; StackCookie
0x140020d88  call    __security_check_cookie
0x140020d8d  add     rsp, 0E0h
0x140020d94  pop     r14
0x140020d96  pop     rdi
0x140020d97  pop     rsi
0x140020d98  pop     rbx
0x140020d99  pop     rbp
0x140020d9a  retn
```
