# ldevLoadCdd

- ea: `0x140132fac`
- end: `0x14013337c`
- name: `ldevLoadCdd`
- size: `976`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, registry_config, service_task`

## callers

- `0x14019b800`

## callees

- `0x1400492a4`
- `0x14004a0d0`
- `0x1400ab4f0`
- `0x1400fdea0`
- `0x140132fac`
- `0x14015e1cc`
- `0x1401b64b4`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140133263`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140133263`
- `ntoskrnl!KeDelayExecutionThread` at `0x140133145`
- `ntoskrnl!KeDelayExecutionThread` at `0x140133145`
- `ntoskrnl!ZwLoadDriver` at `0x140133061`
- `ntoskrnl!ZwLoadDriver` at `0x140133061`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14013311d`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14013311d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140133001`
- `ntoskrnl!RtlInitUnicodeString` at `0x14013301f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401330c5`
- `ntoskrnl!RtlInitUnicodeString` at `0x140133001`
- `ntoskrnl!RtlInitUnicodeString` at `0x14013301f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401330c5`
- `ntoskrnl!ObfDereferenceObject` at `0x1401330f0`
- `watchdog!WdLogSingleEntry0` at `0x140132fd3`
- `watchdog!WdLogSingleEntry0` at `0x140132fd3`
- `watchdog!WdLogSingleEntry1` at `0x140133089`
- `watchdog!WdLogSingleEntry1` at `0x140133167`
- `watchdog!WdLogSingleEntry1` at `0x1401331d4`
- `watchdog!WdLogSingleEntry1` at `0x140133318`
- `watchdog!WdLogSingleEntry1` at `0x140133089`
- `watchdog!WdLogSingleEntry1` at `0x140133167`
- `watchdog!WdLogSingleEntry1` at `0x1401331d4`
- `watchdog!WdLogSingleEntry1` at `0x140133318`
- `WIN32K!W32GetSessionState` at `0x1401332c2`
- `WIN32K!W32GetSessionState` at `0x1401332c2`

## string_xrefs

- `0x140133010`: `\Registry\Machine\System\CurrentControlSet\Services\cdd`

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
0x140132fac  mov     [rsp-8+arg_0], rbx
0x140132fb1  push    rbp
0x140132fb2  push    rdi
0x140132fb3  push    r12
0x140132fb5  push    r14
0x140132fb7  push    r15
0x140132fb9  lea     rbp, [rsp-37h]
0x140132fbe  sub     rsp, 0B0h
0x140132fc5  mov     r12d, r8d
0x140132fc8  mov     rbx, rdx
0x140132fcb  mov     r15, rcx
0x140132fce  mov     ecx, 4
0x140132fd3  call    cs:__imp_WdLogSingleEntry0
0x140132fda  nop     dword ptr [rax+rax+00h]
0x140132fdf  xorps   xmm0, xmm0
0x140132fe2  mov     cs:WdLogGlobalForLineNumber, 34Dh
0x140132fec  lea     rdx, aCdd_0; "cdd"
0x140132ff3  mov     dword ptr [rbx], 0
0x140132ff9  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140132ffd  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140133001  call    cs:__imp_RtlInitUnicodeString
0x140133008  nop     dword ptr [rax+rax+00h]
0x14013300d  xorps   xmm0, xmm0
0x140133010  lea     rdx, aRegistryMachin_23; "\\Registry\\Machine\\System\\CurrentCon"...
0x140133017  lea     rcx, [rbp+57h+DriverServiceName]; DestinationString
0x14013301b  movups  xmmword ptr [rbp+57h+DriverServiceName.Length], xmm0
0x14013301f  call    cs:__imp_RtlInitUnicodeString
0x140133026  nop     dword ptr [rax+rax+00h]
0x14013302b  mov     r8d, r12d
0x14013302e  lea     rcx, [rbp+57h+DestinationString]; String2
0x140133032  xor     edx, edx
0x140133034  call    ldevTryReferenceLoadedDisplayDriver
0x140133039  test    rax, rax
0x14013303c  jz      short loc_14013304E
0x14013303e  mov     dword ptr [rbx], 1
0x140133044  mov     [r15], rax
0x140133047  xor     eax, eax
0x140133049  jmp     loc_140133363
0x14013304e  mov     eax, cs:?gbCddLoadedPermanently@@3HC; int volatile gbCddLoadedPermanently
0x140133054  test    eax, eax
0x140133056  jz      short loc_14013305D
0x140133058  mov     dil, 1
0x14013305b  jmp     short loc_1401330B3
0x14013305d  lea     rcx, [rbp+57h+DriverServiceName]; DriverServiceName
0x140133061  call    cs:__imp_ZwLoadDriver
0x140133068  nop     dword ptr [rax+rax+00h]
0x14013306d  movsxd  rbx, eax
0x140133070  cmp     ebx, 0C000010Eh
0x140133076  jnz     short loc_14013307D
0x140133078  xor     dil, dil
0x14013307b  jmp     short loc_1401330A9
0x14013307d  test    eax, eax
0x14013307f  jns     short loc_1401330A6
0x140133081  mov     rdx, rbx
0x140133084  mov     ecx, 2
0x140133089  call    cs:__imp_WdLogSingleEntry1
0x140133090  nop     dword ptr [rax+rax+00h]
0x140133095  mov     cs:WdLogGlobalForLineNumber, 373h
0x14013309f  mov     eax, ebx
0x1401330a1  jmp     loc_140133363
0x1401330a6  mov     dil, 1
0x1401330a9  mov     cs:?gbCddLoadedPermanently@@3HC, 1; int volatile gbCddLoadedPermanently
0x1401330b3  xorps   xmm0, xmm0
0x1401330b6  lea     rdx, aDeviceCdd; "\\Device\\cdd"
0x1401330bd  lea     rcx, [rbp+57h+ObjectName]; DestinationString
0x1401330c1  movups  xmmword ptr [rbp+57h+ObjectName.Length], xmm0
0x1401330c5  call    cs:__imp_RtlInitUnicodeString
0x1401330cc  nop     dword ptr [rax+rax+00h]
0x1401330d1  xor     eax, eax
0x1401330d3  mov     [rbp+57h+DeviceObject], 0
0x1401330db  mov     [rbp+57h+FileObject], rax
0x1401330df  lea     r14d, [rax+0Ah]
0x1401330e3  test    rax, rax
0x1401330e6  jz      short loc_140133104
0x1401330e8  mov     qword ptr [rbp+57h+Interval], rax
0x1401330ec  lea     rdx, [rbp+57h+Interval]
0x1401330f0  mov     rax, cs:__imp_ObfDereferenceObject
0x1401330f7  lea     rcx, [rbp+57h+var_70]
0x1401330fb  mov     [rbp+57h+var_70], rax
0x1401330ff  call    ??$invoke@P6A_JPEAX@ZAEAPEAU_FILE_OBJECT@@@wistd@@YA_J$$QEAP6A_JPEAX@ZAEAPEAU_FILE_OBJECT@@@Z; wistd::invoke<__int64 (*)(void *),_FILE_OBJECT * &>(__int64 (*&&)(void *),_FILE_OBJECT * &)
0x140133104  lea     r9, [rbp+57h+DeviceObject]; DeviceObject
0x140133108  mov     [rbp+57h+FileObject], 0
0x140133110  lea     r8, [rbp+57h+FileObject]; FileObject
0x140133114  mov     edx, 0C0000000h; DesiredAccess
0x140133119  lea     rcx, [rbp+57h+ObjectName]; ObjectName
0x14013311d  call    cs:__imp_IoGetDeviceObjectPointer
0x140133124  nop     dword ptr [rax+rax+00h]
0x140133129  movsxd  rbx, eax
0x14013312c  test    eax, eax
0x14013312e  jns     short loc_14013317F
0x140133130  test    dil, dil
0x140133133  jnz     short loc_14013315F
0x140133135  lea     r8, [rbp+57h+Interval]; Interval
0x140133139  mov     qword ptr [rbp+57h+Interval], 0FFFFFFFFFFFF3CB0h
0x140133141  xor     edx, edx; Alertable
0x140133143  xor     ecx, ecx; WaitMode
0x140133145  call    cs:__imp_KeDelayExecutionThread
0x14013314c  nop     dword ptr [rax+rax+00h]
0x140133151  dec     r14d
0x140133154  test    r14d, r14d
0x140133157  jle     short loc_14013315F
0x140133159  mov     rax, [rbp+57h+FileObject]
0x14013315d  jmp     short loc_1401330E3
0x14013315f  mov     rdx, rbx
0x140133162  mov     ecx, 2
0x140133167  call    cs:__imp_WdLogSingleEntry1
0x14013316e  nop     dword ptr [rax+rax+00h]
0x140133173  mov     cs:WdLogGlobalForLineNumber, 396h
0x14013317d  jmp     short loc_1401331EA
0x14013317f  mov     rcx, [rbp+57h+DeviceObject]; DeviceObject
0x140133183  lea     rax, [rbp+57h+Interval]
0x140133187  mov     [rsp+0D0h+var_90], 0; int
0x14013318f  xor     r9d, r9d; InputBufferLength
0x140133192  mov     dword ptr [rsp+0D0h+var_98], 1; BOOLEAN
0x14013319a  xor     r8d, r8d; InputBuffer
0x14013319d  mov     [rsp+0D0h+var_A0], rax; unsigned int *
0x1401331a2  mov     edx, 232007h; IoControlCode
0x1401331a7  lea     rax, [rbp+57h+var_78]
0x1401331ab  mov     [rsp+0D0h+var_A8], 8; ULONG
0x1401331b3  mov     [rsp+0D0h+var_B0], rax; PVOID
0x1401331b8  mov     [rbp+57h+var_78], 0
0x1401331c0  call    ?GreDeviceIoControlImpl@@YAJPEAXK0K0KPEAKHH@Z; GreDeviceIoControlImpl(void *,ulong,void *,ulong,void *,ulong,ulong *,int,int)
0x1401331c5  movsxd  rbx, eax
0x1401331c8  test    eax, eax
0x1401331ca  jns     short loc_1401331F8
0x1401331cc  mov     rdx, rbx
0x1401331cf  mov     ecx, 2
0x1401331d4  call    cs:__imp_WdLogSingleEntry1
0x1401331db  nop     dword ptr [rax+rax+00h]
0x1401331e0  mov     cs:WdLogGlobalForLineNumber, 39Ch
0x1401331ea  lea     rcx, [rbp+57h+FileObject]
0x1401331ee  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_FILE_OBJECT@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>(void)
0x1401331f3  jmp     loc_14013309F
0x1401331f8  mov     r14d, 76646C47h
0x1401331fe  mov     ecx, 30h ; '0'
0x140133203  mov     edx, r14d
0x140133206  call    PALLOCMEM
0x14013320b  mov     edx, r14d
0x14013320e  mov     ecx, 390h
0x140133213  mov     rbx, rax
0x140133216  call    PALLOCMEM
0x14013321b  movzx   ecx, [rbp+57h+DestinationString.MaximumLength]
0x14013321f  mov     edx, r14d
0x140133222  mov     rdi, rax
0x140133225  call    PALLOCMEM
0x14013322a  mov     r14, rax
0x14013322d  test    rbx, rbx
0x140133230  jz      loc_14013330C
0x140133236  test    rdi, rdi
0x140133239  jz      loc_14013330C
0x14013323f  test    rax, rax
0x140133242  jz      loc_14013330C
0x140133248  xorps   xmm0, xmm0
0x14013324b  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x14013324f  movups  xmmword ptr [rbp+57h+var_58.Length], xmm0
0x140133253  mov     [rbp+57h+var_58.Buffer], rax
0x140133257  lea     rcx, [rbp+57h+var_58]; DestinationString
0x14013325b  movzx   eax, [rbp+57h+DestinationString.MaximumLength]
0x14013325f  mov     [rbp+57h+var_58.MaximumLength], ax
0x140133263  call    cs:__imp_RtlCopyUnicodeString
0x14013326a  nop     dword ptr [rax+rax+00h]
0x14013326f  lea     rax, [rdi+48h]
0x140133273  mov     [rdi+388h], rax
0x14013327a  mov     dword ptr [rdi+44h], 0
0x140133281  movups  xmm0, xmmword ptr [rbp+57h+var_58.Length]
0x140133285  movdqu  xmmword ptr [rbx], xmm0
0x140133289  mov     rax, [rbp+57h+var_78]
0x14013328d  mov     [rbx+20h], rax
0x140133291  lea     eax, ds:0[r12*4]
0x140133299  mov     [rdi+10h], rbx
0x14013329d  mov     ecx, eax
0x14013329f  mov     dword ptr [rdi+24h], 1
0x1401332a6  mov     dword ptr [rdi+20h], 1
0x1401332ad  mov     dword ptr [rdi+40h], 0FFFFFFFFh
0x1401332b4  xor     ecx, [rdi+28h]
0x1401332b7  and     ecx, 0FFFFFFFBh
0x1401332ba  xor     ecx, eax
0x1401332bc  or      ecx, 2
0x1401332bf  mov     [rdi+28h], ecx
0x1401332c2  call    cs:__imp_W32GetSessionState
0x1401332c9  nop     dword ptr [rax+rax+00h]
0x1401332ce  mov     rcx, [rax+58h]
0x1401332d2  mov     rax, [rcx+718h]
0x1401332d9  test    rax, rax
0x1401332dc  jz      short loc_1401332E2
0x1401332de  mov     [rax+8], rdi
0x1401332e2  mov     rax, [rcx+718h]
0x1401332e9  mov     [rdi], rax
0x1401332ec  mov     qword ptr [rdi+8], 0
0x1401332f4  mov     [rcx+718h], rdi
0x1401332fb  lea     rcx, [rbp+57h+FileObject]
0x1401332ff  mov     [r15], rdi
0x140133302  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_FILE_OBJECT@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>(void)
0x140133307  jmp     loc_140133047
0x14013330c  mov     rdx, 0FFFFFFFFC0000017h
0x140133313  mov     ecx, 2
0x140133318  call    cs:__imp_WdLogSingleEntry1
0x14013331f  nop     dword ptr [rax+rax+00h]
0x140133324  mov     cs:WdLogGlobalForLineNumber, 3A4h
0x14013332e  test    r14, r14
0x140133331  jz      short loc_14013333B
0x140133333  mov     rcx, r14; Buffer
0x140133336  call    GreDeleteFastMutex
0x14013333b  test    rdi, rdi
0x14013333e  jz      short loc_140133348
0x140133340  mov     rcx, rdi; Buffer
0x140133343  call    GreDeleteFastMutex
0x140133348  test    rbx, rbx
0x14013334b  jz      short loc_140133355
0x14013334d  mov     rcx, rbx; Buffer
0x140133350  call    GreDeleteFastMutex
0x140133355  lea     rcx, [rbp+57h+FileObject]
0x140133359  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_FILE_OBJECT@@$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_OBJECT *,__int64 (void *),&ObfDereferenceObject(void *),wistd::integral_constant<unsigned __int64,0>,_FILE_OBJECT *,_FILE_OBJECT *,0,std::nullptr_t>>>(void)
0x14013335e  mov     eax, 0C0000017h
0x140133363  mov     rbx, [rsp+0D0h+arg_0]
0x14013336b  add     rsp, 0B0h
0x140133372  pop     r15
0x140133374  pop     r14
0x140133376  pop     r12
0x140133378  pop     rdi
0x140133379  pop     rbp
0x14013337a  retn
```
