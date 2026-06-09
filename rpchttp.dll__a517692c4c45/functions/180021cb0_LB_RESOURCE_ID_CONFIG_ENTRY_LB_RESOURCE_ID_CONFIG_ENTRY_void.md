# LB_RESOURCE_ID_CONFIG_ENTRY::~LB_RESOURCE_ID_CONFIG_ENTRY(void)

- ea: `0x180021cb0`
- end: `0x180021d51`
- name: `??1LB_RESOURCE_ID_CONFIG_ENTRY@@QEAA@XZ`
- size: `161`
- prototype: `void __fastcall(LB_RESOURCE_ID_CONFIG_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180021e20`

## callees

- `0x180021cb0`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180021d43`
- `ntdll!RtlLeaveCriticalSection` at `0x180021d0f`
- `ntdll!RtlLeaveCriticalSection` at `0x180021d0f`
- `ntdll!RtlEnterCriticalSection` at `0x180021ccb`
- `ntdll!RtlEnterCriticalSection` at `0x180021ccb`
- `RPCRT4!I_RpcFree` at `0x180021d2d`
- `RPCRT4!I_RpcFree` at `0x180021d2d`

## pseudocode

```c
void __fastcall LB_RESOURCE_ID_CONFIG_ENTRY::~LB_RESOURCE_ID_CONFIG_ENTRY(LB_RESOURCE_ID_CONFIG_ENTRY *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rcx
  LB_RESOURCE_ID_CONFIG_ENTRY **v3; // rax
  LB_RESOURCE_ID_CONFIG_ENTRY **v4; // rcx
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  void *v6; // rcx

  if ( *(_QWORD *)this )
  {
    v2 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 17);
    if ( v2 )
      RtlEnterCriticalSection(v2);
    v3 = *(LB_RESOURCE_ID_CONFIG_ENTRY ***)this;
    if ( *(_QWORD *)this )
    {
      v4 = (LB_RESOURCE_ID_CONFIG_ENTRY **)*((_QWORD *)this + 1);
      if ( v4 )
      {
        if ( v3[1] != this || *v4 != this )
          __fastfail(3u);
        *v4 = (LB_RESOURCE_ID_CONFIG_ENTRY *)v3;
        v3[1] = (LB_RESOURCE_ID_CONFIG_ENTRY *)v4;
        *(_QWORD *)this = 0;
        *((_QWORD *)this + 1) = 0;
      }
    }
    v5 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 17);
    if ( v5 )
      RtlLeaveCriticalSection(v5);
    *(_QWORD *)this = 0;
    *((_QWORD *)this + 1) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 14);
  if ( v6 )
    I_RpcFree(v6);
  _InterlockedDecrement(&AllocatedResourceConfigEntries);
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 48));
}

```

## disassembly

```asm
0x180021cb0  push    rbx
0x180021cb2  sub     rsp, 20h
0x180021cb6  cmp     qword ptr [rcx], 0
0x180021cba  mov     rbx, rcx
0x180021cbd  jz      short loc_180021D24
0x180021cbf  mov     rcx, [rcx+88h]; CriticalSection
0x180021cc6  test    rcx, rcx
0x180021cc9  jz      short loc_180021CD1
0x180021ccb  call    cs:__imp_RtlEnterCriticalSection
0x180021cd1  mov     rax, [rbx]
0x180021cd4  test    rax, rax
0x180021cd7  jz      short loc_180021D03
0x180021cd9  mov     rcx, [rbx+8]
0x180021cdd  test    rcx, rcx
0x180021ce0  jz      short loc_180021D03
0x180021ce2  cmp     [rax+8], rbx
0x180021ce6  jnz     short loc_180021D4A
0x180021ce8  cmp     [rcx], rbx
0x180021ceb  jnz     short loc_180021D4A
0x180021ced  mov     [rcx], rax
0x180021cf0  mov     [rax+8], rcx
0x180021cf4  mov     qword ptr [rbx], 0
0x180021cfb  mov     qword ptr [rbx+8], 0
0x180021d03  mov     rcx, [rbx+88h]; CriticalSection
0x180021d0a  test    rcx, rcx
0x180021d0d  jz      short loc_180021D15
0x180021d0f  call    cs:__imp_RtlLeaveCriticalSection
0x180021d15  mov     qword ptr [rbx], 0
0x180021d1c  mov     qword ptr [rbx+8], 0
0x180021d24  mov     rcx, [rbx+70h]; Object
0x180021d28  test    rcx, rcx
0x180021d2b  jz      short loc_180021D33
0x180021d2d  call    cs:__imp_I_RpcFree
0x180021d33  lock dec cs:?AllocatedResourceConfigEntries@@3JA; long AllocatedResourceConfigEntries
0x180021d3a  lea     rcx, [rbx+30h]
0x180021d3e  add     rsp, 20h
0x180021d42  pop     rbx
0x180021d43  jmp     cs:__imp_RtlDeleteCriticalSection
0x180021d4a  mov     ecx, 3
0x180021d4f  int     29h; Win8: RtlFailFast(ecx)
```
