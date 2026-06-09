# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18002b11c`
- end: `0x18002b1be`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18001f4c4`

## callees

- `0x18001f5f0`
- `0x18002b11c`
- `0x18002b1e0`
- `0x18002b214`
- `0x18002b24c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b155`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b155`

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
0x18002b11c  push    rbx
0x18002b11e  push    rbp
0x18002b11f  push    rsi
0x18002b120  push    rdi
0x18002b121  sub     rsp, 38h
0x18002b125  mov     rbp, r9
0x18002b128  mov     ebx, r8d
0x18002b12b  mov     esi, edx
0x18002b12d  mov     rdi, rcx
0x18002b130  cmp     r8d, 0FEh
0x18002b137  jz      short loc_18002B1AE
0x18002b139  cmp     ebx, 0C8h
0x18002b13f  jb      short loc_18002B155
0x18002b141  cmp     ebx, 100h
0x18002b147  jl      short loc_18002B151
0x18002b149  cmp     ebx, 200h
0x18002b14f  jb      short loc_18002B155
0x18002b151  xor     al, al
0x18002b153  jmp     short loc_18002B1B5
0x18002b155  call    cs:__imp_AcquireSRWLockExclusive
0x18002b15b  mov     [rsp+58h+var_38], rdi
0x18002b160  cmp     ebx, 7
0x18002b163  ja      short loc_18002B16F
0x18002b165  mov     eax, 0CCh
0x18002b16a  bt      eax, ebx
0x18002b16d  jb      short loc_18002B18F
0x18002b16f  lea     eax, [rbx-100h]
0x18002b175  cmp     eax, 7Fh
0x18002b178  jbe     short loc_18002B18F
0x18002b17a  mov     r9d, ebp
0x18002b17d  lea     rcx, [rdi+48h]
0x18002b181  mov     r8d, esi
0x18002b184  mov     edx, ebx
0x18002b186  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18002b18b  mov     bl, al
0x18002b18d  jmp     short loc_18002B1A0
0x18002b18f  mov     r8d, esi
0x18002b192  lea     rcx, [rdi+8]
0x18002b196  mov     edx, ebx
0x18002b198  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18002b19d  mov     bl, [rdi+40h]
0x18002b1a0  lea     rcx, [rsp+58h+var_38]
0x18002b1a5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002b1aa  mov     al, bl
0x18002b1ac  jmp     short loc_18002B1B5
0x18002b1ae  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18002b1b3  mov     al, 1
0x18002b1b5  add     rsp, 38h
0x18002b1b9  pop     rdi
0x18002b1ba  pop     rsi
0x18002b1bb  pop     rbp
0x18002b1bc  pop     rbx
0x18002b1bd  retn
```
