# CServiceModule::Stop(void)

- ea: `0x180042eb8`
- end: `0x180042fbf`
- name: `?Stop@CServiceModule@@QEAAXXZ`
- size: `263`
- prototype: `void __fastcall(CServiceModule *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180033b14`
- `0x180042fd0`

## callees

- `0x180038ce4`
- `0x180039094`
- `0x180039298`
- `0x18003ae80`
- `0x180042754`
- `0x180042c0c`
- `0x180042eb8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180042ecc`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180042ecc`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180042f8b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180042f8b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180042f46`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180042f46`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180042f39`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180042f39`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180042f2c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180042f2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042f76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042f76`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180042f64`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180042f64`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180042f9d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180042f9d`

## pseudocode

```c
void __fastcall CServiceModule::Stop(HANDLE *this)
{
  HRESULT v2; // edi
  ATL::CComModule *v3; // rcx
  HANDLE v4; // rcx

  v2 = CoInitializeEx(0, 4u);
  if ( v2 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids, (unsigned int)v2);
  CServiceModule::Shutdown((CServiceModule *)this);
  ATL::CComModule::RevokeClassObjects(v3);
  if ( CWorkItem::s_tpEnviron )
  {
    CloseThreadpoolCleanupGroupMembers(*(&CWorkItem::s_tpEnviron + 1), 0, 0);
    CloseThreadpoolCleanupGroup(*(&CWorkItem::s_tpEnviron + 1));
    CloseThreadpool(CWorkItem::s_tpEnviron);
    memset_0(&CWorkItem::s_tpEnviron, 0, 0x58u);
  }
  UnregisterWaitEx(this[11], 0);
  v4 = this[17];
  if ( v4 )
  {
    CloseHandle(v4);
    this[17] = 0;
  }
  if ( v2 >= 0 )
    CoUninitialize();
  if ( pSid )
    FreeSid(pSid);
  CServiceModule::SetServiceStatus((CServiceModule *)this, 1u);
  WppCleanupUm();
}

```

## disassembly

```asm
0x180042eb8  mov     [rsp+arg_0], rbx
0x180042ebd  push    rdi
0x180042ebe  sub     rsp, 20h
0x180042ec2  mov     rbx, rcx
0x180042ec5  mov     edx, 4; dwCoInit
0x180042eca  xor     ecx, ecx; pvReserved
0x180042ecc  call    cs:__imp_CoInitializeEx
0x180042ed2  mov     edi, eax
0x180042ed4  test    eax, eax
0x180042ed6  jz      short loc_180042F09
0x180042ed8  mov     rcx, cs:WPP_GLOBAL_Control
0x180042edf  lea     rax, WPP_GLOBAL_Control
0x180042ee6  cmp     rcx, rax
0x180042ee9  jz      short loc_180042F09
0x180042eeb  test    byte ptr [rcx+1Ch], 1
0x180042eef  jz      short loc_180042F09
0x180042ef1  mov     rcx, [rcx+10h]
0x180042ef5  lea     r8, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids
0x180042efc  mov     edx, 1Bh
0x180042f01  mov     r9d, edi
0x180042f04  call    WPP_SF_d
0x180042f09  mov     rcx, rbx; this
0x180042f0c  call    ?Shutdown@CServiceModule@@AEAAXXZ; CServiceModule::Shutdown(void)
0x180042f11  call    ?RevokeClassObjects@CComModule@ATL@@QEAAJXZ; ATL::CComModule::RevokeClassObjects(void)
0x180042f16  cmp     qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A, 0; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x180042f1e  jz      short loc_180042F5E
0x180042f20  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A+8; ptpcg
0x180042f27  xor     r8d, r8d; pvCleanupContext
0x180042f2a  xor     edx, edx; fCancelPendingCallbacks
0x180042f2c  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180042f32  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A+8; ptpcg
0x180042f39  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180042f3f  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; ptpp
0x180042f46  call    cs:__imp_CloseThreadpool
0x180042f4c  xor     edx, edx; Val
0x180042f4e  lea     rcx, ?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; void *
0x180042f55  lea     r8d, [rdx+58h]; Size
0x180042f59  call    memset_0
0x180042f5e  mov     rcx, [rbx+58h]; WaitHandle
0x180042f62  xor     edx, edx; CompletionEvent
0x180042f64  call    cs:__imp_UnregisterWaitEx
0x180042f6a  mov     rcx, [rbx+88h]; hObject
0x180042f71  test    rcx, rcx
0x180042f74  jz      short loc_180042F87
0x180042f76  call    cs:__imp_CloseHandle
0x180042f7c  mov     qword ptr [rbx+88h], 0
0x180042f87  test    edi, edi
0x180042f89  js      short loc_180042F91
0x180042f8b  call    cs:__imp_CoUninitialize
0x180042f91  mov     rcx, cs:pSid; pSid
0x180042f98  test    rcx, rcx
0x180042f9b  jz      short loc_180042FA3
0x180042f9d  call    cs:__imp_FreeSid
0x180042fa3  mov     edx, 1; unsigned int
0x180042fa8  mov     rcx, rbx; this
0x180042fab  call    ?SetServiceStatus@CServiceModule@@QEAAXK@Z; CServiceModule::SetServiceStatus(ulong)
0x180042fb0  mov     rbx, [rsp+28h+arg_0]
0x180042fb5  add     rsp, 20h
0x180042fb9  pop     rdi
0x180042fba  jmp     WppCleanupUm
```
