# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000a434`
- end: `0x18000a4d6`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000a4dc`

## callees

- `0x180007b44`
- `0x18000a434`
- `0x18000a5f0`
- `0x18000a624`
- `0x18000a65c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a46d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a46d`

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
0x18000a434  push    rbx
0x18000a436  push    rbp
0x18000a437  push    rsi
0x18000a438  push    rdi
0x18000a439  sub     rsp, 38h
0x18000a43d  mov     rbp, r9
0x18000a440  mov     ebx, r8d
0x18000a443  mov     esi, edx
0x18000a445  mov     rdi, rcx
0x18000a448  cmp     r8d, 0FEh
0x18000a44f  jz      short loc_18000A4C6
0x18000a451  cmp     ebx, 0C8h
0x18000a457  jb      short loc_18000A46D
0x18000a459  cmp     ebx, 100h
0x18000a45f  jl      short loc_18000A469
0x18000a461  cmp     ebx, 200h
0x18000a467  jb      short loc_18000A46D
0x18000a469  xor     al, al
0x18000a46b  jmp     short loc_18000A4CD
0x18000a46d  call    cs:__imp_AcquireSRWLockExclusive
0x18000a473  mov     [rsp+58h+var_38], rdi
0x18000a478  cmp     ebx, 7
0x18000a47b  ja      short loc_18000A487
0x18000a47d  mov     eax, 0CCh
0x18000a482  bt      eax, ebx
0x18000a485  jb      short loc_18000A4A7
0x18000a487  lea     eax, [rbx-100h]
0x18000a48d  cmp     eax, 7Fh
0x18000a490  jbe     short loc_18000A4A7
0x18000a492  mov     r9d, ebp
0x18000a495  lea     rcx, [rdi+48h]
0x18000a499  mov     r8d, esi
0x18000a49c  mov     edx, ebx
0x18000a49e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000a4a3  mov     bl, al
0x18000a4a5  jmp     short loc_18000A4B8
0x18000a4a7  mov     r8d, esi
0x18000a4aa  lea     rcx, [rdi+8]
0x18000a4ae  mov     edx, ebx
0x18000a4b0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000a4b5  mov     bl, [rdi+40h]
0x18000a4b8  lea     rcx, [rsp+58h+var_38]
0x18000a4bd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000a4c2  mov     al, bl
0x18000a4c4  jmp     short loc_18000A4CD
0x18000a4c6  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000a4cb  mov     al, 1
0x18000a4cd  add     rsp, 38h
0x18000a4d1  pop     rdi
0x18000a4d2  pop     rsi
0x18000a4d3  pop     rbp
0x18000a4d4  pop     rbx
0x18000a4d5  retn
```
