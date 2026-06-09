# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18003a064`
- end: `0x18003a106`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18003a10c`

## callees

- `0x180036294`
- `0x18003a064`
- `0x18003a20c`
- `0x18003a240`
- `0x18003a278`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18003a09d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18003a09d`

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
0x18003a064  push    rbx
0x18003a066  push    rbp
0x18003a067  push    rsi
0x18003a068  push    rdi
0x18003a069  sub     rsp, 38h
0x18003a06d  mov     rbp, r9
0x18003a070  mov     ebx, r8d
0x18003a073  mov     esi, edx
0x18003a075  mov     rdi, rcx
0x18003a078  cmp     r8d, 0FEh
0x18003a07f  jz      short loc_18003A0F6
0x18003a081  cmp     ebx, 0C8h
0x18003a087  jb      short loc_18003A09D
0x18003a089  cmp     ebx, 100h
0x18003a08f  jl      short loc_18003A099
0x18003a091  cmp     ebx, 200h
0x18003a097  jb      short loc_18003A09D
0x18003a099  xor     al, al
0x18003a09b  jmp     short loc_18003A0FD
0x18003a09d  call    cs:__imp_AcquireSRWLockExclusive
0x18003a0a3  mov     [rsp+58h+var_38], rdi
0x18003a0a8  cmp     ebx, 7
0x18003a0ab  ja      short loc_18003A0B7
0x18003a0ad  mov     eax, 0CCh
0x18003a0b2  bt      eax, ebx
0x18003a0b5  jb      short loc_18003A0D7
0x18003a0b7  lea     eax, [rbx-100h]
0x18003a0bd  cmp     eax, 7Fh
0x18003a0c0  jbe     short loc_18003A0D7
0x18003a0c2  mov     r9d, ebp
0x18003a0c5  lea     rcx, [rdi+48h]
0x18003a0c9  mov     r8d, esi
0x18003a0cc  mov     edx, ebx
0x18003a0ce  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18003a0d3  mov     bl, al
0x18003a0d5  jmp     short loc_18003A0E8
0x18003a0d7  mov     r8d, esi
0x18003a0da  lea     rcx, [rdi+8]
0x18003a0de  mov     edx, ebx
0x18003a0e0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18003a0e5  mov     bl, [rdi+40h]
0x18003a0e8  lea     rcx, [rsp+58h+var_38]
0x18003a0ed  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003a0f2  mov     al, bl
0x18003a0f4  jmp     short loc_18003A0FD
0x18003a0f6  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18003a0fb  mov     al, 1
0x18003a0fd  add     rsp, 38h
0x18003a101  pop     rdi
0x18003a102  pop     rsi
0x18003a103  pop     rbp
0x18003a104  pop     rbx
0x18003a105  retn
```
