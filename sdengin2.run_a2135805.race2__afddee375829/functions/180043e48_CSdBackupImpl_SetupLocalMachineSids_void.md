# CSdBackupImpl::_SetupLocalMachineSids(void)

- ea: `0x180043e48`
- end: `0x180044046`
- name: `?_SetupLocalMachineSids@CSdBackupImpl@@AEAAJXZ`
- size: `510`
- prototype: `__int64 __fastcall(CSdBackupImpl *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001b4f4`

## callees

- `0x180043e48`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x180093698`

## import_xrefs

- `KERNEL32!GetComputerNameW` at `0x180043ea7`
- `KERNEL32!GetComputerNameW` at `0x180043ea7`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180043fb1`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180043fb1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180043fea`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180043fea`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180043f6b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180043f6b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180043eed`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180043eed`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18004401a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18004401a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180044005`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180044005`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180043f1d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180043f1d`

## string_xrefs

- `0x180043e66`: `CSdBackupImpl::_SetupLocalMachineSids`

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
    0x8CBu,
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
0x180043e48  mov     [rsp-8+arg_18], rbx
0x180043e4d  push    rbp
0x180043e4e  lea     rbp, [rsp-57h]
0x180043e53  sub     rsp, 90h
0x180043e5a  mov     rbx, rcx
0x180043e5d  xor     r9d, r9d; unsigned __int16
0x180043e60  mov     r8d, 8CBh; unsigned __int16
0x180043e66  lea     rdx, aCsdbackupimplS_4; "CSdBackupImpl::_SetupLocalMachineSids"
0x180043e6d  lea     rcx, [rbp+57h+var_40]; this
0x180043e71  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180043e76  xorps   xmm0, xmm0
0x180043e79  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180043e7d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180043e81  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180043e85  mov     [rbp+57h+PolicyHandle], 0
0x180043e8d  mov     [rbp+57h+Buffer], 0
0x180043e95  mov     [rbp+57h+nSize], 10h
0x180043e9c  lea     rcx, [rbx+114h]; lpBuffer
0x180043ea3  lea     rdx, [rbp+57h+nSize]; nSize
0x180043ea7  call    cs:__imp_GetComputerNameW
0x180043eae  nop     dword ptr [rax+rax+00h]
0x180043eb3  test    eax, eax
0x180043eb5  jnz     short loc_180043ECD
0x180043eb7  call    GetLastFailureAsHRESULT
0x180043ebc  mov     [rbp+57h+var_40], eax
0x180043ebf  mov     eax, 8D4h
0x180043ec4  mov     [rbp+57h+var_3A], ax
0x180043ec8  jmp     loc_180043FFC
0x180043ecd  mov     [rbp+57h+var_40], 0
0x180043ed4  mov     eax, 8D4h
0x180043ed9  mov     [rbp+57h+var_3C], ax
0x180043edd  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x180043ee1  mov     r8d, 1; DesiredAccess
0x180043ee7  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180043eeb  xor     ecx, ecx; SystemName
0x180043eed  call    cs:__imp_LsaOpenPolicy
0x180043ef4  nop     dword ptr [rax+rax+00h]
0x180043ef9  mov     ecx, eax
0x180043efb  call    HRESULTFromNTSTATUS
0x180043f00  mov     [rbp+57h+var_40], eax
0x180043f03  test    eax, eax
0x180043f05  mov     eax, 8D7h
0x180043f0a  js      short loc_180043EC4
0x180043f0c  mov     [rbp+57h+var_3C], ax
0x180043f10  lea     r8, [rbp+57h+Buffer]; Buffer
0x180043f14  mov     edx, 5; InformationClass
0x180043f19  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x180043f1d  call    cs:__imp_LsaQueryInformationPolicy
0x180043f24  nop     dword ptr [rax+rax+00h]
0x180043f29  mov     ecx, eax
0x180043f2b  call    HRESULTFromNTSTATUS
0x180043f30  mov     [rbp+57h+var_40], eax
0x180043f33  test    eax, eax
0x180043f35  mov     eax, 8DAh
0x180043f3a  js      short loc_180043EC4
0x180043f3c  mov     [rbp+57h+var_3C], ax
0x180043f40  mov     rcx, [rbp+57h+Buffer]
0x180043f44  mov     eax, 8DDh
0x180043f49  cmp     qword ptr [rcx+10h], 0
0x180043f4e  jnz     short loc_180043F5C
0x180043f50  mov     [rbp+57h+var_40], 81000036h
0x180043f57  jmp     loc_180043EC4
0x180043f5c  mov     [rbp+57h+var_40], 0
0x180043f63  mov     [rbp+57h+var_3C], ax
0x180043f67  mov     rcx, [rcx+10h]; pSid
0x180043f6b  call    cs:__imp_IsValidSid
0x180043f72  nop     dword ptr [rax+rax+00h]
0x180043f77  test    eax, eax
0x180043f79  jnz     short loc_180043F8D
0x180043f7b  call    GetLastFailureAsHRESULT
0x180043f80  mov     [rbp+57h+var_40], eax
0x180043f83  mov     eax, 8DEh
0x180043f88  jmp     loc_180043EC4
0x180043f8d  mov     [rbp+57h+var_40], 0
0x180043f94  mov     eax, 8DEh
0x180043f99  mov     [rbp+57h+var_3C], ax
0x180043f9d  mov     r8, [rbp+57h+Buffer]
0x180043fa1  mov     r8, [r8+10h]; pSourceSid
0x180043fa5  mov     rdx, [rbx+108h]; pDestinationSid
0x180043fac  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x180043fb1  call    cs:__imp_CopySid
0x180043fb8  nop     dword ptr [rax+rax+00h]
0x180043fbd  test    eax, eax
0x180043fbf  jnz     short loc_180043FD3
0x180043fc1  call    GetLastFailureAsHRESULT
0x180043fc6  mov     [rbp+57h+var_40], eax
0x180043fc9  mov     eax, 8E1h
0x180043fce  jmp     loc_180043EC4
0x180043fd3  mov     [rbp+57h+var_40], 0
0x180043fda  mov     eax, 8E1h
0x180043fdf  mov     [rbp+57h+var_3C], ax
0x180043fe3  mov     rcx, [rbx+108h]; pSid
0x180043fea  call    cs:__imp_GetLengthSid
0x180043ff1  nop     dword ptr [rax+rax+00h]
0x180043ff6  mov     [rbx+110h], eax
0x180043ffc  mov     rcx, [rbp+57h+Buffer]; Buffer
0x180044000  test    rcx, rcx
0x180044003  jz      short loc_180044011
0x180044005  call    cs:__imp_LsaFreeMemory
0x18004400c  nop     dword ptr [rax+rax+00h]
0x180044011  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x180044015  test    rcx, rcx
0x180044018  jz      short loc_180044026
0x18004401a  call    cs:__imp_LsaClose
0x180044021  nop     dword ptr [rax+rax+00h]
0x180044026  mov     ebx, [rbp+57h+var_40]
0x180044029  lea     rcx, [rbp+57h+var_40]; this
0x18004402d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180044032  mov     eax, ebx
0x180044034  mov     rbx, [rsp+90h+arg_18]
0x18004403c  add     rsp, 90h
0x180044043  pop     rbp
0x180044044  retn
```
