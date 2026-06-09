# CJsonParser::~CJsonParser(void)

- ea: `0x180019104`
- end: `0x18001913b`
- name: `??1CJsonParser@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(CJsonParser *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d620`

## callees

- `0x180019104`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180019112`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180019112`

## pseudocode

```c
void __fastcall CJsonParser::~CJsonParser(CJsonParser *this)
{
  __int64 v2; // rcx

  if ( *(_DWORD *)this )
    RoUninitialize();
  v2 = *((_QWORD *)this + 1);
  if ( v2 )
  {
    *((_QWORD *)this + 1) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
}

```

## disassembly

```asm
0x180019104  push    rbx
0x180019106  sub     rsp, 20h
0x18001910a  cmp     dword ptr [rcx], 0
0x18001910d  mov     rbx, rcx
0x180019110  jz      short loc_180019118
0x180019112  call    cs:__imp_RoUninitialize
0x180019118  mov     rcx, [rbx+8]
0x18001911c  test    rcx, rcx
0x18001911f  jz      short loc_180019135
0x180019121  mov     qword ptr [rbx+8], 0
0x180019129  mov     rax, [rcx]
0x18001912c  mov     rax, [rax+10h]
0x180019130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019135  add     rsp, 20h
0x180019139  pop     rbx
0x18001913a  retn
```
