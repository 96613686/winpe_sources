# CScalingInfoCache::~CScalingInfoCache(void)

- ea: `0x180049c9c`
- end: `0x180049d94`
- name: `??1CScalingInfoCache@@EEAA@XZ`
- size: `248`
- prototype: `void __fastcall(CScalingInfoCache *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180049c60`

## callees

- `0x1800279f4`
- `0x180049c9c`
- `0x180049d9c`
- `0x18004b5ec`
- `0x180068df0`
- `0x1800713e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049cf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049d47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049cf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049d47`

## pseudocode

```c
void __fastcall CScalingInfoCache::~CScalingInfoCache(LPVOID *this)
{
  unsigned __int64 *v2; // rdi
  unsigned __int64 i; // rsi
  unsigned int v4; // edx
  unsigned __int64 *v5; // rdi
  unsigned __int64 j; // rsi

  *this = &CScalingInfoCache::`vftable';
  CScalingInfoCache::_SubscribeToWnfNotifications((CScalingInfoCache *)this, 0);
  v2 = (unsigned __int64 *)(this + 16);
  if ( this[15] )
  {
    for ( i = 0; i < *v2; ++i )
      CScalingInfoCache::EVENT_REGISTRATION::~EVENT_REGISTRATION((CScalingInfoCache::EVENT_REGISTRATION *)((char *)this[15] + 16 * i));
    CoTaskMemFree(this[15]);
    this[15] = 0;
  }
  *v2 = 0;
  this[18] = 0;
  CTSimpleArray<CScalingInfoCache::MONITOR_SCALE_INFO,4294967294,CTPolicyCoTaskMem<CScalingInfoCache::MONITOR_SCALE_INFO>,CSimpleArrayStandardCompareHelper<CScalingInfoCache::MONITOR_SCALE_INFO>,CSimpleArrayStandardMergeHelper<CScalingInfoCache::MONITOR_SCALE_INFO>>::RemoveAll(this + 11);
  v5 = (unsigned __int64 *)(this + 8);
  if ( this[7] )
  {
    for ( j = 0; j < *v5; ++j )
      CScalingInfoCache::WINDOW_SCALE_INFO::`scalar deleting destructor'(
        (CScalingInfoCache::WINDOW_SCALE_INFO *)((char *)this[7] + 16 * j),
        v4);
    CoTaskMemFree(this[7]);
    this[7] = 0;
  }
  *v5 = 0;
  this[10] = 0;
  `eh vector destructor iterator'(
    this + 2,
    8u,
    3u,
    Microsoft::WRL::ComPtr<IObjectWithFileHandle>::~ComPtr<IObjectWithFileHandle>);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180049c9c  mov     [rsp+arg_0], rbx
0x180049ca1  mov     [rsp+arg_8], rsi
0x180049ca6  push    rdi
0x180049ca7  sub     rsp, 20h
0x180049cab  mov     rbx, rcx
0x180049cae  lea     rax, ??_7CScalingInfoCache@@6B@; const CScalingInfoCache::`vftable'
0x180049cb5  mov     [rcx], rax
0x180049cb8  xor     edx, edx; bool
0x180049cba  call    ?_SubscribeToWnfNotifications@CScalingInfoCache@@AEAAJ_N@Z; CScalingInfoCache::_SubscribeToWnfNotifications(bool)
0x180049cbf  lea     rdi, [rbx+80h]
0x180049cc6  cmp     qword ptr [rbx+78h], 0
0x180049ccb  jz      short loc_180049CFE
0x180049ccd  xor     esi, esi
0x180049ccf  cmp     [rdi], rsi
0x180049cd2  jbe     short loc_180049CEC
0x180049cd4  mov     rcx, rsi
0x180049cd7  shl     rcx, 4
0x180049cdb  add     rcx, [rbx+78h]; this
0x180049cdf  call    ??1EVENT_REGISTRATION@CScalingInfoCache@@QEAA@XZ; CScalingInfoCache::EVENT_REGISTRATION::~EVENT_REGISTRATION(void)
0x180049ce4  inc     rsi
0x180049ce7  cmp     rsi, [rdi]
0x180049cea  jb      short loc_180049CD4
0x180049cec  mov     rcx, [rbx+78h]; pv
0x180049cf0  call    cs:__imp_CoTaskMemFree
0x180049cf6  mov     qword ptr [rbx+78h], 0
0x180049cfe  mov     qword ptr [rdi], 0
0x180049d05  mov     qword ptr [rbx+90h], 0
0x180049d10  lea     rcx, [rbx+58h]
0x180049d14  call    ?RemoveAll@?$CTSimpleArray@UMONITOR_SCALE_INFO@CScalingInfoCache@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UMONITOR_SCALE_INFO@CScalingInfoCache@@@@V?$CSimpleArrayStandardCompareHelper@UMONITOR_SCALE_INFO@CScalingInfoCache@@@@V?$CSimpleArrayStandardMergeHelper@UMONITOR_SCALE_INFO@CScalingInfoCache@@@@@@QEAAXXZ; CTSimpleArray<CScalingInfoCache::MONITOR_SCALE_INFO,4294967294,CTPolicyCoTaskMem<CScalingInfoCache::MONITOR_SCALE_INFO>,CSimpleArrayStandardCompareHelper<CScalingInfoCache::MONITOR_SCALE_INFO>,CSimpleArrayStandardMergeHelper<CScalingInfoCache::MONITOR_SCALE_INFO>>::RemoveAll(void)
0x180049d19  lea     rdi, [rbx+40h]
0x180049d1d  cmp     qword ptr [rbx+38h], 0
0x180049d22  jz      short loc_180049D55
0x180049d24  xor     esi, esi
0x180049d26  cmp     [rdi], rsi
0x180049d29  jbe     short loc_180049D43
0x180049d2b  mov     rcx, rsi
0x180049d2e  shl     rcx, 4
0x180049d32  add     rcx, [rbx+38h]; this
0x180049d36  call    ??_GWINDOW_SCALE_INFO@CScalingInfoCache@@QEAAPEAXI@Z; CScalingInfoCache::WINDOW_SCALE_INFO::`scalar deleting destructor'(uint)
0x180049d3b  inc     rsi
0x180049d3e  cmp     rsi, [rdi]
0x180049d41  jb      short loc_180049D2B
0x180049d43  mov     rcx, [rbx+38h]; pv
0x180049d47  call    cs:__imp_CoTaskMemFree
0x180049d4d  mov     qword ptr [rbx+38h], 0
0x180049d55  mov     qword ptr [rdi], 0
0x180049d5c  mov     qword ptr [rbx+50h], 0
0x180049d64  lea     rcx, [rbx+10h]; void *
0x180049d68  lea     r9, ??1?$ComPtr@UIObjectWithFileHandle@@@WRL@Microsoft@@QEAA@XZ; void (*)(void *)
0x180049d6f  mov     edx, 8; unsigned __int64
0x180049d74  lea     r8d, [rdx-5]; unsigned __int64
0x180049d78  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180049d7d  mov     dword ptr [rbx+0Ch], 0C0000001h
0x180049d84  mov     rbx, [rsp+28h+arg_0]
0x180049d89  mov     rsi, [rsp+28h+arg_8]
0x180049d8e  add     rsp, 20h
0x180049d92  pop     rdi
0x180049d93  retn
```
