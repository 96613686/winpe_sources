# HyperVFileIo::OpenInternal(ushort const *,HyperVFileOpenFlags,void * *,int *)

- ea: `0x1400e12bc`
- end: `0x1400e15bc`
- name: `?OpenInternal@HyperVFileIo@@CAJPEBGW4HyperVFileOpenFlags@@PEAPEAXPEAH@Z`
- size: `768`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400def60`
- `0x1400e0010`
- `0x1400e10a0`

## callees

- `0x1400336f0`
- `0x1400371c8`
- `0x1400e0bf4`
- `0x1400e12bc`
- `0x1400e1aec`
- `0x1401332f0`
- `0x1401363ac`
- `0x140136414`

## import_xrefs

- `ntdll!NtCreateFile` at `0x1400e145f`
- `ntdll!NtCreateFile` at `0x1400e14b6`
- `ntdll!NtCreateFile` at `0x1400e145f`
- `ntdll!NtCreateFile` at `0x1400e14b6`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1400e136c`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1400e136c`
- `ntdll!RtlNtStatusToDosError` at `0x1400e1380`
- `ntdll!RtlNtStatusToDosError` at `0x1400e1575`
- `ntdll!RtlNtStatusToDosError` at `0x1400e1380`
- `ntdll!RtlNtStatusToDosError` at `0x1400e1575`

## pseudocode

```c
signed int __fastcall HyperVFileIo::OpenInternal(__int64 a1, __int16 a2, void **a3, int *a4)
{
  ULONG ShareAccess; // ebx
  int v8; // edi
  signed int result; // eax
  ULONG CreateDisposition; // r15d
  unsigned int v11; // r14d
  NTSTATUS v12; // eax
  int v13; // eax
  bool v14; // zf
  int IsDebugTraceEnabled; // ebx
  unsigned __int64 v16; // rdx
  unsigned __int8 v17; // cl
  bool IsEnabled; // al
  char v19; // di
  unsigned int v20; // ebx
  signed int v21; // eax
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  __int128 v24; // [rsp+70h] [rbp-90h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v27; // [rsp+C0h] [rbp-40h] BYREF
  int v28; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v29; // [rsp+CCh] [rbp-34h]
  _DWORD EaBuffer[2]; // [rsp+D8h] [rbp-28h] BYREF
  char v31[28]; // [rsp+E0h] [rbp-20h] BYREF
  int v32; // [rsp+FCh] [rbp-4h]

  *a3 = (void *)-1LL;
  FileHandle = (void *)-1LL;
  *a4 = 0;
  ShareAccess = (a2 & 8) != 0 ? 1 : 3;
  if ( (a2 & 0x40) != 0 )
  {
    if ( (a2 & 8) != 0 )
      return -2147024809;
    ShareAccess |= 4u;
  }
  v8 = 1;
  if ( (a2 & 0x20) != 0 && (a2 & 3) != 0 )
    return -2147024809;
  CreateDisposition = *((_DWORD *)qword_14032EC60 + (a2 & 3));
  v11 = (a2 & 0x20) != 0 ? 0xFFFFFEFE : 0;
  v24 = 0;
  v12 = RtlDosPathNameToRelativeNtPathName_U_WithStatus(a1, &v24, 0, 0);
  if ( v12 >= 0 )
  {
    v27 = *((_QWORD *)&v24 + 1);
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v24;
    ObjectAttributes.SecurityQualityOfService = &v28;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.SecurityDescriptor = 0;
    v29 = 0;
    v28 = 12;
    IoStatusBlock = 0;
    if ( (a2 & 0x1000) == 0
      || (EaBuffer[0] = 0,
          v31[27] = 0,
          v32 = 0,
          strcpy(v31, "SmbDisableHandleDurability"),
          EaBuffer[1] = 6656,
          v13 = NtCreateFile(
                  &FileHandle,
                  v11 + 1048963,
                  &ObjectAttributes,
                  &IoStatusBlock,
                  0,
                  0x80u,
                  ShareAccess,
                  CreateDisposition,
                  0x840u,
                  EaBuffer,
                  0x28u),
          v13 == -1073741808)
      || v13 == -1073741745 )
    {
      v13 = NtCreateFile(
              &FileHandle,
              v11 + 1048963,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              0x80u,
              ShareAccess,
              CreateDisposition,
              0x840u,
              0,
              0);
    }
    if ( v13 < 0 )
    {
      v21 = RtlNtStatusToDosError(v13);
      v20 = v21;
      if ( v21 > 0 )
        v20 = (unsigned __int16)v21 | 0x80070000;
    }
    else
    {
      v14 = (IoStatusBlock.Information & 0xFFFFFFFFFFFFFFFCuLL) == 0;
      *a3 = FileHandle;
      if ( !v14 || IoStatusBlock.Information == 1 )
        v8 = 0;
      *a4 = v8;
      IsDebugTraceEnabled = HvsIsDebugTraceEnabled(0xC000u);
      IsEnabled = HyperVStorageTrace::IsEnabled(v17, v16);
      v19 = IsEnabled;
      if ( IsDebugTraceEnabled || IsEnabled )
      {
        if ( dword_1403DEA9C > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 16LL) )
        {
          Init_thread_header(&dword_1403DEA9C);
          if ( dword_1403DEA9C == -1 )
          {
            byte_1403BCB2C = IsDebugTraceEnabled != 0;
            byte_1403BCB2D = v19;
            Init_thread_footer(&dword_1403DEA9C);
          }
        }
        HvsDebugTraceInternal(0xC000u, (const struct HvsDebugTraceParameters *)&off_1403BCB18, a1);
      }
      v20 = 0;
    }
    std::unique_ptr_unsigned_short__anonymous_namespace_::RtlHeapDeleter_unsigned_short___::_unique_ptr_unsigned_short__anonymous_namespace_::RtlHeapDeleter_unsigned_short___(&v27);
    return v20;
  }
  else
  {
    result = RtlNtStatusToDosError(v12);
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1400e12bc  push    rbp
0x1400e12be  push    rbx
0x1400e12bf  push    rsi
0x1400e12c0  push    rdi
0x1400e12c1  push    r12
0x1400e12c3  push    r13
0x1400e12c5  push    r14
0x1400e12c7  push    r15
0x1400e12c9  lea     rbp, [rsp-18h]
0x1400e12ce  sub     rsp, 118h
0x1400e12d5  mov     rax, cs:__security_cookie
0x1400e12dc  xor     rax, rsp
0x1400e12df  mov     [rbp+50h+var_50], rax
0x1400e12e3  mov     r13, rcx
0x1400e12e6  mov     [rsp+150h+var_F0], r9
0x1400e12eb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400e12ef  mov     r12, r8
0x1400e12f2  mov     [r8], rcx
0x1400e12f5  mov     esi, edx
0x1400e12f7  mov     [rsp+150h+FileHandle], rcx
0x1400e12fc  mov     ecx, edx
0x1400e12fe  and     ecx, 8
0x1400e1301  mov     dword ptr [r9], 0
0x1400e1308  mov     eax, ecx
0x1400e130a  neg     eax
0x1400e130c  sbb     ebx, ebx
0x1400e130e  and     ebx, 0FFFFFFFEh
0x1400e1311  add     ebx, 3
0x1400e1314  test    dl, 40h
0x1400e1317  jz      short loc_1400E1320
0x1400e1319  test    ecx, ecx
0x1400e131b  jnz     short loc_1400E1335
0x1400e131d  or      ebx, 4
0x1400e1320  mov     eax, esi
0x1400e1322  mov     ecx, esi
0x1400e1324  and     eax, 3
0x1400e1327  mov     edi, 1
0x1400e132c  and     ecx, 20h
0x1400e132f  jz      short loc_1400E133F
0x1400e1331  cmp     eax, edi
0x1400e1333  jb      short loc_1400E133F
0x1400e1335  mov     eax, 80070057h
0x1400e133a  jmp     loc_1400E159B
0x1400e133f  neg     ecx
0x1400e1341  lea     r15, qword_14032EC60
0x1400e1348  mov     r15d, [r15+rax*4]
0x1400e134c  lea     rdx, [rsp+150h+var_E0]
0x1400e1351  sbb     r14d, r14d
0x1400e1354  xorps   xmm0, xmm0
0x1400e1357  xor     r9d, r9d
0x1400e135a  xor     r8d, r8d
0x1400e135d  mov     rcx, r13
0x1400e1360  and     r14d, 0FFFFFEFEh
0x1400e1367  movups  [rsp+150h+var_E0], xmm0
0x1400e136c  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x1400e1373  nop     dword ptr [rax+rax+00h]
0x1400e1378  xor     ecx, ecx
0x1400e137a  test    eax, eax
0x1400e137c  jns     short loc_1400E13A1
0x1400e137e  mov     ecx, eax; Status
0x1400e1380  call    cs:__imp_RtlNtStatusToDosError
0x1400e1387  nop     dword ptr [rax+rax+00h]
0x1400e138c  test    eax, eax
0x1400e138e  jle     loc_1400E159B
0x1400e1394  movzx   eax, ax
0x1400e1397  or      eax, 80070000h
0x1400e139c  jmp     loc_1400E159B
0x1400e13a1  mov     rax, qword ptr [rsp+150h+var_E0+8]
0x1400e13a6  xorps   xmm0, xmm0
0x1400e13a9  mov     [rbp+50h+var_90], rax
0x1400e13ad  lea     rax, [rsp+150h+var_E0]
0x1400e13b2  mov     [rbp+50h+ObjectAttributes.ObjectName], rax
0x1400e13b6  lea     rax, [rbp+50h+var_88]
0x1400e13ba  mov     [rbp+50h+ObjectAttributes.SecurityQualityOfService], rax
0x1400e13be  mov     qword ptr [rbp+50h+ObjectAttributes.Length], 30h ; '0'
0x1400e13c6  mov     qword ptr [rbp+50h+ObjectAttributes.Attributes], 40h ; '@'
0x1400e13ce  mov     [rbp+50h+ObjectAttributes.RootDirectory], rcx
0x1400e13d2  mov     [rbp+50h+ObjectAttributes.SecurityDescriptor], rcx
0x1400e13d6  mov     [rbp+50h+var_84], rcx
0x1400e13da  mov     [rbp+50h+var_88], 0Ch
0x1400e13e1  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x1400e13e5  bt      esi, 0Ch
0x1400e13e9  jnb     loc_1400E147B
0x1400e13ef  movups  xmm1, cs:xmmword_14032ED10+0Ah
0x1400e13f6  mov     [rsp+150h+EaLength], 28h ; '('; EaLength
0x1400e13fe  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x1400e1402  movups  xmmword ptr [rbp+50h+var_74], xmm0
0x1400e1406  xor     eax, eax
0x1400e1408  mov     [rbp+50h+var_78], ecx
0x1400e140b  movups  xmmword ptr [rbp+50h+var_74+10h], xmm0
0x1400e140f  mov     [rbp+50h+var_54], eax
0x1400e1412  lea     rax, [rbp+50h+var_78]
0x1400e1416  movups  xmm0, cs:xmmword_14032ED10
0x1400e141d  mov     [rsp+150h+EaBuffer], rax; EaBuffer
0x1400e1422  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x1400e1426  mov     [rsp+150h+CreateOptions], 840h; CreateOptions
0x1400e142e  lea     edx, [r14+100183h]; DesiredAccess
0x1400e1435  mov     [rsp+150h+CreateDisposition], r15d; CreateDisposition
0x1400e143a  mov     [rsp+150h+ShareAccess], ebx; ShareAccess
0x1400e143e  movups  xmmword ptr [rbp+50h+var_74+4], xmm0
0x1400e1442  mov     [rsp+150h+FileAttributes], 80h; FileAttributes
0x1400e144a  mov     [rsp+150h+AllocationSize], rcx; AllocationSize
0x1400e144f  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x1400e1454  mov     dword ptr [rbp+50h+var_74], 1A00h
0x1400e145b  movups  xmmword ptr [rbp+50h+var_74+0Eh], xmm1
0x1400e145f  call    cs:__imp_NtCreateFile
0x1400e1466  nop     dword ptr [rax+rax+00h]
0x1400e146b  cmp     eax, 0C0000010h
0x1400e1470  jz      short loc_1400E1479
0x1400e1472  cmp     eax, 0C000004Fh
0x1400e1477  jnz     short loc_1400E14C2
0x1400e1479  xor     ecx, ecx
0x1400e147b  mov     [rsp+150h+EaLength], ecx; EaLength
0x1400e147f  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x1400e1483  mov     [rsp+150h+EaBuffer], rcx; EaBuffer
0x1400e1488  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x1400e148c  mov     [rsp+150h+CreateOptions], 840h; CreateOptions
0x1400e1494  lea     edx, [r14+100183h]; DesiredAccess
0x1400e149b  mov     [rsp+150h+CreateDisposition], r15d; CreateDisposition
0x1400e14a0  mov     [rsp+150h+ShareAccess], ebx; ShareAccess
0x1400e14a4  mov     [rsp+150h+FileAttributes], 80h; FileAttributes
0x1400e14ac  mov     [rsp+150h+AllocationSize], rcx; AllocationSize
0x1400e14b1  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x1400e14b6  call    cs:__imp_NtCreateFile
0x1400e14bd  nop     dword ptr [rax+rax+00h]
0x1400e14c2  test    eax, eax
0x1400e14c4  js      loc_1400E1573
0x1400e14ca  test    [rbp+50h+IoStatusBlock.Information], 0FFFFFFFFFFFFFFFCh
0x1400e14d2  mov     rax, [rsp+150h+FileHandle]
0x1400e14d7  mov     [r12], rax
0x1400e14db  jnz     short loc_1400E14E3
0x1400e14dd  cmp     [rbp+50h+IoStatusBlock.Information], rdi
0x1400e14e1  jnz     short loc_1400E14E5
0x1400e14e3  xor     edi, edi
0x1400e14e5  mov     rax, [rsp+150h+var_F0]
0x1400e14ea  mov     r14d, 0C000h
0x1400e14f0  mov     ecx, r14d; unsigned __int16
0x1400e14f3  mov     [rax], edi
0x1400e14f5  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1400e14fa  test    eax, eax
0x1400e14fc  mov     ebx, eax
0x1400e14fe  setnz   sil
0x1400e1502  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1400e1507  mov     dil, al
0x1400e150a  test    ebx, ebx
0x1400e150c  jnz     short loc_1400E1512
0x1400e150e  test    al, al
0x1400e1510  jz      short loc_1400E156F
0x1400e1512  mov     rcx, gs:58h
0x1400e151b  mov     eax, 10h
0x1400e1520  mov     rdx, [rcx]
0x1400e1523  mov     ecx, [rax+rdx]
0x1400e1526  cmp     cs:dword_1403DEA9C, ecx
0x1400e152c  jle     short loc_1400E155D
0x1400e152e  lea     rcx, dword_1403DEA9C
0x1400e1535  call    _Init_thread_header
0x1400e153a  cmp     cs:dword_1403DEA9C, 0FFFFFFFFh
0x1400e1541  jnz     short loc_1400E155D
0x1400e1543  lea     rcx, dword_1403DEA9C
0x1400e154a  mov     cs:byte_1403BCB2C, sil
0x1400e1551  mov     cs:byte_1403BCB2D, dil
0x1400e1558  call    _Init_thread_footer
0x1400e155d  mov     r8, r13
0x1400e1560  lea     rdx, off_1403BCB18; struct HvsDebugTraceParameters *
0x1400e1567  mov     ecx, r14d; unsigned int
0x1400e156a  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x1400e156f  xor     ebx, ebx
0x1400e1571  jmp     short loc_1400E1590
0x1400e1573  mov     ecx, eax; Status
0x1400e1575  call    cs:__imp_RtlNtStatusToDosError
0x1400e157c  nop     dword ptr [rax+rax+00h]
0x1400e1581  mov     ebx, eax
0x1400e1583  test    eax, eax
0x1400e1585  jle     short loc_1400E1590
0x1400e1587  movzx   ebx, ax
0x1400e158a  or      ebx, 80070000h
0x1400e1590  lea     rcx, [rbp+50h+var_90]
0x1400e1594  call    std__unique_ptr_unsigned_short__anonymous_namespace___RtlHeapDeleter_unsigned_short______unique_ptr_unsigned_short__anonymous_namespace___RtlHeapDeleter_unsigned_short___
0x1400e1599  mov     eax, ebx
0x1400e159b  mov     rcx, [rbp+50h+var_50]
0x1400e159f  xor     rcx, rsp; StackCookie
0x1400e15a2  call    __security_check_cookie
0x1400e15a7  add     rsp, 118h
0x1400e15ae  pop     r15
0x1400e15b0  pop     r14
0x1400e15b2  pop     r13
0x1400e15b4  pop     r12
0x1400e15b6  pop     rdi
0x1400e15b7  pop     rsi
0x1400e15b8  pop     rbx
0x1400e15b9  pop     rbp
0x1400e15ba  retn
```
