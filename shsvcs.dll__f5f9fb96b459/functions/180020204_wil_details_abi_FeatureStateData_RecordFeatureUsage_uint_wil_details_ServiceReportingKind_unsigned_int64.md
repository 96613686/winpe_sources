# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180020204`
- end: `0x1800202a6`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800202ac`

## callees

- `0x18001d654`
- `0x180020204`
- `0x1800203c0`
- `0x1800203f4`
- `0x18002042c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002023d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002023d`

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
0x180020204  push    rbx
0x180020206  push    rbp
0x180020207  push    rsi
0x180020208  push    rdi
0x180020209  sub     rsp, 38h
0x18002020d  mov     rbp, r9
0x180020210  mov     ebx, r8d
0x180020213  mov     esi, edx
0x180020215  mov     rdi, rcx
0x180020218  cmp     r8d, 0FEh
0x18002021f  jz      short loc_180020296
0x180020221  cmp     ebx, 0C8h
0x180020227  jb      short loc_18002023D
0x180020229  cmp     ebx, 100h
0x18002022f  jl      short loc_180020239
0x180020231  cmp     ebx, 200h
0x180020237  jb      short loc_18002023D
0x180020239  xor     al, al
0x18002023b  jmp     short loc_18002029D
0x18002023d  call    cs:__imp_AcquireSRWLockExclusive
0x180020243  mov     [rsp+58h+var_38], rdi
0x180020248  cmp     ebx, 7
0x18002024b  ja      short loc_180020257
0x18002024d  mov     eax, 0CCh
0x180020252  bt      eax, ebx
0x180020255  jb      short loc_180020277
0x180020257  lea     eax, [rbx-100h]
0x18002025d  cmp     eax, 7Fh
0x180020260  jbe     short loc_180020277
0x180020262  mov     r9d, ebp
0x180020265  lea     rcx, [rdi+48h]
0x180020269  mov     r8d, esi
0x18002026c  mov     edx, ebx
0x18002026e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180020273  mov     bl, al
0x180020275  jmp     short loc_180020288
0x180020277  mov     r8d, esi
0x18002027a  lea     rcx, [rdi+8]
0x18002027e  mov     edx, ebx
0x180020280  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180020285  mov     bl, [rdi+40h]
0x180020288  lea     rcx, [rsp+58h+var_38]
0x18002028d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180020292  mov     al, bl
0x180020294  jmp     short loc_18002029D
0x180020296  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18002029b  mov     al, 1
0x18002029d  add     rsp, 38h
0x1800202a1  pop     rdi
0x1800202a2  pop     rsi
0x1800202a3  pop     rbp
0x1800202a4  pop     rbx
0x1800202a5  retn
```
