# SecMgrSuccessExitAction(PORT_EVENT *,ulong *)

- ea: `0x18003d510`
- end: `0x18003d611`
- name: `?SecMgrSuccessExitAction@@YAKPEAUPORT_EVENT@@PEAK@Z`
- size: `257`
- prototype: `unsigned int __fastcall(struct PORT_EVENT *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000892c`
- `0x180008998`
- `0x1800096b8`
- `0x1800169c0`
- `0x18003d510`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18003d5ca`
- `MobileNetworking!ReleaseWriteLock` at `0x18003d5ca`
- `MobileNetworking!AcquireWriteLock` at `0x18003d580`
- `MobileNetworking!AcquireWriteLock` at `0x18003d580`

## pseudocode

```c
__int64 __fastcall SecMgrSuccessExitAction(struct PORT_EVENT *a1, unsigned int *a2)
{
  __int64 v3; // rbx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 63, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids);
  v3 = *((_QWORD *)a1 + 3);
  TraceAdapterId(*(_DWORD *)(*(_QWORD *)(v3 + 24) + 2496LL), ">>> Locking >>>");
  AcquireWriteLock(*(_QWORD *)(v3 + 24), *(_QWORD *)(v3 + 24) + 2512LL, "SecMgrSuccessExitAction", 743);
  PreAuthDeactivate((struct MSMSEC_PREAUTH_CONTEXT *)(*(_QWORD *)(v3 + 24) + 2912LL));
  TraceAdapterId(*(_DWORD *)(*(_QWORD *)(v3 + 24) + 2496LL), "<<< Unlocking <<<");
  ReleaseWriteLock(*(_QWORD *)(v3 + 24), *(_QWORD *)(v3 + 24) + 2512LL, "SecMgrSuccessExitAction", 745);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 64, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x18003d510  mov     [rsp+arg_0], rbx
0x18003d515  push    rsi
0x18003d516  sub     rsp, 20h
0x18003d51a  mov     rbx, rcx
0x18003d51d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d524  lea     rsi, WPP_GLOBAL_Control
0x18003d52b  cmp     rcx, rsi
0x18003d52e  jz      short loc_18003D54E
0x18003d530  test    dword ptr [rcx+44h], 100h
0x18003d537  jz      short loc_18003D54E
0x18003d539  mov     rcx, [rcx+38h]
0x18003d53d  lea     r8, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x18003d544  mov     edx, 3Fh ; '?'
0x18003d549  call    WPP_SF_
0x18003d54e  mov     rbx, [rbx+18h]
0x18003d552  lea     rdx, aLocking; ">>> Locking >>>"
0x18003d559  mov     rcx, [rbx+18h]
0x18003d55d  mov     ecx, [rcx+9C0h]; unsigned int
0x18003d563  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18003d568  mov     rcx, [rbx+18h]
0x18003d56c  lea     r8, aSecmgrsuccesse; "SecMgrSuccessExitAction"
0x18003d573  mov     r9d, 2E7h
0x18003d579  lea     rdx, [rcx+9D0h]
0x18003d580  call    cs:__imp_AcquireWriteLock
0x18003d587  nop     dword ptr [rax+rax+00h]
0x18003d58c  mov     rcx, [rbx+18h]
0x18003d590  add     rcx, 0B60h; struct MSMSEC_PREAUTH_CONTEXT *
0x18003d597  call    ?PreAuthDeactivate@@YAKPEAUMSMSEC_PREAUTH_CONTEXT@@@Z; PreAuthDeactivate(MSMSEC_PREAUTH_CONTEXT *)
0x18003d59c  mov     rcx, [rbx+18h]
0x18003d5a0  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x18003d5a7  mov     ecx, [rcx+9C0h]; unsigned int
0x18003d5ad  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18003d5b2  mov     rcx, [rbx+18h]
0x18003d5b6  lea     r8, aSecmgrsuccesse; "SecMgrSuccessExitAction"
0x18003d5bd  mov     r9d, 2E9h
0x18003d5c3  lea     rdx, [rcx+9D0h]
0x18003d5ca  call    cs:__imp_ReleaseWriteLock
0x18003d5d1  nop     dword ptr [rax+rax+00h]
0x18003d5d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d5dd  cmp     rcx, rsi
0x18003d5e0  jz      short loc_18003D603
0x18003d5e2  test    dword ptr [rcx+44h], 100h
0x18003d5e9  jz      short loc_18003D603
0x18003d5eb  mov     rcx, [rcx+38h]
0x18003d5ef  lea     r8, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x18003d5f6  mov     edx, 40h ; '@'
0x18003d5fb  xor     r9d, r9d
0x18003d5fe  call    WPP_SF_d
0x18003d603  mov     rbx, [rsp+28h+arg_0]
0x18003d608  xor     eax, eax
0x18003d60a  add     rsp, 20h
0x18003d60e  pop     rsi
0x18003d60f  retn
```
