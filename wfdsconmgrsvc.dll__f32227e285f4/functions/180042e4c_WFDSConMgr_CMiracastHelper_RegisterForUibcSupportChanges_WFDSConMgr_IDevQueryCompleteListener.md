# WFDSConMgr::CMiracastHelper::RegisterForUibcSupportChanges(WFDSConMgr::IDevQueryCompleteListener *)

- ea: `0x180042e4c`
- end: `0x180042f8a`
- name: `?RegisterForUibcSupportChanges@CMiracastHelper@WFDSConMgr@@QEAA?AV?$unique_ptr@VCUibcSupportRegistration@CMiracastHelper@WFDSConMgr@@U?$default_delete@VCUibcSupportRegistration@CMiracastHelper@WFDSConMgr@@@std@@@std@@PEAVIDevQueryCompleteListener@2@@Z`
- size: `318`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003e934`

## callees

- `0x18000421c`
- `0x18000475c`
- `0x180004ca8`
- `0x1800059c0`
- `0x180006e6c`
- `0x180024d50`
- `0x180028d00`
- `0x1800420cc`
- `0x180042e4c`
- `0x180043f30`
- `0x18005c888`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042f6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042f6c`

## string_xrefs

- `0x180042e87`: `Listener already registered`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall WFDSConMgr::CMiracastHelper::RegisterForUibcSupportChanges(
        WFDSConMgr::CDevQueryHelper **a1,
        _QWORD *a2,
        struct WFDSConMgr::IDevQueryCompleteListener *a3)
{
  _QWORD *v6; // rax
  __int64 v7; // rax
  _QWORD *v8; // rbx
  void *v9; // rsi
  std::_Ref_count_base *v10; // r8
  _QWORD v12[2]; // [rsp+38h] [rbp-28h] BYREF
  _BYTE v13[8]; // [rsp+48h] [rbp-18h] BYREF
  std::_Ref_count_base *v14; // [rsp+50h] [rbp-10h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+80h] [rbp+20h] BYREF
  void *v16; // [rsp+98h] [rbp+38h]

  WFDSConMgr::CriticalSection::Lock(a1 + 13, &lpCriticalSection);
  if ( a1[11] )
    WFDSConMgr::CException::Throw(
      159,
      "WFDSConMgr::CMiracastHelper::RegisterForUibcSupportChanges",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\miracasthelper.cpp",
      207,
      L"Listener already registered",
      a1);
  v6 = std::shared_ptr<WFDSConMgr::IConfigHelper>::shared_ptr<WFDSConMgr::IConfigHelper>(v12, a1 + 5);
  v7 = WFDSConMgr::CMiracastUibcDevQueryHelper::Create(v13, v6, a1 + 24);
  std::shared_ptr<WFDSConMgr::CDevQueryHelper>::operator=(a1 + 11, v7);
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  WFDSConMgr::CDevQueryHelper::StartQuery(a1[11], a3, 0);
  v8 = (_QWORD *)std::enable_shared_from_this<WFDSConMgr::CMiracastHelper>::shared_from_this(a1 + 1, v13);
  v9 = operator new(0x10u);
  v16 = v9;
  v12[0] = *v8;
  v12[1] = v8[1];
  *v8 = 0;
  v8[1] = 0;
  std::weak_ptr<WFDSConMgr::CMiracastHelper>::weak_ptr<WFDSConMgr::CMiracastHelper>(v9, v12);
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  *a2 = v9;
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return a2;
}

```

## disassembly

```asm
0x180042e4c  mov     [rsp-18h+arg_8], rbx
0x180042e51  mov     [rsp-18h+arg_10], rsi
0x180042e56  push    rbp
0x180042e57  push    rdi
0x180042e58  push    r14
0x180042e5a  mov     rbp, rsp
0x180042e5d  sub     rsp, 60h
0x180042e61  mov     r14, r8
0x180042e64  mov     rdi, rdx
0x180042e67  mov     rbx, rcx
0x180042e6a  add     rcx, 68h ; 'h'
0x180042e6e  lea     rdx, [rbp+lpCriticalSection]
0x180042e72  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x180042e77  nop
0x180042e78  lea     rsi, [rbx+58h]
0x180042e7c  cmp     qword ptr [rsi], 0
0x180042e80  jz      short loc_180042EB2
0x180042e82  mov     [rsp+60h+var_38], rbx; void *
0x180042e87  lea     rax, aListenerAlread; "Listener already registered"
0x180042e8e  mov     [rsp+60h+var_40], rax; unsigned __int16 *
0x180042e93  mov     r9d, 1CFh; char
0x180042e99  lea     r8, aOnecoreuapNetW_20; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180042ea0  lea     rdx, aWfdsconmgrCmir_2; "WFDSConMgr::CMiracastHelper::RegisterFo"...
0x180042ea7  mov     ecx, 8007139Fh; char
0x180042eac  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180042eb2  lea     rdx, [rbx+28h]
0x180042eb6  lea     rcx, [rbp+var_28]
0x180042eba  call    ??0?$shared_ptr@VIConfigHelper@WFDSConMgr@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<WFDSConMgr::IConfigHelper>::shared_ptr<WFDSConMgr::IConfigHelper>(std::shared_ptr<WFDSConMgr::IConfigHelper> const &)
0x180042ebf  lea     r8, [rbx+0C0h]
0x180042ec6  mov     rdx, rax
0x180042ec9  lea     rcx, [rbp+var_18]
0x180042ecd  call    ?Create@CMiracastUibcDevQueryHelper@WFDSConMgr@@SA?AV?$shared_ptr@VCDevQueryHelper@WFDSConMgr@@@std@@V?$shared_ptr@VCDevQueryShim@WFDSConMgr@@@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; WFDSConMgr::CMiracastUibcDevQueryHelper::Create(std::shared_ptr<WFDSConMgr::CDevQueryShim>,std::wstring const &)
0x180042ed2  mov     rdx, rax
0x180042ed5  mov     rcx, rsi
0x180042ed8  call    ??4?$shared_ptr@VCDevQueryHelper@WFDSConMgr@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<WFDSConMgr::CDevQueryHelper>::operator=(std::shared_ptr<WFDSConMgr::CDevQueryHelper> &&)
0x180042edd  mov     rcx, [rbp+var_10]; this
0x180042ee1  test    rcx, rcx
0x180042ee4  jz      short loc_180042EEB
0x180042ee6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180042eeb  xor     r8d, r8d; bool
0x180042eee  mov     rdx, r14; struct WFDSConMgr::IDevQueryCompleteListener *
0x180042ef1  mov     rcx, [rsi]; this
0x180042ef4  call    ?StartQuery@CDevQueryHelper@WFDSConMgr@@QEAAXPEAVIDevQueryCompleteListener@2@_N@Z; WFDSConMgr::CDevQueryHelper::StartQuery(WFDSConMgr::IDevQueryCompleteListener *,bool)
0x180042ef9  lea     rcx, [rbx+8]
0x180042efd  lea     rdx, [rbp+var_18]
0x180042f01  call    ?shared_from_this@?$enable_shared_from_this@VCMiracastHelper@WFDSConMgr@@@std@@QEAA?AV?$shared_ptr@VCMiracastHelper@WFDSConMgr@@@2@XZ; std::enable_shared_from_this<WFDSConMgr::CMiracastHelper>::shared_from_this(void)
0x180042f06  mov     rbx, rax
0x180042f09  mov     ecx, 10h; Size
0x180042f0e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180042f13  mov     rsi, rax
0x180042f16  mov     [rbp+arg_18], rax
0x180042f1a  mov     rcx, [rbx]
0x180042f1d  mov     [rbp+var_28], rcx
0x180042f21  mov     r8, [rbx+8]
0x180042f25  mov     [rbp+var_20], r8
0x180042f29  mov     qword ptr [rbx], 0
0x180042f30  mov     qword ptr [rbx+8], 0
0x180042f38  lea     rdx, [rbp+var_28]
0x180042f3c  mov     rcx, rax
0x180042f3f  call    ??$?0VCMiracastHelper@WFDSConMgr@@$0A@@?$weak_ptr@VCMiracastHelper@WFDSConMgr@@@std@@QEAA@AEBV?$shared_ptr@VCMiracastHelper@WFDSConMgr@@@1@@Z; std::weak_ptr<WFDSConMgr::CMiracastHelper>::weak_ptr<WFDSConMgr::CMiracastHelper>(std::shared_ptr<WFDSConMgr::CMiracastHelper> const &)
0x180042f44  test    r8, r8
0x180042f47  jz      short loc_180042F51
0x180042f49  mov     rcx, r8; this
0x180042f4c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180042f51  mov     [rdi], rsi
0x180042f54  mov     rcx, [rbp+var_10]; this
0x180042f58  test    rcx, rcx
0x180042f5b  jz      short loc_180042F63
0x180042f5d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180042f62  nop
0x180042f63  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180042f67  test    rcx, rcx
0x180042f6a  jz      short loc_180042F72
0x180042f6c  call    cs:__imp_LeaveCriticalSection
0x180042f72  mov     rax, rdi
0x180042f75  lea     r11, [rsp+60h+var_s0]
0x180042f7a  mov     rbx, [r11+28h]
0x180042f7e  mov     rsi, [r11+30h]
0x180042f82  mov     rsp, r11
0x180042f85  pop     r14
0x180042f87  pop     rdi
0x180042f88  pop     rbp
0x180042f89  retn
```
