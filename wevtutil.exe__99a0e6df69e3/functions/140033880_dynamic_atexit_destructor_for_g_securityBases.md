# _dynamic_atexit_destructor_for__g_securityBases__

- ea: `0x140033880`
- end: `0x1400338d8`
- name: `_dynamic_atexit_destructor_for__g_securityBases__`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140015848`
- `0x140033880`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400338c7`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1400338a7`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1400338a7`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_securityBases__()
{
  WINBOOL v0; // [rsp+30h] [rbp+8h] BYREF
  LazySecurityBases *v1; // [rsp+38h] [rbp+10h] BYREF

  v0 = 0;
  v1 = 0;
  InitOnceBeginInitialize(&stru_140042630, 0, &v0, (LPVOID *)&v1);
  if ( v1 )
    LazySecurityBases::~LazySecurityBases(v1);
  else
    InitOnceComplete(&stru_140042630, 0, 0);
}

```

## disassembly

```asm
0x140033880  mov     rax, rsp
0x140033883  sub     rsp, 28h
0x140033887  lea     r9, [rax+10h]; lpContext
0x14003388b  mov     dword ptr [rax+8], 0
0x140033892  lea     r8, [rax+8]; fPending
0x140033896  mov     qword ptr [rax+10h], 0
0x14003389e  xor     edx, edx; dwFlags
0x1400338a0  lea     rcx, stru_140042630; lpInitOnce
0x1400338a7  call    cs:__imp_InitOnceBeginInitialize
0x1400338ad  mov     rcx, [rsp+28h+arg_8]; this
0x1400338b2  test    rcx, rcx
0x1400338b5  jnz     short loc_1400338CE
0x1400338b7  xor     r8d, r8d
0x1400338ba  lea     rcx, stru_140042630
0x1400338c1  xor     edx, edx
0x1400338c3  add     rsp, 28h
0x1400338c7  jmp     cs:__imp_InitOnceComplete
0x1400338ce  call    ??1LazySecurityBases@@QEAA@XZ; LazySecurityBases::~LazySecurityBases(void)
0x1400338d3  add     rsp, 28h
0x1400338d7  retn
```
