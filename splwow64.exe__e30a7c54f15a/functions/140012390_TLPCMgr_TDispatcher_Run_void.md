# TLPCMgr::TDispatcher::Run(void)

- ea: `0x140012390`
- end: `0x14001258c`
- name: `?Run@TDispatcher@TLPCMgr@@UEAAJXZ`
- size: `508`
- prototype: `__int64 __fastcall(TLPCMgr::TDispatcher *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x1400085d8`
- `0x140011814`
- `0x140011bb0`
- `0x140012390`
- `0x140013870`
- `0x1400144a0`
- `0x140016010`

## import_xrefs

- `ADVAPI32!RevertToSelf` at `0x140012556`
- `ADVAPI32!RevertToSelf` at `0x140012556`
- `KERNEL32!WaitForSingleObject` at `0x1400123c4`
- `KERNEL32!WaitForSingleObject` at `0x1400123c4`
- `KERNEL32!GetCurrentThreadId` at `0x1400123d6`
- `KERNEL32!GetCurrentThreadId` at `0x1400123d6`
- `KERNEL32!EnterCriticalSection` at `0x1400123cd`
- `KERNEL32!EnterCriticalSection` at `0x1400123cd`
- `KERNEL32!LeaveCriticalSection` at `0x14001241f`
- `KERNEL32!LeaveCriticalSection` at `0x14001241f`
- `KERNEL32!SetThreadPreferredUILanguages` at `0x14001256b`
- `KERNEL32!SetThreadPreferredUILanguages` at `0x14001256b`
- `ntdll!NtAlpcCancelMessage` at `0x1400124d9`
- `ntdll!NtAlpcCancelMessage` at `0x1400124d9`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1400124a1`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1400124a1`

## string_xrefs

- `0x140012543`: `Driver failed to revert impersonation.`

## pseudocode

```c
__int64 __fastcall TLPCMgr::TDispatcher::Run(HANDLE *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  int v3; // r14d
  char *v4; // r12
  char *v5; // rbx
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  int v8; // eax
  __int64 v9; // rcx
  char *v10; // rbx
  struct NAdvancedLibrary::THashElementBase *v11; // r8
  struct NAdvancedLibrary::THashElementBase **v12; // r9
  __int128 v14; // [rsp+40h] [rbp-20h] BYREF
  __int128 v15; // [rsp+50h] [rbp-10h]
  int v16; // [rsp+90h] [rbp+30h] BYREF
  ULONG pulNumLanguages; // [rsp+98h] [rbp+38h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)(this + 16);
  v3 = 0;
  v4 = (char *)(this + 24);
  do
  {
    WaitForSingleObject(this[15], 0xFFFFFFFF);
    while ( 1 )
    {
      EnterCriticalSection(v2);
      ++HIDWORD(v2[1].DebugInfo);
      LODWORD(v2[1].DebugInfo) = GetCurrentThreadId();
      v5 = (char *)this[26];
      *(_QWORD *)(*((_QWORD *)v5 + 2) + 24LL) = *((_QWORD *)v5 + 3);
      *(_QWORD *)(*((_QWORD *)v5 + 3) + 16LL) = *((_QWORD *)v5 + 2);
      *((_QWORD *)v5 + 2) = v5;
      *((_QWORD *)v5 + 3) = v5;
      if ( v5 == v4 )
        v5 = 0;
      if ( !--HIDWORD(v2[1].DebugInfo) )
        LODWORD(v2[1].DebugInfo) = 0;
      LeaveCriticalSection(v2);
      if ( !v5 )
        break;
      v3 = 0;
      v6 = *((unsigned __int16 *)v5 + 26) & 0xFFFF00FF;
      v16 = 0;
      v7 = v6 - 1;
      if ( v7 )
      {
        if ( v7 == 4 )
        {
          TLPCMgr::ProcessPortShutdown(*((TLPCMgr **)v5 + 4), *((void **)v5 + 5), &v16);
          v3 = v16;
          goto LABEL_15;
        }
      }
      else if ( !(unsigned int)TLPCMgr::ProcessRequest(
                                 *((TLPCMgr **)v5 + 4),
                                 (struct PROXY_MSG *)(v5 + 48),
                                 (struct _REMOTE_PORT_VIEW *)(*((_QWORD *)v5 + 5) + 80LL)) )
      {
        NtAlpcSendWaitReceivePort(*(_QWORD *)(*((_QWORD *)v5 + 5) + 56LL), 0x10000, v5 + 48, 0, 0, 0, 0, 0);
        goto LABEL_15;
      }
      if ( (*((_WORD *)v5 + 26) & 0x2000) != 0 )
      {
        v8 = *((_DWORD *)v5 + 18);
        v9 = *((_QWORD *)v5 + 5);
        v15 = 0;
        DWORD1(v15) = v8;
        DWORD2(v15) = *((_DWORD *)v5 + 20);
        v14 = 0;
        NtAlpcCancelMessage(*(_QWORD *)(v9 + 56), 0, &v14);
      }
LABEL_15:
      (**(void (__fastcall ***)(HANDLE, __int64))v5)(v5, 1);
    }
  }
  while ( !v3 );
  v10 = (char *)this[28];
  NThreadingLibrary::TWorkCrew::DeleteItem(
    (NThreadingLibrary::TWorkCrew *)v10,
    (struct NThreadingLibrary::TWorkItem *)this);
  LOBYTE(v16) = 0;
  if ( this != (HANDLE *)-232LL )
    NAdvancedLibrary::THashTableBase::RemoveSpecificElement(
      (NAdvancedLibrary::THashTableBase *)(v10 + 232),
      this + 29,
      v11,
      v12,
      (bool *)&v16);
  if ( NtCurrentTeb()->IsImpersonating )
  {
    SplWow64Telemetry::WriteDbgTraceError("TLPCMgr::TDispatcher::Run", L"Driver failed to revert impersonation.");
    RevertToSelf();
  }
  pulNumLanguages = 0;
  SetThreadPreferredUILanguages(0, 0, &pulNumLanguages);
  return 0;
}

```

## disassembly

```asm
0x140012390  mov     [rsp-28h+arg_10], rbx
0x140012395  mov     [rsp-28h+arg_18], rsi
0x14001239a  push    rbp
0x14001239b  push    rdi
0x14001239c  push    r12
0x14001239e  push    r14
0x1400123a0  push    r15
0x1400123a2  mov     rbp, rsp
0x1400123a5  sub     rsp, 60h
0x1400123a9  mov     rdi, rcx
0x1400123ac  lea     rsi, [rcx+80h]
0x1400123b3  xor     r14d, r14d
0x1400123b6  lea     r12, [rcx+0C0h]
0x1400123bd  mov     rcx, [rdi+78h]; hHandle
0x1400123c1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400123c4  call    cs:__imp_WaitForSingleObject
0x1400123ca  mov     rcx, rsi; lpCriticalSection
0x1400123cd  call    cs:__imp_EnterCriticalSection
0x1400123d3  inc     dword ptr [rsi+2Ch]
0x1400123d6  call    cs:__imp_GetCurrentThreadId
0x1400123dc  mov     [rsi+28h], eax
0x1400123df  mov     rbx, [rdi+0D0h]
0x1400123e6  mov     rcx, [rbx+10h]
0x1400123ea  mov     rax, [rbx+18h]
0x1400123ee  mov     [rcx+18h], rax
0x1400123f2  mov     rax, [rbx+10h]
0x1400123f6  mov     rcx, [rbx+18h]
0x1400123fa  mov     [rcx+10h], rax
0x1400123fe  xor     eax, eax
0x140012400  mov     [rbx+10h], rbx
0x140012404  cmp     rbx, r12
0x140012407  mov     [rbx+18h], rbx
0x14001240b  cmovz   rbx, rax
0x14001240f  dec     dword ptr [rsi+2Ch]
0x140012412  mov     eax, [rsi+2Ch]
0x140012415  test    eax, eax
0x140012417  jnz     short loc_14001241C
0x140012419  mov     [rsi+28h], eax
0x14001241c  mov     rcx, rsi; lpCriticalSection
0x14001241f  call    cs:__imp_LeaveCriticalSection
0x140012425  test    rbx, rbx
0x140012428  jz      loc_1400124F7
0x14001242e  movzx   ecx, word ptr [rbx+34h]
0x140012432  xor     r14d, r14d
0x140012435  and     ecx, 0FFFF00FFh
0x14001243b  mov     [rbp+arg_0], r14d
0x14001243f  sub     ecx, 1
0x140012442  jz      short loc_140012460
0x140012444  cmp     ecx, 4
0x140012447  jnz     short loc_1400124A9
0x140012449  mov     rdx, [rbx+28h]; void *
0x14001244d  lea     r8, [rbp+arg_0]; int *
0x140012451  mov     rcx, [rbx+20h]; this
0x140012455  call    ?ProcessPortShutdown@TLPCMgr@@QEAAKPEAXPEAH@Z; TLPCMgr::ProcessPortShutdown(void *,int *)
0x14001245a  mov     r14d, [rbp+arg_0]
0x14001245e  jmp     short loc_1400124DF
0x140012460  mov     r8, [rbx+28h]
0x140012464  lea     rdx, [rbx+30h]; struct PROXY_MSG *
0x140012468  mov     rcx, [rbx+20h]; this
0x14001246c  add     r8, 50h ; 'P'; struct _REMOTE_PORT_VIEW *
0x140012470  call    ?ProcessRequest@TLPCMgr@@QEBAKPEAUPROXY_MSG@@PEAU_REMOTE_PORT_VIEW@@@Z; TLPCMgr::ProcessRequest(PROXY_MSG *,_REMOTE_PORT_VIEW *)
0x140012475  test    eax, eax
0x140012477  jnz     short loc_1400124A9
0x140012479  mov     rcx, [rbx+28h]
0x14001247d  lea     r8, [rbx+30h]
0x140012481  mov     [rsp+60h+var_28], r14
0x140012486  xor     r9d, r9d
0x140012489  mov     [rsp+60h+var_30], r14
0x14001248e  mov     edx, 10000h
0x140012493  mov     [rsp+60h+var_38], r14
0x140012498  mov     rcx, [rcx+38h]
0x14001249c  mov     [rsp+60h+var_40], r14
0x1400124a1  call    cs:__imp_NtAlpcSendWaitReceivePort
0x1400124a7  jmp     short loc_1400124DF
0x1400124a9  mov     eax, 2000h
0x1400124ae  test    [rbx+34h], ax
0x1400124b2  jz      short loc_1400124DF
0x1400124b4  mov     eax, [rbx+48h]
0x1400124b7  lea     r8, [rbp+var_20]
0x1400124bb  mov     rcx, [rbx+28h]
0x1400124bf  xorps   xmm0, xmm0
0x1400124c2  movups  [rbp+var_10], xmm0
0x1400124c6  mov     dword ptr [rbp+var_10+4], eax
0x1400124c9  xor     edx, edx
0x1400124cb  mov     eax, [rbx+50h]
0x1400124ce  mov     dword ptr [rbp+var_10+8], eax
0x1400124d1  movups  [rbp+var_20], xmm0
0x1400124d5  mov     rcx, [rcx+38h]
0x1400124d9  call    cs:__imp_NtAlpcCancelMessage
0x1400124df  mov     rax, [rbx]
0x1400124e2  mov     edx, 1
0x1400124e7  mov     rcx, rbx
0x1400124ea  mov     rax, [rax]
0x1400124ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400124f2  jmp     loc_1400123CA
0x1400124f7  test    r14d, r14d
0x1400124fa  jz      loc_1400123BD
0x140012500  mov     rbx, [rdi+0E0h]
0x140012507  mov     rdx, rdi; struct NThreadingLibrary::TWorkItem *
0x14001250a  mov     rcx, rbx; this
0x14001250d  call    ?DeleteItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::DeleteItem(NThreadingLibrary::TWorkItem *)
0x140012512  lea     rdx, [rdi+0E8h]; void *
0x140012519  mov     byte ptr [rbp+arg_0], 0
0x14001251d  test    rdx, rdx
0x140012520  jz      short loc_140012537
0x140012522  lea     rax, [rbp+arg_0]
0x140012526  lea     rcx, [rbx+0E8h]; this
0x14001252d  mov     [rsp+60h+var_40], rax; bool *
0x140012532  call    ?RemoveSpecificElement@THashTableBase@NAdvancedLibrary@@AEAAXPEBXPEAVTHashElementBase@2@PEAPEAV32@PEA_N@Z; NAdvancedLibrary::THashTableBase::RemoveSpecificElement(void const *,NAdvancedLibrary::THashElementBase *,NAdvancedLibrary::THashElementBase * *,bool *)
0x140012537  mov     eax, gs:179Ch
0x14001253f  test    eax, eax
0x140012541  jz      short loc_14001255C
0x140012543  lea     rdx, aDriverFailedTo; "Driver failed to revert impersonation."
0x14001254a  lea     rcx, aTlpcmgrTdispat; "TLPCMgr::TDispatcher::Run"
0x140012551  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x140012556  call    cs:__imp_RevertToSelf
0x14001255c  lea     r8, [rbp+pulNumLanguages]; pulNumLanguages
0x140012560  mov     [rbp+pulNumLanguages], 0
0x140012567  xor     edx, edx; pwszLanguagesBuffer
0x140012569  xor     ecx, ecx; dwFlags
0x14001256b  call    cs:__imp_SetThreadPreferredUILanguages
0x140012571  lea     r11, [rsp+60h+var_s0]
0x140012576  xor     eax, eax
0x140012578  mov     rbx, [r11+40h]
0x14001257c  mov     rsi, [r11+48h]
0x140012580  mov     rsp, r11
0x140012583  pop     r15
0x140012585  pop     r14
0x140012587  pop     r12
0x140012589  pop     rdi
0x14001258a  pop     rbp
0x14001258b  retn
```
