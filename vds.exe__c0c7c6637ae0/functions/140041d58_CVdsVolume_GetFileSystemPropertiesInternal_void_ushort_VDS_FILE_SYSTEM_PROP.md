# CVdsVolume::GetFileSystemPropertiesInternal(void *,ushort *,_VDS_FILE_SYSTEM_PROP *)

- ea: `0x140041d58`
- end: `0x140042225`
- name: `?GetFileSystemPropertiesInternal@CVdsVolume@@SAJPEAXPEAGPEAU_VDS_FILE_SYSTEM_PROP@@@Z`
- size: `1229`
- prototype: `__int64 __fastcall(HANDLE FileHandle, wchar_t *Str, struct _VDS_FILE_SYSTEM_PROP *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140020bb0`
- `0x140041b50`

## callees

- `0x140003710`
- `0x140004360`
- `0x140013298`
- `0x14002e123`
- `0x14003cd8c`
- `0x140041d58`
- `0x1400514b8`
- `0x140052e80`

## import_xrefs

- `msvcrt!wcsstr` at `0x140041e03`
- `msvcrt!wcsstr` at `0x140041e03`
- `msvcrt!_wcsnicmp` at `0x140041ea1`
- `msvcrt!_wcsnicmp` at `0x140041ecb`
- `msvcrt!_wcsnicmp` at `0x140041f45`
- `msvcrt!_wcsnicmp` at `0x140041f9e`
- `msvcrt!_wcsnicmp` at `0x140041fc6`
- `msvcrt!_wcsnicmp` at `0x140041fee`
- `msvcrt!_wcsnicmp` at `0x140042015`
- `msvcrt!_wcsnicmp` at `0x14004203e`
- `msvcrt!_wcsnicmp` at `0x140042066`
- `msvcrt!_wcsnicmp` at `0x140042090`
- `msvcrt!_wcsnicmp` at `0x140041ea1`
- `msvcrt!_wcsnicmp` at `0x140041ecb`
- `msvcrt!_wcsnicmp` at `0x140041f45`
- `msvcrt!_wcsnicmp` at `0x140041f9e`
- `msvcrt!_wcsnicmp` at `0x140041fc6`
- `msvcrt!_wcsnicmp` at `0x140041fee`
- `msvcrt!_wcsnicmp` at `0x140042015`
- `msvcrt!_wcsnicmp` at `0x14004203e`
- `msvcrt!_wcsnicmp` at `0x140042066`
- `msvcrt!_wcsnicmp` at `0x140042090`
- `ntdll!NtQueryVolumeInformationFile` at `0x140041e3a`
- `ntdll!NtQueryVolumeInformationFile` at `0x140041ef6`
- `ntdll!NtQueryVolumeInformationFile` at `0x140042113`
- `ntdll!NtQueryVolumeInformationFile` at `0x140041e3a`
- `ntdll!NtQueryVolumeInformationFile` at `0x140041ef6`
- `ntdll!NtQueryVolumeInformationFile` at `0x140042113`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14004215d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14004215d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400421d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400421d3`
- `vdsutil!GetFileSystemRecognitionName` at `0x140041f57`
- `vdsutil!GetFileSystemRecognitionName` at `0x140041f57`
- `vdsutil!VdsHeapFree` at `0x1400421e1`
- `vdsutil!VdsHeapFree` at `0x1400421e1`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140041dc8`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140041dc8`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400421ff`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400421ff`
- `vdsutil!VdsTraceW` at `0x140041e52`
- `vdsutil!VdsTraceW` at `0x140041f21`
- `vdsutil!VdsTraceW` at `0x140041f72`
- `vdsutil!VdsTraceW` at `0x1400420b2`
- `vdsutil!VdsTraceW` at `0x14004212b`
- `vdsutil!VdsTraceW` at `0x14004217d`
- `vdsutil!VdsTraceW` at `0x140041e52`
- `vdsutil!VdsTraceW` at `0x140041f21`
- `vdsutil!VdsTraceW` at `0x140041f72`
- `vdsutil!VdsTraceW` at `0x1400420b2`
- `vdsutil!VdsTraceW` at `0x14004212b`
- `vdsutil!VdsTraceW` at `0x14004217d`

## string_xrefs

- `0x140041dba`: `CVdsVolume::GetFileSystemPropertiesInternal()`
- `0x140041e49`: `CVdsVolume::GetFileSystemPropertiesInternal, 1, status=%lX`
- `0x140041f66`: `CVdsVolume::GetFileSystemPropertiesInternal, 1b, file system name=%s`
- `0x140041f15`: `CVdsVolume::GetFileSystemPropertiesInternal, 2, status=%lX`
- `0x1400420a9`: `CVdsVolume::GetFileSystemPropertiesInternal, 3, status=%lX`
- `0x140042122`: `CVdsVolume::GetFileSystemPropertiesInternal, 4, status=%lX`
- `0x140042174`: `CVdsVolume::GetFileSystemPropertiesInternal, 5, hr=%lX`
- `0x1400421bb`: `CVdsVolume::GetFileSystemPropertiesInternal, 6, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsVolume::GetFileSystemPropertiesInternal(
        HANDLE FileHandle,
        wchar_t *Str,
        struct _VDS_FILE_SYSTEM_PROP *a3)
{
  char v6; // r14
  signed int v7; // edi
  unsigned int v8; // eax
  unsigned int v9; // edi
  VDS_FILE_SYSTEM_TYPE v10; // ebx
  int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  SIZE_T v14; // rbx
  WCHAR *v15; // rax
  int v16; // eax
  __int64 v17; // rbx
  HANDLE ProcessHeap; // rax
  _BYTE v20[8]; // [rsp+30h] [rbp-99h] BYREF
  __int64 v21; // [rsp+38h] [rbp-91h] BYREF
  __int64 v22; // [rsp+40h] [rbp-89h] BYREF
  int v23; // [rsp+48h] [rbp-81h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-79h] BYREF
  _BYTE v25[16]; // [rsp+60h] [rbp-69h] BYREF
  _BYTE FsInformation[8]; // [rsp+70h] [rbp-59h] BYREF
  int v27; // [rsp+78h] [rbp-51h]
  wchar_t String1[2]; // [rsp+7Ch] [rbp-4Dh] BYREF
  unsigned __int16 v29[39]; // [rsp+82h] [rbp-47h] BYREF
  __int128 v30; // [rsp+D0h] [rbp+7h] BYREF
  __int64 v31; // [rsp+E0h] [rbp+17h]

  IoStatusBlock = 0;
  v6 = 0;
  v20[0] = 0;
  v21 = 0;
  memset_0(FsInformation, 0, 0x58u);
  v30 = 0;
  v31 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v25, 0x5Eu, "CVdsVolume::GetFileSystemPropertiesInternal()");
  v22 = 0;
  v23 = 0;
  v7 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v22);
  if ( v7 >= 0 )
  {
    if ( Str && !wcsstr(Str, L"CdRom") )
    {
      FveDetectVolume(Str, v20);
      v6 = v20[0];
    }
    v8 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, FsInformation, 0x58u, FileFsAttributeInformation);
    v9 = v8;
    if ( v8 )
    {
      VdsTraceW(0, L"CVdsVolume::GetFileSystemPropertiesInternal, 1, status=%lX", v8);
      VdsLogError(0xC2000001, 0, 0, v9, 0x20A0006u, 0);
LABEL_7:
      v7 = v9 | 0x10000000;
LABEL_64:
      v17 = v21;
      ProcessHeap = GetProcessHeap();
      VdsHeapFree(ProcessHeap, 0, v17);
      v21 = 0;
      goto LABEL_65;
    }
    v10 = VDS_FST_NTFS;
    v11 = v27;
    if ( v27 == 8 )
    {
      if ( !_wcsnicmp(String1, L"NTFS", 4u) )
        goto LABEL_15;
      v11 = v27;
    }
    if ( v6 )
    {
      if ( v11 != 6 )
        goto LABEL_27;
      if ( !_wcsnicmp(String1, L"RAW", 3u) )
      {
LABEL_14:
        v10 = VDS_FST_UNKNOWN;
        goto LABEL_15;
      }
    }
    else
    {
      if ( v11 != 6 )
        goto LABEL_27;
      if ( !_wcsnicmp(String1, L"RAW", 3u) )
      {
        if ( (int)GetFileSystemRecognitionName(FileHandle, &v21) >= 0 )
        {
          VdsTraceW(2, L"CVdsVolume::GetFileSystemPropertiesInternal, 1b, file system name=%s", v21);
          goto LABEL_14;
        }
        v10 = VDS_FST_RAW;
        goto LABEL_15;
      }
    }
    v11 = v27;
    if ( v27 == 6 )
    {
      if ( !_wcsnicmp(String1, L"FAT", 3u) )
      {
        v10 = VDS_FST_FAT;
        goto LABEL_15;
      }
      v11 = v27;
    }
LABEL_27:
    if ( v11 == 10 )
    {
      if ( !_wcsnicmp(String1, L"FAT32", 5u) )
      {
        v10 = VDS_FST_FAT32;
        goto LABEL_15;
      }
      v11 = v27;
      if ( v27 == 10 )
      {
        if ( !_wcsnicmp(String1, L"EXFAT", 5u) )
        {
          v10 = VDS_FST_EXFAT;
          goto LABEL_15;
        }
        v11 = v27;
      }
    }
    if ( v11 == 8 )
    {
      if ( !_wcsnicmp(String1, L"CDFS", 4u) )
      {
        v10 = VDS_FST_CDFS;
        goto LABEL_15;
      }
      v11 = v27;
    }
    if ( v11 == 6 )
    {
      if ( !_wcsnicmp(String1, L"UDF", 3u) )
      {
        v10 = VDS_FST_UDF;
        goto LABEL_15;
      }
      v11 = v27;
    }
    if ( v11 == 10 )
    {
      if ( !_wcsnicmp(String1, L"CSVFS", 5u) )
      {
        v10 = VDS_FST_CSVFS;
        goto LABEL_15;
      }
      v11 = v27;
    }
    if ( v11 != 8 || _wcsnicmp(String1, L"ReFS", 4u) )
      goto LABEL_14;
    v10 = VDS_FST_REFS;
LABEL_15:
    a3->type = v10;
    v12 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &v30, 0x18u, FileFsSizeInformation);
    v9 = v12;
    if ( v12 )
    {
      if ( v12 == -2147483632 )
      {
        VdsTraceW(1, L"CVdsVolume::GetFileSystemPropertiesInternal, 2, status=%lX");
        v7 = -2147212227;
        goto LABEL_64;
      }
      VdsTraceW(0, L"CVdsVolume::GetFileSystemPropertiesInternal, 3, status=%lX", v12);
      if ( v9 != -1073741801 )
      {
        VdsLogError(0xC2000001, 0, 0, v9, 0x20A0007u, 0);
        goto LABEL_7;
      }
    }
    else
    {
      a3->ulAllocationUnitSize = v31 * HIDWORD(v31);
      *(_OWORD *)&a3->ullTotalAllocationUnits = v30;
      v13 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, FsInformation, 0x58u, FileFsVolumeInformation);
      v9 = v13;
      if ( !v13 )
      {
        if ( *(_DWORD *)String1 )
        {
          v14 = (unsigned int)(*(_DWORD *)String1 + 2);
          v15 = (WCHAR *)CoTaskMemAlloc(v14);
          a3->pwszLabel = v15;
          if ( !v15 )
          {
            v7 = -2147024882;
            VdsTraceW(0, L"CVdsVolume::GetFileSystemPropertiesInternal, 5, hr=%lX", 2147942414LL);
            goto LABEL_64;
          }
          memset_0(v15, 0, v14);
          if ( *(_DWORD *)String1 >= 2u )
          {
            v16 = StringCchCopyNW(a3->pwszLabel, v14 >> 1, v29, (unsigned __int64)*(unsigned int *)String1 >> 1);
            v7 = v16;
            if ( v16 < 0 )
            {
              VdsTraceW(0, L"CVdsVolume::GetFileSystemPropertiesInternal, 6, hr=%lX", (unsigned int)v16);
              goto LABEL_64;
            }
          }
        }
        else
        {
          a3->pwszLabel = 0;
        }
        v7 = 0;
        goto LABEL_64;
      }
      VdsTraceW(0, L"CVdsVolume::GetFileSystemPropertiesInternal, 4, status=%lX", v13);
      if ( v9 != -1073741801 )
      {
        VdsLogError(0xC2000001, 0, 0, v9, 0x20A0008u, 0);
        goto LABEL_7;
      }
    }
    v7 = -2147024882;
    goto LABEL_64;
  }
LABEL_65:
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v22);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v25);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140041d58  push    rbp
0x140041d5a  push    rbx
0x140041d5b  push    rsi
0x140041d5c  push    rdi
0x140041d5d  push    r13
0x140041d5f  push    r14
0x140041d61  push    r15
0x140041d63  lea     rbp, [rsp-27h]
0x140041d68  sub     rsp, 0F0h
0x140041d6f  mov     rax, cs:__security_cookie
0x140041d76  xor     rax, rsp
0x140041d79  mov     [rbp+57h+var_38], rax
0x140041d7d  mov     rsi, r8
0x140041d80  mov     rbx, rdx
0x140041d83  mov     r15, rcx
0x140041d86  xorps   xmm0, xmm0
0x140041d89  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140041d8d  xor     r14b, r14b
0x140041d90  mov     [rsp+120h+var_F0], r14b
0x140041d95  mov     [rsp+120h+var_E8], 0
0x140041d9e  xor     edx, edx; Val
0x140041da0  lea     r8d, [rdx+58h]; Size
0x140041da4  lea     rcx, [rbp+57h+FsInformation]; void *
0x140041da8  call    memset_0
0x140041dad  xorps   xmm0, xmm0
0x140041db0  xor     eax, eax
0x140041db2  movups  [rbp+57h+var_50], xmm0
0x140041db6  mov     [rbp+57h+var_40], rax
0x140041dba  lea     r8, aCvdsvolumeGetf_13; "CVdsVolume::GetFileSystemPropertiesInte"...
0x140041dc1  lea     edx, [rax+5Eh]
0x140041dc4  lea     rcx, [rbp+57h+var_C0]
0x140041dc8  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140041dce  nop
0x140041dcf  mov     [rsp+120h+var_E0], 0
0x140041dd8  mov     [rsp+120h+var_D8], 0
0x140041de0  lea     rcx, [rsp+120h+var_E0]; this
0x140041de5  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140041dea  mov     edi, eax
0x140041dec  test    eax, eax
0x140041dee  js      loc_1400421F0
0x140041df4  test    rbx, rbx
0x140041df7  jz      short loc_140041E20
0x140041df9  lea     rdx, aCdrom; "CdRom"
0x140041e00  mov     rcx, rbx; Str
0x140041e03  call    cs:__imp_wcsstr
0x140041e09  test    rax, rax
0x140041e0c  jnz     short loc_140041E20
0x140041e0e  lea     rdx, [rsp+120h+var_F0]
0x140041e13  mov     rcx, rbx
0x140041e16  call    FveDetectVolume
0x140041e1b  mov     r14b, [rsp+120h+var_F0]
0x140041e20  mov     r13d, 5
0x140041e26  mov     [rsp+120h+FsInformationClass], r13d; FsInformationClass
0x140041e2b  lea     r9d, [r13+53h]; Length
0x140041e2f  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x140041e33  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140041e37  mov     rcx, r15; FileHandle
0x140041e3a  call    cs:__imp_NtQueryVolumeInformationFile
0x140041e40  mov     edi, eax
0x140041e42  test    eax, eax
0x140041e44  jz      short loc_140041E84
0x140041e46  mov     r8d, eax
0x140041e49  lea     rdx, aCvdsvolumeGetf_16; "CVdsVolume::GetFileSystemPropertiesInte"...
0x140041e50  xor     ecx, ecx
0x140041e52  call    cs:__imp_VdsTraceW
0x140041e58  mov     [rsp+120h+var_F8], 0; unsigned __int16 *
0x140041e61  mov     [rsp+120h+FsInformationClass], 20A0006h; unsigned int
0x140041e69  mov     r9d, edi; unsigned int
0x140041e6c  xor     r8d, r8d; void *
0x140041e6f  xor     edx, edx; unsigned int
0x140041e71  mov     ecx, 0C2000001h; unsigned int
0x140041e76  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x140041e7b  bts     edi, 1Ch
0x140041e7f  jmp     loc_1400421CE
0x140041e84  mov     ebx, 4
0x140041e89  mov     eax, [rbp+57h+var_A8]
0x140041e8c  lea     edi, [rbx+4]
0x140041e8f  cmp     eax, edi
0x140041e91  jnz     short loc_140041EAE
0x140041e93  mov     r8d, ebx; MaxCount
0x140041e96  lea     rdx, aNtfs; "NTFS"
0x140041e9d  lea     rcx, [rbp+57h+String1]; String1
0x140041ea1  call    cs:__imp__wcsnicmp
0x140041ea7  test    eax, eax
0x140041ea9  jz      short loc_140041EDB
0x140041eab  mov     eax, [rbp+57h+var_A8]
0x140041eae  test    r14b, r14b
0x140041eb1  jz      short loc_140041F31
0x140041eb3  cmp     eax, 6
0x140041eb6  jnz     loc_140041FB3
0x140041ebc  lea     r8d, [rax-3]; MaxCount
0x140041ec0  lea     rdx, aRaw; "RAW"
0x140041ec7  lea     rcx, [rbp+57h+String1]; String1
0x140041ecb  call    cs:__imp__wcsnicmp
0x140041ed1  test    eax, eax
0x140041ed3  jnz     loc_140041F87
0x140041ed9  xor     ebx, ebx
0x140041edb  mov     [rsi], ebx
0x140041edd  mov     [rsp+120h+FsInformationClass], 3; FsInformationClass
0x140041ee5  mov     r9d, 18h; Length
0x140041eeb  lea     r8, [rbp+57h+var_50]; FsInformation
0x140041eef  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140041ef3  mov     rcx, r15; FileHandle
0x140041ef6  call    cs:__imp_NtQueryVolumeInformationFile
0x140041efc  mov     edi, eax
0x140041efe  test    eax, eax
0x140041f00  jz      loc_1400420E0
0x140041f06  mov     r8d, 80000010h
0x140041f0c  cmp     eax, r8d
0x140041f0f  jnz     loc_1400420A6
0x140041f15  lea     rdx, aCvdsvolumeGetf; "CVdsVolume::GetFileSystemPropertiesInte"...
0x140041f1c  mov     ecx, 1
0x140041f21  call    cs:__imp_VdsTraceW
0x140041f27  mov     edi, 8004243Dh
0x140041f2c  jmp     loc_1400421CE
0x140041f31  cmp     eax, 6
0x140041f34  jnz     short loc_140041FB3
0x140041f36  lea     r8d, [rax-3]; MaxCount
0x140041f3a  lea     rdx, aRaw; "RAW"
0x140041f41  lea     rcx, [rbp+57h+String1]; String1
0x140041f45  call    cs:__imp__wcsnicmp
0x140041f4b  test    eax, eax
0x140041f4d  jnz     short loc_140041F87
0x140041f4f  lea     rdx, [rsp+120h+var_E8]
0x140041f54  mov     rcx, r15
0x140041f57  call    cs:__imp_GetFileSystemRecognitionName
0x140041f5d  test    eax, eax
0x140041f5f  js      short loc_140041F7D
0x140041f61  mov     r8, [rsp+120h+var_E8]
0x140041f66  lea     rdx, aCvdsvolumeGetf_6; "CVdsVolume::GetFileSystemPropertiesInte"...
0x140041f6d  mov     ecx, 2
0x140041f72  call    cs:__imp_VdsTraceW
0x140041f78  jmp     loc_140041ED9
0x140041f7d  mov     ebx, 1
0x140041f82  jmp     loc_140041EDB
0x140041f87  mov     eax, [rbp+57h+var_A8]
0x140041f8a  cmp     eax, 6
0x140041f8d  jnz     short loc_140041FB3
0x140041f8f  lea     r8d, [rax-3]; MaxCount
0x140041f93  lea     rdx, aFat; "FAT"
0x140041f9a  lea     rcx, [rbp+57h+String1]; String1
0x140041f9e  call    cs:__imp__wcsnicmp
0x140041fa4  test    eax, eax
0x140041fa6  jnz     short loc_140041FB0
0x140041fa8  lea     ebx, [rax+2]
0x140041fab  jmp     loc_140041EDB
0x140041fb0  mov     eax, [rbp+57h+var_A8]
0x140041fb3  cmp     eax, 0Ah
0x140041fb6  jnz     short loc_140042003
0x140041fb8  mov     r8, r13; MaxCount
0x140041fbb  lea     rdx, aFat32; "FAT32"
0x140041fc2  lea     rcx, [rbp+57h+String1]; String1
0x140041fc6  call    cs:__imp__wcsnicmp
0x140041fcc  test    eax, eax
0x140041fce  jnz     short loc_140041FD8
0x140041fd0  lea     ebx, [rax+3]
0x140041fd3  jmp     loc_140041EDB
0x140041fd8  mov     eax, [rbp+57h+var_A8]
0x140041fdb  cmp     eax, 0Ah
0x140041fde  jnz     short loc_140042003
0x140041fe0  mov     r8, r13; MaxCount
0x140041fe3  lea     rdx, aExfat; "EXFAT"
0x140041fea  lea     rcx, [rbp+57h+String1]; String1
0x140041fee  call    cs:__imp__wcsnicmp
0x140041ff4  test    eax, eax
0x140041ff6  jnz     short loc_140042000
0x140041ff8  lea     ebx, [rax+7]
0x140041ffb  jmp     loc_140041EDB
0x140042000  mov     eax, [rbp+57h+var_A8]
0x140042003  cmp     eax, edi
0x140042005  jnz     short loc_14004202A
0x140042007  mov     r8, rbx; MaxCount
0x14004200a  lea     rdx, aCdfs; "CDFS"
0x140042011  lea     rcx, [rbp+57h+String1]; String1
0x140042015  call    cs:__imp__wcsnicmp
0x14004201b  test    eax, eax
0x14004201d  jnz     short loc_140042027
0x14004201f  mov     ebx, r13d
0x140042022  jmp     loc_140041EDB
0x140042027  mov     eax, [rbp+57h+var_A8]
0x14004202a  cmp     eax, 6
0x14004202d  jnz     short loc_140042053
0x14004202f  lea     r8d, [rax-3]; MaxCount
0x140042033  lea     rdx, aUdf; "UDF"
0x14004203a  lea     rcx, [rbp+57h+String1]; String1
0x14004203e  call    cs:__imp__wcsnicmp
0x140042044  test    eax, eax
0x140042046  jnz     short loc_140042050
0x140042048  lea     ebx, [rax+6]
0x14004204b  jmp     loc_140041EDB
0x140042050  mov     eax, [rbp+57h+var_A8]
0x140042053  cmp     eax, 0Ah
0x140042056  jnz     short loc_14004207A
0x140042058  mov     r8, r13; MaxCount
0x14004205b  lea     rdx, aCsvfs; "CSVFS"
0x140042062  lea     rcx, [rbp+57h+String1]; String1
0x140042066  call    cs:__imp__wcsnicmp
0x14004206c  test    eax, eax
0x14004206e  jnz     short loc_140042077
0x140042070  mov     ebx, edi
0x140042072  jmp     loc_140041EDB
0x140042077  mov     eax, [rbp+57h+var_A8]
0x14004207a  cmp     eax, edi
0x14004207c  jnz     loc_140041ED9
0x140042082  mov     r8, rbx; MaxCount
0x140042085  lea     rdx, aRefs_0; "ReFS"
0x14004208c  lea     rcx, [rbp+57h+String1]; String1
0x140042090  call    cs:__imp__wcsnicmp
0x140042096  test    eax, eax
0x140042098  jnz     loc_140041ED9
0x14004209e  lea     ebx, [rax+9]
0x1400420a1  jmp     loc_140041EDB
0x1400420a6  mov     r8d, edi
0x1400420a9  lea     rdx, aCvdsvolumeGetf_0; "CVdsVolume::GetFileSystemPropertiesInte"...
0x1400420b0  xor     ecx, ecx
0x1400420b2  call    cs:__imp_VdsTraceW
0x1400420b8  cmp     edi, 0C0000017h
0x1400420be  jnz     short loc_1400420CA
0x1400420c0  mov     edi, 8007000Eh
0x1400420c5  jmp     loc_1400421CE
0x1400420ca  mov     [rsp+120h+var_F8], 0
0x1400420d3  mov     [rsp+120h+FsInformationClass], 20A0007h
0x1400420db  jmp     loc_140041E69
0x1400420e0  mov     eax, dword ptr [rbp+57h+var_40+4]
0x1400420e3  imul    eax, dword ptr [rbp+57h+var_40]
0x1400420e7  mov     [rsi+28h], eax
0x1400420ea  mov     rax, qword ptr [rbp+57h+var_50]
0x1400420ee  mov     [rsi+18h], rax
0x1400420f2  mov     rax, qword ptr [rbp+57h+var_50+8]
0x1400420f6  mov     [rsi+20h], rax
0x1400420fa  mov     [rsp+120h+FsInformationClass], 1; FsInformationClass
0x140042102  mov     r9d, 58h ; 'X'; Length
0x140042108  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x14004210c  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140042110  mov     rcx, r15; FileHandle
0x140042113  call    cs:__imp_NtQueryVolumeInformationFile
0x140042119  mov     edi, eax
0x14004211b  test    eax, eax
0x14004211d  jz      short loc_14004214F
0x14004211f  mov     r8d, eax
0x140042122  lea     rdx, aCvdsvolumeGetf_19; "CVdsVolume::GetFileSystemPropertiesInte"...
0x140042129  xor     ecx, ecx
0x14004212b  call    cs:__imp_VdsTraceW
0x140042131  cmp     edi, 0C0000017h
0x140042137  jz      short loc_1400420C0
0x140042139  mov     [rsp+120h+var_F8], 0
0x140042142  mov     [rsp+120h+FsInformationClass], 20A0008h
0x14004214a  jmp     loc_140041E69
0x14004214f  mov     eax, dword ptr [rbp+57h+String1]
0x140042152  test    eax, eax
0x140042154  jz      short loc_1400421C4
0x140042156  add     eax, 2
0x140042159  mov     ebx, eax
0x14004215b  mov     ecx, eax; cb
0x14004215d  call    cs:__imp_CoTaskMemAlloc
0x140042163  mov     [rsi+30h], rax
0x140042167  test    rax, rax
0x14004216a  jnz     short loc_140042185
0x14004216c  mov     edi, 8007000Eh
0x140042171  mov     r8d, edi
0x140042174  lea     rdx, aCvdsvolumeGetf_17; "CVdsVolume::GetFileSystemPropertiesInte"...
0x14004217b  xor     ecx, ecx
0x14004217d  call    cs:__imp_VdsTraceW
0x140042183  jmp     short loc_1400421CE
0x140042185  mov     r8, rbx; Size
0x140042188  xor     edx, edx; Val
0x14004218a  mov     rcx, rax; void *
0x14004218d  call    memset_0
0x140042192  cmp     dword ptr [rbp+57h+String1], 2
0x140042196  jb      short loc_1400421CC
0x140042198  mov     r9d, dword ptr [rbp+57h+String1]
0x14004219c  shr     r9, 1; unsigned __int64
0x14004219f  shr     rbx, 1
0x1400421a2  lea     r8, [rbp+57h+var_9E]; unsigned __int16 *
0x1400421a6  mov     rdx, rbx; unsigned __int64
0x1400421a9  mov     rcx, [rsi+30h]; unsigned __int16 *
0x1400421ad  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1400421b2  mov     edi, eax
0x1400421b4  test    eax, eax
0x1400421b6  jns     short loc_1400421CC
0x1400421b8  mov     r8d, eax
0x1400421bb  lea     rdx, aCvdsvolumeGetf_11; "CVdsVolume::GetFileSystemPropertiesInte"...
0x1400421c2  jmp     short loc_14004217B
0x1400421c4  mov     qword ptr [rsi+30h], 0
0x1400421cc  xor     edi, edi
0x1400421ce  mov     rbx, [rsp+120h+var_E8]
0x1400421d3  call    cs:__imp_GetProcessHeap
0x1400421d9  mov     r8, rbx
0x1400421dc  xor     edx, edx
0x1400421de  mov     rcx, rax
0x1400421e1  call    cs:__imp_VdsHeapFree
0x1400421e7  mov     [rsp+120h+var_E8], 0
0x1400421f0  lea     rcx, [rsp+120h+var_E0]; this
0x1400421f5  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x1400421fa  nop
0x1400421fb  lea     rcx, [rbp+57h+var_C0]
0x1400421ff  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140042205  mov     eax, edi
0x140042207  mov     rcx, [rbp+57h+var_38]
0x14004220b  xor     rcx, rsp; StackCookie
  ... truncated ...
```
