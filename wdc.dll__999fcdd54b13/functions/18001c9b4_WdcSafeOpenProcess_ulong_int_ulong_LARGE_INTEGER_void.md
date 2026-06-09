# WdcSafeOpenProcess(ulong,int,ulong,_LARGE_INTEGER,void * *)

- ea: `0x18001c9b4`
- end: `0x18001cb19`
- name: `?WdcSafeOpenProcess@@YAJKHKT_LARGE_INTEGER@@PEAPEAX@Z`
- size: `357`
- prototype: `__int64 __fastcall(unsigned int, int, unsigned int, union _LARGE_INTEGER, void **)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c718`
- `0x1800281c4`
- `0x1800286f8`
- `0x1800354d8`
- `0x18007f8c8`
- `0x18007fe4c`

## callees

- `0x18000b854`
- `0x18001c9b4`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001cb11`
- `KERNEL32!CloseHandle` at `0x18001cb11`
- `KERNEL32!GetLastError` at `0x18001ca2f`
- `KERNEL32!GetLastError` at `0x18001ca78`
- `KERNEL32!GetLastError` at `0x18001ca2f`
- `KERNEL32!GetLastError` at `0x18001ca78`
- `KERNEL32!OpenProcess` at `0x18001c9f1`
- `KERNEL32!OpenProcess` at `0x18001c9f1`
- `KERNEL32!GetProcessTimes` at `0x18001ca21`
- `KERNEL32!GetProcessTimes` at `0x18001ca21`

## string_xrefs

- `0x18001ca59`: `WdcSafeOpenProcess`
- `0x18001caac`: `WdcSafeOpenProcess`

## pseudocode

```c
__int64 __fastcall WdcSafeOpenProcess(int a1, __int64 a2, DWORD a3, union _LARGE_INTEGER a4, void **a5)
{
  DWORD LowPart; // ebx
  HANDLE v6; // rax
  void *v7; // rsi
  signed int v8; // eax
  signed int v9; // edi
  signed int LastError; // eax
  LPFILETIME lpUserTime; // [rsp+20h] [rbp-38h]
  _FILETIME CreationTime; // [rsp+30h] [rbp-28h] BYREF
  struct _FILETIME UserTime; // [rsp+38h] [rbp-20h] BYREF
  struct _FILETIME KernelTime; // [rsp+40h] [rbp-18h] BYREF
  struct _FILETIME ExitTime; // [rsp+48h] [rbp-10h] BYREF
  LONG HighPart; // [rsp+7Ch] [rbp+24h]

  HighPart = a4.HighPart;
  CreationTime = 0;
  ExitTime = 0;
  LowPart = a4.LowPart;
  KernelTime = 0;
  UserTime = 0;
  v6 = OpenProcess(a1 | 0x1000u, 0, a3);
  v7 = v6;
  if ( v6 && v6 != (HANDLE)-1LL )
    goto LABEL_3;
  LastError = GetLastError();
  v9 = LastError;
  if ( !LastError )
  {
    v9 = -2147467259;
LABEL_16:
    WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mon\\process.cpp", "WdcSafeOpenProcess", 0, L"FAILURE: 0x%08x", v9);
    return (unsigned int)v9;
  }
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  if ( v9 < 0 )
    goto LABEL_16;
LABEL_3:
  if ( GetProcessTimes(v7, &CreationTime, &ExitTime, &KernelTime, &UserTime) )
  {
    v9 = 0;
    goto LABEL_19;
  }
  v8 = GetLastError();
  v9 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    if ( v9 < 0 )
      goto LABEL_8;
LABEL_19:
    if ( CreationTime.dwLowDateTime == LowPart && CreationTime.dwHighDateTime == HighPart )
    {
      *a5 = v7;
      return (unsigned int)v9;
    }
    v9 = -2147467259;
    goto LABEL_23;
  }
  v9 = -2147467259;
LABEL_8:
  LODWORD(lpUserTime) = v9;
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mon\\process.cpp",
    "WdcSafeOpenProcess",
    0,
    L"FAILURE: 0x%08x",
    lpUserTime);
LABEL_23:
  if ( v7 && v7 != (void *)-1LL )
    CloseHandle(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001c9b4  mov     rax, rsp
0x18001c9b7  mov     [rax+8], rbx
0x18001c9bb  mov     [rax+10h], rsi
0x18001c9bf  mov     [rax+20h], r9
0x18001c9c3  push    rdi
0x18001c9c4  sub     rsp, 50h
0x18001c9c8  bts     ecx, 0Ch; dwDesiredAccess
0x18001c9cc  mov     qword ptr [rax-28h], 0
0x18001c9d4  xor     edx, edx; bInheritHandle
0x18001c9d6  mov     qword ptr [rax-10h], 0
0x18001c9de  mov     rbx, r9
0x18001c9e1  mov     qword ptr [rax-18h], 0
0x18001c9e9  mov     qword ptr [rax-20h], 0
0x18001c9f1  call    cs:__imp_OpenProcess
0x18001c9f7  mov     rsi, rax
0x18001c9fa  test    rax, rax
0x18001c9fd  jz      short loc_18001CA78
0x18001c9ff  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ca03  jz      short loc_18001CA78
0x18001ca05  lea     rax, [rsp+58h+UserTime]
0x18001ca0a  mov     rcx, rsi; hProcess
0x18001ca0d  lea     r9, [rsp+58h+KernelTime]; lpKernelTime
0x18001ca12  mov     [rsp+58h+lpUserTime], rax; lpUserTime
0x18001ca17  lea     r8, [rsp+58h+ExitTime]; lpExitTime
0x18001ca1c  lea     rdx, [rsp+58h+CreationTime]; lpCreationTime
0x18001ca21  call    cs:__imp_GetProcessTimes
0x18001ca27  test    eax, eax
0x18001ca29  jnz     loc_18001CAD1
0x18001ca2f  call    cs:__imp_GetLastError
0x18001ca35  mov     edi, eax
0x18001ca37  test    eax, eax
0x18001ca39  jz      short loc_18001CA71
0x18001ca3b  jg      loc_18001CAF0
0x18001ca41  test    edi, edi
0x18001ca43  jns     loc_18001CAD3
0x18001ca49  mov     eax, edi
0x18001ca4b  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18001ca52  xor     r8d, r8d; int
0x18001ca55  mov     dword ptr [rsp+58h+lpUserTime], eax
0x18001ca59  lea     rdx, aWdcsafeopenpro; "WdcSafeOpenProcess"
0x18001ca60  lea     rcx, aBaseDiagnosisP_42; "base\\diagnosis\\pdui\\perfmon\\mon\\pr"...
0x18001ca67  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18001ca6c  jmp     loc_18001CB03
0x18001ca71  mov     edi, 80004005h
0x18001ca76  jmp     short loc_18001CA49
0x18001ca78  call    cs:__imp_GetLastError
0x18001ca7e  mov     edi, eax
0x18001ca80  test    eax, eax
0x18001ca82  jz      short loc_18001CA99
0x18001ca84  jle     short loc_18001CA8F
0x18001ca86  movzx   edi, ax
0x18001ca89  or      edi, 80070000h
0x18001ca8f  test    edi, edi
0x18001ca91  jns     loc_18001CA05
0x18001ca97  jmp     short loc_18001CA9E
0x18001ca99  mov     edi, 80004005h
0x18001ca9e  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18001caa5  mov     dword ptr [rsp+58h+lpUserTime], edi
0x18001caa9  xor     r8d, r8d; int
0x18001caac  lea     rdx, aWdcsafeopenpro; "WdcSafeOpenProcess"
0x18001cab3  lea     rcx, aBaseDiagnosisP_42; "base\\diagnosis\\pdui\\perfmon\\mon\\pr"...
0x18001caba  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18001cabf  mov     rbx, [rsp+58h+arg_0]
0x18001cac4  mov     eax, edi
0x18001cac6  mov     rsi, [rsp+58h+arg_8]
0x18001cacb  add     rsp, 50h
0x18001cacf  pop     rdi
0x18001cad0  retn
0x18001cad1  xor     edi, edi
0x18001cad3  cmp     [rsp+58h+CreationTime.dwLowDateTime], ebx
0x18001cad7  jnz     short loc_18001CAFE
0x18001cad9  mov     eax, [rsp+58h+arg_1C]
0x18001cadd  cmp     [rsp+58h+CreationTime.dwHighDateTime], eax
0x18001cae1  jnz     short loc_18001CAFE
0x18001cae3  mov     rax, [rsp+58h+arg_20]
0x18001caeb  mov     [rax], rsi
0x18001caee  jmp     short loc_18001CABF
0x18001caf0  movzx   edi, ax
0x18001caf3  or      edi, 80070000h
0x18001caf9  jmp     loc_18001CA41
0x18001cafe  mov     edi, 80004005h
0x18001cb03  test    rsi, rsi
0x18001cb06  jz      short loc_18001CABF
0x18001cb08  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001cb0c  jz      short loc_18001CABF
0x18001cb0e  mov     rcx, rsi; hObject
0x18001cb11  call    cs:__imp_CloseHandle
0x18001cb17  jmp     short loc_18001CABF
```
