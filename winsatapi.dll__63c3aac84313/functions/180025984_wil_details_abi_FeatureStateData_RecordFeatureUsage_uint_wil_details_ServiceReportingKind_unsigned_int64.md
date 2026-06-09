# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180025984`
- end: `0x180025a2f`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180025a38`

## callees

- `0x1800126f0`
- `0x180025984`
- `0x180025af8`
- `0x180025b2c`
- `0x180025b64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800259c6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800259c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall wil::details_abi::FeatureStateData::RecordFeatureUsage(
        wil::details_abi::FeatureStateData *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  int v9; // eax
  char v10; // bl
  RTL_SRWLOCK *v11; // [rsp+20h] [rbp-38h] BYREF
  __int64 v12; // [rsp+28h] [rbp-30h]

  v12 = -2;
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
              v11,
              v12);
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
0x180025984  push    rbx
0x180025986  push    rbp
0x180025987  push    rsi
0x180025988  push    rdi
0x180025989  sub     rsp, 38h
0x18002598d  mov     [rsp+58h+var_30], 0FFFFFFFFFFFFFFFEh
0x180025996  mov     rbp, r9
0x180025999  mov     ebx, r8d
0x18002599c  mov     esi, edx
0x18002599e  mov     rdi, rcx
0x1800259a1  cmp     r8d, 0FEh
0x1800259a8  jz      short loc_180025A1F
0x1800259aa  cmp     ebx, 0C8h
0x1800259b0  jb      short loc_1800259C6
0x1800259b2  cmp     ebx, 100h
0x1800259b8  jl      short loc_1800259C2
0x1800259ba  cmp     ebx, 200h
0x1800259c0  jb      short loc_1800259C6
0x1800259c2  xor     al, al
0x1800259c4  jmp     short loc_180025A26
0x1800259c6  call    cs:__imp_AcquireSRWLockExclusive
0x1800259cc  mov     [rsp+58h+var_38], rdi
0x1800259d1  cmp     ebx, 7
0x1800259d4  ja      short loc_1800259E0
0x1800259d6  mov     eax, 0CCh
0x1800259db  bt      eax, ebx
0x1800259de  jb      short loc_180025A00
0x1800259e0  lea     eax, [rbx-100h]
0x1800259e6  cmp     eax, 7Fh
0x1800259e9  jbe     short loc_180025A00
0x1800259eb  mov     r9d, ebp
0x1800259ee  lea     rcx, [rdi+48h]
0x1800259f2  mov     r8d, esi
0x1800259f5  mov     edx, ebx
0x1800259f7  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800259fc  mov     bl, al
0x1800259fe  jmp     short loc_180025A11
0x180025a00  mov     r8d, esi
0x180025a03  mov     edx, ebx
0x180025a05  lea     rcx, [rdi+8]
0x180025a09  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180025a0e  mov     bl, [rdi+40h]
0x180025a11  lea     rcx, [rsp+58h+var_38]
0x180025a16  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180025a1b  mov     al, bl
0x180025a1d  jmp     short loc_180025A26
0x180025a1f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180025a24  mov     al, 1
0x180025a26  add     rsp, 38h
0x180025a2a  pop     rdi
0x180025a2b  pop     rsi
0x180025a2c  pop     rbp
0x180025a2d  pop     rbx
0x180025a2e  retn
```
