# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180005e6c`
- end: `0x180005f11`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180005a90`

## callees

- `0x18000595c`
- `0x180005e6c`
- `0x180005f18`
- `0x180018810`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005ea5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005ea5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005ed3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005ed3`

## pseudocode

```c
char __fastcall wil::details_abi::FeatureStateData::RecordFeatureUsage(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  int v9; // eax
  char v10; // bl

  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage((PSRWLOCK)a1);
    return 1;
  }
  else if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1);
    if ( a3 <= 7 && (v9 = 204, _bittest(&v9, a3)) || a3 - 256 <= 0x7F )
    {
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(a1 + 8, a3, a2);
      v10 = *(_BYTE *)(a1 + 64);
    }
    else
    {
      v10 = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              a1 + 72,
              a3,
              a2,
              a4);
    }
    if ( a1 )
      ReleaseSRWLockExclusive((PSRWLOCK)a1);
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
0x180005e6c  push    rbx
0x180005e6e  push    rbp
0x180005e6f  push    rsi
0x180005e70  push    rdi
0x180005e71  push    r14
0x180005e73  sub     rsp, 20h
0x180005e77  mov     r14, r9
0x180005e7a  mov     ebx, r8d
0x180005e7d  mov     ebp, edx
0x180005e7f  mov     rdi, rcx
0x180005e82  cmp     r8d, 0FEh
0x180005e89  jnz     short loc_180005E9D
0x180005e8b  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180005e90  mov     al, 1
0x180005e92  add     rsp, 20h
0x180005e96  pop     r14
0x180005e98  pop     rdi
0x180005e99  pop     rsi
0x180005e9a  pop     rbp
0x180005e9b  pop     rbx
0x180005e9c  retn
0x180005e9d  cmp     ebx, 0C8h
0x180005ea3  jnb     short loc_180005EDD
0x180005ea5  call    cs:__imp_AcquireSRWLockExclusive
0x180005eab  cmp     ebx, 7
0x180005eae  ja      short loc_180005EF1
0x180005eb0  mov     eax, 0CCh
0x180005eb5  bt      eax, ebx
0x180005eb8  jnb     short loc_180005EF1
0x180005eba  mov     r8d, ebp
0x180005ebd  lea     rcx, [rdi+8]
0x180005ec1  mov     edx, ebx
0x180005ec3  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180005ec8  mov     bl, [rdi+40h]
0x180005ecb  test    rdi, rdi
0x180005ece  jz      short loc_180005ED9
0x180005ed0  mov     rcx, rdi; SRWLock
0x180005ed3  call    cs:__imp_ReleaseSRWLockExclusive
0x180005ed9  mov     al, bl
0x180005edb  jmp     short loc_180005E92
0x180005edd  cmp     ebx, 100h
0x180005ee3  jl      short loc_180005EED
0x180005ee5  cmp     ebx, 200h
0x180005eeb  jb      short loc_180005EA5
0x180005eed  xor     al, al
0x180005eef  jmp     short loc_180005E92
0x180005ef1  lea     eax, [rbx-100h]
0x180005ef7  cmp     eax, 7Fh
0x180005efa  jbe     short loc_180005EBA
0x180005efc  mov     r9d, r14d
0x180005eff  lea     rcx, [rdi+48h]
0x180005f03  mov     r8d, ebp
0x180005f06  mov     edx, ebx
0x180005f08  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180005f0d  mov     bl, al
0x180005f0f  jmp     short loc_180005ECB
```
