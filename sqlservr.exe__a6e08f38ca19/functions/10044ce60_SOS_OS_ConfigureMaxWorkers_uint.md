# SOS_OS::ConfigureMaxWorkers(uint)

- ea: `0x10044ce60`
- end: `0x10044cf38`
- name: `?ConfigureMaxWorkers@SOS_OS@@SAHI@Z`
- size: `216`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x100413d90`

## callees

- `0x10044ce60`

## import_xrefs

- `sqldk!?sm_MaxWorkers@SOS_PublicGlobals@@2IA` at `0x10044ce97`
- `sqldk!?sm_MaxWorkers@SOS_PublicGlobals@@2IA` at `0x10044ceb4`
- `sqldk!?sm_MaxWorkers@SOS_PublicGlobals@@2IA` at `0x10044ced6`
- `sqldk!?sm_MaxWorkers@SOS_PublicGlobals@@2IA` at `0x10044cef8`
- `sqldk!?GetDefaultMaxWorkers@SOS_OS@@CAIXZ` at `0x10044ce85`
- `sqldk!?GetDefaultMaxWorkers@SOS_OS@@CAIXZ` at `0x10044ce8f`
- `sqldk!?GetDefaultMaxWorkers@SOS_OS@@CAIXZ` at `0x10044cec4`
- `sqldk!?GetDefaultMaxWorkers@SOS_OS@@CAIXZ` at `0x10044cece`
- `sqldk!?GetDefaultMaxWorkers@SOS_OS@@CAIXZ` at `0x10044ce85`
- `sqldk!?GetDefaultMaxWorkers@SOS_OS@@CAIXZ` at `0x10044ce8f`
- `sqldk!?GetDefaultMaxWorkers@SOS_OS@@CAIXZ` at `0x10044cec4`
- `sqldk!?GetDefaultMaxWorkers@SOS_OS@@CAIXZ` at `0x10044cece`
- `sqldk!?sm_MaxWorkersConfigType@SOS_PublicGlobals@@2W4MaxWorkersConfigType@SOS_OS@@A` at `0x10044cea0`
- `sqldk!?sm_MaxWorkersConfigType@SOS_PublicGlobals@@2W4MaxWorkersConfigType@SOS_OS@@A` at `0x10044cedf`
- `sqldk!?SOS_OS_MaxWorkersPerSchedulerLowerBound@@3IA` at `0x10044ce6a`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x10044ce75`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x10044cee8`
- `sqldk!?SOS_OS_WorkersAvailable@@3JC` at `0x10044cf1d`
- `sqldk!?sm_WorkersAvailableTotal@SOS_PublicGlobals@@2IA` at `0x10044ceef`
- `sqldk!?sm_WorkersAvailableTotal@SOS_PublicGlobals@@2IA` at `0x10044cf08`
- `sqldk!?sm_WorkersAvailableTotal@SOS_PublicGlobals@@2IA` at `0x10044cf14`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 __fastcall SOS_OS::ConfigureMaxWorkers(unsigned int a1)
{
  unsigned int v1; // edi
  unsigned int DefaultMaxWorkers; // ebx

  v1 = 0;
  DefaultMaxWorkers = SOS_OS_MaxWorkersPerSchedulerLowerBound * SOS_PublicGlobals::sm_cpuCount;
  if ( a1 )
  {
    if ( a1 < DefaultMaxWorkers )
    {
      if ( DefaultMaxWorkers <= (unsigned int)SOS_OS::GetDefaultMaxWorkers() )
        DefaultMaxWorkers = SOS_OS::GetDefaultMaxWorkers();
      SOS_PublicGlobals::sm_MaxWorkers = DefaultMaxWorkers;
    }
    else
    {
      v1 = 1;
      SOS_PublicGlobals::sm_MaxWorkers = a1;
    }
    SOS_PublicGlobals::sm_MaxWorkersConfigType = v1;
  }
  else
  {
    if ( DefaultMaxWorkers <= (unsigned int)SOS_OS::GetDefaultMaxWorkers() )
      DefaultMaxWorkers = SOS_OS::GetDefaultMaxWorkers();
    SOS_PublicGlobals::sm_MaxWorkers = DefaultMaxWorkers;
    SOS_PublicGlobals::sm_MaxWorkersConfigType = 0;
    v1 = 1;
  }
  SOS_PublicGlobals::sm_WorkersAvailableTotal = SOS_PublicGlobals::sm_MaxWorkers - 3 * SOS_PublicGlobals::sm_cpuCount;
  _InterlockedExchangeAdd(*(volatile signed __int32 **)&SOS_OS_WorkersAvailable, 0);
  return v1;
}

```

## disassembly

```asm
0x10044ce60  mov     [rsp+arg_0], rbx
0x10044ce65  push    rdi
0x10044ce66  sub     rsp, 20h
0x10044ce6a  mov     rax, cs:__imp_?SOS_OS_MaxWorkersPerSchedulerLowerBound@@3IA; uint SOS_OS_MaxWorkersPerSchedulerLowerBound
0x10044ce71  xor     edi, edi
0x10044ce73  mov     edx, [rax]
0x10044ce75  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x10044ce7c  mov     ebx, [rax]
0x10044ce7e  imul    ebx, edx
0x10044ce81  test    ecx, ecx
0x10044ce83  jnz     short loc_10044CEB0
0x10044ce85  call    cs:__imp_?GetDefaultMaxWorkers@SOS_OS@@CAIXZ; SOS_OS::GetDefaultMaxWorkers(void)
0x10044ce8b  cmp     ebx, eax
0x10044ce8d  ja      short loc_10044CE97
0x10044ce8f  call    cs:__imp_?GetDefaultMaxWorkers@SOS_OS@@CAIXZ; SOS_OS::GetDefaultMaxWorkers(void)
0x10044ce95  mov     ebx, eax
0x10044ce97  mov     rcx, cs:__imp_?sm_MaxWorkers@SOS_PublicGlobals@@2IA; uint SOS_PublicGlobals::sm_MaxWorkers
0x10044ce9e  mov     [rcx], ebx
0x10044cea0  mov     rax, cs:__imp_?sm_MaxWorkersConfigType@SOS_PublicGlobals@@2W4MaxWorkersConfigType@SOS_OS@@A; SOS_OS::MaxWorkersConfigType SOS_PublicGlobals::sm_MaxWorkersConfigType
0x10044cea7  mov     [rax], edi
0x10044cea9  mov     edi, 1
0x10044ceae  jmp     short loc_10044CEE8
0x10044ceb0  cmp     ecx, ebx
0x10044ceb2  jb      short loc_10044CEC4
0x10044ceb4  mov     rax, cs:__imp_?sm_MaxWorkers@SOS_PublicGlobals@@2IA; uint SOS_PublicGlobals::sm_MaxWorkers
0x10044cebb  mov     edi, 1
0x10044cec0  mov     [rax], ecx
0x10044cec2  jmp     short loc_10044CEDF
0x10044cec4  call    cs:__imp_?GetDefaultMaxWorkers@SOS_OS@@CAIXZ; SOS_OS::GetDefaultMaxWorkers(void)
0x10044ceca  cmp     ebx, eax
0x10044cecc  ja      short loc_10044CED6
0x10044cece  call    cs:__imp_?GetDefaultMaxWorkers@SOS_OS@@CAIXZ; SOS_OS::GetDefaultMaxWorkers(void)
0x10044ced4  mov     ebx, eax
0x10044ced6  mov     rax, cs:__imp_?sm_MaxWorkers@SOS_PublicGlobals@@2IA; uint SOS_PublicGlobals::sm_MaxWorkers
0x10044cedd  mov     [rax], ebx
0x10044cedf  mov     rax, cs:__imp_?sm_MaxWorkersConfigType@SOS_PublicGlobals@@2W4MaxWorkersConfigType@SOS_OS@@A; SOS_OS::MaxWorkersConfigType SOS_PublicGlobals::sm_MaxWorkersConfigType
0x10044cee6  mov     [rax], edi
0x10044cee8  mov     rcx, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x10044ceef  mov     rax, cs:__imp_?sm_WorkersAvailableTotal@SOS_PublicGlobals@@2IA; uint SOS_PublicGlobals::sm_WorkersAvailableTotal
0x10044cef6  mov     edx, [rcx]
0x10044cef8  mov     rcx, cs:__imp_?sm_MaxWorkers@SOS_PublicGlobals@@2IA; uint SOS_PublicGlobals::sm_MaxWorkers
0x10044ceff  mov     r9d, [rax]
0x10044cf02  lea     r8d, [rdx+rdx*2]
0x10044cf06  mov     edx, [rcx]
0x10044cf08  mov     rcx, cs:__imp_?sm_WorkersAvailableTotal@SOS_PublicGlobals@@2IA; uint SOS_PublicGlobals::sm_WorkersAvailableTotal
0x10044cf0f  sub     edx, r8d
0x10044cf12  mov     [rcx], edx
0x10044cf14  mov     rcx, cs:__imp_?sm_WorkersAvailableTotal@SOS_PublicGlobals@@2IA; uint SOS_PublicGlobals::sm_WorkersAvailableTotal
0x10044cf1b  mov     edx, [rcx]
0x10044cf1d  mov     rcx, cs:__imp_?SOS_OS_WorkersAvailable@@3JC; long volatile SOS_OS_WorkersAvailable
0x10044cf24  sub     edx, r9d
0x10044cf27  lock xadd [rcx], edx
0x10044cf2b  mov     rbx, [rsp+28h+arg_0]
0x10044cf30  mov     eax, edi
0x10044cf32  add     rsp, 20h
0x10044cf36  pop     rdi
0x10044cf37  retn
```
