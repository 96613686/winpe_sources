# CWdsTransportNamespace::Refresh(void)

- ea: `0x180012484`
- end: `0x18001259c`
- name: `?Refresh@CWdsTransportNamespace@@UEAAJXZ`
- size: `280`
- prototype: `__int64 __fastcall(CWdsTransportNamespace *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800125b0`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180012484`
- `0x180012bb0`
- `0x1800137c4`
- `0x18001af4c`
- `0x18001c9a4`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800124bb`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180012516`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180012578`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800124bb`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180012516`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180012578`

## string_xrefs

- `0x180012503`: `Successfully retrieved latest server data for namespace %s.\nWill now update internal object state.\n`

## pseudocode

```c
__int64 __fastcall CWdsTransportNamespace::Refresh(CWdsTransportNamespace *this)
{
  void *v2; // rdx
  __int64 updated; // rbx
  int refreshed; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  _BYTE v8[24]; // [rsp+30h] [rbp-18h] BYREF
  struct _WDSTPT_NAMESPACE *v9; // [rsp+50h] [rbp+8h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v8, (char *)this + 64);
  v9 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportNamespace::Refresh(0x%p)", this);
  v2 = (void *)*((_QWORD *)this + 22);
  if ( v2 )
  {
    refreshed = CWdsTptMgmtClient::RefreshNamespace(*((CWdsTptMgmtClient **)this + 14), v2, &v9);
    LODWORD(updated) = refreshed;
    if ( refreshed >= 0 )
    {
      CTrace::Trace(
        (CTrace *)qword_18003B770,
        0x10000u,
        L"Successfully retrieved latest server data for namespace %s.\nWill now update internal object state.\n",
        *((_QWORD *)this + 17));
      updated = (unsigned int)CWdsTransportNamespace::UpdateLiveNamespaceData(this, v9);
      if ( (int)ElValidateHr_7(updated, v5, v6, 2026) >= 0 && *((_DWORD *)this + 46) )
        *((_DWORD *)this + 31) = 0;
    }
    else if ( refreshed == -1054801659 )
    {
      LODWORD(updated) = -1055915755;
    }
  }
  else
  {
    LODWORD(updated) = -1055915756;
  }
  CTptControlPacket::FreeNamespace(v9, 1);
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"<- CWdsTransportNamespace::Refresh(0x%p) =%x", this, updated);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v8);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180012484  mov     [rsp+arg_8], rbx
0x180012489  push    rdi
0x18001248a  sub     rsp, 40h
0x18001248e  mov     rdi, rcx
0x180012491  lea     rdx, [rcx+40h]
0x180012495  lea     rcx, [rsp+48h+var_18]
0x18001249a  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18001249f  and     [rsp+48h+arg_0], 0
0x1800124a5  lea     r8, aCwdstransportn_45; "-> CWdsTransportNamespace::Refresh(0x%p"...
0x1800124ac  mov     r9, rdi
0x1800124af  lea     rcx, qword_18003B770
0x1800124b6  mov     edx, 10000h
0x1800124bb  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800124c2  nop     dword ptr [rax+rax+00h]
0x1800124c7  mov     rdx, [rdi+0B0h]; void *
0x1800124ce  test    rdx, rdx
0x1800124d1  jnz     short loc_1800124DA
0x1800124d3  mov     ebx, 0C1100114h
0x1800124d8  jmp     short loc_18001254F
0x1800124da  mov     rcx, [rdi+70h]; this
0x1800124de  lea     r8, [rsp+48h+arg_0]; struct _WDSTPT_NAMESPACE **
0x1800124e3  call    ?RefreshNamespace@CWdsTptMgmtClient@@QEAAJPEAXPEAPEAU_WDSTPT_NAMESPACE@@@Z; CWdsTptMgmtClient::RefreshNamespace(void *,_WDSTPT_NAMESPACE * *)
0x1800124e8  mov     ebx, eax
0x1800124ea  test    eax, eax
0x1800124ec  jns     short loc_1800124FC
0x1800124ee  cmp     eax, 0C1210105h
0x1800124f3  jnz     short loc_18001254F
0x1800124f5  mov     ebx, 0C1100115h
0x1800124fa  jmp     short loc_18001254F
0x1800124fc  mov     r9, [rdi+88h]
0x180012503  lea     r8, aSuccessfullyRe_5; "Successfully retrieved latest server da"...
0x18001250a  mov     edx, 10000h
0x18001250f  lea     rcx, qword_18003B770
0x180012516  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18001251d  nop     dword ptr [rax+rax+00h]
0x180012522  mov     rdx, [rsp+48h+arg_0]; struct _WDSTPT_NAMESPACE *
0x180012527  mov     rcx, rdi; this
0x18001252a  call    ?UpdateLiveNamespaceData@CWdsTransportNamespace@@AEAAJPEAU_WDSTPT_NAMESPACE@@@Z; CWdsTransportNamespace::UpdateLiveNamespaceData(_WDSTPT_NAMESPACE *)
0x18001252f  mov     r9d, 7EAh
0x180012535  mov     ecx, eax
0x180012537  mov     ebx, eax
0x180012539  call    ElValidateHr_7
0x18001253e  test    eax, eax
0x180012540  js      short loc_18001254F
0x180012542  cmp     dword ptr [rdi+0B8h], 0
0x180012549  jz      short loc_18001254F
0x18001254b  and     dword ptr [rdi+7Ch], 0
0x18001254f  mov     rcx, [rsp+48h+arg_0]; struct _WDSTPT_NAMESPACE *
0x180012554  mov     edx, 1; int
0x180012559  call    ?FreeNamespace@CTptControlPacket@@SAXPEAU_WDSTPT_NAMESPACE@@H@Z; CTptControlPacket::FreeNamespace(_WDSTPT_NAMESPACE *,int)
0x18001255e  mov     r9, rdi
0x180012561  mov     [rsp+48h+var_28], ebx
0x180012565  lea     r8, aCwdstransportn_44; "<- CWdsTransportNamespace::Refresh(0x%p"...
0x18001256c  mov     edx, 10000h
0x180012571  lea     rcx, qword_18003B770
0x180012578  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18001257f  nop     dword ptr [rax+rax+00h]
0x180012584  lea     rcx, [rsp+48h+var_18]
0x180012589  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18001258e  mov     eax, ebx
0x180012590  mov     rbx, [rsp+48h+arg_8]
0x180012595  add     rsp, 40h
0x180012599  pop     rdi
0x18001259a  retn
```
