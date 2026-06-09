# CompatibilityAdapter::GetAdapter(void)

- ea: `0x180005c10`
- end: `0x180005c4d`
- name: `?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ`
- size: `61`
- prototype: `struct CompatibilityAdapter *(void)`
- caller_count: `20`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800036a0`
- `0x180004a40`
- `0x1800066c0`
- `0x18000dca8`
- `0x1800111e0`
- `0x180011600`
- `0x180012360`
- `0x180012a70`
- `0x180012f5c`
- `0x1800130c0`
- `0x180013820`
- `0x18001394c`
- `0x180013a80`
- `0x1800148d0`
- `0x180016040`
- `0x180016620`
- `0x180016ab0`
- `0x180016bf0`
- `0x180016ea0`
- `0x1800174c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005c1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005c1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005c37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005c37`

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
0x180005c10  push    rbx
0x180005c12  sub     rsp, 20h
0x180005c16  lea     rcx, ?s_csAdapterAccess@CompatibilityAdapter@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180005c1d  call    cs:__imp_EnterCriticalSection
0x180005c24  nop     dword ptr [rax+rax+00h]
0x180005c29  mov     rbx, cs:?g_pAdapter@CompatibilityAdapter@@0PEAV1@EA; CompatibilityAdapter * CompatibilityAdapter::g_pAdapter
0x180005c30  lea     rcx, ?s_csAdapterAccess@CompatibilityAdapter@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180005c37  call    cs:__imp_LeaveCriticalSection
0x180005c3e  nop     dword ptr [rax+rax+00h]
0x180005c43  mov     rax, rbx
0x180005c46  add     rsp, 20h
0x180005c4a  pop     rbx
0x180005c4b  retn
```
