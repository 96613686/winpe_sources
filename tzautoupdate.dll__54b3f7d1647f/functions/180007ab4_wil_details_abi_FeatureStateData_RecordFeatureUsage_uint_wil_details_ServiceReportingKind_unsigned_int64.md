# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180007ab4`
- end: `0x180007b56`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180007b5c`

## callees

- `0x180004614`
- `0x180007ab4`
- `0x180007c70`
- `0x180007ca4`
- `0x180007cdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007aed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007aed`

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
0x180007ab4  push    rbx
0x180007ab6  push    rbp
0x180007ab7  push    rsi
0x180007ab8  push    rdi
0x180007ab9  sub     rsp, 38h
0x180007abd  mov     rbp, r9
0x180007ac0  mov     ebx, r8d
0x180007ac3  mov     esi, edx
0x180007ac5  mov     rdi, rcx
0x180007ac8  cmp     r8d, 0FEh
0x180007acf  jz      short loc_180007B46
0x180007ad1  cmp     ebx, 0C8h
0x180007ad7  jb      short loc_180007AED
0x180007ad9  cmp     ebx, 100h
0x180007adf  jl      short loc_180007AE9
0x180007ae1  cmp     ebx, 200h
0x180007ae7  jb      short loc_180007AED
0x180007ae9  xor     al, al
0x180007aeb  jmp     short loc_180007B4D
0x180007aed  call    cs:__imp_AcquireSRWLockExclusive
0x180007af3  mov     [rsp+58h+var_38], rdi
0x180007af8  cmp     ebx, 7
0x180007afb  ja      short loc_180007B07
0x180007afd  mov     eax, 0CCh
0x180007b02  bt      eax, ebx
0x180007b05  jb      short loc_180007B27
0x180007b07  lea     eax, [rbx-100h]
0x180007b0d  cmp     eax, 7Fh
0x180007b10  jbe     short loc_180007B27
0x180007b12  mov     r9d, ebp
0x180007b15  lea     rcx, [rdi+48h]
0x180007b19  mov     r8d, esi
0x180007b1c  mov     edx, ebx
0x180007b1e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007b23  mov     bl, al
0x180007b25  jmp     short loc_180007B38
0x180007b27  mov     r8d, esi
0x180007b2a  lea     rcx, [rdi+8]
0x180007b2e  mov     edx, ebx
0x180007b30  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007b35  mov     bl, [rdi+40h]
0x180007b38  lea     rcx, [rsp+58h+var_38]
0x180007b3d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180007b42  mov     al, bl
0x180007b44  jmp     short loc_180007B4D
0x180007b46  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180007b4b  mov     al, 1
0x180007b4d  add     rsp, 38h
0x180007b51  pop     rdi
0x180007b52  pop     rsi
0x180007b53  pop     rbp
0x180007b54  pop     rbx
0x180007b55  retn
```
