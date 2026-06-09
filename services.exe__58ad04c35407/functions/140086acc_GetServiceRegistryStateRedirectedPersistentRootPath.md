# GetServiceRegistryStateRedirectedPersistentRootPath

- ea: `0x140086acc`
- end: `0x140086c13`
- name: `GetServiceRegistryStateRedirectedPersistentRootPath`
- size: `327`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140077b3c`
- `0x14007abec`

## callees

- `0x140086acc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140086bfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140086bfb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140086b54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140086bed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140086b54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140086bed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140086b67`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140086b67`
- `ntdll!RtlNtStatusToDosError` at `0x140086b43`
- `ntdll!RtlNtStatusToDosError` at `0x140086baf`
- `ntdll!RtlNtStatusToDosError` at `0x140086b43`
- `ntdll!RtlNtStatusToDosError` at `0x140086baf`
- `ntdll!RtlGetPersistedStateLocation` at `0x140086b29`
- `ntdll!RtlGetPersistedStateLocation` at `0x140086ba3`
- `ntdll!RtlGetPersistedStateLocation` at `0x140086b29`
- `ntdll!RtlGetPersistedStateLocation` at `0x140086ba3`

## string_xrefs

- `0x140086b22`: `SYSTEM\CurrentControlSet\Services`
- `0x140086b86`: `SYSTEM\CurrentControlSet\Services`
- `0x140086b0e`: `DriverStatePath`
- `0x140086b91`: `DriverStatePath`
- `0x140086bd9`: `OSDATA\System\Services`

## pseudocode

```c
__int64 __fastcall GetServiceRegistryStateRedirectedPersistentRootPath(int a1, _QWORD *a2)
{
  __int64 v2; // r8
  NTSTATUS PersistedStateLocation; // eax
  ULONG v5; // ebx
  unsigned int v6; // ebx
  HANDLE v7; // rax
  SIZE_T v8; // r8
  signed __int64 v9; // rdi
  NTSTATUS v10; // eax
  HANDLE ProcessHeap; // rax
  __int64 v13; // [rsp+28h] [rbp-20h]
  SIZE_T dwBytes; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  LODWORD(dwBytes) = 0;
  if ( !a1 )
  {
    *a2 = L"OSDATA\\System\\Services";
LABEL_13:
    v9 = v2;
    v5 = 0;
    if ( !v2 )
      return v5;
LABEL_14:
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)v9);
    return v5;
  }
  if ( g_DriverPersistentRegistryRoot )
  {
LABEL_11:
    *a2 = g_DriverPersistentRegistryRoot;
    goto LABEL_13;
  }
  LODWORD(dwBytes) = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"DriverStatePath",
                             0,
                             L"SYSTEM\\CurrentControlSet\\Services",
                             0,
                             0,
                             0,
                             &dwBytes);
  if ( PersistedStateLocation >= 0 )
    __fastfail(0x1Fu);
  if ( PersistedStateLocation == -2147483643 )
  {
    v6 = dwBytes;
    v7 = GetProcessHeap();
    v8 = v6;
    v5 = 8;
    v9 = (signed __int64)HeapAlloc(v7, 8u, v8);
    if ( !v9 )
      return v5;
    LODWORD(v13) = dwBytes;
    v10 = RtlGetPersistedStateLocation(
            L"DriverStatePath",
            0,
            L"SYSTEM\\CurrentControlSet\\Services",
            0,
            v9,
            v13,
            &dwBytes);
    if ( v10 < 0 )
    {
      v5 = RtlNtStatusToDosError(v10);
      goto LABEL_14;
    }
    v2 = v9
       & -(__int64)(_InterlockedCompareExchange64((volatile signed __int64 *)&g_DriverPersistentRegistryRoot, v9, 0) != 0);
    goto LABEL_11;
  }
  return RtlNtStatusToDosError(PersistedStateLocation);
}

```

## disassembly

```asm
0x140086acc  mov     r11, rsp
0x140086acf  mov     [r11+10h], rbx
0x140086ad3  mov     [r11+18h], rsi
0x140086ad7  push    rdi
0x140086ad8  sub     rsp, 40h
0x140086adc  xor     r8d, r8d
0x140086adf  mov     dword ptr [rsp+48h+dwBytes], 0
0x140086ae7  mov     rsi, rdx
0x140086aea  test    ecx, ecx
0x140086aec  jz      loc_140086BD9
0x140086af2  mov     rax, cs:?g_DriverPersistentRegistryRoot@@3REAGEA; ushort * g_DriverPersistentRegistryRoot
0x140086af9  test    rax, rax
0x140086afc  jnz     loc_140086BCD
0x140086b02  lea     rax, [r11+8]
0x140086b06  mov     [r11+8], r8d
0x140086b0a  mov     [r11-18h], rax
0x140086b0e  lea     rcx, aDriverstatepat; "DriverStatePath"
0x140086b15  mov     [r11-20h], r8d
0x140086b19  xor     r9d, r9d
0x140086b1c  mov     [r11-28h], r8
0x140086b20  xor     edx, edx
0x140086b22  lea     r8, aSystemCurrentc_10; "SYSTEM\\CurrentControlSet\\Services"
0x140086b29  call    cs:__imp_RtlGetPersistedStateLocation
0x140086b2f  test    eax, eax
0x140086b31  js      short loc_140086B3A
0x140086b33  mov     ecx, 1Fh
0x140086b38  int     29h; Win8: RtlFailFast(ecx)
0x140086b3a  cmp     eax, 80000005h
0x140086b3f  jz      short loc_140086B50
0x140086b41  mov     ecx, eax; Status
0x140086b43  call    cs:__imp_RtlNtStatusToDosError
0x140086b49  mov     ebx, eax
0x140086b4b  jmp     loc_140086C01
0x140086b50  mov     ebx, dword ptr [rsp+48h+dwBytes]
0x140086b54  call    cs:__imp_GetProcessHeap
0x140086b5a  mov     r8d, ebx; dwBytes
0x140086b5d  mov     ebx, 8
0x140086b62  mov     edx, ebx; dwFlags
0x140086b64  mov     rcx, rax; hHeap
0x140086b67  call    cs:__imp_HeapAlloc
0x140086b6d  mov     rdi, rax
0x140086b70  test    rax, rax
0x140086b73  jz      loc_140086C01
0x140086b79  lea     rax, [rsp+48h+dwBytes]
0x140086b7e  xor     r9d, r9d
0x140086b81  mov     [rsp+48h+var_18], rax
0x140086b86  lea     r8, aSystemCurrentc_10; "SYSTEM\\CurrentControlSet\\Services"
0x140086b8d  mov     eax, dword ptr [rsp+48h+dwBytes]
0x140086b91  lea     rcx, aDriverstatepat; "DriverStatePath"
0x140086b98  mov     dword ptr [rsp+48h+var_20], eax
0x140086b9c  xor     edx, edx
0x140086b9e  mov     [rsp+48h+var_28], rdi
0x140086ba3  call    cs:__imp_RtlGetPersistedStateLocation
0x140086ba9  test    eax, eax
0x140086bab  jns     short loc_140086BB9
0x140086bad  mov     ecx, eax; Status
0x140086baf  call    cs:__imp_RtlNtStatusToDosError
0x140086bb5  mov     ebx, eax
0x140086bb7  jmp     short loc_140086BED
0x140086bb9  xor     eax, eax
0x140086bbb  lock cmpxchg cs:?g_DriverPersistentRegistryRoot@@3REAGEA, rdi; ushort * g_DriverPersistentRegistryRoot
0x140086bc4  neg     rax
0x140086bc7  sbb     r8, r8
0x140086bca  and     r8, rdi
0x140086bcd  mov     rax, cs:?g_DriverPersistentRegistryRoot@@3REAGEA; ushort * g_DriverPersistentRegistryRoot
0x140086bd4  mov     [rsi], rax
0x140086bd7  jmp     short loc_140086BE3
0x140086bd9  lea     rax, aOsdataSystemSe; "OSDATA\\System\\Services"
0x140086be0  mov     [rdx], rax
0x140086be3  mov     rdi, r8
0x140086be6  xor     ebx, ebx
0x140086be8  test    r8, r8
0x140086beb  jz      short loc_140086C01
0x140086bed  call    cs:__imp_GetProcessHeap
0x140086bf3  mov     r8, rdi; lpMem
0x140086bf6  xor     edx, edx; dwFlags
0x140086bf8  mov     rcx, rax; hHeap
0x140086bfb  call    cs:__imp_HeapFree
0x140086c01  mov     rsi, [rsp+48h+arg_10]
0x140086c06  mov     eax, ebx
0x140086c08  mov     rbx, [rsp+48h+arg_8]
0x140086c0d  add     rsp, 40h
0x140086c11  pop     rdi
0x140086c12  retn
```
