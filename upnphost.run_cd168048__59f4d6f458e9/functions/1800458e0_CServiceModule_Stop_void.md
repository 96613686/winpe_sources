# CServiceModule::Stop(void)

- ea: `0x1800458e0`
- end: `0x180045a17`
- name: `?Stop@CServiceModule@@QEAAXXZ`
- size: `311`
- prototype: `void __fastcall(CServiceModule *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180035a7c`
- `0x180045a20`

## callees

- `0x18003b1cc`
- `0x18003b534`
- `0x18003b800`
- `0x18003d4b0`
- `0x180045124`
- `0x180045600`
- `0x1800458e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800458f4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800458f4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800459d7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800459d7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180045980`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180045980`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18004596d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18004596d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18004595a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18004595a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800459bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800459bc`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800459a4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800459a4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800459ef`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800459ef`

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
0x1800458e0  mov     [rsp+arg_0], rbx
0x1800458e5  push    rdi
0x1800458e6  sub     rsp, 20h
0x1800458ea  mov     rbx, rcx
0x1800458ed  mov     edx, 4; dwCoInit
0x1800458f2  xor     ecx, ecx; pvReserved
0x1800458f4  call    cs:__imp_CoInitializeEx
0x1800458fb  nop     dword ptr [rax+rax+00h]
0x180045900  mov     edi, eax
0x180045902  test    eax, eax
0x180045904  jz      short loc_180045937
0x180045906  mov     rcx, cs:WPP_GLOBAL_Control
0x18004590d  lea     rax, WPP_GLOBAL_Control
0x180045914  cmp     rcx, rax
0x180045917  jz      short loc_180045937
0x180045919  test    byte ptr [rcx+1Ch], 1
0x18004591d  jz      short loc_180045937
0x18004591f  mov     rcx, [rcx+10h]
0x180045923  lea     r8, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids
0x18004592a  mov     edx, 1Bh
0x18004592f  mov     r9d, edi
0x180045932  call    WPP_SF_d
0x180045937  mov     rcx, rbx; this
0x18004593a  call    ?Shutdown@CServiceModule@@AEAAXXZ; CServiceModule::Shutdown(void)
0x18004593f  call    ?RevokeClassObjects@CComModule@ATL@@QEAAJXZ; ATL::CComModule::RevokeClassObjects(void)
0x180045944  cmp     qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A, 0; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x18004594c  jz      short loc_18004599E
0x18004594e  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A+8; ptpcg
0x180045955  xor     r8d, r8d; pvCleanupContext
0x180045958  xor     edx, edx; fCancelPendingCallbacks
0x18004595a  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180045961  nop     dword ptr [rax+rax+00h]
0x180045966  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A+8; ptpcg
0x18004596d  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180045974  nop     dword ptr [rax+rax+00h]
0x180045979  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; ptpp
0x180045980  call    cs:__imp_CloseThreadpool
0x180045987  nop     dword ptr [rax+rax+00h]
0x18004598c  xor     edx, edx; Val
0x18004598e  lea     rcx, ?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; void *
0x180045995  lea     r8d, [rdx+58h]; Size
0x180045999  call    memset_0
0x18004599e  mov     rcx, [rbx+58h]; WaitHandle
0x1800459a2  xor     edx, edx; CompletionEvent
0x1800459a4  call    cs:__imp_UnregisterWaitEx
0x1800459ab  nop     dword ptr [rax+rax+00h]
0x1800459b0  mov     rcx, [rbx+88h]; hObject
0x1800459b7  test    rcx, rcx
0x1800459ba  jz      short loc_1800459D3
0x1800459bc  call    cs:__imp_CloseHandle
0x1800459c3  nop     dword ptr [rax+rax+00h]
0x1800459c8  mov     qword ptr [rbx+88h], 0
0x1800459d3  test    edi, edi
0x1800459d5  js      short loc_1800459E3
0x1800459d7  call    cs:__imp_CoUninitialize
0x1800459de  nop     dword ptr [rax+rax+00h]
0x1800459e3  mov     rcx, cs:pSid; pSid
0x1800459ea  test    rcx, rcx
0x1800459ed  jz      short loc_1800459FB
0x1800459ef  call    cs:__imp_FreeSid
0x1800459f6  nop     dword ptr [rax+rax+00h]
0x1800459fb  mov     edx, 1; unsigned int
0x180045a00  mov     rcx, rbx; this
0x180045a03  call    ?SetServiceStatus@CServiceModule@@QEAAXK@Z; CServiceModule::SetServiceStatus(ulong)
0x180045a08  mov     rbx, [rsp+28h+arg_0]
0x180045a0d  add     rsp, 20h
0x180045a11  pop     rdi
0x180045a12  jmp     WppCleanupUm
```
