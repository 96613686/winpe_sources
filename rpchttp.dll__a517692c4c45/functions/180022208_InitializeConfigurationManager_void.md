# InitializeConfigurationManager(void)

- ea: `0x180022208`
- end: `0x1800222ae`
- name: `?InitializeConfigurationManager@@YAJXZ`
- size: `166`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001fc58`

## callees

- `0x1800220f4`
- `0x180022208`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18002228a`
- `ntdll!RtlDeleteCriticalSection` at `0x18002228a`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180022242`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180022242`
- `RPCRT4!I_RpcFree` at `0x180022293`
- `RPCRT4!I_RpcFree` at `0x180022293`
- `RPCRT4!I_RpcAllocate` at `0x18002222c`
- `RPCRT4!I_RpcAllocate` at `0x18002222c`

## pseudocode

```c
__int64 InitializeConfigurationManager(void)
{
  struct _RTL_CRITICAL_SECTION *v1; // rax
  signed __int64 v2; // rbx
  LB_CONFIGURATION_MANAGER *v3; // rcx

  if ( g_pConfigurationManager && LODWORD(g_pConfigurationManager[1].DebugInfo) )
    return 0;
  v1 = (struct _RTL_CRITICAL_SECTION *)I_RpcAllocate(0x70u);
  v2 = (signed __int64)v1;
  if ( !v1 )
    return 14;
  RtlInitializeCriticalSectionAndSpinCount(v1, 0xBB8u);
  v3 = (LB_CONFIGURATION_MANAGER *)(v2 + 48);
  *(_DWORD *)(v2 + 40) = 0;
  *(_QWORD *)(v2 + 56) = v2 + 48;
  *(_QWORD *)(v2 + 48) = v2 + 48;
  *(_QWORD *)(v2 + 64) = 0;
  *(_QWORD *)(v2 + 72) = 20000;
  *(_QWORD *)(v2 + 96) = 0;
  *(_QWORD *)(v2 + 104) = 0;
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_pConfigurationManager, v2, 0) )
  {
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)v2);
    I_RpcFree((void *)v2);
  }
  return LB_CONFIGURATION_MANAGER::Initialize(v3);
}

```

## disassembly

```asm
0x180022208  push    rbx
0x18002220a  sub     rsp, 20h
0x18002220e  mov     rax, cs:?g_pConfigurationManager@@3PEAVLB_CONFIGURATION_MANAGER@@EA; LB_CONFIGURATION_MANAGER * g_pConfigurationManager
0x180022215  test    rax, rax
0x180022218  jz      short loc_180022227
0x18002221a  cmp     dword ptr [rax+28h], 0
0x18002221e  jz      short loc_180022227
0x180022220  xor     eax, eax
0x180022222  jmp     loc_1800222A8
0x180022227  mov     ecx, 70h ; 'p'; Size
0x18002222c  call    cs:__imp_I_RpcAllocate
0x180022232  mov     rbx, rax
0x180022235  test    rax, rax
0x180022238  jz      short loc_1800222A3
0x18002223a  mov     edx, 0BB8h; SpinCount
0x18002223f  mov     rcx, rax; CriticalSection
0x180022242  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x180022248  lea     rcx, [rbx+30h]
0x18002224c  mov     dword ptr [rbx+28h], 0
0x180022253  mov     [rcx+8], rcx
0x180022257  xor     eax, eax
0x180022259  mov     [rcx], rcx
0x18002225c  mov     qword ptr [rbx+40h], 0
0x180022264  mov     qword ptr [rbx+48h], 4E20h
0x18002226c  mov     qword ptr [rbx+60h], 0
0x180022274  mov     qword ptr [rbx+68h], 0
0x18002227c  lock cmpxchg cs:?g_pConfigurationManager@@3PEAVLB_CONFIGURATION_MANAGER@@EA, rbx; LB_CONFIGURATION_MANAGER * g_pConfigurationManager
0x180022285  jz      short loc_180022299
0x180022287  mov     rcx, rbx; CriticalSection
0x18002228a  call    cs:__imp_RtlDeleteCriticalSection
0x180022290  mov     rcx, rbx; Object
0x180022293  call    cs:__imp_I_RpcFree
0x180022299  add     rsp, 20h
0x18002229d  pop     rbx
0x18002229e  jmp     ?Initialize@LB_CONFIGURATION_MANAGER@@QEAAJXZ; LB_CONFIGURATION_MANAGER::Initialize(void)
0x1800222a3  mov     eax, 0Eh
0x1800222a8  add     rsp, 20h
0x1800222ac  pop     rbx
0x1800222ad  retn
```
