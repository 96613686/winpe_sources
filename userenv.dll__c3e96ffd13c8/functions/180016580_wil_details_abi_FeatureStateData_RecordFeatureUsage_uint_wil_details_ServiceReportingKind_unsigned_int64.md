# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180016580`
- end: `0x180016622`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180016628`

## callees

- `0x18000d158`
- `0x180016580`
- `0x180016700`
- `0x180016734`
- `0x18001676c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800165b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800165b9`

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
  RTL_SRWLOCK *v11; // [rsp+20h] [rbp-38h] BYREF

  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(a1);
    return 1;
  }
  else if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1);
    v11 = (RTL_SRWLOCK *)a1;
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
0x180016580  push    rbx
0x180016582  push    rbp
0x180016583  push    rsi
0x180016584  push    rdi
0x180016585  sub     rsp, 38h
0x180016589  mov     rbp, r9
0x18001658c  mov     ebx, r8d
0x18001658f  mov     esi, edx
0x180016591  mov     rdi, rcx
0x180016594  cmp     r8d, 0FEh
0x18001659b  jz      short loc_180016612
0x18001659d  cmp     ebx, 0C8h
0x1800165a3  jb      short loc_1800165B9
0x1800165a5  cmp     ebx, 100h
0x1800165ab  jl      short loc_1800165B5
0x1800165ad  cmp     ebx, 200h
0x1800165b3  jb      short loc_1800165B9
0x1800165b5  xor     al, al
0x1800165b7  jmp     short loc_180016619
0x1800165b9  call    cs:__imp_AcquireSRWLockExclusive
0x1800165bf  mov     [rsp+58h+var_38], rdi
0x1800165c4  cmp     ebx, 7
0x1800165c7  ja      short loc_1800165D3
0x1800165c9  mov     eax, 0CCh
0x1800165ce  bt      eax, ebx
0x1800165d1  jb      short loc_1800165F3
0x1800165d3  lea     eax, [rbx-100h]
0x1800165d9  cmp     eax, 7Fh
0x1800165dc  jbe     short loc_1800165F3
0x1800165de  mov     r9d, ebp
0x1800165e1  lea     rcx, [rdi+48h]
0x1800165e5  mov     r8d, esi
0x1800165e8  mov     edx, ebx
0x1800165ea  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800165ef  mov     bl, al
0x1800165f1  jmp     short loc_180016604
0x1800165f3  mov     r8d, esi
0x1800165f6  lea     rcx, [rdi+8]
0x1800165fa  mov     edx, ebx
0x1800165fc  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180016601  mov     bl, [rdi+40h]
0x180016604  lea     rcx, [rsp+58h+var_38]
0x180016609  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001660e  mov     al, bl
0x180016610  jmp     short loc_180016619
0x180016612  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180016617  mov     al, 1
0x180016619  add     rsp, 38h
0x18001661d  pop     rdi
0x18001661e  pop     rsi
0x18001661f  pop     rbp
0x180016620  pop     rbx
0x180016621  retn
```
