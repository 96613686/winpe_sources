# CWdsTransportNamespace::Deregister(short)

- ea: `0x180011874`
- end: `0x180011a06`
- name: `?Deregister@CWdsTransportNamespace@@UEAAJF@Z`
- size: `402`
- prototype: `__int64 __fastcall(CWdsTransportNamespace *__hidden this, __int16)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180011a10`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180011874`
- `0x1800137c4`
- `0x18001a564`
- `0x18001e9f0`

## import_xrefs

- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180011985`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180011985`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800118ca`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180011942`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001196d`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800119a9`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800119cb`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800118ca`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180011942`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001196d`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800119a9`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800119cb`

## string_xrefs

- `0x180011933`: `Successfully deregistered the namespace %s.\nWill now update internal object state.\n`

## pseudocode

```c
__int64 __fastcall CWdsTransportNamespace::Deregister(CWdsTransportNamespace *this, __int16 a2)
{
  __int64 v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  LPSYSTEMTIME v8; // [rsp+20h] [rbp-58h]
  _BYTE v9[16]; // [rsp+30h] [rbp-48h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-38h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v9, (char *)this + 64);
  SystemTime = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportNamespace::Deregister(0x%p)", this);
  if ( *((_DWORD *)this + 31) )
  {
    v4 = (unsigned int)CWdsTptMgmtClient::DeregisterNamespace(
                         *((CWdsTptMgmtClient **)this + 14),
                         *((void **)this + 22),
                         a2 == -1,
                         (int *)this + 46,
                         &SystemTime);
    if ( (int)ElValidateHr_7(v4, v5, v6, 1810) >= 0 )
    {
      CTrace::Trace(
        (CTrace *)qword_18003B770,
        0x10000u,
        L"Successfully deregistered the namespace %s.\nWill now update internal object state.\n",
        *((_QWORD *)this + 17));
      *((_DWORD *)this + 31) = 0;
      if ( *((_DWORD *)this + 46) )
      {
        if ( a2 == -1 )
          CTrace::Trace(
            (CTrace *)qword_18003B770,
            0x40000u,
            L"DeregisterNamespace requested that active sessions be terminated\n"
             "but the server tombstoned the namespace!");
        if ( !SystemTimeToVariantTime(&SystemTime, (DOUBLE *)this + 24) )
        {
          LODWORD(v4) = -1055915765;
          CTrace::Trace((CTrace *)qword_18003B770, 0x80000u, L"Received an invalid tombstone time from the server.\n");
        }
      }
    }
  }
  else
  {
    LODWORD(v4) = -1055915768;
  }
  LODWORD(v8) = v4;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"<- CWdsTransportNamespace::Deregister(0x%p) =%x", this, v8);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180011874  mov     [rsp+arg_8], rbx
0x180011879  mov     [rsp+arg_10], rbp
0x18001187e  push    rsi
0x18001187f  push    rdi
0x180011880  push    r14
0x180011882  sub     rsp, 60h
0x180011886  mov     rax, cs:__security_cookie
0x18001188d  xor     rax, rsp
0x180011890  mov     [rsp+78h+var_28], rax
0x180011895  movzx   esi, dx
0x180011898  mov     rbx, rcx
0x18001189b  lea     rdx, [rcx+40h]
0x18001189f  lea     rcx, [rsp+78h+var_48]
0x1800118a4  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x1800118a9  xorps   xmm0, xmm0
0x1800118ac  lea     r14, qword_18003B770
0x1800118b3  mov     rcx, r14
0x1800118b6  lea     r8, aCwdstransportn_38; "-> CWdsTransportNamespace::Deregister(0"...
0x1800118bd  mov     r9, rbx
0x1800118c0  mov     edx, 10000h
0x1800118c5  movups  xmmword ptr [rsp+78h+SystemTime.wYear], xmm0
0x1800118ca  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800118d1  nop     dword ptr [rax+rax+00h]
0x1800118d6  cmp     dword ptr [rbx+7Ch], 0
0x1800118da  jnz     short loc_1800118E6
0x1800118dc  mov     edi, 0C1100108h
0x1800118e1  jmp     loc_1800119B5
0x1800118e6  mov     rdx, [rbx+0B0h]; void *
0x1800118ed  lea     rax, [rsp+78h+SystemTime]
0x1800118f2  mov     rcx, [rbx+70h]; this
0x1800118f6  lea     rbp, [rbx+0B8h]
0x1800118fd  xor     r8d, r8d
0x180011900  mov     [rsp+78h+var_58], rax; LPSYSTEMTIME
0x180011905  cmp     si, 0FFFFh
0x180011909  mov     r9, rbp; int *
0x18001190c  setz    r8b; int
0x180011910  call    ?DeregisterNamespace@CWdsTptMgmtClient@@QEAAJPEAXHPEAHPEAU_SYSTEMTIME@@@Z; CWdsTptMgmtClient::DeregisterNamespace(void *,int,int *,_SYSTEMTIME *)
0x180011915  mov     r9d, 712h
0x18001191b  mov     ecx, eax
0x18001191d  mov     edi, eax
0x18001191f  call    ElValidateHr_7
0x180011924  test    eax, eax
0x180011926  js      loc_1800119B5
0x18001192c  mov     r9, [rbx+88h]
0x180011933  lea     r8, aSuccessfullyDe; "Successfully deregistered the namespace"...
0x18001193a  mov     edx, 10000h
0x18001193f  mov     rcx, r14
0x180011942  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180011949  nop     dword ptr [rax+rax+00h]
0x18001194e  and     dword ptr [rbx+7Ch], 0
0x180011952  cmp     dword ptr [rbp+0], 0
0x180011956  jz      short loc_1800119B5
0x180011958  cmp     si, 0FFFFh
0x18001195c  jnz     short loc_180011979
0x18001195e  lea     r8, aDeregistername; "DeregisterNamespace requested that acti"...
0x180011965  mov     edx, 40000h
0x18001196a  mov     rcx, r14
0x18001196d  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180011974  nop     dword ptr [rax+rax+00h]
0x180011979  lea     rdx, [rbx+0C0h]; pvtime
0x180011980  lea     rcx, [rsp+78h+SystemTime]; lpSystemTime
0x180011985  call    cs:__imp_SystemTimeToVariantTime
0x18001198c  nop     dword ptr [rax+rax+00h]
0x180011991  test    eax, eax
0x180011993  jnz     short loc_1800119B5
0x180011995  lea     r8, aReceivedAnInva; "Received an invalid tombstone time from"...
0x18001199c  mov     edx, 80000h
0x1800119a1  mov     rcx, r14
0x1800119a4  mov     edi, 0C110010Bh
0x1800119a9  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800119b0  nop     dword ptr [rax+rax+00h]
0x1800119b5  mov     r9, rbx
0x1800119b8  mov     dword ptr [rsp+78h+var_58], edi
0x1800119bc  lea     r8, aCwdstransportn_69; "<- CWdsTransportNamespace::Deregister(0"...
0x1800119c3  mov     edx, 10000h
0x1800119c8  mov     rcx, r14
0x1800119cb  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800119d2  nop     dword ptr [rax+rax+00h]
0x1800119d7  lea     rcx, [rsp+78h+var_48]
0x1800119dc  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x1800119e1  mov     eax, edi
0x1800119e3  mov     rcx, [rsp+78h+var_28]
0x1800119e8  xor     rcx, rsp; StackCookie
0x1800119eb  call    __security_check_cookie
0x1800119f0  lea     r11, [rsp+78h+var_18]
0x1800119f5  mov     rbx, [r11+28h]
0x1800119f9  mov     rbp, [r11+30h]
0x1800119fd  mov     rsp, r11
0x180011a00  pop     r14
0x180011a02  pop     rdi
0x180011a03  pop     rsi
0x180011a04  retn
```
