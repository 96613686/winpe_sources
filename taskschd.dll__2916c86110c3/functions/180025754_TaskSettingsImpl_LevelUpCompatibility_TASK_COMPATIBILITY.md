# TaskSettingsImpl::LevelUpCompatibility(_TASK_COMPATIBILITY)

- ea: `0x180025754`
- end: `0x1800257db`
- name: `?LevelUpCompatibility@TaskSettingsImpl@@QEAAJW4_TASK_COMPATIBILITY@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(TaskSettingsImpl *__hidden this, enum _TASK_COMPATIBILITY)`
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180024ba0`
- `0x180024e40`
- `0x180025640`
- `0x1800256d0`
- `0x18003d7b0`
- `0x18003d870`
- `0x18003f660`
- `0x18003f8a0`
- `0x18003f9e0`
- `0x1800413f0`
- `0x1800432dc`

## callees

- `0x180025754`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800257a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800257a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002578b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002578b`

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
0x180025754  mov     [rsp+arg_0], rbx
0x180025759  mov     [rsp+arg_10], rsi
0x18002575e  push    rdi
0x18002575f  push    r14
0x180025761  push    r15
0x180025763  sub     rsp, 30h
0x180025767  mov     r15d, edx
0x18002576a  mov     rdi, rcx
0x18002576d  xor     esi, esi
0x18002576f  mov     [rsp+48h+arg_8], esi
0x180025773  test    rcx, rcx
0x180025776  jz      short loc_1800257C2
0x180025778  lea     rbx, [rcx+10h]
0x18002577c  mov     rax, rbx
0x18002577f  test    rbx, rbx
0x180025782  jz      short loc_1800257C6
0x180025784  lea     r14, [rbx+8]
0x180025788  mov     rcx, r14; lpCriticalSection
0x18002578b  call    cs:__imp_EnterCriticalSection
0x180025791  mov     rax, rbx
0x180025794  cmp     [rdi+0ACh], r15d
0x18002579b  jl      short loc_1800257CC
0x18002579d  test    rax, rax
0x1800257a0  jz      short loc_1800257AC
0x1800257a2  mov     rcx, r14; lpCriticalSection
0x1800257a5  call    cs:__imp_LeaveCriticalSection
0x1800257ab  nop
0x1800257ac  mov     eax, esi
0x1800257ae  mov     rbx, [rsp+48h+arg_0]
0x1800257b3  mov     rsi, [rsp+48h+arg_10]
0x1800257b8  add     rsp, 30h
0x1800257bc  pop     r15
0x1800257be  pop     r14
0x1800257c0  pop     rdi
0x1800257c1  retn
0x1800257c2  xor     eax, eax
0x1800257c4  xor     ebx, ebx
0x1800257c6  lea     r14, [rbx+8]
0x1800257ca  jmp     short loc_180025794
0x1800257cc  mov     [rdi+0ACh], r15d
0x1800257d3  jmp     short loc_18002579D
0x1800257d5  mov     esi, [rsp+48h+arg_8]
0x1800257d9  jmp     short loc_1800257AC
```
