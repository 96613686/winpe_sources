# CVdsDiskLun::AssignDriveLetter(unsigned __int64,ushort)

- ea: `0x140029600`
- end: `0x140029857`
- name: `?AssignDriveLetter@CVdsDiskLun@@UEAAJ_KG@Z`
- size: `599`
- prototype: `__int64 __fastcall(CVdsDiskLun *this, unsigned __int64, wint_t)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140003710`
- `0x140004360`
- `0x140005630`
- `0x1400069e8`
- `0x140029600`
- `0x1400446d8`
- `0x140052e80`

## import_xrefs

- `msvcrt!towupper` at `0x1400296cb`
- `msvcrt!towupper` at `0x1400296cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140029812`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140029812`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140029687`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140029687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400297dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400297dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400297b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400297b1`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x140029707`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x140029707`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x1400297d2`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x1400297d2`
- `vdsutil!OpenDevice` at `0x14002975c`
- `vdsutil!OpenDevice` at `0x14002975c`
- `vdsutil!GetDeviceName` at `0x1400297a4`
- `vdsutil!GetDeviceName` at `0x1400297a4`
- `vdsutil!VdsTraceEx` at `0x1400296ac`
- `vdsutil!VdsTraceEx` at `0x140029725`
- `vdsutil!VdsTraceEx` at `0x140029777`
- `vdsutil!VdsTraceEx` at `0x1400297f3`
- `vdsutil!VdsTraceEx` at `0x1400296ac`
- `vdsutil!VdsTraceEx` at `0x140029725`
- `vdsutil!VdsTraceEx` at `0x140029777`
- `vdsutil!VdsTraceEx` at `0x1400297f3`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002964b`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002964b`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140029829`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140029829`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsDiskLun::AssignDriveLetter(CVdsDiskLun *this, unsigned __int64 a2, wint_t a3)
{
  signed int LastError; // ebx
  int v7; // eax
  wint_t v8; // ax
  unsigned int v9; // r8d
  int v10; // edi
  HANDLE hObject; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v13; // [rsp+28h] [rbp-D8h] BYREF
  int v14; // [rsp+30h] [rbp-D0h]
  _BYTE v15[16]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR DeviceName; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v17[40]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR TargetPath[14]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR v19[270]; // [rsp+BCh] [rbp-44h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v15, 0x5Eu, "CVdsDiskLun::AssignDriveLetter()");
  hObject = 0;
  v13 = 0;
  v14 = 0;
  LastError = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v13);
  if ( LastError >= 0 )
  {
    EnterCriticalSection(&g_GlobalCriticalSection);
    v7 = CVdsDiskLun::ValidateDiskInterfaces((CVdsDiskLun *)((char *)this - 32));
    LastError = v7;
    if ( v7 < 0 )
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::AssignDriveLetter, 1, hr=%lX", v7);
      if ( LastError == -2147212283 )
        LastError = -2147212277;
      goto LABEL_24;
    }
    v8 = towupper(a3);
    if ( (unsigned __int16)(v8 - 65) > 0x19u )
    {
      LastError = -2147211938;
      goto LABEL_24;
    }
    StringCchPrintfW(&DeviceName, 3u, L"%c:", v8);
    if ( QueryDosDeviceW(&DeviceName, TargetPath, 0x104u) )
    {
      LastError = -2147211940;
      VdsTraceEx(94, 0, "CVdsDiskLun::AssignDriveLetter, 1.5, hr=%lX", 2147755356LL);
      goto LABEL_24;
    }
    LastError = CVdsDiskLun::BuildOEMPartitionName((CVdsDiskLun *)((char *)this - 32), a2, v9, v17);
    if ( LastError < 0 )
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::AssignDriveLetter, 2, hr=%lX", (unsigned int)LastError);
      goto LABEL_24;
    }
    v10 = OpenDevice(v17, 0, &hObject);
    if ( v10 )
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::AssignDriveLetter, 3, hr=%lX", (unsigned int)LastError);
    }
    else
    {
      v10 = GetDeviceName(hObject, 0, 274, TargetPath);
      CloseHandle(hObject);
      if ( !v10 )
      {
        if ( DefineDosDeviceW(1u, &DeviceName, v19) )
        {
          LastError = 0;
          goto LABEL_24;
        }
        LastError = GetLastError();
        VdsTraceEx(94, 0, "CVdsDiskLun::AssignDriveLetter, 5, error=%lX", LastError);
        if ( LastError <= 0 )
        {
LABEL_24:
          LeaveCriticalSection(&g_GlobalCriticalSection);
          goto LABEL_25;
        }
        LastError = (unsigned __int16)LastError;
LABEL_16:
        LastError |= 0x80070000;
        goto LABEL_24;
      }
      VdsTraceEx(94, 0, "CVdsDiskLun::AssignDriveLetter, 4, hr=%lX", (unsigned int)LastError);
    }
    if ( v10 <= 0 )
    {
      LastError = v10;
      goto LABEL_24;
    }
    LastError = (unsigned __int16)v10;
    goto LABEL_16;
  }
LABEL_25:
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v13);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v15);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140029600  mov     [rsp-8+arg_18], rbx
0x140029605  push    rbp
0x140029606  push    rsi
0x140029607  push    rdi
0x140029608  push    r12
0x14002960a  push    r14
0x14002960c  lea     rbp, [rsp-1E0h]
0x140029614  sub     rsp, 2E0h
0x14002961b  mov     rax, cs:__security_cookie
0x140029622  xor     rax, rsp
0x140029625  mov     [rbp+200h+var_28], rax
0x14002962c  movzx   esi, r8w
0x140029630  mov     r14, rdx
0x140029633  mov     rdi, rcx
0x140029636  lea     r8, aCvdsdisklunAss_5; "CVdsDiskLun::AssignDriveLetter()"
0x14002963d  mov     r12d, 5Eh ; '^'
0x140029643  mov     edx, r12d
0x140029646  lea     rcx, [rsp+300h+var_2C8]
0x14002964b  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140029651  nop
0x140029652  mov     [rsp+300h+hObject], 0
0x14002965b  mov     [rsp+300h+var_2D8], 0
0x140029664  mov     [rsp+300h+var_2D0], 0
0x14002966c  lea     rcx, [rsp+300h+var_2D8]; this
0x140029671  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140029676  mov     ebx, eax
0x140029678  test    eax, eax
0x14002967a  js      loc_140029819
0x140029680  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140029687  call    cs:__imp_EnterCriticalSection
0x14002968d  nop
0x14002968e  lea     rcx, [rdi-20h]; this
0x140029692  call    ?ValidateDiskInterfaces@CVdsDiskLun@@AEAAJXZ; CVdsDiskLun::ValidateDiskInterfaces(void)
0x140029697  mov     ebx, eax
0x140029699  test    eax, eax
0x14002969b  jns     short loc_1400296C8
0x14002969d  mov     r9d, eax
0x1400296a0  lea     r8, aCvdsdisklunAss_11; "CVdsDiskLun::AssignDriveLetter, 1, hr=%"...
0x1400296a7  xor     edx, edx
0x1400296a9  mov     ecx, r12d
0x1400296ac  call    cs:__imp_VdsTraceEx
0x1400296b2  cmp     ebx, 80042405h
0x1400296b8  jnz     loc_14002980B
0x1400296be  mov     ebx, 8004240Bh
0x1400296c3  jmp     loc_14002980B
0x1400296c8  movzx   ecx, si; C
0x1400296cb  call    cs:__imp_towupper
0x1400296d1  lea     ecx, [rax-41h]
0x1400296d4  cmp     cx, 19h
0x1400296d8  ja      loc_140029806
0x1400296de  movzx   r9d, ax
0x1400296e2  lea     r8, aC; "%c:"
0x1400296e9  mov     edx, 3; unsigned __int64
0x1400296ee  lea     rcx, [rsp+300h+DeviceName]; unsigned __int16 *
0x1400296f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400296f8  mov     r8d, 104h; ucchMax
0x1400296fe  lea     rdx, [rbp+200h+TargetPath]; lpTargetPath
0x140029702  lea     rcx, [rsp+300h+DeviceName]; lpDeviceName
0x140029707  call    cs:__imp_QueryDosDeviceW
0x14002970d  test    eax, eax
0x14002970f  jz      short loc_140029730
0x140029711  mov     ebx, 8004255Ch
0x140029716  lea     r8, aCvdsdisklunAss_4; "CVdsDiskLun::AssignDriveLetter, 1.5, hr"...
0x14002971d  mov     r9d, ebx
0x140029720  xor     edx, edx
0x140029722  mov     ecx, r12d
0x140029725  call    cs:__imp_VdsTraceEx
0x14002972b  jmp     loc_14002980B
0x140029730  lea     r9, [rsp+300h+var_2B0]; unsigned __int16 *
0x140029735  mov     rdx, r14; unsigned __int64
0x140029738  lea     rcx, [rdi-20h]; this
0x14002973c  call    ?BuildOEMPartitionName@CVdsDiskLun@@AEAAJ_KKPEAG@Z; CVdsDiskLun::BuildOEMPartitionName(unsigned __int64,ulong,ushort *)
0x140029741  mov     ebx, eax
0x140029743  test    eax, eax
0x140029745  jns     short loc_140029750
0x140029747  lea     r8, aCvdsdisklunAss_3; "CVdsDiskLun::AssignDriveLetter, 2, hr=%"...
0x14002974e  jmp     short loc_14002971D
0x140029750  lea     r8, [rsp+300h+hObject]
0x140029755  xor     edx, edx
0x140029757  lea     rcx, [rsp+300h+var_2B0]
0x14002975c  call    cs:__imp_OpenDevice
0x140029762  mov     edi, eax
0x140029764  test    eax, eax
0x140029766  jz      short loc_140029793
0x140029768  lea     r8, aCvdsdisklunAss_2; "CVdsDiskLun::AssignDriveLetter, 3, hr=%"...
0x14002976f  mov     r9d, ebx
0x140029772  xor     edx, edx
0x140029774  mov     ecx, r12d
0x140029777  call    cs:__imp_VdsTraceEx
0x14002977d  test    edi, edi
0x14002977f  jg      short loc_140029788
0x140029781  mov     ebx, edi
0x140029783  jmp     loc_14002980B
0x140029788  movzx   ebx, di
0x14002978b  or      ebx, 80070000h
0x140029791  jmp     short loc_14002980B
0x140029793  lea     r9, [rbp+200h+TargetPath]
0x140029797  xor     edx, edx
0x140029799  mov     r8d, 112h
0x14002979f  mov     rcx, [rsp+300h+hObject]
0x1400297a4  call    cs:__imp_GetDeviceName
0x1400297aa  mov     edi, eax
0x1400297ac  mov     rcx, [rsp+300h+hObject]; hObject
0x1400297b1  call    cs:__imp_CloseHandle
0x1400297b7  test    edi, edi
0x1400297b9  jz      short loc_1400297C4
0x1400297bb  lea     r8, aCvdsdisklunAss_10; "CVdsDiskLun::AssignDriveLetter, 4, hr=%"...
0x1400297c2  jmp     short loc_14002976F
0x1400297c4  lea     r8, [rbp+200h+var_244]; lpTargetPath
0x1400297c8  lea     rdx, [rsp+300h+DeviceName]; lpDeviceName
0x1400297cd  mov     ecx, 1; dwFlags
0x1400297d2  call    cs:__imp_DefineDosDeviceW
0x1400297d8  test    eax, eax
0x1400297da  jnz     short loc_140029802
0x1400297dc  call    cs:__imp_GetLastError
0x1400297e2  mov     ebx, eax
0x1400297e4  mov     r9d, eax
0x1400297e7  lea     r8, aCvdsdisklunAss; "CVdsDiskLun::AssignDriveLetter, 5, erro"...
0x1400297ee  xor     edx, edx
0x1400297f0  mov     ecx, r12d
0x1400297f3  call    cs:__imp_VdsTraceEx
0x1400297f9  test    ebx, ebx
0x1400297fb  jle     short loc_14002980B
0x1400297fd  movzx   ebx, bx
0x140029800  jmp     short loc_14002978B
0x140029802  xor     ebx, ebx
0x140029804  jmp     short loc_14002980B
0x140029806  mov     ebx, 8004255Eh
0x14002980b  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140029812  call    cs:__imp_LeaveCriticalSection
0x140029818  nop
0x140029819  lea     rcx, [rsp+300h+var_2D8]; this
0x14002981e  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140029823  nop
0x140029824  lea     rcx, [rsp+300h+var_2C8]
0x140029829  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14002982f  mov     eax, ebx
0x140029831  mov     rcx, [rbp+200h+var_28]
0x140029838  xor     rcx, rsp; StackCookie
0x14002983b  call    __security_check_cookie
0x140029840  mov     rbx, [rsp+300h+arg_18]
0x140029848  add     rsp, 2E0h
0x14002984f  pop     r14
0x140029851  pop     r12
0x140029853  pop     rdi
0x140029854  pop     rsi
0x140029855  pop     rbp
0x140029856  retn
```
