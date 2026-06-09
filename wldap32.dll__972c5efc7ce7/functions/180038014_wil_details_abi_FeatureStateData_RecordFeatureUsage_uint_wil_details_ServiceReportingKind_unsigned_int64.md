# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180038014`
- end: `0x1800380bd`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18003322c`

## callees

- `0x180031a10`
- `0x180038014`
- `0x180038104`
- `0x18003813c`
- `0x180038174`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003804d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003804d`

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
0x180038014  push    rbx
0x180038016  push    rbp
0x180038017  push    rsi
0x180038018  push    rdi
0x180038019  sub     rsp, 38h
0x18003801d  mov     rbp, r9
0x180038020  mov     ebx, r8d
0x180038023  mov     esi, edx
0x180038025  mov     rdi, rcx
0x180038028  cmp     r8d, 0FEh
0x18003802f  jz      short loc_1800380AC
0x180038031  cmp     ebx, 0C8h
0x180038037  jb      short loc_18003804D
0x180038039  cmp     ebx, 100h
0x18003803f  jl      short loc_180038049
0x180038041  cmp     ebx, 200h
0x180038047  jb      short loc_18003804D
0x180038049  xor     al, al
0x18003804b  jmp     short loc_1800380B3
0x18003804d  call    cs:__imp_AcquireSRWLockExclusive
0x180038054  nop     dword ptr [rax+rax+00h]
0x180038059  mov     [rsp+58h+var_38], rdi
0x18003805e  cmp     ebx, 7
0x180038061  ja      short loc_18003806D
0x180038063  mov     eax, 0CCh
0x180038068  bt      eax, ebx
0x18003806b  jb      short loc_18003808D
0x18003806d  lea     eax, [rbx-100h]
0x180038073  cmp     eax, 7Fh
0x180038076  jbe     short loc_18003808D
0x180038078  mov     r9d, ebp
0x18003807b  lea     rcx, [rdi+48h]
0x18003807f  mov     r8d, esi
0x180038082  mov     edx, ebx
0x180038084  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180038089  mov     bl, al
0x18003808b  jmp     short loc_18003809E
0x18003808d  mov     r8d, esi
0x180038090  lea     rcx, [rdi+8]
0x180038094  mov     edx, ebx
0x180038096  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18003809b  mov     bl, [rdi+40h]
0x18003809e  lea     rcx, [rsp+58h+var_38]
0x1800380a3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800380a8  mov     al, bl
0x1800380aa  jmp     short loc_1800380B3
0x1800380ac  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800380b1  mov     al, 1
0x1800380b3  add     rsp, 38h
0x1800380b7  pop     rdi
0x1800380b8  pop     rsi
0x1800380b9  pop     rbp
0x1800380ba  pop     rbx
0x1800380bb  retn
```
