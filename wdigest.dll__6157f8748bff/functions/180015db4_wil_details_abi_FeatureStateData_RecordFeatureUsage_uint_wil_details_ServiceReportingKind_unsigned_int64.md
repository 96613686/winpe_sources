# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180015db4`
- end: `0x180015e59`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000f294`

## callees

- `0x180011708`
- `0x180015db4`
- `0x180015eb0`
- `0x180015ee4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015def`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015def`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015e3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015e3d`

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

  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(a1);
    return 1;
  }
  else if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1);
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
0x180015db4  push    rbx
0x180015db6  push    rbp
0x180015db7  push    rsi
0x180015db8  push    rdi
0x180015db9  push    r14
0x180015dbb  sub     rsp, 20h
0x180015dbf  mov     r14, r9
0x180015dc2  mov     ebx, r8d
0x180015dc5  mov     ebp, edx
0x180015dc7  mov     rdi, rcx
0x180015dca  cmp     r8d, 0FEh
0x180015dd1  jz      short loc_180015E47
0x180015dd3  cmp     ebx, 0C8h
0x180015dd9  jb      short loc_180015DEF
0x180015ddb  cmp     ebx, 100h
0x180015de1  jl      short loc_180015DEB
0x180015de3  cmp     ebx, 200h
0x180015de9  jb      short loc_180015DEF
0x180015deb  xor     al, al
0x180015ded  jmp     short loc_180015E4E
0x180015def  call    cs:__imp_AcquireSRWLockExclusive
0x180015df5  cmp     ebx, 7
0x180015df8  ja      short loc_180015E04
0x180015dfa  mov     eax, 0CCh
0x180015dff  bt      eax, ebx
0x180015e02  jb      short loc_180015E24
0x180015e04  lea     eax, [rbx-100h]
0x180015e0a  cmp     eax, 7Fh
0x180015e0d  jbe     short loc_180015E24
0x180015e0f  mov     r9d, r14d
0x180015e12  lea     rcx, [rdi+48h]
0x180015e16  mov     r8d, ebp
0x180015e19  mov     edx, ebx
0x180015e1b  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180015e20  mov     bl, al
0x180015e22  jmp     short loc_180015E35
0x180015e24  mov     r8d, ebp
0x180015e27  lea     rcx, [rdi+8]
0x180015e2b  mov     edx, ebx
0x180015e2d  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180015e32  mov     bl, [rdi+40h]
0x180015e35  test    rdi, rdi
0x180015e38  jz      short loc_180015E43
0x180015e3a  mov     rcx, rdi; SRWLock
0x180015e3d  call    cs:__imp_ReleaseSRWLockExclusive
0x180015e43  mov     al, bl
0x180015e45  jmp     short loc_180015E4E
0x180015e47  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180015e4c  mov     al, 1
0x180015e4e  add     rsp, 20h
0x180015e52  pop     r14
0x180015e54  pop     rdi
0x180015e55  pop     rsi
0x180015e56  pop     rbp
0x180015e57  pop     rbx
0x180015e58  retn
```
