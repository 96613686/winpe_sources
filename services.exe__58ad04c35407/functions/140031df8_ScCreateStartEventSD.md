# ScCreateStartEventSD

- ea: `0x140031df8`
- end: `0x14003200d`
- name: `ScCreateStartEventSD`
- size: `533`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x140031cb8`

## callees

- `0x140016318`
- `0x140031df8`
- `0x1400575b0`
- `0x14005ab2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031ee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031ee8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140031fe9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140031fe9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140031ea7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140031ea7`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x140031f96`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x140031f96`
- `ntdll!RtlNtStatusToDosError` at `0x140031fa2`
- `ntdll!RtlNtStatusToDosError` at `0x140031fa2`

## pseudocode

```c
__int64 __fastcall ScCreateStartEventSD(_QWORD *a1)
{
  ULONG LastError; // eax
  ULONG v3; // ebx
  NTSTATUS v4; // eax
  __int64 v6; // [rsp+60h] [rbp-49h] BYREF
  __int16 v7; // [rsp+70h] [rbp-39h] BYREF
  char v8; // [rsp+72h] [rbp-37h]
  int v9; // [rsp+74h] [rbp-35h]
  PSID *v10; // [rsp+78h] [rbp-31h]
  __int16 v11; // [rsp+80h] [rbp-29h]
  char v12; // [rsp+82h] [rbp-27h]
  int v13; // [rsp+84h] [rbp-25h]
  PSID *v14; // [rsp+88h] [rbp-21h]
  __int16 v15; // [rsp+90h] [rbp-19h]
  char v16; // [rsp+92h] [rbp-17h]
  int v17; // [rsp+94h] [rbp-15h]
  PSID *v18; // [rsp+98h] [rbp-11h]
  __int16 v19; // [rsp+A0h] [rbp-9h]
  char v20; // [rsp+A2h] [rbp-7h]
  int v21; // [rsp+A4h] [rbp-5h]
  __int64 *v22; // [rsp+A8h] [rbp-1h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B0h] [rbp+7h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v24; // [rsp+B8h] [rbp+Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v25; // [rsp+C0h] [rbp+17h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  v6 = 0;
  v9 = 0x100000;
  v17 = 0x100000;
  v21 = 0x100000;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v22 = &LpacServicesManagementCapabilitySid;
  *(_DWORD *)v24.Value = 0;
  *(_WORD *)&v24.Value[4] = 1280;
  *(_DWORD *)v25.Value = 0;
  *(_WORD *)&v25.Value[4] = 3840;
  v7 = 0;
  v8 = 0;
  v10 = &WorldSid;
  v11 = 0;
  v12 = 0;
  v13 = 0x10000000;
  v14 = &LocalSystemSid;
  v15 = 0;
  v16 = 0;
  v18 = &AnyPackageSid;
  v19 = 0;
  v20 = 0;
  RtlAcquireSRWLockExclusive(&qword_1400BC960);
  if ( (WorldSid || AllocateAndInitializeSid_0(&pIdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &WorldSid))
    && (LocalSystemSid || AllocateAndInitializeSid_0(&v24, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &LocalSystemSid))
    && (AnyPackageSid || AllocateAndInitializeSid_0(&v25, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, &AnyPackageSid)) )
  {
    if ( !LpacServicesManagementCapabilitySid )
    {
      v4 = RtlDeriveCapabilitySidsFromName(
             L",.",
             &LpacServicesManagementCapabilityGroupSidBuffer,
             &LpacServicesManagementCapabilitySidBuffer);
      if ( v4 < 0 )
      {
LABEL_11:
        LastError = RtlNtStatusToDosError(v4);
        goto LABEL_4;
      }
      LpacServicesManagementCapabilitySid = (__int64)&LpacServicesManagementCapabilitySidBuffer;
    }
    v4 = ScCreateAndSetSD((unsigned int)&v7, 4, (_DWORD)LocalSystemSid, (_DWORD)LocalSystemSid, (__int64)&v6);
    if ( v4 >= 0 )
    {
      *a1 = v6;
      v3 = 0;
      goto LABEL_15;
    }
    goto LABEL_11;
  }
  LastError = GetLastError();
LABEL_4:
  v3 = LastError;
LABEL_15:
  RtlReleaseSRWLockExclusive(&qword_1400BC960);
  return v3;
}

```

## disassembly

```asm
0x140031df8  push    rbp
0x140031dfa  push    rbx
0x140031dfb  push    rsi
0x140031dfc  push    rdi
0x140031dfd  push    r14
0x140031dff  push    r15
0x140031e01  lea     rbp, [rsp-2Fh]
0x140031e06  sub     rsp, 0D8h
0x140031e0d  mov     rax, cs:__security_cookie
0x140031e14  xor     rax, rsp
0x140031e17  mov     [rbp+57h+var_38], rax
0x140031e1b  xor     edi, edi
0x140031e1d  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 100h
0x140031e23  mov     eax, 100000h
0x140031e28  mov     [rbp+57h+var_A0], rdi
0x140031e2c  mov     [rbp+57h+var_8C], eax
0x140031e2f  lea     rsi, WorldSid
0x140031e36  mov     [rbp+57h+var_6C], eax
0x140031e39  lea     r14, LocalSystemSid
0x140031e40  mov     [rbp+57h+var_5C], eax
0x140031e43  lea     r15, AnyPackageSid
0x140031e4a  lea     rax, LpacServicesManagementCapabilitySid
0x140031e51  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x140031e54  mov     rbx, rcx
0x140031e57  mov     [rbp+57h+var_58], rax
0x140031e5b  lea     rcx, qword_1400BC960
0x140031e62  mov     dword ptr [rbp+57h+var_48.Value], edi
0x140031e65  mov     word ptr [rbp+57h+var_48.Value+4], 500h
0x140031e6b  mov     dword ptr [rbp+57h+var_40.Value], edi
0x140031e6e  mov     word ptr [rbp+57h+var_40.Value+4], 0F00h
0x140031e74  mov     [rbp+57h+var_90], di
0x140031e78  mov     [rbp+57h+var_8E], dil
0x140031e7c  mov     [rbp+57h+var_88], rsi
0x140031e80  mov     [rbp+57h+var_80], di
0x140031e84  mov     [rbp+57h+var_7E], dil
0x140031e88  mov     [rbp+57h+var_7C], 10000000h
0x140031e8f  mov     [rbp+57h+var_78], r14
0x140031e93  mov     [rbp+57h+var_70], di
0x140031e97  mov     [rbp+57h+var_6E], dil
0x140031e9b  mov     [rbp+57h+var_68], r15
0x140031e9f  mov     [rbp+57h+var_60], di
0x140031ea3  mov     [rbp+57h+var_5E], dil
0x140031ea7  call    cs:__imp_RtlAcquireSRWLockExclusive
0x140031ead  cmp     cs:WorldSid, rdi
0x140031eb4  jnz     short loc_140031EF5
0x140031eb6  mov     [rsp+100h+pSid], rsi; pSid
0x140031ebb  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140031ebf  mov     [rsp+100h+nSubAuthority7], edi; nSubAuthority7
0x140031ec3  xor     r9d, r9d; nSubAuthority1
0x140031ec6  mov     [rsp+100h+nSubAuthority6], edi; nSubAuthority6
0x140031eca  xor     r8d, r8d; nSubAuthority0
0x140031ecd  mov     [rsp+100h+nSubAuthority5], edi; nSubAuthority5
0x140031ed1  mov     dl, 1; nSubAuthorityCount
0x140031ed3  mov     [rsp+100h+nSubAuthority4], edi; nSubAuthority4
0x140031ed7  mov     [rsp+100h+nSubAuthority3], edi; nSubAuthority3
0x140031edb  mov     [rsp+100h+nSubAuthority2], edi; nSubAuthority2
0x140031edf  call    AllocateAndInitializeSid_0
0x140031ee4  test    eax, eax
0x140031ee6  jnz     short loc_140031EF5
0x140031ee8  call    cs:__imp_GetLastError
0x140031eee  mov     ebx, eax
0x140031ef0  jmp     loc_140031FE2
0x140031ef5  cmp     cs:LocalSystemSid, rdi
0x140031efc  jnz     short loc_140031F31
0x140031efe  mov     [rsp+100h+pSid], r14; pSid
0x140031f03  lea     rcx, [rbp+57h+var_48]; pIdentifierAuthority
0x140031f07  mov     [rsp+100h+nSubAuthority7], edi; nSubAuthority7
0x140031f0b  xor     r9d, r9d; nSubAuthority1
0x140031f0e  mov     [rsp+100h+nSubAuthority6], edi; nSubAuthority6
0x140031f12  mov     dl, 1; nSubAuthorityCount
0x140031f14  mov     [rsp+100h+nSubAuthority5], edi; nSubAuthority5
0x140031f18  mov     [rsp+100h+nSubAuthority4], edi; nSubAuthority4
0x140031f1c  mov     [rsp+100h+nSubAuthority3], edi; nSubAuthority3
0x140031f20  lea     r8d, [r9+12h]; nSubAuthority0
0x140031f24  mov     [rsp+100h+nSubAuthority2], edi; nSubAuthority2
0x140031f28  call    AllocateAndInitializeSid_0
0x140031f2d  test    eax, eax
0x140031f2f  jz      short loc_140031EE8
0x140031f31  cmp     cs:AnyPackageSid, rdi
0x140031f38  jnz     short loc_140031F75
0x140031f3a  mov     [rsp+100h+pSid], r15; pSid
0x140031f3f  lea     rcx, [rbp+57h+var_40]; pIdentifierAuthority
0x140031f43  mov     [rsp+100h+nSubAuthority7], edi; nSubAuthority7
0x140031f47  mov     r9d, 1; nSubAuthority1
0x140031f4d  mov     [rsp+100h+nSubAuthority6], edi; nSubAuthority6
0x140031f51  mov     [rsp+100h+nSubAuthority5], edi; nSubAuthority5
0x140031f55  mov     [rsp+100h+nSubAuthority4], edi; nSubAuthority4
0x140031f59  lea     r8d, [r9+1]; nSubAuthority0
0x140031f5d  mov     [rsp+100h+nSubAuthority3], edi; nSubAuthority3
0x140031f61  mov     dl, r8b; nSubAuthorityCount
0x140031f64  mov     [rsp+100h+nSubAuthority2], edi; nSubAuthority2
0x140031f68  call    AllocateAndInitializeSid_0
0x140031f6d  test    eax, eax
0x140031f6f  jz      loc_140031EE8
0x140031f75  cmp     cs:LpacServicesManagementCapabilitySid, rdi
0x140031f7c  jnz     short loc_140031FB4
0x140031f7e  lea     rsi, ?LpacServicesManagementCapabilitySidBuffer@@3PAEA; uchar near * LpacServicesManagementCapabilitySidBuffer
0x140031f85  mov     r8, rsi
0x140031f88  lea     rdx, ?LpacServicesManagementCapabilityGroupSidBuffer@@3PAEA; uchar near * LpacServicesManagementCapabilityGroupSidBuffer
0x140031f8f  lea     rcx, asc_1400988F0; ",."
0x140031f96  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x140031f9c  test    eax, eax
0x140031f9e  jns     short loc_140031FAD
0x140031fa0  mov     ecx, eax; Status
0x140031fa2  call    cs:__imp_RtlNtStatusToDosError
0x140031fa8  jmp     loc_140031EEE
0x140031fad  mov     cs:LpacServicesManagementCapabilitySid, rsi
0x140031fb4  mov     r8, cs:LocalSystemSid
0x140031fbb  lea     rax, [rbp+57h+var_A0]
0x140031fbf  mov     r9, r8
0x140031fc2  mov     qword ptr [rsp+100h+nSubAuthority2], rax
0x140031fc7  mov     edx, 4
0x140031fcc  lea     rcx, [rbp+57h+var_90]
0x140031fd0  call    ScCreateAndSetSD
0x140031fd5  test    eax, eax
0x140031fd7  js      short loc_140031FA0
0x140031fd9  mov     rax, [rbp+57h+var_A0]
0x140031fdd  mov     [rbx], rax
0x140031fe0  mov     ebx, edi
0x140031fe2  lea     rcx, qword_1400BC960
0x140031fe9  call    cs:__imp_RtlReleaseSRWLockExclusive
0x140031fef  mov     eax, ebx
0x140031ff1  mov     rcx, [rbp+57h+var_38]
0x140031ff5  xor     rcx, rsp; StackCookie
0x140031ff8  call    __security_check_cookie
0x140031ffd  add     rsp, 0D8h
0x140032004  pop     r15
0x140032006  pop     r14
0x140032008  pop     rdi
0x140032009  pop     rsi
0x14003200a  pop     rbx
0x14003200b  pop     rbp
0x14003200c  retn
```
