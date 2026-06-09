# CVdsDiskLun::DeleteDriveLetter(unsigned __int64,ushort)

- ea: `0x140029a70`
- end: `0x140029ced`
- name: `?DeleteDriveLetter@CVdsDiskLun@@UEAAJ_KG@Z`
- size: `637`
- prototype: `int(CVdsDiskLun *__hidden this, unsigned __int64, unsigned __int16)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140003710`
- `0x140004360`
- `0x140005630`
- `0x1400069e8`
- `0x140029a70`
- `0x1400446d8`
- `0x140052e80`

## import_xrefs

- `msvcrt!towupper` at `0x140029b3b`
- `msvcrt!towupper` at `0x140029b3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140029ca8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140029ca8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140029af7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140029af7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029c23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029c55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029c23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029c55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140029be0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140029be0`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x140029c19`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x140029c4b`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x140029c19`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x140029c4b`
- `vdsutil!OpenDevice` at `0x140029b85`
- `vdsutil!OpenDevice` at `0x140029b85`
- `vdsutil!GetDeviceName` at `0x140029bd3`
- `vdsutil!GetDeviceName` at `0x140029bd3`
- `vdsutil!VdsTraceEx` at `0x140029b1c`
- `vdsutil!VdsTraceEx` at `0x140029ba6`
- `vdsutil!VdsTraceEx` at `0x140029c39`
- `vdsutil!VdsTraceEx` at `0x140029c6c`
- `vdsutil!VdsTraceEx` at `0x140029c9a`
- `vdsutil!VdsTraceEx` at `0x140029b1c`
- `vdsutil!VdsTraceEx` at `0x140029ba6`
- `vdsutil!VdsTraceEx` at `0x140029c39`
- `vdsutil!VdsTraceEx` at `0x140029c6c`
- `vdsutil!VdsTraceEx` at `0x140029c9a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140029abb`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140029abb`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140029cbf`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140029cbf`

## string_xrefs

- `0x140029b91`: `CVdsDiskLun::DeleteDriveLetter, 3, name(%S): %ld`
- `0x140029bea`: `CVdsDiskLun::DeleteDriveLetter, 4, name(%S): %ld`
- `0x140029aa6`: `CVdsDiskLun::DeleteDriveLetter()`
- `0x140029b10`: `CVdsDiskLun::DeleteDriveLetter, 1, hr=%lX`
- `0x140029c8e`: `CVdsDiskLun::DeleteDriveLetter, 1.5, hr=%lX`
- `0x140029b6d`: `CVdsDiskLun::DeleteDriveLetter, 2, hr=%lX`
- `0x140029c2c`: `CVdsDiskLun::DeleteDriveLetter, 5, error=%ld`
- `0x140029c60`: `CVdsDiskLun::DeleteDriveLetter, 6, error=%ld`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVdsDiskLun::DeleteDriveLetter(CVdsDiskLun *this, __int64 a2, wint_t a3)
{
  int v6; // ebx
  int v7; // eax
  wint_t v8; // ax
  unsigned int v9; // esi
  int v10; // eax
  const char *v11; // r8
  DWORD LastError; // eax
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+38h] [rbp-C8h] BYREF
  int v16; // [rsp+40h] [rbp-C0h]
  _BYTE v17[16]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR DeviceName; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR v19[40]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[28]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR TargetPath[270]; // [rsp+CCh] [rbp-34h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v17, 0x5Eu, "CVdsDiskLun::DeleteDriveLetter()");
  hObject = 0;
  v15 = 0;
  v16 = 0;
  v6 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v15);
  if ( v6 >= 0 )
  {
    EnterCriticalSection(&g_GlobalCriticalSection);
    v7 = CVdsDiskLun::ValidateDiskInterfaces((CVdsDiskLun *)((char *)this - 32));
    v6 = v7;
    if ( v7 < 0 )
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::DeleteDriveLetter, 1, hr=%lX", v7);
      if ( v6 == -2147212283 )
        v6 = -2147212277;
      goto LABEL_21;
    }
    v8 = towupper(a3);
    v9 = v8;
    if ( (unsigned __int16)(v8 - 65) > 0x19u )
    {
      v6 = -2147211938;
      VdsTraceEx(94, 0, "CVdsDiskLun::DeleteDriveLetter, 1.5, hr=%lX", 2147755358LL);
      goto LABEL_21;
    }
    v10 = CVdsDiskLun::BuildOEMPartitionName((CVdsDiskLun *)((char *)this - 32), a2, (unsigned int)v8 - 65, v19);
    v6 = v10;
    if ( v10 < 0 )
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::DeleteDriveLetter, 2, hr=%lX", (unsigned int)v10);
LABEL_21:
      LeaveCriticalSection(&g_GlobalCriticalSection);
      goto LABEL_22;
    }
    v6 = OpenDevice(v19, 0, &hObject);
    if ( v6 )
    {
      v11 = "CVdsDiskLun::DeleteDriveLetter, 3, name(%S): %ld";
    }
    else
    {
      v6 = GetDeviceName(hObject, 0, 274, v20);
      CloseHandle(hObject);
      if ( !v6 )
      {
        StringCchPrintfW(&DeviceName, 3u, L"%c:", v9);
        if ( DefineDosDeviceW(3u, &DeviceName, TargetPath)
          || (LastError = GetLastError(),
              VdsTraceEx(94, 2, "CVdsDiskLun::DeleteDriveLetter, 5, error=%ld", LastError),
              DefineDosDeviceW(3u, &DeviceName, v19)) )
        {
          v6 = 0;
          goto LABEL_21;
        }
        v6 = GetLastError();
        VdsTraceEx(94, 0, "CVdsDiskLun::DeleteDriveLetter, 6, error=%ld", v6);
        if ( v6 == 2 )
        {
          v6 = -2147211938;
          goto LABEL_21;
        }
LABEL_11:
        if ( v6 > 0 )
          v6 = (unsigned __int16)v6 | 0x80070000;
        goto LABEL_21;
      }
      v11 = "CVdsDiskLun::DeleteDriveLetter, 4, name(%S): %ld";
    }
    VdsTraceEx(94, 0, v11, v19, v6);
    goto LABEL_11;
  }
LABEL_22:
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v15);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v17);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140029a70  mov     [rsp-8+arg_18], rbx
0x140029a75  push    rbp
0x140029a76  push    rsi
0x140029a77  push    rdi
0x140029a78  push    r12
0x140029a7a  push    r14
0x140029a7c  lea     rbp, [rsp-1F0h]
0x140029a84  sub     rsp, 2F0h
0x140029a8b  mov     rax, cs:__security_cookie
0x140029a92  xor     rax, rsp
0x140029a95  mov     [rbp+210h+var_28], rax
0x140029a9c  movzx   esi, r8w
0x140029aa0  mov     r14, rdx
0x140029aa3  mov     rdi, rcx
0x140029aa6  lea     r8, aCvdsdisklunDel_2; "CVdsDiskLun::DeleteDriveLetter()"
0x140029aad  mov     r12d, 5Eh ; '^'
0x140029ab3  mov     edx, r12d
0x140029ab6  lea     rcx, [rsp+310h+var_2C8]
0x140029abb  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140029ac1  nop
0x140029ac2  mov     [rsp+310h+hObject], 0
0x140029acb  mov     [rsp+310h+var_2D8], 0
0x140029ad4  mov     [rsp+310h+var_2D0], 0
0x140029adc  lea     rcx, [rsp+310h+var_2D8]; this
0x140029ae1  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140029ae6  mov     ebx, eax
0x140029ae8  test    eax, eax
0x140029aea  js      loc_140029CAF
0x140029af0  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140029af7  call    cs:__imp_EnterCriticalSection
0x140029afd  nop
0x140029afe  lea     rcx, [rdi-20h]; this
0x140029b02  call    ?ValidateDiskInterfaces@CVdsDiskLun@@AEAAJXZ; CVdsDiskLun::ValidateDiskInterfaces(void)
0x140029b07  mov     ebx, eax
0x140029b09  test    eax, eax
0x140029b0b  jns     short loc_140029B38
0x140029b0d  mov     r9d, eax
0x140029b10  lea     r8, aCvdsdisklunDel_5; "CVdsDiskLun::DeleteDriveLetter, 1, hr=%"...
0x140029b17  xor     edx, edx
0x140029b19  mov     ecx, r12d
0x140029b1c  call    cs:__imp_VdsTraceEx
0x140029b22  cmp     ebx, 80042405h
0x140029b28  jnz     loc_140029CA1
0x140029b2e  mov     ebx, 8004240Bh
0x140029b33  jmp     loc_140029CA1
0x140029b38  movzx   ecx, si; C
0x140029b3b  call    cs:__imp_towupper
0x140029b41  movzx   esi, ax
0x140029b44  lea     r8d, [rsi-41h]; unsigned int
0x140029b48  cmp     r8w, 19h
0x140029b4d  ja      loc_140029C86
0x140029b53  lea     r9, [rsp+310h+var_2B0]; unsigned __int16 *
0x140029b58  mov     rdx, r14; unsigned __int64
0x140029b5b  lea     rcx, [rdi-20h]; this
0x140029b5f  call    ?BuildOEMPartitionName@CVdsDiskLun@@AEAAJ_KKPEAG@Z; CVdsDiskLun::BuildOEMPartitionName(unsigned __int64,ulong,ushort *)
0x140029b64  mov     ebx, eax
0x140029b66  test    eax, eax
0x140029b68  jns     short loc_140029B79
0x140029b6a  mov     r9d, eax
0x140029b6d  lea     r8, aCvdsdisklunDel_8; "CVdsDiskLun::DeleteDriveLetter, 2, hr=%"...
0x140029b74  jmp     loc_140029C95
0x140029b79  lea     r8, [rsp+310h+hObject]
0x140029b7e  xor     edx, edx
0x140029b80  lea     rcx, [rsp+310h+var_2B0]
0x140029b85  call    cs:__imp_OpenDevice
0x140029b8b  mov     ebx, eax
0x140029b8d  test    eax, eax
0x140029b8f  jz      short loc_140029BC2
0x140029b91  lea     r8, aCvdsdisklunDel_1; "CVdsDiskLun::DeleteDriveLetter, 3, name"...
0x140029b98  lea     r9, [rsp+310h+var_2B0]
0x140029b9d  mov     [rsp+310h+var_2F0], ebx
0x140029ba1  xor     edx, edx
0x140029ba3  mov     ecx, r12d
0x140029ba6  call    cs:__imp_VdsTraceEx
0x140029bac  test    ebx, ebx
0x140029bae  jle     loc_140029CA1
0x140029bb4  movzx   ebx, bx
0x140029bb7  or      ebx, 80070000h
0x140029bbd  jmp     loc_140029CA1
0x140029bc2  lea     r9, [rbp+210h+var_260]
0x140029bc6  xor     edx, edx
0x140029bc8  mov     r8d, 112h
0x140029bce  mov     rcx, [rsp+310h+hObject]
0x140029bd3  call    cs:__imp_GetDeviceName
0x140029bd9  mov     ebx, eax
0x140029bdb  mov     rcx, [rsp+310h+hObject]; hObject
0x140029be0  call    cs:__imp_CloseHandle
0x140029be6  test    ebx, ebx
0x140029be8  jz      short loc_140029BF3
0x140029bea  lea     r8, aCvdsdisklunDel_16; "CVdsDiskLun::DeleteDriveLetter, 4, name"...
0x140029bf1  jmp     short loc_140029B98
0x140029bf3  mov     r9d, esi
0x140029bf6  lea     r8, aC; "%c:"
0x140029bfd  mov     ebx, 3
0x140029c02  mov     edx, ebx; unsigned __int64
0x140029c04  lea     rcx, [rsp+310h+DeviceName]; unsigned __int16 *
0x140029c09  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140029c0e  lea     r8, [rbp+210h+TargetPath]; lpTargetPath
0x140029c12  lea     rdx, [rsp+310h+DeviceName]; lpDeviceName
0x140029c17  mov     ecx, ebx; dwFlags
0x140029c19  call    cs:__imp_DefineDosDeviceW
0x140029c1f  test    eax, eax
0x140029c21  jnz     short loc_140029C82
0x140029c23  call    cs:__imp_GetLastError
0x140029c29  mov     r9d, eax
0x140029c2c  lea     r8, aCvdsdisklunDel_4; "CVdsDiskLun::DeleteDriveLetter, 5, erro"...
0x140029c33  lea     edx, [rbx-1]
0x140029c36  mov     ecx, r12d
0x140029c39  call    cs:__imp_VdsTraceEx
0x140029c3f  lea     r8, [rsp+310h+var_2B0]; lpTargetPath
0x140029c44  lea     rdx, [rsp+310h+DeviceName]; lpDeviceName
0x140029c49  mov     ecx, ebx; dwFlags
0x140029c4b  call    cs:__imp_DefineDosDeviceW
0x140029c51  test    eax, eax
0x140029c53  jnz     short loc_140029C82
0x140029c55  call    cs:__imp_GetLastError
0x140029c5b  mov     ebx, eax
0x140029c5d  mov     r9d, eax
0x140029c60  lea     r8, aCvdsdisklunDel_7; "CVdsDiskLun::DeleteDriveLetter, 6, erro"...
0x140029c67  xor     edx, edx
0x140029c69  mov     ecx, r12d
0x140029c6c  call    cs:__imp_VdsTraceEx
0x140029c72  cmp     ebx, 2
0x140029c75  jnz     loc_140029BAC
0x140029c7b  mov     ebx, 8004255Eh
0x140029c80  jmp     short loc_140029CA1
0x140029c82  xor     ebx, ebx
0x140029c84  jmp     short loc_140029CA1
0x140029c86  mov     ebx, 8004255Eh
0x140029c8b  mov     r9d, ebx
0x140029c8e  lea     r8, aCvdsdisklunDel_11; "CVdsDiskLun::DeleteDriveLetter, 1.5, hr"...
0x140029c95  xor     edx, edx
0x140029c97  mov     ecx, r12d
0x140029c9a  call    cs:__imp_VdsTraceEx
0x140029ca0  nop
0x140029ca1  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140029ca8  call    cs:__imp_LeaveCriticalSection
0x140029cae  nop
0x140029caf  lea     rcx, [rsp+310h+var_2D8]; this
0x140029cb4  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140029cb9  nop
0x140029cba  lea     rcx, [rsp+310h+var_2C8]
0x140029cbf  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140029cc5  mov     eax, ebx
0x140029cc7  mov     rcx, [rbp+210h+var_28]
0x140029cce  xor     rcx, rsp; StackCookie
0x140029cd1  call    __security_check_cookie
0x140029cd6  mov     rbx, [rsp+310h+arg_18]
0x140029cde  add     rsp, 2F0h
0x140029ce5  pop     r14
0x140029ce7  pop     r12
0x140029ce9  pop     rdi
0x140029cea  pop     rsi
0x140029ceb  pop     rbp
0x140029cec  retn
```
