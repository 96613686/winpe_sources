# CAnimationScheduler::_SetStoryboardTriggerForAnimationClock(_GUID)

- ea: `0x18002ffac`
- end: `0x1800301da`
- name: `?_SetStoryboardTriggerForAnimationClock@CAnimationScheduler@@AEAAJU_GUID@@@Z`
- size: `558`
- prototype: `int(CAnimationScheduler *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002fde0`

## callees

- `0x18001ce00`
- `0x18002ffac`
- `0x1800301e0`
- `0x180030214`
- `0x180044ec0`
- `0x180090664`
- `0x180090f90`
- `0x180095b28`
- `0x18009ddd8`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180030181`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180030181`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003009f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800301cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003009f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800301cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CAnimationScheduler::_SetStoryboardTriggerForAnimationClock(
        CAnimationScheduler *this,
        struct _GUID *a2)
{
  int SynchronizationCommitHandle; // edi
  struct CAnimationTriggerProxy *v5; // rbx
  __int64 i; // r14
  _DWORD *v7; // rsi
  CAnimationClockCoordinator *v9; // rdi
  DWORD CurrentProcessId; // eax
  HANDLE hObject; // [rsp+20h] [rbp-30h] BYREF
  struct CAnimationTriggerProxy *v12; // [rsp+28h] [rbp-28h] BYREF
  __int128 Buf1; // [rsp+30h] [rbp-20h] BYREF
  struct _GUID v14; // [rsp+40h] [rbp-10h] BYREF

  SynchronizationCommitHandle = 0;
  hObject = 0;
  v5 = 0;
  v12 = 0;
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 10); i = (unsigned int)(i + 1) )
  {
    if ( SynchronizationCommitHandle < 0 )
      break;
    v7 = *(_DWORD **)(*((_QWORD *)this + 2) + 8 * i);
    Buf1 = *((_OWORD *)v7 + 3);
    if ( !memcmp_0(&Buf1, a2, 0x10u)
      && v7[6] != 4
      && (CStoryboard::UseDComposition((CStoryboard *)v7)
       || (*(unsigned __int8 (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 48LL))(v7)) )
    {
      if ( (((unsigned __int64)hObject + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0
        && (*(unsigned __int8 (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 48LL))(v7) )
      {
        v9 = (CAnimationClockCoordinator *)*((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 21);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &hObject,
          0);
        CurrentProcessId = GetCurrentProcessId();
        SynchronizationCommitHandle = CAnimationClockCoordinator::OnGetSynchronizationCommitHandle(
                                        v9,
                                        a2,
                                        CurrentProcessId,
                                        &hObject);
      }
      if ( v5
        || CStoryboard::UseDComposition((CStoryboard *)v7)
        && (*(_QWORD *)&Buf1 = 0,
            v14 = *a2,
            SynchronizationCommitHandle = CAnimationClockCoordinator::OnGetAnimationClockToken(
                                            *((CAnimationClockCoordinator **)CDesktopManager::s_pDesktopManagerInstance
                                            + 21),
                                            &v14,
                                            (void **)&Buf1),
            SynchronizationCommitHandle >= 0)
        && (v12 = 0,
            SynchronizationCommitHandle = CCompositor::CreateAnimationTriggerProxyFromSharedHandle(
                                            *((CCompositor **)CDesktopManager::s_pDesktopManagerInstance + 6),
                                            (void *)Buf1,
                                            &v12),
            CloseHandle((HANDLE)Buf1),
            (v5 = v12) != 0) )
      {
        if ( CStoryboard::UseDComposition((CStoryboard *)v7) )
          CStoryboard::SetStartTrigger((CStoryboard *)v7, v5);
      }
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL
        && (*(unsigned __int8 (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 48LL))(v7) )
      {
        (*(void (__fastcall **)(_DWORD *, HANDLE))(*(_QWORD *)v7 + 56LL))(v7, hObject);
      }
    }
  }
  if ( v5 )
    CBaseObject::Release(v5);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return (unsigned int)SynchronizationCommitHandle;
}

```

## disassembly

```asm
0x18002ffac  mov     [rsp-28h+arg_8], rbx
0x18002ffb1  mov     [rsp-28h+arg_10], rsi
0x18002ffb6  push    rbp
0x18002ffb7  push    rdi
0x18002ffb8  push    r12
0x18002ffba  push    r14
0x18002ffbc  push    r15
0x18002ffbe  mov     rbp, rsp
0x18002ffc1  sub     rsp, 50h
0x18002ffc5  mov     r12, rdx
0x18002ffc8  mov     r15, rcx
0x18002ffcb  xor     edi, edi
0x18002ffcd  mov     [rbp+hObject], rdi
0x18002ffd1  xor     ebx, ebx
0x18002ffd3  mov     [rbp+var_28], rbx
0x18002ffd7  xor     r14d, r14d
0x18002ffda  cmp     [rcx+28h], r14d
0x18002ffde  jbe     loc_1800300CC
0x18002ffe4  test    edi, edi
0x18002ffe6  js      loc_1800300CC
0x18002ffec  mov     rax, [r15+10h]
0x18002fff0  mov     rsi, [rax+r14*8]
0x18002fff4  movups  xmm0, xmmword ptr [rsi+30h]
0x18002fff8  movdqu  [rbp+Buf1], xmm0
0x18002fffd  mov     r8d, 10h; Size
0x180030003  mov     rdx, r12; Buf2
0x180030006  lea     rcx, [rbp+Buf1]; Buf1
0x18003000a  call    memcmp_0
0x18003000f  test    eax, eax
0x180030011  jnz     loc_1800300BF
0x180030017  cmp     dword ptr [rsi+18h], 4
0x18003001b  jz      loc_1800300BF
0x180030021  mov     rcx, rsi; this
0x180030024  call    ?UseDComposition@CStoryboard@@QEAA_NXZ; CStoryboard::UseDComposition(void)
0x180030029  test    al, al
0x18003002b  jz      loc_180030107
0x180030031  mov     rax, [rbp+hObject]
0x180030035  inc     rax
0x180030038  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003003e  jnz     short loc_180030057
0x180030040  mov     rax, [rsi]
0x180030043  mov     rcx, rsi
0x180030046  mov     rax, [rax+30h]
0x18003004a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003004f  test    al, al
0x180030051  jnz     loc_180030168
0x180030057  test    rbx, rbx
0x18003005a  jz      loc_180030120
0x180030060  mov     rcx, rsi; this
0x180030063  call    ?UseDComposition@CStoryboard@@QEAA_NXZ; CStoryboard::UseDComposition(void)
0x180030068  test    al, al
0x18003006a  jz      short loc_1800300AE
0x18003006c  mov     rdx, rbx; struct CAnimationTriggerProxy *
0x18003006f  mov     rcx, rsi; this
0x180030072  call    ?SetStartTrigger@CStoryboard@@QEAAXPEAVCAnimationTriggerProxy@@@Z; CStoryboard::SetStartTrigger(CAnimationTriggerProxy *)
0x180030077  jmp     short loc_1800300AE
0x180030079  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x180030080  mov     [rbp+var_28], 0
0x180030088  lea     r8, [rbp+var_28]; struct CAnimationTriggerProxy **
0x18003008c  mov     rdx, qword ptr [rbp+Buf1]; void *
0x180030090  mov     rcx, [rax+30h]; this
0x180030094  call    ?CreateAnimationTriggerProxyFromSharedHandle@CCompositor@@QEAAJPEAXPEAPEAVCAnimationTriggerProxy@@@Z; CCompositor::CreateAnimationTriggerProxyFromSharedHandle(void *,CAnimationTriggerProxy * *)
0x180030099  mov     edi, eax
0x18003009b  mov     rcx, qword ptr [rbp+Buf1]; hObject
0x18003009f  call    cs:__imp_CloseHandle
0x1800300a5  mov     rbx, [rbp+var_28]
0x1800300a9  test    rbx, rbx
0x1800300ac  jnz     short loc_180030060
0x1800300ae  mov     rax, [rbp+hObject]
0x1800300b2  dec     rax
0x1800300b5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800300b9  jbe     loc_1800301A0
0x1800300bf  inc     r14d
0x1800300c2  cmp     r14d, [r15+28h]
0x1800300c6  jb      loc_18002FFE4
0x1800300cc  test    rbx, rbx
0x1800300cf  jz      short loc_1800300DA
0x1800300d1  mov     rcx, rbx; this
0x1800300d4  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x1800300d9  nop
0x1800300da  mov     rcx, [rbp+hObject]; hObject
0x1800300de  lea     rax, [rcx-1]
0x1800300e2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800300e6  jbe     loc_1800301CF
0x1800300ec  mov     eax, edi
0x1800300ee  lea     r11, [rsp+50h+var_s0]
0x1800300f3  mov     rbx, [r11+38h]
0x1800300f7  mov     rsi, [r11+40h]
0x1800300fb  mov     rsp, r11
0x1800300fe  pop     r15
0x180030100  pop     r14
0x180030102  pop     r12
0x180030104  pop     rdi
0x180030105  pop     rbp
0x180030106  retn
0x180030107  mov     rax, [rsi]
0x18003010a  mov     rcx, rsi
0x18003010d  mov     rax, [rax+30h]
0x180030111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030116  test    al, al
0x180030118  jnz     loc_180030031
0x18003011e  jmp     short loc_1800300BF
0x180030120  mov     rcx, rsi; this
0x180030123  call    ?UseDComposition@CStoryboard@@QEAA_NXZ; CStoryboard::UseDComposition(void)
0x180030128  test    al, al
0x18003012a  jz      short loc_1800300AE
0x18003012c  mov     qword ptr [rbp+Buf1], 0
0x180030134  movaps  xmm0, xmmword ptr [r12]
0x180030139  movdqa  xmmword ptr [rbp+var_10.Data1], xmm0
0x18003013e  lea     r8, [rbp+Buf1]; void **
0x180030142  lea     rdx, [rbp+var_10]; struct _GUID
0x180030146  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18003014d  mov     rcx, [rcx+0A8h]; this
0x180030154  call    ?OnGetAnimationClockToken@CAnimationClockCoordinator@@QEAAJU_GUID@@PEAPEAX@Z; CAnimationClockCoordinator::OnGetAnimationClockToken(_GUID,void * *)
0x180030159  mov     edi, eax
0x18003015b  test    eax, eax
0x18003015d  js      loc_1800300AE
0x180030163  jmp     loc_180030079
0x180030168  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18003016f  mov     rdi, [rax+0A8h]
0x180030176  xor     edx, edx
0x180030178  lea     rcx, [rbp+hObject]
0x18003017c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180030181  call    cs:__imp_GetCurrentProcessId
0x180030187  lea     r9, [rbp+hObject]; void **
0x18003018b  mov     r8d, eax; unsigned int
0x18003018e  mov     rdx, r12; struct _GUID *
0x180030191  mov     rcx, rdi; this
0x180030194  call    ?OnGetSynchronizationCommitHandle@CAnimationClockCoordinator@@QEAAJAEBU_GUID@@KPEAPEAX@Z; CAnimationClockCoordinator::OnGetSynchronizationCommitHandle(_GUID const &,ulong,void * *)
0x180030199  mov     edi, eax
0x18003019b  jmp     loc_180030057
0x1800301a0  mov     rax, [rsi]
0x1800301a3  mov     rcx, rsi
0x1800301a6  mov     rax, [rax+30h]
0x1800301aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301af  test    al, al
0x1800301b1  jz      loc_1800300BF
0x1800301b7  mov     rax, [rsi]
0x1800301ba  mov     rdx, [rbp+hObject]
0x1800301be  mov     rcx, rsi
0x1800301c1  mov     rax, [rax+38h]
0x1800301c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301ca  jmp     loc_1800300BF
0x1800301cf  call    cs:__imp_CloseHandle
0x1800301d5  jmp     loc_1800300EC
```
