# CTrkWksSvc::CTrkWksSvc(void)

- ea: `0x180003684`
- end: `0x180003792`
- name: `??0CTrkWksSvc@@QEAA@XZ`
- size: `270`
- prototype: `CTrkWksSvc *__fastcall(CTrkWksSvc *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180001d4c`

## callees

- `0x1800034fc`
- `0x180003b8c`
- `0x180009ff8`
- `0x18000a12c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800036bd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800036bd`

## string_xrefs

- `0x18000376d`: `MoveQuotaReached`

## pseudocode

```c
CTrkWksSvc *__fastcall CTrkWksSvc::CTrkWksSvc(CTrkWksSvc *this)
{
  CTrkWksSvc *result; // rax

  *(_QWORD *)this = &PShareMerit::`vftable';
  CTrkRpcConfig::CTrkRpcConfig((CTrkWksSvc *)((char *)this + 16));
  *(_QWORD *)this = &CTrkWksSvc::`vftable'{for `IServiceHandler'};
  *((_QWORD *)this + 1) = &CTrkWksSvc::`vftable'{for `PWorkItem'};
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  *((_DWORD *)this + 12) = 0;
  *((_DWORD *)this + 92) &= ~1u;
  *((_DWORD *)this + 90) = 1;
  *((_DWORD *)this + 91) = 1264013908;
  *((_DWORD *)this + 93) = 0;
  *((_DWORD *)this + 98) &= ~1u;
  *((_QWORD *)this + 48) = &CPort::`vftable';
  CTrkRpcConfig::CTrkRpcConfig((CTrkWksSvc *)((char *)this + 448));
  *((_QWORD *)this + 60) = 0;
  *((_DWORD *)this + 122) = 0;
  *((_DWORD *)this + 124) &= ~1u;
  *((_QWORD *)this + 66) = 0;
  *(_OWORD *)((char *)this + 536) = 0;
  *(_OWORD *)((char *)this + 552) = 0;
  *((_QWORD *)this + 71) = 0;
  CVolumeManager::CVolumeManager((CTrkWksSvc *)((char *)this + 576));
  CVolumeLocationCache::CVolumeLocationCache((CTrkWksSvc *)((char *)this + 1040));
  CRegBoolParameter::CRegBoolParameter((CTrkWksSvc *)((char *)this + 2384), L"MoveQuotaReached");
  result = this;
  *((_QWORD *)this + 47) = 0;
  return result;
}

```

## disassembly

```asm
0x180003684  mov     [rsp+arg_0], rbx
0x180003689  push    rdi
0x18000368a  sub     rsp, 20h
0x18000368e  lea     rax, ??_7PShareMerit@@6B@; const PShareMerit::`vftable'
0x180003695  mov     rdi, rcx
0x180003698  mov     [rcx], rax
0x18000369b  add     rcx, 10h; this
0x18000369f  call    ??0CTrkRpcConfig@@IEAA@XZ; CTrkRpcConfig::CTrkRpcConfig(void)
0x1800036a4  lea     rax, ??_7CTrkWksSvc@@6BIServiceHandler@@@; const CTrkWksSvc::`vftable'{for `IServiceHandler'}
0x1800036ab  mov     [rdi], rax
0x1800036ae  lea     rcx, [rdi+38h]; lpCriticalSection
0x1800036b2  lea     rax, ??_7CTrkWksSvc@@6BPWorkItem@@@; const CTrkWksSvc::`vftable'{for `PWorkItem'}
0x1800036b9  mov     [rdi+8], rax
0x1800036bd  call    cs:__imp_InitializeCriticalSection
0x1800036c3  mov     dword ptr [rdi+30h], 0
0x1800036ca  lea     rax, ??_7CPort@@6B@; const CPort::`vftable'
0x1800036d1  and     dword ptr [rdi+170h], 0FFFFFFFEh
0x1800036d8  lea     rbx, [rdi+1C0h]
0x1800036df  mov     dword ptr [rdi+168h], 1
0x1800036e9  mov     rcx, rbx; this
0x1800036ec  mov     dword ptr [rdi+16Ch], 4B575254h
0x1800036f6  mov     dword ptr [rdi+174h], 0
0x180003700  and     dword ptr [rdi+188h], 0FFFFFFFEh
0x180003707  mov     [rdi+180h], rax
0x18000370e  call    ??0CTrkRpcConfig@@IEAA@XZ; CTrkRpcConfig::CTrkRpcConfig(void)
0x180003713  mov     qword ptr [rbx+20h], 0
0x18000371b  lea     rcx, [rdi+240h]; this
0x180003722  mov     dword ptr [rbx+28h], 0
0x180003729  xorps   xmm0, xmm0
0x18000372c  and     dword ptr [rdi+1F0h], 0FFFFFFFEh
0x180003733  xor     eax, eax
0x180003735  mov     qword ptr [rdi+210h], 0
0x180003740  movups  xmmword ptr [rdi+218h], xmm0
0x180003747  movups  xmmword ptr [rdi+228h], xmm0
0x18000374e  mov     [rdi+238h], rax
0x180003755  call    ??0CVolumeManager@@QEAA@XZ; CVolumeManager::CVolumeManager(void)
0x18000375a  lea     rcx, [rdi+410h]; this
0x180003761  call    ??0CVolumeLocationCache@@QEAA@XZ; CVolumeLocationCache::CVolumeLocationCache(void)
0x180003766  lea     rcx, [rdi+950h]; this
0x18000376d  lea     rdx, aMovequotareach; "MoveQuotaReached"
0x180003774  call    ??0CRegBoolParameter@@QEAA@PEBG@Z; CRegBoolParameter::CRegBoolParameter(ushort const *)
0x180003779  mov     rbx, [rsp+28h+arg_0]
0x18000377e  mov     rax, rdi
0x180003781  mov     qword ptr [rdi+178h], 0
0x18000378c  add     rsp, 20h
0x180003790  pop     rdi
0x180003791  retn
```
