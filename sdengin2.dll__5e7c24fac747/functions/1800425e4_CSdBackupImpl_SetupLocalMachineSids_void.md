# CSdBackupImpl::_SetupLocalMachineSids(void)

- ea: `0x1800425e4`
- end: `0x1800427b1`
- name: `?_SetupLocalMachineSids@CSdBackupImpl@@AEAAJXZ`
- size: `461`
- prototype: `__int64 __fastcall(CSdBackupImpl *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001aa60`

## callees

- `0x1800425e4`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x18008f660`

## import_xrefs

- `KERNEL32!GetComputerNameW` at `0x180042643`
- `KERNEL32!GetComputerNameW` at `0x180042643`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180042735`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180042735`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180042768`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180042768`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800426f5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800426f5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180042683`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180042683`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18004278c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18004278c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18004277d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18004277d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800426ad`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800426ad`

## string_xrefs

- `0x180042602`: `CSdBackupImpl::_SetupLocalMachineSids`

## pseudocode

```c
__int64 __fastcall CSdBackupImpl::_SetupLocalMachineSids(CSdBackupImpl *this)
{
  __int64 v2; // rcx
  __int16 v3; // ax
  unsigned int v4; // eax
  unsigned int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rcx
  unsigned int v8; // ebx
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-19h] BYREF
  int LastFailureAsHRESULT; // [rsp+50h] [rbp+17h] BYREF
  __int16 v12; // [rsp+54h] [rbp+1Bh]
  __int16 v13; // [rsp+56h] [rbp+1Dh]
  DWORD nSize; // [rsp+A0h] [rbp+67h] BYREF
  PVOID Buffer; // [rsp+A8h] [rbp+6Fh] BYREF
  PVOID PolicyHandle; // [rsp+B0h] [rbp+77h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CSdBackupImpl::_SetupLocalMachineSids",
    2251,
    0);
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  PolicyHandle = 0;
  Buffer = 0;
  nSize = 16;
  if ( !GetComputerNameW((LPWSTR)this + 138, &nSize) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v2);
    v3 = 2260;
LABEL_3:
    v13 = v3;
    goto LABEL_13;
  }
  LastFailureAsHRESULT = 0;
  v12 = 2260;
  v4 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  LastFailureAsHRESULT = HRESULTFromNTSTATUS(v4);
  v3 = 2263;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v12 = 2263;
  v5 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
  LastFailureAsHRESULT = HRESULTFromNTSTATUS(v5);
  v3 = 2266;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v12 = 2266;
  v3 = 2269;
  if ( !*((_QWORD *)Buffer + 2) )
  {
    LastFailureAsHRESULT = -2130706378;
    goto LABEL_3;
  }
  LastFailureAsHRESULT = 0;
  v12 = 2269;
  if ( !IsValidSid(*((PSID *)Buffer + 2)) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v6);
    v3 = 2270;
    goto LABEL_3;
  }
  LastFailureAsHRESULT = 0;
  v12 = 2270;
  if ( !CopySid(0x44u, *((PSID *)this + 33), *((PSID *)Buffer + 2)) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7);
    v3 = 2273;
    goto LABEL_3;
  }
  LastFailureAsHRESULT = 0;
  v12 = 2273;
  *((_DWORD *)this + 68) = GetLengthSid(*((PSID *)this + 33));
LABEL_13:
  if ( Buffer )
    LsaFreeMemory(Buffer);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  v8 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v8;
}

```

## disassembly

```asm
0x1800425e4  mov     [rsp-8+arg_18], rbx
0x1800425e9  push    rbp
0x1800425ea  lea     rbp, [rsp-57h]
0x1800425ef  sub     rsp, 90h
0x1800425f6  mov     rbx, rcx
0x1800425f9  xor     r9d, r9d; unsigned __int16
0x1800425fc  mov     r8d, 8CBh; unsigned __int16
0x180042602  lea     rdx, aCsdbackupimplS_4; "CSdBackupImpl::_SetupLocalMachineSids"
0x180042609  lea     rcx, [rbp+57h+var_40]; this
0x18004260d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180042612  xorps   xmm0, xmm0
0x180042615  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180042619  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18004261d  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180042621  mov     [rbp+57h+PolicyHandle], 0
0x180042629  mov     [rbp+57h+Buffer], 0
0x180042631  mov     [rbp+57h+nSize], 10h
0x180042638  lea     rcx, [rbx+114h]; lpBuffer
0x18004263f  lea     rdx, [rbp+57h+nSize]; nSize
0x180042643  call    cs:__imp_GetComputerNameW
0x180042649  test    eax, eax
0x18004264b  jnz     short loc_180042663
0x18004264d  call    GetLastFailureAsHRESULT
0x180042652  mov     [rbp+57h+var_40], eax
0x180042655  mov     eax, 8D4h
0x18004265a  mov     [rbp+57h+var_3A], ax
0x18004265e  jmp     loc_180042774
0x180042663  mov     [rbp+57h+var_40], 0
0x18004266a  mov     eax, 8D4h
0x18004266f  mov     [rbp+57h+var_3C], ax
0x180042673  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x180042677  mov     r8d, 1; DesiredAccess
0x18004267d  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180042681  xor     ecx, ecx; SystemName
0x180042683  call    cs:__imp_LsaOpenPolicy
0x180042689  mov     ecx, eax
0x18004268b  call    HRESULTFromNTSTATUS
0x180042690  mov     [rbp+57h+var_40], eax
0x180042693  test    eax, eax
0x180042695  mov     eax, 8D7h
0x18004269a  js      short loc_18004265A
0x18004269c  mov     [rbp+57h+var_3C], ax
0x1800426a0  lea     r8, [rbp+57h+Buffer]; Buffer
0x1800426a4  mov     edx, 5; InformationClass
0x1800426a9  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x1800426ad  call    cs:__imp_LsaQueryInformationPolicy
0x1800426b3  mov     ecx, eax
0x1800426b5  call    HRESULTFromNTSTATUS
0x1800426ba  mov     [rbp+57h+var_40], eax
0x1800426bd  test    eax, eax
0x1800426bf  mov     eax, 8DAh
0x1800426c4  js      short loc_18004265A
0x1800426c6  mov     [rbp+57h+var_3C], ax
0x1800426ca  mov     rcx, [rbp+57h+Buffer]
0x1800426ce  mov     eax, 8DDh
0x1800426d3  cmp     qword ptr [rcx+10h], 0
0x1800426d8  jnz     short loc_1800426E6
0x1800426da  mov     [rbp+57h+var_40], 81000036h
0x1800426e1  jmp     loc_18004265A
0x1800426e6  mov     [rbp+57h+var_40], 0
0x1800426ed  mov     [rbp+57h+var_3C], ax
0x1800426f1  mov     rcx, [rcx+10h]; pSid
0x1800426f5  call    cs:__imp_IsValidSid
0x1800426fb  test    eax, eax
0x1800426fd  jnz     short loc_180042711
0x1800426ff  call    GetLastFailureAsHRESULT
0x180042704  mov     [rbp+57h+var_40], eax
0x180042707  mov     eax, 8DEh
0x18004270c  jmp     loc_18004265A
0x180042711  mov     [rbp+57h+var_40], 0
0x180042718  mov     eax, 8DEh
0x18004271d  mov     [rbp+57h+var_3C], ax
0x180042721  mov     r8, [rbp+57h+Buffer]
0x180042725  mov     r8, [r8+10h]; pSourceSid
0x180042729  mov     rdx, [rbx+108h]; pDestinationSid
0x180042730  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x180042735  call    cs:__imp_CopySid
0x18004273b  test    eax, eax
0x18004273d  jnz     short loc_180042751
0x18004273f  call    GetLastFailureAsHRESULT
0x180042744  mov     [rbp+57h+var_40], eax
0x180042747  mov     eax, 8E1h
0x18004274c  jmp     loc_18004265A
0x180042751  mov     [rbp+57h+var_40], 0
0x180042758  mov     eax, 8E1h
0x18004275d  mov     [rbp+57h+var_3C], ax
0x180042761  mov     rcx, [rbx+108h]; pSid
0x180042768  call    cs:__imp_GetLengthSid
0x18004276e  mov     [rbx+110h], eax
0x180042774  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180042778  test    rcx, rcx
0x18004277b  jz      short loc_180042783
0x18004277d  call    cs:__imp_LsaFreeMemory
0x180042783  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x180042787  test    rcx, rcx
0x18004278a  jz      short loc_180042792
0x18004278c  call    cs:__imp_LsaClose
0x180042792  mov     ebx, [rbp+57h+var_40]
0x180042795  lea     rcx, [rbp+57h+var_40]; this
0x180042799  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18004279e  mov     eax, ebx
0x1800427a0  mov     rbx, [rsp+90h+arg_18]
0x1800427a8  add     rsp, 90h
0x1800427af  pop     rbp
0x1800427b0  retn
```
