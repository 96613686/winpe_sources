# CVdsDiskLun::GetPartitionFileSystemTypeName(unsigned __int64,ushort * *)

- ea: `0x140021b50`
- end: `0x140021ce5`
- name: `?GetPartitionFileSystemTypeName@CVdsDiskLun@@UEAAJ_KPEAPEAG@Z`
- size: `405`
- prototype: `int(CVdsDiskLun *__hidden this, unsigned __int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140003710`
- `0x140004360`
- `0x140005630`
- `0x140021b50`
- `0x1400424e4`
- `0x1400446d8`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140021cae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140021cae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140021bc9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140021bc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140021c99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140021c99`
- `vdsutil!OpenDevice` at `0x140021c36`
- `vdsutil!OpenDevice` at `0x140021c36`
- `vdsutil!VdsTraceEx` at `0x140021bee`
- `vdsutil!VdsTraceEx` at `0x140021bee`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140021b8a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140021b8a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140021cc3`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140021cc3`
- `vdsutil!VdsTraceW` at `0x140021c52`
- `vdsutil!VdsTraceW` at `0x140021c85`
- `vdsutil!VdsTraceW` at `0x140021c52`
- `vdsutil!VdsTraceW` at `0x140021c85`

## string_xrefs

- `0x140021c49`: `CVdsDiskLun::GetPartitionFileSystemTypeName: failed to open device (%s), error=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVdsDiskLun::GetPartitionFileSystemTypeName(CVdsDiskLun *this, __int64 a2, unsigned __int16 **a3)
{
  int v6; // ebx
  int v7; // eax
  __int64 v8; // r8
  int v9; // eax
  unsigned int v10; // eax
  int FileSystemTypeNameInternal; // eax
  HANDLE hObject; // [rsp+20h] [rbp-59h] BYREF
  __int64 v14; // [rsp+28h] [rbp-51h] BYREF
  int v15; // [rsp+30h] [rbp-49h]
  _BYTE v16[24]; // [rsp+38h] [rbp-41h] BYREF
  unsigned __int16 v17[44]; // [rsp+50h] [rbp-29h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v16, 0x5Eu, "CVdsDiskLun::GetPartitionFileSystemTypeName()");
  hObject = 0;
  *a3 = 0;
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
      v9 = CVdsDiskLun::BuildOEMPartitionName((CVdsDiskLun *)((char *)this - 64), a2, v8, v17);
      v6 = v9;
      if ( v9 >= 0 )
      {
        v10 = OpenDevice(v17, 0x80000000LL, &hObject);
        v6 = v10;
        if ( v10 )
        {
          VdsTraceW(0, L"CVdsDiskLun::GetPartitionFileSystemTypeName: failed to open device (%s), error=%lX", v17, v10);
          if ( v6 > 0 )
            v6 = (unsigned __int16)v6 | 0x80070000;
        }
        else
        {
          FileSystemTypeNameInternal = CVdsVolume::GetFileSystemTypeNameInternal(hObject, a3);
          v6 = FileSystemTypeNameInternal;
          if ( FileSystemTypeNameInternal < 0 )
            VdsTraceW(
              0,
              L"CVdsDiskLun::GetPartitionFileSystemTypeName, 3, hr=%lX",
              (unsigned int)FileSystemTypeNameInternal);
        }
      }
      else
      {
        VdsTraceW(0, L"CVdsDiskLun::GetPartitionFileSystemTypeName, 2, hr=%lX", (unsigned int)v9);
      }
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::GetPartitionFileSystemTypeName, 1, hr=%lX", v7);
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
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v16);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140021b50  push    rbp
0x140021b52  push    rbx
0x140021b53  push    rsi
0x140021b54  push    rdi
0x140021b55  push    r14
0x140021b57  lea     rbp, [rsp-37h]
0x140021b5c  sub     rsp, 0B0h
0x140021b63  mov     rax, cs:__security_cookie
0x140021b6a  xor     rax, rsp
0x140021b6d  mov     [rbp+57h+var_28], rax
0x140021b71  mov     rsi, r8
0x140021b74  mov     r14, rdx
0x140021b77  mov     rdi, rcx
0x140021b7a  lea     r8, aCvdsdisklunGet_76; "CVdsDiskLun::GetPartitionFileSystemType"...
0x140021b81  mov     edx, 5Eh ; '^'
0x140021b86  lea     rcx, [rbp+57h+var_98]
0x140021b8a  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140021b90  nop
0x140021b91  mov     [rbp+57h+hObject], 0
0x140021b99  mov     qword ptr [rsi], 0
0x140021ba0  mov     [rbp+57h+var_A8], 0
0x140021ba8  mov     [rbp+57h+var_A0], 0
0x140021baf  lea     rcx, [rbp+57h+var_A8]; this
0x140021bb3  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140021bb8  mov     ebx, eax
0x140021bba  test    eax, eax
0x140021bbc  js      loc_140021CB5
0x140021bc2  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140021bc9  call    cs:__imp_EnterCriticalSection
0x140021bcf  nop
0x140021bd0  lea     rcx, [rdi-40h]; this
0x140021bd4  call    ?ValidateDiskInterfaces@CVdsDiskLun@@AEAAJXZ; CVdsDiskLun::ValidateDiskInterfaces(void)
0x140021bd9  mov     ebx, eax
0x140021bdb  test    eax, eax
0x140021bdd  jns     short loc_140021C0A
0x140021bdf  mov     r9d, eax
0x140021be2  lea     r8, aCvdsdisklunGet_154; "CVdsDiskLun::GetPartitionFileSystemType"...
0x140021be9  xor     edx, edx
0x140021beb  lea     ecx, [rdx+5Eh]
0x140021bee  call    cs:__imp_VdsTraceEx
0x140021bf4  cmp     ebx, 80042405h
0x140021bfa  jnz     loc_140021C8B
0x140021c00  mov     ebx, 8004240Bh
0x140021c05  jmp     loc_140021C8B
0x140021c0a  lea     r9, [rbp+57h+var_80]; unsigned __int16 *
0x140021c0e  mov     rdx, r14; unsigned __int64
0x140021c11  lea     rcx, [rdi-40h]; this
0x140021c15  call    ?BuildOEMPartitionName@CVdsDiskLun@@AEAAJ_KKPEAG@Z; CVdsDiskLun::BuildOEMPartitionName(unsigned __int64,ulong,ushort *)
0x140021c1a  mov     ebx, eax
0x140021c1c  test    eax, eax
0x140021c1e  jns     short loc_140021C29
0x140021c20  lea     rdx, aCvdsdisklunGet_130; "CVdsDiskLun::GetPartitionFileSystemType"...
0x140021c27  jmp     short loc_140021C80
0x140021c29  lea     r8, [rbp+57h+hObject]
0x140021c2d  mov     edx, 80000000h
0x140021c32  lea     rcx, [rbp+57h+var_80]
0x140021c36  call    cs:__imp_OpenDevice
0x140021c3c  mov     ebx, eax
0x140021c3e  test    eax, eax
0x140021c40  jz      short loc_140021C67
0x140021c42  mov     r9d, eax
0x140021c45  lea     r8, [rbp+57h+var_80]
0x140021c49  lea     rdx, aCvdsdisklunGet_71; "CVdsDiskLun::GetPartitionFileSystemType"...
0x140021c50  xor     ecx, ecx
0x140021c52  call    cs:__imp_VdsTraceW
0x140021c58  test    ebx, ebx
0x140021c5a  jle     short loc_140021C8B
0x140021c5c  movzx   ebx, bx
0x140021c5f  or      ebx, 80070000h
0x140021c65  jmp     short loc_140021C8B
0x140021c67  mov     rdx, rsi; unsigned __int16 **
0x140021c6a  mov     rcx, [rbp+57h+hObject]; FileHandle
0x140021c6e  call    ?GetFileSystemTypeNameInternal@CVdsVolume@@SAJPEAXPEAPEAG@Z; CVdsVolume::GetFileSystemTypeNameInternal(void *,ushort * *)
0x140021c73  mov     ebx, eax
0x140021c75  test    eax, eax
0x140021c77  jns     short loc_140021C8B
0x140021c79  lea     rdx, aCvdsdisklunGet_92; "CVdsDiskLun::GetPartitionFileSystemType"...
0x140021c80  mov     r8d, eax
0x140021c83  xor     ecx, ecx
0x140021c85  call    cs:__imp_VdsTraceW
0x140021c8b  mov     rcx, [rbp+57h+hObject]; hObject
0x140021c8f  lea     rax, [rcx-1]
0x140021c93  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140021c97  ja      short loc_140021CA7
0x140021c99  call    cs:__imp_CloseHandle
0x140021c9f  mov     [rbp+57h+hObject], 0
0x140021ca7  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140021cae  call    cs:__imp_LeaveCriticalSection
0x140021cb4  nop
0x140021cb5  lea     rcx, [rbp+57h+var_A8]; this
0x140021cb9  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140021cbe  nop
0x140021cbf  lea     rcx, [rbp+57h+var_98]
0x140021cc3  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140021cc9  mov     eax, ebx
0x140021ccb  mov     rcx, [rbp+57h+var_28]
0x140021ccf  xor     rcx, rsp; StackCookie
0x140021cd2  call    __security_check_cookie
0x140021cd7  add     rsp, 0B0h
0x140021cde  pop     r14
0x140021ce0  pop     rdi
0x140021ce1  pop     rsi
0x140021ce2  pop     rbx
0x140021ce3  pop     rbp
0x140021ce4  retn
```
