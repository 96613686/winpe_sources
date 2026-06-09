# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180017e18`
- end: `0x180017ec1`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180017ec8`

## callees

- `0x18000ddcc`
- `0x180017e18`
- `0x180017fc0`
- `0x180017ff8`
- `0x180018030`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017e51`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017e51`

## pseudocode

```c
char __fastcall wil::details_abi::FeatureStateData::RecordFeatureUsage(
        wil::details_abi::FeatureStateData *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  int v9; // eax
  char v10; // bl
  wil::details_abi::FeatureStateData *v11; // [rsp+20h] [rbp-38h] BYREF

  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(a1);
    return 1;
  }
  else if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1);
    v11 = a1;
    if ( a3 <= 7 && (v9 = 204, _bittest(&v9, a3)) || a3 - 256 <= 0x7F )
    {
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(
        (char *)a1 + 8,
        a3,
        a2);
      v10 = *((_BYTE *)a1 + 64);
    }
    else
    {
      v10 = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              (char *)a1 + 72,
              a3,
              a2,
              a4,
              v11);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
    return v10;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180017e18  push    rbx
0x180017e1a  push    rbp
0x180017e1b  push    rsi
0x180017e1c  push    rdi
0x180017e1d  sub     rsp, 38h
0x180017e21  mov     rbp, r9
0x180017e24  mov     ebx, r8d
0x180017e27  mov     esi, edx
0x180017e29  mov     rdi, rcx
0x180017e2c  cmp     r8d, 0FEh
0x180017e33  jz      short loc_180017EB0
0x180017e35  cmp     ebx, 0C8h
0x180017e3b  jb      short loc_180017E51
0x180017e3d  cmp     ebx, 100h
0x180017e43  jl      short loc_180017E4D
0x180017e45  cmp     ebx, 200h
0x180017e4b  jb      short loc_180017E51
0x180017e4d  xor     al, al
0x180017e4f  jmp     short loc_180017EB7
0x180017e51  call    cs:__imp_AcquireSRWLockExclusive
0x180017e58  nop     dword ptr [rax+rax+00h]
0x180017e5d  mov     [rsp+58h+var_38], rdi
0x180017e62  cmp     ebx, 7
0x180017e65  ja      short loc_180017E71
0x180017e67  mov     eax, 0CCh
0x180017e6c  bt      eax, ebx
0x180017e6f  jb      short loc_180017E91
0x180017e71  lea     eax, [rbx-100h]
0x180017e77  cmp     eax, 7Fh
0x180017e7a  jbe     short loc_180017E91
0x180017e7c  mov     r9d, ebp
0x180017e7f  lea     rcx, [rdi+48h]
0x180017e83  mov     r8d, esi
0x180017e86  mov     edx, ebx
0x180017e88  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180017e8d  mov     bl, al
0x180017e8f  jmp     short loc_180017EA2
0x180017e91  mov     r8d, esi
0x180017e94  lea     rcx, [rdi+8]
0x180017e98  mov     edx, ebx
0x180017e9a  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180017e9f  mov     bl, [rdi+40h]
0x180017ea2  lea     rcx, [rsp+58h+var_38]
0x180017ea7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180017eac  mov     al, bl
0x180017eae  jmp     short loc_180017EB7
0x180017eb0  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180017eb5  mov     al, 1
0x180017eb7  add     rsp, 38h
0x180017ebb  pop     rdi
0x180017ebc  pop     rsi
0x180017ebd  pop     rbp
0x180017ebe  pop     rbx
0x180017ebf  retn
```
