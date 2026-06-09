# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800102e4`
- end: `0x180010386`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18001038c`

## callees

- `0x18000d8f4`
- `0x1800102e4`
- `0x18001048c`
- `0x1800104c0`
- `0x1800104f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001031d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001031d`

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
0x1800102e4  push    rbx
0x1800102e6  push    rbp
0x1800102e7  push    rsi
0x1800102e8  push    rdi
0x1800102e9  sub     rsp, 38h
0x1800102ed  mov     rbp, r9
0x1800102f0  mov     ebx, r8d
0x1800102f3  mov     esi, edx
0x1800102f5  mov     rdi, rcx
0x1800102f8  cmp     r8d, 0FEh
0x1800102ff  jz      short loc_180010376
0x180010301  cmp     ebx, 0C8h
0x180010307  jb      short loc_18001031D
0x180010309  cmp     ebx, 100h
0x18001030f  jl      short loc_180010319
0x180010311  cmp     ebx, 200h
0x180010317  jb      short loc_18001031D
0x180010319  xor     al, al
0x18001031b  jmp     short loc_18001037D
0x18001031d  call    cs:__imp_AcquireSRWLockExclusive
0x180010323  mov     [rsp+58h+var_38], rdi
0x180010328  cmp     ebx, 7
0x18001032b  ja      short loc_180010337
0x18001032d  mov     eax, 0CCh
0x180010332  bt      eax, ebx
0x180010335  jb      short loc_180010357
0x180010337  lea     eax, [rbx-100h]
0x18001033d  cmp     eax, 7Fh
0x180010340  jbe     short loc_180010357
0x180010342  mov     r9d, ebp
0x180010345  lea     rcx, [rdi+48h]
0x180010349  mov     r8d, esi
0x18001034c  mov     edx, ebx
0x18001034e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180010353  mov     bl, al
0x180010355  jmp     short loc_180010368
0x180010357  mov     r8d, esi
0x18001035a  lea     rcx, [rdi+8]
0x18001035e  mov     edx, ebx
0x180010360  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180010365  mov     bl, [rdi+40h]
0x180010368  lea     rcx, [rsp+58h+var_38]
0x18001036d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180010372  mov     al, bl
0x180010374  jmp     short loc_18001037D
0x180010376  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18001037b  mov     al, 1
0x18001037d  add     rsp, 38h
0x180010381  pop     rdi
0x180010382  pop     rsi
0x180010383  pop     rbp
0x180010384  pop     rbx
0x180010385  retn
```
