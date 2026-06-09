# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18002cb34`
- end: `0x18002cbdd`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180024950`

## callees

- `0x180024d20`
- `0x18002cb34`
- `0x18002cd30`
- `0x18002cd68`
- `0x18002cda0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002cb6d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002cb6d`

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
0x18002cb34  push    rbx
0x18002cb36  push    rbp
0x18002cb37  push    rsi
0x18002cb38  push    rdi
0x18002cb39  sub     rsp, 38h
0x18002cb3d  mov     rbp, r9
0x18002cb40  mov     ebx, r8d
0x18002cb43  mov     esi, edx
0x18002cb45  mov     rdi, rcx
0x18002cb48  cmp     r8d, 0FEh
0x18002cb4f  jz      short loc_18002CBCC
0x18002cb51  cmp     ebx, 0C8h
0x18002cb57  jb      short loc_18002CB6D
0x18002cb59  cmp     ebx, 100h
0x18002cb5f  jl      short loc_18002CB69
0x18002cb61  cmp     ebx, 200h
0x18002cb67  jb      short loc_18002CB6D
0x18002cb69  xor     al, al
0x18002cb6b  jmp     short loc_18002CBD3
0x18002cb6d  call    cs:__imp_AcquireSRWLockExclusive
0x18002cb74  nop     dword ptr [rax+rax+00h]
0x18002cb79  mov     [rsp+58h+var_38], rdi
0x18002cb7e  cmp     ebx, 7
0x18002cb81  ja      short loc_18002CB8D
0x18002cb83  mov     eax, 0CCh
0x18002cb88  bt      eax, ebx
0x18002cb8b  jb      short loc_18002CBAD
0x18002cb8d  lea     eax, [rbx-100h]
0x18002cb93  cmp     eax, 7Fh
0x18002cb96  jbe     short loc_18002CBAD
0x18002cb98  mov     r9d, ebp
0x18002cb9b  lea     rcx, [rdi+48h]
0x18002cb9f  mov     r8d, esi
0x18002cba2  mov     edx, ebx
0x18002cba4  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18002cba9  mov     bl, al
0x18002cbab  jmp     short loc_18002CBBE
0x18002cbad  mov     r8d, esi
0x18002cbb0  lea     rcx, [rdi+8]
0x18002cbb4  mov     edx, ebx
0x18002cbb6  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18002cbbb  mov     bl, [rdi+40h]
0x18002cbbe  lea     rcx, [rsp+58h+var_38]
0x18002cbc3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002cbc8  mov     al, bl
0x18002cbca  jmp     short loc_18002CBD3
0x18002cbcc  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18002cbd1  mov     al, 1
0x18002cbd3  add     rsp, 38h
0x18002cbd7  pop     rdi
0x18002cbd8  pop     rsi
0x18002cbd9  pop     rbp
0x18002cbda  pop     rbx
0x18002cbdb  retn
```
