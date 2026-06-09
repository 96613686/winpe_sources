# CVdsVolume::GetFileSystemProperties(_VDS_FILE_SYSTEM_PROP *)

- ea: `0x140041b50`
- end: `0x140041d50`
- name: `?GetFileSystemProperties@CVdsVolume@@UEAAJPEAU_VDS_FILE_SYSTEM_PROP@@@Z`
- size: `512`
- prototype: `__int64 __fastcall(CVdsVolume *__hidden this, struct _VDS_FILE_SYSTEM_PROP *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140003710`
- `0x140004360`
- `0x140009990`
- `0x140015b98`
- `0x140041b50`
- `0x140041d58`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140041cf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140041cf4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140041d0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140041d0c`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140041bac`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140041bac`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140041d24`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140041d24`
- `vdsutil!VdsTraceW` at `0x140041c28`
- `vdsutil!VdsTraceW` at `0x140041c28`

## string_xrefs

- `0x140041b9e`: `CVdsVolume::GetFileSystemProperties()`
- `0x140041c1c`: `CVdsVolume::GetFileSystemProperties, 1, hr=%lX`
- `0x140041c86`: `CVdsVolume::GetFileSystemProperties, 2, hr=%lX`
- `0x140041cb5`: `CVdsVolume::GetFileSystemProperties, 3, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsVolume::GetFileSystemProperties(CVdsVolume *this, struct _VDS_FILE_SYSTEM_PROP *a2)
{
  __int64 v4; // rdx
  signed int v5; // ebx
  int v6; // eax
  int FileSystemPropertiesInternal; // eax
  int FsFlags; // eax
  unsigned int v10; // [rsp+20h] [rbp-69h] BYREF
  HANDLE hObject; // [rsp+28h] [rbp-61h] BYREF
  __int64 v12; // [rsp+30h] [rbp-59h] BYREF
  int v13; // [rsp+38h] [rbp-51h]
  struct _VDS_FILE_SYSTEM_PROP v14; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v15[16]; // [rsp+78h] [rbp-11h] BYREF
  struct _VDS_VOLUME_PROP v16; // [rsp+88h] [rbp-1h] BYREF

  hObject = 0;
  memset(&v16, 0, sizeof(v16));
  v10 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v15, 0x5Eu, "CVdsVolume::GetFileSystemProperties()");
  *(_OWORD *)&a2->type = 0;
  *(_OWORD *)&a2->volumeId.Data4[4] = 0;
  *(_OWORD *)&a2->ullAvailableAllocationUnits = 0;
  a2->pwszLabel = 0;
  memset(&v16, 0, sizeof(v16));
  memset(&v14, 0, sizeof(v14));
  v12 = 0;
  v13 = 0;
  v5 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v12);
  if ( v5 < 0 )
    goto LABEL_20;
  v6 = CVdsVolume::OpenHandle((CVdsVolume *)((char *)this - 24), v4, &hObject, &v16);
  v5 = v6;
  if ( v6 < 0 )
  {
    VdsTraceW(0, L"CVdsVolume::GetFileSystemProperties, 1, hr=%lX", (unsigned int)v6);
    goto LABEL_16;
  }
  v14.volumeId = v16.id;
  if ( !v16.ullSize )
  {
    v14.type = VDS_FST_UNKNOWN;
    memset(&v14.ullTotalAllocationUnits, 0, 20);
    *(_OWORD *)&a2->type = *(_OWORD *)&v14.type;
    *(_OWORD *)&a2->volumeId.Data4[4] = *(_OWORD *)&v14.volumeId.Data4[4];
    *(_OWORD *)&a2->ullAvailableAllocationUnits = *(_OWORD *)&v14.ullAvailableAllocationUnits;
    a2->pwszLabel = 0;
LABEL_15:
    v5 = 0;
    goto LABEL_16;
  }
  FileSystemPropertiesInternal = CVdsVolume::GetFileSystemPropertiesInternal(hObject, v16.pwszName, &v14);
  v5 = FileSystemPropertiesInternal;
  if ( FileSystemPropertiesInternal >= 0 )
  {
    if ( (v16.ulFlags & 0x10) == 0 && ((v14.type - 4) & 0xFFFFFFFB) == 0 )
    {
      FsFlags = CVdsVolume::GetFsFlags((CVdsVolume *)((char *)this - 24), &v10);
      v5 = FsFlags;
      if ( FsFlags < 0 )
      {
        VdsTraceW(0, L"CVdsVolume::GetFileSystemProperties, 3, hr=%lX", (unsigned int)FsFlags);
        goto LABEL_16;
      }
      v14.ulFlags = v10;
    }
    *a2 = v14;
    goto LABEL_15;
  }
  VdsTraceW(0, L"CVdsVolume::GetFileSystemProperties, 2, hr=%lX", (unsigned int)FileSystemPropertiesInternal);
LABEL_16:
  if ( v16.pwszName )
  {
    CoTaskMemFree(v16.pwszName);
    v16.pwszName = 0;
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
LABEL_20:
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v12);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140041b50  mov     [rsp-8+arg_10], rbx
0x140041b55  mov     [rsp-8+arg_18], rsi
0x140041b5a  push    rbp
0x140041b5b  push    rdi
0x140041b5c  push    r14
0x140041b5e  lea     rbp, [rsp-47h]
0x140041b63  sub     rsp, 0D0h
0x140041b6a  mov     rax, cs:__security_cookie
0x140041b71  xor     rax, rsp
0x140041b74  mov     [rbp+57h+var_20], rax
0x140041b78  mov     rdi, rdx
0x140041b7b  mov     rsi, rcx
0x140041b7e  xor     r14d, r14d
0x140041b81  mov     [rbp+57h+hObject], r14
0x140041b85  xorps   xmm0, xmm0
0x140041b88  xor     eax, eax
0x140041b8a  movups  xmmword ptr [rbp+57h+var_58.id.Data1], xmm0
0x140041b8e  movups  xmmword ptr [rbp+57h+var_58.type], xmm0
0x140041b92  movups  xmmword ptr [rbp+57h+var_58.ullSize], xmm0
0x140041b96  mov     [rbp+57h+var_58.pwszName], rax
0x140041b9a  mov     [rbp+57h+var_C0], r14d
0x140041b9e  lea     r8, aCvdsvolumeGetf_8; "CVdsVolume::GetFileSystemProperties()"
0x140041ba5  lea     edx, [rax+5Eh]
0x140041ba8  lea     rcx, [rbp+57h+var_68]
0x140041bac  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140041bb2  nop
0x140041bb3  xorps   xmm0, xmm0
0x140041bb6  xor     eax, eax
0x140041bb8  movups  xmmword ptr [rdi], xmm0
0x140041bbb  movups  xmmword ptr [rdi+10h], xmm0
0x140041bbf  movups  xmmword ptr [rdi+20h], xmm0
0x140041bc3  mov     [rdi+30h], rax
0x140041bc7  movups  xmmword ptr [rbp+57h+var_58.id.Data1], xmm0
0x140041bcb  movups  xmmword ptr [rbp+57h+var_58.type], xmm0
0x140041bcf  movups  xmmword ptr [rbp+57h+var_58.ullSize], xmm0
0x140041bd3  mov     [rbp+57h+var_58.pwszName], rax
0x140041bd7  xorps   xmm1, xmm1
0x140041bda  movups  xmmword ptr [rbp+57h+var_A0.type], xmm1
0x140041bde  movups  xmmword ptr [rbp+57h+var_A0.volumeId.Data4+4], xmm1
0x140041be2  movups  xmmword ptr [rbp+57h+var_A0.ullAvailableAllocationUnits], xmm1
0x140041be6  mov     [rbp+57h+var_A0.pwszLabel], rax
0x140041bea  mov     [rbp+57h+var_B0], r14
0x140041bee  mov     [rbp+57h+var_A8], r14d
0x140041bf2  lea     rcx, [rbp+57h+var_B0]; this
0x140041bf6  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140041bfb  mov     ebx, eax
0x140041bfd  test    eax, eax
0x140041bff  js      loc_140041D16
0x140041c05  lea     r9, [rbp+57h+var_58]; struct _VDS_VOLUME_PROP *
0x140041c09  lea     r8, [rbp+57h+hObject]; void **
0x140041c0d  lea     rcx, [rsi-18h]; this
0x140041c11  call    ?OpenHandle@CVdsVolume@@QEAAJKPEAPEAXPEAU_VDS_VOLUME_PROP@@@Z; CVdsVolume::OpenHandle(ulong,void * *,_VDS_VOLUME_PROP *)
0x140041c16  mov     ebx, eax
0x140041c18  test    eax, eax
0x140041c1a  jns     short loc_140041C33
0x140041c1c  lea     rdx, aCvdsvolumeGetf_21; "CVdsVolume::GetFileSystemProperties, 1,"...
0x140041c23  mov     r8d, eax
0x140041c26  xor     ecx, ecx
0x140041c28  call    cs:__imp_VdsTraceW
0x140041c2e  jmp     loc_140041CEB
0x140041c33  movups  xmm0, xmmword ptr [rbp+57h+var_58.id.Data1]
0x140041c37  movdqu  xmmword ptr [rbp+57h+var_A0.volumeId.Data1], xmm0
0x140041c3c  cmp     [rbp+57h+var_58.ullSize], r14
0x140041c40  jnz     short loc_140041C6F
0x140041c42  mov     [rbp+57h+var_A0.type], r14d
0x140041c46  mov     [rbp+57h+var_A0.ulAllocationUnitSize], r14d
0x140041c4a  mov     [rbp+57h+var_A0.ullTotalAllocationUnits], r14
0x140041c4e  mov     [rbp+57h+var_A0.ullAvailableAllocationUnits], r14
0x140041c52  movups  xmm0, xmmword ptr [rbp+57h+var_A0.type]
0x140041c56  movups  xmmword ptr [rdi], xmm0
0x140041c59  movups  xmm1, xmmword ptr [rbp+57h+var_A0.volumeId.Data4+4]
0x140041c5d  movups  xmmword ptr [rdi+10h], xmm1
0x140041c61  movups  xmm0, xmmword ptr [rbp+57h+var_A0.ullAvailableAllocationUnits]
0x140041c65  movups  xmmword ptr [rdi+20h], xmm0
0x140041c69  mov     [rdi+30h], r14
0x140041c6d  jmp     short loc_140041CE8
0x140041c6f  lea     r8, [rbp+57h+var_A0]; struct _VDS_FILE_SYSTEM_PROP *
0x140041c73  mov     rdx, [rbp+57h+var_58.pwszName]; Str
0x140041c77  mov     rcx, [rbp+57h+hObject]; FileHandle
0x140041c7b  call    ?GetFileSystemPropertiesInternal@CVdsVolume@@SAJPEAXPEAGPEAU_VDS_FILE_SYSTEM_PROP@@@Z; CVdsVolume::GetFileSystemPropertiesInternal(void *,ushort *,_VDS_FILE_SYSTEM_PROP *)
0x140041c80  mov     ebx, eax
0x140041c82  test    eax, eax
0x140041c84  jns     short loc_140041C8F
0x140041c86  lea     rdx, aCvdsvolumeGetf_18; "CVdsVolume::GetFileSystemProperties, 2,"...
0x140041c8d  jmp     short loc_140041C23
0x140041c8f  test    byte ptr [rbp+57h+var_58.ulFlags], 10h
0x140041c93  jnz     short loc_140041CC7
0x140041c95  mov     eax, [rbp+57h+var_A0.type]
0x140041c98  add     eax, 0FFFFFFFCh
0x140041c9b  test    eax, 0FFFFFFFBh
0x140041ca0  jnz     short loc_140041CC7
0x140041ca2  lea     rdx, [rbp+57h+var_C0]; unsigned int *
0x140041ca6  lea     rcx, [rsi-18h]; this
0x140041caa  call    ?GetFsFlags@CVdsVolume@@AEAAJPEAK@Z; CVdsVolume::GetFsFlags(ulong *)
0x140041caf  mov     ebx, eax
0x140041cb1  test    eax, eax
0x140041cb3  jns     short loc_140041CC1
0x140041cb5  lea     rdx, aCvdsvolumeGetf_29; "CVdsVolume::GetFileSystemProperties, 3,"...
0x140041cbc  jmp     loc_140041C23
0x140041cc1  mov     eax, [rbp+57h+var_C0]
0x140041cc4  mov     [rbp+57h+var_A0.ulFlags], eax
0x140041cc7  movups  xmm0, xmmword ptr [rbp+57h+var_A0.type]
0x140041ccb  movups  xmmword ptr [rdi], xmm0
0x140041cce  movups  xmm1, xmmword ptr [rbp+57h+var_A0.volumeId.Data4+4]
0x140041cd2  movups  xmmword ptr [rdi+10h], xmm1
0x140041cd6  movups  xmm0, xmmword ptr [rbp+57h+var_A0.ullAvailableAllocationUnits]
0x140041cda  movups  xmmword ptr [rdi+20h], xmm0
0x140041cde  movsd   xmm1, [rbp+57h+var_A0.pwszLabel]
0x140041ce3  movsd   qword ptr [rdi+30h], xmm1
0x140041ce8  mov     ebx, r14d
0x140041ceb  mov     rcx, [rbp+57h+var_58.pwszName]; pv
0x140041cef  test    rcx, rcx
0x140041cf2  jz      short loc_140041CFE
0x140041cf4  call    cs:__imp_CoTaskMemFree
0x140041cfa  mov     [rbp+57h+var_58.pwszName], r14
0x140041cfe  mov     rcx, [rbp+57h+hObject]; hObject
0x140041d02  lea     rax, [rcx-1]
0x140041d06  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140041d0a  ja      short loc_140041D16
0x140041d0c  call    cs:__imp_CloseHandle
0x140041d12  mov     [rbp+57h+hObject], r14
0x140041d16  lea     rcx, [rbp+57h+var_B0]; this
0x140041d1a  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140041d1f  nop
0x140041d20  lea     rcx, [rbp+57h+var_68]
0x140041d24  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140041d2a  mov     eax, ebx
0x140041d2c  mov     rcx, [rbp+57h+var_20]
0x140041d30  xor     rcx, rsp; StackCookie
0x140041d33  call    __security_check_cookie
0x140041d38  lea     r11, [rsp+0E0h+var_10]
0x140041d40  mov     rbx, [r11+30h]
0x140041d44  mov     rsi, [r11+38h]
0x140041d48  mov     rsp, r11
0x140041d4b  pop     r14
0x140041d4d  pop     rdi
0x140041d4e  pop     rbp
0x140041d4f  retn
```
