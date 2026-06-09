# CWdsTransportMulticastSessionPolicy::Refresh(void)

- ea: `0x180017a10`
- end: `0x180017c9d`
- name: `?Refresh@CWdsTransportMulticastSessionPolicy@@UEAAJXZ`
- size: `653`
- prototype: `__int64 __fastcall(CWdsTransportMulticastSessionPolicy *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180009e20`
- `0x180017a10`
- `0x18001811c`
- `0x180018240`

## import_xrefs

- `WdsCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x180017c28`
- `WdsCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x180017c28`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x180017abf`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x180017abf`
- `WdsCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x180017b03`
- `WdsCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x180017bb2`
- `WdsCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x180017bfb`
- `WdsCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x180017b03`
- `WdsCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x180017bb2`
- `WdsCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x180017bfb`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180017a56`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180017b57`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180017c68`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180017a56`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180017b57`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180017c68`

## string_xrefs

- `0x180017a92`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSMC\Protocol`

## pseudocode

```c
__int64 __fastcall CWdsTransportMulticastSessionPolicy::Refresh(CWdsTransportMulticastSessionPolicy *this)
{
  __int64 ValueDword; // rbx
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 ValueBool; // rsi
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v18; // [rsp+20h] [rbp-20h]
  _BYTE v19[16]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v20; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v21; // [rsp+78h] [rbp+38h] BYREF
  __int64 v22; // [rsp+80h] [rbp+40h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v19, (char *)this + 80);
  v22 = 0;
  v20 = 0;
  v21 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportMulticastSessionPolicy::Refresh(0x%p)", this);
  if ( *((_DWORD *)this + 32) )
  {
    LODWORD(ValueDword) = -1055915761;
    goto LABEL_25;
  }
  v3 = *((_QWORD *)this + 8);
  *((_DWORD *)this + 31) = 0;
  *((_DWORD *)this + 33) = 0;
  *((_DWORD *)this + 34) = 0;
  *((_DWORD *)this + 35) = 0;
  *((_DWORD *)this + 36) = 0;
  ValueDword = CRegKey::RemoteOpen(
                 (CRegKey *)&v22,
                 *(const unsigned __int16 **)(v3 + 112),
                 HKEY_LOCAL_MACHINE,
                 L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSMC\\Protocol",
                 0x20019u);
  if ( (unsigned int)ElValidateWin32_11(ValueDword, v4, v5, 1052)
    || (ValueDword = CRegKey::GetValueDword((CRegKey *)&v22, L"TpSlowClientHandling", &v20),
        (unsigned int)ElValidateWin32_11(ValueDword, v6, v7, 1060)) )
  {
    if ( (int)ValueDword <= 0 )
      goto LABEL_25;
    LODWORD(ValueDword) = (unsigned __int16)ValueDword;
LABEL_6:
    LODWORD(ValueDword) = ValueDword | 0x80070000;
    goto LABEL_25;
  }
  LODWORD(ValueDword) = 0;
  if ( v20 )
  {
    switch ( v20 )
    {
      case 1u:
        *((_DWORD *)this + 33) = 1;
        break;
      case 2u:
        *((_DWORD *)this + 33) = 2;
        break;
      case 3u:
        *((_DWORD *)this + 33) = 3;
        break;
      default:
        LODWORD(ValueDword) = -1055915746;
        CTrace::Trace(
          (CTrace *)qword_18003B770,
          0x80000u,
          L"Error: Encountered an unknown TPT Slow-Client Handling type: %u\n");
        break;
    }
  }
  else
  {
    LODWORD(ValueDword) = -1055915746;
  }
  if ( (int)ElValidateHr_12((unsigned int)ValueDword, v8, v9, 1065) >= 0 )
  {
    ValueBool = CRegKey::GetValueDword((CRegKey *)&v22, L"TpAutoKickThreshold", &v21);
    if ( !(unsigned int)ElValidateWin32_11(ValueBool, v11, v12, 1072) )
    {
      *((_DWORD *)this + 34) = v21 >> 10;
      ValueBool = CRegKey::GetValueDword((CRegKey *)&v22, L"TpMultiStreamCount", (unsigned int *)this + 35);
      if ( !(unsigned int)ElValidateWin32_11(ValueBool, v13, v14, 1080) )
      {
        ValueBool = CRegKey::GetValueBool((CRegKey *)&v22, L"TpSlowClientFallback", (int *)this + 36);
        if ( !(unsigned int)ElValidateWin32_11(ValueBool, v15, v16, 1084) )
        {
          *((_DWORD *)this + 31) = 1;
          goto LABEL_25;
        }
      }
    }
    if ( (int)ValueBool <= 0 )
    {
      LODWORD(ValueDword) = ValueBool;
      goto LABEL_25;
    }
    LODWORD(ValueDword) = (unsigned __int16)ValueBool;
    goto LABEL_6;
  }
LABEL_25:
  LODWORD(v18) = ValueDword;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportMulticastSessionPolicy::Refresh(0x%p) =%x",
    this,
    v18);
  CRegKey::Close((CRegKey *)&v22);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v19);
  return (unsigned int)ValueDword;
}

```

## disassembly

```asm
0x180017a10  mov     [rsp-28h+arg_18], rbx
0x180017a15  push    rbp
0x180017a16  push    rsi
0x180017a17  push    rdi
0x180017a18  push    r14
0x180017a1a  push    r15
0x180017a1c  mov     rbp, rsp
0x180017a1f  sub     rsp, 40h
0x180017a23  mov     rdi, rcx
0x180017a26  lea     rdx, [rcx+50h]
0x180017a2a  lea     rcx, [rbp+var_10]
0x180017a2e  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x180017a33  and     [rbp+arg_10], 0
0x180017a38  lea     r8, aCwdstransportm_3; "-> CWdsTransportMulticastSessionPolicy:"...
0x180017a3f  and     [rbp+arg_0], 0
0x180017a43  lea     rcx, qword_18003B770
0x180017a4a  and     [rbp+arg_8], 0
0x180017a4e  mov     r9, rdi
0x180017a51  mov     edx, 10000h
0x180017a56  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180017a5d  nop     dword ptr [rax+rax+00h]
0x180017a62  cmp     dword ptr [rdi+80h], 0
0x180017a69  jz      short loc_180017A75
0x180017a6b  mov     ebx, 0C110010Fh
0x180017a70  jmp     loc_180017C4E
0x180017a75  mov     rdx, [rdi+40h]
0x180017a79  lea     r15, [rdi+8Ch]
0x180017a80  and     dword ptr [rdi+7Ch], 0
0x180017a84  lea     r14, [rdi+90h]
0x180017a8b  and     dword ptr [rdi+84h], 0
0x180017a92  lea     r9, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\WD"...
0x180017a99  and     dword ptr [rdi+88h], 0
0x180017aa0  lea     rcx, [rbp+arg_10]
0x180017aa4  and     dword ptr [r15], 0
0x180017aa8  mov     r8, 0FFFFFFFF80000002h
0x180017aaf  and     dword ptr [r14], 0
0x180017ab3  mov     rdx, [rdx+70h]
0x180017ab7  mov     [rsp+40h+var_20], 20019h
0x180017abf  call    cs:__imp_?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z; CRegKey::RemoteOpen(ushort const *,HKEY__ *,ushort const *,ulong)
0x180017ac6  nop     dword ptr [rax+rax+00h]
0x180017acb  mov     ecx, eax
0x180017acd  mov     r9d, 41Ch
0x180017ad3  mov     ebx, eax
0x180017ad5  call    ElValidateWin32_11
0x180017ada  test    eax, eax
0x180017adc  jz      short loc_180017AF4
0x180017ade  test    ebx, ebx
0x180017ae0  jle     loc_180017C4E
0x180017ae6  movzx   ebx, bx
0x180017ae9  or      ebx, 80070000h
0x180017aef  jmp     loc_180017C4E
0x180017af4  lea     r8, [rbp+arg_0]
0x180017af8  lea     rdx, aTpslowclientha; "TpSlowClientHandling"
0x180017aff  lea     rcx, [rbp+arg_10]
0x180017b03  call    cs:__imp_?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z; CRegKey::GetValueDword(ushort const *,ulong *)
0x180017b0a  nop     dword ptr [rax+rax+00h]
0x180017b0f  mov     ecx, eax
0x180017b11  mov     r9d, 424h
0x180017b17  mov     ebx, eax
0x180017b19  call    ElValidateWin32_11
0x180017b1e  test    eax, eax
0x180017b20  jnz     short loc_180017ADE
0x180017b22  mov     r9d, [rbp+arg_0]
0x180017b26  xor     ebx, ebx
0x180017b28  mov     ecx, r9d
0x180017b2b  test    r9d, r9d
0x180017b2e  jz      short loc_180017B89
0x180017b30  sub     ecx, 1
0x180017b33  jz      short loc_180017B7D
0x180017b35  sub     ecx, 1
0x180017b38  jz      short loc_180017B71
0x180017b3a  cmp     ecx, 1
0x180017b3d  jz      short loc_180017B65
0x180017b3f  lea     r8, aErrorEncounter; "Error: Encountered an unknown TPT Slow-"...
0x180017b46  mov     edx, 80000h
0x180017b4b  lea     rcx, qword_18003B770
0x180017b52  mov     ebx, 0C110011Eh
0x180017b57  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180017b5e  nop     dword ptr [rax+rax+00h]
0x180017b63  jmp     short loc_180017B8E
0x180017b65  mov     dword ptr [rdi+84h], 3
0x180017b6f  jmp     short loc_180017B8E
0x180017b71  mov     dword ptr [rdi+84h], 2
0x180017b7b  jmp     short loc_180017B8E
0x180017b7d  mov     dword ptr [rdi+84h], 1
0x180017b87  jmp     short loc_180017B8E
0x180017b89  mov     ebx, 0C110011Eh
0x180017b8e  mov     r9d, 429h
0x180017b94  mov     ecx, ebx
0x180017b96  call    ElValidateHr_12
0x180017b9b  test    eax, eax
0x180017b9d  js      loc_180017C4E
0x180017ba3  lea     r8, [rbp+arg_8]
0x180017ba7  lea     rdx, aTpautokickthre; "TpAutoKickThreshold"
0x180017bae  lea     rcx, [rbp+arg_10]
0x180017bb2  call    cs:__imp_?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z; CRegKey::GetValueDword(ushort const *,ulong *)
0x180017bb9  nop     dword ptr [rax+rax+00h]
0x180017bbe  mov     ecx, eax
0x180017bc0  mov     r9d, 430h
0x180017bc6  mov     esi, eax
0x180017bc8  call    ElValidateWin32_11
0x180017bcd  test    eax, eax
0x180017bcf  jz      short loc_180017BE1
0x180017bd1  test    esi, esi
0x180017bd3  jg      short loc_180017BD9
0x180017bd5  mov     ebx, esi
0x180017bd7  jmp     short loc_180017C4E
0x180017bd9  movzx   ebx, si
0x180017bdc  jmp     loc_180017AE9
0x180017be1  mov     eax, [rbp+arg_8]
0x180017be4  lea     rdx, aTpmultistreamc; "TpMultiStreamCount"
0x180017beb  shr     eax, 0Ah
0x180017bee  lea     rcx, [rbp+arg_10]
0x180017bf2  mov     r8, r15
0x180017bf5  mov     [rdi+88h], eax
0x180017bfb  call    cs:__imp_?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z; CRegKey::GetValueDword(ushort const *,ulong *)
0x180017c02  nop     dword ptr [rax+rax+00h]
0x180017c07  mov     ecx, eax
0x180017c09  mov     r9d, 438h
0x180017c0f  mov     esi, eax
0x180017c11  call    ElValidateWin32_11
0x180017c16  test    eax, eax
0x180017c18  jnz     short loc_180017BD1
0x180017c1a  mov     r8, r14
0x180017c1d  lea     rdx, aTpslowclientfa; "TpSlowClientFallback"
0x180017c24  lea     rcx, [rbp+arg_10]
0x180017c28  call    cs:__imp_?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z; CRegKey::GetValueBool(ushort const *,int *)
0x180017c2f  nop     dword ptr [rax+rax+00h]
0x180017c34  mov     ecx, eax
0x180017c36  mov     r9d, 43Ch
0x180017c3c  mov     esi, eax
0x180017c3e  call    ElValidateWin32_11
0x180017c43  test    eax, eax
0x180017c45  jnz     short loc_180017BD1
0x180017c47  mov     dword ptr [rdi+7Ch], 1
0x180017c4e  mov     r9, rdi
0x180017c51  mov     [rsp+40h+var_20], ebx
0x180017c55  lea     r8, aCwdstransportm; "<- CWdsTransportMulticastSessionPolicy:"...
0x180017c5c  mov     edx, 10000h
0x180017c61  lea     rcx, qword_18003B770
0x180017c68  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180017c6f  nop     dword ptr [rax+rax+00h]
0x180017c74  lea     rcx, [rbp+arg_10]; this
0x180017c78  call    ?Close@CRegKey@@QEAAXXZ; CRegKey::Close(void)
0x180017c7d  lea     rcx, [rbp+var_10]
0x180017c81  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x180017c86  mov     eax, ebx
0x180017c88  mov     rbx, [rsp+40h+arg_18]
0x180017c90  add     rsp, 40h
0x180017c94  pop     r15
0x180017c96  pop     r14
0x180017c98  pop     rdi
0x180017c99  pop     rsi
0x180017c9a  pop     rbp
0x180017c9b  retn
```
