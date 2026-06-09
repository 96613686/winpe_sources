# HyperVFileIo::OpenInternal(ushort const *,HyperVFileOpenFlags,void * *,int *)

- ea: `0x14010287c`
- end: `0x140102b7c`
- name: `?OpenInternal@HyperVFileIo@@CAJPEBGW4HyperVFileOpenFlags@@PEAPEAXPEAH@Z`
- size: `768`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400612d0`
- `0x1400fe230`
- `0x140102660`

## callees

- `0x140023e50`
- `0x1400261fc`
- `0x1400287c8`
- `0x14010287c`
- `0x140102ed4`
- `0x140132960`
- `0x140133c0c`
- `0x140133c74`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x140102940`
- `ntdll!RtlNtStatusToDosError` at `0x140102b35`
- `ntdll!RtlNtStatusToDosError` at `0x140102940`
- `ntdll!RtlNtStatusToDosError` at `0x140102b35`
- `ntdll!NtCreateFile` at `0x140102a1f`
- `ntdll!NtCreateFile` at `0x140102a76`
- `ntdll!NtCreateFile` at `0x140102a1f`
- `ntdll!NtCreateFile` at `0x140102a76`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x14010292c`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x14010292c`

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
  CreateDisposition = *((_DWORD *)qword_14030E848 + (a2 & 3));
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
        if ( dword_1403C1960 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
        {
          Init_thread_header(&dword_1403C1960);
          if ( dword_1403C1960 == -1 )
          {
            byte_1403A6ECC = IsDebugTraceEnabled != 0;
            byte_1403A6ECD = v19;
            Init_thread_footer(&dword_1403C1960);
          }
        }
        HvsDebugTraceInternal(0xC000u, (const struct HvsDebugTraceParameters *)&off_1403A6EB8, a1);
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
0x14010287c  push    rbp
0x14010287e  push    rbx
0x14010287f  push    rsi
0x140102880  push    rdi
0x140102881  push    r12
0x140102883  push    r13
0x140102885  push    r14
0x140102887  push    r15
0x140102889  lea     rbp, [rsp-18h]
0x14010288e  sub     rsp, 118h
0x140102895  mov     rax, cs:__security_cookie
0x14010289c  xor     rax, rsp
0x14010289f  mov     [rbp+50h+var_50], rax
0x1401028a3  mov     r13, rcx
0x1401028a6  mov     [rsp+150h+var_F0], r9
0x1401028ab  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1401028af  mov     r12, r8
0x1401028b2  mov     [r8], rcx
0x1401028b5  mov     esi, edx
0x1401028b7  mov     [rsp+150h+FileHandle], rcx
0x1401028bc  mov     ecx, edx
0x1401028be  and     ecx, 8
0x1401028c1  mov     dword ptr [r9], 0
0x1401028c8  mov     eax, ecx
0x1401028ca  neg     eax
0x1401028cc  sbb     ebx, ebx
0x1401028ce  and     ebx, 0FFFFFFFEh
0x1401028d1  add     ebx, 3
0x1401028d4  test    dl, 40h
0x1401028d7  jz      short loc_1401028E0
0x1401028d9  test    ecx, ecx
0x1401028db  jnz     short loc_1401028F5
0x1401028dd  or      ebx, 4
0x1401028e0  mov     eax, esi
0x1401028e2  mov     ecx, esi
0x1401028e4  and     eax, 3
0x1401028e7  mov     edi, 1
0x1401028ec  and     ecx, 20h
0x1401028ef  jz      short loc_1401028FF
0x1401028f1  cmp     eax, edi
0x1401028f3  jb      short loc_1401028FF
0x1401028f5  mov     eax, 80070057h
0x1401028fa  jmp     loc_140102B5B
0x1401028ff  neg     ecx
0x140102901  lea     r15, qword_14030E848
0x140102908  mov     r15d, [r15+rax*4]
0x14010290c  lea     rdx, [rsp+150h+var_E0]
0x140102911  sbb     r14d, r14d
0x140102914  xorps   xmm0, xmm0
0x140102917  xor     r9d, r9d
0x14010291a  xor     r8d, r8d
0x14010291d  mov     rcx, r13
0x140102920  and     r14d, 0FFFFFEFEh
0x140102927  movups  [rsp+150h+var_E0], xmm0
0x14010292c  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x140102933  nop     dword ptr [rax+rax+00h]
0x140102938  xor     ecx, ecx
0x14010293a  test    eax, eax
0x14010293c  jns     short loc_140102961
0x14010293e  mov     ecx, eax; Status
0x140102940  call    cs:__imp_RtlNtStatusToDosError
0x140102947  nop     dword ptr [rax+rax+00h]
0x14010294c  test    eax, eax
0x14010294e  jle     loc_140102B5B
0x140102954  movzx   eax, ax
0x140102957  or      eax, 80070000h
0x14010295c  jmp     loc_140102B5B
0x140102961  mov     rax, qword ptr [rsp+150h+var_E0+8]
0x140102966  xorps   xmm0, xmm0
0x140102969  mov     [rbp+50h+var_90], rax
0x14010296d  lea     rax, [rsp+150h+var_E0]
0x140102972  mov     [rbp+50h+ObjectAttributes.ObjectName], rax
0x140102976  lea     rax, [rbp+50h+var_88]
0x14010297a  mov     [rbp+50h+ObjectAttributes.SecurityQualityOfService], rax
0x14010297e  mov     qword ptr [rbp+50h+ObjectAttributes.Length], 30h ; '0'
0x140102986  mov     qword ptr [rbp+50h+ObjectAttributes.Attributes], 40h ; '@'
0x14010298e  mov     [rbp+50h+ObjectAttributes.RootDirectory], rcx
0x140102992  mov     [rbp+50h+ObjectAttributes.SecurityDescriptor], rcx
0x140102996  mov     [rbp+50h+var_84], rcx
0x14010299a  mov     [rbp+50h+var_88], 0Ch
0x1401029a1  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x1401029a5  bt      esi, 0Ch
0x1401029a9  jnb     loc_140102A3B
0x1401029af  movups  xmm1, cs:xmmword_14030E858+0Ah
0x1401029b6  mov     [rsp+150h+EaLength], 28h ; '('; EaLength
0x1401029be  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x1401029c2  movups  xmmword ptr [rbp+50h+var_74], xmm0
0x1401029c6  xor     eax, eax
0x1401029c8  mov     [rbp+50h+var_78], ecx
0x1401029cb  movups  xmmword ptr [rbp+50h+var_74+10h], xmm0
0x1401029cf  mov     [rbp+50h+var_54], eax
0x1401029d2  lea     rax, [rbp+50h+var_78]
0x1401029d6  movups  xmm0, cs:xmmword_14030E858
0x1401029dd  mov     [rsp+150h+EaBuffer], rax; EaBuffer
0x1401029e2  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x1401029e6  mov     [rsp+150h+CreateOptions], 840h; CreateOptions
0x1401029ee  lea     edx, [r14+100183h]; DesiredAccess
0x1401029f5  mov     [rsp+150h+CreateDisposition], r15d; CreateDisposition
0x1401029fa  mov     [rsp+150h+ShareAccess], ebx; ShareAccess
0x1401029fe  movups  xmmword ptr [rbp+50h+var_74+4], xmm0
0x140102a02  mov     [rsp+150h+FileAttributes], 80h; FileAttributes
0x140102a0a  mov     [rsp+150h+AllocationSize], rcx; AllocationSize
0x140102a0f  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x140102a14  mov     dword ptr [rbp+50h+var_74], 1A00h
0x140102a1b  movups  xmmword ptr [rbp+50h+var_74+0Eh], xmm1
0x140102a1f  call    cs:__imp_NtCreateFile
0x140102a26  nop     dword ptr [rax+rax+00h]
0x140102a2b  cmp     eax, 0C0000010h
0x140102a30  jz      short loc_140102A39
0x140102a32  cmp     eax, 0C000004Fh
0x140102a37  jnz     short loc_140102A82
0x140102a39  xor     ecx, ecx
0x140102a3b  mov     [rsp+150h+EaLength], ecx; EaLength
0x140102a3f  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x140102a43  mov     [rsp+150h+EaBuffer], rcx; EaBuffer
0x140102a48  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x140102a4c  mov     [rsp+150h+CreateOptions], 840h; CreateOptions
0x140102a54  lea     edx, [r14+100183h]; DesiredAccess
0x140102a5b  mov     [rsp+150h+CreateDisposition], r15d; CreateDisposition
0x140102a60  mov     [rsp+150h+ShareAccess], ebx; ShareAccess
0x140102a64  mov     [rsp+150h+FileAttributes], 80h; FileAttributes
0x140102a6c  mov     [rsp+150h+AllocationSize], rcx; AllocationSize
0x140102a71  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x140102a76  call    cs:__imp_NtCreateFile
0x140102a7d  nop     dword ptr [rax+rax+00h]
0x140102a82  test    eax, eax
0x140102a84  js      loc_140102B33
0x140102a8a  test    [rbp+50h+IoStatusBlock.Information], 0FFFFFFFFFFFFFFFCh
0x140102a92  mov     rax, [rsp+150h+FileHandle]
0x140102a97  mov     [r12], rax
0x140102a9b  jnz     short loc_140102AA3
0x140102a9d  cmp     [rbp+50h+IoStatusBlock.Information], rdi
0x140102aa1  jnz     short loc_140102AA5
0x140102aa3  xor     edi, edi
0x140102aa5  mov     rax, [rsp+150h+var_F0]
0x140102aaa  mov     r14d, 0C000h
0x140102ab0  mov     ecx, r14d; unsigned __int16
0x140102ab3  mov     [rax], edi
0x140102ab5  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x140102aba  test    eax, eax
0x140102abc  mov     ebx, eax
0x140102abe  setnz   sil
0x140102ac2  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x140102ac7  mov     dil, al
0x140102aca  test    ebx, ebx
0x140102acc  jnz     short loc_140102AD2
0x140102ace  test    al, al
0x140102ad0  jz      short loc_140102B2F
0x140102ad2  mov     rcx, gs:58h
0x140102adb  mov     eax, 810h
0x140102ae0  mov     rdx, [rcx]
0x140102ae3  mov     ecx, [rax+rdx]
0x140102ae6  cmp     cs:dword_1403C1960, ecx
0x140102aec  jle     short loc_140102B1D
0x140102aee  lea     rcx, dword_1403C1960
0x140102af5  call    _Init_thread_header
0x140102afa  cmp     cs:dword_1403C1960, 0FFFFFFFFh
0x140102b01  jnz     short loc_140102B1D
0x140102b03  lea     rcx, dword_1403C1960
0x140102b0a  mov     cs:byte_1403A6ECC, sil
0x140102b11  mov     cs:byte_1403A6ECD, dil
0x140102b18  call    _Init_thread_footer
0x140102b1d  mov     r8, r13
0x140102b20  lea     rdx, off_1403A6EB8; struct HvsDebugTraceParameters *
0x140102b27  mov     ecx, r14d; unsigned int
0x140102b2a  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x140102b2f  xor     ebx, ebx
0x140102b31  jmp     short loc_140102B50
0x140102b33  mov     ecx, eax; Status
0x140102b35  call    cs:__imp_RtlNtStatusToDosError
0x140102b3c  nop     dword ptr [rax+rax+00h]
0x140102b41  mov     ebx, eax
0x140102b43  test    eax, eax
0x140102b45  jle     short loc_140102B50
0x140102b47  movzx   ebx, ax
0x140102b4a  or      ebx, 80070000h
0x140102b50  lea     rcx, [rbp+50h+var_90]
0x140102b54  call    std__unique_ptr_unsigned_short__anonymous_namespace___RtlHeapDeleter_unsigned_short______unique_ptr_unsigned_short__anonymous_namespace___RtlHeapDeleter_unsigned_short___
0x140102b59  mov     eax, ebx
0x140102b5b  mov     rcx, [rbp+50h+var_50]
0x140102b5f  xor     rcx, rsp; StackCookie
0x140102b62  call    __security_check_cookie
0x140102b67  add     rsp, 118h
0x140102b6e  pop     r15
0x140102b70  pop     r14
0x140102b72  pop     r13
0x140102b74  pop     r12
0x140102b76  pop     rdi
0x140102b77  pop     rsi
0x140102b78  pop     rbx
0x140102b79  pop     rbp
0x140102b7a  retn
```
