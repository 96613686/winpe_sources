# CompatibilityAdapter::GetAdapter(void)

- ea: `0x1800058f0`
- end: `0x180005920`
- name: `?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ`
- size: `48`
- prototype: `struct CompatibilityAdapter *(void)`
- caller_count: `20`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180003500`
- `0x180004820`
- `0x1800062d0`
- `0x18000d414`
- `0x180010750`
- `0x180010bd0`
- `0x180011880`
- `0x180011f40`
- `0x180012408`
- `0x180012560`
- `0x180012c50`
- `0x180012d74`
- `0x180012ea0`
- `0x180013c80`
- `0x180015280`
- `0x1800157e0`
- `0x180015c50`
- `0x180015d80`
- `0x180016020`
- `0x1800165f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800058fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800058fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005911`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005911`

## pseudocode

```c
struct CompatibilityAdapter *CompatibilityAdapter::GetAdapter(void)
{
  CompatibilityAdapter *v0; // rbx

  EnterCriticalSection(&CompatibilityAdapter::s_csAdapterAccess);
  v0 = CompatibilityAdapter::g_pAdapter;
  LeaveCriticalSection(&CompatibilityAdapter::s_csAdapterAccess);
  return v0;
}

```

## disassembly

```asm
0x1800058f0  push    rbx
0x1800058f2  sub     rsp, 20h
0x1800058f6  lea     rcx, ?s_csAdapterAccess@CompatibilityAdapter@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800058fd  call    cs:__imp_EnterCriticalSection
0x180005903  mov     rbx, cs:?g_pAdapter@CompatibilityAdapter@@0PEAV1@EA; CompatibilityAdapter * CompatibilityAdapter::g_pAdapter
0x18000590a  lea     rcx, ?s_csAdapterAccess@CompatibilityAdapter@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180005911  call    cs:__imp_LeaveCriticalSection
0x180005917  mov     rax, rbx
0x18000591a  add     rsp, 20h
0x18000591e  pop     rbx
0x18000591f  retn
```
