# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000f0b8`
- end: `0x18000f168`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000f170`

## callees

- `0x18000bf04`
- `0x18000f0b8`
- `0x18000f2a0`
- `0x18000f2f4`
- `0x18000f34c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f0f4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f0f4`

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
  wil::details_abi::FeatureStateData *v11; // [rsp+20h] [rbp-28h] BYREF

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
0x18000f0b8  mov     [rsp+arg_18], rbx
0x18000f0bd  push    rbp
0x18000f0be  push    rsi
0x18000f0bf  push    rdi
0x18000f0c0  sub     rsp, 30h
0x18000f0c4  mov     rbp, r9
0x18000f0c7  mov     ebx, r8d
0x18000f0ca  mov     esi, edx
0x18000f0cc  mov     rdi, rcx
0x18000f0cf  cmp     r8d, 0FEh
0x18000f0d6  jz      short loc_18000F153
0x18000f0d8  cmp     ebx, 0C8h
0x18000f0de  jb      short loc_18000F0F4
0x18000f0e0  cmp     ebx, 100h
0x18000f0e6  jl      short loc_18000F0F0
0x18000f0e8  cmp     ebx, 200h
0x18000f0ee  jb      short loc_18000F0F4
0x18000f0f0  xor     al, al
0x18000f0f2  jmp     short loc_18000F15A
0x18000f0f4  call    cs:__imp_AcquireSRWLockExclusive
0x18000f0fb  nop     dword ptr [rax+rax+00h]
0x18000f100  mov     [rsp+48h+var_28], rdi
0x18000f105  cmp     ebx, 7
0x18000f108  ja      short loc_18000F114
0x18000f10a  mov     eax, 0CCh
0x18000f10f  bt      eax, ebx
0x18000f112  jb      short loc_18000F134
0x18000f114  lea     eax, [rbx-100h]
0x18000f11a  cmp     eax, 7Fh
0x18000f11d  jbe     short loc_18000F134
0x18000f11f  mov     r9d, ebp
0x18000f122  lea     rcx, [rdi+48h]
0x18000f126  mov     r8d, esi
0x18000f129  mov     edx, ebx
0x18000f12b  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000f130  mov     bl, al
0x18000f132  jmp     short loc_18000F145
0x18000f134  mov     r8d, esi
0x18000f137  lea     rcx, [rdi+8]
0x18000f13b  mov     edx, ebx
0x18000f13d  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000f142  mov     bl, [rdi+40h]
0x18000f145  lea     rcx, [rsp+48h+var_28]
0x18000f14a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000f14f  mov     al, bl
0x18000f151  jmp     short loc_18000F15A
0x18000f153  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000f158  mov     al, 1
0x18000f15a  mov     rbx, [rsp+48h+arg_18]
0x18000f15f  add     rsp, 30h
0x18000f163  pop     rdi
0x18000f164  pop     rsi
0x18000f165  pop     rbp
0x18000f166  retn
```
