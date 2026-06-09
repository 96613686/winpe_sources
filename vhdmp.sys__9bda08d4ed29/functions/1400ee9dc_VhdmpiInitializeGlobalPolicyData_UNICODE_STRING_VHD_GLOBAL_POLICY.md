# VhdmpiInitializeGlobalPolicyData(_UNICODE_STRING *,_VHD_GLOBAL_POLICY *)

- ea: `0x1400ee9dc`
- end: `0x1400eee5f`
- name: `?VhdmpiInitializeGlobalPolicyData@@YAJPEAU_UNICODE_STRING@@PEAU_VHD_GLOBAL_POLICY@@@Z`
- size: `1155`
- prototype: `__int64 __fastcall(PCUNICODE_STRING StringIn, struct _VHD_GLOBAL_POLICY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400ee42c`

## callees

- `0x14005e100`
- `0x1400a8354`
- `0x1400d10ac`
- `0x1400d10fc`
- `0x1400d11b8`
- `0x1400d12bc`
- `0x1400ee9dc`

## import_xrefs

- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1400eea32`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1400eea32`
- `ntoskrnl!ZwClose` at `0x1400eee2c`
- `ntoskrnl!ZwClose` at `0x1400eee40`
- `ntoskrnl!ZwClose` at `0x1400eee2c`
- `ntoskrnl!ZwClose` at `0x1400eee40`

## string_xrefs

- `0x1400eec28`: `CachePagePriority`
- `0x1400eeb6f`: `VhdxCacheFlushTimeoutMs`
- `0x1400eeb38`: `MinimumInternalOffloadReadSize`
- `0x1400eedc6`: `InternalConcurrentCopyThreadCount`
- `0x1400eed1b`: `EnableAtomicWrites`

## pseudocode

```c
__int64 __fastcall VhdmpiInitializeGlobalPolicyData(PCUNICODE_STRING StringIn, struct _VHD_GLOBAL_POLICY *a2)
{
  HANDLE v3; // rdi
  int updated; // ebx
  int v5; // ecx
  HANDLE Handle; // [rsp+38h] [rbp+18h] BYREF
  HANDLE KeyHandle; // [rsp+40h] [rbp+20h] BYREF

  v3 = 0;
  KeyHandle = 0;
  Handle = 0;
  memset(&StringOut, 0, 0x98u);
  VhdmpGlobalPolicy = 0;
  qword_14008E318 = -1;
  updated = RtlDuplicateUnicodeString(0, StringIn, &StringOut);
  if ( updated >= 0 )
  {
    updated = VhdmpiOpenGlobalPolicyKey(&KeyHandle, &Handle);
    if ( updated < 0 )
    {
      v3 = KeyHandle;
    }
    else
    {
      VhdmpiGetPolicyDWORD(Handle);
      VhdmpiGetPolicyDWORD(Handle);
      VhdmpiGetPolicyBOOLEAN(Handle, L"ForceDisableTpSupport", 0, &byte_14008E338);
      VhdmpiGetPolicyBOOLEAN(Handle, L"ForceEnableMegaTrim", 0, &byte_14008E339);
      v3 = KeyHandle;
      if ( (unsigned __int8)VhdmpiGetPolicyDWORD(KeyHandle) )
        byte_14008E340 = 1;
      VhdmpiGetPolicyBOOLEAN(Handle, L"IgnoreCrcFailures", 0, &byte_14008E341);
      VhdmpiGetPolicyBOOLEAN(Handle, L"Vhd1PhysicalSectorSize4KB", 0, &byte_14008E342);
      VhdmpiGetPolicyDWORD(Handle);
      VhdmpiGetPolicyBOOLEAN(Handle, L"VhdxNoDiskAndBlockSizeLimit", 0, &byte_14008E33A);
      VhdmpiGetPolicyDWORD(Handle);
      VhdmpiGetPolicyBOOLEAN(Handle, L"ForceDisableODX", 0, &byte_14008E34C);
      VhdmpiGetPolicyBOOLEAN(Handle, L"ForceDisableTrim", 0, &byte_14008E34D);
      VhdmpiGetPolicyBOOLEAN(Handle, L"DisableReFSDuplicateExtents", 0, &byte_14008E34E);
      VhdmpiGetPolicyBOOLEAN(Handle, L"DisableResiliency", 0, &byte_14008E34F);
      VhdmpiGetPolicyBOOLEAN(Handle, L"DisableVhdxMetadataResiliency", 0, &byte_14008E350);
      VhdmpiGetPolicyBOOLEAN(Handle, L"EnableSharedParentCaching", 0, &byte_14008E351);
      VhdmpiGetPolicyDWORD(Handle);
      VhdmpiGetPolicyDWORD(Handle);
      if ( (unsigned int)(dword_14008E358 - 1) > 0x493DF )
        dword_14008E358 = 60000;
      VhdmpiGetPolicyDWORD(Handle);
      if ( dword_14008E35C - 1 > 0x493DF )
        dword_14008E35C = 180000;
      VhdmpiGetPolicyDWORD(Handle);
      if ( (unsigned int)(dword_14008E360 - 200) > 0x49318 )
        dword_14008E360 = 700;
      VhdmpiGetPolicyDWORD(Handle);
      v5 = dword_14008E364;
      if ( !dword_14008E364 || ((dword_14008E364 - 1) & dword_14008E364) != 0 )
      {
        dword_14008E364 = 128;
        v5 = 128;
      }
      qword_14008E368 = (unsigned int)(v5 - 1);
      VhdmpiGetPolicyBOOLEAN(Handle, L"EnableAtomicWrites", 0, &byte_14008E370);
      VhdmpiGetPolicyDWORD(Handle);
      VhdmpiGetPolicyDWORD(Handle);
      VhdmpiGetPolicyDWORD(Handle);
      VhdmpiGetPolicyDWORD(Handle);
      VhdmpiGetPolicyBOOLEAN(Handle, L"EnableLiveDumpOnSurfaceCancel", 0, &byte_14008E3B4);
      VhdmpiGetPolicyDWORD(Handle);
      if ( dword_14008E380 )
      {
        if ( (unsigned int)dword_14008E380 > 8 )
          dword_14008E380 = 8;
      }
      else
      {
        dword_14008E380 = 1;
      }
      VhdmpiInitializeGPCTLPerfOpts(Handle, (struct _VHD_GLOBAL_POLICY *)&VhdmpGlobalPolicy);
      updated = VhdmpiUpdateDynamicGlobalPolicy((__int64)&VhdmpGlobalPolicy);
      if ( updated >= 0 )
        updated = 0;
    }
  }
  if ( Handle )
    ZwClose(Handle);
  if ( v3 )
    ZwClose(v3);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1400ee9dc  mov     [rsp-8+arg_0], rbx
0x1400ee9e1  mov     [rsp-8+arg_18], rdi
0x1400ee9e6  mov     [rsp-8+Handle], rdx
0x1400ee9eb  push    rbp
0x1400ee9ec  mov     rbp, rsp
0x1400ee9ef  sub     rsp, 20h
0x1400ee9f3  mov     rbx, rcx
0x1400ee9f6  xor     edi, edi
0x1400ee9f8  lea     rcx, StringOut; void *
0x1400ee9ff  mov     [rbp+KeyHandle], rdi
0x1400eea03  xor     edx, edx; Val
0x1400eea05  mov     [rbp+Handle], rdi
0x1400eea09  mov     r8d, 98h; Size
0x1400eea0f  call    memset
0x1400eea14  lea     r8, StringOut; StringOut
0x1400eea1b  mov     cs:VhdmpGlobalPolicy, rdi
0x1400eea22  mov     rdx, rbx; StringIn
0x1400eea25  mov     cs:qword_14008E318, 0FFFFFFFFFFFFFFFFh
0x1400eea30  xor     ecx, ecx; Flags
0x1400eea32  call    cs:__imp_RtlDuplicateUnicodeString
0x1400eea39  nop     dword ptr [rax+rax+00h]
0x1400eea3e  mov     ebx, eax
0x1400eea40  test    eax, eax
0x1400eea42  js      loc_1400EEE23
0x1400eea48  lea     rdx, [rbp+Handle]
0x1400eea4c  lea     rcx, [rbp+KeyHandle]
0x1400eea50  call    VhdmpiOpenGlobalPolicyKey
0x1400eea55  mov     ebx, eax
0x1400eea57  test    eax, eax
0x1400eea59  js      loc_1400EEE1F
0x1400eea5f  mov     rcx, [rbp+Handle]; KeyHandle
0x1400eea63  lea     r9, dword_14008E330
0x1400eea6a  mov     r8d, 12Ch
0x1400eea70  lea     rdx, aSurfacetimeout; "SurfaceTimeout"
0x1400eea77  call    VhdmpiGetPolicyDWORD
0x1400eea7c  mov     rcx, [rbp+Handle]; KeyHandle
0x1400eea80  lea     r9, dword_14008E334
0x1400eea87  lea     r8d, [rdi+3Ch]
0x1400eea8b  lea     rdx, aSurfacebusscan; "SurfaceBusScanPeriod"
0x1400eea92  call    VhdmpiGetPolicyDWORD
0x1400eea97  mov     rcx, [rbp+Handle]
0x1400eea9b  lea     r9, byte_14008E338
0x1400eeaa2  xor     r8d, r8d
0x1400eeaa5  lea     rdx, aForcedisabletp; "ForceDisableTpSupport"
0x1400eeaac  call    VhdmpiGetPolicyBOOLEAN
0x1400eeab1  mov     rcx, [rbp+Handle]
0x1400eeab5  lea     r9, byte_14008E339
0x1400eeabc  xor     r8d, r8d
0x1400eeabf  lea     rdx, aForceenablemeg; "ForceEnableMegaTrim"
0x1400eeac6  call    VhdmpiGetPolicyBOOLEAN
0x1400eeacb  mov     rdi, [rbp+KeyHandle]
0x1400eeacf  lea     r9, dword_14008E33C
0x1400eead6  mov     rcx, rdi; KeyHandle
0x1400eead9  lea     rdx, aSectorsize; "SectorSize"
0x1400eeae0  xor     r8d, r8d
0x1400eeae3  call    VhdmpiGetPolicyDWORD
0x1400eeae8  test    al, al
0x1400eeaea  jz      short loc_1400EEAF3
0x1400eeaec  mov     cs:byte_14008E340, 1
0x1400eeaf3  mov     rcx, [rbp+Handle]
0x1400eeaf7  lea     r9, byte_14008E341
0x1400eeafe  xor     r8d, r8d
0x1400eeb01  lea     rdx, aIgnorecrcfailu; "IgnoreCrcFailures"
0x1400eeb08  call    VhdmpiGetPolicyBOOLEAN
0x1400eeb0d  mov     rcx, [rbp+Handle]
0x1400eeb11  lea     r9, byte_14008E342
0x1400eeb18  xor     r8d, r8d
0x1400eeb1b  lea     rdx, aVhd1physicalse; "Vhd1PhysicalSectorSize4KB"
0x1400eeb22  call    VhdmpiGetPolicyBOOLEAN
0x1400eeb27  mov     rcx, [rbp+Handle]; KeyHandle
0x1400eeb2b  lea     r9, dword_14008E344
0x1400eeb32  mov     r8d, 10000h
0x1400eeb38  lea     rdx, aMinimuminterna; "MinimumInternalOffloadReadSize"
0x1400eeb3f  call    VhdmpiGetPolicyDWORD
0x1400eeb44  mov     rcx, [rbp+Handle]
0x1400eeb48  lea     r9, byte_14008E33A
0x1400eeb4f  xor     r8d, r8d
0x1400eeb52  lea     rdx, aVhdxnodiskandb; "VhdxNoDiskAndBlockSizeLimit"
0x1400eeb59  call    VhdmpiGetPolicyBOOLEAN
0x1400eeb5e  mov     rcx, [rbp+Handle]; KeyHandle
0x1400eeb62  lea     r9, dword_14008E348
0x1400eeb69  mov     r8d, 1388h
0x1400eeb6f  lea     rdx, aVhdxcacheflush; "VhdxCacheFlushTimeoutMs"
0x1400eeb76  call    VhdmpiGetPolicyDWORD
0x1400eeb7b  mov     rcx, [rbp+Handle]
0x1400eeb7f  lea     r9, byte_14008E34C
0x1400eeb86  xor     r8d, r8d
0x1400eeb89  lea     rdx, aForcedisableod; "ForceDisableODX"
0x1400eeb90  call    VhdmpiGetPolicyBOOLEAN
0x1400eeb95  mov     rcx, [rbp+Handle]
0x1400eeb99  lea     r9, byte_14008E34D
0x1400eeba0  xor     r8d, r8d
0x1400eeba3  lea     rdx, aForcedisabletr; "ForceDisableTrim"
0x1400eebaa  call    VhdmpiGetPolicyBOOLEAN
0x1400eebaf  mov     rcx, [rbp+Handle]
0x1400eebb3  lea     r9, byte_14008E34E
0x1400eebba  xor     r8d, r8d
0x1400eebbd  lea     rdx, aDisablerefsdup; "DisableReFSDuplicateExtents"
0x1400eebc4  call    VhdmpiGetPolicyBOOLEAN
0x1400eebc9  mov     rcx, [rbp+Handle]
0x1400eebcd  lea     r9, byte_14008E34F
0x1400eebd4  xor     r8d, r8d
0x1400eebd7  lea     rdx, aDisableresilie; "DisableResiliency"
0x1400eebde  call    VhdmpiGetPolicyBOOLEAN
0x1400eebe3  mov     rcx, [rbp+Handle]
0x1400eebe7  lea     r9, byte_14008E350
0x1400eebee  xor     r8d, r8d
0x1400eebf1  lea     rdx, aDisablevhdxmet; "DisableVhdxMetadataResiliency"
0x1400eebf8  call    VhdmpiGetPolicyBOOLEAN
0x1400eebfd  mov     rcx, [rbp+Handle]
0x1400eec01  lea     r9, byte_14008E351
0x1400eec08  xor     r8d, r8d
0x1400eec0b  lea     rdx, aEnablesharedpa; "EnableSharedParentCaching"
0x1400eec12  call    VhdmpiGetPolicyBOOLEAN
0x1400eec17  mov     rcx, [rbp+Handle]; KeyHandle
0x1400eec1b  lea     r9, dword_14008E354
0x1400eec22  mov     r8d, 5
0x1400eec28  lea     rdx, aCachepageprior; "CachePagePriority"
0x1400eec2f  call    VhdmpiGetPolicyDWORD
0x1400eec34  mov     rcx, [rbp+Handle]; KeyHandle
0x1400eec38  lea     r9, dword_14008E358
0x1400eec3f  mov     ebx, 0EA60h
0x1400eec44  lea     rdx, aSmbresiliencyt; "SmbResiliencyTimeoutMs"
0x1400eec4b  mov     r8d, ebx
0x1400eec4e  call    VhdmpiGetPolicyDWORD
0x1400eec53  mov     eax, cs:dword_14008E358
0x1400eec59  dec     eax
0x1400eec5b  cmp     eax, 493DFh
0x1400eec60  jbe     short loc_1400EEC68
0x1400eec62  mov     cs:dword_14008E358, ebx
0x1400eec68  mov     rcx, [rbp+Handle]; KeyHandle
0x1400eec6c  lea     r9, dword_14008E35C
0x1400eec73  mov     ebx, 2BF20h
0x1400eec78  lea     rdx, aCsvresiliencyt; "CsvResiliencyTimeoutMs"
0x1400eec7f  mov     r8d, ebx
0x1400eec82  call    VhdmpiGetPolicyDWORD
0x1400eec87  mov     eax, cs:dword_14008E35C
0x1400eec8d  dec     eax
0x1400eec8f  cmp     eax, 493DFh
0x1400eec94  jbe     short loc_1400EEC9C
0x1400eec96  mov     cs:dword_14008E35C, ebx
0x1400eec9c  mov     rcx, [rbp+Handle]; KeyHandle
0x1400eeca0  lea     r9, dword_14008E360
0x1400eeca7  mov     ebx, 2BCh
0x1400eecac  lea     rdx, aCtunblockstage; "CTUnblockStageServerTimeoutMs"
0x1400eecb3  mov     r8d, ebx
0x1400eecb6  call    VhdmpiGetPolicyDWORD
0x1400eecbb  mov     eax, cs:dword_14008E360
0x1400eecc1  add     eax, 0FFFFFF38h
0x1400eecc6  cmp     eax, 49318h
0x1400eeccb  jbe     short loc_1400EECD3
0x1400eeccd  mov     cs:dword_14008E360, ebx
0x1400eecd3  mov     rcx, [rbp+Handle]; KeyHandle
0x1400eecd7  lea     r9, dword_14008E364
0x1400eecde  mov     ebx, 80h
0x1400eece3  lea     rdx, aIosubtrackerco; "IoSubTrackerCount"
0x1400eecea  mov     r8d, ebx
0x1400eeced  call    VhdmpiGetPolicyDWORD
0x1400eecf2  mov     ecx, cs:dword_14008E364
0x1400eecf8  test    ecx, ecx
0x1400eecfa  jz      short loc_1400EED03
0x1400eecfc  lea     eax, [rcx-1]
0x1400eecff  test    ecx, eax
0x1400eed01  jz      short loc_1400EED0B
0x1400eed03  mov     cs:dword_14008E364, ebx
0x1400eed09  mov     ecx, ebx
0x1400eed0b  dec     ecx
0x1400eed0d  lea     r9, byte_14008E370
0x1400eed14  mov     cs:qword_14008E368, rcx
0x1400eed1b  lea     rdx, aEnableatomicwr; "EnableAtomicWrites"
0x1400eed22  mov     rcx, [rbp+Handle]
0x1400eed26  xor     r8d, r8d
0x1400eed29  call    VhdmpiGetPolicyBOOLEAN
0x1400eed2e  mov     rcx, [rbp+Handle]; KeyHandle
0x1400eed32  lea     r9, dword_14008E374
0x1400eed39  mov     ebx, 40h ; '@'
0x1400eed3e  lea     rdx, aRctmaximumdirt; "RctMaximumDirtyCount"
0x1400eed45  mov     r8d, ebx
0x1400eed48  call    VhdmpiGetPolicyDWORD
0x1400eed4d  mov     rcx, [rbp+Handle]; KeyHandle
0x1400eed51  lea     r9, byte_14008E378
0x1400eed58  lea     r8d, [rbx+38h]
0x1400eed5c  lea     rdx, aRctmaximumwrit; "RctMaximumWrittenCount"
0x1400eed63  call    VhdmpiGetPolicyDWORD
0x1400eed68  mov     rcx, [rbp+Handle]; KeyHandle
0x1400eed6c  lea     r9, dword_14008E37C
0x1400eed73  mov     r8d, ebx
0x1400eed76  lea     rdx, aRctmaximumflus; "RctMaximumFlushedCount"
0x1400eed7d  call    VhdmpiGetPolicyDWORD
0x1400eed82  mov     rcx, [rbp+Handle]; KeyHandle
0x1400eed86  lea     r9, dword_14008E3B0
0x1400eed8d  lea     r8d, [rbx-35h]
0x1400eed91  lea     rdx, aTelemetrylaten; "TelemetryLatencyThresholdIndex"
0x1400eed98  call    VhdmpiGetPolicyDWORD
0x1400eed9d  mov     rcx, [rbp+Handle]
0x1400eeda1  lea     r9, byte_14008E3B4
0x1400eeda8  xor     r8d, r8d
0x1400eedab  lea     rdx, aEnablelivedump; "EnableLiveDumpOnSurfaceCancel"
0x1400eedb2  call    VhdmpiGetPolicyBOOLEAN
0x1400eedb7  mov     rcx, [rbp+Handle]; KeyHandle
0x1400eedbb  lea     r9, dword_14008E380
0x1400eedc2  lea     r8d, [rbx-3Ch]
0x1400eedc6  lea     rdx, aInternalconcur_1; "InternalConcurrentCopyThreadCount"
0x1400eedcd  call    VhdmpiGetPolicyDWORD
0x1400eedd2  mov     eax, cs:dword_14008E380
0x1400eedd8  cmp     eax, 1
0x1400eeddb  jnb     short loc_1400EEDE9
0x1400eeddd  mov     cs:dword_14008E380, 1
0x1400eede7  jmp     short loc_1400EEDF8
0x1400eede9  cmp     eax, 8
0x1400eedec  jbe     short loc_1400EEDF8
0x1400eedee  mov     cs:dword_14008E380, 8
0x1400eedf8  mov     rcx, [rbp+Handle]; KeyHandle
0x1400eedfc  lea     rdx, VhdmpGlobalPolicy; struct _VHD_GLOBAL_POLICY *
0x1400eee03  call    VhdmpiInitializeGPCTLPerfOpts
0x1400eee08  lea     rcx, VhdmpGlobalPolicy
0x1400eee0f  call    VhdmpiUpdateDynamicGlobalPolicy
0x1400eee14  mov     ebx, eax
0x1400eee16  xor     eax, eax
0x1400eee18  test    ebx, ebx
0x1400eee1a  cmovns  ebx, eax
0x1400eee1d  jmp     short loc_1400EEE23
0x1400eee1f  mov     rdi, [rbp+KeyHandle]
0x1400eee23  mov     rcx, [rbp+Handle]; Handle
0x1400eee27  test    rcx, rcx
0x1400eee2a  jz      short loc_1400EEE38
0x1400eee2c  call    cs:__imp_ZwClose
0x1400eee33  nop     dword ptr [rax+rax+00h]
0x1400eee38  test    rdi, rdi
0x1400eee3b  jz      short loc_1400EEE4C
0x1400eee3d  mov     rcx, rdi; Handle
0x1400eee40  call    cs:__imp_ZwClose
0x1400eee47  nop     dword ptr [rax+rax+00h]
0x1400eee4c  mov     rdi, [rsp+20h+arg_18]
0x1400eee51  mov     eax, ebx
0x1400eee53  mov     rbx, [rsp+20h+arg_0]
0x1400eee58  add     rsp, 20h
0x1400eee5c  pop     rbp
0x1400eee5d  retn
```
