# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000fe54`
- end: `0x18000fef6`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000fefc`

## callees

- `0x18000cb5c`
- `0x18000fe54`
- `0x180010010`
- `0x180010044`
- `0x18001007c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fe8d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fe8d`

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
0x18000fe54  push    rbx
0x18000fe56  push    rbp
0x18000fe57  push    rsi
0x18000fe58  push    rdi
0x18000fe59  sub     rsp, 38h
0x18000fe5d  mov     rbp, r9
0x18000fe60  mov     ebx, r8d
0x18000fe63  mov     esi, edx
0x18000fe65  mov     rdi, rcx
0x18000fe68  cmp     r8d, 0FEh
0x18000fe6f  jz      short loc_18000FEE6
0x18000fe71  cmp     ebx, 0C8h
0x18000fe77  jb      short loc_18000FE8D
0x18000fe79  cmp     ebx, 100h
0x18000fe7f  jl      short loc_18000FE89
0x18000fe81  cmp     ebx, 200h
0x18000fe87  jb      short loc_18000FE8D
0x18000fe89  xor     al, al
0x18000fe8b  jmp     short loc_18000FEED
0x18000fe8d  call    cs:__imp_AcquireSRWLockExclusive
0x18000fe93  mov     [rsp+58h+var_38], rdi
0x18000fe98  cmp     ebx, 7
0x18000fe9b  ja      short loc_18000FEA7
0x18000fe9d  mov     eax, 0CCh
0x18000fea2  bt      eax, ebx
0x18000fea5  jb      short loc_18000FEC7
0x18000fea7  lea     eax, [rbx-100h]
0x18000fead  cmp     eax, 7Fh
0x18000feb0  jbe     short loc_18000FEC7
0x18000feb2  mov     r9d, ebp
0x18000feb5  lea     rcx, [rdi+48h]
0x18000feb9  mov     r8d, esi
0x18000febc  mov     edx, ebx
0x18000febe  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000fec3  mov     bl, al
0x18000fec5  jmp     short loc_18000FED8
0x18000fec7  mov     r8d, esi
0x18000feca  lea     rcx, [rdi+8]
0x18000fece  mov     edx, ebx
0x18000fed0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000fed5  mov     bl, [rdi+40h]
0x18000fed8  lea     rcx, [rsp+58h+var_38]
0x18000fedd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000fee2  mov     al, bl
0x18000fee4  jmp     short loc_18000FEED
0x18000fee6  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000feeb  mov     al, 1
0x18000feed  add     rsp, 38h
0x18000fef1  pop     rdi
0x18000fef2  pop     rsi
0x18000fef3  pop     rbp
0x18000fef4  pop     rbx
0x18000fef5  retn
```
