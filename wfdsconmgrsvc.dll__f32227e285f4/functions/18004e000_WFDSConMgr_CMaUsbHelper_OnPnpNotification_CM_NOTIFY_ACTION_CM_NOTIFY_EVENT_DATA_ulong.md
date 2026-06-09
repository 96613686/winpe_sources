# WFDSConMgr::CMaUsbHelper::OnPnpNotification(_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)

- ea: `0x18004e000`
- end: `0x18004e2a7`
- name: `?OnPnpNotification@CMaUsbHelper@WFDSConMgr@@AEAAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18004e6c0`

## callees

- `0x1800059c0`
- `0x180006740`
- `0x180006780`
- `0x18002f5f0`
- `0x18004e000`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e19c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e19c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e221`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18004e192`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18004e217`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18004e192`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18004e217`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e294`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e294`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WFDSConMgr::CMaUsbHelper::OnPnpNotification(__int64 a1, int a2, struct _RTL_CRITICAL_SECTION *a3)
{
  PVOID *v5; // r10
  struct _TP_CALLBACK_ENVIRON_V3 *v6; // rdi
  int v7; // eax
  DWORD LastError; // eax
  PVOID *v9; // rcx
  DWORD v10; // eax
  PVOID *v11; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+80h] [rbp+18h] BYREF

  lpCriticalSection = a3;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, a1, a2);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 != 2 && a2 != 3 && (unsigned int)(a2 - 4) >= 2 )
  {
    if ( v5 != &WPP_GLOBAL_Control && *((_BYTE *)v5 + 25) >= 4u && (*((_BYTE *)v5 + 28) & 1) != 0 )
      WPP_SF_q(v5[2], 65, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, a1);
    return;
  }
  WFDSConMgr::CriticalSection::Lock(a1 + 8, &lpCriticalSection);
  if ( !*(_QWORD *)(a1 + 264) )
  {
    v6 = (struct _TP_CALLBACK_ENVIRON_V3 *)(a1 + 128);
LABEL_32:
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_33;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, a1);
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 48) + 24LL))(
         *(_QWORD *)(a1 + 48),
         *(_QWORD *)(a1 + 264));
  if ( v7
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, a1, v7);
  }
  std::shared_ptr<WFDSConMgr::CWFDClientHandle>::reset(a1 + 264);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, a1);
  }
  v6 = (struct _TP_CALLBACK_ENVIRON_V3 *)(a1 + 128);
  if ( TrySubmitThreadpoolCallback(
         WFDSConMgr::CMaUsbHelper::DeferredDriverRemovalNotificationCallback,
         (PVOID)a1,
         (PTP_CALLBACK_ENVIRON)(a1 + 128)) )
  {
    goto LABEL_32;
  }
  LastError = GetLastError();
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, a1, LastError);
    goto LABEL_32;
  }
LABEL_33:
  if ( (unsigned int)(a2 - 3) <= 2 )
  {
    if ( v9 != &WPP_GLOBAL_Control && *((_BYTE *)v9 + 25) >= 4u && (*((_BYTE *)v9 + 28) & 1) != 0 )
      WPP_SF_q(v9[2], 62, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, a1);
    if ( !TrySubmitThreadpoolCallback(WFDSConMgr::CMaUsbHelper::DeferredUnregisterPnpCallback, (PVOID)a1, v6) )
    {
      v10 = GetLastError();
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 25)
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_44:
        if ( a2 == 3 && v11 != &WPP_GLOBAL_Control && *((_BYTE *)v11 + 25) && (*((_BYTE *)v11 + 28) & 1) != 0 )
          WPP_SF_q(v11[2], 64, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, a1);
        goto LABEL_49;
      }
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids, a1, v10);
    }
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_44;
  }
LABEL_49:
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18004e000  mov     [rsp+lpCriticalSection], r8
0x18004e005  push    rbx
0x18004e006  push    rbp
0x18004e007  push    rsi
0x18004e008  push    rdi
0x18004e009  push    r14
0x18004e00b  push    r15
0x18004e00d  sub     rsp, 38h
0x18004e011  mov     esi, edx
0x18004e013  mov     rbx, rcx
0x18004e016  lea     r14, WPP_GLOBAL_Control
0x18004e01d  mov     bpl, 1
0x18004e020  lea     r15, WPP_5355f4da57723a19ba8345d2e5cc961d_Traceguids
0x18004e027  mov     r10, cs:WPP_GLOBAL_Control
0x18004e02e  cmp     r10, r14
0x18004e031  jz      short loc_18004E05F
0x18004e033  cmp     byte ptr [r10+19h], 4
0x18004e038  jb      short loc_18004E05F
0x18004e03a  test    [r10+1Ch], bpl
0x18004e03e  jz      short loc_18004E05F
0x18004e040  mov     edx, 39h ; '9'
0x18004e045  mov     [rsp+68h+var_48], esi
0x18004e049  mov     r9, rcx
0x18004e04c  mov     r8, r15
0x18004e04f  mov     rcx, [r10+10h]
0x18004e053  call    WPP_SF_qD
0x18004e058  mov     r10, cs:WPP_GLOBAL_Control
0x18004e05f  mov     ecx, esi
0x18004e061  sub     ecx, 2
0x18004e064  jz      short loc_18004E0AC
0x18004e066  sub     ecx, 1
0x18004e069  jz      short loc_18004E0AC
0x18004e06b  sub     ecx, 1
0x18004e06e  jz      short loc_18004E0AC
0x18004e070  cmp     ecx, 1
0x18004e073  jz      short loc_18004E0AC
0x18004e075  cmp     r10, r14
0x18004e078  jz      loc_18004E29A
0x18004e07e  cmp     byte ptr [r10+19h], 4
0x18004e083  jb      loc_18004E29A
0x18004e089  test    [r10+1Ch], bpl
0x18004e08d  jz      loc_18004E29A
0x18004e093  mov     edx, 41h ; 'A'
0x18004e098  mov     r9, rbx
0x18004e09b  mov     r8, r15
0x18004e09e  mov     rcx, [r10+10h]
0x18004e0a2  call    WPP_SF_q
0x18004e0a7  jmp     loc_18004E29A
0x18004e0ac  lea     rcx, [rbx+8]
0x18004e0b0  lea     rdx, [rsp+68h+lpCriticalSection]
0x18004e0b8  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18004e0bd  nop
0x18004e0be  lea     rdi, [rbx+108h]
0x18004e0c5  cmp     qword ptr [rdi], 0
0x18004e0c9  jnz     short loc_18004E0D7
0x18004e0cb  lea     rdi, [rbx+80h]
0x18004e0d2  jmp     loc_18004E1D2
0x18004e0d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e0de  cmp     rcx, r14
0x18004e0e1  jz      short loc_18004E103
0x18004e0e3  cmp     byte ptr [rcx+19h], 4
0x18004e0e7  jb      short loc_18004E103
0x18004e0e9  test    [rcx+1Ch], bpl
0x18004e0ed  jz      short loc_18004E103
0x18004e0ef  mov     edx, 3Ah ; ':'
0x18004e0f4  mov     r9, rbx
0x18004e0f7  mov     r8, r15
0x18004e0fa  mov     rcx, [rcx+10h]
0x18004e0fe  call    WPP_SF_q
0x18004e103  mov     rcx, [rbx+30h]
0x18004e107  mov     rax, [rcx]
0x18004e10a  mov     rdx, [rdi]
0x18004e10d  mov     rax, [rax+18h]
0x18004e111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e116  test    eax, eax
0x18004e118  jz      short loc_18004E14A
0x18004e11a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e121  cmp     rcx, r14
0x18004e124  jz      short loc_18004E14A
0x18004e126  cmp     [rcx+19h], bpl
0x18004e12a  jb      short loc_18004E14A
0x18004e12c  test    [rcx+1Ch], bpl
0x18004e130  jz      short loc_18004E14A
0x18004e132  mov     edx, 3Bh ; ';'
0x18004e137  mov     [rsp+68h+var_48], eax
0x18004e13b  mov     r9, rbx
0x18004e13e  mov     r8, r15
0x18004e141  mov     rcx, [rcx+10h]
0x18004e145  call    WPP_SF_qD
0x18004e14a  mov     rcx, rdi
0x18004e14d  call    ?reset@?$shared_ptr@VCWFDClientHandle@WFDSConMgr@@@std@@QEAAXXZ; std::shared_ptr<WFDSConMgr::CWFDClientHandle>::reset(void)
0x18004e152  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e159  cmp     rcx, r14
0x18004e15c  jz      short loc_18004E17E
0x18004e15e  cmp     byte ptr [rcx+19h], 4
0x18004e162  jb      short loc_18004E17E
0x18004e164  test    [rcx+1Ch], bpl
0x18004e168  jz      short loc_18004E17E
0x18004e16a  mov     edx, 3Ch ; '<'
0x18004e16f  mov     r9, rbx
0x18004e172  mov     r8, r15
0x18004e175  mov     rcx, [rcx+10h]
0x18004e179  call    WPP_SF_q
0x18004e17e  lea     rdi, [rbx+80h]
0x18004e185  mov     r8, rdi; pcbe
0x18004e188  mov     rdx, rbx; pv
0x18004e18b  lea     rcx, ?DeferredDriverRemovalNotificationCallback@CMaUsbHelper@WFDSConMgr@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18004e192  call    cs:__imp_TrySubmitThreadpoolCallback
0x18004e198  test    eax, eax
0x18004e19a  jnz     short loc_18004E1D2
0x18004e19c  call    cs:__imp_GetLastError
0x18004e1a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e1a9  cmp     rcx, r14
0x18004e1ac  jz      short loc_18004E1D9
0x18004e1ae  cmp     [rcx+19h], bpl
0x18004e1b2  jb      short loc_18004E1D9
0x18004e1b4  test    [rcx+1Ch], bpl
0x18004e1b8  jz      short loc_18004E1D9
0x18004e1ba  mov     edx, 3Dh ; '='
0x18004e1bf  mov     [rsp+68h+var_48], eax
0x18004e1c3  mov     r9, rbx
0x18004e1c6  mov     r8, r15
0x18004e1c9  mov     rcx, [rcx+10h]
0x18004e1cd  call    WPP_SF_qD
0x18004e1d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e1d9  lea     eax, [rsi-3]
0x18004e1dc  cmp     eax, 2
0x18004e1df  ja      loc_18004E287
0x18004e1e5  cmp     rcx, r14
0x18004e1e8  jz      short loc_18004E20A
0x18004e1ea  cmp     byte ptr [rcx+19h], 4
0x18004e1ee  jb      short loc_18004E20A
0x18004e1f0  test    [rcx+1Ch], bpl
0x18004e1f4  jz      short loc_18004E20A
0x18004e1f6  mov     edx, 3Eh ; '>'
0x18004e1fb  mov     r9, rbx
0x18004e1fe  mov     r8, r15
0x18004e201  mov     rcx, [rcx+10h]
0x18004e205  call    WPP_SF_q
0x18004e20a  mov     r8, rdi; pcbe
0x18004e20d  mov     rdx, rbx; pv
0x18004e210  lea     rcx, ?DeferredUnregisterPnpCallback@CMaUsbHelper@WFDSConMgr@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18004e217  call    cs:__imp_TrySubmitThreadpoolCallback
0x18004e21d  test    eax, eax
0x18004e21f  jnz     short loc_18004E257
0x18004e221  call    cs:__imp_GetLastError
0x18004e227  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e22e  cmp     rcx, r14
0x18004e231  jz      short loc_18004E25E
0x18004e233  cmp     [rcx+19h], bpl
0x18004e237  jb      short loc_18004E25E
0x18004e239  test    [rcx+1Ch], bpl
0x18004e23d  jz      short loc_18004E25E
0x18004e23f  mov     edx, 3Fh ; '?'
0x18004e244  mov     [rsp+68h+var_48], eax
0x18004e248  mov     r9, rbx
0x18004e24b  mov     r8, r15
0x18004e24e  mov     rcx, [rcx+10h]
0x18004e252  call    WPP_SF_qD
0x18004e257  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e25e  cmp     esi, 3
0x18004e261  jnz     short loc_18004E287
0x18004e263  cmp     rcx, r14
0x18004e266  jz      short loc_18004E287
0x18004e268  cmp     [rcx+19h], bpl
0x18004e26c  jb      short loc_18004E287
0x18004e26e  test    [rcx+1Ch], bpl
0x18004e272  jz      short loc_18004E287
0x18004e274  lea     edx, [rsi+3Dh]
0x18004e277  mov     r9, rbx
0x18004e27a  mov     r8, r15
0x18004e27d  mov     rcx, [rcx+10h]
0x18004e281  call    WPP_SF_q
0x18004e286  nop
0x18004e287  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x18004e28f  test    rcx, rcx
0x18004e292  jz      short loc_18004E29A
0x18004e294  call    cs:__imp_LeaveCriticalSection
0x18004e29a  add     rsp, 38h
0x18004e29e  pop     r15
0x18004e2a0  pop     r14
0x18004e2a2  pop     rdi
0x18004e2a3  pop     rsi
0x18004e2a4  pop     rbp
0x18004e2a5  pop     rbx
0x18004e2a6  retn
```
