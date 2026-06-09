# MONITOR_MGR::_CreateBootPersistentMonitors(_DXGK_DISPLAY_SCENARIO_CONTEXT *)

- ea: `0x14018cb44`
- end: `0x14018cfd8`
- name: `?_CreateBootPersistentMonitors@MONITOR_MGR@@QEAAJPEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z`
- size: `1172`
- prototype: `__int64 __fastcall(MONITOR_MGR *__hidden this, struct _DXGK_DISPLAY_SCENARIO_CONTEXT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1402fad20`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x1400372f8`
- `0x1400a0bd0`
- `0x14018cb44`
- `0x14018d5a8`
- `0x1401e640c`
- `0x1402fadd0`
- `0x1402fb0b4`
- `0x14034755c`
- `0x140348f90`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14018cfa2`
- `ntoskrnl!ZwClose` at `0x14018cfa2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14018cdbb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14018cdcf`
- `ntoskrnl!RtlInitUnicodeString` at `0x14018cdbb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14018cdcf`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14018cde6`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14018cde6`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14018cc3a`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14018cce0`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14018cc3a`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14018cce0`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x14018cf60`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x14018cf60`
- `watchdog!WdLogSingleEntry2` at `0x14018cc5f`
- `watchdog!WdLogSingleEntry2` at `0x14018cca2`
- `watchdog!WdLogSingleEntry2` at `0x14018cd23`
- `watchdog!WdLogSingleEntry2` at `0x14018cc5f`
- `watchdog!WdLogSingleEntry2` at `0x14018cca2`
- `watchdog!WdLogSingleEntry2` at `0x14018cd23`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14018cb76`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14018ce72`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14018cb76`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14018ce72`
- `watchdog!WdLogSingleEntry0` at `0x14018cbc0`
- `watchdog!WdLogSingleEntry0` at `0x14018ccfd`
- `watchdog!WdLogSingleEntry0` at `0x14018cdfb`
- `watchdog!WdLogSingleEntry0` at `0x14018ce52`
- `watchdog!WdLogSingleEntry0` at `0x14018cf0a`
- `watchdog!WdLogSingleEntry0` at `0x14018cbc0`
- `watchdog!WdLogSingleEntry0` at `0x14018ccfd`
- `watchdog!WdLogSingleEntry0` at `0x14018cdfb`
- `watchdog!WdLogSingleEntry0` at `0x14018ce52`
- `watchdog!WdLogSingleEntry0` at `0x14018cf0a`
- `watchdog!WdLogSingleEntry1` at `0x14018cd76`
- `watchdog!WdLogSingleEntry1` at `0x14018ce32`
- `watchdog!WdLogSingleEntry1` at `0x14018cf76`
- `watchdog!WdLogSingleEntry1` at `0x14018cd76`
- `watchdog!WdLogSingleEntry1` at `0x14018ce32`
- `watchdog!WdLogSingleEntry1` at `0x14018cf76`

## pseudocode

```c
__int64 __fastcall MONITOR_MGR::_CreateBootPersistentMonitors(
        MONITOR_MGR *this,
        struct _DXGK_DISPLAY_SCENARIO_CONTEXT *a2)
{
  ULONG v3; // esi
  unsigned int *v4; // rdi
  unsigned int *v5; // rbx
  unsigned int *v6; // r12
  _DWORD *v7; // r15
  NTSTATUS v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // eax
  NTSTATUS v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // r14d
  int IsTargetForceable; // eax
  MONITOR_MGR *v15; // rcx
  __int64 result; // rax
  __int64 v17; // rax
  __int64 v18; // r14
  unsigned int *v19; // r8
  unsigned int *v20; // rdi
  struct DXGMONITOR *v21; // rdx
  int SimulatedMonitor; // esi
  char v23[8]; // [rsp+30h] [rbp-99h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-91h] BYREF
  ULONG ResultLength; // [rsp+40h] [rbp-89h] BYREF
  _QWORD v26[2]; // [rsp+48h] [rbp-81h] BYREF
  UNICODE_STRING String2; // [rsp+58h] [rbp-71h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-61h] BYREF
  _BYTE v29[16]; // [rsp+78h] [rbp-51h] BYREF
  char KeyValueInformation[12]; // [rsp+88h] [rbp-41h] BYREF
  unsigned int v31; // [rsp+94h] [rbp-35h]
  WCHAR SourceString[32]; // [rsp+A0h] [rbp-29h] BYREF

  v26[0] = a2;
  *(_QWORD *)(WdLogNewEntry5_WdTrace(this) + 24) = this;
  WdLogGlobalForLineNumber = 3691;
  KeyHandle = 0;
  if ( MONITOR_MGR::_OpenPersistencyRegistry(this, 0x20019u, &KeyHandle) >= 0 )
  {
    if ( !KeyHandle )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 3703;
    }
    v3 = -1;
    ResultLength = 0;
    v4 = 0;
    v5 = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          if ( !v4 )
          {
            v4 = (unsigned int *)operator new[](96, 1298626628, 256);
            if ( !v4 )
            {
              WdLogSingleEntry0(6);
              result = 3221225495LL;
              WdLogGlobalForLineNumber = 3754;
              return result;
            }
          }
          ++v3;
          v6 = v4 + 2;
          v4[2] = -1;
          v7 = v4 + 3;
          v8 = ZwEnumerateValueKey(KeyHandle, v3, KeyValueBasicInformation, v4 + 3, 0x4Eu, &ResultLength);
          if ( v8 == -2147483622 )
          {
            v17 = WdLogNewEntry5_WdTrace(v9);
            *(_QWORD *)(v17 + 24) = v3;
            *(_QWORD *)(v17 + 32) = this;
            WdLogGlobalForLineNumber = 3786;
            DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v4);
            if ( v5 )
            {
              v18 = v26[0];
              do
              {
                v19 = v5;
                v20 = v5;
                v5 = *(unsigned int **)v5;
                if ( v19[2] == -1 )
                {
                  if ( RtlDeleteRegistryValue(0x40000000u, (PCWSTR)KeyHandle, (PCWSTR)v19 + 12) < 0 )
                  {
                    WdLogSingleEntry1(2);
                    WdLogGlobalForLineNumber = 3997;
                  }
                }
                else
                {
                  MONITOR_REF_ACCESSOR::MONITOR_REF_ACCESSOR((MONITOR_REF_ACCESSOR *)v26, 0);
                  MONITOR_REF_ACCESSOR::MONITOR_REF_ACCESSOR((MONITOR_REF_ACCESSOR *)v29, v21);
                  SimulatedMonitor = MONITOR_MGR::_HandleCreateSimulatedMonitor(this, v20[2], 2, v29, v26, v18);
                  if ( SimulatedMonitor >= 0 && !v26[1] )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 3979;
                  }
                  MONITOR_MGR::_LogMonitorPresentEvent(this, 1073741825, v20[2], (unsigned int)SimulatedMonitor, 0);
                  MONITOR_REF_ACCESSOR::Release((MONITOR_REF_ACCESSOR *)v29);
                  MONITOR_REF_ACCESSOR::Release((MONITOR_REF_ACCESSOR *)v26);
                }
                DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v20);
              }
              while ( v5 );
            }
            ZwClose(KeyHandle);
            return 0;
          }
          if ( v8 >= 0 )
            break;
          WdLogSingleEntry2(3, v3);
          WdLogGlobalForLineNumber = 3802;
        }
        *((_WORD *)v7 + ((unsigned __int64)v4[5] >> 1) + 6) = 0;
        *(_QWORD *)v4 = v5;
        v5 = v4;
        v10 = v4[4];
        v4 = 0;
        if ( v10 == 4 )
          break;
        WdLogSingleEntry2(3, v3);
        WdLogGlobalForLineNumber = 3828;
      }
      v11 = ZwEnumerateValueKey(KeyHandle, v3, KeyValuePartialInformation, KeyValueInformation, 0x13u, &ResultLength);
      if ( v11 == -2147483622 )
        break;
      if ( v11 >= 0 )
      {
        v12 = *((_QWORD *)this + 3);
        v13 = v31;
        v23[0] = 0;
        IsTargetForceable = DmmIsTargetForceable(*(_QWORD *)(v12 + 16), v31, v23, 0);
        if ( IsTargetForceable < 0 )
        {
          if ( IsTargetForceable == -1071774971 )
          {
            WdLogSingleEntry1(3);
            WdLogGlobalForLineNumber = 3894;
          }
        }
        else if ( v23[0] )
        {
          if ( MONITOR_MGR::_PersistencyRegNameFromTargetID(v15, v13, SourceString) >= 0 )
          {
            DestinationString = 0;
            String2 = 0;
            RtlInitUnicodeString(&DestinationString, (PCWSTR)v7 + 6);
            RtlInitUnicodeString(&String2, SourceString);
            if ( RtlCompareUnicodeString(&DestinationString, &String2, 0) )
            {
              WdLogSingleEntry0(3);
              WdLogGlobalForLineNumber = 3934;
            }
            else
            {
              *v6 = v13;
            }
          }
        }
        else
        {
          WdLogSingleEntry1(3);
          WdLogGlobalForLineNumber = 3881;
        }
      }
      else
      {
LABEL_15:
        WdLogSingleEntry2(3, v3);
        WdLogGlobalForLineNumber = 3854;
      }
    }
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 3840;
    goto LABEL_15;
  }
  return 0;
}

```

## disassembly

```asm
0x14018cb44  mov     [rsp-8+arg_10], rbx
0x14018cb49  push    rbp
0x14018cb4a  push    rsi
0x14018cb4b  push    rdi
0x14018cb4c  push    r12
0x14018cb4e  push    r13
0x14018cb50  push    r14
0x14018cb52  push    r15
0x14018cb54  lea     rbp, [rsp-27h]
0x14018cb59  sub     rsp, 0F0h
0x14018cb60  mov     rax, cs:__security_cookie
0x14018cb67  xor     rax, rsp
0x14018cb6a  mov     [rbp+57h+var_40], rax
0x14018cb6e  mov     [rsp+120h+var_D8], rdx
0x14018cb73  mov     r13, rcx
0x14018cb76  call    cs:__imp_WdLogNewEntry5_WdTrace
0x14018cb7d  nop     dword ptr [rax+rax+00h]
0x14018cb82  lea     r8, [rsp+120h+KeyHandle]; void **
0x14018cb87  mov     edx, 20019h; unsigned int
0x14018cb8c  mov     rcx, r13; this
0x14018cb8f  mov     [rax+18h], r13
0x14018cb93  mov     cs:WdLogGlobalForLineNumber, 0E6Bh
0x14018cb9d  mov     [rsp+120h+KeyHandle], 0
0x14018cba6  call    ?_OpenPersistencyRegistry@MONITOR_MGR@@AEBAJKPEAPEAX@Z; MONITOR_MGR::_OpenPersistencyRegistry(ulong,void * *)
0x14018cbab  test    eax, eax
0x14018cbad  js      loc_14018CFAE
0x14018cbb3  cmp     [rsp+120h+KeyHandle], 0
0x14018cbb9  jnz     short loc_14018CBD6
0x14018cbbb  mov     ecx, 1
0x14018cbc0  call    cs:__imp_WdLogSingleEntry0
0x14018cbc7  nop     dword ptr [rax+rax+00h]
0x14018cbcc  mov     cs:WdLogGlobalForLineNumber, 0E77h
0x14018cbd6  or      esi, 0FFFFFFFFh
0x14018cbd9  mov     [rsp+120h+var_E0], 0
0x14018cbe1  xor     edi, edi
0x14018cbe3  xor     ebx, ebx
0x14018cbe5  test    rdi, rdi
0x14018cbe8  jnz     short loc_14018CC09
0x14018cbea  mov     edx, 4D677844h
0x14018cbef  lea     ecx, [rdi+60h]
0x14018cbf2  mov     r8d, 100h
0x14018cbf8  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14018cbfd  mov     rdi, rax
0x14018cc00  test    rax, rax
0x14018cc03  jz      loc_14018CE4D
0x14018cc09  lea     rax, [rsp+120h+var_E0]
0x14018cc0e  inc     esi
0x14018cc10  mov     [rsp+120h+ResultLength], rax; ResultLength
0x14018cc15  lea     r12, [rdi+8]
0x14018cc19  mov     dword ptr [r12], 0FFFFFFFFh
0x14018cc21  lea     r15, [rdi+0Ch]
0x14018cc25  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x14018cc2a  mov     r9, r15; KeyValueInformation
0x14018cc2d  xor     r8d, r8d; KeyValueInformationClass
0x14018cc30  mov     [rsp+120h+Length], 4Eh ; 'N'; Length
0x14018cc38  mov     edx, esi; Index
0x14018cc3a  call    cs:__imp_ZwEnumerateValueKey
0x14018cc41  nop     dword ptr [rax+rax+00h]
0x14018cc46  cmp     eax, 8000001Ah
0x14018cc4b  jz      loc_14018CE72
0x14018cc51  test    eax, eax
0x14018cc53  jns     short loc_14018CC7A
0x14018cc55  movsxd  r8, eax
0x14018cc58  mov     ecx, 3
0x14018cc5d  mov     edx, esi
0x14018cc5f  call    cs:__imp_WdLogSingleEntry2
0x14018cc66  nop     dword ptr [rax+rax+00h]
0x14018cc6b  mov     cs:WdLogGlobalForLineNumber, 0EDAh
0x14018cc75  jmp     loc_14018CBE5
0x14018cc7a  mov     ecx, [r15+8]
0x14018cc7e  xor     eax, eax
0x14018cc80  shr     rcx, 1
0x14018cc83  mov     [r15+rcx*2+0Ch], ax
0x14018cc89  mov     [rdi], rbx
0x14018cc8c  mov     rbx, rdi
0x14018cc8f  mov     eax, [r15+4]
0x14018cc93  xor     edi, edi
0x14018cc95  cmp     eax, 4
0x14018cc98  jz      short loc_14018CCBD
0x14018cc9a  mov     r8d, eax
0x14018cc9d  mov     edx, esi
0x14018cc9f  lea     ecx, [rdi+3]
0x14018cca2  call    cs:__imp_WdLogSingleEntry2
0x14018cca9  nop     dword ptr [rax+rax+00h]
0x14018ccae  mov     cs:WdLogGlobalForLineNumber, 0EF4h
0x14018ccb8  jmp     loc_14018CBE5
0x14018ccbd  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x14018ccc2  lea     rax, [rsp+120h+var_E0]
0x14018ccc7  mov     [rsp+120h+ResultLength], rax; ResultLength
0x14018cccc  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14018ccd0  mov     r8d, 2; KeyValueInformationClass
0x14018ccd6  mov     [rsp+120h+Length], 13h; Length
0x14018ccde  mov     edx, esi; Index
0x14018cce0  call    cs:__imp_ZwEnumerateValueKey
0x14018cce7  nop     dword ptr [rax+rax+00h]
0x14018ccec  movsxd  r14, eax
0x14018ccef  cmp     r14d, 8000001Ah
0x14018ccf6  jnz     short loc_14018CD15
0x14018ccf8  mov     ecx, 1
0x14018ccfd  call    cs:__imp_WdLogSingleEntry0
0x14018cd04  nop     dword ptr [rax+rax+00h]
0x14018cd09  mov     cs:WdLogGlobalForLineNumber, 0F00h
0x14018cd13  jmp     short loc_14018CD19
0x14018cd15  test    eax, eax
0x14018cd17  jns     short loc_14018CD3E
0x14018cd19  mov     r8, r14
0x14018cd1c  mov     edx, esi
0x14018cd1e  mov     ecx, 3
0x14018cd23  call    cs:__imp_WdLogSingleEntry2
0x14018cd2a  nop     dword ptr [rax+rax+00h]
0x14018cd2f  mov     cs:WdLogGlobalForLineNumber, 0F0Eh
0x14018cd39  jmp     loc_14018CBE5
0x14018cd3e  mov     rcx, [r13+18h]
0x14018cd42  lea     r8, [rsp+120h+var_F0]
0x14018cd47  mov     r14d, [rbp+57h+var_8C]
0x14018cd4b  xor     r9d, r9d
0x14018cd4e  mov     edx, r14d
0x14018cd51  mov     [rsp+120h+var_F0], dil
0x14018cd56  mov     rcx, [rcx+10h]
0x14018cd5a  call    ?DmmIsTargetForceable@@YAJQEAXIPEAEW4_DMM_VIDPN_MONITOR_TYPE@@@Z; DmmIsTargetForceable(void * const,uint,uchar *,_DMM_VIDPN_MONITOR_TYPE)
0x14018cd5f  test    eax, eax
0x14018cd61  js      loc_14018CE1F
0x14018cd67  cmp     [rsp+120h+var_F0], dil
0x14018cd6c  jnz     short loc_14018CD91
0x14018cd6e  mov     edx, r14d
0x14018cd71  mov     ecx, 3
0x14018cd76  call    cs:__imp_WdLogSingleEntry1
0x14018cd7d  nop     dword ptr [rax+rax+00h]
0x14018cd82  mov     cs:WdLogGlobalForLineNumber, 0F29h
0x14018cd8c  jmp     loc_14018CBE5
0x14018cd91  lea     r8, [rbp+57h+SourceString]; unsigned __int16 *
0x14018cd95  mov     edx, r14d; unsigned int
0x14018cd98  call    ?_PersistencyRegNameFromTargetID@MONITOR_MGR@@AEBAJIQEAG@Z; MONITOR_MGR::_PersistencyRegNameFromTargetID(uint,ushort * const)
0x14018cd9d  test    eax, eax
0x14018cd9f  js      loc_14018CBE5
0x14018cda5  xorps   xmm0, xmm0
0x14018cda8  lea     rdx, [r15+0Ch]; SourceString
0x14018cdac  xorps   xmm1, xmm1
0x14018cdaf  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14018cdb3  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14018cdb7  movups  xmmword ptr [rbp+57h+String2.Length], xmm1
0x14018cdbb  call    cs:__imp_RtlInitUnicodeString
0x14018cdc2  nop     dword ptr [rax+rax+00h]
0x14018cdc7  lea     rdx, [rbp+57h+SourceString]; SourceString
0x14018cdcb  lea     rcx, [rbp+57h+String2]; DestinationString
0x14018cdcf  call    cs:__imp_RtlInitUnicodeString
0x14018cdd6  nop     dword ptr [rax+rax+00h]
0x14018cddb  xor     r8d, r8d; CaseInSensitive
0x14018cdde  lea     rdx, [rbp+57h+String2]; String2
0x14018cde2  lea     rcx, [rbp+57h+DestinationString]; String1
0x14018cde6  call    cs:__imp_RtlCompareUnicodeString
0x14018cded  nop     dword ptr [rax+rax+00h]
0x14018cdf2  test    eax, eax
0x14018cdf4  jz      short loc_14018CE16
0x14018cdf6  mov     ecx, 3
0x14018cdfb  call    cs:__imp_WdLogSingleEntry0
0x14018ce02  nop     dword ptr [rax+rax+00h]
0x14018ce07  mov     cs:WdLogGlobalForLineNumber, 0F5Eh
0x14018ce11  jmp     loc_14018CBE5
0x14018ce16  mov     [r12], r14d
0x14018ce1a  jmp     loc_14018CBE5
0x14018ce1f  cmp     eax, 0C01E0305h
0x14018ce24  jnz     loc_14018CBE5
0x14018ce2a  mov     rdx, r14
0x14018ce2d  mov     ecx, 3
0x14018ce32  call    cs:__imp_WdLogSingleEntry1
0x14018ce39  nop     dword ptr [rax+rax+00h]
0x14018ce3e  mov     cs:WdLogGlobalForLineNumber, 0F36h
0x14018ce48  jmp     loc_14018CBE5
0x14018ce4d  mov     ecx, 6
0x14018ce52  call    cs:__imp_WdLogSingleEntry0
0x14018ce59  nop     dword ptr [rax+rax+00h]
0x14018ce5e  mov     eax, 0C0000017h
0x14018ce63  mov     cs:WdLogGlobalForLineNumber, 0EAAh
0x14018ce6d  jmp     loc_14018CFB0
0x14018ce72  call    cs:__imp_WdLogNewEntry5_WdTrace
0x14018ce79  nop     dword ptr [rax+rax+00h]
0x14018ce7e  mov     ecx, esi
0x14018ce80  mov     [rax+18h], rcx
0x14018ce84  mov     rcx, rdi; void *
0x14018ce87  mov     [rax+20h], r13
0x14018ce8b  mov     cs:WdLogGlobalForLineNumber, 0ECAh
0x14018ce95  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x14018ce9a  test    rbx, rbx
0x14018ce9d  jz      loc_14018CF9D
0x14018cea3  mov     r14, [rsp+120h+var_D8]
0x14018cea8  mov     r15d, 2
0x14018ceae  mov     r8, rbx
0x14018ceb1  mov     rdi, rbx
0x14018ceb4  mov     rbx, [rbx]
0x14018ceb7  cmp     dword ptr [r8+8], 0FFFFFFFFh
0x14018cebc  jz      loc_14018CF52
0x14018cec2  xor     edx, edx; struct DXGMONITOR *
0x14018cec4  lea     rcx, [rsp+120h+var_D8]; this
0x14018cec9  call    ??0MONITOR_REF_ACCESSOR@@QEAA@PEAVDXGMONITOR@@@Z; MONITOR_REF_ACCESSOR::MONITOR_REF_ACCESSOR(DXGMONITOR *)
0x14018cece  lea     rcx, [rbp+57h+var_A8]; this
0x14018ced2  call    ??0MONITOR_REF_ACCESSOR@@QEAA@PEAVDXGMONITOR@@@Z; MONITOR_REF_ACCESSOR::MONITOR_REF_ACCESSOR(DXGMONITOR *)
0x14018ced7  mov     edx, [rdi+8]
0x14018ceda  lea     rax, [rsp+120h+var_D8]
0x14018cedf  mov     [rsp+120h+ResultLength], r14
0x14018cee4  lea     r9, [rbp+57h+var_A8]
0x14018cee8  mov     r8d, r15d
0x14018ceeb  mov     qword ptr [rsp+120h+Length], rax
0x14018cef0  mov     rcx, r13
0x14018cef3  call    ?_HandleCreateSimulatedMonitor@MONITOR_MGR@@QEAAJIW4_DMM_VIDPN_MONITOR_TYPE@@AEBVMONITOR_REF_ACCESSOR@@AEAV3@PEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z; MONITOR_MGR::_HandleCreateSimulatedMonitor(uint,_DMM_VIDPN_MONITOR_TYPE,MONITOR_REF_ACCESSOR const &,MONITOR_REF_ACCESSOR &,_DXGK_DISPLAY_SCENARIO_CONTEXT *)
0x14018cef8  mov     esi, eax
0x14018cefa  test    eax, eax
0x14018cefc  js      short loc_14018CF20
0x14018cefe  cmp     [rbp+57h+var_D0], 0
0x14018cf03  jnz     short loc_14018CF20
0x14018cf05  mov     ecx, 1
0x14018cf0a  call    cs:__imp_WdLogSingleEntry0
0x14018cf11  nop     dword ptr [rax+rax+00h]
0x14018cf16  mov     cs:WdLogGlobalForLineNumber, 0F8Bh
0x14018cf20  mov     r8d, [rdi+8]
0x14018cf24  mov     r9d, esi
0x14018cf27  mov     edx, 40000001h
0x14018cf2c  mov     qword ptr [rsp+120h+Length], 0
0x14018cf35  mov     rcx, r13
0x14018cf38  call    ?_LogMonitorPresentEvent@MONITOR_MGR@@QEAAXW4_DMM_MONITOR_PRESENCE_EVENT_TYPE@@IJPEAU_DXGK_DIAG_MONITOR_MGR_EXTRA_INFO@@@Z; MONITOR_MGR::_LogMonitorPresentEvent(_DMM_MONITOR_PRESENCE_EVENT_TYPE,uint,long,_DXGK_DIAG_MONITOR_MGR_EXTRA_INFO *)
0x14018cf3d  lea     rcx, [rbp+57h+var_A8]; this
0x14018cf41  call    ?Release@MONITOR_REF_ACCESSOR@@QEAAXXZ; MONITOR_REF_ACCESSOR::Release(void)
0x14018cf46  lea     rcx, [rsp+120h+var_D8]; this
0x14018cf4b  call    ?Release@MONITOR_REF_ACCESSOR@@QEAAXXZ; MONITOR_REF_ACCESSOR::Release(void)
0x14018cf50  jmp     short loc_14018CF8C
0x14018cf52  mov     rdx, [rsp+120h+KeyHandle]; Path
0x14018cf57  add     r8, 18h; ValueName
0x14018cf5b  mov     ecx, 40000000h; RelativeTo
0x14018cf60  call    cs:__imp_RtlDeleteRegistryValue
0x14018cf67  nop     dword ptr [rax+rax+00h]
0x14018cf6c  test    eax, eax
0x14018cf6e  jns     short loc_14018CF8C
0x14018cf70  movsxd  rdx, eax
0x14018cf73  mov     ecx, r15d
0x14018cf76  call    cs:__imp_WdLogSingleEntry1
0x14018cf7d  nop     dword ptr [rax+rax+00h]
0x14018cf82  mov     cs:WdLogGlobalForLineNumber, 0F9Dh
0x14018cf8c  mov     rcx, rdi; void *
0x14018cf8f  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x14018cf94  test    rbx, rbx
0x14018cf97  jnz     loc_14018CEAE
0x14018cf9d  mov     rcx, [rsp+120h+KeyHandle]; Handle
0x14018cfa2  call    cs:__imp_ZwClose
0x14018cfa9  nop     dword ptr [rax+rax+00h]
0x14018cfae  xor     eax, eax
0x14018cfb0  mov     rcx, [rbp+57h+var_40]
0x14018cfb4  xor     rcx, rsp; StackCookie
0x14018cfb7  call    __security_check_cookie
0x14018cfbc  mov     rbx, [rsp+120h+arg_10]
0x14018cfc4  add     rsp, 0F0h
0x14018cfcb  pop     r15
0x14018cfcd  pop     r14
0x14018cfcf  pop     r13
0x14018cfd1  pop     r12
0x14018cfd3  pop     rdi
0x14018cfd4  pop     rsi
0x14018cfd5  pop     rbp
0x14018cfd6  retn
```
