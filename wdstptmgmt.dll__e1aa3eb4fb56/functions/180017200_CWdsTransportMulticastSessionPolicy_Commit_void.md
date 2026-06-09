# CWdsTransportMulticastSessionPolicy::Commit(void)

- ea: `0x180017200`
- end: `0x1800174bb`
- name: `?Commit@CWdsTransportMulticastSessionPolicy@@UEAAJXZ`
- size: `699`
- prototype: `__int64 __fastcall(CWdsTransportMulticastSessionPolicy *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180009254`
- `0x180009e20`
- `0x180017200`
- `0x18001811c`
- `0x180018240`

## import_xrefs

- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18001727a`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18001727a`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x180017341`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18001738c`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x1800173d3`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18001741a`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x180017341`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18001738c`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x1800173d3`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18001741a`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001723f`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800172f5`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180017457`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180017488`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001723f`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800172f5`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180017457`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180017488`

## string_xrefs

- `0x180017444`: `Will notify WDS Transport services of the settings modification.\n`
- `0x18001725b`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSMC\Protocol`
- `0x180017227`: `-> CWdsTransportMulticastSessionPolicy::Commit(0x%p)`
- `0x180017475`: `<- CWdsTransportMulticastSessionPolicy::Commit(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportMulticastSessionPolicy::Commit(CWdsTransportMulticastSessionPolicy *this)
{
  __int64 v2; // rbx
  unsigned int v3; // esi
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // eax
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v21; // [rsp+20h] [rbp-28h]
  _BYTE v22[24]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v23; // [rsp+50h] [rbp+8h] BYREF

  LODWORD(v2) = 0;
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v22, (char *)this + 80);
  v23 = 0;
  v3 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportMulticastSessionPolicy::Commit(0x%p)", this);
  if ( !*((_DWORD *)this + 32) )
    goto LABEL_28;
  v2 = CRegKey::RemoteOpen(
         (CRegKey *)&v23,
         *(const unsigned __int16 **)(*((_QWORD *)this + 8) + 112LL),
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSMC\\Protocol",
         0x20006u);
  if ( (unsigned int)ElValidateWin32_11(v2, v4, v5, 1167) )
    goto LABEL_3;
  v8 = *((_DWORD *)this + 32);
  if ( (v8 & 1) == 0 )
    goto LABEL_18;
  LODWORD(v2) = 0;
  v9 = *((_DWORD *)this + 33);
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        if ( v11 == 1 )
        {
          v3 = 3;
        }
        else
        {
          LODWORD(v2) = -1055915746;
          CTrace::Trace(
            (CTrace *)qword_18003B770,
            0x80000u,
            L"Error: Encountered an unknown WdsTptMgmt Slow-Client Handling type: %u\n");
        }
      }
      else
      {
        v3 = 2;
      }
    }
    else
    {
      v3 = 1;
    }
  }
  else
  {
    LODWORD(v2) = -1055915746;
  }
  if ( (int)ElValidateHr_12((unsigned int)v2, v6, v7, 1180) >= 0 )
  {
    v2 = CRegKey::SetValueDword((CRegKey *)&v23, L"TpSlowClientHandling", v3);
    if ( (unsigned int)ElValidateWin32_11(v2, v12, v13, 1184) )
      goto LABEL_3;
    *((_DWORD *)this + 32) &= ~1u;
    v8 = *((_DWORD *)this + 32);
LABEL_18:
    if ( (v8 & 2) != 0 )
    {
      v2 = CRegKey::SetValueDword((CRegKey *)&v23, L"TpAutoKickThreshold", *((_DWORD *)this + 34) << 10);
      if ( (unsigned int)ElValidateWin32_11(v2, v14, v15, 1200) )
        goto LABEL_3;
      *((_DWORD *)this + 32) &= ~2u;
      v8 = *((_DWORD *)this + 32);
    }
    if ( (v8 & 4) != 0 )
    {
      v2 = CRegKey::SetValueDword((CRegKey *)&v23, L"TpMultiStreamCount", *((_DWORD *)this + 35));
      if ( (unsigned int)ElValidateWin32_11(v2, v16, v17, 1213) )
        goto LABEL_3;
      *((_DWORD *)this + 32) &= ~4u;
      v8 = *((_DWORD *)this + 32);
    }
    if ( (v8 & 8) == 0 )
    {
LABEL_27:
      CTrace::Trace(
        (CTrace *)qword_18003B770,
        0x10000u,
        L"Will notify WDS Transport services of the settings modification.\n");
      LODWORD(v2) = CWdsTransportServer::SignalSettingsChange(*((CWdsTransportServer **)this + 8));
      goto LABEL_28;
    }
    v2 = CRegKey::SetValueDword((CRegKey *)&v23, L"TpSlowClientFallback", *((_DWORD *)this + 36));
    if ( !(unsigned int)ElValidateWin32_11(v2, v18, v19, 1226) )
    {
      *((_DWORD *)this + 32) &= ~8u;
      goto LABEL_27;
    }
LABEL_3:
    if ( (int)v2 > 0 )
      LODWORD(v2) = (unsigned __int16)v2 | 0x80070000;
  }
LABEL_28:
  LODWORD(v21) = v2;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportMulticastSessionPolicy::Commit(0x%p) =%x",
    this,
    v21);
  CRegKey::Close((CRegKey *)&v23);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v22);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180017200  mov     [rsp+arg_8], rbx
0x180017205  mov     [rsp+arg_10], rsi
0x18001720a  push    rdi
0x18001720b  sub     rsp, 40h
0x18001720f  mov     rdi, rcx
0x180017212  lea     rdx, [rcx+50h]
0x180017216  lea     rcx, [rsp+48h+var_18]
0x18001721b  xor     ebx, ebx
0x18001721d  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x180017222  and     [rsp+48h+arg_0], rbx
0x180017227  lea     r8, aCwdstransportm_16; "-> CWdsTransportMulticastSessionPolicy:"...
0x18001722e  mov     r9, rdi
0x180017231  lea     rcx, qword_18003B770
0x180017238  mov     edx, 10000h
0x18001723d  xor     esi, esi
0x18001723f  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180017246  nop     dword ptr [rax+rax+00h]
0x18001724b  cmp     [rdi+80h], ebx
0x180017251  jz      loc_18001746E
0x180017257  mov     rdx, [rdi+40h]
0x18001725b  lea     r9, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\WD"...
0x180017262  mov     r8, 0FFFFFFFF80000002h
0x180017269  mov     [rsp+48h+var_28], 20006h
0x180017271  lea     rcx, [rsp+48h+arg_0]
0x180017276  mov     rdx, [rdx+70h]
0x18001727a  call    cs:__imp_?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z; CRegKey::RemoteOpen(ushort const *,HKEY__ *,ushort const *,ulong)
0x180017281  nop     dword ptr [rax+rax+00h]
0x180017286  mov     ecx, eax
0x180017288  mov     r9d, 48Fh
0x18001728e  mov     ebx, eax
0x180017290  call    ElValidateWin32_11
0x180017295  test    eax, eax
0x180017297  jz      short loc_1800172AF
0x180017299  test    ebx, ebx
0x18001729b  jle     loc_18001746E
0x1800172a1  movzx   ebx, bx
0x1800172a4  or      ebx, 80070000h
0x1800172aa  jmp     loc_18001746E
0x1800172af  mov     eax, [rdi+80h]
0x1800172b5  test    al, 1
0x1800172b7  jz      loc_180017371
0x1800172bd  mov     r9d, [rdi+84h]
0x1800172c4  xor     ebx, ebx
0x1800172c6  mov     ecx, r9d
0x1800172c9  test    r9d, r9d
0x1800172cc  jz      short loc_180017318
0x1800172ce  sub     ecx, 1
0x1800172d1  jz      short loc_180017311
0x1800172d3  sub     ecx, 1
0x1800172d6  jz      short loc_18001730A
0x1800172d8  cmp     ecx, 1
0x1800172db  jz      short loc_180017303
0x1800172dd  lea     r8, aErrorEncounter_0; "Error: Encountered an unknown WdsTptMgm"...
0x1800172e4  mov     edx, 80000h
0x1800172e9  lea     rcx, qword_18003B770
0x1800172f0  mov     ebx, 0C110011Eh
0x1800172f5  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800172fc  nop     dword ptr [rax+rax+00h]
0x180017301  jmp     short loc_18001731D
0x180017303  mov     esi, 3
0x180017308  jmp     short loc_18001731D
0x18001730a  mov     esi, 2
0x18001730f  jmp     short loc_18001731D
0x180017311  mov     esi, 1
0x180017316  jmp     short loc_18001731D
0x180017318  mov     ebx, 0C110011Eh
0x18001731d  mov     r9d, 49Ch
0x180017323  mov     ecx, ebx
0x180017325  call    ElValidateHr_12
0x18001732a  test    eax, eax
0x18001732c  js      loc_18001746E
0x180017332  mov     r8d, esi
0x180017335  lea     rdx, aTpslowclientha; "TpSlowClientHandling"
0x18001733c  lea     rcx, [rsp+48h+arg_0]
0x180017341  call    cs:__imp_?SetValueDword@CRegKey@@QEAAKPEBGK@Z; CRegKey::SetValueDword(ushort const *,ulong)
0x180017348  nop     dword ptr [rax+rax+00h]
0x18001734d  mov     ecx, eax
0x18001734f  mov     r9d, 4A0h
0x180017355  mov     ebx, eax
0x180017357  call    ElValidateWin32_11
0x18001735c  test    eax, eax
0x18001735e  jnz     loc_180017299
0x180017364  and     dword ptr [rdi+80h], 0FFFFFFFEh
0x18001736b  mov     eax, [rdi+80h]
0x180017371  test    al, 2
0x180017373  jz      short loc_1800173BC
0x180017375  mov     r8d, [rdi+88h]
0x18001737c  lea     rdx, aTpautokickthre; "TpAutoKickThreshold"
0x180017383  shl     r8d, 0Ah
0x180017387  lea     rcx, [rsp+48h+arg_0]
0x18001738c  call    cs:__imp_?SetValueDword@CRegKey@@QEAAKPEBGK@Z; CRegKey::SetValueDword(ushort const *,ulong)
0x180017393  nop     dword ptr [rax+rax+00h]
0x180017398  mov     ecx, eax
0x18001739a  mov     r9d, 4B0h
0x1800173a0  mov     ebx, eax
0x1800173a2  call    ElValidateWin32_11
0x1800173a7  test    eax, eax
0x1800173a9  jnz     loc_180017299
0x1800173af  and     dword ptr [rdi+80h], 0FFFFFFFDh
0x1800173b6  mov     eax, [rdi+80h]
0x1800173bc  test    al, 4
0x1800173be  jz      short loc_180017403
0x1800173c0  mov     r8d, [rdi+8Ch]
0x1800173c7  lea     rdx, aTpmultistreamc; "TpMultiStreamCount"
0x1800173ce  lea     rcx, [rsp+48h+arg_0]
0x1800173d3  call    cs:__imp_?SetValueDword@CRegKey@@QEAAKPEBGK@Z; CRegKey::SetValueDword(ushort const *,ulong)
0x1800173da  nop     dword ptr [rax+rax+00h]
0x1800173df  mov     ecx, eax
0x1800173e1  mov     r9d, 4BDh
0x1800173e7  mov     ebx, eax
0x1800173e9  call    ElValidateWin32_11
0x1800173ee  test    eax, eax
0x1800173f0  jnz     loc_180017299
0x1800173f6  and     dword ptr [rdi+80h], 0FFFFFFFBh
0x1800173fd  mov     eax, [rdi+80h]
0x180017403  test    al, 8
0x180017405  jz      short loc_180017444
0x180017407  mov     r8d, [rdi+90h]
0x18001740e  lea     rdx, aTpslowclientfa; "TpSlowClientFallback"
0x180017415  lea     rcx, [rsp+48h+arg_0]
0x18001741a  call    cs:__imp_?SetValueDword@CRegKey@@QEAAKPEBGK@Z; CRegKey::SetValueDword(ushort const *,ulong)
0x180017421  nop     dword ptr [rax+rax+00h]
0x180017426  mov     ecx, eax
0x180017428  mov     r9d, 4CAh
0x18001742e  mov     ebx, eax
0x180017430  call    ElValidateWin32_11
0x180017435  test    eax, eax
0x180017437  jnz     loc_180017299
0x18001743d  and     dword ptr [rdi+80h], 0FFFFFFF7h
0x180017444  lea     r8, aWillNotifyWdsT; "Will notify WDS Transport services of t"...
0x18001744b  mov     edx, 10000h
0x180017450  lea     rcx, qword_18003B770
0x180017457  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18001745e  nop     dword ptr [rax+rax+00h]
0x180017463  mov     rcx, [rdi+40h]; this
0x180017467  call    ?SignalSettingsChange@CWdsTransportServer@@QEAAJXZ; CWdsTransportServer::SignalSettingsChange(void)
0x18001746c  mov     ebx, eax
0x18001746e  mov     r9, rdi
0x180017471  mov     [rsp+48h+var_28], ebx
0x180017475  lea     r8, aCwdstransportm_10; "<- CWdsTransportMulticastSessionPolicy:"...
0x18001747c  mov     edx, 10000h
0x180017481  lea     rcx, qword_18003B770
0x180017488  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18001748f  nop     dword ptr [rax+rax+00h]
0x180017494  lea     rcx, [rsp+48h+arg_0]; this
0x180017499  call    ?Close@CRegKey@@QEAAXXZ; CRegKey::Close(void)
0x18001749e  lea     rcx, [rsp+48h+var_18]
0x1800174a3  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x1800174a8  mov     rsi, [rsp+48h+arg_10]
0x1800174ad  mov     eax, ebx
0x1800174af  mov     rbx, [rsp+48h+arg_8]
0x1800174b4  add     rsp, 40h
0x1800174b8  pop     rdi
0x1800174b9  retn
```
