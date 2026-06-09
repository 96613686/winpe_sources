# SampMaybeReleaseReadLock(uchar)

- ea: `0x180016240`
- end: `0x180016535`
- name: `?SampMaybeReleaseReadLock@@YAXE@Z`
- size: `757`
- prototype: `void __fastcall(unsigned __int8)`
- caller_count: `21`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002b40`
- `0x180009030`
- `0x18000b150`
- `0x180012160`
- `0x180012d60`
- `0x180013370`
- `0x180013710`
- `0x180013b90`
- `0x180014ea0`
- `0x180015430`
- `0x180015c50`
- `0x180015e90`
- `0x180036700`
- `0x18004f050`
- `0x1800559a0`
- `0x180055cc0`
- `0x1800647e0`
- `0x180064b60`
- `0x1800a3130`
- `0x1800a8e60`
- `0x1800ae5f0`

## callees

- `0x1800022a0`
- `0x180016240`
- `0x1800270b4`
- `0x180027ef8`
- `0x18002cd80`
- `0x18002d720`
- `0x180037284`
- `0x1800372ac`

## import_xrefs

- `ntdll!NtSetEvent` at `0x18001635e`
- `ntdll!NtSetEvent` at `0x18001635e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800162f8`
- `ntdll!RtlLeaveCriticalSection` at `0x1800162f8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800164d0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800164d0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800162dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800162dd`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180016506`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180016506`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtMaybeEndDsTransaction` at `0x180016522`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtMaybeEndDsTransaction` at `0x180016522`

## string_xrefs

- `0x1800164a6`: `DirectoryServiceExtPt`
- `0x1800164bd`: `SYSTEM\CurrentControlSet\Services\NTDS`

## pseudocode

```c
void __fastcall SampMaybeReleaseReadLock(char a1)
{
  PUNICODE_STRING v1; // rcx
  bool v2; // bl
  signed int v3; // eax
  DWORD pcbData[4]; // [rsp+50h] [rbp-238h] BYREF
  WCHAR String1[264]; // [rsp+60h] [rbp-228h] BYREF

  if ( a1 )
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SampUseDsData);
    if ( SampUseDsData && (unsigned int)SampExtIsWriteLockHeldByDs() )
    {
      SampSetTransactionWithinDomain(0);
    }
    else
    {
      if ( SampLock.OwningThread == NtCurrentTeb()->ClientId.UniqueThread )
      {
        v1 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 209, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 1);
          v1 = WPP_GLOBAL_Control;
        }
        SampTransactionWithinDomainGlobal = 0;
      }
      else
      {
        v1 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 210, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 0);
          v1 = WPP_GLOBAL_Control;
        }
        if ( (*(_BYTE *)(&v1[4].MaximumLength + 1) & 4) != 0 && HIBYTE(v1[4].Length) >= 2u )
        {
          WPP_SF_(v1[3].Buffer, 10, WPP_48bf36016493398285a8dbc678e80a21_Traceguids);
          v1 = WPP_GLOBAL_Control;
        }
      }
      v2 = SampUseDsData && !SampDsStopped;
      if ( (*(_DWORD *)(&v1[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_d(v1[3].Buffer, 74, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v2);
      if ( v2 )
        SampExtMaybeEndDsTransactionDs(3);
      v3 = GetTickCount() - SamLockCurrentHoldStartTime;
      if ( v3 > 0 )
      {
        if ( SamLockTotalAquisitions )
          SamCumulativeHoldTime += v3;
      }
      RtlLeaveCriticalSection(&SampLock);
    }
    return;
  }
  memset_0(String1, 0, 0x208u);
  pcbData[0] = 520;
  if ( !SampDsStopped )
  {
    if ( !g_ShouldCallNtdsaApiset )
    {
      if ( RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\NTDS",
             L"DirectoryServiceExtPt",
             6u,
             0,
             String1,
             pcbData)
        || (CompareStringEx(&Annotation, 1u, String1, -1, &Annotation, -1, 0, 0, 0) & 0xFFFFFFFD) == 0 )
      {
        goto LABEL_19;
      }
      g_ShouldCallNtdsaApiset = 1;
    }
    NtdsaExtMaybeEndDsTransaction(3);
  }
LABEL_19:
  if ( _InterlockedDecrement((volatile signed __int32 *)&SampActiveThreadCount) == 0x40000000 )
    NtSetEvent(SampShutdownEventHandle, 0);
}

```

## disassembly

```asm
0x180016240  push    rbx
0x180016242  sub     rsp, 280h
0x180016249  mov     rax, cs:__security_cookie
0x180016250  xor     rax, rsp
0x180016253  mov     [rsp+288h+var_18], rax
0x18001625b  test    cl, cl
0x18001625d  jz      loc_180016317
0x180016263  mov     rcx, cs:WPP_GLOBAL_Control
0x18001626a  test    dword ptr [rcx+44h], 20000h
0x180016271  jnz     loc_180016366
0x180016277  cmp     cs:?SampUseDsData@@3EA, 0; uchar SampUseDsData
0x18001627e  jnz     loc_180016388
0x180016284  mov     rax, gs:30h
0x18001628d  mov     rcx, [rax+48h]
0x180016291  cmp     cs:?SampLock@@3U_RTL_CRITICAL_SECTION@@A.OwningThread, rcx; _RTL_CRITICAL_SECTION SampLock ...
0x180016298  jnz     loc_1800163C8
0x18001629e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800162a5  test    dword ptr [rcx+44h], 20000h
0x1800162ac  jnz     loc_1800163A1
0x1800162b2  mov     cs:?SampTransactionWithinDomainGlobal@@3EA, 0; uchar SampTransactionWithinDomainGlobal
0x1800162b9  cmp     cs:?SampUseDsData@@3EA, 0; uchar SampUseDsData
0x1800162c0  jnz     loc_18001642C
0x1800162c6  xor     bl, bl
0x1800162c8  test    dword ptr [rcx+44h], 20000h
0x1800162cf  jnz     loc_180016440
0x1800162d5  test    bl, bl
0x1800162d7  jnz     loc_18001645E
0x1800162dd  call    cs:__imp_GetTickCount
0x1800162e3  sub     eax, cs:?SamLockCurrentHoldStartTime@@3KA; ulong SamLockCurrentHoldStartTime
0x1800162e9  test    eax, eax
0x1800162eb  jg      loc_18001646D
0x1800162f1  lea     rcx, ?SampLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800162f8  call    cs:__imp_RtlLeaveCriticalSection
0x1800162fe  mov     rcx, [rsp+288h+var_18]
0x180016306  xor     rcx, rsp; StackCookie
0x180016309  call    __security_check_cookie
0x18001630e  add     rsp, 280h
0x180016315  pop     rbx
0x180016316  retn
0x180016317  xor     edx, edx; Val
0x180016319  lea     rcx, [rsp+288h+String1]; void *
0x18001631e  mov     r8d, 208h; Size
0x180016324  call    memset_0
0x180016329  cmp     cs:?SampDsStopped@@3EA, 0; uchar SampDsStopped
0x180016330  mov     ebx, 0FFFFFFFFh
0x180016335  mov     [rsp+288h+var_238], 208h
0x18001633d  jz      loc_180016485
0x180016343  lock xadd cs:?SampActiveThreadCount@@3KA, ebx; ulong SampActiveThreadCount
0x18001634b  dec     ebx
0x18001634d  cmp     ebx, 40000000h
0x180016353  jnz     short loc_1800162FE
0x180016355  mov     rcx, cs:?SampShutdownEventHandle@@3PEAXEA; EventHandle
0x18001635c  xor     edx, edx; PreviousState
0x18001635e  call    cs:__imp_NtSetEvent
0x180016364  jmp     short loc_1800162FE
0x180016366  movzx   r9d, cs:?SampUseDsData@@3EA; uchar SampUseDsData
0x18001636e  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x180016375  mov     rcx, [rcx+38h]
0x180016379  mov     edx, 49h ; 'I'
0x18001637e  call    WPP_SF_d
0x180016383  jmp     loc_180016277
0x180016388  call    ?SampExtIsWriteLockHeldByDs@@YAHXZ; SampExtIsWriteLockHeldByDs(void)
0x18001638d  test    eax, eax
0x18001638f  jz      loc_180016284
0x180016395  xor     ecx, ecx
0x180016397  call    SampSetTransactionWithinDomain
0x18001639c  jmp     loc_1800162FE
0x1800163a1  mov     rcx, [rcx+38h]
0x1800163a5  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x1800163ac  mov     edx, 0D1h
0x1800163b1  mov     r9d, 1
0x1800163b7  call    WPP_SF_d
0x1800163bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163c3  jmp     loc_1800162B2
0x1800163c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163cf  test    dword ptr [rcx+44h], 20000h
0x1800163d6  jz      short loc_1800163F7
0x1800163d8  mov     rcx, [rcx+38h]
0x1800163dc  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x1800163e3  mov     edx, 0D2h
0x1800163e8  xor     r9d, r9d
0x1800163eb  call    WPP_SF_d
0x1800163f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163f7  test    byte ptr [rcx+44h], 4
0x1800163fb  jz      loc_1800162B9
0x180016401  cmp     byte ptr [rcx+41h], 2
0x180016405  jb      loc_1800162B9
0x18001640b  mov     rcx, [rcx+38h]
0x18001640f  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x180016416  mov     edx, 0Ah
0x18001641b  call    WPP_SF_
0x180016420  mov     rcx, cs:WPP_GLOBAL_Control
0x180016427  jmp     loc_1800162B9
0x18001642c  cmp     cs:?SampDsStopped@@3EA, 0; uchar SampDsStopped
0x180016433  jnz     loc_1800162C6
0x180016439  mov     bl, 1
0x18001643b  jmp     loc_1800162C8
0x180016440  mov     rcx, [rcx+38h]
0x180016444  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x18001644b  movzx   r9d, bl
0x18001644f  mov     edx, 4Ah ; 'J'
0x180016454  call    WPP_SF_d
0x180016459  jmp     loc_1800162D5
0x18001645e  mov     ecx, 3
0x180016463  call    ?SampExtMaybeEndDsTransactionDs@@YAJW4SAMP_DS_TRANSACTION_CONTROL@@@Z; SampExtMaybeEndDsTransactionDs(SAMP_DS_TRANSACTION_CONTROL)
0x180016468  jmp     loc_1800162DD
0x18001646d  cmp     cs:?SamLockTotalAquisitions@@3KA, 0; ulong SamLockTotalAquisitions
0x180016474  jz      loc_1800162F1
0x18001647a  add     cs:?SamCumulativeHoldTime@@3KA, eax; ulong SamCumulativeHoldTime
0x180016480  jmp     loc_1800162F1
0x180016485  cmp     cs:?g_ShouldCallNtdsaApiset@@3HA, 0; int g_ShouldCallNtdsaApiset
0x18001648c  mov     [rsp+288h+arg_0], rdi
0x180016494  jnz     loc_18001651D
0x18001649a  lea     rax, [rsp+288h+var_238]
0x18001649f  xor     edi, edi
0x1800164a1  mov     [rsp+288h+pcbData], rax; pcbData
0x1800164a6  lea     r8, Value; "DirectoryServiceExtPt"
0x1800164ad  lea     rax, [rsp+288h+String1]
0x1800164b2  mov     r9d, 6; dwFlags
0x1800164b8  mov     [rsp+288h+pvData], rax; pvData
0x1800164bd  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\NT"...
0x1800164c4  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800164cb  mov     [rsp+288h+pdwType], rdi; pdwType
0x1800164d0  call    cs:__imp_RegGetValueW
0x1800164d6  test    eax, eax
0x1800164d8  jnz     short loc_180016528
0x1800164da  mov     [rsp+288h+lParam], rdi; lParam
0x1800164df  lea     rcx, Annotation; lpLocaleName
0x1800164e6  mov     [rsp+288h+lpReserved], rdi; lpReserved
0x1800164eb  lea     r8, [rsp+288h+String1]; lpString1
0x1800164f0  mov     [rsp+288h+pcbData], rdi; lpVersionInformation
0x1800164f5  mov     r9d, ebx; cchCount1
0x1800164f8  mov     dword ptr [rsp+288h+pvData], ebx; cchCount2
0x1800164fc  mov     edx, 1; dwCmpFlags
0x180016501  mov     [rsp+288h+pdwType], rcx; lpString2
0x180016506  call    cs:__imp_CompareStringEx
0x18001650c  test    eax, 0FFFFFFFDh
0x180016511  jz      short loc_180016528
0x180016513  mov     cs:?g_ShouldCallNtdsaApiset@@3HA, 1; int g_ShouldCallNtdsaApiset
0x18001651d  mov     ecx, 3
0x180016522  call    cs:__imp_NtdsaExtMaybeEndDsTransaction
0x180016528  mov     rdi, [rsp+288h+arg_0]
0x180016530  jmp     loc_180016343
```
