# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18001f038`
- end: `0x18001f0da`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180010904`

## callees

- `0x180010a10`
- `0x18001f038`
- `0x18001f118`
- `0x18001f14c`
- `0x18001f184`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f071`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f071`

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
0x18001f038  push    rbx
0x18001f03a  push    rbp
0x18001f03b  push    rsi
0x18001f03c  push    rdi
0x18001f03d  sub     rsp, 38h
0x18001f041  mov     rbp, r9
0x18001f044  mov     ebx, r8d
0x18001f047  mov     esi, edx
0x18001f049  mov     rdi, rcx
0x18001f04c  cmp     r8d, 0FEh
0x18001f053  jz      short loc_18001F0CA
0x18001f055  cmp     ebx, 0C8h
0x18001f05b  jb      short loc_18001F071
0x18001f05d  cmp     ebx, 100h
0x18001f063  jl      short loc_18001F06D
0x18001f065  cmp     ebx, 200h
0x18001f06b  jb      short loc_18001F071
0x18001f06d  xor     al, al
0x18001f06f  jmp     short loc_18001F0D1
0x18001f071  call    cs:__imp_AcquireSRWLockExclusive
0x18001f077  mov     [rsp+58h+var_38], rdi
0x18001f07c  cmp     ebx, 7
0x18001f07f  ja      short loc_18001F08B
0x18001f081  mov     eax, 0CCh
0x18001f086  bt      eax, ebx
0x18001f089  jb      short loc_18001F0AB
0x18001f08b  lea     eax, [rbx-100h]
0x18001f091  cmp     eax, 7Fh
0x18001f094  jbe     short loc_18001F0AB
0x18001f096  mov     r9d, ebp
0x18001f099  lea     rcx, [rdi+48h]
0x18001f09d  mov     r8d, esi
0x18001f0a0  mov     edx, ebx
0x18001f0a2  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18001f0a7  mov     bl, al
0x18001f0a9  jmp     short loc_18001F0BC
0x18001f0ab  mov     r8d, esi
0x18001f0ae  lea     rcx, [rdi+8]
0x18001f0b2  mov     edx, ebx
0x18001f0b4  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18001f0b9  mov     bl, [rdi+40h]
0x18001f0bc  lea     rcx, [rsp+58h+var_38]
0x18001f0c1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001f0c6  mov     al, bl
0x18001f0c8  jmp     short loc_18001F0D1
0x18001f0ca  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18001f0cf  mov     al, 1
0x18001f0d1  add     rsp, 38h
0x18001f0d5  pop     rdi
0x18001f0d6  pop     rsi
0x18001f0d7  pop     rbp
0x18001f0d8  pop     rbx
0x18001f0d9  retn
```
