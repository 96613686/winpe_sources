# CWwanUicc::runOobeDssaSlotSwitch(bool)

- ea: `0x1800708dc`
- end: `0x180070b29`
- name: `?runOobeDssaSlotSwitch@CWwanUicc@@AEAAX_N@Z`
- size: `589`
- prototype: `void __fastcall(CWwanUicc *__hidden this, bool)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180068eac`
- `0x18006d9e4`

## callees

- `0x180012300`
- `0x180014f1c`
- `0x180064698`
- `0x18006b6e0`
- `0x18006dfa8`
- `0x1800708dc`
- `0x1800c5dd0`
- `0x1800c6454`
- `0x1800c6518`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180070a93`
- `ntdll!RtlPublishWnfStateData` at `0x180070a93`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x180070910`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x180070910`
- `api-ms-win-core-sysinfo-l1-2-3!GetOsManufacturingMode` at `0x18007098b`
- `api-ms-win-core-sysinfo-l1-2-3!GetOsManufacturingMode` at `0x18007098b`

## string_xrefs

- `0x180070921`: `check for OOBEComplete failed, assume completed`
- `0x180070995`: `Failed to get Manufacturing mode, assume off.`
- `0x180070aa5`: `failed to publish WNF WNF_WWAN_OOBE_DISCOVERY_TASK_TRIGGER, status = 0x%x`
- `0x180070ab3`: ` published WNF WNF_WWAN_OOBE_DISCOVERY_TASK_TRIGGER`
- `0x180070add`: ` Slot Switch logic should not be executed. isOobeComplete:%d isAuditMode:%d isManufacturingMode:%d IsUpgradedInstallation:%d isDSSASupported:%d isEsimProfileStateChange:%d`

## pseudocode

```c
void __fastcall CWwanUicc::runOobeDssaSlotSwitch(CWwanUicc *this, unsigned __int8 a2)
{
  int v3; // edi
  BOOL v4; // esi
  int v5; // eax
  CWwanUicc *v6; // rcx
  unsigned int EmbeddedSlotIndex; // esi
  int v8; // edi
  __int64 v9; // rcx
  __int64 v10; // r15
  unsigned int v11; // eax
  unsigned int *v12; // [rsp+20h] [rbp-40h]
  BOOL v13; // [rsp+30h] [rbp-30h]
  BOOL isDSSASupported; // [rsp+38h] [rbp-28h]
  unsigned __int8 v15[16]; // [rsp+50h] [rbp-10h] BYREF
  int v16; // [rsp+A0h] [rbp+40h] BYREF
  int v17; // [rsp+A8h] [rbp+48h] BYREF

  v3 = a2;
  v16 = 0;
  v17 = 1;
  if ( !(unsigned int)OOBEComplete(&v17) )
  {
    WwanLog::Error("CWwanUicc::runOobeDssaSlotSwitch", 0, L"check for OOBEComplete failed, assume completed");
    v17 = 1;
  }
  v4 = (unsigned int)RegExists(-2147483646, L"System\\Setup\\Status", L"AuditBoot")
    && (unsigned int)RegGetDword(-2147483646, L"System\\Setup\\Status")
    || (unsigned int)RegExists(-2147483646, L"System\\Setup\\Status\\AuditBootVolatile", 0);
  if ( (unsigned int)GetOsManufacturingMode(&v16) )
  {
    v5 = v16;
  }
  else
  {
    WwanLog::Error("CWwanUicc::runOobeDssaSlotSwitch", 0, L"Failed to get Manufacturing mode, assume off.");
    v5 = 0;
    v16 = 0;
  }
  if ( v17 || v4 || v5 || (unsigned int)QueryRegValue() || (_BYTE)v3 )
  {
    isDSSASupported = CWwanUicc::isDSSASupported(this);
    v13 = QueryRegValue() != 0;
    WwanLog::Info(
      "CWwanUicc::runOobeDssaSlotSwitch",
      0,
      L" Slot Switch logic should not be executed. isOobeComplete:%d isAuditMode:%d isManufacturingMode:%d IsUpgradedInsta"
       "llation:%d isDSSASupported:%d isEsimProfileStateChange:%d",
      v17 != 0,
      v4,
      v16 != 0,
      v13,
      isDSSASupported,
      v3);
  }
  else
  {
    EmbeddedSlotIndex = CWwanUicc::getEmbeddedSlotIndex(v6);
    if ( CWwanUicc::isDSSASupported(this) )
    {
      v8 = EmbeddedSlotIndex;
      v9 = ((EmbeddedSlotIndex - 1) & 1) + 39LL;
      v10 = 3 * v9;
      if ( ((*((_DWORD *)this + 6 * v9) - 1) & 0xFFFFFFFD) != 0 )
        v8 = (EmbeddedSlotIndex - 1) & 1;
      *(_DWORD *)v15 = v8;
      if ( v8 != *((_DWORD *)this + 203) && CWwanUicc::UiccSlotRemap(this, 4u, v15, 0, v12) )
        WwanLog::Error("CWwanUicc::runOobeDssaSlotSwitch", 0, L"UiccSlotRemap failed");
      LODWORD(v12) = (EmbeddedSlotIndex - 1) & 1;
      WwanLog::Info(
        "CWwanUicc::runOobeDssaSlotSwitch",
        0,
        L" Embedded slot: %d. Physical slot: %d. Physical slot state: %d. Previous slot in use: %d. Slot to be selected: %d",
        EmbeddedSlotIndex,
        v12,
        *((_DWORD *)this + 2 * v10),
        *((_DWORD *)this + 203),
        v8);
    }
    v11 = RtlPublishWnfStateData(WNF_WWAN_OOBE_DISCOVERY_TASK_TRIGGER, 0, 0, 0, 0);
    if ( v11 )
      WwanLog::Error(
        "CWwanUicc::runOobeDssaSlotSwitch",
        0,
        L"failed to publish WNF WNF_WWAN_OOBE_DISCOVERY_TASK_TRIGGER, status = 0x%x",
        v11);
    else
      WwanLog::Info("CWwanUicc::runOobeDssaSlotSwitch", 0, L" published WNF WNF_WWAN_OOBE_DISCOVERY_TASK_TRIGGER");
  }
}

```

## disassembly

```asm
0x1800708dc  mov     [rsp-28h+arg_0], rbx
0x1800708e1  mov     [rsp-28h+arg_8], rsi
0x1800708e6  push    rbp
0x1800708e7  push    rdi
0x1800708e8  push    r13
0x1800708ea  push    r14
0x1800708ec  push    r15
0x1800708ee  mov     rbp, rsp
0x1800708f1  sub     rsp, 60h
0x1800708f5  mov     rbx, rcx
0x1800708f8  movzx   edi, dl
0x1800708fb  mov     r14d, 1
0x180070901  mov     [rbp+arg_10], 0
0x180070908  lea     rcx, [rbp+arg_18]
0x18007090c  mov     [rbp+arg_18], r14d
0x180070910  call    cs:__imp_OOBEComplete
0x180070916  lea     r13, aCwwanuiccRunoo; "CWwanUicc::runOobeDssaSlotSwitch"
0x18007091d  test    eax, eax
0x18007091f  jnz     short loc_180070936
0x180070921  lea     r8, aCheckForOobeco; "check for OOBEComplete failed, assume c"...
0x180070928  xor     edx, edx; struct _GUID *
0x18007092a  mov     rcx, r13; char *
0x18007092d  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180070932  mov     [rbp+arg_18], r14d
0x180070936  mov     rsi, 0FFFFFFFF80000002h
0x18007093d  lea     r8, aAuditboot; "AuditBoot"
0x180070944  mov     rcx, rsi
0x180070947  lea     rdx, aSystemSetupSta; "System\\Setup\\Status"
0x18007094e  call    RegExists
0x180070953  test    eax, eax
0x180070955  jz      short loc_18007096A
0x180070957  lea     rdx, aSystemSetupSta; "System\\Setup\\Status"
0x18007095e  mov     rcx, rsi
0x180070961  call    RegGetDword
0x180070966  test    eax, eax
0x180070968  jnz     short loc_180070980
0x18007096a  xor     r8d, r8d
0x18007096d  lea     rdx, aSystemSetupSta_0; "System\\Setup\\Status\\AuditBootVolatil"...
0x180070974  mov     rcx, rsi
0x180070977  call    RegExists
0x18007097c  test    eax, eax
0x18007097e  jz      short loc_180070985
0x180070980  mov     esi, r14d
0x180070983  jmp     short loc_180070987
0x180070985  xor     esi, esi
0x180070987  lea     rcx, [rbp+arg_10]
0x18007098b  call    cs:__imp_GetOsManufacturingMode
0x180070991  test    eax, eax
0x180070993  jnz     short loc_1800709AD
0x180070995  lea     r8, aFailedToGetMan; "Failed to get Manufacturing mode, assum"...
0x18007099c  xor     edx, edx; struct _GUID *
0x18007099e  mov     rcx, r13; char *
0x1800709a1  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800709a6  xor     eax, eax
0x1800709a8  mov     [rbp+arg_10], eax
0x1800709ab  jmp     short loc_1800709B0
0x1800709ad  mov     eax, [rbp+arg_10]
0x1800709b0  cmp     [rbp+arg_18], 0
0x1800709b4  jnz     loc_180070AC1
0x1800709ba  test    esi, esi
0x1800709bc  jnz     loc_180070AC1
0x1800709c2  test    eax, eax
0x1800709c4  jnz     loc_180070AC1
0x1800709ca  call    QueryRegValue
0x1800709cf  test    eax, eax
0x1800709d1  jnz     loc_180070AC1
0x1800709d7  test    dil, dil
0x1800709da  jnz     loc_180070AC1
0x1800709e0  call    ?getEmbeddedSlotIndex@CWwanUicc@@AEAAHXZ; CWwanUicc::getEmbeddedSlotIndex(void)
0x1800709e5  mov     rcx, rbx; this
0x1800709e8  mov     esi, eax
0x1800709ea  call    ?isDSSASupported@CWwanUicc@@IEAA_NXZ; CWwanUicc::isDSSASupported(void)
0x1800709ef  test    al, al
0x1800709f1  jz      loc_180070A7B
0x1800709f7  lea     ecx, [rsi-1]
0x1800709fa  mov     edi, esi
0x1800709fc  and     ecx, r14d
0x1800709ff  mov     r14d, ecx
0x180070a02  add     rcx, 27h ; '''
0x180070a06  lea     r15, [rcx+rcx*2]
0x180070a0a  mov     eax, [rbx+r15*8]
0x180070a0e  dec     eax
0x180070a10  test    eax, 0FFFFFFFDh
0x180070a15  cmovnz  edi, r14d
0x180070a19  mov     dword ptr [rbp+var_10], edi
0x180070a1c  cmp     edi, [rbx+32Ch]
0x180070a22  jz      short loc_180070A4C
0x180070a24  xor     r9d, r9d; unsigned int *
0x180070a27  lea     r8, [rbp+var_10]; unsigned __int8 *
0x180070a2b  mov     rcx, rbx; this
0x180070a2e  lea     edx, [r9+4]; unsigned int
0x180070a32  call    ?UiccSlotRemap@CWwanUicc@@QEAAKKPEBEPEAK1@Z; CWwanUicc::UiccSlotRemap(ulong,uchar const *,ulong *,ulong *)
0x180070a37  test    eax, eax
0x180070a39  jz      short loc_180070A4C
0x180070a3b  lea     r8, aUiccslotremapF_0; "UiccSlotRemap failed"
0x180070a42  xor     edx, edx; struct _GUID *
0x180070a44  mov     rcx, r13; char *
0x180070a47  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180070a4c  mov     eax, [rbx+32Ch]
0x180070a52  lea     r8, aEmbeddedSlotDP; " Embedded slot: %d. Physical slot: %d. "...
0x180070a59  mov     [rsp+60h+var_28], edi
0x180070a5d  mov     r9d, esi
0x180070a60  mov     [rsp+60h+var_30], eax
0x180070a64  xor     edx, edx; struct _GUID *
0x180070a66  mov     eax, [rbx+r15*8]
0x180070a6a  mov     rcx, r13; char *
0x180070a6d  mov     [rsp+60h+var_38], eax
0x180070a71  mov     dword ptr [rsp+60h+var_40], r14d
0x180070a76  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180070a7b  mov     rcx, cs:WNF_WWAN_OOBE_DISCOVERY_TASK_TRIGGER
0x180070a82  xor     r9d, r9d
0x180070a85  xor     r8d, r8d
0x180070a88  mov     [rsp+60h+var_40], 0
0x180070a91  xor     edx, edx
0x180070a93  call    cs:__imp_RtlPublishWnfStateData
0x180070a99  xor     edx, edx; struct _GUID *
0x180070a9b  mov     rcx, r13; char *
0x180070a9e  test    eax, eax
0x180070aa0  jz      short loc_180070AB3
0x180070aa2  mov     r9d, eax
0x180070aa5  lea     r8, aFailedToPublis_0; "failed to publish WNF WNF_WWAN_OOBE_DIS"...
0x180070aac  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180070ab1  jmp     short loc_180070B10
0x180070ab3  lea     r8, aPublishedWnfWn; " published WNF WNF_WWAN_OOBE_DISCOVERY_"...
0x180070aba  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180070abf  jmp     short loc_180070B10
0x180070ac1  mov     rcx, rbx; this
0x180070ac4  call    ?isDSSASupported@CWwanUicc@@IEAA_NXZ; CWwanUicc::isDSSASupported(void)
0x180070ac9  movzx   ebx, al
0x180070acc  call    QueryRegValue
0x180070ad1  xor     ecx, ecx
0x180070ad3  mov     [rsp+60h+var_20], edi
0x180070ad7  test    eax, eax
0x180070ad9  mov     [rsp+60h+var_28], ebx
0x180070add  lea     r8, aSlotSwitchLogi; " Slot Switch logic should not be execut"...
0x180070ae4  setnz   cl
0x180070ae7  xor     eax, eax
0x180070ae9  cmp     [rbp+arg_10], eax
0x180070aec  mov     [rsp+60h+var_30], ecx
0x180070af0  mov     rcx, r13; char *
0x180070af3  setnz   al
0x180070af6  xor     r9d, r9d
0x180070af9  cmp     [rbp+arg_18], r9d
0x180070afd  mov     [rsp+60h+var_38], eax
0x180070b01  setnz   r9b
0x180070b05  mov     dword ptr [rsp+60h+var_40], esi
0x180070b09  xor     edx, edx; struct _GUID *
0x180070b0b  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180070b10  lea     r11, [rsp+60h+var_s0]
0x180070b15  mov     rbx, [r11+30h]
0x180070b19  mov     rsi, [r11+38h]
0x180070b1d  mov     rsp, r11
0x180070b20  pop     r15
0x180070b22  pop     r14
0x180070b24  pop     r13
0x180070b26  pop     rdi
0x180070b27  pop     rbp
0x180070b28  retn
```
