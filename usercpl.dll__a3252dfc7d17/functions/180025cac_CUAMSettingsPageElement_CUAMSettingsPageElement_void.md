# CUAMSettingsPageElement::~CUAMSettingsPageElement(void)

- ea: `0x180025cac`
- end: `0x180025e8a`
- name: `??1CUAMSettingsPageElement@@UEAA@XZ`
- size: `478`
- prototype: `void __fastcall(CUAMSettingsPageElement *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800260c0`

## callees

- `0x18000dafc`
- `0x180025bcc`
- `0x180025cac`
- `0x18002be04`
- `0x18006409c`
- `0x180078010`

## import_xrefs

- `DUI70!??1Element@DirectUI@@UEAA@XZ` at `0x180025e83`
- `DUser!DeleteHandle` at `0x180025cf0`
- `DUser!DeleteHandle` at `0x180025d33`
- `DUser!DeleteHandle` at `0x180025e0d`
- `DUser!DeleteHandle` at `0x180025e50`
- `DUser!DeleteHandle` at `0x180025cf0`
- `DUser!DeleteHandle` at `0x180025d33`
- `DUser!DeleteHandle` at `0x180025e0d`
- `DUser!DeleteHandle` at `0x180025e50`

## pseudocode

```c
void __fastcall CUAMSettingsPageElement::~CUAMSettingsPageElement(CUAMSettingsPageElement *this)
{
  _QWORD *v2; // rdi
  __int64 v3; // rcx
  _QWORD *v4; // rdi
  __int64 v5; // rcx
  CPrivateNotificationWindow *v6; // rcx
  __int64 v7; // rcx
  CMachineLockSettings *v8; // rcx
  void *v9; // rdi
  void (__fastcall ***v10)(_QWORD, __int64); // rcx
  _QWORD *v11; // rdi
  __int64 v12; // rcx
  _QWORD *v13; // rdi
  __int64 v14; // rcx

  *(_QWORD *)this = &CUAMSettingsPageElement::`vftable'{for `DirectUI::Element'};
  v2 = (_QWORD *)*((_QWORD *)this + 34);
  *((_QWORD *)this + 25) = &CUAMSettingsPageElement::`vftable'{for `CPrivateNotificationWindowSink'};
  *((_QWORD *)this + 34) = 0;
  if ( v2 )
  {
    if ( *v2 )
    {
      DeleteHandle(*v2);
      *v2 = 0;
    }
    v3 = v2[1];
    if ( v3 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 8LL))(v3, 1);
    operator delete(v2);
  }
  v4 = (_QWORD *)*((_QWORD *)this + 35);
  *((_QWORD *)this + 35) = 0;
  if ( v4 )
  {
    if ( *v4 )
    {
      DeleteHandle(*v4);
      *v4 = 0;
    }
    v5 = v4[1];
    if ( v5 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 8LL))(v5, 1);
    operator delete(v4);
  }
  v6 = (CPrivateNotificationWindow *)*((_QWORD *)this + 26);
  if ( v6 )
  {
    CPrivateNotificationWindow::DisconnectAndRelease(v6);
    *((_QWORD *)this + 26) = 0;
  }
  v7 = *((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = (CMachineLockSettings *)*((_QWORD *)this + 32);
  if ( v8 )
  {
    CMachineLockSettings::SaveSelection(v8);
    v9 = (void *)*((_QWORD *)this + 32);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9, 0xFFFFFFFF) == 1 && v9 )
    {
      CTSimpleArray<CMachineLockSettings::DELAY_LOCK_ITEM,4294967294,CTPolicyCoTaskMem<CMachineLockSettings::DELAY_LOCK_ITEM>,CSimpleArrayStandardCompareHelper<CMachineLockSettings::DELAY_LOCK_ITEM>,CSimpleArrayStandardMergeHelper<CMachineLockSettings::DELAY_LOCK_ITEM>>::~CTSimpleArray<CMachineLockSettings::DELAY_LOCK_ITEM,4294967294,CTPolicyCoTaskMem<CMachineLockSettings::DELAY_LOCK_ITEM>,CSimpleArrayStandardCompareHelper<CMachineLockSettings::DELAY_LOCK_ITEM>,CSimpleArrayStandardMergeHelper<CMachineLockSettings::DELAY_LOCK_ITEM>>((__int64)v9 + 8);
      operator delete(v9);
    }
    *((_QWORD *)this + 32) = 0;
  }
  v10 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 28);
  if ( v10 )
  {
    (**v10)(v10, 1);
    *((_QWORD *)this + 28) = 0;
  }
  v11 = (_QWORD *)*((_QWORD *)this + 35);
  *((_QWORD *)this + 35) = 0;
  if ( v11 )
  {
    if ( *v11 )
    {
      DeleteHandle(*v11);
      *v11 = 0;
    }
    v12 = v11[1];
    if ( v12 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 8LL))(v12, 1);
    operator delete(v11);
  }
  v13 = (_QWORD *)*((_QWORD *)this + 34);
  *((_QWORD *)this + 34) = 0;
  if ( v13 )
  {
    if ( *v13 )
    {
      DeleteHandle(*v13);
      *v13 = 0;
    }
    v14 = v13[1];
    if ( v14 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 8LL))(v14, 1);
    operator delete(v13);
  }
  DirectUI::Element::~Element(this);
}

```

## disassembly

```asm
0x180025cac  push    rbx
0x180025cae  push    rbp
0x180025caf  push    rsi
0x180025cb0  push    rdi
0x180025cb1  sub     rsp, 28h
0x180025cb5  xor     esi, esi
0x180025cb7  lea     rax, ??_7CUAMSettingsPageElement@@6BElement@DirectUI@@@; const CUAMSettingsPageElement::`vftable'{for `DirectUI::Element'}
0x180025cbe  mov     [rcx], rax
0x180025cc1  mov     rbx, rcx
0x180025cc4  mov     rdi, [rcx+110h]
0x180025ccb  lea     rax, ??_7CUAMSettingsPageElement@@6BCPrivateNotificationWindowSink@@@; const CUAMSettingsPageElement::`vftable'{for `CPrivateNotificationWindowSink'}
0x180025cd2  mov     [rcx+0C8h], rax
0x180025cd9  mov     [rcx+110h], rsi
0x180025ce0  lea     ebp, [rsi+1]
0x180025ce3  test    rdi, rdi
0x180025ce6  jz      short loc_180025D18
0x180025ce8  mov     rcx, [rdi]
0x180025ceb  test    rcx, rcx
0x180025cee  jz      short loc_180025CF9
0x180025cf0  call    cs:__imp_DeleteHandle
0x180025cf6  mov     [rdi], rsi
0x180025cf9  mov     rcx, [rdi+8]
0x180025cfd  test    rcx, rcx
0x180025d00  jz      short loc_180025D10
0x180025d02  mov     rax, [rcx]
0x180025d05  mov     edx, ebp
0x180025d07  mov     rax, [rax+8]
0x180025d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d10  mov     rcx, rdi; lpMem
0x180025d13  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025d18  mov     rdi, [rbx+118h]
0x180025d1f  mov     [rbx+118h], rsi
0x180025d26  test    rdi, rdi
0x180025d29  jz      short loc_180025D5B
0x180025d2b  mov     rcx, [rdi]
0x180025d2e  test    rcx, rcx
0x180025d31  jz      short loc_180025D3C
0x180025d33  call    cs:__imp_DeleteHandle
0x180025d39  mov     [rdi], rsi
0x180025d3c  mov     rcx, [rdi+8]
0x180025d40  test    rcx, rcx
0x180025d43  jz      short loc_180025D53
0x180025d45  mov     rax, [rcx]
0x180025d48  mov     edx, ebp
0x180025d4a  mov     rax, [rax+8]
0x180025d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d53  mov     rcx, rdi; lpMem
0x180025d56  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025d5b  mov     rcx, [rbx+0D0h]; this
0x180025d62  test    rcx, rcx
0x180025d65  jz      short loc_180025D73
0x180025d67  call    ?DisconnectAndRelease@CPrivateNotificationWindow@@QEAAXXZ; CPrivateNotificationWindow::DisconnectAndRelease(void)
0x180025d6c  mov     [rbx+0D0h], rsi
0x180025d73  mov     rcx, [rbx+0D8h]
0x180025d7a  mov     [rbx+0D8h], rsi
0x180025d81  test    rcx, rcx
0x180025d84  jz      short loc_180025D92
0x180025d86  mov     rax, [rcx]
0x180025d89  mov     rax, [rax+10h]
0x180025d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d92  mov     rcx, [rbx+100h]; this
0x180025d99  test    rcx, rcx
0x180025d9c  jz      short loc_180025DD2
0x180025d9e  call    ?SaveSelection@CMachineLockSettings@@QEAAJXZ; CMachineLockSettings::SaveSelection(void)
0x180025da3  mov     rdi, [rbx+100h]
0x180025daa  or      eax, 0FFFFFFFFh
0x180025dad  lock xadd [rdi], eax
0x180025db1  cmp     eax, ebp
0x180025db3  jnz     short loc_180025DCB
0x180025db5  test    rdi, rdi
0x180025db8  jz      short loc_180025DCB
0x180025dba  lea     rcx, [rdi+8]
0x180025dbe  call    ??1?$CTSimpleArray@UDELAY_LOCK_ITEM@CMachineLockSettings@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UDELAY_LOCK_ITEM@CMachineLockSettings@@@@V?$CSimpleArrayStandardCompareHelper@UDELAY_LOCK_ITEM@CMachineLockSettings@@@@V?$CSimpleArrayStandardMergeHelper@UDELAY_LOCK_ITEM@CMachineLockSettings@@@@@@QEAA@XZ; CTSimpleArray<CMachineLockSettings::DELAY_LOCK_ITEM,4294967294,CTPolicyCoTaskMem<CMachineLockSettings::DELAY_LOCK_ITEM>,CSimpleArrayStandardCompareHelper<CMachineLockSettings::DELAY_LOCK_ITEM>,CSimpleArrayStandardMergeHelper<CMachineLockSettings::DELAY_LOCK_ITEM>>::~CTSimpleArray<CMachineLockSettings::DELAY_LOCK_ITEM,4294967294,CTPolicyCoTaskMem<CMachineLockSettings::DELAY_LOCK_ITEM>,CSimpleArrayStandardCompareHelper<CMachineLockSettings::DELAY_LOCK_ITEM>,CSimpleArrayStandardMergeHelper<CMachineLockSettings::DELAY_LOCK_ITEM>>(void)
0x180025dc3  mov     rcx, rdi; lpMem
0x180025dc6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025dcb  mov     [rbx+100h], rsi
0x180025dd2  mov     rcx, [rbx+0E0h]
0x180025dd9  test    rcx, rcx
0x180025ddc  jz      short loc_180025DF2
0x180025dde  mov     rax, [rcx]
0x180025de1  mov     edx, ebp
0x180025de3  mov     rax, [rax]
0x180025de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025deb  mov     [rbx+0E0h], rsi
0x180025df2  mov     rdi, [rbx+118h]
0x180025df9  mov     [rbx+118h], rsi
0x180025e00  test    rdi, rdi
0x180025e03  jz      short loc_180025E35
0x180025e05  mov     rcx, [rdi]
0x180025e08  test    rcx, rcx
0x180025e0b  jz      short loc_180025E16
0x180025e0d  call    cs:__imp_DeleteHandle
0x180025e13  mov     [rdi], rsi
0x180025e16  mov     rcx, [rdi+8]
0x180025e1a  test    rcx, rcx
0x180025e1d  jz      short loc_180025E2D
0x180025e1f  mov     rax, [rcx]
0x180025e22  mov     edx, ebp
0x180025e24  mov     rax, [rax+8]
0x180025e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e2d  mov     rcx, rdi; lpMem
0x180025e30  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025e35  mov     rdi, [rbx+110h]
0x180025e3c  mov     [rbx+110h], rsi
0x180025e43  test    rdi, rdi
0x180025e46  jz      short loc_180025E78
0x180025e48  mov     rcx, [rdi]
0x180025e4b  test    rcx, rcx
0x180025e4e  jz      short loc_180025E59
0x180025e50  call    cs:__imp_DeleteHandle
0x180025e56  mov     [rdi], rsi
0x180025e59  mov     rcx, [rdi+8]
0x180025e5d  test    rcx, rcx
0x180025e60  jz      short loc_180025E70
0x180025e62  mov     rax, [rcx]
0x180025e65  mov     edx, ebp
0x180025e67  mov     rax, [rax+8]
0x180025e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e70  mov     rcx, rdi; lpMem
0x180025e73  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025e78  mov     rcx, rbx
0x180025e7b  add     rsp, 28h
0x180025e7f  pop     rdi
0x180025e80  pop     rsi
0x180025e81  pop     rbp
0x180025e82  pop     rbx
0x180025e83  jmp     cs:__imp_??1Element@DirectUI@@UEAA@XZ; DirectUI::Element::~Element(void)
```
