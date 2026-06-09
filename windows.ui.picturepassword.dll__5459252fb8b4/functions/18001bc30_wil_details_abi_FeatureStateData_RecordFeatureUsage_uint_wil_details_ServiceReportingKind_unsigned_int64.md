# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18001bc30`
- end: `0x18001bcd2`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18001bcd8`

## callees

- `0x180005cb8`
- `0x18001bc30`
- `0x18001bda0`
- `0x18001bdd4`
- `0x18001be0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001bc69`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001bc69`

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
0x18001bc30  push    rbx
0x18001bc32  push    rbp
0x18001bc33  push    rsi
0x18001bc34  push    rdi
0x18001bc35  sub     rsp, 38h
0x18001bc39  mov     rbp, r9
0x18001bc3c  mov     ebx, r8d
0x18001bc3f  mov     esi, edx
0x18001bc41  mov     rdi, rcx
0x18001bc44  cmp     r8d, 0FEh
0x18001bc4b  jz      short loc_18001BCC2
0x18001bc4d  cmp     ebx, 0C8h
0x18001bc53  jb      short loc_18001BC69
0x18001bc55  cmp     ebx, 100h
0x18001bc5b  jl      short loc_18001BC65
0x18001bc5d  cmp     ebx, 200h
0x18001bc63  jb      short loc_18001BC69
0x18001bc65  xor     al, al
0x18001bc67  jmp     short loc_18001BCC9
0x18001bc69  call    cs:__imp_AcquireSRWLockExclusive
0x18001bc6f  mov     [rsp+58h+var_38], rdi
0x18001bc74  cmp     ebx, 7
0x18001bc77  ja      short loc_18001BC83
0x18001bc79  mov     eax, 0CCh
0x18001bc7e  bt      eax, ebx
0x18001bc81  jb      short loc_18001BCA3
0x18001bc83  lea     eax, [rbx-100h]
0x18001bc89  cmp     eax, 7Fh
0x18001bc8c  jbe     short loc_18001BCA3
0x18001bc8e  mov     r9d, ebp
0x18001bc91  lea     rcx, [rdi+48h]
0x18001bc95  mov     r8d, esi
0x18001bc98  mov     edx, ebx
0x18001bc9a  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18001bc9f  mov     bl, al
0x18001bca1  jmp     short loc_18001BCB4
0x18001bca3  mov     r8d, esi
0x18001bca6  lea     rcx, [rdi+8]
0x18001bcaa  mov     edx, ebx
0x18001bcac  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18001bcb1  mov     bl, [rdi+40h]
0x18001bcb4  lea     rcx, [rsp+58h+var_38]
0x18001bcb9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001bcbe  mov     al, bl
0x18001bcc0  jmp     short loc_18001BCC9
0x18001bcc2  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18001bcc7  mov     al, 1
0x18001bcc9  add     rsp, 38h
0x18001bccd  pop     rdi
0x18001bcce  pop     rsi
0x18001bccf  pop     rbp
0x18001bcd0  pop     rbx
0x18001bcd1  retn
```
