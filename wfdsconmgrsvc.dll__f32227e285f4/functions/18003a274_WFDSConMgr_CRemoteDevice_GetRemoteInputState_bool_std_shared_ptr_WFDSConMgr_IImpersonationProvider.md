# WFDSConMgr::CRemoteDevice::GetRemoteInputState(bool,std::shared_ptr<WFDSConMgr::IImpersonationProvider>)

- ea: `0x18003a274`
- end: `0x18003a5cc`
- name: `?GetRemoteInputState@CRemoteDevice@WFDSConMgr@@QEAA?AW4_WFDSConMgrRemoteInputState@@_NV?$shared_ptr@VIImpersonationProvider@WFDSConMgr@@@std@@@Z`
- size: `856`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `12`
- tags: ``

## callers

- `0x180032474`
- `0x180034248`
- `0x18003e934`

## callees

- `0x18000475c`
- `0x180004f38`
- `0x1800059c0`
- `0x180006780`
- `0x180006c60`
- `0x180008a10`
- `0x180025c6c`
- `0x1800276f0`
- `0x18003a274`
- `0x1800428c8`
- `0x18005c888`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a3b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a53e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a3b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a53e`

## string_xrefs

- `0x18003a2c5`: `Trying to refresh UIBC state but need impersonation provider`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WFDSConMgr::CRemoteDevice::GetRemoteInputState(char *a1, char a2, _QWORD *a3)
{
  int v6; // esi
  __int64 v7; // rbx
  void *v8; // rcx
  __int64 v9; // rbx
  void *v10; // rcx
  int *v11; // rdi
  bool v12; // al
  __int64 v13; // rbx
  char v14; // si
  char v15; // bl
  unsigned int v16; // ebx
  std::_Ref_count_base *v17; // rcx
  bool v19; // [rsp+30h] [rbp-20h] BYREF
  bool v20; // [rsp+31h] [rbp-1Fh] BYREF
  bool v21; // [rsp+32h] [rbp-1Eh] BYREF
  __int64 v22; // [rsp+38h] [rbp-18h] BYREF
  _BYTE v23[16]; // [rsp+40h] [rbp-10h] BYREF
  bool v24; // [rsp+90h] [rbp+40h] BYREF
  char v25; // [rsp+98h] [rbp+48h] BYREF
  _QWORD *v26; // [rsp+A0h] [rbp+50h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+A8h] [rbp+58h] BYREF

  v26 = a3;
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(
    (__int64)v23,
    (RTL_SRWLOCK *)a1 + 6);
  v24 = 0;
  v25 = 1;
  v6 = 2;
  if ( !a2 )
  {
    v11 = (int *)(a1 + 864);
    if ( *((_DWORD *)a1 + 216) )
      goto LABEL_37;
    goto LABEL_18;
  }
  if ( !*a3 )
    WFDSConMgr::CException::Throw(
      87,
      "WFDSConMgr::CRemoteDevice::GetRemoteInputState",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\remotedevice.cpp",
      170,
      L"Trying to refresh UIBC state but need impersonation provider",
      a1);
  (*(void (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 8LL))(*a3, &v22);
  if ( (a1[412] & 2) == 0 )
  {
    v7 = *((_QWORD *)a1 + 106);
    if ( v7 )
    {
      WFDSConMgr::CriticalSection::Lock(v7 + 104, &lpCriticalSection);
      v8 = *(void **)(v7 + 72);
      if ( v8 && *(_QWORD *)(v7 + 208) )
        WFDSConMgr::CDevQueryHelper::GetUibcPropertiesForMiracastDisplayDevice(v8, v7 + 286, v7 + 287);
LABEL_14:
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      goto LABEL_16;
    }
  }
  v9 = *((_QWORD *)a1 + 111);
  if ( v9 )
  {
    WFDSConMgr::CriticalSection::Lock(v9 + 8, &lpCriticalSection);
    v10 = *(void **)(v9 + 96);
    if ( v10 && *(_QWORD *)(v9 + 328) )
      WFDSConMgr::CDevQueryHelper::GetMaUsbDeviceRemoteInputAllowed(v10);
    goto LABEL_14;
  }
LABEL_16:
  std::unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>::~unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>(&v22);
  v11 = (int *)(a1 + 864);
LABEL_18:
  if ( (a1[412] & 2) == 0 && *((_QWORD *)a1 + 106) )
  {
    (*(void (__fastcall **)(_QWORD, LPCRITICAL_SECTION *))(*(_QWORD *)*a3 + 8LL))(*a3, &lpCriticalSection);
    (*(void (__fastcall **)(_QWORD, bool *))(**((_QWORD **)a1 + 21) + 8LL))(*((_QWORD *)a1 + 21), &v24);
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)a1 + 21) + 16LL))(*((_QWORD *)a1 + 21), &v25);
    std::unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>::~unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>(&lpCriticalSection);
    if ( v25 )
    {
      LOBYTE(lpCriticalSection) = 0;
      v19 = 0;
      v20 = 0;
      v21 = 0;
      WFDSConMgr::CMiracastHelper::GetUibcState(
        *((WFDSConMgr::CMiracastHelper **)a1 + 106),
        (bool *)&lpCriticalSection,
        &v19,
        &v20,
        &v21);
      if ( (_BYTE)lpCriticalSection )
      {
        if ( v19 )
        {
          v12 = v21;
          if ( !v20 )
            v12 = v24;
          v6 = v12 + 3;
        }
        else
        {
          v6 = 1;
        }
      }
      else
      {
        v6 = 0;
      }
    }
    v11 = (int *)(a1 + 864);
    goto LABEL_31;
  }
  if ( *((_QWORD *)a1 + 111) )
  {
    (*(void (__fastcall **)(_QWORD, LPCRITICAL_SECTION *))(*(_QWORD *)*a3 + 8LL))(*a3, &lpCriticalSection);
    (*(void (__fastcall **)(_QWORD, bool *))(**((_QWORD **)a1 + 21) + 24LL))(*((_QWORD *)a1 + 21), &v24);
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)a1 + 21) + 16LL))(*((_QWORD *)a1 + 21), &v25);
    std::unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>::~unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>(&lpCriticalSection);
    if ( !v25 )
    {
LABEL_31:
      *v11 = v6;
      goto LABEL_37;
    }
    v13 = *((_QWORD *)a1 + 111);
    WFDSConMgr::CriticalSection::Lock(v13 + 8, &lpCriticalSection);
    v14 = *(_BYTE *)(v13 + 372);
    v15 = *(_BYTE *)(v13 + 373);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    if ( v14 )
      *v11 = (v15 != 0) + 3;
    else
      *v11 = v24 + 3;
  }
LABEL_37:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_b0264b43d37c3d36bda437b21bf2ef10_Traceguids, a1, *v11);
  }
  v16 = *v11;
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(v23);
  v17 = (std::_Ref_count_base *)a3[1];
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  return v16;
}

```

## disassembly

```asm
0x18003a274  mov     [rsp-38h+arg_10], r8
0x18003a279  push    rbp
0x18003a27a  push    rbx
0x18003a27b  push    rsi
0x18003a27c  push    rdi
0x18003a27d  push    r12
0x18003a27f  push    r14
0x18003a281  push    r15
0x18003a283  mov     rbp, rsp
0x18003a286  sub     rsp, 50h
0x18003a28a  mov     r15, r8
0x18003a28d  mov     bl, dl
0x18003a28f  mov     r14, rcx
0x18003a292  lea     rdx, [rcx+30h]
0x18003a296  lea     rcx, [rbp+var_10]
0x18003a29a  call    ??0?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAA@AEAVReadersWriterLock@1@@Z; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(WFDSConMgr::ReadersWriterLock &)
0x18003a29f  nop
0x18003a2a0  xor     r12d, r12d
0x18003a2a3  mov     [rbp+arg_0], r12b
0x18003a2a7  mov     [rbp+arg_8], 1
0x18003a2ab  lea     esi, [r12+2]
0x18003a2b0  test    bl, bl
0x18003a2b2  jz      loc_18003A3CE
0x18003a2b8  mov     rcx, [r15]
0x18003a2bb  test    rcx, rcx
0x18003a2be  jnz     short loc_18003A2F0
0x18003a2c0  mov     [rsp+50h+var_28], r14; void *
0x18003a2c5  lea     rax, aTryingToRefres; "Trying to refresh UIBC state but need i"...
0x18003a2cc  mov     [rsp+50h+var_30], rax; unsigned __int16 *
0x18003a2d1  mov     r9d, 5AAh; char
0x18003a2d7  lea     r8, aOnecoreuapNetW_17; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18003a2de  lea     rdx, aWfdsconmgrCrem_19; "WFDSConMgr::CRemoteDevice::GetRemoteInp"...
0x18003a2e5  mov     ecx, 80070057h; char
0x18003a2ea  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18003a2f0  mov     rax, [rcx]
0x18003a2f3  lea     rdx, [rbp+var_18]
0x18003a2f7  mov     rax, [rax+8]
0x18003a2fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a300  nop
0x18003a301  test    [r14+19Ch], sil
0x18003a308  jnz     short loc_18003A368
0x18003a30a  mov     rbx, [r14+350h]
0x18003a311  test    rbx, rbx
0x18003a314  jz      short loc_18003A368
0x18003a316  lea     rcx, [rbx+68h]
0x18003a31a  lea     rdx, [rbp+lpCriticalSection]
0x18003a31e  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18003a323  nop
0x18003a324  mov     rcx, [rbx+48h]; void *
0x18003a328  test    rcx, rcx
0x18003a32b  jz      short loc_18003A366
0x18003a32d  lea     rdx, [rbx+0C0h]
0x18003a334  cmp     [rdx+10h], r12
0x18003a338  jz      short loc_18003A366
0x18003a33a  lea     rax, [rbx+11Fh]
0x18003a341  lea     r10, [rbx+11Eh]
0x18003a348  lea     r9, [rbx+11Dh]
0x18003a34f  lea     r8, [rbx+11Ch]
0x18003a356  mov     [rsp+50h+var_28], rax; __int64
0x18003a35b  mov     [rsp+50h+var_30], r10; __int64
0x18003a360  call    ?GetUibcPropertiesForMiracastDisplayDevice@CDevQueryHelper@WFDSConMgr@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_N111@Z; WFDSConMgr::CDevQueryHelper::GetUibcPropertiesForMiracastDisplayDevice(std::wstring const &,bool &,bool &,bool &,bool &)
0x18003a365  nop
0x18003a366  jmp     short loc_18003A3AC
0x18003a368  mov     rbx, [r14+378h]
0x18003a36f  test    rbx, rbx
0x18003a372  jz      short loc_18003A3BC
0x18003a374  lea     rcx, [rbx+8]
0x18003a378  lea     rdx, [rbp+lpCriticalSection]
0x18003a37c  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18003a381  nop
0x18003a382  mov     rcx, [rbx+60h]; void *
0x18003a386  test    rcx, rcx
0x18003a389  jz      short loc_18003A3AC
0x18003a38b  lea     rdx, [rbx+138h]
0x18003a392  cmp     [rdx+10h], r12
0x18003a396  jz      short loc_18003A3AC
0x18003a398  lea     r9, [rbx+175h]
0x18003a39f  lea     r8, [rbx+174h]
0x18003a3a6  call    ?GetMaUsbDeviceRemoteInputAllowed@CDevQueryHelper@WFDSConMgr@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_N1@Z; WFDSConMgr::CDevQueryHelper::GetMaUsbDeviceRemoteInputAllowed(std::wstring const &,bool &,bool &)
0x18003a3ab  nop
0x18003a3ac  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18003a3b0  test    rcx, rcx
0x18003a3b3  jz      short loc_18003A3BC
0x18003a3b5  call    cs:__imp_LeaveCriticalSection
0x18003a3bb  nop
0x18003a3bc  lea     rcx, [rbp+var_18]
0x18003a3c0  call    ??1?$unique_ptr@VCMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@U?$default_delete@VCMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@@std@@@std@@QEAA@XZ; std::unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>::~unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>(void)
0x18003a3c5  lea     rdi, [r14+360h]
0x18003a3cc  jmp     short loc_18003A3DE
0x18003a3ce  lea     rdi, [r14+360h]
0x18003a3d5  cmp     [rdi], r12d
0x18003a3d8  jnz     loc_18003A564
0x18003a3de  test    [r14+19Ch], sil
0x18003a3e5  jnz     loc_18003A4B1
0x18003a3eb  cmp     [r14+350h], r12
0x18003a3f2  jz      loc_18003A4B1
0x18003a3f8  mov     rcx, [r15]
0x18003a3fb  mov     rax, [rcx]
0x18003a3fe  lea     rdx, [rbp+lpCriticalSection]
0x18003a402  mov     rax, [rax+8]
0x18003a406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a40b  nop
0x18003a40c  mov     rcx, [r14+0A8h]
0x18003a413  mov     rax, [rcx]
0x18003a416  lea     rdx, [rbp+arg_0]
0x18003a41a  mov     rax, [rax+8]
0x18003a41e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a423  mov     rcx, [r14+0A8h]
0x18003a42a  mov     rax, [rcx]
0x18003a42d  lea     rdx, [rbp+arg_8]
0x18003a431  mov     rax, [rax+10h]
0x18003a435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a43a  nop
0x18003a43b  lea     rcx, [rbp+lpCriticalSection]
0x18003a43f  call    ??1?$unique_ptr@VCMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@U?$default_delete@VCMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@@std@@@std@@QEAA@XZ; std::unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>::~unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>(void)
0x18003a444  cmp     [rbp+arg_8], r12b
0x18003a448  jz      short loc_18003A4A8
0x18003a44a  mov     byte ptr [rbp+lpCriticalSection], r12b
0x18003a44e  mov     [rbp+var_20], r12b
0x18003a452  mov     [rbp+var_1F], r12b
0x18003a456  mov     [rbp+var_1E], r12b
0x18003a45a  lea     rax, [rbp+var_1E]
0x18003a45e  mov     [rsp+50h+var_30], rax; bool *
0x18003a463  lea     r9, [rbp+var_1F]; bool *
0x18003a467  lea     r8, [rbp+var_20]; bool *
0x18003a46b  lea     rdx, [rbp+lpCriticalSection]; bool *
0x18003a46f  mov     rcx, [r14+350h]; this
0x18003a476  call    ?GetUibcState@CMiracastHelper@WFDSConMgr@@QEBAXAEA_N000@Z; WFDSConMgr::CMiracastHelper::GetUibcState(bool &,bool &,bool &,bool &)
0x18003a47b  cmp     byte ptr [rbp+lpCriticalSection], r12b
0x18003a47f  jnz     short loc_18003A486
0x18003a481  mov     esi, r12d
0x18003a484  jmp     short loc_18003A4A8
0x18003a486  cmp     [rbp+var_20], r12b
0x18003a48a  jnz     short loc_18003A493
0x18003a48c  mov     esi, 1
0x18003a491  jmp     short loc_18003A4A8
0x18003a493  cmp     [rbp+var_1F], r12b
0x18003a497  mov     al, [rbp+var_1E]
0x18003a49a  jnz     short loc_18003A49F
0x18003a49c  mov     al, [rbp+arg_0]
0x18003a49f  neg     al
0x18003a4a1  sbb     esi, esi
0x18003a4a3  neg     esi
0x18003a4a5  add     esi, 3
0x18003a4a8  lea     rdi, [r14+360h]
0x18003a4af  jmp     short loc_18003A510
0x18003a4b1  cmp     [r14+378h], r12
0x18003a4b8  jz      loc_18003A564
0x18003a4be  mov     rcx, [r15]
0x18003a4c1  mov     rax, [rcx]
0x18003a4c4  lea     rdx, [rbp+lpCriticalSection]
0x18003a4c8  mov     rax, [rax+8]
0x18003a4cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4d1  nop
0x18003a4d2  mov     rcx, [r14+0A8h]
0x18003a4d9  mov     rax, [rcx]
0x18003a4dc  lea     rdx, [rbp+arg_0]
0x18003a4e0  mov     rax, [rax+18h]
0x18003a4e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4e9  mov     rcx, [r14+0A8h]
0x18003a4f0  mov     rax, [rcx]
0x18003a4f3  lea     rdx, [rbp+arg_8]
0x18003a4f7  mov     rax, [rax+10h]
0x18003a4fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a500  nop
0x18003a501  lea     rcx, [rbp+lpCriticalSection]
0x18003a505  call    ??1?$unique_ptr@VCMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@U?$default_delete@VCMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@@std@@@std@@QEAA@XZ; std::unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>::~unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>(void)
0x18003a50a  cmp     [rbp+arg_8], r12b
0x18003a50e  jnz     short loc_18003A514
0x18003a510  mov     [rdi], esi
0x18003a512  jmp     short loc_18003A564
0x18003a514  mov     rbx, [r14+378h]
0x18003a51b  lea     rcx, [rbx+8]
0x18003a51f  lea     rdx, [rbp+lpCriticalSection]
0x18003a523  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18003a528  mov     sil, [rbx+174h]
0x18003a52f  mov     bl, [rbx+175h]
0x18003a535  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18003a539  test    rcx, rcx
0x18003a53c  jz      short loc_18003A544
0x18003a53e  call    cs:__imp_LeaveCriticalSection
0x18003a544  test    sil, sil
0x18003a547  jz      short loc_18003A556
0x18003a549  neg     bl
0x18003a54b  sbb     eax, eax
0x18003a54d  neg     eax
0x18003a54f  add     eax, 3
0x18003a552  mov     [rdi], eax
0x18003a554  jmp     short loc_18003A564
0x18003a556  mov     al, [rbp+arg_0]
0x18003a559  neg     al
0x18003a55b  sbb     ecx, ecx
0x18003a55d  neg     ecx
0x18003a55f  add     ecx, 3
0x18003a562  mov     [rdi], ecx
0x18003a564  lea     rax, WPP_GLOBAL_Control
0x18003a56b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a572  cmp     rcx, rax
0x18003a575  jz      short loc_18003A5A1
0x18003a577  cmp     byte ptr [rcx+19h], 4
0x18003a57b  jb      short loc_18003A5A1
0x18003a57d  test    byte ptr [rcx+1Ch], 1
0x18003a581  jz      short loc_18003A5A1
0x18003a583  mov     edx, 1Bh
0x18003a588  mov     eax, [rdi]
0x18003a58a  mov     dword ptr [rsp+50h+var_30], eax
0x18003a58e  mov     r9, r14
0x18003a591  lea     r8, WPP_b0264b43d37c3d36bda437b21bf2ef10_Traceguids
0x18003a598  mov     rcx, [rcx+10h]
0x18003a59c  call    WPP_SF_qD
0x18003a5a1  mov     ebx, [rdi]
0x18003a5a3  lea     rcx, [rbp+var_10]
0x18003a5a7  call    ?Unlock@?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAAXXZ; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(void)
0x18003a5ac  nop
0x18003a5ad  mov     rcx, [r15+8]; this
0x18003a5b1  test    rcx, rcx
0x18003a5b4  jz      short loc_18003A5BB
0x18003a5b6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003a5bb  mov     eax, ebx
0x18003a5bd  add     rsp, 50h
0x18003a5c1  pop     r15
0x18003a5c3  pop     r14
0x18003a5c5  pop     r12
0x18003a5c7  pop     rdi
0x18003a5c8  pop     rsi
0x18003a5c9  pop     rbx
0x18003a5ca  pop     rbp
0x18003a5cb  retn
```
