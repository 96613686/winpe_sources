# PerfCache::~PerfCache(void)

- ea: `0x18000ea34`
- end: `0x18000ea9b`
- name: `??1PerfCache@@UEAA@XZ`
- size: `103`
- prototype: `void __fastcall(PerfCache *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000ec80`
- `0x18000fae8`
- `0x180016ac0`

## callees

- `0x1800087f0`
- `0x18000e9f4`
- `0x18000ea34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ea60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ea60`

## pseudocode

```c
void __fastcall PerfCache::~PerfCache(PerfCache *this)
{
  HKEY v2; // rcx

  *(_QWORD *)this = &PerfCache::`vftable';
  v2 = (HKEY)*((_QWORD *)this + 45);
  if ( v2 && v2 != HKEY_PERFORMANCE_DATA )
    RegCloseKey(v2);
  TString::Empty((PerfCache *)((char *)this + 368));
  PerfBuff::~PerfBuff((PerfCache *)((char *)this + 184));
  PerfBuff::~PerfBuff((PerfCache *)((char *)this + 8));
  *(_QWORD *)this = &CObject::`vftable';
}

```

## disassembly

```asm
0x18000ea34  mov     [rsp+arg_0], rcx
0x18000ea39  push    rbx
0x18000ea3a  sub     rsp, 20h
0x18000ea3e  mov     rbx, rcx
0x18000ea41  lea     rax, ??_7PerfCache@@6B@; const PerfCache::`vftable'
0x18000ea48  mov     [rcx], rax
0x18000ea4b  mov     rcx, [rcx+168h]; hKey
0x18000ea52  test    rcx, rcx
0x18000ea55  jz      short loc_18000EA67
0x18000ea57  cmp     rcx, 0FFFFFFFF80000004h
0x18000ea5e  jz      short loc_18000EA67
0x18000ea60  call    cs:__imp_RegCloseKey
0x18000ea66  nop
0x18000ea67  lea     rcx, [rbx+170h]; this
0x18000ea6e  call    ?Empty@TString@@QEAAXXZ; TString::Empty(void)
0x18000ea73  nop
0x18000ea74  lea     rcx, [rbx+0B8h]; this
0x18000ea7b  call    ??1PerfBuff@@UEAA@XZ; PerfBuff::~PerfBuff(void)
0x18000ea80  nop
0x18000ea81  lea     rcx, [rbx+8]; this
0x18000ea85  call    ??1PerfBuff@@UEAA@XZ; PerfBuff::~PerfBuff(void)
0x18000ea8a  nop
0x18000ea8b  lea     rax, ??_7CObject@@6B@; const CObject::`vftable'
0x18000ea92  mov     [rbx], rax
0x18000ea95  add     rsp, 20h
0x18000ea99  pop     rbx
0x18000ea9a  retn
```
