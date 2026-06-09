# PfXpContextStart

- ea: `0x180065770`
- end: `0x18006593a`
- name: `PfXpContextStart`
- size: `458`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006a020`

## callees

- `0x180039490`
- `0x180058b30`
- `0x180065770`
- `0x180067f88`
- `0x18006ed1c`
- `0x180071c64`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800657c5`
- `ntdll!RtlInitUnicodeString` at `0x180065820`
- `ntdll!RtlInitUnicodeString` at `0x1800657c5`
- `ntdll!RtlInitUnicodeString` at `0x180065820`
- `ntdll!NtOpenEvent` at `0x1800657fe`
- `ntdll!NtOpenEvent` at `0x180065858`
- `ntdll!NtOpenEvent` at `0x1800657fe`
- `ntdll!NtOpenEvent` at `0x180065858`
- `ntdll!RtlNtStatusToDosError` at `0x18006580a`
- `ntdll!RtlNtStatusToDosError` at `0x18006580a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065895`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180065920`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180065920`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180065883`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180065883`

## string_xrefs

- `0x180065815`: `\KernelObjects\PrefetchTracesReady`

## pseudocode

```c
DWORD __fastcall PfXpContextStart(char *Context, __int64 a2, __int64 a3)
{
  DWORD result; // eax
  int v6; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  __int64 v8; // rcx
  struct _TP_TIMER *v9; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  struct _FILETIME pftDueTime; // [rsp+88h] [rbp+18h] BYREF

  pftDueTime = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  result = PfXpParametersRead(Context + 368);
  if ( !result )
  {
    RtlInitUnicodeString(&DestinationString, L"\\KernelObjects\\SuperfetchParametersChanged");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v6 = NtOpenEvent((PHANDLE)Context + 1, 0x120001u, &ObjectAttributes);
    if ( v6 < 0 )
      return RtlNtStatusToDosError(v6);
    RtlInitUnicodeString(&DestinationString, L"\\KernelObjects\\PrefetchTracesReady");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v6 = NtOpenEvent((PHANDLE)Context, 0x120001u, &ObjectAttributes);
    if ( v6 < 0 )
      return RtlNtStatusToDosError(v6);
    *((_QWORD *)Context + 48) = a3;
    PfXpRefreshIdleTasks(0, Context, 0);
    ThreadpoolTimer = CreateThreadpoolTimer(PfXpRefreshIdleTasks, Context, 0);
    *((_QWORD *)Context + 45) = ThreadpoolTimer;
    if ( !ThreadpoolTimer )
      return GetLastError();
    result = PfsMultiStringContextLoad(Context + 392, hKey, L"HiPriSections", 7, 1);
    if ( result )
    {
      if ( result != 2 )
        return result;
      PfsMultiStringContextCleanup(Context + 392);
      *(_OWORD *)(Context + 392) = 0;
      *((_QWORD *)Context + 51) = 0;
    }
    result = PfSvPowerNotifyRegister(v8, 0, 3);
    if ( !result )
    {
      v9 = (struct _TP_TIMER *)*((_QWORD *)Context + 45);
      *((_DWORD *)Context + 104) |= 1u;
      pftDueTime = (struct _FILETIME)-864000000000LL;
      SetThreadpoolTimer(v9, &pftDueTime, 0x5265C00u, 0);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180065770  mov     [rsp-8+arg_0], rbx
0x180065775  mov     [rsp-8+arg_10], rdi
0x18006577a  mov     qword ptr [rsp-8+pftDueTime.dwLowDateTime], rdx
0x18006577f  push    rbp
0x180065780  mov     rbp, rsp
0x180065783  sub     rsp, 70h
0x180065787  xorps   xmm0, xmm0
0x18006578a  mov     rbx, rcx
0x18006578d  xor     eax, eax
0x18006578f  add     rcx, 170h
0x180065796  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18006579a  mov     rdi, r8
0x18006579d  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], rax
0x1800657a1  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800657a5  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800657a9  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800657ad  call    PfXpParametersRead
0x1800657b2  test    eax, eax
0x1800657b4  jnz     loc_180065928
0x1800657ba  lea     rdx, aKernelobjectsS_0; "\\KernelObjects\\SuperfetchParametersCh"...
0x1800657c1  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800657c5  call    cs:__imp_RtlInitUnicodeString
0x1800657cb  lea     rax, [rbp+DestinationString]
0x1800657cf  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800657d6  xorps   xmm0, xmm0
0x1800657d9  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800657dd  lea     rcx, [rbx+8]; EventHandle
0x1800657e1  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800657e9  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800657ed  mov     [rbp+ObjectAttributes.Attributes], 0
0x1800657f4  mov     edx, 120001h; DesiredAccess
0x1800657f9  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800657fe  call    cs:__imp_NtOpenEvent
0x180065804  test    eax, eax
0x180065806  jns     short loc_180065815
0x180065808  mov     ecx, eax; Status
0x18006580a  call    cs:__imp_RtlNtStatusToDosError
0x180065810  jmp     loc_180065928
0x180065815  lea     rdx, aKernelobjectsP; "\\KernelObjects\\PrefetchTracesReady"
0x18006581c  lea     rcx, [rbp+DestinationString]; DestinationString
0x180065820  call    cs:__imp_RtlInitUnicodeString
0x180065826  lea     rax, [rbp+DestinationString]
0x18006582a  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180065831  xorps   xmm0, xmm0
0x180065834  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180065838  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18006583c  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180065844  mov     edx, 120001h; DesiredAccess
0x180065849  mov     [rbp+ObjectAttributes.Attributes], 0
0x180065850  mov     rcx, rbx; EventHandle
0x180065853  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180065858  call    cs:__imp_NtOpenEvent
0x18006585e  test    eax, eax
0x180065860  js      short loc_180065808
0x180065862  xor     r8d, r8d; Timer
0x180065865  mov     [rbx+180h], rdi
0x18006586c  mov     rdx, rbx; Context
0x18006586f  xor     ecx, ecx; Instance
0x180065871  call    PfXpRefreshIdleTasks
0x180065876  xor     r8d, r8d; pcbe
0x180065879  lea     rcx, PfXpRefreshIdleTasks; pfnti
0x180065880  mov     rdx, rbx; pv
0x180065883  call    cs:__imp_CreateThreadpoolTimer
0x180065889  mov     [rbx+168h], rax
0x180065890  test    rax, rax
0x180065893  jnz     short loc_1800658A0
0x180065895  call    cs:__imp_GetLastError
0x18006589b  jmp     loc_180065928
0x1800658a0  mov     rdx, cs:hKey
0x1800658a7  lea     rdi, [rbx+188h]
0x1800658ae  mov     rcx, rdi
0x1800658b1  mov     [rsp+70h+var_50], 1
0x1800658b9  mov     r9d, 7
0x1800658bf  lea     r8, aHiprisections; "HiPriSections"
0x1800658c6  call    PfsMultiStringContextLoad
0x1800658cb  test    eax, eax
0x1800658cd  jz      short loc_1800658E8
0x1800658cf  cmp     eax, 2
0x1800658d2  jnz     short loc_180065928
0x1800658d4  mov     rcx, rdi
0x1800658d7  call    PfsMultiStringContextCleanup
0x1800658dc  xorps   xmm0, xmm0
0x1800658df  xor     eax, eax
0x1800658e1  movups  xmmword ptr [rdi], xmm0
0x1800658e4  mov     [rdi+10h], rax
0x1800658e8  xor     edx, edx
0x1800658ea  lea     r8d, [rdx+3]
0x1800658ee  call    PfSvPowerNotifyRegister
0x1800658f3  test    eax, eax
0x1800658f5  jnz     short loc_180065928
0x1800658f7  mov     rcx, [rbx+168h]; pti
0x1800658fe  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x180065902  or      dword ptr [rbx+1A0h], 1
0x180065909  mov     rax, 0FFFFFF36D5964000h
0x180065913  xor     r9d, r9d; msWindowLength
0x180065916  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], rax
0x18006591a  mov     r8d, 5265C00h; msPeriod
0x180065920  call    cs:__imp_SetThreadpoolTimer
0x180065926  xor     eax, eax
0x180065928  lea     r11, [rsp+70h+var_s0]
0x18006592d  mov     rbx, [r11+10h]
0x180065931  mov     rdi, [r11+20h]
0x180065935  mov     rsp, r11
0x180065938  pop     rbp
0x180065939  retn
```
