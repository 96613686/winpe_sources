# CWdsTransportNamespace::Register(void)

- ea: `0x1800125f4`
- end: `0x180012746`
- name: `?Register@CWdsTransportNamespace@@UEAAJXZ`
- size: `338`
- prototype: `__int64 __fastcall(CWdsTransportNamespace *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012750`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180011024`
- `0x1800125f4`
- `0x1800137c4`
- `0x18001b0a4`
- `0x18001e9c2`
- `0x18001e9f0`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001264a`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800126d8`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001270c`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001264a`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800126d8`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001270c`

## string_xrefs

- `0x1800126c5`: `Successfully registered the namespace %s.\nWill now update internal object state.\n`

## pseudocode

```c
__int64 __fastcall CWdsTransportNamespace::Register(CWdsTransportNamespace *this)
{
  __int64 v2; // rdi
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // r8
  int v8; // [rsp+20h] [rbp-A8h]
  _BYTE v9[16]; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v10[112]; // [rsp+40h] [rbp-88h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v9, (char *)this + 64);
  memset_0(v10, 0, sizeof(v10));
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportNamespace::Register(0x%p)", this);
  if ( *((_DWORD *)this + 31) )
  {
    LODWORD(v2) = -1055915769;
  }
  else if ( *((_DWORD *)this + 32) )
  {
    LODWORD(v2) = -1055915764;
  }
  else
  {
    v2 = (unsigned int)CWdsTransportNamespace::ConstructServerNamespaceData(this, (struct _WDSTPT_NAMESPACE *)v10);
    if ( (int)ElValidateHr_7(v2, v3, v4, 1731) >= 0 )
    {
      v2 = (unsigned int)CWdsTptMgmtClient::RegisterNamespace(
                           *((CWdsTptMgmtClient **)this + 14),
                           (struct _WDSTPT_NAMESPACE *)v10,
                           (void **)this + 22);
      if ( (int)ElValidateHr_7(v2, v5, v6, 1738) >= 0 )
      {
        CTrace::Trace(
          (CTrace *)qword_18003B770,
          0x10000u,
          L"Successfully registered the namespace %s.\nWill now update internal object state.\n",
          *((_QWORD *)this + 17));
        *((_DWORD *)this + 31) = 1;
        *((_DWORD *)this + 32) = 1;
      }
    }
  }
  v8 = v2;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"<- CWdsTransportNamespace::Register(0x%p) =%x", this, v8);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v9);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800125f4  mov     [rsp+arg_8], rbx
0x1800125f9  push    rdi
0x1800125fa  sub     rsp, 0C0h
0x180012601  mov     rax, cs:__security_cookie
0x180012608  xor     rax, rsp
0x18001260b  mov     [rsp+0C8h+var_18], rax
0x180012613  mov     rbx, rcx
0x180012616  lea     rdx, [rcx+40h]
0x18001261a  lea     rcx, [rsp+0C8h+var_98]
0x18001261f  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x180012624  xor     edx, edx; Val
0x180012626  lea     rcx, [rsp+0C8h+var_88]; void *
0x18001262b  lea     r8d, [rdx+70h]; Size
0x18001262f  call    memset_0
0x180012634  mov     r9, rbx
0x180012637  lea     r8, aCwdstransportn_15; "-> CWdsTransportNamespace::Register(0x%"...
0x18001263e  mov     edx, 10000h
0x180012643  lea     rcx, qword_18003B770
0x18001264a  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180012651  nop     dword ptr [rax+rax+00h]
0x180012656  cmp     dword ptr [rbx+7Ch], 0
0x18001265a  jz      short loc_180012666
0x18001265c  mov     edi, 0C1100107h
0x180012661  jmp     loc_1800126F2
0x180012666  cmp     dword ptr [rbx+80h], 0
0x18001266d  jz      short loc_180012676
0x18001266f  mov     edi, 0C110010Ch
0x180012674  jmp     short loc_1800126F2
0x180012676  lea     rdx, [rsp+0C8h+var_88]; struct _WDSTPT_NAMESPACE *
0x18001267b  mov     rcx, rbx; this
0x18001267e  call    ?ConstructServerNamespaceData@CWdsTransportNamespace@@AEAAJPEAU_WDSTPT_NAMESPACE@@@Z; CWdsTransportNamespace::ConstructServerNamespaceData(_WDSTPT_NAMESPACE *)
0x180012683  mov     r9d, 6C3h
0x180012689  mov     ecx, eax
0x18001268b  mov     edi, eax
0x18001268d  call    ElValidateHr_7
0x180012692  test    eax, eax
0x180012694  js      short loc_1800126F2
0x180012696  mov     rcx, [rbx+70h]; this
0x18001269a  lea     r8, [rbx+0B0h]; void **
0x1800126a1  lea     rdx, [rsp+0C8h+var_88]; struct _WDSTPT_NAMESPACE *
0x1800126a6  call    ?RegisterNamespace@CWdsTptMgmtClient@@QEAAJPEAU_WDSTPT_NAMESPACE@@PEAPEAX@Z; CWdsTptMgmtClient::RegisterNamespace(_WDSTPT_NAMESPACE *,void * *)
0x1800126ab  mov     r9d, 6CAh
0x1800126b1  mov     ecx, eax
0x1800126b3  mov     edi, eax
0x1800126b5  call    ElValidateHr_7
0x1800126ba  test    eax, eax
0x1800126bc  js      short loc_1800126F2
0x1800126be  mov     r9, [rbx+88h]
0x1800126c5  lea     r8, aSuccessfullyRe_4; "Successfully registered the namespace %"...
0x1800126cc  mov     edx, 10000h
0x1800126d1  lea     rcx, qword_18003B770
0x1800126d8  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800126df  nop     dword ptr [rax+rax+00h]
0x1800126e4  mov     eax, 1
0x1800126e9  mov     [rbx+7Ch], eax
0x1800126ec  mov     [rbx+80h], eax
0x1800126f2  mov     r9, rbx
0x1800126f5  mov     [rsp+0C8h+var_A8], edi
0x1800126f9  lea     r8, aCwdstransportn_16; "<- CWdsTransportNamespace::Register(0x%"...
0x180012700  mov     edx, 10000h
0x180012705  lea     rcx, qword_18003B770
0x18001270c  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180012713  nop     dword ptr [rax+rax+00h]
0x180012718  lea     rcx, [rsp+0C8h+var_98]
0x18001271d  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x180012722  mov     eax, edi
0x180012724  mov     rcx, [rsp+0C8h+var_18]
0x18001272c  xor     rcx, rsp; StackCookie
0x18001272f  call    __security_check_cookie
0x180012734  mov     rbx, [rsp+0C8h+arg_8]
0x18001273c  add     rsp, 0C0h
0x180012743  pop     rdi
0x180012744  retn
```
