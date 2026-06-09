# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000bb5c`
- end: `0x18000bbfe`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180006f24`

## callees

- `0x180007050`
- `0x18000bb5c`
- `0x18000bc04`
- `0x18000bc38`
- `0x18000bc70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bb95`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bb95`

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
0x18000bb5c  push    rbx
0x18000bb5e  push    rbp
0x18000bb5f  push    rsi
0x18000bb60  push    rdi
0x18000bb61  sub     rsp, 38h
0x18000bb65  mov     rbp, r9
0x18000bb68  mov     ebx, r8d
0x18000bb6b  mov     esi, edx
0x18000bb6d  mov     rdi, rcx
0x18000bb70  cmp     r8d, 0FEh
0x18000bb77  jz      short loc_18000BBEE
0x18000bb79  cmp     ebx, 0C8h
0x18000bb7f  jb      short loc_18000BB95
0x18000bb81  cmp     ebx, 100h
0x18000bb87  jl      short loc_18000BB91
0x18000bb89  cmp     ebx, 200h
0x18000bb8f  jb      short loc_18000BB95
0x18000bb91  xor     al, al
0x18000bb93  jmp     short loc_18000BBF5
0x18000bb95  call    cs:__imp_AcquireSRWLockExclusive
0x18000bb9b  mov     [rsp+58h+var_38], rdi
0x18000bba0  cmp     ebx, 7
0x18000bba3  ja      short loc_18000BBAF
0x18000bba5  mov     eax, 0CCh
0x18000bbaa  bt      eax, ebx
0x18000bbad  jb      short loc_18000BBCF
0x18000bbaf  lea     eax, [rbx-100h]
0x18000bbb5  cmp     eax, 7Fh
0x18000bbb8  jbe     short loc_18000BBCF
0x18000bbba  mov     r9d, ebp
0x18000bbbd  lea     rcx, [rdi+48h]
0x18000bbc1  mov     r8d, esi
0x18000bbc4  mov     edx, ebx
0x18000bbc6  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000bbcb  mov     bl, al
0x18000bbcd  jmp     short loc_18000BBE0
0x18000bbcf  mov     r8d, esi
0x18000bbd2  lea     rcx, [rdi+8]
0x18000bbd6  mov     edx, ebx
0x18000bbd8  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000bbdd  mov     bl, [rdi+40h]
0x18000bbe0  lea     rcx, [rsp+58h+var_38]
0x18000bbe5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000bbea  mov     al, bl
0x18000bbec  jmp     short loc_18000BBF5
0x18000bbee  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000bbf3  mov     al, 1
0x18000bbf5  add     rsp, 38h
0x18000bbf9  pop     rdi
0x18000bbfa  pop     rsi
0x18000bbfb  pop     rbp
0x18000bbfc  pop     rbx
0x18000bbfd  retn
```
