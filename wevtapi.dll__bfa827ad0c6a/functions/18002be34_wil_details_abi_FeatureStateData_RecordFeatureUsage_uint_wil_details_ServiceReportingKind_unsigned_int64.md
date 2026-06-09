# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18002be34`
- end: `0x18002bed6`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800204d0`

## callees

- `0x1800205fc`
- `0x18002be34`
- `0x18002bf30`
- `0x18002bf64`
- `0x18002bf9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002be6d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002be6d`

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
0x18002be34  push    rbx
0x18002be36  push    rbp
0x18002be37  push    rsi
0x18002be38  push    rdi
0x18002be39  sub     rsp, 38h
0x18002be3d  mov     rbp, r9
0x18002be40  mov     ebx, r8d
0x18002be43  mov     esi, edx
0x18002be45  mov     rdi, rcx
0x18002be48  cmp     r8d, 0FEh
0x18002be4f  jz      short loc_18002BEC6
0x18002be51  cmp     ebx, 0C8h
0x18002be57  jb      short loc_18002BE6D
0x18002be59  cmp     ebx, 100h
0x18002be5f  jl      short loc_18002BE69
0x18002be61  cmp     ebx, 200h
0x18002be67  jb      short loc_18002BE6D
0x18002be69  xor     al, al
0x18002be6b  jmp     short loc_18002BECD
0x18002be6d  call    cs:__imp_AcquireSRWLockExclusive
0x18002be73  mov     [rsp+58h+var_38], rdi
0x18002be78  cmp     ebx, 7
0x18002be7b  ja      short loc_18002BE87
0x18002be7d  mov     eax, 0CCh
0x18002be82  bt      eax, ebx
0x18002be85  jb      short loc_18002BEA7
0x18002be87  lea     eax, [rbx-100h]
0x18002be8d  cmp     eax, 7Fh
0x18002be90  jbe     short loc_18002BEA7
0x18002be92  mov     r9d, ebp
0x18002be95  lea     rcx, [rdi+48h]
0x18002be99  mov     r8d, esi
0x18002be9c  mov     edx, ebx
0x18002be9e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18002bea3  mov     bl, al
0x18002bea5  jmp     short loc_18002BEB8
0x18002bea7  mov     r8d, esi
0x18002beaa  lea     rcx, [rdi+8]
0x18002beae  mov     edx, ebx
0x18002beb0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18002beb5  mov     bl, [rdi+40h]
0x18002beb8  lea     rcx, [rsp+58h+var_38]
0x18002bebd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002bec2  mov     al, bl
0x18002bec4  jmp     short loc_18002BECD
0x18002bec6  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18002becb  mov     al, 1
0x18002becd  add     rsp, 38h
0x18002bed1  pop     rdi
0x18002bed2  pop     rsi
0x18002bed3  pop     rbp
0x18002bed4  pop     rbx
0x18002bed5  retn
```
