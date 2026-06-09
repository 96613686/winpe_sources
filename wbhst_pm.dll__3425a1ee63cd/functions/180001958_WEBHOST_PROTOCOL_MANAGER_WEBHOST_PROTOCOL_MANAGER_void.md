# WEBHOST_PROTOCOL_MANAGER::~WEBHOST_PROTOCOL_MANAGER(void)

- ea: `0x180001958`
- end: `0x180001a83`
- name: `??1WEBHOST_PROTOCOL_MANAGER@@QEAA@XZ`
- size: `299`
- prototype: `void __fastcall(WEBHOST_PROTOCOL_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800025e0`

## callees

- `0x180001958`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800019c1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800019c1`

## pseudocode

```c
void __fastcall WEBHOST_PROTOCOL_MANAGER::~WEBHOST_PROTOCOL_MANAGER(WEBHOST_PROTOCOL_MANAGER *this)
{
  bool v1; // zf
  HMODULE v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx

  v1 = *((_QWORD *)this + 8) == 0;
  *(_QWORD *)this = &WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IProtocolManager'};
  *((_DWORD *)this + 12) = 1483761783;
  *((_QWORD *)this + 1) = &WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IPmCustomActions'};
  *((_QWORD *)this + 2) = &WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IPmHealthAndIdleMonitor'};
  *((_QWORD *)this + 3) = &WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IPmListenerChannelManager'};
  *((_QWORD *)this + 4) = &WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IPmApplicationPreload'};
  *((_QWORD *)this + 5) = &WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IPmIdleTimeOutAction'};
  if ( !v1 )
    *((_QWORD *)this + 8) = 0;
  v3 = (HMODULE)*((_QWORD *)this + 7);
  if ( v3 )
  {
    FreeLibrary(v3);
    *((_QWORD *)this + 7) = 0;
  }
  v4 = *((_QWORD *)this + 12);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 12) = 0;
  }
  v5 = *((_QWORD *)this + 10);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 10) = 0;
  }
  v6 = *((_QWORD *)this + 14);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 14) = 0;
  }
  v7 = *((_QWORD *)this + 11);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 11) = 0;
  }
  v8 = *((_QWORD *)this + 9);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    *((_QWORD *)this + 9) = 0;
  }
  v9 = *((_QWORD *)this + 13);
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)this + 13) = 0;
  }
}

```

## disassembly

```asm
0x180001958  push    rbx
0x18000195a  sub     rsp, 20h
0x18000195e  cmp     qword ptr [rcx+40h], 0
0x180001963  lea     rax, ??_7WEBHOST_PROTOCOL_MANAGER@@6BIProtocolManager@@@; const WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IProtocolManager'}
0x18000196a  mov     [rcx], rax
0x18000196d  mov     rbx, rcx
0x180001970  lea     rax, ??_7WEBHOST_PROTOCOL_MANAGER@@6BIPmCustomActions@@@; const WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IPmCustomActions'}
0x180001977  mov     dword ptr [rcx+30h], 58706877h
0x18000197e  mov     [rcx+8], rax
0x180001982  lea     rax, ??_7WEBHOST_PROTOCOL_MANAGER@@6BIPmHealthAndIdleMonitor@@@; const WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IPmHealthAndIdleMonitor'}
0x180001989  mov     [rcx+10h], rax
0x18000198d  lea     rax, ??_7WEBHOST_PROTOCOL_MANAGER@@6BIPmListenerChannelManager@@@; const WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IPmListenerChannelManager'}
0x180001994  mov     [rcx+18h], rax
0x180001998  lea     rax, ??_7WEBHOST_PROTOCOL_MANAGER@@6BIPmApplicationPreload@@@; const WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IPmApplicationPreload'}
0x18000199f  mov     [rcx+20h], rax
0x1800019a3  lea     rax, ??_7WEBHOST_PROTOCOL_MANAGER@@6BIPmIdleTimeOutAction@@@; const WEBHOST_PROTOCOL_MANAGER::`vftable'{for `IPmIdleTimeOutAction'}
0x1800019aa  mov     [rcx+28h], rax
0x1800019ae  jz      short loc_1800019B8
0x1800019b0  mov     qword ptr [rcx+40h], 0
0x1800019b8  mov     rcx, [rcx+38h]; hLibModule
0x1800019bc  test    rcx, rcx
0x1800019bf  jz      short loc_1800019CF
0x1800019c1  call    cs:__imp_FreeLibrary
0x1800019c7  mov     qword ptr [rbx+38h], 0
0x1800019cf  mov     rcx, [rbx+60h]
0x1800019d3  test    rcx, rcx
0x1800019d6  jz      short loc_1800019EC
0x1800019d8  mov     rax, [rcx]
0x1800019db  mov     rax, [rax+10h]
0x1800019df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019e4  mov     qword ptr [rbx+60h], 0
0x1800019ec  mov     rcx, [rbx+50h]
0x1800019f0  test    rcx, rcx
0x1800019f3  jz      short loc_180001A09
0x1800019f5  mov     rax, [rcx]
0x1800019f8  mov     rax, [rax+10h]
0x1800019fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a01  mov     qword ptr [rbx+50h], 0
0x180001a09  mov     rcx, [rbx+70h]
0x180001a0d  test    rcx, rcx
0x180001a10  jz      short loc_180001A26
0x180001a12  mov     rax, [rcx]
0x180001a15  mov     rax, [rax+10h]
0x180001a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a1e  mov     qword ptr [rbx+70h], 0
0x180001a26  mov     rcx, [rbx+58h]
0x180001a2a  test    rcx, rcx
0x180001a2d  jz      short loc_180001A43
0x180001a2f  mov     rax, [rcx]
0x180001a32  mov     rax, [rax+10h]
0x180001a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a3b  mov     qword ptr [rbx+58h], 0
0x180001a43  mov     rcx, [rbx+48h]
0x180001a47  test    rcx, rcx
0x180001a4a  jz      short loc_180001A60
0x180001a4c  mov     rax, [rcx]
0x180001a4f  mov     rax, [rax+10h]
0x180001a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a58  mov     qword ptr [rbx+48h], 0
0x180001a60  mov     rcx, [rbx+68h]
0x180001a64  test    rcx, rcx
0x180001a67  jz      short loc_180001A7D
0x180001a69  mov     rax, [rcx]
0x180001a6c  mov     rax, [rax+10h]
0x180001a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a75  mov     qword ptr [rbx+68h], 0
0x180001a7d  add     rsp, 20h
0x180001a81  pop     rbx
0x180001a82  retn
```
