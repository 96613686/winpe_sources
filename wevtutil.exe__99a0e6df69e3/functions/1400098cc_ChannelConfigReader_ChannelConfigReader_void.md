# ChannelConfigReader::~ChannelConfigReader(void)

- ea: `0x1400098cc`
- end: `0x14000993a`
- name: `??1ChannelConfigReader@@QEAA@XZ`
- size: `110`
- prototype: `void __fastcall(ChannelConfigReader *__hidden this)`
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14001d828`
- `0x14002a9b0`
- `0x14002d8e4`
- `0x14002daf0`
- `0x14002ddb0`
- `0x14002e018`
- `0x140032c81`
- `0x1400336a9`
- `0x140033755`
- `0x14003379c`

## callees

- `0x1400098cc`
- `0x14001b1dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400098fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400098fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400098ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400098ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000990c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000991b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140009929`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000990c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000991b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140009929`

## pseudocode

```c
void __fastcall ChannelConfigReader::~ChannelConfigReader(ChannelConfigReader *this)
{
  char *v2; // rdi
  HANDLE ProcessHeap; // rax
  HKEY v4; // rcx
  HKEY v5; // rcx

  utl::_OptionalData1<ChannelPolicy,0>::~_OptionalData1<ChannelPolicy,0>((char *)this + 64);
  v2 = (char *)*((_QWORD *)this + 4);
  if ( v2 != (char *)this + 48 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  v4 = (HKEY)*((_QWORD *)this + 2);
  if ( v4 )
    RegCloseKey(v4);
  v5 = (HKEY)*((_QWORD *)this + 1);
  if ( v5 )
    RegCloseKey(v5);
  if ( *(_QWORD *)this )
    RegCloseKey(*(HKEY *)this);
}

```

## disassembly

```asm
0x1400098cc  mov     [rsp+arg_0], rbx
0x1400098d1  push    rdi
0x1400098d2  sub     rsp, 20h
0x1400098d6  mov     rbx, rcx
0x1400098d9  add     rcx, 40h ; '@'
0x1400098dd  call    ??1?$_OptionalData1@VChannelPolicy@@$0A@@utl@@QEAA@XZ; utl::_OptionalData1<ChannelPolicy,0>::~_OptionalData1<ChannelPolicy,0>(void)
0x1400098e2  mov     rdi, [rbx+20h]
0x1400098e6  lea     rax, [rbx+30h]
0x1400098ea  cmp     rdi, rax
0x1400098ed  jz      short loc_140009903
0x1400098ef  call    cs:__imp_GetProcessHeap
0x1400098f5  mov     r8, rdi; lpMem
0x1400098f8  xor     edx, edx; dwFlags
0x1400098fa  mov     rcx, rax; hHeap
0x1400098fd  call    cs:__imp_HeapFree
0x140009903  mov     rcx, [rbx+10h]; hKey
0x140009907  test    rcx, rcx
0x14000990a  jz      short loc_140009912
0x14000990c  call    cs:__imp_RegCloseKey
0x140009912  mov     rcx, [rbx+8]; hKey
0x140009916  test    rcx, rcx
0x140009919  jz      short loc_140009921
0x14000991b  call    cs:__imp_RegCloseKey
0x140009921  mov     rcx, [rbx]; hKey
0x140009924  test    rcx, rcx
0x140009927  jz      short loc_14000992F
0x140009929  call    cs:__imp_RegCloseKey
0x14000992f  mov     rbx, [rsp+28h+arg_0]
0x140009934  add     rsp, 20h
0x140009938  pop     rdi
0x140009939  retn
```
