# WdipLowerPagePriorityThread

- ea: `0x180001080`
- end: `0x1800011c7`
- name: `WdipLowerPagePriorityThread`
- size: `327`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001010`
- `0x180003420`
- `0x1800042c0`
- `0x1800063d0`
- `0x1800068f0`

## callees

- `0x180001080`
- `0x180002ba0`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x1800010b7`
- `ntdll!NtQueryInformationThread` at `0x1800010b7`
- `ntdll!NtSetInformationThread` at `0x180001159`
- `ntdll!NtSetInformationThread` at `0x180001159`
- `ntdll!RtlNtStatusToDosError` at `0x1800010c7`
- `ntdll!RtlNtStatusToDosError` at `0x180001169`
- `ntdll!RtlNtStatusToDosError` at `0x1800010c7`
- `ntdll!RtlNtStatusToDosError` at `0x180001169`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001095`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001140`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001095`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001140`

## string_xrefs

- `0x1800010f4`: `WdipGetPagePriorityThread`
- `0x180001196`: `WdipSetPagePriorityThread`
- `0x180001118`: `WdipLowerPagePriorityThread`

## pseudocode

```c
__int64 __fastcall WdipLowerPagePriorityThread(_DWORD *a1)
{
  HANDLE CurrentThread; // rax
  int v3; // eax
  signed int v4; // edi
  signed int v5; // eax
  char v6; // bl
  int v7; // r8d
  __int64 result; // rax
  HANDLE v9; // rax
  int v10; // eax
  signed int v11; // eax
  int ThreadInformation; // [rsp+48h] [rbp+10h] BYREF
  int v13; // [rsp+50h] [rbp+18h] BYREF

  ThreadInformation = 0;
  CurrentThread = GetCurrentThread();
  v3 = NtQueryInformationThread(CurrentThread, ThreadPagePriority, &ThreadInformation, 4u, 0);
  if ( v3 < 0 )
  {
    v5 = RtlNtStatusToDosError(v3);
    v4 = v5;
    if ( v5 > 0 )
      v4 = (unsigned __int16)v5 | 0x80070000;
  }
  else
  {
    v4 = 0;
  }
  if ( v4 < 0 )
  {
    v6 = v4;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\mempri.cpp",
      (int)L"WdipGetPagePriorityThread",
      60,
      (int)L"Error = %d",
      v4);
    v7 = 166;
LABEL_7:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\mempri.cpp",
      (int)L"WdipLowerPagePriorityThread",
      v7,
      (int)L"Error = %d",
      v6);
    return (unsigned int)v4;
  }
  v13 = 1;
  v9 = GetCurrentThread();
  v10 = NtSetInformationThread(v9, ThreadPagePriority, &v13, 4u);
  if ( v10 < 0 )
  {
    v11 = RtlNtStatusToDosError(v10);
    v4 = v11;
    if ( v11 > 0 )
      v4 = (unsigned __int16)v11 | 0x80070000;
  }
  else
  {
    v4 = 0;
  }
  if ( v4 < 0 )
  {
    v6 = v4;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\mempri.cpp",
      (int)L"WdipSetPagePriorityThread",
      115,
      (int)L"Error = %d",
      v4);
    v7 = 173;
    goto LABEL_7;
  }
  result = (unsigned int)v4;
  *a1 = ThreadInformation;
  return result;
}

```

## disassembly

```asm
0x180001080  mov     [rsp+arg_0], rbx
0x180001085  push    rdi
0x180001086  sub     rsp, 30h
0x18000108a  mov     rbx, rcx
0x18000108d  mov     [rsp+38h+ThreadInformation], 0
0x180001095  call    cs:__imp_GetCurrentThread
0x18000109b  mov     r9d, 4; ThreadInformationLength
0x1800010a1  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x1800010aa  mov     rcx, rax; ThreadHandle
0x1800010ad  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x1800010b2  mov     edx, 18h; ThreadInformationClass
0x1800010b7  call    cs:__imp_NtQueryInformationThread
0x1800010bd  test    eax, eax
0x1800010bf  js      short loc_1800010C5
0x1800010c1  xor     edi, edi
0x1800010c3  jmp     short loc_1800010DC
0x1800010c5  mov     ecx, eax; Status
0x1800010c7  call    cs:__imp_RtlNtStatusToDosError
0x1800010cd  mov     edi, eax
0x1800010cf  test    eax, eax
0x1800010d1  jle     short loc_1800010DC
0x1800010d3  movzx   edi, ax
0x1800010d6  or      edi, 80070000h
0x1800010dc  test    edi, edi
0x1800010de  jns     short loc_180001138
0x1800010e0  movzx   ebx, di
0x1800010e3  lea     r9, aErrorD_0; "Error = %d"
0x1800010ea  mov     r8d, 3Ch ; '<'; int
0x1800010f0  mov     dword ptr [rsp+38h+ReturnLength], ebx; Args
0x1800010f4  lea     rdx, aWdipgetpagepri; "WdipGetPagePriorityThread"
0x1800010fb  lea     rcx, aClientcoreBase_4; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180001102  call    WdipTraceError
0x180001107  mov     r8d, 0A6h; int
0x18000110d  lea     r9, aErrorD_0; "Error = %d"
0x180001114  mov     dword ptr [rsp+38h+ReturnLength], ebx; Args
0x180001118  lea     rdx, aWdiplowerpagep; "WdipLowerPagePriorityThread"
0x18000111f  lea     rcx, aClientcoreBase_4; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180001126  call    WdipTraceError
0x18000112b  mov     eax, edi
0x18000112d  mov     rbx, [rsp+38h+arg_0]
0x180001132  add     rsp, 30h
0x180001136  pop     rdi
0x180001137  retn
0x180001138  mov     [rsp+38h+arg_10], 1
0x180001140  call    cs:__imp_GetCurrentThread
0x180001146  mov     r9d, 4; ThreadInformationLength
0x18000114c  lea     r8, [rsp+38h+arg_10]; ThreadInformation
0x180001151  mov     rcx, rax; ThreadHandle
0x180001154  mov     edx, 18h; ThreadInformationClass
0x180001159  call    cs:__imp_NtSetInformationThread
0x18000115f  test    eax, eax
0x180001161  js      short loc_180001167
0x180001163  xor     edi, edi
0x180001165  jmp     short loc_18000117E
0x180001167  mov     ecx, eax; Status
0x180001169  call    cs:__imp_RtlNtStatusToDosError
0x18000116f  mov     edi, eax
0x180001171  test    eax, eax
0x180001173  jle     short loc_18000117E
0x180001175  movzx   edi, ax
0x180001178  or      edi, 80070000h
0x18000117e  test    edi, edi
0x180001180  jns     short loc_1800011B4
0x180001182  movzx   ebx, di
0x180001185  lea     r9, aErrorD_0; "Error = %d"
0x18000118c  mov     r8d, 73h ; 's'; int
0x180001192  mov     dword ptr [rsp+38h+ReturnLength], ebx; Args
0x180001196  lea     rdx, aWdipsetpagepri; "WdipSetPagePriorityThread"
0x18000119d  lea     rcx, aClientcoreBase_4; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800011a4  call    WdipTraceError
0x1800011a9  mov     r8d, 0ADh
0x1800011af  jmp     loc_18000110D
0x1800011b4  mov     ecx, [rsp+38h+ThreadInformation]
0x1800011b8  mov     eax, edi
0x1800011ba  mov     [rbx], ecx
0x1800011bc  mov     rbx, [rsp+38h+arg_0]
0x1800011c1  add     rsp, 30h
0x1800011c5  pop     rdi
0x1800011c6  retn
```
