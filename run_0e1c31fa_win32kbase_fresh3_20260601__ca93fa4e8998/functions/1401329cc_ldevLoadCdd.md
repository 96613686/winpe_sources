# ldevLoadCdd

- ea: `0x1401329cc`
- end: `0x140132d9c`
- name: `ldevLoadCdd`
- size: `976`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, registry_config, service_task`

## callers

- `0x14019bd60`

## callees

- `0x140040394`
- `0x1400411c0`
- `0x1400c5dc0`
- `0x140102630`
- `0x1401329cc`
- `0x14015d7dc`
- `0x1401b6a14`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140132c83`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140132c83`
- `ntoskrnl!KeDelayExecutionThread` at `0x140132b65`
- `ntoskrnl!KeDelayExecutionThread` at `0x140132b65`
- `ntoskrnl!ZwLoadDriver` at `0x140132a81`
- `ntoskrnl!ZwLoadDriver` at `0x140132a81`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140132b3d`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140132b3d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140132a21`
- `ntoskrnl!RtlInitUnicodeString` at `0x140132a3f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140132ae5`
- `ntoskrnl!RtlInitUnicodeString` at `0x140132a21`
- `ntoskrnl!RtlInitUnicodeString` at `0x140132a3f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140132ae5`
- `ntoskrnl!ObfDereferenceObject` at `0x140132b10`
- `watchdog!WdLogSingleEntry0` at `0x1401329f3`
- `watchdog!WdLogSingleEntry0` at `0x1401329f3`
- `watchdog!WdLogSingleEntry1` at `0x140132aa9`
- `watchdog!WdLogSingleEntry1` at `0x140132b87`
- `watchdog!WdLogSingleEntry1` at `0x140132bf4`
- `watchdog!WdLogSingleEntry1` at `0x140132d38`
- `watchdog!WdLogSingleEntry1` at `0x140132aa9`
- `watchdog!WdLogSingleEntry1` at `0x140132b87`
- `watchdog!WdLogSingleEntry1` at `0x140132bf4`
- `watchdog!WdLogSingleEntry1` at `0x140132d38`
- `WIN32K!W32GetSessionState` at `0x140132ce2`
- `WIN32K!W32GetSessionState` at `0x140132ce2`

## string_xrefs

- `0x140132a30`: `\Registry\Machine\System\CurrentControlSet\Services\cdd`

## pseudocode

```c
__int64 __fastcall ldevLoadCdd(__int64 *a1, _DWORD *a2, int a3)
{
  __int64 v6; // rax
  char v8; // di
  NTSTATUS v9; // eax
  __int64 v10; // rbx
  PFILE_OBJECT v11; // rax
  int v12; // r14d
  NTSTATUS DeviceObjectPointer; // eax
  int v14; // eax
  struct _UNICODE_STRING *v15; // rbx
  _QWORD *v16; // rdi
  WCHAR *v17; // rax
  WCHAR *v18; // r14
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rax
  PDEVICE_OBJECT DeviceObject; // [rsp+50h] [rbp-29h] BYREF
  __int64 v23; // [rsp+58h] [rbp-21h] BYREF
  LONG_PTR (__stdcall *v24)(PVOID); // [rsp+60h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-11h] BYREF
  struct _UNICODE_STRING v26; // [rsp+78h] [rbp-1h] BYREF
  struct _UNICODE_STRING DriverServiceName; // [rsp+88h] [rbp+Fh] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+98h] [rbp+1Fh] BYREF
  union _LARGE_INTEGER Interval; // [rsp+E8h] [rbp+6Fh] BYREF
  PFILE_OBJECT FileObject; // [rsp+F8h] [rbp+7Fh] BYREF

  WdLogSingleEntry0(4);
  WdLogGlobalForLineNumber = 845;
  *a2 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"cdd");
  DriverServiceName = 0;
  RtlInitUnicodeString(&DriverServiceName, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\cdd");
  v6 = ldevTryReferenceLoadedDisplayDriver(&DestinationString);
  if ( v6 )
  {
    *a2 = 1;
    *a1 = v6;
    return 0;
  }
  if ( gbCddLoadedPermanently )
  {
    v8 = 1;
  }
  else
  {
    v9 = ZwLoadDriver(&DriverServiceName);
    LODWORD(v10) = v9;
    if ( v9 == -1073741554 )
    {
      v8 = 0;
    }
    else
    {
      if ( v9 < 0 )
      {
        WdLogSingleEntry1(2, v9);
        WdLogGlobalForLineNumber = 883;
        return (unsigned int)v10;
      }
      v8 = 1;
    }
    gbCddLoadedPermanently = 1;
  }
  ObjectName = 0;
  RtlInitUnicodeString(&ObjectName, L"\\Device\\cdd");
  v11 = 0;
  DeviceObject = 0;
  FileObject = 0;
  v12 = 10;
  while ( 1 )
  {
    if ( v11 )
    {
      Interval.QuadPart = (LONGLONG)v11;
      v24 = ObfDereferenceObject;
      wistd::invoke<__int64 (*)(void *),_FILE_OBJECT * &>(&v24, &Interval);
    }
    FileObject = 0;
    DeviceObjectPointer = IoGetDeviceObjectPointer(&ObjectName, 0xC0000000, &FileObject, &DeviceObject);
    v10 = DeviceObjectPointer;
    if ( DeviceObjectPointer >= 0 )
      break;
    if ( v8 || (Interval.QuadPart = -50000, KeDelayExecutionThread(0, 0, &Interval), --v12, v12 <= 0) )
    {
      WdLogSingleEntry1(2, v10);
      WdLogGlobalForLineNumber = 918;
LABEL_23:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>(&FileObject);
      return (unsigned int)v10;
    }
    v11 = FileObject;
  }
  v23 = 0;
  v14 = GreDeviceIoControlImpl(DeviceObject, 0x232007u, 0, 0, &v23, 8u, (unsigned int *)&Interval, 1u, 0);
  LODWORD(v10) = v14;
  if ( v14 < 0 )
  {
    WdLogSingleEntry1(2, v14);
    WdLogGlobalForLineNumber = 924;
    goto LABEL_23;
  }
  v15 = (struct _UNICODE_STRING *)PALLOCMEM(48, 1986292807);
  v16 = (_QWORD *)PALLOCMEM(912, 1986292807);
  v17 = (WCHAR *)PALLOCMEM(DestinationString.MaximumLength, 1986292807);
  v18 = v17;
  if ( v15 && v16 && v17 )
  {
    *(_QWORD *)&v26.Length = 0;
    v26.Buffer = v17;
    v26.MaximumLength = DestinationString.MaximumLength;
    RtlCopyUnicodeString(&v26, &DestinationString);
    v16[113] = v16 + 9;
    *((_DWORD *)v16 + 17) = 0;
    *v15 = v26;
    *(_QWORD *)&v15[2].Length = v23;
    v16[2] = v15;
    *((_DWORD *)v16 + 9) = 1;
    *((_DWORD *)v16 + 8) = 1;
    *((_DWORD *)v16 + 16) = -1;
    v19 = (4 * a3) ^ (*((_DWORD *)v16 + 10) ^ (4 * a3)) & 0xFFFFFFFB | 2;
    *((_DWORD *)v16 + 10) = v19;
    v20 = *(_QWORD *)(W32GetSessionState(v19) + 88);
    v21 = *(_QWORD *)(v20 + 1816);
    if ( v21 )
      *(_QWORD *)(v21 + 8) = v16;
    *v16 = *(_QWORD *)(v20 + 1816);
    v16[1] = 0;
    *(_QWORD *)(v20 + 1816) = v16;
    *a1 = (__int64)v16;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>(&FileObject);
    return 0;
  }
  WdLogSingleEntry1(2, -1073741801);
  WdLogGlobalForLineNumber = 932;
  if ( v18 )
    GreDeleteFastMutex(v18);
  if ( v16 )
    GreDeleteFastMutex(v16);
  if ( v15 )
    GreDeleteFastMutex(v15);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>(&FileObject);
  return 3221225495LL;
}

```

## disassembly

```asm
0x1401329cc  mov     [rsp-8+arg_0], rbx
0x1401329d1  push    rbp
0x1401329d2  push    rdi
0x1401329d3  push    r12
0x1401329d5  push    r14
0x1401329d7  push    r15
0x1401329d9  lea     rbp, [rsp-37h]
0x1401329de  sub     rsp, 0B0h
0x1401329e5  mov     r12d, r8d
0x1401329e8  mov     rbx, rdx
0x1401329eb  mov     r15, rcx
0x1401329ee  mov     ecx, 4
0x1401329f3  call    cs:__imp_WdLogSingleEntry0
0x1401329fa  nop     dword ptr [rax+rax+00h]
0x1401329ff  xorps   xmm0, xmm0
0x140132a02  mov     cs:WdLogGlobalForLineNumber, 34Dh
0x140132a0c  lea     rdx, aCdd_0; "cdd"
0x140132a13  mov     dword ptr [rbx], 0
0x140132a19  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140132a1d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140132a21  call    cs:__imp_RtlInitUnicodeString
0x140132a28  nop     dword ptr [rax+rax+00h]
0x140132a2d  xorps   xmm0, xmm0
0x140132a30  lea     rdx, aRegistryMachin_23; "\\Registry\\Machine\\System\\CurrentCon"...
0x140132a37  lea     rcx, [rbp+57h+DriverServiceName]; DestinationString
0x140132a3b  movups  xmmword ptr [rbp+57h+DriverServiceName.Length], xmm0
0x140132a3f  call    cs:__imp_RtlInitUnicodeString
0x140132a46  nop     dword ptr [rax+rax+00h]
0x140132a4b  mov     r8d, r12d
0x140132a4e  lea     rcx, [rbp+57h+DestinationString]; String2
0x140132a52  xor     edx, edx
0x140132a54  call    ldevTryReferenceLoadedDisplayDriver
0x140132a59  test    rax, rax
0x140132a5c  jz      short loc_140132A6E
0x140132a5e  mov     dword ptr [rbx], 1
0x140132a64  mov     [r15], rax
0x140132a67  xor     eax, eax
0x140132a69  jmp     loc_140132D83
0x140132a6e  mov     eax, cs:?gbCddLoadedPermanently@@3HC; int volatile gbCddLoadedPermanently
0x140132a74  test    eax, eax
0x140132a76  jz      short loc_140132A7D
0x140132a78  mov     dil, 1
0x140132a7b  jmp     short loc_140132AD3
0x140132a7d  lea     rcx, [rbp+57h+DriverServiceName]; DriverServiceName
0x140132a81  call    cs:__imp_ZwLoadDriver
0x140132a88  nop     dword ptr [rax+rax+00h]
0x140132a8d  movsxd  rbx, eax
0x140132a90  cmp     ebx, 0C000010Eh
0x140132a96  jnz     short loc_140132A9D
0x140132a98  xor     dil, dil
0x140132a9b  jmp     short loc_140132AC9
0x140132a9d  test    eax, eax
0x140132a9f  jns     short loc_140132AC6
0x140132aa1  mov     rdx, rbx
0x140132aa4  mov     ecx, 2
0x140132aa9  call    cs:__imp_WdLogSingleEntry1
0x140132ab0  nop     dword ptr [rax+rax+00h]
0x140132ab5  mov     cs:WdLogGlobalForLineNumber, 373h
0x140132abf  mov     eax, ebx
0x140132ac1  jmp     loc_140132D83
0x140132ac6  mov     dil, 1
0x140132ac9  mov     cs:?gbCddLoadedPermanently@@3HC, 1; int volatile gbCddLoadedPermanently
0x140132ad3  xorps   xmm0, xmm0
0x140132ad6  lea     rdx, aDeviceCdd; "\\Device\\cdd"
0x140132add  lea     rcx, [rbp+57h+ObjectName]; DestinationString
0x140132ae1  movups  xmmword ptr [rbp+57h+ObjectName.Length], xmm0
0x140132ae5  call    cs:__imp_RtlInitUnicodeString
0x140132aec  nop     dword ptr [rax+rax+00h]
0x140132af1  xor     eax, eax
0x140132af3  mov     [rbp+57h+DeviceObject], 0
0x140132afb  mov     [rbp+57h+FileObject], rax
0x140132aff  lea     r14d, [rax+0Ah]
0x140132b03  test    rax, rax
0x140132b06  jz      short loc_140132B24
0x140132b08  mov     qword ptr [rbp+57h+Interval], rax
0x140132b0c  lea     rdx, [rbp+57h+Interval]
0x140132b10  mov     rax, cs:__imp_ObfDereferenceObject
0x140132b17  lea     rcx, [rbp+57h+var_70]
0x140132b1b  mov     [rbp+57h+var_70], rax
0x140132b1f  call    ??$invoke@P6A_JPEAX@ZAEAPEAU_FILE_OBJECT@@@wistd@@YA_J$$QEAP6A_JPEAX@ZAEAPEAU_FILE_OBJECT@@@Z; wistd::invoke<__int64 (*)(void *),_FILE_OBJECT * &>(__int64 (*&&)(void *),_FILE_OBJECT * &)
0x140132b24  lea     r9, [rbp+57h+DeviceObject]; DeviceObject
0x140132b28  mov     [rbp+57h+FileObject], 0
0x140132b30  lea     r8, [rbp+57h+FileObject]; FileObject
0x140132b34  mov     edx, 0C0000000h; DesiredAccess
0x140132b39  lea     rcx, [rbp+57h+ObjectName]; ObjectName
0x140132b3d  call    cs:__imp_IoGetDeviceObjectPointer
0x140132b44  nop     dword ptr [rax+rax+00h]
0x140132b49  movsxd  rbx, eax
0x140132b4c  test    eax, eax
0x140132b4e  jns     short loc_140132B9F
0x140132b50  test    dil, dil
0x140132b53  jnz     short loc_140132B7F
0x140132b55  lea     r8, [rbp+57h+Interval]; Interval
0x140132b59  mov     qword ptr [rbp+57h+Interval], 0FFFFFFFFFFFF3CB0h
0x140132b61  xor     edx, edx; Alertable
0x140132b63  xor     ecx, ecx; WaitMode
0x140132b65  call    cs:__imp_KeDelayExecutionThread
0x140132b6c  nop     dword ptr [rax+rax+00h]
0x140132b71  dec     r14d
0x140132b74  test    r14d, r14d
0x140132b77  jle     short loc_140132B7F
0x140132b79  mov     rax, [rbp+57h+FileObject]
0x140132b7d  jmp     short loc_140132B03
0x140132b7f  mov     rdx, rbx
0x140132b82  mov     ecx, 2
0x140132b87  call    cs:__imp_WdLogSingleEntry1
0x140132b8e  nop     dword ptr [rax+rax+00h]
0x140132b93  mov     cs:WdLogGlobalForLineNumber, 396h
0x140132b9d  jmp     short loc_140132C0A
0x140132b9f  mov     rcx, [rbp+57h+DeviceObject]; DeviceObject
0x140132ba3  lea     rax, [rbp+57h+Interval]
0x140132ba7  mov     [rsp+0D0h+var_90], 0; int
0x140132baf  xor     r9d, r9d; InputBufferLength
0x140132bb2  mov     dword ptr [rsp+0D0h+var_98], 1; BOOLEAN
0x140132bba  xor     r8d, r8d; InputBuffer
0x140132bbd  mov     [rsp+0D0h+var_A0], rax; unsigned int *
0x140132bc2  mov     edx, 232007h; IoControlCode
0x140132bc7  lea     rax, [rbp+57h+var_78]
0x140132bcb  mov     [rsp+0D0h+var_A8], 8; ULONG
0x140132bd3  mov     [rsp+0D0h+var_B0], rax; PVOID
0x140132bd8  mov     [rbp+57h+var_78], 0
0x140132be0  call    ?GreDeviceIoControlImpl@@YAJPEAXK0K0KPEAKHH@Z; GreDeviceIoControlImpl(void *,ulong,void *,ulong,void *,ulong,ulong *,int,int)
0x140132be5  movsxd  rbx, eax
0x140132be8  test    eax, eax
0x140132bea  jns     short loc_140132C18
0x140132bec  mov     rdx, rbx
0x140132bef  mov     ecx, 2
0x140132bf4  call    cs:__imp_WdLogSingleEntry1
0x140132bfb  nop     dword ptr [rax+rax+00h]
0x140132c00  mov     cs:WdLogGlobalForLineNumber, 39Ch
0x140132c0a  lea     rcx, [rbp+57h+FileObject]
0x140132c0e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_FILE_OBJECT@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>(void)
0x140132c13  jmp     loc_140132ABF
0x140132c18  mov     r14d, 76646C47h
0x140132c1e  mov     ecx, 30h ; '0'
0x140132c23  mov     edx, r14d
0x140132c26  call    PALLOCMEM
0x140132c2b  mov     edx, r14d
0x140132c2e  mov     ecx, 390h
0x140132c33  mov     rbx, rax
0x140132c36  call    PALLOCMEM
0x140132c3b  movzx   ecx, [rbp+57h+DestinationString.MaximumLength]
0x140132c3f  mov     edx, r14d
0x140132c42  mov     rdi, rax
0x140132c45  call    PALLOCMEM
0x140132c4a  mov     r14, rax
0x140132c4d  test    rbx, rbx
0x140132c50  jz      loc_140132D2C
0x140132c56  test    rdi, rdi
0x140132c59  jz      loc_140132D2C
0x140132c5f  test    rax, rax
0x140132c62  jz      loc_140132D2C
0x140132c68  xorps   xmm0, xmm0
0x140132c6b  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x140132c6f  movups  xmmword ptr [rbp+57h+var_58.Length], xmm0
0x140132c73  mov     [rbp+57h+var_58.Buffer], rax
0x140132c77  lea     rcx, [rbp+57h+var_58]; DestinationString
0x140132c7b  movzx   eax, [rbp+57h+DestinationString.MaximumLength]
0x140132c7f  mov     [rbp+57h+var_58.MaximumLength], ax
0x140132c83  call    cs:__imp_RtlCopyUnicodeString
0x140132c8a  nop     dword ptr [rax+rax+00h]
0x140132c8f  lea     rax, [rdi+48h]
0x140132c93  mov     [rdi+388h], rax
0x140132c9a  mov     dword ptr [rdi+44h], 0
0x140132ca1  movups  xmm0, xmmword ptr [rbp+57h+var_58.Length]
0x140132ca5  movdqu  xmmword ptr [rbx], xmm0
0x140132ca9  mov     rax, [rbp+57h+var_78]
0x140132cad  mov     [rbx+20h], rax
0x140132cb1  lea     eax, ds:0[r12*4]
0x140132cb9  mov     [rdi+10h], rbx
0x140132cbd  mov     ecx, eax
0x140132cbf  mov     dword ptr [rdi+24h], 1
0x140132cc6  mov     dword ptr [rdi+20h], 1
0x140132ccd  mov     dword ptr [rdi+40h], 0FFFFFFFFh
0x140132cd4  xor     ecx, [rdi+28h]
0x140132cd7  and     ecx, 0FFFFFFFBh
0x140132cda  xor     ecx, eax
0x140132cdc  or      ecx, 2
0x140132cdf  mov     [rdi+28h], ecx
0x140132ce2  call    cs:__imp_W32GetSessionState
0x140132ce9  nop     dword ptr [rax+rax+00h]
0x140132cee  mov     rcx, [rax+58h]
0x140132cf2  mov     rax, [rcx+718h]
0x140132cf9  test    rax, rax
0x140132cfc  jz      short loc_140132D02
0x140132cfe  mov     [rax+8], rdi
0x140132d02  mov     rax, [rcx+718h]
0x140132d09  mov     [rdi], rax
0x140132d0c  mov     qword ptr [rdi+8], 0
0x140132d14  mov     [rcx+718h], rdi
0x140132d1b  lea     rcx, [rbp+57h+FileObject]
0x140132d1f  mov     [r15], rdi
0x140132d22  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_FILE_OBJECT@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>(void)
0x140132d27  jmp     loc_140132A67
0x140132d2c  mov     rdx, 0FFFFFFFFC0000017h
0x140132d33  mov     ecx, 2
0x140132d38  call    cs:__imp_WdLogSingleEntry1
0x140132d3f  nop     dword ptr [rax+rax+00h]
0x140132d44  mov     cs:WdLogGlobalForLineNumber, 3A4h
0x140132d4e  test    r14, r14
0x140132d51  jz      short loc_140132D5B
0x140132d53  mov     rcx, r14; Buffer
0x140132d56  call    GreDeleteFastMutex
0x140132d5b  test    rdi, rdi
0x140132d5e  jz      short loc_140132D68
0x140132d60  mov     rcx, rdi; Buffer
0x140132d63  call    GreDeleteFastMutex
0x140132d68  test    rbx, rbx
0x140132d6b  jz      short loc_140132D75
0x140132d6d  mov     rcx, rbx; Buffer
0x140132d70  call    GreDeleteFastMutex
0x140132d75  lea     rcx, [rbp+57h+FileObject]
0x140132d79  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_FILE_OBJECT@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>(void)
0x140132d7e  mov     eax, 0C0000017h
0x140132d83  mov     rbx, [rsp+0D0h+arg_0]
0x140132d8b  add     rsp, 0B0h
0x140132d92  pop     r15
0x140132d94  pop     r14
0x140132d96  pop     r12
0x140132d98  pop     rdi
0x140132d99  pop     rbp
0x140132d9a  retn
```
