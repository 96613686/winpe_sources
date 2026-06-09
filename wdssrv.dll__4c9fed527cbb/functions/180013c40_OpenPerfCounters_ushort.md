# OpenPerfCounters(ushort *)

- ea: `0x180013c40`
- end: `0x180013cad`
- name: `?OpenPerfCounters@@YAKPEAG@Z`
- size: `109`
- prototype: `unsigned int __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180013c40`
- `0x180013cb4`

## import_xrefs

- `WdsServerCommonLib!?InitializeClient@CPerfCounters@@QEAAKAEBU_GUID@@0PEBGKKPEAK@Z` at `0x180013c8f`
- `WdsServerCommonLib!?InitializeClient@CPerfCounters@@QEAAKAEBU_GUID@@0PEBGKKPEAK@Z` at `0x180013c8f`

## string_xrefs

- `0x180013c66`: `System\CurrentControlSet\Services\WDSServer\Performance`

## pseudocode

```c
__int64 __fastcall OpenPerfCounters(unsigned __int16 *a1)
{
  __int64 v1; // rbx

  LODWORD(v1) = 0;
  if ( !g_PerfCounters || !qword_180039328 )
  {
    v1 = CPerfCounters::InitializeClient(
           (CPerfCounters *)&g_PerfCounters,
           (const struct _GUID *)qword_1800219F8,
           (const struct _GUID *)qword_1800219E8,
           L"System\\CurrentControlSet\\Services\\WDSServer\\Performance",
           0x28u,
           0x28u,
           (unsigned int *)qword_180028220);
    ElValidateWin32_4(v1);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180013c40  push    rbx
0x180013c42  sub     rsp, 40h
0x180013c46  xor     ebx, ebx
0x180013c48  cmp     cs:?g_PerfCounters@@3VCWdsPerfCounters@@A, rbx; CWdsPerfCounters g_PerfCounters
0x180013c4f  jz      short loc_180013C5A
0x180013c51  cmp     cs:qword_180039328, rbx
0x180013c58  jnz     short loc_180013CA4
0x180013c5a  lea     rax, qword_180028220
0x180013c61  mov     [rsp+48h+var_18], rax
0x180013c66  lea     r9, aSystemCurrentc; "System\\CurrentControlSet\\Services\\WD"...
0x180013c6d  mov     eax, 28h ; '('
0x180013c72  lea     r8, qword_1800219E8
0x180013c79  mov     [rsp+48h+var_20], eax
0x180013c7d  lea     rdx, qword_1800219F8
0x180013c84  lea     rcx, ?g_PerfCounters@@3VCWdsPerfCounters@@A; CWdsPerfCounters g_PerfCounters
0x180013c8b  mov     [rsp+48h+var_28], eax
0x180013c8f  call    cs:__imp_?InitializeClient@CPerfCounters@@QEAAKAEBU_GUID@@0PEBGKKPEAK@Z; CPerfCounters::InitializeClient(_GUID const &,_GUID const &,ushort const *,ulong,ulong,ulong *)
0x180013c96  nop     dword ptr [rax+rax+00h]
0x180013c9b  mov     ecx, eax
0x180013c9d  mov     ebx, eax
0x180013c9f  call    ElValidateWin32_4
0x180013ca4  mov     eax, ebx
0x180013ca6  add     rsp, 40h
0x180013caa  pop     rbx
0x180013cab  retn
```
