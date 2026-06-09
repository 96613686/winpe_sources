# CWdsTransportServicePolicy::Commit(void)

- ea: `0x18000c790`
- end: `0x18000cd00`
- name: `?Commit@CWdsTransportServicePolicy@@UEAAJXZ`
- size: `1392`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180009254`
- `0x180009e20`
- `0x18000c790`
- `0x18000d988`
- `0x18000eb74`
- `0x18000ec98`

## import_xrefs

- `WdsCommonLib!?SetValueSz@CRegKey@@QEAAKPEBG0@Z` at `0x18000c8d0`
- `WdsCommonLib!?SetValueSz@CRegKey@@QEAAKPEBG0@Z` at `0x18000c905`
- `WdsCommonLib!?SetValueSz@CRegKey@@QEAAKPEBG0@Z` at `0x18000c9ba`
- `WdsCommonLib!?SetValueSz@CRegKey@@QEAAKPEBG0@Z` at `0x18000c9ef`
- `WdsCommonLib!?SetValueSz@CRegKey@@QEAAKPEBG0@Z` at `0x18000cb97`
- `WdsCommonLib!?SetValueSz@CRegKey@@QEAAKPEBG0@Z` at `0x18000c8d0`
- `WdsCommonLib!?SetValueSz@CRegKey@@QEAAKPEBG0@Z` at `0x18000c905`
- `WdsCommonLib!?SetValueSz@CRegKey@@QEAAKPEBG0@Z` at `0x18000c9ba`
- `WdsCommonLib!?SetValueSz@CRegKey@@QEAAKPEBG0@Z` at `0x18000c9ef`
- `WdsCommonLib!?SetValueSz@CRegKey@@QEAAKPEBG0@Z` at `0x18000cb97`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000c810`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000cb0f`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000cbdf`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000c810`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000cb0f`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000cbdf`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000c89b`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000c985`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000ca4c`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000ca81`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000cac7`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000cc1e`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000cc4d`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000c89b`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000c985`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000ca4c`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000ca81`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000cac7`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000cc1e`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000cc4d`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000c7d3`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000cc73`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000cca4`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000ccf2`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000c7d3`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000cc73`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000cca4`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000ccf2`

## string_xrefs

- `0x18000c7ef`: `System\CurrentControlSet\Services\WDSServer\Parameters`
- `0x18000caf5`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSMC`
- `0x18000cbc5`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSTFTP`
- `0x18000cc42`: `EnableVariableWindowExtension`
- `0x18000c7bd`: `-> CWdsTransportServicePolicy::Commit(0x%p)`
- `0x18000cc60`: `Will notify WDS Transport services of the settings modification.\n`
- `0x18000cc91`: `<- CWdsTransportServicePolicy::Commit(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::Commit(CWdsTransportServicePolicy *this)
{
  __int64 v2; // rbx
  __int64 v3; // rdx
  __int64 v4; // r8
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned int v22; // r8d
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rdx
  __int64 v30; // r8
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  const unsigned __int16 *v35; // r8
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rdx
  __int64 v39; // r8
  int v40; // eax
  __int64 v42; // [rsp+20h] [rbp-20h]
  _BYTE v43[16]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v44; // [rsp+50h] [rbp+10h] BYREF

  LODWORD(v2) = 0;
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v43, (char *)this + 80);
  v44 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportServicePolicy::Commit(0x%p)", this);
  if ( !*((_DWORD *)this + 32) )
    goto LABEL_45;
  v2 = CRegKey::RemoteOpen(
         (CRegKey *)&v44,
         *(const unsigned __int16 **)(*((_QWORD *)this + 8) + 112LL),
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WDSServer\\Parameters",
         0x20006u);
  if ( (unsigned int)ElValidateWin32_4(v2, v3, v4, 2624) )
    goto LABEL_3;
  v5 = *((_DWORD *)this + 32);
  if ( (v5 & 1) != 0 )
  {
    v2 = (unsigned int)CWdsTransportServicePolicy::ValidateIpAddressRange(
                         2u,
                         *((const unsigned __int16 **)this + 17),
                         *((const unsigned __int16 **)this + 18));
    if ( (int)ElValidateHr_4(v2, v6, v7, 2638) < 0 )
      goto LABEL_45;
    v2 = CRegKey::SetValueDword((CRegKey *)&v44, L"UseMADCAP", *((_DWORD *)this + 33) == 1);
    if ( (unsigned int)ElValidateWin32_4(v2, v8, v9, 2647) )
      goto LABEL_3;
    v2 = CRegKey::SetValueSz((CRegKey *)&v44, L"McStartAddr", *((const unsigned __int16 **)this + 17));
    if ( (unsigned int)ElValidateWin32_4(v2, v10, v11, 2652) )
      goto LABEL_3;
    v2 = CRegKey::SetValueSz((CRegKey *)&v44, L"McEndAddr", *((const unsigned __int16 **)this + 18));
    if ( (unsigned int)ElValidateWin32_4(v2, v12, v13, 2656) )
      goto LABEL_3;
    *((_DWORD *)this + 32) &= ~1u;
    v5 = *((_DWORD *)this + 32);
  }
  if ( (v5 & 2) != 0 )
  {
    v2 = (unsigned int)CWdsTransportServicePolicy::ValidateIpAddressRange(
                         0x17u,
                         *((const unsigned __int16 **)this + 20),
                         *((const unsigned __int16 **)this + 21));
    if ( (int)ElValidateHr_4(v2, v14, v15, 2678) < 0 )
      goto LABEL_45;
    v2 = CRegKey::SetValueDword((CRegKey *)&v44, L"UseMADCAP6", *((_DWORD *)this + 38) == 1);
    if ( (unsigned int)ElValidateWin32_4(v2, v16, v17, 2687) )
      goto LABEL_3;
    v2 = CRegKey::SetValueSz((CRegKey *)&v44, L"McStartAddr6", *((const unsigned __int16 **)this + 20));
    if ( (unsigned int)ElValidateWin32_4(v2, v18, v19, 2692) )
      goto LABEL_3;
    v2 = CRegKey::SetValueSz((CRegKey *)&v44, L"McEndAddr6", *((const unsigned __int16 **)this + 21));
    if ( (unsigned int)ElValidateWin32_4(v2, v20, v21, 2696) )
      goto LABEL_3;
    *((_DWORD *)this + 32) &= ~2u;
    v5 = *((_DWORD *)this + 32);
  }
  if ( (v5 & 4) != 0 )
  {
    v22 = *((_DWORD *)this + 44);
    if ( v22 > *((_DWORD *)this + 45) )
    {
      LODWORD(v2) = -1055915759;
      goto LABEL_45;
    }
    v2 = CRegKey::SetValueDword((CRegKey *)&v44, L"UdpStartPort", v22);
    if ( (unsigned int)ElValidateWin32_4(v2, v23, v24, 2722) )
      goto LABEL_3;
    v2 = CRegKey::SetValueDword((CRegKey *)&v44, L"UdpEndPort", *((_DWORD *)this + 45));
    if ( (unsigned int)ElValidateWin32_4(v2, v25, v26, 2726) )
      goto LABEL_3;
    *((_DWORD *)this + 32) &= ~4u;
    v5 = *((_DWORD *)this + 32);
  }
  if ( (v5 & 0x10) != 0 )
  {
    v2 = CRegKey::SetValueDword((CRegKey *)&v44, L"UdpPortPolicy", *((_DWORD *)this + 47));
    if ( (unsigned int)ElValidateWin32_4(v2, v27, v28, 2743) )
      goto LABEL_3;
    *((_DWORD *)this + 32) &= ~0x10u;
  }
  v2 = CRegKey::RemoteOpen(
         (CRegKey *)&v44,
         *(const unsigned __int16 **)(*((_QWORD *)this + 8) + 112LL),
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSMC",
         0x20006u);
  if ( (unsigned int)ElValidateWin32_4(v2, v29, v30, 2758) )
  {
LABEL_3:
    if ( (int)v2 > 0 )
      LODWORD(v2) = (unsigned __int16)v2 | 0x80070000;
    goto LABEL_45;
  }
  if ( (*((_BYTE *)this + 128) & 8) != 0 )
  {
    v31 = *((_DWORD *)this + 46);
    if ( v31 )
    {
      v32 = v31 - 1;
      if ( !v32 )
      {
        v35 = L"Custom";
        goto LABEL_37;
      }
      v33 = v32 - 1;
      if ( !v33 )
      {
        v35 = L"10Mbps";
        goto LABEL_37;
      }
      v34 = v33 - 1;
      if ( !v34 )
      {
        v35 = L"100Mbps";
        goto LABEL_37;
      }
      if ( v34 == 1 )
      {
        v35 = L"1Gbps";
LABEL_37:
        v2 = CRegKey::SetValueSz((CRegKey *)&v44, L"DefaultProfile", v35);
        if ( (unsigned int)ElValidateWin32_4(v2, v36, v37, 2815) )
          goto LABEL_3;
        *((_DWORD *)this + 32) &= ~8u;
        goto LABEL_39;
      }
    }
    LODWORD(v2) = -2147024809;
    CTrace::Trace((CTrace *)qword_18003B770, 0x80000u, L"Network Profile enum is set to an invalid value: %u.\n");
    goto LABEL_45;
  }
LABEL_39:
  v2 = CRegKey::RemoteOpen(
         (CRegKey *)&v44,
         *(const unsigned __int16 **)(*((_QWORD *)this + 8) + 112LL),
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSTFTP",
         0x20006u);
  if ( (unsigned int)ElValidateWin32_4(v2, v38, v39, 2830) )
    goto LABEL_3;
  v40 = *((_DWORD *)this + 32);
  if ( (v40 & 0x20) != 0 )
  {
    CRegKey::SetValueDword((CRegKey *)&v44, L"MaximumBlockSize", *((_DWORD *)this + 48));
    *((_DWORD *)this + 32) &= ~0x20u;
    v40 = *((_DWORD *)this + 32);
  }
  if ( (v40 & 0x40) != 0 )
  {
    CRegKey::SetValueDword((CRegKey *)&v44, L"EnableVariableWindowExtension", *((_DWORD *)this + 49));
    *((_DWORD *)this + 32) &= ~0x40u;
  }
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"Will notify WDS Transport services of the settings modification.\n");
  LODWORD(v2) = CWdsTransportServer::SignalSettingsChange(*((CWdsTransportServer **)this + 8));
LABEL_45:
  LODWORD(v42) = v2;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"<- CWdsTransportServicePolicy::Commit(0x%p) =%x", this, v42);
  CRegKey::Close((CRegKey *)&v44);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v43);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000c790  mov     [rsp-8+arg_8], rbx
0x18000c795  mov     [rsp-8+arg_10], rdi
0x18000c79a  mov     [rsp-8+arg_18], r15
0x18000c79f  push    rbp
0x18000c7a0  mov     rbp, rsp
0x18000c7a3  sub     rsp, 40h
0x18000c7a7  mov     rdi, rcx
0x18000c7aa  lea     rdx, [rcx+50h]
0x18000c7ae  lea     rcx, [rbp+var_10]
0x18000c7b2  xor     ebx, ebx
0x18000c7b4  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000c7b9  and     [rbp+arg_0], rbx
0x18000c7bd  lea     r8, aCwdstransports_49; "-> CWdsTransportServicePolicy::Commit(0"...
0x18000c7c4  mov     r9, rdi
0x18000c7c7  lea     rcx, qword_18003B770
0x18000c7ce  mov     edx, 10000h
0x18000c7d3  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000c7da  nop     dword ptr [rax+rax+00h]
0x18000c7df  cmp     [rdi+80h], ebx
0x18000c7e5  jz      loc_18000CC8A
0x18000c7eb  mov     rdx, [rdi+40h]
0x18000c7ef  lea     r9, aSystemCurrentc_7; "System\\CurrentControlSet\\Services\\WD"...
0x18000c7f6  mov     r15, 0FFFFFFFF80000002h
0x18000c7fd  mov     [rsp+40h+var_20], 20006h
0x18000c805  mov     r8, r15
0x18000c808  lea     rcx, [rbp+arg_0]
0x18000c80c  mov     rdx, [rdx+70h]
0x18000c810  call    cs:__imp_?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z; CRegKey::RemoteOpen(ushort const *,HKEY__ *,ushort const *,ulong)
0x18000c817  nop     dword ptr [rax+rax+00h]
0x18000c81c  mov     ecx, eax
0x18000c81e  mov     r9d, 0A40h
0x18000c824  mov     ebx, eax
0x18000c826  call    ElValidateWin32_4
0x18000c82b  test    eax, eax
0x18000c82d  jz      short loc_18000C845
0x18000c82f  test    ebx, ebx
0x18000c831  jle     loc_18000CC8A
0x18000c837  movzx   ebx, bx
0x18000c83a  or      ebx, 80070000h
0x18000c840  jmp     loc_18000CC8A
0x18000c845  mov     eax, [rdi+80h]
0x18000c84b  test    al, 1
0x18000c84d  jz      loc_18000C935
0x18000c853  mov     r8, [rdi+90h]; unsigned __int16 *
0x18000c85a  mov     ecx, 2; unsigned int
0x18000c85f  mov     rdx, [rdi+88h]; unsigned __int16 *
0x18000c866  call    ?ValidateIpAddressRange@CWdsTransportServicePolicy@@CAJKPEBG0@Z; CWdsTransportServicePolicy::ValidateIpAddressRange(ulong,ushort const *,ushort const *)
0x18000c86b  mov     r9d, 0A4Eh
0x18000c871  mov     ecx, eax
0x18000c873  mov     ebx, eax
0x18000c875  call    ElValidateHr_4
0x18000c87a  test    eax, eax
0x18000c87c  js      loc_18000CC8A
0x18000c882  xor     r8d, r8d
0x18000c885  lea     rdx, aUsemadcap; "UseMADCAP"
0x18000c88c  cmp     dword ptr [rdi+84h], 1
0x18000c893  lea     rcx, [rbp+arg_0]
0x18000c897  setz    r8b
0x18000c89b  call    cs:__imp_?SetValueDword@CRegKey@@QEAAKPEBGK@Z; CRegKey::SetValueDword(ushort const *,ulong)
0x18000c8a2  nop     dword ptr [rax+rax+00h]
0x18000c8a7  mov     ecx, eax
0x18000c8a9  mov     r9d, 0A57h
0x18000c8af  mov     ebx, eax
0x18000c8b1  call    ElValidateWin32_4
0x18000c8b6  test    eax, eax
0x18000c8b8  jnz     loc_18000C82F
0x18000c8be  mov     r8, [rdi+88h]
0x18000c8c5  lea     rdx, aMcstartaddr; "McStartAddr"
0x18000c8cc  lea     rcx, [rbp+arg_0]
0x18000c8d0  call    cs:__imp_?SetValueSz@CRegKey@@QEAAKPEBG0@Z; CRegKey::SetValueSz(ushort const *,ushort const *)
0x18000c8d7  nop     dword ptr [rax+rax+00h]
0x18000c8dc  mov     ecx, eax
0x18000c8de  mov     r9d, 0A5Ch
0x18000c8e4  mov     ebx, eax
0x18000c8e6  call    ElValidateWin32_4
0x18000c8eb  test    eax, eax
0x18000c8ed  jnz     loc_18000C82F
0x18000c8f3  mov     r8, [rdi+90h]
0x18000c8fa  lea     rdx, aMcendaddr; "McEndAddr"
0x18000c901  lea     rcx, [rbp+arg_0]
0x18000c905  call    cs:__imp_?SetValueSz@CRegKey@@QEAAKPEBG0@Z; CRegKey::SetValueSz(ushort const *,ushort const *)
0x18000c90c  nop     dword ptr [rax+rax+00h]
0x18000c911  mov     ecx, eax
0x18000c913  mov     r9d, 0A60h
0x18000c919  mov     ebx, eax
0x18000c91b  call    ElValidateWin32_4
0x18000c920  test    eax, eax
0x18000c922  jnz     loc_18000C82F
0x18000c928  and     dword ptr [rdi+80h], 0FFFFFFFEh
0x18000c92f  mov     eax, [rdi+80h]
0x18000c935  test    al, 2
0x18000c937  jz      loc_18000CA1F
0x18000c93d  mov     r8, [rdi+0A8h]; unsigned __int16 *
0x18000c944  mov     ecx, 17h; unsigned int
0x18000c949  mov     rdx, [rdi+0A0h]; unsigned __int16 *
0x18000c950  call    ?ValidateIpAddressRange@CWdsTransportServicePolicy@@CAJKPEBG0@Z; CWdsTransportServicePolicy::ValidateIpAddressRange(ulong,ushort const *,ushort const *)
0x18000c955  mov     r9d, 0A76h
0x18000c95b  mov     ecx, eax
0x18000c95d  mov     ebx, eax
0x18000c95f  call    ElValidateHr_4
0x18000c964  test    eax, eax
0x18000c966  js      loc_18000CC8A
0x18000c96c  xor     r8d, r8d
0x18000c96f  lea     rdx, aUsemadcap6; "UseMADCAP6"
0x18000c976  cmp     dword ptr [rdi+98h], 1
0x18000c97d  lea     rcx, [rbp+arg_0]
0x18000c981  setz    r8b
0x18000c985  call    cs:__imp_?SetValueDword@CRegKey@@QEAAKPEBGK@Z; CRegKey::SetValueDword(ushort const *,ulong)
0x18000c98c  nop     dword ptr [rax+rax+00h]
0x18000c991  mov     ecx, eax
0x18000c993  mov     r9d, 0A7Fh
0x18000c999  mov     ebx, eax
0x18000c99b  call    ElValidateWin32_4
0x18000c9a0  test    eax, eax
0x18000c9a2  jnz     loc_18000C82F
0x18000c9a8  mov     r8, [rdi+0A0h]
0x18000c9af  lea     rdx, aMcstartaddr6; "McStartAddr6"
0x18000c9b6  lea     rcx, [rbp+arg_0]
0x18000c9ba  call    cs:__imp_?SetValueSz@CRegKey@@QEAAKPEBG0@Z; CRegKey::SetValueSz(ushort const *,ushort const *)
0x18000c9c1  nop     dword ptr [rax+rax+00h]
0x18000c9c6  mov     ecx, eax
0x18000c9c8  mov     r9d, 0A84h
0x18000c9ce  mov     ebx, eax
0x18000c9d0  call    ElValidateWin32_4
0x18000c9d5  test    eax, eax
0x18000c9d7  jnz     loc_18000C82F
0x18000c9dd  mov     r8, [rdi+0A8h]
0x18000c9e4  lea     rdx, aMcendaddr6; "McEndAddr6"
0x18000c9eb  lea     rcx, [rbp+arg_0]
0x18000c9ef  call    cs:__imp_?SetValueSz@CRegKey@@QEAAKPEBG0@Z; CRegKey::SetValueSz(ushort const *,ushort const *)
0x18000c9f6  nop     dword ptr [rax+rax+00h]
0x18000c9fb  mov     ecx, eax
0x18000c9fd  mov     r9d, 0A88h
0x18000ca03  mov     ebx, eax
0x18000ca05  call    ElValidateWin32_4
0x18000ca0a  test    eax, eax
0x18000ca0c  jnz     loc_18000C82F
0x18000ca12  and     dword ptr [rdi+80h], 0FFFFFFFDh
0x18000ca19  mov     eax, [rdi+80h]
0x18000ca1f  test    al, 4
0x18000ca21  jz      loc_18000CAB1
0x18000ca27  mov     r8d, [rdi+0B0h]
0x18000ca2e  cmp     r8d, [rdi+0B4h]
0x18000ca35  jbe     short loc_18000CA41
0x18000ca37  mov     ebx, 0C1100111h
0x18000ca3c  jmp     loc_18000CC8A
0x18000ca41  lea     rdx, aUdpstartport; "UdpStartPort"
0x18000ca48  lea     rcx, [rbp+arg_0]
0x18000ca4c  call    cs:__imp_?SetValueDword@CRegKey@@QEAAKPEBGK@Z; CRegKey::SetValueDword(ushort const *,ulong)
0x18000ca53  nop     dword ptr [rax+rax+00h]
0x18000ca58  mov     ecx, eax
0x18000ca5a  mov     r9d, 0AA2h
0x18000ca60  mov     ebx, eax
0x18000ca62  call    ElValidateWin32_4
0x18000ca67  test    eax, eax
0x18000ca69  jnz     loc_18000C82F
0x18000ca6f  mov     r8d, [rdi+0B4h]
0x18000ca76  lea     rdx, aUdpendport; "UdpEndPort"
0x18000ca7d  lea     rcx, [rbp+arg_0]
0x18000ca81  call    cs:__imp_?SetValueDword@CRegKey@@QEAAKPEBGK@Z; CRegKey::SetValueDword(ushort const *,ulong)
0x18000ca88  nop     dword ptr [rax+rax+00h]
0x18000ca8d  mov     ecx, eax
0x18000ca8f  mov     r9d, 0AA6h
0x18000ca95  mov     ebx, eax
0x18000ca97  call    ElValidateWin32_4
0x18000ca9c  test    eax, eax
0x18000ca9e  jnz     loc_18000C82F
0x18000caa4  and     dword ptr [rdi+80h], 0FFFFFFFBh
0x18000caab  mov     eax, [rdi+80h]
0x18000cab1  test    al, 10h
0x18000cab3  jz      short loc_18000CAF1
0x18000cab5  mov     r8d, [rdi+0BCh]
0x18000cabc  lea     rdx, aUdpportpolicy; "UdpPortPolicy"
0x18000cac3  lea     rcx, [rbp+arg_0]
0x18000cac7  call    cs:__imp_?SetValueDword@CRegKey@@QEAAKPEBGK@Z; CRegKey::SetValueDword(ushort const *,ulong)
0x18000cace  nop     dword ptr [rax+rax+00h]
0x18000cad3  mov     ecx, eax
0x18000cad5  mov     r9d, 0AB7h
0x18000cadb  mov     ebx, eax
0x18000cadd  call    ElValidateWin32_4
0x18000cae2  test    eax, eax
0x18000cae4  jnz     loc_18000C82F
0x18000caea  and     dword ptr [rdi+80h], 0FFFFFFEFh
0x18000caf1  mov     rdx, [rdi+40h]
0x18000caf5  lea     r9, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\WD"...
0x18000cafc  mov     r8, r15
0x18000caff  mov     [rsp+40h+var_20], 20006h
0x18000cb07  lea     rcx, [rbp+arg_0]
0x18000cb0b  mov     rdx, [rdx+70h]
0x18000cb0f  call    cs:__imp_?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z; CRegKey::RemoteOpen(ushort const *,HKEY__ *,ushort const *,ulong)
0x18000cb16  nop     dword ptr [rax+rax+00h]
0x18000cb1b  mov     ecx, eax
0x18000cb1d  mov     r9d, 0AC6h
0x18000cb23  mov     ebx, eax
0x18000cb25  call    ElValidateWin32_4
0x18000cb2a  test    eax, eax
0x18000cb2c  jnz     loc_18000C82F
0x18000cb32  test    byte ptr [rdi+80h], 8
0x18000cb39  jz      loc_18000CBC1
0x18000cb3f  mov     r9d, [rdi+0B8h]
0x18000cb46  mov     ecx, r9d
0x18000cb49  test    r9d, r9d
0x18000cb4c  jz      loc_18000CCDA
0x18000cb52  sub     ecx, 1
0x18000cb55  jz      short loc_18000CB85
0x18000cb57  sub     ecx, 1
0x18000cb5a  jz      short loc_18000CB7C
0x18000cb5c  sub     ecx, 1
0x18000cb5f  jz      short loc_18000CB73
0x18000cb61  cmp     ecx, 1
0x18000cb64  jnz     loc_18000CCDA
0x18000cb6a  lea     r8, a1gbps; "1Gbps"
0x18000cb71  jmp     short loc_18000CB8C
0x18000cb73  lea     r8, a100mbps; "100Mbps"
0x18000cb7a  jmp     short loc_18000CB8C
0x18000cb7c  lea     r8, a10mbps; "10Mbps"
0x18000cb83  jmp     short loc_18000CB8C
0x18000cb85  lea     r8, aCustom; "Custom"
0x18000cb8c  lea     rdx, aDefaultprofile; "DefaultProfile"
0x18000cb93  lea     rcx, [rbp+arg_0]
0x18000cb97  call    cs:__imp_?SetValueSz@CRegKey@@QEAAKPEBG0@Z; CRegKey::SetValueSz(ushort const *,ushort const *)
0x18000cb9e  nop     dword ptr [rax+rax+00h]
0x18000cba3  mov     ecx, eax
0x18000cba5  mov     r9d, 0AFFh
0x18000cbab  mov     ebx, eax
0x18000cbad  call    ElValidateWin32_4
0x18000cbb2  test    eax, eax
0x18000cbb4  jnz     loc_18000C82F
0x18000cbba  and     dword ptr [rdi+80h], 0FFFFFFF7h
0x18000cbc1  mov     rdx, [rdi+40h]
0x18000cbc5  lea     r9, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\WD"...
0x18000cbcc  mov     r8, r15
0x18000cbcf  mov     [rsp+40h+var_20], 20006h
0x18000cbd7  lea     rcx, [rbp+arg_0]
0x18000cbdb  mov     rdx, [rdx+70h]
0x18000cbdf  call    cs:__imp_?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z; CRegKey::RemoteOpen(ushort const *,HKEY__ *,ushort const *,ulong)
0x18000cbe6  nop     dword ptr [rax+rax+00h]
0x18000cbeb  mov     ecx, eax
0x18000cbed  mov     r9d, 0B0Eh
0x18000cbf3  mov     ebx, eax
0x18000cbf5  call    ElValidateWin32_4
0x18000cbfa  test    eax, eax
0x18000cbfc  jnz     loc_18000C82F
0x18000cc02  mov     eax, [rdi+80h]
0x18000cc08  test    al, 20h
0x18000cc0a  jz      short loc_18000CC37
0x18000cc0c  mov     r8d, [rdi+0C0h]
0x18000cc13  lea     rdx, aMaximumblocksi; "MaximumBlockSize"
0x18000cc1a  lea     rcx, [rbp+arg_0]
0x18000cc1e  call    cs:__imp_?SetValueDword@CRegKey@@QEAAKPEBGK@Z; CRegKey::SetValueDword(ushort const *,ulong)
0x18000cc25  nop     dword ptr [rax+rax+00h]
0x18000cc2a  and     dword ptr [rdi+80h], 0FFFFFFDFh
0x18000cc31  mov     eax, [rdi+80h]
0x18000cc37  test    al, 40h
0x18000cc39  jz      short loc_18000CC60
0x18000cc3b  mov     r8d, [rdi+0C4h]
0x18000cc42  lea     rdx, aEnablevariable; "EnableVariableWindowExtension"
0x18000cc49  lea     rcx, [rbp+arg_0]
0x18000cc4d  call    cs:__imp_?SetValueDword@CRegKey@@QEAAKPEBGK@Z; CRegKey::SetValueDword(ushort const *,ulong)
0x18000cc54  nop     dword ptr [rax+rax+00h]
0x18000cc59  and     dword ptr [rdi+80h], 0FFFFFFBFh
0x18000cc60  lea     r8, aWillNotifyWdsT; "Will notify WDS Transport services of t"...
0x18000cc67  mov     edx, 10000h
0x18000cc6c  lea     rcx, qword_18003B770
0x18000cc73  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000cc7a  nop     dword ptr [rax+rax+00h]
0x18000cc7f  mov     rcx, [rdi+40h]; this
0x18000cc83  call    ?SignalSettingsChange@CWdsTransportServer@@QEAAJXZ; CWdsTransportServer::SignalSettingsChange(void)
0x18000cc88  mov     ebx, eax
0x18000cc8a  mov     r9, rdi
0x18000cc8d  mov     [rsp+40h+var_20], ebx
0x18000cc91  lea     r8, aCwdstransports_54; "<- CWdsTransportServicePolicy::Commit(0"...
0x18000cc98  mov     edx, 10000h
0x18000cc9d  lea     rcx, qword_18003B770
0x18000cca4  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000ccab  nop     dword ptr [rax+rax+00h]
0x18000ccb0  lea     rcx, [rbp+arg_0]; this
0x18000ccb4  call    ?Close@CRegKey@@QEAAXXZ; CRegKey::Close(void)
0x18000ccb9  lea     rcx, [rbp+var_10]
0x18000ccbd  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000ccc2  mov     rdi, [rsp+40h+arg_10]
0x18000ccc7  mov     eax, ebx
0x18000ccc9  mov     rbx, [rsp+40h+arg_8]
0x18000ccce  mov     r15, [rsp+40h+arg_18]
0x18000ccd3  add     rsp, 40h
0x18000ccd7  pop     rbp
0x18000ccd8  retn
0x18000ccda  lea     r8, aNetworkProfile; "Network Profile enum is set to an inval"...
0x18000cce1  mov     edx, 80000h
0x18000cce6  lea     rcx, qword_18003B770
0x18000cced  mov     ebx, 80070057h
0x18000ccf2  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000ccf9  nop     dword ptr [rax+rax+00h]
0x18000ccfe  jmp     short loc_18000CC8A
```
