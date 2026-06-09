# CWdsTransportSetupManager::DeregisterContentProvider(ushort *)

- ea: `0x18000a4b0`
- end: `0x18000a604`
- name: `?DeregisterContentProvider@CWdsTransportSetupManager@@UEAAJPEAG@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWdsTransportSetupManager *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180009e20`
- `0x18000a4b0`

## import_xrefs

- `WdsCommonLib!?DeleteSubkey@CRegKey@@QEAAKPEBG@Z` at `0x18000a584`
- `WdsCommonLib!?DeleteSubkey@CRegKey@@QEAAKPEBG@Z` at `0x18000a584`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000a535`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000a535`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a4f4`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a55d`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a5cc`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a4f4`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a55d`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a5cc`

## string_xrefs

- `0x18000a516`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSMC\Providers`
- `0x18000a54a`: `Failed to open the server content provider key with error 0x%lx.\n`

## pseudocode

```c
__int64 __fastcall CWdsTransportSetupManager::DeregisterContentProvider(
        CWdsTransportSetupManager *this,
        unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  unsigned int v5; // eax
  int v6; // edi
  int v7; // ebx
  int v8; // eax
  __int64 v10; // [rsp+20h] [rbp-28h]
  _BYTE v11[24]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF

  v4 = 0;
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v11, (char *)this + 80);
  v12 = 0;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportSetupManager::DeregisterContentProvider(0x%p)",
    this);
  if ( !a2 || !*a2 )
  {
    v4 = -2147024809;
    goto LABEL_15;
  }
  v5 = CRegKey::RemoteOpen(
         (CRegKey *)&v12,
         *(const unsigned __int16 **)(*((_QWORD *)this + 8) + 112LL),
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSMC\\Providers",
         0x20006u);
  v6 = v5;
  if ( !v5 )
  {
    v8 = CRegKey::DeleteSubkey((CRegKey *)&v12, a2);
    if ( !v8 )
      goto LABEL_15;
    if ( v8 == 2 )
    {
      v4 = -1055915772;
      goto LABEL_15;
    }
    if ( v8 <= 0 )
    {
      v4 = v8;
      goto LABEL_15;
    }
    v7 = (unsigned __int16)v8;
    goto LABEL_7;
  }
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x80000u,
    L"Failed to open the server content provider key with error 0x%lx.\n",
    v5);
  if ( v6 > 0 )
  {
    v7 = (unsigned __int16)v6;
LABEL_7:
    v4 = v7 | 0x80070000;
    goto LABEL_15;
  }
  v4 = v6;
LABEL_15:
  LODWORD(v10) = v4;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportSetupManager::DeregisterContentProvider(0x%p) =%x",
    this,
    v10);
  CRegKey::Close((CRegKey *)&v12);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v11);
  return v4;
}

```

## disassembly

```asm
0x18000a4b0  mov     rax, rsp
0x18000a4b3  mov     [rax+10h], rbx
0x18000a4b7  mov     [rax+18h], rbp
0x18000a4bb  mov     [rax+20h], rsi
0x18000a4bf  push    rdi
0x18000a4c0  sub     rsp, 40h
0x18000a4c4  mov     rsi, rdx
0x18000a4c7  mov     rbp, rcx
0x18000a4ca  lea     rdx, [rcx+50h]
0x18000a4ce  xor     ebx, ebx
0x18000a4d0  lea     rcx, [rax-18h]
0x18000a4d4  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000a4d9  mov     r9, rbp
0x18000a4dc  mov     [rsp+48h+arg_0], rbx
0x18000a4e1  lea     r8, aCwdstransports_20; "-> CWdsTransportSetupManager::Deregiste"...
0x18000a4e8  mov     edx, 10000h
0x18000a4ed  lea     rcx, qword_18003B770
0x18000a4f4  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000a4fb  nop     dword ptr [rax+rax+00h]
0x18000a500  test    rsi, rsi
0x18000a503  jz      loc_18000A5AD
0x18000a509  cmp     [rsi], bx
0x18000a50c  jz      loc_18000A5AD
0x18000a512  mov     rdx, [rbp+40h]
0x18000a516  lea     r9, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\WD"...
0x18000a51d  mov     r8, 0FFFFFFFF80000002h
0x18000a524  mov     [rsp+48h+var_28], 20006h
0x18000a52c  lea     rcx, [rsp+48h+arg_0]
0x18000a531  mov     rdx, [rdx+70h]
0x18000a535  call    cs:__imp_?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z; CRegKey::RemoteOpen(ushort const *,HKEY__ *,ushort const *,ulong)
0x18000a53c  nop     dword ptr [rax+rax+00h]
0x18000a541  mov     edi, eax
0x18000a543  test    eax, eax
0x18000a545  jz      short loc_18000A57C
0x18000a547  mov     r9d, eax
0x18000a54a  lea     r8, aFailedToOpenTh_0; "Failed to open the server content provi"...
0x18000a551  mov     edx, 80000h
0x18000a556  lea     rcx, qword_18003B770
0x18000a55d  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000a564  nop     dword ptr [rax+rax+00h]
0x18000a569  test    edi, edi
0x18000a56b  jg      short loc_18000A571
0x18000a56d  mov     ebx, edi
0x18000a56f  jmp     short loc_18000A5B2
0x18000a571  movzx   ebx, di
0x18000a574  or      ebx, 80070000h
0x18000a57a  jmp     short loc_18000A5B2
0x18000a57c  mov     rdx, rsi
0x18000a57f  lea     rcx, [rsp+48h+arg_0]
0x18000a584  call    cs:__imp_?DeleteSubkey@CRegKey@@QEAAKPEBG@Z; CRegKey::DeleteSubkey(ushort const *)
0x18000a58b  nop     dword ptr [rax+rax+00h]
0x18000a590  test    eax, eax
0x18000a592  jz      short loc_18000A5B2
0x18000a594  cmp     eax, 2
0x18000a597  jnz     short loc_18000A5A0
0x18000a599  mov     ebx, 0C1100104h
0x18000a59e  jmp     short loc_18000A5B2
0x18000a5a0  test    eax, eax
0x18000a5a2  jg      short loc_18000A5A8
0x18000a5a4  mov     ebx, eax
0x18000a5a6  jmp     short loc_18000A5B2
0x18000a5a8  movzx   ebx, ax
0x18000a5ab  jmp     short loc_18000A574
0x18000a5ad  mov     ebx, 80070057h
0x18000a5b2  mov     r9, rbp
0x18000a5b5  mov     [rsp+48h+var_28], ebx
0x18000a5b9  lea     r8, aCwdstransports_36; "<- CWdsTransportSetupManager::Deregiste"...
0x18000a5c0  mov     edx, 10000h
0x18000a5c5  lea     rcx, qword_18003B770
0x18000a5cc  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000a5d3  nop     dword ptr [rax+rax+00h]
0x18000a5d8  lea     rcx, [rsp+48h+arg_0]; this
0x18000a5dd  call    ?Close@CRegKey@@QEAAXXZ; CRegKey::Close(void)
0x18000a5e2  lea     rcx, [rsp+48h+var_18]
0x18000a5e7  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000a5ec  mov     rbp, [rsp+48h+arg_10]
0x18000a5f1  mov     eax, ebx
0x18000a5f3  mov     rbx, [rsp+48h+arg_8]
0x18000a5f8  mov     rsi, [rsp+48h+arg_18]
0x18000a5fd  add     rsp, 40h
0x18000a601  pop     rdi
0x18000a602  retn
```
