# CSFPIntegrityCheckAndRepair::~CSFPIntegrityCheckAndRepair(void)

- ea: `0x180002694`
- end: `0x18000274f`
- name: `??1CSFPIntegrityCheckAndRepair@@QEAA@XZ`
- size: `187`
- prototype: `void __fastcall(CSFPIntegrityCheckAndRepair *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800062d0`

## callees

- `0x180001de0`
- `0x180002694`
- `0x180002758`
- `0x180002794`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800026cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002702`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800026cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002702`

## pseudocode

```c
void __fastcall CSFPIntegrityCheckAndRepair::~CSFPIntegrityCheckAndRepair(CSFPIntegrityCheckAndRepair *this)
{
  HKEY v2; // rcx
  __int64 v3; // rcx
  OFFLINE_REGISTRY_KEY *v4; // rbx
  HKEY v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rsi

  *(_QWORD *)this = &CSFPIntegrityCheckAndRepair::`vftable';
  if ( qword_18002B8C0 )
    qword_18002B8C0();
  v2 = (HKEY)*((_QWORD *)this + 25);
  if ( v2 )
    RegCloseKey(v2);
  v3 = *((_QWORD *)this + 23);
  *((_DWORD *)this + 48) = 0;
  if ( v3 )
    operator delete((void *)(v3 - 8));
  v4 = (CSFPIntegrityCheckAndRepair *)((char *)this + 160);
  v5 = (HKEY)*((_QWORD *)this + 22);
  if ( v5 )
    RegCloseKey(v5);
  v6 = *(_QWORD *)v4;
  *((_DWORD *)this + 42) = 0;
  if ( v6 )
    operator delete((void *)(v6 - 8));
  v7 = 6;
  do
  {
    v4 = (OFFLINE_REGISTRY_KEY *)((char *)v4 - 24);
    OFFLINE_REGISTRY_KEY::~OFFLINE_REGISTRY_KEY(v4);
    --v7;
  }
  while ( v7 );
  LogAdapter::WdsLoader::~WdsLoader((CSFPIntegrityCheckAndRepair *)((char *)this + 8));
}

```

## disassembly

```asm
0x180002694  mov     [rsp+arg_0], rbx
0x180002699  mov     [rsp+arg_8], rsi
0x18000269e  push    rdi
0x18000269f  sub     rsp, 20h
0x1800026a3  lea     rax, ??_7CSFPIntegrityCheckAndRepair@@6B@; const CSFPIntegrityCheckAndRepair::`vftable'
0x1800026aa  mov     rdi, rcx
0x1800026ad  mov     [rcx], rax
0x1800026b0  mov     rax, cs:qword_18002B8C0
0x1800026b7  test    rax, rax
0x1800026ba  jz      short loc_1800026C1
0x1800026bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026c1  mov     rcx, [rdi+0C8h]; hKey
0x1800026c8  test    rcx, rcx
0x1800026cb  jz      short loc_1800026D3
0x1800026cd  call    cs:__imp_RegCloseKey
0x1800026d3  mov     rcx, [rdi+0B8h]
0x1800026da  mov     dword ptr [rdi+0C0h], 0
0x1800026e4  test    rcx, rcx
0x1800026e7  jz      short loc_1800026F2
0x1800026e9  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800026ed  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800026f2  lea     rbx, [rdi+0A0h]
0x1800026f9  mov     rcx, [rbx+10h]; hKey
0x1800026fd  test    rcx, rcx
0x180002700  jz      short loc_180002708
0x180002702  call    cs:__imp_RegCloseKey
0x180002708  mov     rcx, [rbx]
0x18000270b  mov     dword ptr [rbx+8], 0
0x180002712  test    rcx, rcx
0x180002715  jz      short loc_180002720
0x180002717  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x18000271b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002720  mov     esi, 6
0x180002725  sub     rbx, 18h
0x180002729  mov     rcx, rbx; this
0x18000272c  call    ??1OFFLINE_REGISTRY_KEY@@QEAA@XZ; OFFLINE_REGISTRY_KEY::~OFFLINE_REGISTRY_KEY(void)
0x180002731  sub     rsi, 1
0x180002735  jnz     short loc_180002725
0x180002737  lea     rcx, [rdi+8]; this
0x18000273b  mov     rbx, [rsp+28h+arg_0]
0x180002740  mov     rsi, [rsp+28h+arg_8]
0x180002745  add     rsp, 20h
0x180002749  pop     rdi
0x18000274a  jmp     ??1WdsLoader@LogAdapter@@QEAA@XZ; LogAdapter::WdsLoader::~WdsLoader(void)
```
