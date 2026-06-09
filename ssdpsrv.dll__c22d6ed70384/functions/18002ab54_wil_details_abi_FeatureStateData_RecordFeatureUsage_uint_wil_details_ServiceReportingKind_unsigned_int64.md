# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18002ab54`
- end: `0x18002abf6`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180022f0c`

## callees

- `0x1800232a8`
- `0x18002ab54`
- `0x18002ad40`
- `0x18002ad74`
- `0x18002adac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ab8d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ab8d`

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
0x18002ab54  push    rbx
0x18002ab56  push    rbp
0x18002ab57  push    rsi
0x18002ab58  push    rdi
0x18002ab59  sub     rsp, 38h
0x18002ab5d  mov     rbp, r9
0x18002ab60  mov     ebx, r8d
0x18002ab63  mov     esi, edx
0x18002ab65  mov     rdi, rcx
0x18002ab68  cmp     r8d, 0FEh
0x18002ab6f  jz      short loc_18002ABE6
0x18002ab71  cmp     ebx, 0C8h
0x18002ab77  jb      short loc_18002AB8D
0x18002ab79  cmp     ebx, 100h
0x18002ab7f  jl      short loc_18002AB89
0x18002ab81  cmp     ebx, 200h
0x18002ab87  jb      short loc_18002AB8D
0x18002ab89  xor     al, al
0x18002ab8b  jmp     short loc_18002ABED
0x18002ab8d  call    cs:__imp_AcquireSRWLockExclusive
0x18002ab93  mov     [rsp+58h+var_38], rdi
0x18002ab98  cmp     ebx, 7
0x18002ab9b  ja      short loc_18002ABA7
0x18002ab9d  mov     eax, 0CCh
0x18002aba2  bt      eax, ebx
0x18002aba5  jb      short loc_18002ABC7
0x18002aba7  lea     eax, [rbx-100h]
0x18002abad  cmp     eax, 7Fh
0x18002abb0  jbe     short loc_18002ABC7
0x18002abb2  mov     r9d, ebp
0x18002abb5  lea     rcx, [rdi+48h]
0x18002abb9  mov     r8d, esi
0x18002abbc  mov     edx, ebx
0x18002abbe  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18002abc3  mov     bl, al
0x18002abc5  jmp     short loc_18002ABD8
0x18002abc7  mov     r8d, esi
0x18002abca  lea     rcx, [rdi+8]
0x18002abce  mov     edx, ebx
0x18002abd0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18002abd5  mov     bl, [rdi+40h]
0x18002abd8  lea     rcx, [rsp+58h+var_38]
0x18002abdd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002abe2  mov     al, bl
0x18002abe4  jmp     short loc_18002ABED
0x18002abe6  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18002abeb  mov     al, 1
0x18002abed  add     rsp, 38h
0x18002abf1  pop     rdi
0x18002abf2  pop     rsi
0x18002abf3  pop     rbp
0x18002abf4  pop     rbx
0x18002abf5  retn
```
