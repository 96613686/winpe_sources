# HyperVFileIo::OpenInternal(ushort const *,HyperVFileOpenFlags,void * *,int *)

- ea: `0x1400f13dc`
- end: `0x1400f16dc`
- name: `?OpenInternal@HyperVFileIo@@CAJPEBGW4HyperVFileOpenFlags@@PEAPEAXPEAH@Z`
- size: `768`
- prototype: `signed int __fastcall(__int64, __int16, void **, int *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14006f010`
- `0x1400ef090`
- `0x1400f11c0`

## callees

- `0x1400243c0`
- `0x14002676c`
- `0x140028d38`
- `0x1400f13dc`
- `0x1400f1a34`
- `0x14011ea40`
- `0x14011fcec`
- `0x14011fd54`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1400f14a0`
- `ntdll!RtlNtStatusToDosError` at `0x1400f1695`
- `ntdll!RtlNtStatusToDosError` at `0x1400f14a0`
- `ntdll!RtlNtStatusToDosError` at `0x1400f1695`
- `ntdll!NtCreateFile` at `0x1400f157f`
- `ntdll!NtCreateFile` at `0x1400f15d6`
- `ntdll!NtCreateFile` at `0x1400f157f`
- `ntdll!NtCreateFile` at `0x1400f15d6`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1400f148c`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1400f148c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  CreateDisposition = *((_DWORD *)qword_140318010 + (a2 & 3));
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
        if ( dword_1403CDEF0 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
        {
          Init_thread_header(&dword_1403CDEF0);
          if ( dword_1403CDEF0 == -1 )
          {
            byte_1403B2FDC = IsDebugTraceEnabled != 0;
            byte_1403B2FDD = v19;
            Init_thread_footer(&dword_1403CDEF0);
          }
        }
        HvsDebugTraceInternal(0xC000u, (const struct HvsDebugTraceParameters *)&off_1403B2FC8, a1);
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
0x1400f13dc  push    rbp
0x1400f13de  push    rbx
0x1400f13df  push    rsi
0x1400f13e0  push    rdi
0x1400f13e1  push    r12
0x1400f13e3  push    r13
0x1400f13e5  push    r14
0x1400f13e7  push    r15
0x1400f13e9  lea     rbp, [rsp-18h]
0x1400f13ee  sub     rsp, 118h
0x1400f13f5  mov     rax, cs:__security_cookie
0x1400f13fc  xor     rax, rsp
0x1400f13ff  mov     [rbp+50h+var_50], rax
0x1400f1403  mov     r13, rcx
0x1400f1406  mov     [rsp+150h+var_F0], r9
0x1400f140b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400f140f  mov     r12, r8
0x1400f1412  mov     [r8], rcx
0x1400f1415  mov     esi, edx
0x1400f1417  mov     [rsp+150h+FileHandle], rcx
0x1400f141c  mov     ecx, edx
0x1400f141e  and     ecx, 8
0x1400f1421  mov     dword ptr [r9], 0
0x1400f1428  mov     eax, ecx
0x1400f142a  neg     eax
0x1400f142c  sbb     ebx, ebx
0x1400f142e  and     ebx, 0FFFFFFFEh
0x1400f1431  add     ebx, 3
0x1400f1434  test    dl, 40h
0x1400f1437  jz      short loc_1400F1440
0x1400f1439  test    ecx, ecx
0x1400f143b  jnz     short loc_1400F1455
0x1400f143d  or      ebx, 4
0x1400f1440  mov     eax, esi
0x1400f1442  mov     ecx, esi
0x1400f1444  and     eax, 3
0x1400f1447  mov     edi, 1
0x1400f144c  and     ecx, 20h
0x1400f144f  jz      short loc_1400F145F
0x1400f1451  cmp     eax, edi
0x1400f1453  jb      short loc_1400F145F
0x1400f1455  mov     eax, 80070057h
0x1400f145a  jmp     loc_1400F16BB
0x1400f145f  neg     ecx
0x1400f1461  lea     r15, qword_140318010
0x1400f1468  mov     r15d, [r15+rax*4]
0x1400f146c  lea     rdx, [rsp+150h+var_E0]
0x1400f1471  sbb     r14d, r14d
0x1400f1474  xorps   xmm0, xmm0
0x1400f1477  xor     r9d, r9d
0x1400f147a  xor     r8d, r8d
0x1400f147d  mov     rcx, r13
0x1400f1480  and     r14d, 0FFFFFEFEh
0x1400f1487  movups  [rsp+150h+var_E0], xmm0
0x1400f148c  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x1400f1493  nop     dword ptr [rax+rax+00h]
0x1400f1498  xor     ecx, ecx
0x1400f149a  test    eax, eax
0x1400f149c  jns     short loc_1400F14C1
0x1400f149e  mov     ecx, eax; Status
0x1400f14a0  call    cs:__imp_RtlNtStatusToDosError
0x1400f14a7  nop     dword ptr [rax+rax+00h]
0x1400f14ac  test    eax, eax
0x1400f14ae  jle     loc_1400F16BB
0x1400f14b4  movzx   eax, ax
0x1400f14b7  or      eax, 80070000h
0x1400f14bc  jmp     loc_1400F16BB
0x1400f14c1  mov     rax, qword ptr [rsp+150h+var_E0+8]
0x1400f14c6  xorps   xmm0, xmm0
0x1400f14c9  mov     [rbp+50h+var_90], rax
0x1400f14cd  lea     rax, [rsp+150h+var_E0]
0x1400f14d2  mov     [rbp+50h+ObjectAttributes.ObjectName], rax
0x1400f14d6  lea     rax, [rbp+50h+var_88]
0x1400f14da  mov     [rbp+50h+ObjectAttributes.SecurityQualityOfService], rax
0x1400f14de  mov     qword ptr [rbp+50h+ObjectAttributes.Length], 30h ; '0'
0x1400f14e6  mov     qword ptr [rbp+50h+ObjectAttributes.Attributes], 40h ; '@'
0x1400f14ee  mov     [rbp+50h+ObjectAttributes.RootDirectory], rcx
0x1400f14f2  mov     [rbp+50h+ObjectAttributes.SecurityDescriptor], rcx
0x1400f14f6  mov     [rbp+50h+var_84], rcx
0x1400f14fa  mov     [rbp+50h+var_88], 0Ch
0x1400f1501  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x1400f1505  bt      esi, 0Ch
0x1400f1509  jnb     loc_1400F159B
0x1400f150f  movups  xmm1, cs:xmmword_140318020+0Ah
0x1400f1516  mov     [rsp+150h+EaLength], 28h ; '('; EaLength
0x1400f151e  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x1400f1522  movups  xmmword ptr [rbp+50h+var_74], xmm0
0x1400f1526  xor     eax, eax
0x1400f1528  mov     [rbp+50h+var_78], ecx
0x1400f152b  movups  xmmword ptr [rbp+50h+var_74+10h], xmm0
0x1400f152f  mov     [rbp+50h+var_54], eax
0x1400f1532  lea     rax, [rbp+50h+var_78]
0x1400f1536  movups  xmm0, cs:xmmword_140318020
0x1400f153d  mov     [rsp+150h+EaBuffer], rax; EaBuffer
0x1400f1542  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x1400f1546  mov     [rsp+150h+CreateOptions], 840h; CreateOptions
0x1400f154e  lea     edx, [r14+100183h]; DesiredAccess
0x1400f1555  mov     [rsp+150h+CreateDisposition], r15d; CreateDisposition
0x1400f155a  mov     [rsp+150h+ShareAccess], ebx; ShareAccess
0x1400f155e  movups  xmmword ptr [rbp+50h+var_74+4], xmm0
0x1400f1562  mov     [rsp+150h+FileAttributes], 80h; FileAttributes
0x1400f156a  mov     [rsp+150h+AllocationSize], rcx; AllocationSize
0x1400f156f  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x1400f1574  mov     dword ptr [rbp+50h+var_74], 1A00h
0x1400f157b  movups  xmmword ptr [rbp+50h+var_74+0Eh], xmm1
0x1400f157f  call    cs:__imp_NtCreateFile
0x1400f1586  nop     dword ptr [rax+rax+00h]
0x1400f158b  cmp     eax, 0C0000010h
0x1400f1590  jz      short loc_1400F1599
0x1400f1592  cmp     eax, 0C000004Fh
0x1400f1597  jnz     short loc_1400F15E2
0x1400f1599  xor     ecx, ecx
0x1400f159b  mov     [rsp+150h+EaLength], ecx; EaLength
0x1400f159f  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x1400f15a3  mov     [rsp+150h+EaBuffer], rcx; EaBuffer
0x1400f15a8  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x1400f15ac  mov     [rsp+150h+CreateOptions], 840h; CreateOptions
0x1400f15b4  lea     edx, [r14+100183h]; DesiredAccess
0x1400f15bb  mov     [rsp+150h+CreateDisposition], r15d; CreateDisposition
0x1400f15c0  mov     [rsp+150h+ShareAccess], ebx; ShareAccess
0x1400f15c4  mov     [rsp+150h+FileAttributes], 80h; FileAttributes
0x1400f15cc  mov     [rsp+150h+AllocationSize], rcx; AllocationSize
0x1400f15d1  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x1400f15d6  call    cs:__imp_NtCreateFile
0x1400f15dd  nop     dword ptr [rax+rax+00h]
0x1400f15e2  test    eax, eax
0x1400f15e4  js      loc_1400F1693
0x1400f15ea  test    [rbp+50h+IoStatusBlock.Information], 0FFFFFFFFFFFFFFFCh
0x1400f15f2  mov     rax, [rsp+150h+FileHandle]
0x1400f15f7  mov     [r12], rax
0x1400f15fb  jnz     short loc_1400F1603
0x1400f15fd  cmp     [rbp+50h+IoStatusBlock.Information], rdi
0x1400f1601  jnz     short loc_1400F1605
0x1400f1603  xor     edi, edi
0x1400f1605  mov     rax, [rsp+150h+var_F0]
0x1400f160a  mov     r14d, 0C000h
0x1400f1610  mov     ecx, r14d; unsigned __int16
0x1400f1613  mov     [rax], edi
0x1400f1615  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1400f161a  test    eax, eax
0x1400f161c  mov     ebx, eax
0x1400f161e  setnz   sil
0x1400f1622  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1400f1627  mov     dil, al
0x1400f162a  test    ebx, ebx
0x1400f162c  jnz     short loc_1400F1632
0x1400f162e  test    al, al
0x1400f1630  jz      short loc_1400F168F
0x1400f1632  mov     rcx, gs:58h
0x1400f163b  mov     eax, 810h
0x1400f1640  mov     rdx, [rcx]
0x1400f1643  mov     ecx, [rax+rdx]
0x1400f1646  cmp     cs:dword_1403CDEF0, ecx
0x1400f164c  jle     short loc_1400F167D
0x1400f164e  lea     rcx, dword_1403CDEF0
0x1400f1655  call    _Init_thread_header
0x1400f165a  cmp     cs:dword_1403CDEF0, 0FFFFFFFFh
0x1400f1661  jnz     short loc_1400F167D
0x1400f1663  lea     rcx, dword_1403CDEF0
0x1400f166a  mov     cs:byte_1403B2FDC, sil
0x1400f1671  mov     cs:byte_1403B2FDD, dil
0x1400f1678  call    _Init_thread_footer
0x1400f167d  mov     r8, r13
0x1400f1680  lea     rdx, off_1403B2FC8; struct HvsDebugTraceParameters *
0x1400f1687  mov     ecx, r14d; unsigned int
0x1400f168a  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x1400f168f  xor     ebx, ebx
0x1400f1691  jmp     short loc_1400F16B0
0x1400f1693  mov     ecx, eax; Status
0x1400f1695  call    cs:__imp_RtlNtStatusToDosError
0x1400f169c  nop     dword ptr [rax+rax+00h]
0x1400f16a1  mov     ebx, eax
0x1400f16a3  test    eax, eax
0x1400f16a5  jle     short loc_1400F16B0
0x1400f16a7  movzx   ebx, ax
0x1400f16aa  or      ebx, 80070000h
0x1400f16b0  lea     rcx, [rbp+50h+var_90]
0x1400f16b4  call    std__unique_ptr_unsigned_short__anonymous_namespace___RtlHeapDeleter_unsigned_short______unique_ptr_unsigned_short__anonymous_namespace___RtlHeapDeleter_unsigned_short___
0x1400f16b9  mov     eax, ebx
0x1400f16bb  mov     rcx, [rbp+50h+var_50]
0x1400f16bf  xor     rcx, rsp; StackCookie
0x1400f16c2  call    __security_check_cookie
0x1400f16c7  add     rsp, 118h
0x1400f16ce  pop     r15
0x1400f16d0  pop     r14
0x1400f16d2  pop     r13
0x1400f16d4  pop     r12
0x1400f16d6  pop     rdi
0x1400f16d7  pop     rsi
0x1400f16d8  pop     rbx
0x1400f16d9  pop     rbp
0x1400f16da  retn
```
