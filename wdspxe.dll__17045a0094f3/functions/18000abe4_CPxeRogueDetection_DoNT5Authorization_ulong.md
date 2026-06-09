# CPxeRogueDetection::DoNT5Authorization(ulong *)

- ea: `0x18000abe4`
- end: `0x18000adf0`
- name: `?DoNT5Authorization@CPxeRogueDetection@@AEAAKPEAK@Z`
- size: `524`
- prototype: `unsigned int __fastcall(CPxeRogueDetection *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000ea3c`

## callees

- `0x180001acc`
- `0x180002a30`
- `0x18000abe4`
- `0x18000b7c4`
- `0x18000eda0`
- `0x18000f8b8`
- `0x180011068`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000add4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000add4`
- `ADVAPI32!RegCloseKey` at `0x18000ad5f`
- `ADVAPI32!RegCloseKey` at `0x18000ad5f`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ad20`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ad20`
- `WDSSRV!WdsGetInterfaces` at `0x18000ac14`
- `WDSSRV!WdsGetInterfaces` at `0x18000ac7a`
- `WDSSRV!WdsGetInterfaces` at `0x18000ac14`
- `WDSSRV!WdsGetInterfaces` at `0x18000ac7a`
- `WdsCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x18000ad41`
- `WdsCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x18000ad41`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000ad98`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000adbb`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000ad98`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000adbb`

## string_xrefs

- `0x18000ad04`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSPXE\AuthCache`
- `0x18000ad75`: `Rogue Detection: WDSPXE authorized based on cached results.`

## pseudocode

```c
__int64 __fastcall CPxeRogueDetection::DoNT5Authorization(const unsigned __int16 **this, unsigned int *a2)
{
  int v4; // r14d
  unsigned int Interfaces; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned int v8; // edi
  struct tagWDS_INTERFACE_INFO *v9; // rax
  struct tagWDS_INTERFACE_INFO *v10; // r15
  unsigned int v11; // eax
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int DhcpAuthorization; // eax
  BOOL v17; // ebx
  LSTATUS ValueDword; // ebx
  int v19; // edx
  unsigned __int64 v20; // [rsp+78h] [rbp+48h] BYREF
  int v21; // [rsp+80h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+58h] BYREF

  LODWORD(v20) = 0;
  v4 = 0;
  v21 = 0;
  Interfaces = WdsGetInterfaces(g_hPxeProvider, 0, &v20);
  v8 = Interfaces;
  if ( Interfaces != 111 )
  {
    ElValidateWin32_4(Interfaces, v6, v7, 943);
    goto LABEL_23;
  }
  v9 = (struct tagWDS_INTERFACE_INFO *)operator new[]((unsigned int)v20, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  if ( !v9 )
  {
    v8 = 8;
    goto LABEL_5;
  }
  v13 = WdsGetInterfaces(g_hPxeProvider, v9, &v20);
  v8 = ElValidateWin32_4(v13, v14, v15, 956);
  if ( !v8 )
  {
    LODWORD(v20) = (unsigned int)v20 / 0x30;
    DhcpAuthorization = CPxeRogueDetection::GetDhcpAuthorization((CPxeRogueDetection *)this, v10, v20, &v21);
    v8 = DhcpAuthorization;
    if ( !DhcpAuthorization )
    {
      v17 = v21 != 0;
      CPxeRogueDetection::SetAuthState((CPxeRogueDetection *)this, v17);
      CPxeRogueDetection::SaveAuthCache(this, v17);
      goto LABEL_22;
    }
    if ( DhcpAuthorization != 1157 )
    {
      v21 = 0;
      hKey = 0;
      ValueDword = RegOpenKeyExW(
                     HKEY_LOCAL_MACHINE,
                     L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSPXE\\AuthCache",
                     0,
                     0x20119u,
                     &hKey);
      if ( !ValueDword )
      {
        ValueDword = CRegKey::GetValueDword((CRegKey *)&hKey, this[29], (unsigned int *)&v21);
        if ( !ValueDword )
          v4 = v21;
      }
      if ( hKey )
        RegCloseKey(hKey);
      if ( !ValueDword && v4 == 1 )
      {
        Trace(0x20000u, L"Rogue Detection: WDSPXE authorized based on cached results.");
        CEventLog::Log((CEventLog *)qword_18001CC40, 0x81070303, 0, 0);
        v19 = 1;
LABEL_21:
        CPxeRogueDetection::SetAuthState((CPxeRogueDetection *)this, v19);
        goto LABEL_22;
      }
      CEventLog::Log((CEventLog *)qword_18001CC40, 0xC1070304, 0, 0);
    }
    v19 = 0;
    goto LABEL_21;
  }
LABEL_22:
  operator delete[](v10);
LABEL_23:
  if ( !v8 )
  {
    v11 = *((_DWORD *)this + 14);
    goto LABEL_6;
  }
LABEL_5:
  v11 = *((_DWORD *)this + 15);
LABEL_6:
  *a2 = v11;
  return v8;
}

```

## disassembly

```asm
0x18000abe4  push    rbp
0x18000abe6  push    rbx
0x18000abe7  push    rsi
0x18000abe8  push    rdi
0x18000abe9  push    r12
0x18000abeb  push    r14
0x18000abed  push    r15
0x18000abef  mov     rbp, rsp
0x18000abf2  sub     rsp, 30h
0x18000abf6  and     dword ptr [rbp+arg_8], 0
0x18000abfa  lea     r8, [rbp+arg_8]
0x18000abfe  mov     r12, rdx
0x18000ac01  mov     rsi, rcx
0x18000ac04  mov     rcx, cs:?g_hPxeProvider@@3PEAXEA; void * g_hPxeProvider
0x18000ac0b  xor     r14d, r14d
0x18000ac0e  and     [rbp+arg_10], r14d
0x18000ac12  xor     edx, edx
0x18000ac14  call    cs:__imp_WdsGetInterfaces
0x18000ac1b  nop     dword ptr [rax+rax+00h]
0x18000ac20  mov     edi, eax
0x18000ac22  cmp     eax, 6Fh ; 'o'
0x18000ac25  jz      short loc_18000AC39
0x18000ac27  mov     r9d, 3AFh
0x18000ac2d  mov     ecx, eax
0x18000ac2f  call    ElValidateWin32_4
0x18000ac34  jmp     loc_18000ADE0
0x18000ac39  mov     ecx, dword ptr [rbp+arg_8]; unsigned __int64
0x18000ac3c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ac43  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000ac48  mov     r15, rax
0x18000ac4b  test    rax, rax
0x18000ac4e  jnz     short loc_18000AC6C
0x18000ac50  lea     edi, [rax+8]
0x18000ac53  mov     eax, [rsi+3Ch]
0x18000ac56  mov     [r12], eax
0x18000ac5a  mov     eax, edi
0x18000ac5c  add     rsp, 30h
0x18000ac60  pop     r15
0x18000ac62  pop     r14
0x18000ac64  pop     r12
0x18000ac66  pop     rdi
0x18000ac67  pop     rsi
0x18000ac68  pop     rbx
0x18000ac69  pop     rbp
0x18000ac6a  retn
0x18000ac6c  mov     rcx, cs:?g_hPxeProvider@@3PEAXEA; void * g_hPxeProvider
0x18000ac73  lea     r8, [rbp+arg_8]
0x18000ac77  mov     rdx, r15
0x18000ac7a  call    cs:__imp_WdsGetInterfaces
0x18000ac81  nop     dword ptr [rax+rax+00h]
0x18000ac86  mov     ecx, eax
0x18000ac88  mov     r9d, 3BCh
0x18000ac8e  call    ElValidateWin32_4
0x18000ac93  mov     edi, eax
0x18000ac95  test    eax, eax
0x18000ac97  jnz     loc_18000ADD1
0x18000ac9d  mov     ecx, dword ptr [rbp+arg_8]
0x18000aca0  lea     r9, [rbp+arg_10]; int *
0x18000aca4  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000acae  mul     rcx
0x18000acb1  mov     rcx, rsi; this
0x18000acb4  shr     rdx, 5
0x18000acb8  mov     dword ptr [rbp+arg_8], edx
0x18000acbb  mov     r8d, edx; unsigned int
0x18000acbe  mov     rdx, r15; struct tagWDS_INTERFACE_INFO *
0x18000acc1  call    ?GetDhcpAuthorization@CPxeRogueDetection@@AEAAKPEAUtagWDS_INTERFACE_INFO@@KPEAH@Z; CPxeRogueDetection::GetDhcpAuthorization(tagWDS_INTERFACE_INFO *,ulong,int *)
0x18000acc6  mov     edi, eax
0x18000acc8  test    eax, eax
0x18000acca  jnz     short loc_18000ACED
0x18000accc  xor     ebx, ebx
0x18000acce  mov     rcx, rsi; this
0x18000acd1  cmp     [rbp+arg_10], ebx
0x18000acd4  setnz   bl
0x18000acd7  mov     edx, ebx; int
0x18000acd9  call    ?SetAuthState@CPxeRogueDetection@@AEAAXH@Z; CPxeRogueDetection::SetAuthState(int)
0x18000acde  mov     edx, ebx; int
0x18000ace0  mov     rcx, rsi; this
0x18000ace3  call    ?SaveAuthCache@CPxeRogueDetection@@AEAAKH@Z; CPxeRogueDetection::SaveAuthCache(int)
0x18000ace8  jmp     loc_18000ADD1
0x18000aced  cmp     eax, 485h
0x18000acf2  jz      loc_18000ADC7
0x18000acf8  and     [rbp+arg_10], r14d
0x18000acfc  lea     rax, [rbp+hKey]
0x18000ad00  and     [rbp+hKey], r14
0x18000ad04  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\WD"...
0x18000ad0b  mov     r9d, 20119h; samDesired
0x18000ad11  mov     [rsp+30h+phkResult], rax; phkResult
0x18000ad16  xor     r8d, r8d; ulOptions
0x18000ad19  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ad20  call    cs:__imp_RegOpenKeyExW
0x18000ad27  nop     dword ptr [rax+rax+00h]
0x18000ad2c  mov     ebx, eax
0x18000ad2e  test    eax, eax
0x18000ad30  jnz     short loc_18000AD56
0x18000ad32  mov     rdx, [rsi+0E8h]
0x18000ad39  lea     r8, [rbp+arg_10]
0x18000ad3d  lea     rcx, [rbp+hKey]
0x18000ad41  call    cs:__imp_?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z; CRegKey::GetValueDword(ushort const *,ulong *)
0x18000ad48  nop     dword ptr [rax+rax+00h]
0x18000ad4d  test    eax, eax
0x18000ad4f  mov     ebx, eax
0x18000ad51  cmovz   r14d, [rbp+arg_10]
0x18000ad56  mov     rcx, [rbp+hKey]; hKey
0x18000ad5a  test    rcx, rcx
0x18000ad5d  jz      short loc_18000AD6B
0x18000ad5f  call    cs:__imp_RegCloseKey
0x18000ad66  nop     dword ptr [rax+rax+00h]
0x18000ad6b  test    ebx, ebx
0x18000ad6d  jnz     short loc_18000ADA9
0x18000ad6f  cmp     r14d, 1
0x18000ad73  jnz     short loc_18000ADA9
0x18000ad75  lea     rdx, aRogueDetection_16; "Rogue Detection: WDSPXE authorized base"...
0x18000ad7c  mov     ecx, 20000h; unsigned int
0x18000ad81  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x18000ad86  xor     r9d, r9d
0x18000ad89  lea     rcx, qword_18001CC40
0x18000ad90  xor     r8d, r8d
0x18000ad93  mov     edx, 81070303h
0x18000ad98  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x18000ad9f  nop     dword ptr [rax+rax+00h]
0x18000ada4  mov     edx, r14d
0x18000ada7  jmp     short loc_18000ADC9
0x18000ada9  xor     r9d, r9d
0x18000adac  lea     rcx, qword_18001CC40
0x18000adb3  xor     r8d, r8d
0x18000adb6  mov     edx, 0C1070304h
0x18000adbb  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x18000adc2  nop     dword ptr [rax+rax+00h]
0x18000adc7  xor     edx, edx; int
0x18000adc9  mov     rcx, rsi; this
0x18000adcc  call    ?SetAuthState@CPxeRogueDetection@@AEAAXH@Z; CPxeRogueDetection::SetAuthState(int)
0x18000add1  mov     rcx, r15
0x18000add4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000addb  nop     dword ptr [rax+rax+00h]
0x18000ade0  test    edi, edi
0x18000ade2  jnz     loc_18000AC53
0x18000ade8  mov     eax, [rsi+38h]
0x18000adeb  jmp     loc_18000AC56
```
