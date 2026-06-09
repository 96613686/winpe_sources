# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18001aec4`
- end: `0x18001af6d`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18001af74`

## callees

- `0x180018778`
- `0x18001aec4`
- `0x18001b08c`
- `0x18001b0c4`
- `0x18001b0fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001aefd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001aefd`

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
0x18001aec4  push    rbx
0x18001aec6  push    rbp
0x18001aec7  push    rsi
0x18001aec8  push    rdi
0x18001aec9  sub     rsp, 38h
0x18001aecd  mov     rbp, r9
0x18001aed0  mov     ebx, r8d
0x18001aed3  mov     esi, edx
0x18001aed5  mov     rdi, rcx
0x18001aed8  cmp     r8d, 0FEh
0x18001aedf  jz      short loc_18001AF5C
0x18001aee1  cmp     ebx, 0C8h
0x18001aee7  jb      short loc_18001AEFD
0x18001aee9  cmp     ebx, 100h
0x18001aeef  jl      short loc_18001AEF9
0x18001aef1  cmp     ebx, 200h
0x18001aef7  jb      short loc_18001AEFD
0x18001aef9  xor     al, al
0x18001aefb  jmp     short loc_18001AF63
0x18001aefd  call    cs:__imp_AcquireSRWLockExclusive
0x18001af04  nop     dword ptr [rax+rax+00h]
0x18001af09  mov     [rsp+58h+var_38], rdi
0x18001af0e  cmp     ebx, 7
0x18001af11  ja      short loc_18001AF1D
0x18001af13  mov     eax, 0CCh
0x18001af18  bt      eax, ebx
0x18001af1b  jb      short loc_18001AF3D
0x18001af1d  lea     eax, [rbx-100h]
0x18001af23  cmp     eax, 7Fh
0x18001af26  jbe     short loc_18001AF3D
0x18001af28  mov     r9d, ebp
0x18001af2b  lea     rcx, [rdi+48h]
0x18001af2f  mov     r8d, esi
0x18001af32  mov     edx, ebx
0x18001af34  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18001af39  mov     bl, al
0x18001af3b  jmp     short loc_18001AF4E
0x18001af3d  mov     r8d, esi
0x18001af40  lea     rcx, [rdi+8]
0x18001af44  mov     edx, ebx
0x18001af46  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18001af4b  mov     bl, [rdi+40h]
0x18001af4e  lea     rcx, [rsp+58h+var_38]
0x18001af53  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001af58  mov     al, bl
0x18001af5a  jmp     short loc_18001AF63
0x18001af5c  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18001af61  mov     al, 1
0x18001af63  add     rsp, 38h
0x18001af67  pop     rdi
0x18001af68  pop     rsi
0x18001af69  pop     rbp
0x18001af6a  pop     rbx
0x18001af6b  retn
```
