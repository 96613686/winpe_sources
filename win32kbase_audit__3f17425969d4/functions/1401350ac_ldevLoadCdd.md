# ldevLoadCdd

- ea: `0x1401350ac`
- end: `0x14013547c`
- name: `ldevLoadCdd`
- size: `976`
- prototype: `__int64 __fastcall(__int64 *, _DWORD *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, registry_config, service_task`

## callers

- `0x14019d1c0`

## callees

- `0x14000f138`
- `0x14007ab04`
- `0x14007b930`
- `0x1400d4e00`
- `0x1401350ac`
- `0x1401607ac`
- `0x1401b7634`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140135363`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140135363`
- `ntoskrnl!KeDelayExecutionThread` at `0x140135245`
- `ntoskrnl!KeDelayExecutionThread` at `0x140135245`
- `ntoskrnl!ZwLoadDriver` at `0x140135161`
- `ntoskrnl!ZwLoadDriver` at `0x140135161`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14013521d`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14013521d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140135101`
- `ntoskrnl!RtlInitUnicodeString` at `0x14013511f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401351c5`
- `ntoskrnl!RtlInitUnicodeString` at `0x140135101`
- `ntoskrnl!RtlInitUnicodeString` at `0x14013511f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401351c5`
- `ntoskrnl!ObfDereferenceObject` at `0x1401351f0`
- `watchdog!WdLogSingleEntry0` at `0x1401350d3`
- `watchdog!WdLogSingleEntry0` at `0x1401350d3`
- `watchdog!WdLogSingleEntry1` at `0x140135189`
- `watchdog!WdLogSingleEntry1` at `0x140135267`
- `watchdog!WdLogSingleEntry1` at `0x1401352d4`
- `watchdog!WdLogSingleEntry1` at `0x140135418`
- `watchdog!WdLogSingleEntry1` at `0x140135189`
- `watchdog!WdLogSingleEntry1` at `0x140135267`
- `watchdog!WdLogSingleEntry1` at `0x1401352d4`
- `watchdog!WdLogSingleEntry1` at `0x140135418`
- `WIN32K!W32GetSessionState` at `0x1401353c2`
- `WIN32K!W32GetSessionState` at `0x1401353c2`

## string_xrefs

- `0x140135110`: `\Registry\Machine\System\CurrentControlSet\Services\cdd`

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
  __int64 v15; // rbx
  __int64 v16; // rdi
  WCHAR *v17; // rax
  WCHAR *v18; // r14
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rdx
  PDEVICE_OBJECT DeviceObject; // [rsp+50h] [rbp-29h] BYREF
  __int64 v24; // [rsp+58h] [rbp-21h] BYREF
  LONG_PTR (__stdcall *v25)(PVOID); // [rsp+60h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-11h] BYREF
  struct _UNICODE_STRING v27; // [rsp+78h] [rbp-1h] BYREF
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
      v25 = ObfDereferenceObject;
      wistd::invoke<__int64 (*)(void *),_FILE_OBJECT * &>(&v25, &Interval);
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
  v24 = 0;
  v14 = GreDeviceIoControlImpl(DeviceObject, 0x232007u, 0, 0, &v24, 8u, (unsigned int *)&Interval, 1u, 0);
  LODWORD(v10) = v14;
  if ( v14 < 0 )
  {
    WdLogSingleEntry1(2, v14);
    WdLogGlobalForLineNumber = 924;
    goto LABEL_23;
  }
  v15 = PALLOCMEM(48, 1986292807);
  v16 = PALLOCMEM(912, 1986292807);
  v17 = (WCHAR *)PALLOCMEM(DestinationString.MaximumLength, 1986292807);
  v18 = v17;
  if ( v15 && v16 && v17 )
  {
    *(_QWORD *)&v27.Length = 0;
    v27.Buffer = v17;
    v27.MaximumLength = DestinationString.MaximumLength;
    RtlCopyUnicodeString(&v27, &DestinationString);
    *(_QWORD *)(v16 + 904) = v16 + 72;
    *(_DWORD *)(v16 + 68) = 0;
    *(struct _UNICODE_STRING *)v15 = v27;
    *(_QWORD *)(v15 + 32) = v24;
    *(_QWORD *)(v16 + 16) = v15;
    *(_DWORD *)(v16 + 36) = 1;
    *(_DWORD *)(v16 + 32) = 1;
    *(_DWORD *)(v16 + 64) = -1;
    v19 = (4 * a3) ^ (*(_DWORD *)(v16 + 40) ^ (4 * a3)) & 0xFFFFFFFB | 2;
    *(_DWORD *)(v16 + 40) = v19;
    v20 = *(_QWORD *)(W32GetSessionState(v19) + 88);
    v21 = *(_QWORD *)(v20 + 1816);
    if ( v21 )
      *(_QWORD *)(v21 + 8) = v16;
    *(_QWORD *)v16 = *(_QWORD *)(v20 + 1816);
    *(_QWORD *)(v16 + 8) = 0;
    *(_QWORD *)(v20 + 1816) = v16;
    *a1 = v16;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>(&FileObject);
    return 0;
  }
  WdLogSingleEntry1(2, -1073741801);
  WdLogGlobalForLineNumber = 932;
  if ( v18 )
    GreDeleteFastMutex(v18, v22);
  if ( v16 )
    GreDeleteFastMutex((_DWORD *)v16, v22);
  if ( v15 )
    GreDeleteFastMutex((_DWORD *)v15, v22);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&__int64 ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>(&FileObject);
  return 3221225495LL;
}

```

## disassembly

```asm
0x1401350ac  mov     [rsp-8+arg_0], rbx
0x1401350b1  push    rbp
0x1401350b2  push    rdi
0x1401350b3  push    r12
0x1401350b5  push    r14
0x1401350b7  push    r15
0x1401350b9  lea     rbp, [rsp-37h]
0x1401350be  sub     rsp, 0B0h
0x1401350c5  mov     r12d, r8d
0x1401350c8  mov     rbx, rdx
0x1401350cb  mov     r15, rcx
0x1401350ce  mov     ecx, 4
0x1401350d3  call    cs:__imp_WdLogSingleEntry0
0x1401350da  nop     dword ptr [rax+rax+00h]
0x1401350df  xorps   xmm0, xmm0
0x1401350e2  mov     cs:WdLogGlobalForLineNumber, 34Dh
0x1401350ec  lea     rdx, aCdd_0; "cdd"
0x1401350f3  mov     dword ptr [rbx], 0
0x1401350f9  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1401350fd  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140135101  call    cs:__imp_RtlInitUnicodeString
0x140135108  nop     dword ptr [rax+rax+00h]
0x14013510d  xorps   xmm0, xmm0
0x140135110  lea     rdx, aRegistryMachin_23; "\\Registry\\Machine\\System\\CurrentCon"...
0x140135117  lea     rcx, [rbp+57h+DriverServiceName]; DestinationString
0x14013511b  movups  xmmword ptr [rbp+57h+DriverServiceName.Length], xmm0
0x14013511f  call    cs:__imp_RtlInitUnicodeString
0x140135126  nop     dword ptr [rax+rax+00h]
0x14013512b  mov     r8d, r12d
0x14013512e  lea     rcx, [rbp+57h+DestinationString]; String2
0x140135132  xor     edx, edx
0x140135134  call    ldevTryReferenceLoadedDisplayDriver
0x140135139  test    rax, rax
0x14013513c  jz      short loc_14013514E
0x14013513e  mov     dword ptr [rbx], 1
0x140135144  mov     [r15], rax
0x140135147  xor     eax, eax
0x140135149  jmp     loc_140135463
0x14013514e  mov     eax, cs:?gbCddLoadedPermanently@@3HC; int volatile gbCddLoadedPermanently
0x140135154  test    eax, eax
0x140135156  jz      short loc_14013515D
0x140135158  mov     dil, 1
0x14013515b  jmp     short loc_1401351B3
0x14013515d  lea     rcx, [rbp+57h+DriverServiceName]; DriverServiceName
0x140135161  call    cs:__imp_ZwLoadDriver
0x140135168  nop     dword ptr [rax+rax+00h]
0x14013516d  movsxd  rbx, eax
0x140135170  cmp     ebx, 0C000010Eh
0x140135176  jnz     short loc_14013517D
0x140135178  xor     dil, dil
0x14013517b  jmp     short loc_1401351A9
0x14013517d  test    eax, eax
0x14013517f  jns     short loc_1401351A6
0x140135181  mov     rdx, rbx
0x140135184  mov     ecx, 2
0x140135189  call    cs:__imp_WdLogSingleEntry1
0x140135190  nop     dword ptr [rax+rax+00h]
0x140135195  mov     cs:WdLogGlobalForLineNumber, 373h
0x14013519f  mov     eax, ebx
0x1401351a1  jmp     loc_140135463
0x1401351a6  mov     dil, 1
0x1401351a9  mov     cs:?gbCddLoadedPermanently@@3HC, 1; int volatile gbCddLoadedPermanently
0x1401351b3  xorps   xmm0, xmm0
0x1401351b6  lea     rdx, aDeviceCdd; "\\Device\\cdd"
0x1401351bd  lea     rcx, [rbp+57h+ObjectName]; DestinationString
0x1401351c1  movups  xmmword ptr [rbp+57h+ObjectName.Length], xmm0
0x1401351c5  call    cs:__imp_RtlInitUnicodeString
0x1401351cc  nop     dword ptr [rax+rax+00h]
0x1401351d1  xor     eax, eax
0x1401351d3  mov     [rbp+57h+DeviceObject], 0
0x1401351db  mov     [rbp+57h+FileObject], rax
0x1401351df  lea     r14d, [rax+0Ah]
0x1401351e3  test    rax, rax
0x1401351e6  jz      short loc_140135204
0x1401351e8  mov     qword ptr [rbp+57h+Interval], rax
0x1401351ec  lea     rdx, [rbp+57h+Interval]
0x1401351f0  mov     rax, cs:__imp_ObfDereferenceObject
0x1401351f7  lea     rcx, [rbp+57h+var_70]
0x1401351fb  mov     [rbp+57h+var_70], rax
0x1401351ff  call    ??$invoke@P6A_JPEAX@ZAEAPEAU_FILE_OBJECT@@@wistd@@YA_J$$QEAP6A_JPEAX@ZAEAPEAU_FILE_OBJECT@@@Z; wistd::invoke<__int64 (*)(void *),_FILE_OBJECT * &>(__int64 (*&&)(void *),_FILE_OBJECT * &)
0x140135204  lea     r9, [rbp+57h+DeviceObject]; DeviceObject
0x140135208  mov     [rbp+57h+FileObject], 0
0x140135210  lea     r8, [rbp+57h+FileObject]; FileObject
0x140135214  mov     edx, 0C0000000h; DesiredAccess
0x140135219  lea     rcx, [rbp+57h+ObjectName]; ObjectName
0x14013521d  call    cs:__imp_IoGetDeviceObjectPointer
0x140135224  nop     dword ptr [rax+rax+00h]
0x140135229  movsxd  rbx, eax
0x14013522c  test    eax, eax
0x14013522e  jns     short loc_14013527F
0x140135230  test    dil, dil
0x140135233  jnz     short loc_14013525F
0x140135235  lea     r8, [rbp+57h+Interval]; Interval
0x140135239  mov     qword ptr [rbp+57h+Interval], 0FFFFFFFFFFFF3CB0h
0x140135241  xor     edx, edx; Alertable
0x140135243  xor     ecx, ecx; WaitMode
0x140135245  call    cs:__imp_KeDelayExecutionThread
0x14013524c  nop     dword ptr [rax+rax+00h]
0x140135251  dec     r14d
0x140135254  test    r14d, r14d
0x140135257  jle     short loc_14013525F
0x140135259  mov     rax, [rbp+57h+FileObject]
0x14013525d  jmp     short loc_1401351E3
0x14013525f  mov     rdx, rbx
0x140135262  mov     ecx, 2
0x140135267  call    cs:__imp_WdLogSingleEntry1
0x14013526e  nop     dword ptr [rax+rax+00h]
0x140135273  mov     cs:WdLogGlobalForLineNumber, 396h
0x14013527d  jmp     short loc_1401352EA
0x14013527f  mov     rcx, [rbp+57h+DeviceObject]; DeviceObject
0x140135283  lea     rax, [rbp+57h+Interval]
0x140135287  mov     [rsp+0D0h+var_90], 0; int
0x14013528f  xor     r9d, r9d; InputBufferLength
0x140135292  mov     dword ptr [rsp+0D0h+var_98], 1; BOOLEAN
0x14013529a  xor     r8d, r8d; InputBuffer
0x14013529d  mov     [rsp+0D0h+var_A0], rax; unsigned int *
0x1401352a2  mov     edx, 232007h; IoControlCode
0x1401352a7  lea     rax, [rbp+57h+var_78]
0x1401352ab  mov     [rsp+0D0h+var_A8], 8; ULONG
0x1401352b3  mov     [rsp+0D0h+var_B0], rax; PVOID
0x1401352b8  mov     [rbp+57h+var_78], 0
0x1401352c0  call    ?GreDeviceIoControlImpl@@YAJPEAXK0K0KPEAKHH@Z; GreDeviceIoControlImpl(void *,ulong,void *,ulong,void *,ulong,ulong *,int,int)
0x1401352c5  movsxd  rbx, eax
0x1401352c8  test    eax, eax
0x1401352ca  jns     short loc_1401352F8
0x1401352cc  mov     rdx, rbx
0x1401352cf  mov     ecx, 2
0x1401352d4  call    cs:__imp_WdLogSingleEntry1
0x1401352db  nop     dword ptr [rax+rax+00h]
0x1401352e0  mov     cs:WdLogGlobalForLineNumber, 39Ch
0x1401352ea  lea     rcx, [rbp+57h+FileObject]
0x1401352ee  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_FILE_OBJECT@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>(void)
0x1401352f3  jmp     loc_14013519F
0x1401352f8  mov     r14d, 76646C47h
0x1401352fe  mov     ecx, 30h ; '0'
0x140135303  mov     edx, r14d
0x140135306  call    PALLOCMEM
0x14013530b  mov     edx, r14d
0x14013530e  mov     ecx, 390h
0x140135313  mov     rbx, rax
0x140135316  call    PALLOCMEM
0x14013531b  movzx   ecx, [rbp+57h+DestinationString.MaximumLength]
0x14013531f  mov     edx, r14d
0x140135322  mov     rdi, rax
0x140135325  call    PALLOCMEM
0x14013532a  mov     r14, rax
0x14013532d  test    rbx, rbx
0x140135330  jz      loc_14013540C
0x140135336  test    rdi, rdi
0x140135339  jz      loc_14013540C
0x14013533f  test    rax, rax
0x140135342  jz      loc_14013540C
0x140135348  xorps   xmm0, xmm0
0x14013534b  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x14013534f  movups  xmmword ptr [rbp+57h+var_58.Length], xmm0
0x140135353  mov     [rbp+57h+var_58.Buffer], rax
0x140135357  lea     rcx, [rbp+57h+var_58]; DestinationString
0x14013535b  movzx   eax, [rbp+57h+DestinationString.MaximumLength]
0x14013535f  mov     [rbp+57h+var_58.MaximumLength], ax
0x140135363  call    cs:__imp_RtlCopyUnicodeString
0x14013536a  nop     dword ptr [rax+rax+00h]
0x14013536f  lea     rax, [rdi+48h]
0x140135373  mov     [rdi+388h], rax
0x14013537a  mov     dword ptr [rdi+44h], 0
0x140135381  movups  xmm0, xmmword ptr [rbp+57h+var_58.Length]
0x140135385  movdqu  xmmword ptr [rbx], xmm0
0x140135389  mov     rax, [rbp+57h+var_78]
0x14013538d  mov     [rbx+20h], rax
0x140135391  lea     eax, ds:0[r12*4]
0x140135399  mov     [rdi+10h], rbx
0x14013539d  mov     ecx, eax
0x14013539f  mov     dword ptr [rdi+24h], 1
0x1401353a6  mov     dword ptr [rdi+20h], 1
0x1401353ad  mov     dword ptr [rdi+40h], 0FFFFFFFFh
0x1401353b4  xor     ecx, [rdi+28h]
0x1401353b7  and     ecx, 0FFFFFFFBh
0x1401353ba  xor     ecx, eax
0x1401353bc  or      ecx, 2
0x1401353bf  mov     [rdi+28h], ecx
0x1401353c2  call    cs:__imp_W32GetSessionState
0x1401353c9  nop     dword ptr [rax+rax+00h]
0x1401353ce  mov     rcx, [rax+58h]
0x1401353d2  mov     rax, [rcx+718h]
0x1401353d9  test    rax, rax
0x1401353dc  jz      short loc_1401353E2
0x1401353de  mov     [rax+8], rdi
0x1401353e2  mov     rax, [rcx+718h]
0x1401353e9  mov     [rdi], rax
0x1401353ec  mov     qword ptr [rdi+8], 0
0x1401353f4  mov     [rcx+718h], rdi
0x1401353fb  lea     rcx, [rbp+57h+FileObject]
0x1401353ff  mov     [r15], rdi
0x140135402  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_FILE_OBJECT@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>(void)
0x140135407  jmp     loc_140135147
0x14013540c  mov     rdx, 0FFFFFFFFC0000017h
0x140135413  mov     ecx, 2
0x140135418  call    cs:__imp_WdLogSingleEntry1
0x14013541f  nop     dword ptr [rax+rax+00h]
0x140135424  mov     cs:WdLogGlobalForLineNumber, 3A4h
0x14013542e  test    r14, r14
0x140135431  jz      short loc_14013543B
0x140135433  mov     rcx, r14; Buffer
0x140135436  call    GreDeleteFastMutex
0x14013543b  test    rdi, rdi
0x14013543e  jz      short loc_140135448
0x140135440  mov     rcx, rdi; Buffer
0x140135443  call    GreDeleteFastMutex
0x140135448  test    rbx, rbx
0x14013544b  jz      short loc_140135455
0x14013544d  mov     rcx, rbx; Buffer
0x140135450  call    GreDeleteFastMutex
0x140135455  lea     rcx, [rbp+57h+FileObject]
0x140135459  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_FILE_OBJECT@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>(void)
0x14013545e  mov     eax, 0C0000017h
0x140135463  mov     rbx, [rsp+0D0h+arg_0]
0x14013546b  add     rsp, 0B0h
0x140135472  pop     r15
0x140135474  pop     r14
0x140135476  pop     r12
0x140135478  pop     rdi
0x140135479  pop     rbp
0x14013547a  retn
```
