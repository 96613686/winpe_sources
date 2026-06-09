# WFDSConMgr::RPC::CClientContext::CClientContext(WFDSConMgr::RPC::CServer *,std::shared_ptr<WFDSConMgr::IImpersonationProvider>)

- ea: `0x180009e80`
- end: `0x180009faf`
- name: `??0CClientContext@RPC@WFDSConMgr@@QEAA@PEAVCServer@12@V?$shared_ptr@VIImpersonationProvider@WFDSConMgr@@@std@@@Z`
- size: `303`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180006974`

## callees

- `0x18000475c`
- `0x180004ca8`
- `0x180009ba8`
- `0x180009cb0`
- `0x180009e80`
- `0x18005c800`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180009ea6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180009ea6`

## string_xrefs

- `0x180009f23`: `Created client context without server pointer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WFDSConMgr::RPC::CClientContext::CClientContext(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v6; // r8
  std::_Ref_count_base *v7; // rcx

  *(_QWORD *)a1 = a1;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(a1 + 8), 0, 0);
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>();
  *(_QWORD *)(a1 + 88) = -1;
  *(_QWORD *)(a1 + 96) = a2;
  *(_BYTE *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  std::shared_ptr<WFDSConMgr::IConfigHelper>::shared_ptr<WFDSConMgr::IConfigHelper>((_QWORD *)(a1 + 136), a3);
  if ( !*(_QWORD *)(a1 + 96) )
    WFDSConMgr::CException::Throw(
      -2147024809,
      "WFDSConMgr::RPC::CClientContext::CClientContext",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\server\\src\\clientcontext.cpp",
      22,
      L"Created client context without server pointer");
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_a2095e9d95ef327a6cb68890677ecf94_Traceguids,
      a1,
      *(_QWORD *)a1,
      *v6);
  }
  v7 = (std::_Ref_count_base *)a3[1];
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
  return a1;
}

```

## disassembly

```asm
0x180009e80  mov     [rsp+arg_10], r8
0x180009e85  mov     [rsp+arg_0], rcx
0x180009e8a  push    rbx
0x180009e8b  push    rsi
0x180009e8c  push    rdi
0x180009e8d  sub     rsp, 30h
0x180009e91  mov     rsi, r8
0x180009e94  mov     rbx, rdx
0x180009e97  mov     rdi, rcx
0x180009e9a  mov     [rcx], rcx
0x180009e9d  add     rcx, 8; lpCriticalSection
0x180009ea1  xor     r8d, r8d; Flags
0x180009ea4  xor     edx, edx; dwSpinCount
0x180009ea6  call    cs:__imp_InitializeCriticalSectionEx
0x180009eac  nop
0x180009ead  lea     rcx, [rdi+30h]
0x180009eb1  mov     qword ptr [rcx], 0
0x180009eb8  mov     qword ptr [rcx+8], 0
0x180009ec0  mov     qword ptr [rcx+10h], 0
0x180009ec8  mov     qword ptr [rcx+18h], 0
0x180009ed0  mov     qword ptr [rcx+20h], 0
0x180009ed8  call    ??$_Alloc_proxy@V?$allocator@U_Container_proxy@std@@@std@@@_Container_base12@std@@QEAAX$$QEAV?$allocator@U_Container_proxy@std@@@1@@Z; std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(std::allocator<std::_Container_proxy> &&)
0x180009edd  nop
0x180009ede  mov     qword ptr [rdi+58h], 0FFFFFFFFFFFFFFFFh
0x180009ee6  mov     [rdi+60h], rbx
0x180009eea  mov     byte ptr [rdi+68h], 0
0x180009eee  mov     qword ptr [rdi+70h], 0
0x180009ef6  mov     qword ptr [rdi+78h], 0
0x180009efe  mov     qword ptr [rdi+80h], 0
0x180009f09  lea     r8, [rdi+88h]
0x180009f10  mov     rdx, rsi
0x180009f13  mov     rcx, r8
0x180009f16  call    ??0?$shared_ptr@VIConfigHelper@WFDSConMgr@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<WFDSConMgr::IConfigHelper>::shared_ptr<WFDSConMgr::IConfigHelper>(std::shared_ptr<WFDSConMgr::IConfigHelper> const &)
0x180009f1b  nop
0x180009f1c  cmp     qword ptr [rdi+60h], 0
0x180009f21  jnz     short loc_180009F4E
0x180009f23  lea     rax, aCreatedClientC; "Created client context without server p"...
0x180009f2a  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180009f2f  mov     r9d, 16h; char
0x180009f35  lea     r8, aOnecoreuapNetW_11; "onecoreuap\\net\\wlan\\wfdsconmgr\\serv"...
0x180009f3c  lea     rdx, aWfdsconmgrRpcC_10; "WFDSConMgr::RPC::CClientContext::CClien"...
0x180009f43  mov     ecx, 80070057h; int
0x180009f48  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBG@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *)
0x180009f4e  lea     rax, WPP_GLOBAL_Control
0x180009f55  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f5c  cmp     rcx, rax
0x180009f5f  jz      short loc_180009F96
0x180009f61  cmp     byte ptr [rcx+19h], 4
0x180009f65  jb      short loc_180009F96
0x180009f67  test    byte ptr [rcx+1Ch], 1
0x180009f6b  jz      short loc_180009F96
0x180009f6d  mov     edx, 0Ah
0x180009f72  mov     rax, [r8]
0x180009f75  mov     [rsp+48h+var_20], rax
0x180009f7a  mov     rax, [rdi]
0x180009f7d  mov     [rsp+48h+var_28], rax
0x180009f82  mov     r9, rdi
0x180009f85  lea     r8, WPP_a2095e9d95ef327a6cb68890677ecf94_Traceguids
0x180009f8c  mov     rcx, [rcx+10h]
0x180009f90  call    WPP_SF_qqq
0x180009f95  nop
0x180009f96  mov     rcx, [rsi+8]; this
0x180009f9a  test    rcx, rcx
0x180009f9d  jz      short loc_180009FA4
0x180009f9f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180009fa4  mov     rax, rdi
0x180009fa7  add     rsp, 30h
0x180009fab  pop     rdi
0x180009fac  pop     rsi
0x180009fad  pop     rbx
0x180009fae  retn
```
