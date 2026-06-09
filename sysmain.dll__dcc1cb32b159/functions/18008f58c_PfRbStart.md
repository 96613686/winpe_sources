# PfRbStart

- ea: `0x18008f58c`
- end: `0x18008f861`
- name: `PfRbStart`
- size: `725`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18007fc80`

## callees

- `0x1800612e8`
- `0x18008e60c`
- `0x18008eeb0`
- `0x18008f58c`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x18008f6a3`
- `ntdll!NtQuerySystemInformation` at `0x18008f706`
- `ntdll!NtQuerySystemInformation` at `0x18008f6a3`
- `ntdll!NtQuerySystemInformation` at `0x18008f706`
- `ntdll!RtlNtStatusToDosError` at `0x18008f6af`
- `ntdll!RtlNtStatusToDosError` at `0x18008f6af`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008f5fa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008f623`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008f63f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008f5fa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008f623`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008f63f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f60c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f60c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18008f774`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18008f774`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!PfsGetPageCount` at `0x18008f73f`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!PfsGetPageCount` at `0x18008f751`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!PfsGetPageCount` at `0x18008f73f`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!PfsGetPageCount` at `0x18008f751`

## pseudocode

```c
__int64 __fastcall PfRbStart(__int64 a1)
{
  unsigned int v2; // esi
  HANDLE EventW; // rax
  HANDLE v5; // rax
  HANDLE v6; // rax
  unsigned __int64 v7; // rcx
  NTSTATUS v8; // eax
  NTSTATUS v9; // ecx
  NTSTATUS v10; // eax
  __int64 v11; // rbx
  __int64 v12; // rbx
  __int64 PageCount; // r14
  __int64 v14; // rcx
  __int64 v15; // rax
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int64 v27; // [rsp+28h] [rbp-D8h]
  _DWORD v28[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v29; // [rsp+38h] [rbp-C8h]
  __int128 *v30; // [rsp+40h] [rbp-C0h]
  __int64 v31; // [rsp+48h] [rbp-B8h]
  __int128 v32; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD SystemInformation[2]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v34[4]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v35[5]; // [rsp+C0h] [rbp-40h] BYREF

  *(_QWORD *)&v32 = 0;
  memset_0(SystemInformation, 0, 0xB0u);
  LODWORD(v27) = 0;
  v2 = PfRbParametersRead(a1, 0xFFFFFFFFLL);
  if ( !v2 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *(_QWORD *)(a1 + 1968) = EventW;
    if ( !EventW )
      return GetLastError();
    v5 = CreateEventW(0, 0, 0, 0);
    if ( (*(_QWORD *)(a1 + 1984) = v5) == 0 )
      return GetLastError();
    v6 = CreateEventW(0, 0, 0, 0);
    if ( (*(_QWORD *)(a1 + 1992) = v6) == 0 )
      return GetLastError();
    v7 = *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 872LL);
    if ( v7 >= 0xFFFFFFFF )
    {
      LODWORD(v7) = -1;
      LODWORD(v32) = -1;
    }
    else
    {
      LODWORD(v32) = *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 872LL);
    }
    DWORD1(v32) = 4 * v7;
    if ( 4 * (unsigned __int64)(unsigned int)v7 >= 0xFFFFFFFF )
      DWORD1(v32) = -1;
    CrDbLimitsUpdate(a1 + 4224, &v32);
    v8 = NtQuerySystemInformation(SystemMemoryListInformation, SystemInformation, 0xB0u, 0);
    if ( v8 < 0 )
    {
      v9 = v8;
      return RtlNtStatusToDosError(v9);
    }
    v29 = 20;
    v31 = 16;
    v28[0] = 45;
    v32 = 0;
    v28[1] = 1802856515;
    v30 = &v32;
    LODWORD(v32) = 1;
    v10 = NtQuerySystemInformation(SystemSuperfetchInformation, v28, 0x20u, 0);
    if ( v10 >= 0 )
      v27 = *((_QWORD *)&v32 + 1);
    v9 = 0;
    if ( v10 < 0 )
      v9 = v10;
    if ( v9 < 0 )
      return RtlNtStatusToDosError(v9);
    v11 = *((_QWORD *)&SystemInformation[0] + 1) + *(_QWORD *)&SystemInformation[0];
    v12 = PfsGetPageCount((char *)v34 + 8, 0, 7) + v11;
    PageCount = PfsGetPageCount((char *)v35 + 8, 0, 7);
    *(_QWORD *)(a1 + 1680) = v12;
    *(_QWORD *)(a1 + 1688) = PageCount;
    *(_QWORD *)(a1 + 1696) = v27;
    *(_DWORD *)(a1 + 1672) = GetTickCount();
    v14 = 0;
    do
    {
      v15 = 3 * v14++;
      *(_QWORD *)(a1 + 8 * v15 + 464) = v12;
      *(_QWORD *)(a1 + 8 * v15 + 472) = PageCount;
      *(_QWORD *)(a1 + 8 * v15 + 480) = v27;
    }
    while ( v14 != 35 );
    v16 = SystemInformation[1];
    *(_OWORD *)(a1 + 1744) = SystemInformation[0];
    v17 = v34[0];
    *(_OWORD *)(a1 + 1760) = v16;
    v18 = v34[1];
    *(_OWORD *)(a1 + 1776) = v17;
    v19 = v34[2];
    *(_OWORD *)(a1 + 1792) = v18;
    v20 = v34[3];
    *(_OWORD *)(a1 + 1808) = v19;
    v21 = v35[0];
    *(_OWORD *)(a1 + 1824) = v20;
    v22 = v35[1];
    *(_OWORD *)(a1 + 1840) = v21;
    v23 = v35[2];
    *(_OWORD *)(a1 + 1856) = v22;
    v24 = v35[3];
    *(_OWORD *)(a1 + 1872) = v23;
    v25 = v35[4];
    *(_OWORD *)(a1 + 1888) = v24;
    *(_OWORD *)(a1 + 1904) = v25;
    PfRbRunOnBatteryPowerCheck(a1, 0);
    if ( (*(_BYTE *)(*(_QWORD *)&PfSvcGlobals + 1600LL) & 0x10) != 0 )
      *(_DWORD *)(a1 + 1956) |= 8u;
  }
  return v2;
}

```

## disassembly

```asm
0x18008f58c  push    rbp
0x18008f58e  push    rbx
0x18008f58f  push    rsi
0x18008f590  push    rdi
0x18008f591  push    r14
0x18008f593  push    r15
0x18008f595  lea     rbp, [rsp-28h]
0x18008f59a  sub     rsp, 128h
0x18008f5a1  mov     rax, cs:__security_cookie
0x18008f5a8  xor     rax, rsp
0x18008f5ab  mov     [rbp+50h+var_40], rax
0x18008f5af  mov     rdi, rcx
0x18008f5b2  mov     qword ptr [rsp+150h+var_100], 0
0x18008f5bb  mov     r14d, 0B0h
0x18008f5c1  lea     rcx, [rsp+150h+SystemInformation]; void *
0x18008f5c6  mov     r8d, r14d; Size
0x18008f5c9  xor     edx, edx; Val
0x18008f5cb  call    memset_0
0x18008f5d0  xor     eax, eax
0x18008f5d2  mov     ebx, 0FFFFFFFFh
0x18008f5d7  mov     edx, ebx
0x18008f5d9  mov     [rsp+150h+var_12C], rax
0x18008f5de  mov     rcx, rdi
0x18008f5e1  call    PfRbParametersRead
0x18008f5e6  mov     esi, eax
0x18008f5e8  test    eax, eax
0x18008f5ea  jnz     loc_18008F843
0x18008f5f0  xor     r9d, r9d; lpName
0x18008f5f3  xor     r8d, r8d; bInitialState
0x18008f5f6  xor     edx, edx; bManualReset
0x18008f5f8  xor     ecx, ecx; lpEventAttributes
0x18008f5fa  call    cs:__imp_CreateEventW
0x18008f600  mov     [rdi+7B0h], rax
0x18008f607  test    rax, rax
0x18008f60a  jnz     short loc_18008F619
0x18008f60c  call    cs:__imp_GetLastError
0x18008f612  mov     esi, eax
0x18008f614  jmp     loc_18008F843
0x18008f619  xor     r9d, r9d; lpName
0x18008f61c  xor     r8d, r8d; bInitialState
0x18008f61f  xor     edx, edx; bManualReset
0x18008f621  xor     ecx, ecx; lpEventAttributes
0x18008f623  call    cs:__imp_CreateEventW
0x18008f629  mov     [rdi+7C0h], rax
0x18008f630  test    rax, rax
0x18008f633  jz      short loc_18008F60C
0x18008f635  xor     r9d, r9d; lpName
0x18008f638  xor     r8d, r8d; bInitialState
0x18008f63b  xor     edx, edx; bManualReset
0x18008f63d  xor     ecx, ecx; lpEventAttributes
0x18008f63f  call    cs:__imp_CreateEventW
0x18008f645  mov     [rdi+7C8h], rax
0x18008f64c  test    rax, rax
0x18008f64f  jz      short loc_18008F60C
0x18008f651  mov     rax, cs:PfSvcGlobals
0x18008f658  mov     rcx, [rax+368h]
0x18008f65f  cmp     rcx, rbx
0x18008f662  jnb     short loc_18008F66A
0x18008f664  mov     dword ptr [rsp+150h+var_100], ecx
0x18008f668  jmp     short loc_18008F670
0x18008f66a  mov     ecx, ebx
0x18008f66c  mov     dword ptr [rsp+150h+var_100], ebx
0x18008f670  mov     eax, ecx
0x18008f672  shl     rax, 2
0x18008f676  mov     dword ptr [rsp+150h+var_100+4], eax
0x18008f67a  cmp     rax, rbx
0x18008f67d  jb      short loc_18008F683
0x18008f67f  mov     dword ptr [rsp+150h+var_100+4], ebx
0x18008f683  lea     rcx, [rdi+1080h]
0x18008f68a  lea     rdx, [rsp+150h+var_100]
0x18008f68f  call    CrDbLimitsUpdate
0x18008f694  xor     r9d, r9d; ReturnLength
0x18008f697  lea     rdx, [rsp+150h+SystemInformation]; SystemInformation
0x18008f69c  mov     r8d, r14d; SystemInformationLength
0x18008f69f  lea     ecx, [r9+50h]; SystemInformationClass
0x18008f6a3  call    cs:__imp_NtQuerySystemInformation
0x18008f6a9  test    eax, eax
0x18008f6ab  jns     short loc_18008F6BA
0x18008f6ad  mov     ecx, eax; Status
0x18008f6af  call    cs:__imp_RtlNtStatusToDosError
0x18008f6b5  jmp     loc_18008F612
0x18008f6ba  xor     r9d, r9d; ReturnLength
0x18008f6bd  mov     [rsp+150h+var_118], 14h
0x18008f6c6  xorps   xmm0, xmm0
0x18008f6c9  mov     [rsp+150h+var_108], 10h
0x18008f6d2  lea     rax, [rsp+150h+var_100]
0x18008f6d7  mov     [rsp+150h+var_120], 2Dh ; '-'
0x18008f6df  movups  [rsp+150h+var_100], xmm0
0x18008f6e4  lea     r8d, [r9+20h]; SystemInformationLength
0x18008f6e8  mov     [rsp+150h+var_11C], 6B756843h
0x18008f6f0  lea     ecx, [r9+4Fh]; SystemInformationClass
0x18008f6f4  mov     [rsp+150h+var_110], rax
0x18008f6f9  lea     rdx, [rsp+150h+var_120]; SystemInformation
0x18008f6fe  mov     dword ptr [rsp+150h+var_100], 1
0x18008f706  call    cs:__imp_NtQuerySystemInformation
0x18008f70c  test    eax, eax
0x18008f70e  js      short loc_18008F71B
0x18008f710  movaps  xmm0, [rsp+150h+var_100]
0x18008f715  movdqa  xmmword ptr [rsp+20h], xmm0
0x18008f71b  xor     ecx, ecx
0x18008f71d  test    eax, eax
0x18008f71f  cmovs   ecx, eax
0x18008f722  test    ecx, ecx
0x18008f724  js      short loc_18008F6AF
0x18008f726  mov     rbx, qword ptr [rsp+150h+SystemInformation]
0x18008f72b  lea     rcx, [rbp+50h+var_C8]
0x18008f72f  add     rbx, qword ptr [rsp+150h+SystemInformation+8]
0x18008f734  mov     r14d, 7
0x18008f73a  mov     r8d, r14d
0x18008f73d  xor     edx, edx
0x18008f73f  call    cs:__imp_PfsGetPageCount
0x18008f745  mov     r8d, r14d
0x18008f748  lea     rcx, [rbp+50h+var_88]
0x18008f74c  xor     edx, edx
0x18008f74e  add     rbx, rax
0x18008f751  call    cs:__imp_PfsGetPageCount
0x18008f757  mov     r15, [rsp+150h+var_12C+4]
0x18008f75c  mov     r14, rax
0x18008f75f  mov     [rdi+690h], rbx
0x18008f766  mov     [rdi+698h], rax
0x18008f76d  mov     [rdi+6A0h], r15
0x18008f774  call    cs:__imp_GetTickCount
0x18008f77a  mov     [rdi+688h], eax
0x18008f780  xor     ecx, ecx
0x18008f782  lea     rax, [rcx+rcx*2]
0x18008f786  inc     rcx
0x18008f789  mov     [rdi+rax*8+1D0h], rbx
0x18008f791  mov     [rdi+rax*8+1D8h], r14
0x18008f799  mov     [rdi+rax*8+1E0h], r15
0x18008f7a1  cmp     rcx, 23h ; '#'
0x18008f7a5  jnz     short loc_18008F782
0x18008f7a7  movaps  xmm0, [rsp+150h+SystemInformation]
0x18008f7ac  xor     edx, edx
0x18008f7ae  movaps  xmm1, [rsp+150h+var_E0]
0x18008f7b3  mov     rcx, rdi
0x18008f7b6  movups  xmmword ptr [rdi+6D0h], xmm0
0x18008f7bd  movaps  xmm0, xmmword ptr [rbp-80h]
0x18008f7c1  movups  xmmword ptr [rdi+6E0h], xmm1
0x18008f7c8  movaps  xmm1, [rbp+50h+var_C0]
0x18008f7cc  movups  xmmword ptr [rdi+6F0h], xmm0
0x18008f7d3  movaps  xmm0, [rbp+50h+var_B0]
0x18008f7d7  movups  xmmword ptr [rdi+700h], xmm1
0x18008f7de  movaps  xmm1, [rbp+50h+var_A0]
0x18008f7e2  movups  xmmword ptr [rdi+710h], xmm0
0x18008f7e9  movaps  xmm0, xmmword ptr [rbp-40h]
0x18008f7ed  movups  xmmword ptr [rdi+720h], xmm1
0x18008f7f4  movaps  xmm1, [rbp+50h+var_80]
0x18008f7f8  movups  xmmword ptr [rdi+730h], xmm0
0x18008f7ff  movaps  xmm0, [rbp+50h+var_70]
0x18008f803  movups  xmmword ptr [rdi+740h], xmm1
0x18008f80a  movaps  xmm1, [rbp+50h+var_60]
0x18008f80e  movups  xmmword ptr [rdi+750h], xmm0
0x18008f815  movaps  xmm0, [rbp+50h+var_50]
0x18008f819  movups  xmmword ptr [rdi+760h], xmm1
0x18008f820  movups  xmmword ptr [rdi+770h], xmm0
0x18008f827  call    PfRbRunOnBatteryPowerCheck
0x18008f82c  mov     rax, cs:PfSvcGlobals
0x18008f833  test    byte ptr [rax+640h], 10h
0x18008f83a  jz      short loc_18008F843
0x18008f83c  or      dword ptr [rdi+7A4h], 8
0x18008f843  mov     eax, esi
0x18008f845  mov     rcx, [rbp+50h+var_40]
0x18008f849  xor     rcx, rsp; StackCookie
0x18008f84c  call    __security_check_cookie
0x18008f851  add     rsp, 128h
0x18008f858  pop     r15
0x18008f85a  pop     r14
0x18008f85c  pop     rdi
0x18008f85d  pop     rsi
0x18008f85e  pop     rbx
0x18008f85f  pop     rbp
0x18008f860  retn
```
