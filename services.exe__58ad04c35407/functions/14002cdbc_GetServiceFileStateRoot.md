# GetServiceFileStateRoot

- ea: `0x14002cdbc`
- end: `0x14002cfa4`
- name: `GetServiceFileStateRoot`
- size: `488`
- prototype: `__int64 __fastcall(unsigned int, _QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400766dc`
- `0x140076d48`
- `0x140077674`
- `0x140077d80`

## callees

- `0x14002cdbc`
- `0x140050dd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002cf85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002cf85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002ce6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002cef9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002cf77`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002ce6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002cef9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002cf77`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002ce7f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002cf0f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002ce7f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002cf0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002cee7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002cf2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002cee7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002cf2e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x14002cedd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x14002cf24`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x14002cedd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x14002cf24`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14002cdfa`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14002cdfa`
- `ntdll!RtlNtStatusToDosError` at `0x14002ce5b`
- `ntdll!RtlNtStatusToDosError` at `0x14002cecc`
- `ntdll!RtlNtStatusToDosError` at `0x14002ce5b`
- `ntdll!RtlNtStatusToDosError` at `0x14002cecc`
- `ntdll!RtlGetPersistedStateLocation` at `0x14002ce41`
- `ntdll!RtlGetPersistedStateLocation` at `0x14002cebc`
- `ntdll!RtlGetPersistedStateLocation` at `0x14002ce41`
- `ntdll!RtlGetPersistedStateLocation` at `0x14002cebc`

## string_xrefs

- `0x14002ce1a`: `U:\ServiceState`
- `0x14002cea5`: `U:\ServiceState`
- `0x14002ce29`: `Win32ServiceStateRoot`
- `0x14002ceb0`: `Win32ServiceStateRoot`
- `0x14002cf3a`: `\ServiceState`

## pseudocode

```c
__int64 __fastcall GetServiceFileStateRoot(unsigned int a1, _QWORD *a2)
{
  __int64 v3; // rcx
  NTSTATUS PersistedStateLocation; // eax
  unsigned int v6; // ebx
  unsigned int v7; // ebx
  HANDLE v8; // rax
  SIZE_T v9; // r8
  signed __int64 v10; // rdi
  NTSTATUS v11; // eax
  DWORD LastError; // eax
  UINT SystemWindowsDirectoryW; // eax
  UINT v14; // ebx
  HANDLE v15; // rax
  __int64 v16; // r8
  WCHAR *v17; // rax
  HANDLE ProcessHeap; // rax
  __int64 v20; // [rsp+28h] [rbp-20h]
  SIZE_T dwBytes; // [rsp+58h] [rbp+10h] BYREF

  LODWORD(dwBytes) = 0;
  if ( !a2 || a1 > 1 )
    return 87;
  v3 = 0;
  if ( g_ServicePersistentFileRoot )
  {
LABEL_21:
    v10 = v3;
    *a2 = g_ServicePersistentFileRoot;
    v6 = 0;
    if ( !v3 )
      return v6;
LABEL_22:
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)v10);
    return v6;
  }
  if ( !(unsigned __int8)RtlIsStateSeparationEnabled(0) )
  {
    SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(0, 0);
    if ( !SystemWindowsDirectoryW )
      return GetLastError();
    v14 = SystemWindowsDirectoryW + 13;
    LODWORD(dwBytes) = SystemWindowsDirectoryW + 13;
    v15 = GetProcessHeap();
    v16 = v14;
    v6 = 8;
    v17 = (WCHAR *)HeapAlloc(v15, 8u, 2 * v16);
    v10 = (signed __int64)v17;
    if ( !v17 )
      return v6;
    if ( !GetSystemWindowsDirectoryW(v17, dwBytes) )
    {
      LastError = GetLastError();
      goto LABEL_13;
    }
    v6 = wcscat_s((wchar_t *)v10, (unsigned int)dwBytes, L"\\ServiceState");
    if ( v6 )
      goto LABEL_22;
    goto LABEL_20;
  }
  LODWORD(dwBytes) = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"Win32ServiceStateRoot",
                             0,
                             L"U:\\ServiceState",
                             1,
                             0,
                             0,
                             &dwBytes);
  if ( PersistedStateLocation >= 0 )
    __fastfail(0x1Fu);
  if ( PersistedStateLocation == -2147483643 )
  {
    v7 = dwBytes;
    v8 = GetProcessHeap();
    v9 = v7;
    v6 = 8;
    v10 = (signed __int64)HeapAlloc(v8, 8u, v9);
    if ( !v10 )
      return v6;
    LODWORD(v20) = dwBytes;
    v11 = RtlGetPersistedStateLocation(L"Win32ServiceStateRoot", 0, L"U:\\ServiceState", 1, v10, v20, &dwBytes);
    if ( v11 < 0 )
    {
      LastError = RtlNtStatusToDosError(v11);
LABEL_13:
      v6 = LastError;
      goto LABEL_22;
    }
LABEL_20:
    v3 = v10
       & -(__int64)(_InterlockedCompareExchange64((volatile signed __int64 *)&g_ServicePersistentFileRoot, v10, 0) != 0);
    goto LABEL_21;
  }
  return RtlNtStatusToDosError(PersistedStateLocation);
}

```

## disassembly

```asm
0x14002cdbc  mov     [rsp+arg_0], rbx
0x14002cdc1  mov     [rsp+arg_10], rsi
0x14002cdc6  push    rdi
0x14002cdc7  sub     rsp, 40h
0x14002cdcb  mov     dword ptr [rsp+48h+dwBytes], 0
0x14002cdd3  mov     rsi, rdx
0x14002cdd6  test    rdx, rdx
0x14002cdd9  jz      loc_14002CF8D
0x14002cddf  cmp     ecx, 1
0x14002cde2  ja      loc_14002CF8D
0x14002cde8  mov     rax, cs:?g_ServicePersistentFileRoot@@3REAGEA; ushort * g_ServicePersistentFileRoot
0x14002cdef  xor     ecx, ecx
0x14002cdf1  test    rax, rax
0x14002cdf4  jnz     loc_14002CF63
0x14002cdfa  call    cs:__imp_RtlIsStateSeparationEnabled
0x14002ce00  test    al, al
0x14002ce02  jz      loc_14002CED9
0x14002ce08  lea     rax, [rsp+48h+dwBytes]
0x14002ce0d  mov     dword ptr [rsp+48h+dwBytes], 0
0x14002ce15  mov     [rsp+48h+var_18], rax
0x14002ce1a  lea     r8, aUServicestate; "U:\\ServiceState"
0x14002ce21  mov     dword ptr [rsp+48h+var_20], 0
0x14002ce29  lea     rcx, aWin32servicest; "Win32ServiceStateRoot"
0x14002ce30  mov     r9d, 1
0x14002ce36  mov     [rsp+48h+var_28], 0
0x14002ce3f  xor     edx, edx
0x14002ce41  call    cs:__imp_RtlGetPersistedStateLocation
0x14002ce47  test    eax, eax
0x14002ce49  js      short loc_14002CE52
0x14002ce4b  mov     ecx, 1Fh
0x14002ce50  int     29h; Win8: RtlFailFast(ecx)
0x14002ce52  cmp     eax, 80000005h
0x14002ce57  jz      short loc_14002CE68
0x14002ce59  mov     ecx, eax; Status
0x14002ce5b  call    cs:__imp_RtlNtStatusToDosError
0x14002ce61  mov     ebx, eax
0x14002ce63  jmp     loc_14002CF92
0x14002ce68  mov     ebx, dword ptr [rsp+48h+dwBytes]
0x14002ce6c  call    cs:__imp_GetProcessHeap
0x14002ce72  mov     r8d, ebx; dwBytes
0x14002ce75  mov     ebx, 8
0x14002ce7a  mov     edx, ebx; dwFlags
0x14002ce7c  mov     rcx, rax; hHeap
0x14002ce7f  call    cs:__imp_HeapAlloc
0x14002ce85  mov     rdi, rax
0x14002ce88  test    rax, rax
0x14002ce8b  jz      loc_14002CF92
0x14002ce91  lea     rax, [rsp+48h+dwBytes]
0x14002ce96  xor     edx, edx
0x14002ce98  mov     [rsp+48h+var_18], rax
0x14002ce9d  lea     r9d, [rbx-7]
0x14002cea1  mov     eax, dword ptr [rsp+48h+dwBytes]
0x14002cea5  lea     r8, aUServicestate; "U:\\ServiceState"
0x14002ceac  mov     dword ptr [rsp+48h+var_20], eax
0x14002ceb0  lea     rcx, aWin32servicest; "Win32ServiceStateRoot"
0x14002ceb7  mov     [rsp+48h+var_28], rdi
0x14002cebc  call    cs:__imp_RtlGetPersistedStateLocation
0x14002cec2  test    eax, eax
0x14002cec4  jns     loc_14002CF4F
0x14002ceca  mov     ecx, eax; Status
0x14002cecc  call    cs:__imp_RtlNtStatusToDosError
0x14002ced2  mov     ebx, eax
0x14002ced4  jmp     loc_14002CF77
0x14002ced9  xor     edx, edx; uSize
0x14002cedb  xor     ecx, ecx; lpBuffer
0x14002cedd  call    cs:__imp_GetSystemWindowsDirectoryW
0x14002cee3  test    eax, eax
0x14002cee5  jnz     short loc_14002CEF2
0x14002cee7  call    cs:__imp_GetLastError
0x14002ceed  jmp     loc_14002CE61
0x14002cef2  lea     ebx, [rax+0Dh]
0x14002cef5  mov     dword ptr [rsp+48h+dwBytes], ebx
0x14002cef9  call    cs:__imp_GetProcessHeap
0x14002ceff  mov     r8d, ebx
0x14002cf02  mov     ebx, 8
0x14002cf07  mov     edx, ebx; dwFlags
0x14002cf09  mov     rcx, rax; hHeap
0x14002cf0c  add     r8, r8; dwBytes
0x14002cf0f  call    cs:__imp_HeapAlloc
0x14002cf15  mov     rdi, rax
0x14002cf18  test    rax, rax
0x14002cf1b  jz      short loc_14002CF92
0x14002cf1d  mov     edx, dword ptr [rsp+48h+dwBytes]; uSize
0x14002cf21  mov     rcx, rax; lpBuffer
0x14002cf24  call    cs:__imp_GetSystemWindowsDirectoryW
0x14002cf2a  test    eax, eax
0x14002cf2c  jnz     short loc_14002CF36
0x14002cf2e  call    cs:__imp_GetLastError
0x14002cf34  jmp     short loc_14002CED2
0x14002cf36  mov     edx, dword ptr [rsp+48h+dwBytes]; SizeInWords
0x14002cf3a  lea     r8, aServicestate; "\\ServiceState"
0x14002cf41  mov     rcx, rdi; Destination
0x14002cf44  call    wcscat_s
0x14002cf49  mov     ebx, eax
0x14002cf4b  test    eax, eax
0x14002cf4d  jnz     short loc_14002CF77
0x14002cf4f  xor     eax, eax
0x14002cf51  lock cmpxchg cs:?g_ServicePersistentFileRoot@@3REAGEA, rdi; ushort * g_ServicePersistentFileRoot
0x14002cf5a  neg     rax
0x14002cf5d  sbb     rcx, rcx
0x14002cf60  and     rcx, rdi
0x14002cf63  mov     rax, cs:?g_ServicePersistentFileRoot@@3REAGEA; ushort * g_ServicePersistentFileRoot
0x14002cf6a  mov     rdi, rcx
0x14002cf6d  mov     [rsi], rax
0x14002cf70  xor     ebx, ebx
0x14002cf72  test    rcx, rcx
0x14002cf75  jz      short loc_14002CF92
0x14002cf77  call    cs:__imp_GetProcessHeap
0x14002cf7d  mov     r8, rdi; lpMem
0x14002cf80  xor     edx, edx; dwFlags
0x14002cf82  mov     rcx, rax; hHeap
0x14002cf85  call    cs:__imp_HeapFree
0x14002cf8b  jmp     short loc_14002CF92
0x14002cf8d  mov     ebx, 57h ; 'W'
0x14002cf92  mov     rsi, [rsp+48h+arg_10]
0x14002cf97  mov     eax, ebx
0x14002cf99  mov     rbx, [rsp+48h+arg_0]
0x14002cf9e  add     rsp, 40h
0x14002cfa2  pop     rdi
0x14002cfa3  retn
```
