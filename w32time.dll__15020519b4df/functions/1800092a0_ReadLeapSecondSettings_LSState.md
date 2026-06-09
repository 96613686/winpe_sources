# ReadLeapSecondSettings(LSState *)

- ea: `0x1800092a0`
- end: `0x1800097c3`
- name: `?ReadLeapSecondSettings@@YAJPEAULSState@@@Z`
- size: `1315`
- prototype: `__int64 __fastcall(struct LSState *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008930`
- `0x1800118c0`

## callees

- `0x180001680`
- `0x180003ac0`
- `0x1800092a0`
- `0x1800097cc`
- `0x18000a818`
- `0x180018138`
- `0x18001d9a0`
- `0x18002b034`
- `0x18002b140`
- `0x18003d270`
- `0x18003dd2c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800095da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800095f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000968e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800095da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800095f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000968e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000933f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000933f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800092f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800092f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000937c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000937c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000943c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000943c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800093d5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180009423`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800093d5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180009423`

## string_xrefs

- `0x18000936e`: `System\CurrentControlSet\Services\W32Time\Config`

## pseudocode

```c
__int64 __fastcall ReadLeapSecondSettings(struct LSState *a1)
{
  HLOCAL v2; // r13
  int v3; // r14d
  unsigned int v4; // eax
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // r15
  void *v7; // rcx
  int LeapSecondCompiledStatusFromKernel; // edi
  int v9; // esi
  unsigned int v10; // r12d
  int LSStatusFromKernel; // r12d
  int v13; // eax
  __int64 i; // r8
  char *v15; // r9
  unsigned __int64 v16; // rcx
  __int64 j; // rsi
  const wchar_t *v18; // r9
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PVOID pvData; // [rsp+28h] [rbp-D8h]
  LPDWORD pcbData; // [rsp+30h] [rbp-D0h]
  DWORD pdwType; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v23; // [rsp+54h] [rbp-ACh] BYREF
  DWORD v24; // [rsp+58h] [rbp-A8h] BYREF
  int v25; // [rsp+5Ch] [rbp-A4h] BYREF
  HKEY hkey; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL v27; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v28; // [rsp+70h] [rbp-90h]
  HLOCAL hMem; // [rsp+78h] [rbp-88h] BYREF
  __int64 v30; // [rsp+80h] [rbp-80h]
  unsigned __int16 v31; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v32[126]; // [rsp+92h] [rbp-6Eh] BYREF
  unsigned __int16 v33; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v34[126]; // [rsp+112h] [rbp+12h] BYREF
  unsigned __int16 v35[512]; // [rsp+190h] [rbp+90h] BYREF

  v28 = *((_DWORD *)a1 + 24);
  v2 = 0;
  v3 = 0;
  v30 = *((_QWORD *)a1 + 7);
  hkey = 0;
  EnterCriticalSection(&stru_1800A4610);
  v4 = dword_1800A5284;
  v5 = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
  if ( (unsigned int)v5 < dword_1800A5278 )
    v4 = ++dword_1800A5284;
  dword_1800A5278 = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
  v6 = (unsigned int)v5 + ((unsigned __int64)v4 << 32);
  LeaveCriticalSection(&stru_1800A4610);
  *(_DWORD *)a1 = 0;
  v7 = (void *)*((_QWORD *)a1 + 3);
  if ( v7 )
  {
    LocalFree(v7);
    *((_QWORD *)a1 + 3) = 0;
    *((_DWORD *)a1 + 8) = 0;
  }
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\W32Time\\Config", 0, 0x20019u, &hkey);
  if ( hkey )
  {
    pdwType = 0;
    v23 = 0;
    v24 = 4;
    if ( !RegGetValueW(hkey, 0, L"TxLocalLeapSettingsAsLeapIndicator", 0xFFFFu, &pdwType, &v23, &v24) && pdwType == 4 )
      *(_DWORD *)a1 = v23 != 0;
    v24 = 4;
    if ( !RegGetValueW(hkey, 0, L"AddLeapSecondsUsingRxLeapIndicator", 0xFFFFu, &pdwType, &v23, &v24) && pdwType == 4 )
      *((_DWORD *)a1 + 1) = v23 != 0;
    RegCloseKey(hkey);
  }
  LeapSecondCompiledStatusFromKernel = GetLeapSecondCompiledStatusFromKernel(
                                         (struct LSState *)((char *)a1 + 16),
                                         (struct LSState *)((char *)a1 + 48));
  if ( LeapSecondCompiledStatusFromKernel < 0 )
    goto LABEL_10;
  v25 = 0;
  hMem = 0;
  v24 = 0;
  pdwType = 0;
  v27 = 0;
  v23 = 0;
  LSStatusFromKernel = GetLSStatusFromKernel(&v25, (struct _LEAP_SECOND_DATA_REGISTRY_ENTRY **)&hMem, &v24);
  if ( LSStatusFromKernel < 0
    || (v13 = ReadLSStatusFromRegistry((int *)&pdwType, (struct _LEAP_SECOND_DATA_REGISTRY_ENTRY **)&v27, &v23),
        v2 = v27,
        LSStatusFromKernel = v13,
        v13 < 0) )
  {
    v9 = 1;
    v3 = 1;
    if ( hMem )
      LocalFree(hMem);
  }
  else
  {
    v9 = 1;
    if ( v24 == v23 )
    {
      if ( v24 )
      {
        for ( i = 0; (unsigned int)i < v24; i = (unsigned int)(i + 1) )
        {
          v15 = (char *)hMem + 12 * i;
          v16 = *(_QWORD *)v15 - *(_QWORD *)((char *)v27 + 12 * i);
          if ( *(_QWORD *)v15 == *(_QWORD *)((char *)v27 + 12 * i) )
            v16 = *((unsigned int *)v15 + 2) - (unsigned __int64)*((unsigned int *)v27 + 3 * i + 2);
          if ( v16 )
            goto LABEL_24;
        }
      }
      if ( v25 == pdwType )
        v3 = 1;
    }
  }
LABEL_24:
  if ( v2 )
    LocalFree(v2);
  if ( LSStatusFromKernel >= 0 && v3 )
  {
    if ( *((_DWORD *)a1 + 24) )
      v9 = *((_DWORD *)a1 + 24);
    else
      *((_DWORD *)a1 + 24) = 1;
  }
  else
  {
LABEL_10:
    *((_DWORD *)a1 + 24) = 0;
    v9 = 0;
  }
  v10 = v28;
  if ( v28 != v9 || v30 != *((_QWORD *)a1 + 7) )
  {
    if ( (unsigned __int8)FileLogAllowEntry(18) )
      FileLogAdd(L"eLSState changed. Old State:%d. New State:%d\n", v10, *((unsigned int *)a1 + 24));
    *((_QWORD *)a1 + 13) = v6;
  }
  v35[0] = 0;
  if ( dword_1800A4720 )
  {
    for ( j = dword_1800A4720 - 1; (int)j >= 0; j = (unsigned int)(j - 1) )
    {
      v31 = 0;
      memset_0(v32, 0, sizeof(v32));
      v33 = 0;
      memset_0(v34, 0, sizeof(v34));
      LODWORD(pcbData) = *((unsigned __int16 *)qword_1800A4718 + 20 * j + 8);
      LODWORD(pvData) = *((unsigned __int16 *)qword_1800A4718 + 20 * j + 7);
      LODWORD(phkResult) = *((unsigned __int16 *)qword_1800A4718 + 20 * j + 5);
      StringCchPrintfW(
        &v31,
        0x40u,
        L"%04u-%02u-%02uT%02u:59:59",
        *((unsigned __int16 *)qword_1800A4718 + 20 * j + 4),
        phkResult,
        pvData,
        pcbData);
      v18 = L"-";
      if ( !*((_DWORD *)qword_1800A4718 + 10 * j + 6) )
        v18 = L"+";
      if ( (int)StringCchPrintfW(&v33, 0x40u, L"%s%s\n", v18, &v31) < 0 )
        break;
      if ( (int)StringCchCatW(v35, 0x200u, &v33) < 0 )
        break;
    }
  }
  LODWORD(phkResult) = dword_1800A4710;
  LogThrottledEvent(&_W32TimeRegistrationHandle, W32TIME_OPS_LEAP_SECOND_CONFIG, L"ddDdSi", 60000, phkResult);
  return (unsigned int)LeapSecondCompiledStatusFromKernel;
}

```

## disassembly

```asm
0x1800092a0  push    rbp
0x1800092a2  push    rbx
0x1800092a3  push    rsi
0x1800092a4  push    rdi
0x1800092a5  push    r12
0x1800092a7  push    r13
0x1800092a9  push    r14
0x1800092ab  push    r15
0x1800092ad  lea     rbp, [rsp-4A8h]
0x1800092b5  sub     rsp, 5A8h
0x1800092bc  mov     rax, cs:__security_cookie
0x1800092c3  xor     rax, rsp
0x1800092c6  mov     [rbp+4E0h+var_50], rax
0x1800092cd  mov     eax, [rcx+60h]
0x1800092d0  mov     rbx, rcx
0x1800092d3  mov     [rsp+5E0h+var_570], eax
0x1800092d7  xor     r13d, r13d
0x1800092da  mov     rax, [rcx+38h]
0x1800092de  mov     r14d, r13d
0x1800092e1  lea     rcx, stru_1800A4610; lpCriticalSection
0x1800092e8  mov     [rbp+4E0h+var_560], rax
0x1800092ec  mov     [rsp+5E0h+hkey], r13
0x1800092f1  call    cs:__imp_EnterCriticalSection
0x1800092f8  nop     dword ptr [rax+rax+00h]
0x1800092fd  mov     eax, 7FFE0320h
0x180009302  mov     rax, [rax]
0x180009305  mov     ecx, ds:7FFE0004h
0x18000930c  imul    rcx, rax
0x180009310  mov     eax, cs:dword_1800A5284
0x180009316  shr     rcx, 18h
0x18000931a  cmp     ecx, cs:dword_1800A5278
0x180009320  jb      loc_1800095E8
0x180009326  mov     r15d, eax
0x180009329  mov     eax, ecx
0x18000932b  mov     cs:dword_1800A5278, ecx
0x180009331  lea     rcx, stru_1800A4610; lpCriticalSection
0x180009338  shl     r15, 20h
0x18000933c  add     r15, rax
0x18000933f  call    cs:__imp_LeaveCriticalSection
0x180009346  nop     dword ptr [rax+rax+00h]
0x18000934b  mov     [rbx], r13d
0x18000934e  mov     rcx, [rbx+18h]; hMem
0x180009352  test    rcx, rcx
0x180009355  jnz     loc_1800095F5
0x18000935b  lea     rax, [rsp+5E0h+hkey]
0x180009360  mov     r9d, 20019h; samDesired
0x180009366  xor     r8d, r8d; ulOptions
0x180009369  mov     [rsp+5E0h+phkResult], rax; phkResult
0x18000936e  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x180009375  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000937c  call    cs:__imp_RegOpenKeyExW
0x180009383  nop     dword ptr [rax+rax+00h]
0x180009388  mov     rcx, [rsp+5E0h+hkey]; hkey
0x18000938d  test    rcx, rcx
0x180009390  jz      loc_180009448
0x180009396  lea     rax, [rsp+5E0h+var_588]
0x18000939b  mov     [rsp+5E0h+pdwType], r13d
0x1800093a0  mov     [rsp+5E0h+pcbData], rax; pcbData
0x1800093a5  lea     r8, aTxlocalleapset; "TxLocalLeapSettingsAsLeapIndicator"
0x1800093ac  lea     rax, [rsp+5E0h+var_58C]
0x1800093b1  mov     [rsp+5E0h+var_58C], r13d
0x1800093b6  mov     [rsp+5E0h+pvData], rax; pvData
0x1800093bb  mov     r9d, 0FFFFh; dwFlags
0x1800093c1  lea     rax, [rsp+5E0h+pdwType]
0x1800093c6  mov     [rsp+5E0h+var_588], 4
0x1800093ce  xor     edx, edx; lpSubKey
0x1800093d0  mov     [rsp+5E0h+phkResult], rax; pdwType
0x1800093d5  call    cs:__imp_RegGetValueW
0x1800093dc  nop     dword ptr [rax+rax+00h]
0x1800093e1  test    eax, eax
0x1800093e3  jz      loc_18000960E
0x1800093e9  mov     rcx, [rsp+5E0h+hkey]; hkey
0x1800093ee  lea     rax, [rsp+5E0h+var_588]
0x1800093f3  mov     [rsp+5E0h+pcbData], rax; pcbData
0x1800093f8  lea     r8, aAddleapseconds; "AddLeapSecondsUsingRxLeapIndicator"
0x1800093ff  lea     rax, [rsp+5E0h+var_58C]
0x180009404  mov     [rsp+5E0h+var_588], 4
0x18000940c  mov     [rsp+5E0h+pvData], rax; pvData
0x180009411  mov     r9d, 0FFFFh; dwFlags
0x180009417  lea     rax, [rsp+5E0h+pdwType]
0x18000941c  xor     edx, edx; lpSubKey
0x18000941e  mov     [rsp+5E0h+phkResult], rax; pdwType
0x180009423  call    cs:__imp_RegGetValueW
0x18000942a  nop     dword ptr [rax+rax+00h]
0x18000942f  test    eax, eax
0x180009431  jz      loc_18000962A
0x180009437  mov     rcx, [rsp+5E0h+hkey]; hKey
0x18000943c  call    cs:__imp_RegCloseKey
0x180009443  nop     dword ptr [rax+rax+00h]
0x180009448  lea     rdx, [rbx+30h]; struct KernelLSSnapshot *
0x18000944c  lea     rcx, [rbx+10h]; struct KernelLSCompiledInfo *
0x180009450  call    ?GetLeapSecondCompiledStatusFromKernel@@YAJPEAUKernelLSCompiledInfo@@PEAUKernelLSSnapshot@@@Z; GetLeapSecondCompiledStatusFromKernel(KernelLSCompiledInfo *,KernelLSSnapshot *)
0x180009455  mov     edi, eax
0x180009457  test    eax, eax
0x180009459  jns     loc_18000952E
0x18000945f  mov     [rbx+60h], r13d
0x180009463  mov     esi, r13d
0x180009466  mov     r12d, [rsp+5E0h+var_570]
0x18000946b  cmp     r12d, esi
0x18000946e  jnz     loc_1800096A7
0x180009474  mov     rax, [rbx+38h]
0x180009478  cmp     [rbp+4E0h+var_560], rax
0x18000947c  jnz     loc_1800096A7
0x180009482  mov     eax, cs:dword_1800A4720
0x180009488  mov     [rbp+4E0h+var_450], r13w
0x180009490  test    eax, eax
0x180009492  jnz     loc_1800096D1
0x180009498  mov     rax, cs:qword_1800A4738
0x18000949f  lea     rcx, [rbp+4E0h+var_450]
0x1800094a6  mov     [rsp+5E0h+var_598], r15
0x1800094ab  lea     r8, aDdddsi; "ddDdSi"
0x1800094b2  mov     [rsp+5E0h+var_5A0], rcx
0x1800094b7  lea     rdx, W32TIME_OPS_LEAP_SECOND_CONFIG
0x1800094be  mov     [rsp+5E0h+var_5A8], r14d
0x1800094c3  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x1800094ca  mov     dword ptr [rsp+5E0h+pcbData], eax
0x1800094ce  mov     r9d, 0EA60h
0x1800094d4  mov     eax, cs:dword_1800A4720
0x1800094da  mov     dword ptr [rsp+5E0h+pvData], eax
0x1800094de  mov     eax, cs:dword_1800A4710
0x1800094e4  mov     dword ptr [rsp+5E0h+phkResult], eax
0x1800094e8  call    LogThrottledEvent
0x1800094ed  mov     eax, edi
0x1800094ef  mov     rcx, [rbp+4E0h+var_50]
0x1800094f6  xor     rcx, rsp; StackCookie
0x1800094f9  call    __security_check_cookie
0x1800094fe  add     rsp, 5A8h
0x180009505  pop     r15
0x180009507  pop     r14
0x180009509  pop     r13
0x18000950b  pop     r12
0x18000950d  pop     rdi
0x18000950e  pop     rsi
0x18000950f  pop     rbx
0x180009510  pop     rbp
0x180009511  retn
0x180009513  test    r14d, r14d
0x180009516  jz      loc_18000945F
0x18000951c  mov     eax, [rbx+60h]
0x18000951f  test    eax, eax
0x180009521  jz      loc_18000969F
0x180009527  mov     esi, eax
0x180009529  jmp     loc_180009466
0x18000952e  lea     r8, [rsp+5E0h+var_588]; unsigned int *
0x180009533  mov     [rsp+5E0h+var_584], r13d
0x180009538  lea     rdx, [rsp+5E0h+hMem]; struct _LEAP_SECOND_DATA_REGISTRY_ENTRY **
0x18000953d  mov     [rsp+5E0h+hMem], r13
0x180009542  lea     rcx, [rsp+5E0h+var_584]; int *
0x180009547  mov     [rsp+5E0h+var_588], r13d
0x18000954c  mov     [rsp+5E0h+pdwType], r13d
0x180009551  mov     [rsp+5E0h+var_578], r13
0x180009556  mov     [rsp+5E0h+var_58C], r13d
0x18000955b  call    ?GetLSStatusFromKernel@@YAJPEAHPEAPEAU_LEAP_SECOND_DATA_REGISTRY_ENTRY@@PEAK@Z; GetLSStatusFromKernel(int *,_LEAP_SECOND_DATA_REGISTRY_ENTRY * *,ulong *)
0x180009560  mov     r12d, eax
0x180009563  test    eax, eax
0x180009565  js      short loc_1800095C8
0x180009567  lea     r8, [rsp+5E0h+var_58C]; unsigned int *
0x18000956c  lea     rdx, [rsp+5E0h+var_578]; struct _LEAP_SECOND_DATA_REGISTRY_ENTRY **
0x180009571  lea     rcx, [rsp+5E0h+pdwType]; int *
0x180009576  call    ?ReadLSStatusFromRegistry@@YAJPEAHPEAPEAU_LEAP_SECOND_DATA_REGISTRY_ENTRY@@PEAK@Z; ReadLSStatusFromRegistry(int *,_LEAP_SECOND_DATA_REGISTRY_ENTRY * *,ulong *)
0x18000957b  mov     r13, [rsp+5E0h+var_578]
0x180009580  mov     r12d, eax
0x180009583  test    eax, eax
0x180009585  js      short loc_1800095C8
0x180009587  mov     edx, [rsp+5E0h+var_588]
0x18000958b  mov     esi, 1
0x180009590  cmp     edx, [rsp+5E0h+var_58C]
0x180009594  jnz     short loc_1800095AB
0x180009596  test    edx, edx
0x180009598  jnz     loc_180009647
0x18000959e  mov     eax, [rsp+5E0h+pdwType]
0x1800095a2  cmp     [rsp+5E0h+var_584], eax
0x1800095a6  jnz     short loc_1800095AB
0x1800095a8  mov     r14d, esi
0x1800095ab  test    r13, r13
0x1800095ae  jnz     loc_18000968B
0x1800095b4  xor     r13d, r13d
0x1800095b7  test    r12d, r12d
0x1800095ba  jns     loc_180009513
0x1800095c0  mov     r14d, r13d
0x1800095c3  jmp     loc_18000945F
0x1800095c8  mov     rcx, [rsp+5E0h+hMem]; hMem
0x1800095cd  mov     esi, 1
0x1800095d2  mov     r14d, esi
0x1800095d5  test    rcx, rcx
0x1800095d8  jz      short loc_1800095AB
0x1800095da  call    cs:__imp_LocalFree
0x1800095e1  nop     dword ptr [rax+rax+00h]
0x1800095e6  jmp     short loc_1800095AB
0x1800095e8  inc     eax
0x1800095ea  mov     cs:dword_1800A5284, eax
0x1800095f0  jmp     loc_180009326
0x1800095f5  call    cs:__imp_LocalFree
0x1800095fc  nop     dword ptr [rax+rax+00h]
0x180009601  mov     [rbx+18h], r13
0x180009605  mov     [rbx+20h], r13d
0x180009609  jmp     loc_18000935B
0x18000960e  cmp     [rsp+5E0h+pdwType], 4
0x180009613  jnz     loc_1800093E9
0x180009619  mov     eax, r13d
0x18000961c  cmp     [rsp+5E0h+var_58C], eax
0x180009620  setnz   al
0x180009623  mov     [rbx], eax
0x180009625  jmp     loc_1800093E9
0x18000962a  cmp     [rsp+5E0h+pdwType], 4
0x18000962f  jnz     loc_180009437
0x180009635  mov     eax, r13d
0x180009638  cmp     [rsp+5E0h+var_58C], eax
0x18000963c  setnz   al
0x18000963f  mov     [rbx+4], eax
0x180009642  jmp     loc_180009437
0x180009647  mov     r10, [rsp+5E0h+hMem]
0x18000964c  xor     r8d, r8d
0x18000964f  cmp     r8d, edx
0x180009652  jnb     loc_18000959E
0x180009658  lea     rcx, [r8+r8*2]
0x18000965c  lea     r9, [r10+rcx*4]
0x180009660  lea     rax, ds:0[rcx*4]
0x180009668  mov     rcx, [r9]
0x18000966b  sub     rcx, [rax+r13]
0x18000966f  jnz     short loc_18000967D
0x180009671  mov     ecx, [r9+8]
0x180009675  mov     eax, [rax+r13+8]
0x18000967a  sub     rcx, rax
0x18000967d  test    rcx, rcx
0x180009680  jnz     loc_1800095AB
0x180009686  inc     r8d
0x180009689  jmp     short loc_18000964F
0x18000968b  mov     rcx, r13; hMem
0x18000968e  call    cs:__imp_LocalFree
0x180009695  nop     dword ptr [rax+rax+00h]
0x18000969a  jmp     loc_1800095B4
0x18000969f  mov     [rbx+60h], esi
0x1800096a2  jmp     loc_180009466
0x1800096a7  mov     ecx, 12h
0x1800096ac  call    FileLogAllowEntry
0x1800096b1  test    al, al
0x1800096b3  jz      short loc_1800096C8
0x1800096b5  mov     r8d, [rbx+60h]
0x1800096b9  lea     rcx, aElsstateChange; "eLSState changed. Old State:%d. New Sta"...
0x1800096c0  mov     edx, r12d
0x1800096c3  call    FileLogAdd
0x1800096c8  mov     [rbx+68h], r15
0x1800096cc  jmp     loc_180009482
0x1800096d1  lea     esi, [rax-1]
0x1800096d4  test    esi, esi
0x1800096d6  js      loc_180009498
0x1800096dc  lea     r12, asc_18008016C; "+"
0x1800096e3  xor     edx, edx; Val
0x1800096e5  mov     [rbp+4E0h+var_550], r13w
0x1800096ea  mov     r8d, 7Eh ; '~'; Size
0x1800096f0  lea     rcx, [rbp+4E0h+var_54E]; void *
0x1800096f4  call    memset_0
0x1800096f9  xor     edx, edx; Val
0x1800096fb  mov     [rbp+4E0h+var_4D0], r13w
0x180009700  mov     r8d, 7Eh ; '~'; Size
0x180009706  lea     rcx, [rbp+4E0h+var_4CE]; void *
0x18000970a  call    memset_0
0x18000970f  mov     r8, cs:qword_1800A4718
0x180009716  lea     rcx, [rsi+rsi*4]
0x18000971a  lea     rbx, ds:0[rcx*8]
0x180009722  movzx   ecx, word ptr [rbx+r8+0Eh]
0x180009728  movzx   edx, word ptr [rbx+r8+0Ah]
0x18000972e  movzx   eax, word ptr [rbx+r8+10h]
0x180009734  movzx   r9d, word ptr [rbx+r8+8]
0x18000973a  lea     r8, a04u02u02ut02u5; "%04u-%02u-%02uT%02u:59:59"
0x180009741  mov     dword ptr [rsp+5E0h+pcbData], eax
0x180009745  mov     dword ptr [rsp+5E0h+pvData], ecx
0x180009749  lea     rcx, [rbp+4E0h+var_550]; unsigned __int16 *
0x18000974d  mov     dword ptr [rsp+5E0h+phkResult], edx
0x180009751  mov     edx, 40h ; '@'; unsigned __int64
0x180009756  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000975b  mov     rax, cs:qword_1800A4718
0x180009762  lea     r9, asc_180080168; "-"
0x180009769  lea     r8, aSS_1; "%s%s\n"
0x180009770  mov     edx, 40h ; '@'; unsigned __int64
0x180009775  lea     rcx, [rbp+4E0h+var_4D0]; unsigned __int16 *
0x180009779  cmp     dword ptr [rbx+rax+18h], 0
0x18000977e  lea     rax, [rbp+4E0h+var_550]
0x180009782  mov     [rsp+5E0h+phkResult], rax
0x180009787  cmovz   r9, r12
0x18000978b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009790  test    eax, eax
0x180009792  js      loc_180009498
0x180009798  lea     r8, [rbp+4E0h+var_4D0]; unsigned __int16 *
0x18000979c  mov     edx, 200h; unsigned __int64
0x1800097a1  lea     rcx, [rbp+4E0h+var_450]; unsigned __int16 *
0x1800097a8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800097ad  test    eax, eax
0x1800097af  js      loc_180009498
0x1800097b5  sub     esi, 1
0x1800097b8  jns     loc_1800096E3
0x1800097be  jmp     loc_180009498
```
