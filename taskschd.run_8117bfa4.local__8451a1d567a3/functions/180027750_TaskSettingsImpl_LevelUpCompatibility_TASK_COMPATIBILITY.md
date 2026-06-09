# TaskSettingsImpl::LevelUpCompatibility(_TASK_COMPATIBILITY)

- ea: `0x180027750`
- end: `0x1800277e4`
- name: `?LevelUpCompatibility@TaskSettingsImpl@@QEAAJW4_TASK_COMPATIBILITY@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(TaskSettingsImpl *__hidden this, enum _TASK_COMPATIBILITY)`
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026b60`
- `0x180026e20`
- `0x180027630`
- `0x1800276c0`
- `0x180040c80`
- `0x180040d40`
- `0x180042c30`
- `0x180042e70`
- `0x180042fb0`
- `0x180044b10`
- `0x180046ac8`

## callees

- `0x180027750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800277a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800277a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027787`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027787`

## pseudocode

```c
__int64 __fastcall TaskSettingsImpl::LevelUpCompatibility(TaskSettingsImpl *this, enum _TASK_COMPATIBILITY a2)
{
  char *v4; // rbx
  char *v5; // rax
  struct _RTL_CRITICAL_SECTION *v6; // r14

  if ( this )
  {
    v4 = (char *)this + 16;
    v5 = (char *)this + 16;
    if ( this != (TaskSettingsImpl *)-16LL )
    {
      v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
      v5 = v4;
      goto LABEL_4;
    }
  }
  else
  {
    v5 = 0;
    v4 = 0;
  }
  v6 = (struct _RTL_CRITICAL_SECTION *)(v4 + 8);
LABEL_4:
  if ( *((_DWORD *)this + 43) < a2 )
    *((_DWORD *)this + 43) = a2;
  if ( v5 )
    LeaveCriticalSection(v6);
  return 0;
}

```

## disassembly

```asm
0x180027750  mov     [rsp+arg_0], rbx
0x180027755  mov     [rsp+arg_10], rsi
0x18002775a  push    rdi
0x18002775b  push    r14
0x18002775d  push    r15
0x18002775f  sub     rsp, 30h
0x180027763  mov     r15d, edx
0x180027766  mov     rdi, rcx
0x180027769  xor     esi, esi
0x18002776b  mov     [rsp+48h+arg_8], esi
0x18002776f  test    rcx, rcx
0x180027772  jz      short loc_1800277CB
0x180027774  lea     rbx, [rcx+10h]
0x180027778  mov     rax, rbx
0x18002777b  test    rbx, rbx
0x18002777e  jz      short loc_1800277CF
0x180027780  lea     r14, [rbx+8]
0x180027784  mov     rcx, r14; lpCriticalSection
0x180027787  call    cs:__imp_EnterCriticalSection
0x18002778e  nop     dword ptr [rax+rax+00h]
0x180027793  mov     rax, rbx
0x180027796  cmp     [rdi+0ACh], r15d
0x18002779d  jl      short loc_1800277D5
0x18002779f  test    rax, rax
0x1800277a2  jz      short loc_1800277B4
0x1800277a4  mov     rcx, r14; lpCriticalSection
0x1800277a7  call    cs:__imp_LeaveCriticalSection
0x1800277ae  nop     dword ptr [rax+rax+00h]
0x1800277b3  nop
0x1800277b4  mov     eax, esi
0x1800277b6  mov     rbx, [rsp+48h+arg_0]
0x1800277bb  mov     rsi, [rsp+48h+arg_10]
0x1800277c0  add     rsp, 30h
0x1800277c4  pop     r15
0x1800277c6  pop     r14
0x1800277c8  pop     rdi
0x1800277c9  retn
0x1800277cb  xor     eax, eax
0x1800277cd  xor     ebx, ebx
0x1800277cf  lea     r14, [rbx+8]
0x1800277d3  jmp     short loc_180027796
0x1800277d5  mov     [rdi+0ACh], r15d
0x1800277dc  jmp     short loc_18002779F
0x1800277de  mov     esi, [rsp+48h+arg_8]
0x1800277e2  jmp     short loc_1800277B4
```
