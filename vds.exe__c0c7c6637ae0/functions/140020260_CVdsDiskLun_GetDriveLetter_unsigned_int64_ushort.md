# CVdsDiskLun::GetDriveLetter(unsigned __int64,ushort *)

- ea: `0x140020260`
- end: `0x14002058a`
- name: `?GetDriveLetter@CVdsDiskLun@@UEAAJ_KPEAG@Z`
- size: `810`
- prototype: `int(CVdsDiskLun *__hidden this, unsigned __int64, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140003710`
- `0x140004360`
- `0x140005630`
- `0x140020260`
- `0x1400446d8`
- `0x140052e80`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x140020460`
- `msvcrt!_wcsicmp` at `0x140020526`
- `msvcrt!_wcsicmp` at `0x140020460`
- `msvcrt!_wcsicmp` at `0x140020526`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140020545`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140020545`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140020319`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140020319`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400203f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400204ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400203f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400204ec`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x140020433`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x140020433`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x140020446`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x140020446`
- `vdsutil!OpenDevice` at `0x140020397`
- `vdsutil!OpenDevice` at `0x140020479`
- `vdsutil!OpenDevice` at `0x140020397`
- `vdsutil!OpenDevice` at `0x140020479`
- `vdsutil!GetDeviceName` at `0x1400203e8`
- `vdsutil!GetDeviceName` at `0x1400204df`
- `vdsutil!GetDeviceName` at `0x1400203e8`
- `vdsutil!GetDeviceName` at `0x1400204df`
- `vdsutil!VdsTraceEx` at `0x14002033e`
- `vdsutil!VdsTraceEx` at `0x140020380`
- `vdsutil!VdsTraceEx` at `0x1400203b8`
- `vdsutil!VdsTraceEx` at `0x14002049f`
- `vdsutil!VdsTraceEx` at `0x1400204c3`
- `vdsutil!VdsTraceEx` at `0x140020510`
- `vdsutil!VdsTraceEx` at `0x14002033e`
- `vdsutil!VdsTraceEx` at `0x140020380`
- `vdsutil!VdsTraceEx` at `0x1400203b8`
- `vdsutil!VdsTraceEx` at `0x14002049f`
- `vdsutil!VdsTraceEx` at `0x1400204c3`
- `vdsutil!VdsTraceEx` at `0x140020510`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400202aa`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400202aa`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002055c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002055c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVdsDiskLun::GetDriveLetter(CVdsDiskLun *this, __int64 a2, unsigned __int16 *a3)
{
  int v6; // ebx
  int v7; // eax
  __int64 v8; // r8
  int v9; // eax
  const char *v10; // r8
  unsigned __int16 i; // si
  int v12; // eax
  int v13; // edi
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  int v17; // [rsp+40h] [rbp-C0h]
  _BYTE v18[16]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR DeviceName[4]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR RootPathName[8]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v21[40]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR TargetPath[264]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t String2[280]; // [rsp+2D0h] [rbp+1D0h] BYREF
  wchar_t v24[284]; // [rsp+500h] [rbp+400h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v18, 0x5Eu, "CVdsDiskLun::GetDriveLetter()");
  hObject = 0;
  wcscpy(DeviceName, L"?:");
  wcscpy(RootPathName, L"?:\\");
  *a3 = 32;
  v16 = 0;
  v17 = 0;
  v6 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v16);
  if ( v6 >= 0 )
  {
    EnterCriticalSection(&g_GlobalCriticalSection);
    v7 = CVdsDiskLun::ValidateDiskInterfaces((CVdsDiskLun *)((char *)this - 32));
    v6 = v7;
    if ( v7 < 0 )
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::GetDriveLetter, 1, hr=%lX", v7);
      if ( v6 == -2147212283 )
        v6 = -2147212277;
      goto LABEL_29;
    }
    v9 = CVdsDiskLun::BuildOEMPartitionName((CVdsDiskLun *)((char *)this - 32), a2, v8, v21);
    v6 = v9;
    if ( v9 < 0 )
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::GetDriveLetter, 2, hr=%lX", v9);
LABEL_29:
      LeaveCriticalSection(&g_GlobalCriticalSection);
      goto LABEL_30;
    }
    v6 = OpenDevice(v21, 0, &hObject);
    if ( v6 )
    {
      v10 = "CVdsDiskLun::GetDriveLetter, 3, name(%S): %ld";
      goto LABEL_9;
    }
    v6 = GetDeviceName(hObject, 0, 274, String2);
    CloseHandle(hObject);
    if ( v6 )
    {
      v10 = "CVdsDiskLun::GetDriveLetter, 4, name(%S): %ld";
LABEL_9:
      VdsTraceEx(94, 0, v10, v21, v6);
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      goto LABEL_29;
    }
    v6 = 1;
    for ( i = 65; ; ++i )
    {
      if ( i > 0x5Au )
        goto LABEL_29;
      DeviceName[0] = i;
      RootPathName[0] = i;
      if ( QueryDosDeviceW(DeviceName, TargetPath, 0x104u) && GetDriveTypeW(RootPathName) != 4 )
      {
        if ( !_wcsicmp(TargetPath, String2) )
          goto LABEL_28;
        v12 = OpenDevice(TargetPath, 0, &hObject);
        v13 = v12;
        if ( v12 )
        {
          if ( v12 != 2 )
            VdsTraceEx(94, 0, "CVdsDiskLun::GetDriveLetter, 5, name(%S): %ld", DeviceName, v12);
          if ( v13 != 2 )
            goto LABEL_22;
        }
        else
        {
          v13 = GetDeviceName(hObject, 0, 274, v24);
          CloseHandle(hObject);
          if ( v13 )
          {
            if ( v13 != 2 )
            {
              VdsTraceEx(94, 0, "CVdsDiskLun::GetDriveLetter, 6, name(%S): %ld", DeviceName, v13);
LABEL_22:
              VdsTraceEx(94, 0, "CVdsDiskLun::GetDriveLetter, 7, name(%S): %ld", DeviceName, v13);
              continue;
            }
          }
          else if ( !_wcsicmp(String2, v24) )
          {
LABEL_28:
            v6 = 0;
            *a3 = i;
            goto LABEL_29;
          }
        }
      }
    }
  }
LABEL_30:
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v16);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v18);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140020260  mov     [rsp-8+arg_18], rbx
0x140020265  push    rbp
0x140020266  push    rsi
0x140020267  push    rdi
0x140020268  push    r12
0x14002026a  push    r14
0x14002026c  lea     rbp, [rsp-640h]
0x140020274  sub     rsp, 740h
0x14002027b  mov     rax, cs:__security_cookie
0x140020282  xor     rax, rsp
0x140020285  mov     [rbp+660h+var_28], rax
0x14002028c  mov     r14, r8
0x14002028f  mov     rsi, rdx
0x140020292  mov     rdi, rcx
0x140020295  lea     r8, aCvdsdisklunGet_11; "CVdsDiskLun::GetDriveLetter()"
0x14002029c  mov     r12d, 5Eh ; '^'
0x1400202a2  mov     edx, r12d
0x1400202a5  lea     rcx, [rsp+760h+var_718]
0x1400202aa  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x1400202b0  nop
0x1400202b1  mov     [rsp+760h+hObject], 0
0x1400202ba  lea     eax, [r12-1Fh]
0x1400202bf  mov     [rsp+760h+DeviceName], ax
0x1400202c4  mov     [rsp+760h+var_706], 3Ah ; ':'
0x1400202cc  mov     [rsp+760h+RootPathName], ax
0x1400202d1  mov     eax, dword ptr cs:asc_140069000+2; ":\\"
0x1400202d7  mov     [rsp+760h+var_6FE], eax
0x1400202db  movzx   eax, word ptr cs:asc_140069000+6; ""
0x1400202e2  mov     [rsp+760h+var_6FA], ax
0x1400202e7  mov     word ptr [r14], 20h ; ' '
0x1400202ed  mov     [rsp+760h+var_728], 0
0x1400202f6  mov     [rsp+760h+var_720], 0
0x1400202fe  lea     rcx, [rsp+760h+var_728]; this
0x140020303  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140020308  mov     ebx, eax
0x14002030a  test    eax, eax
0x14002030c  js      loc_14002054C
0x140020312  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140020319  call    cs:__imp_EnterCriticalSection
0x14002031f  nop
0x140020320  lea     rcx, [rdi-20h]; this
0x140020324  call    ?ValidateDiskInterfaces@CVdsDiskLun@@AEAAJXZ; CVdsDiskLun::ValidateDiskInterfaces(void)
0x140020329  mov     ebx, eax
0x14002032b  test    eax, eax
0x14002032d  jns     short loc_14002035A
0x14002032f  mov     r9d, eax
0x140020332  lea     r8, aCvdsdisklunGet_65; "CVdsDiskLun::GetDriveLetter, 1, hr=%lX"
0x140020339  xor     edx, edx
0x14002033b  mov     ecx, r12d
0x14002033e  call    cs:__imp_VdsTraceEx
0x140020344  cmp     ebx, 80042405h
0x14002034a  jnz     loc_14002053E
0x140020350  mov     ebx, 8004240Bh
0x140020355  jmp     loc_14002053E
0x14002035a  lea     r9, [rsp+760h+var_6F0]; unsigned __int16 *
0x14002035f  mov     rdx, rsi; unsigned __int64
0x140020362  lea     rcx, [rdi-20h]; this
0x140020366  call    ?BuildOEMPartitionName@CVdsDiskLun@@AEAAJ_KKPEAG@Z; CVdsDiskLun::BuildOEMPartitionName(unsigned __int64,ulong,ushort *)
0x14002036b  mov     ebx, eax
0x14002036d  test    eax, eax
0x14002036f  jns     short loc_14002038B
0x140020371  mov     r9d, eax
0x140020374  lea     r8, aCvdsdisklunGet_140; "CVdsDiskLun::GetDriveLetter, 2, hr=%lX"
0x14002037b  xor     edx, edx
0x14002037d  mov     ecx, r12d
0x140020380  call    cs:__imp_VdsTraceEx
0x140020386  jmp     loc_14002053E
0x14002038b  lea     r8, [rsp+760h+hObject]
0x140020390  xor     edx, edx
0x140020392  lea     rcx, [rsp+760h+var_6F0]
0x140020397  call    cs:__imp_OpenDevice
0x14002039d  mov     ebx, eax
0x14002039f  test    eax, eax
0x1400203a1  jz      short loc_1400203D4
0x1400203a3  lea     r8, aCvdsdisklunGet_67; "CVdsDiskLun::GetDriveLetter, 3, name(%S"...
0x1400203aa  lea     r9, [rsp+760h+var_6F0]
0x1400203af  mov     [rsp+760h+var_740], ebx
0x1400203b3  xor     edx, edx
0x1400203b5  mov     ecx, r12d
0x1400203b8  call    cs:__imp_VdsTraceEx
0x1400203be  test    ebx, ebx
0x1400203c0  jle     loc_14002053E
0x1400203c6  movzx   ebx, bx
0x1400203c9  or      ebx, 80070000h
0x1400203cf  jmp     loc_14002053E
0x1400203d4  lea     r9, [rbp+660h+String2]
0x1400203db  xor     edx, edx
0x1400203dd  mov     r8d, 112h
0x1400203e3  mov     rcx, [rsp+760h+hObject]
0x1400203e8  call    cs:__imp_GetDeviceName
0x1400203ee  mov     ebx, eax
0x1400203f0  mov     rcx, [rsp+760h+hObject]; hObject
0x1400203f5  call    cs:__imp_CloseHandle
0x1400203fb  test    ebx, ebx
0x1400203fd  jz      short loc_140020408
0x1400203ff  lea     r8, aCvdsdisklunGet_142; "CVdsDiskLun::GetDriveLetter, 4, name(%S"...
0x140020406  jmp     short loc_1400203AA
0x140020408  mov     ebx, 1
0x14002040d  lea     esi, [rbx+40h]
0x140020410  cmp     si, 5Ah ; 'Z'
0x140020414  ja      loc_14002053E
0x14002041a  mov     [rsp+760h+DeviceName], si
0x14002041f  mov     [rsp+760h+RootPathName], si
0x140020424  mov     r8d, 104h; ucchMax
0x14002042a  lea     rdx, [rbp+660h+TargetPath]; lpTargetPath
0x14002042e  lea     rcx, [rsp+760h+DeviceName]; lpDeviceName
0x140020433  call    cs:__imp_QueryDosDeviceW
0x140020439  test    eax, eax
0x14002043b  jz      loc_140020530
0x140020441  lea     rcx, [rsp+760h+RootPathName]; lpRootPathName
0x140020446  call    cs:__imp_GetDriveTypeW
0x14002044c  cmp     eax, 4
0x14002044f  jz      loc_140020530
0x140020455  lea     rdx, [rbp+660h+String2]; String2
0x14002045c  lea     rcx, [rbp+660h+TargetPath]; String1
0x140020460  call    cs:__imp__wcsicmp
0x140020466  test    eax, eax
0x140020468  jz      loc_140020538
0x14002046e  lea     r8, [rsp+760h+hObject]
0x140020473  xor     edx, edx
0x140020475  lea     rcx, [rbp+660h+TargetPath]
0x140020479  call    cs:__imp_OpenDevice
0x14002047f  mov     edi, eax
0x140020481  test    eax, eax
0x140020483  jz      short loc_1400204CB
0x140020485  cmp     eax, 2
0x140020488  jz      short loc_1400204A5
0x14002048a  mov     [rsp+760h+var_740], eax
0x14002048e  lea     r9, [rsp+760h+DeviceName]
0x140020493  lea     r8, aCvdsdisklunGet_95; "CVdsDiskLun::GetDriveLetter, 5, name(%S"...
0x14002049a  xor     edx, edx
0x14002049c  mov     ecx, r12d
0x14002049f  call    cs:__imp_VdsTraceEx
0x1400204a5  cmp     edi, 2
0x1400204a8  jz      loc_140020530
0x1400204ae  mov     [rsp+760h+var_740], edi
0x1400204b2  lea     r9, [rsp+760h+DeviceName]
0x1400204b7  lea     r8, aCvdsdisklunGet_122; "CVdsDiskLun::GetDriveLetter, 7, name(%S"...
0x1400204be  xor     edx, edx
0x1400204c0  mov     ecx, r12d
0x1400204c3  call    cs:__imp_VdsTraceEx
0x1400204c9  jmp     short loc_140020530
0x1400204cb  lea     r9, [rbp+660h+var_260]
0x1400204d2  xor     edx, edx
0x1400204d4  mov     r8d, 112h
0x1400204da  mov     rcx, [rsp+760h+hObject]
0x1400204df  call    cs:__imp_GetDeviceName
0x1400204e5  mov     edi, eax
0x1400204e7  mov     rcx, [rsp+760h+hObject]; hObject
0x1400204ec  call    cs:__imp_CloseHandle
0x1400204f2  test    edi, edi
0x1400204f4  jz      short loc_140020518
0x1400204f6  cmp     edi, 2
0x1400204f9  jz      short loc_140020530
0x1400204fb  mov     [rsp+760h+var_740], edi
0x1400204ff  lea     r9, [rsp+760h+DeviceName]
0x140020504  lea     r8, aCvdsdisklunGet_111; "CVdsDiskLun::GetDriveLetter, 6, name(%S"...
0x14002050b  xor     edx, edx
0x14002050d  mov     ecx, r12d
0x140020510  call    cs:__imp_VdsTraceEx
0x140020516  jmp     short loc_1400204AE
0x140020518  lea     rdx, [rbp+660h+var_260]; String2
0x14002051f  lea     rcx, [rbp+660h+String2]; String1
0x140020526  call    cs:__imp__wcsicmp
0x14002052c  test    eax, eax
0x14002052e  jz      short loc_140020538
0x140020530  add     si, bx
0x140020533  jmp     loc_140020410
0x140020538  xor     ebx, ebx
0x14002053a  mov     [r14], si
0x14002053e  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140020545  call    cs:__imp_LeaveCriticalSection
0x14002054b  nop
0x14002054c  lea     rcx, [rsp+760h+var_728]; this
0x140020551  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140020556  nop
0x140020557  lea     rcx, [rsp+760h+var_718]
0x14002055c  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140020562  mov     eax, ebx
0x140020564  mov     rcx, [rbp+660h+var_28]
0x14002056b  xor     rcx, rsp; StackCookie
0x14002056e  call    __security_check_cookie
0x140020573  mov     rbx, [rsp+760h+arg_18]
0x14002057b  add     rsp, 740h
0x140020582  pop     r14
0x140020584  pop     r12
0x140020586  pop     rdi
0x140020587  pop     rsi
0x140020588  pop     rbp
0x140020589  retn
```
