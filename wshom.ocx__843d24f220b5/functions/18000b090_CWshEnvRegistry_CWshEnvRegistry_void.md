# CWshEnvRegistry::~CWshEnvRegistry(void)

- ea: `0x18000b090`
- end: `0x18000b0d5`
- name: `??1CWshEnvRegistry@@EEAA@XZ`
- size: `69`
- prototype: `void __fastcall(CWshEnvRegistry *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18000b158`

## callees

- `0x180001f30`
- `0x18000b090`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000b0c2`
- `ADVAPI32!RegCloseKey` at `0x18000b0c2`

## pseudocode

```c
void __fastcall CWshEnvRegistry::~CWshEnvRegistry(CWshEnvRegistry *this)
{
  CDispatch *v1; // rbx
  HKEY v2; // rcx

  *(_QWORD *)this = &CWshEnvRegistry::`vftable'{for `IWshEnvironment'};
  v1 = (CWshEnvRegistry *)((char *)this + 16);
  *((_QWORD *)this + 1) = &CWshEnvProcess::`vftable'{for `IProvideClassInfo'};
  v2 = (HKEY)*((_QWORD *)this + 9);
  *(_QWORD *)v1 = &CWshEnvRegistry::`vftable'{for `CDispatch'};
  if ( v2 )
    RegCloseKey(v2);
  CDispatch::~CDispatch(v1);
}

```

## disassembly

```asm
0x18000b090  push    rbx
0x18000b092  sub     rsp, 20h
0x18000b096  lea     rax, ??_7CWshEnvRegistry@@6BIWshEnvironment@@@; const CWshEnvRegistry::`vftable'{for `IWshEnvironment'}
0x18000b09d  mov     [rcx], rax
0x18000b0a0  lea     rbx, [rcx+10h]
0x18000b0a4  lea     rax, ??_7CWshEnvProcess@@6BIProvideClassInfo@@@; const CWshEnvProcess::`vftable'{for `IProvideClassInfo'}
0x18000b0ab  mov     [rcx+8], rax
0x18000b0af  lea     rax, ??_7CWshEnvRegistry@@6BCDispatch@@@; const CWshEnvRegistry::`vftable'{for `CDispatch'}
0x18000b0b6  mov     rcx, [rcx+48h]; hKey
0x18000b0ba  mov     [rbx], rax
0x18000b0bd  test    rcx, rcx
0x18000b0c0  jz      short loc_18000B0C8
0x18000b0c2  call    cs:__imp_RegCloseKey
0x18000b0c8  mov     rcx, rbx; this
0x18000b0cb  add     rsp, 20h
0x18000b0cf  pop     rbx
0x18000b0d0  jmp     ??1CDispatch@@UEAA@XZ; CDispatch::~CDispatch(void)
```
