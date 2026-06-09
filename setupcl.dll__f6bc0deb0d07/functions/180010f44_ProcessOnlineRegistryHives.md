# ProcessOnlineRegistryHives

- ea: `0x180010f44`
- end: `0x1800111b3`
- name: `ProcessOnlineRegistryHives`
- size: `623`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800117e4`

## callees

- `0x180005a20`
- `0x18000a524`
- `0x18000a69c`
- `0x18000ac28`
- `0x180010f44`

## string_xrefs

- `0x180010ffc`: `SECURITY`
- `0x180011087`: `Marking event [&SclEvent_ProcessSystemRegistry_Start]`
- `0x180011186`: `Marking event [&SclEvent_ProcessSystemRegistry_Stop]`
- `0x180010f5d`: `\REGISTRY\USER\.DEFAULT`
- `0x180010fa5`: `\REGISTRY\MACHINE\SAM`
- `0x180010fc1`: `\REGISTRY\MACHINE\SAM\SAM`
- `0x180010ff1`: `\REGISTRY\MACHINE\SECURITY`
- `0x180011021`: `\REGISTRY\MACHINE\SOFTWARE`
- `0x180011051`: `\REGISTRY\MACHINE\SYSTEM`
- `0x1800110a1`: `ProcessOnlineRegistryHives`
- `0x180011136`: `ProcessOnlineRegistryHives`
- `0x18001116d`: `ProcessOnlineRegistryHives`

## pseudocode

```c
__int64 __fastcall ProcessOnlineRegistryHives(__int64 a1, __int64 *a2)
{
  unsigned int v2; // edi
  int v4; // r14d
  _QWORD *v5; // rax
  __int64 v6; // r12
  __int64 v7; // rbx
  const wchar_t *v8; // r13
  _DWORD v10[2]; // [rsp+40h] [rbp-89h]
  const wchar_t *v11; // [rsp+48h] [rbp-81h]
  const WCHAR *v12; // [rsp+50h] [rbp-79h]
  __int64 v13; // [rsp+58h] [rbp-71h]
  int v14; // [rsp+60h] [rbp-69h]
  const wchar_t *v15; // [rsp+68h] [rbp-61h]
  const WCHAR *v16; // [rsp+70h] [rbp-59h]
  __int64 v17; // [rsp+78h] [rbp-51h]
  int v18; // [rsp+80h] [rbp-49h]
  const wchar_t *v19; // [rsp+88h] [rbp-41h]
  const WCHAR *v20; // [rsp+90h] [rbp-39h]
  __int64 v21; // [rsp+98h] [rbp-31h]
  int v22; // [rsp+A0h] [rbp-29h]
  const wchar_t *v23; // [rsp+A8h] [rbp-21h]
  const WCHAR *v24; // [rsp+B0h] [rbp-19h]
  __int64 v25; // [rsp+B8h] [rbp-11h]
  int v26; // [rsp+C0h] [rbp-9h]
  const wchar_t *v27; // [rsp+C8h] [rbp-1h]
  const WCHAR *v28; // [rsp+D0h] [rbp+7h]
  __int64 v29; // [rsp+D8h] [rbp+Fh]

  v10[0] = 256;
  v2 = 0;
  v11 = L"\\REGISTRY\\USER\\.DEFAULT";
  v14 = 512;
  v12 = L"DEFAULT";
  v4 = 0;
  if ( a2 )
  {
    v13 = *a2;
    v5 = (_QWORD *)a2[1];
    if ( v5 && *v5 )
    {
      v15 = L"\\REGISTRY\\MACHINE\\SAM";
      v16 = L"SAM";
      goto LABEL_7;
    }
  }
  else
  {
    v13 = 0;
  }
  v15 = L"\\REGISTRY\\MACHINE\\SAM\\SAM";
  v16 = L"SAM";
  if ( !a2 )
  {
    v17 = 0;
    goto LABEL_9;
  }
LABEL_7:
  v17 = a2[1];
LABEL_9:
  v18 = 1024;
  v19 = L"\\REGISTRY\\MACHINE\\SECURITY";
  v20 = L"SECURITY";
  if ( a2 )
    v21 = a2[2];
  else
    v21 = 0;
  v22 = 2048;
  v23 = L"\\REGISTRY\\MACHINE\\SOFTWARE";
  v24 = L"SOFTWARE";
  if ( a2 )
    v25 = a2[3];
  else
    v25 = 0;
  v26 = 4096;
  v27 = L"\\REGISTRY\\MACHINE\\SYSTEM";
  v28 = L"SYSTEM";
  if ( a2 )
    v29 = a2[4];
  else
    v29 = 0;
  v6 = a1 + 1152;
  v7 = a1 + 1152;
  if ( !a1 )
    v7 = 0;
  SclLogTimingEvent(v7, SclEvent_ProcessSystemRegistry_Start, "Marking event [&SclEvent_ProcessSystemRegistry_Start]");
  while ( v2 < 5 )
  {
    if ( (v10[8 * v2] & *(_DWORD *)(a1 + 8)) != 0 )
    {
      v8 = (&v11)[4 * v2];
      SclLogGenericMessage(v7, 1, (unsigned int)SclEvent_Generic_Info, 497, (__int64)"ProcessOnlineRegistryHives");
      SclEtwWriteString(v6, SclEvent_ProcessRegistryHive_Start, (&v12)[4 * v2]);
      v4 = SclRegProcessKey(a1, v8, *(&v13 + 4 * v2));
      SclEtwWriteString(v6, SclEvent_ProcessRegistryHive_Stop, (&v12)[4 * v2]);
      if ( v4 < 0 )
      {
        SclLogGenericMessage(v7, 3, (unsigned int)SclEvent_Generic_Error, 514, (__int64)"ProcessOnlineRegistryHives");
        break;
      }
    }
    ++v2;
  }
  SclLogTimingEvent(v7, SclEvent_ProcessSystemRegistry_Stop, "Marking event [&SclEvent_ProcessSystemRegistry_Stop]");
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180010f44  push    rbp
0x180010f46  push    rbx
0x180010f47  push    rsi
0x180010f48  push    rdi
0x180010f49  push    r12
0x180010f4b  push    r13
0x180010f4d  push    r14
0x180010f4f  push    r15
0x180010f51  lea     rbp, [rsp-1Fh]
0x180010f56  sub     rsp, 0E8h
0x180010f5d  lea     rax, aRegistryUserDe; "\\REGISTRY\\USER\\.DEFAULT"
0x180010f64  mov     [rsp+120h+var_E0], 100h
0x180010f6c  xor     edi, edi
0x180010f6e  mov     [rsp+120h+var_D8], rax
0x180010f73  mov     [rbp+57h+var_C0], 200h
0x180010f7a  lea     rax, aDefault_0; "DEFAULT"
0x180010f81  mov     [rbp+57h+var_D0], rax
0x180010f85  mov     r15, rcx
0x180010f88  mov     r14d, edi
0x180010f8b  test    rdx, rdx
0x180010f8e  jz      short loc_180010FBD
0x180010f90  mov     rax, [rdx]
0x180010f93  mov     [rbp+57h+var_C8], rax
0x180010f97  mov     rax, [rdx+8]
0x180010f9b  test    rax, rax
0x180010f9e  jz      short loc_180010FC1
0x180010fa0  cmp     [rax], rdi
0x180010fa3  jz      short loc_180010FC1
0x180010fa5  lea     rax, aRegistryMachin_4; "\\REGISTRY\\MACHINE\\SAM"
0x180010fac  mov     [rbp+57h+var_B8], rax
0x180010fb0  lea     rax, aSam; "SAM"
0x180010fb7  mov     [rbp+57h+var_B0], rax
0x180010fbb  jmp     short loc_180010FDC
0x180010fbd  mov     [rbp+57h+var_C8], rdi
0x180010fc1  lea     rax, aRegistryMachin_6; "\\REGISTRY\\MACHINE\\SAM\\SAM"
0x180010fc8  mov     [rbp+57h+var_B8], rax
0x180010fcc  lea     rax, aSam; "SAM"
0x180010fd3  mov     [rbp+57h+var_B0], rax
0x180010fd7  test    rdx, rdx
0x180010fda  jz      short loc_180010FE6
0x180010fdc  mov     rax, [rdx+8]
0x180010fe0  mov     [rbp+57h+var_A8], rax
0x180010fe4  jmp     short loc_180010FEA
0x180010fe6  mov     [rbp+57h+var_A8], rdi
0x180010fea  mov     [rbp+57h+var_A0], 400h
0x180010ff1  lea     rax, aRegistryMachin_9; "\\REGISTRY\\MACHINE\\SECURITY"
0x180010ff8  mov     [rbp+57h+var_98], rax
0x180010ffc  lea     rax, aSecurity; "SECURITY"
0x180011003  mov     [rbp+57h+var_90], rax
0x180011007  test    rdx, rdx
0x18001100a  jz      short loc_180011016
0x18001100c  mov     rax, [rdx+10h]
0x180011010  mov     [rbp+57h+var_88], rax
0x180011014  jmp     short loc_18001101A
0x180011016  mov     [rbp+57h+var_88], rdi
0x18001101a  mov     [rbp+57h+var_80], 800h
0x180011021  lea     rax, aRegistryMachin_10; "\\REGISTRY\\MACHINE\\SOFTWARE"
0x180011028  mov     [rbp+57h+var_78], rax
0x18001102c  lea     rax, aSoftware; "SOFTWARE"
0x180011033  mov     [rbp+57h+var_70], rax
0x180011037  test    rdx, rdx
0x18001103a  jz      short loc_180011046
0x18001103c  mov     rax, [rdx+18h]
0x180011040  mov     [rbp+57h+var_68], rax
0x180011044  jmp     short loc_18001104A
0x180011046  mov     [rbp+57h+var_68], rdi
0x18001104a  mov     [rbp+57h+var_60], 1000h
0x180011051  lea     rax, aRegistryMachin_5; "\\REGISTRY\\MACHINE\\SYSTEM"
0x180011058  mov     [rbp+57h+var_58], rax
0x18001105c  lea     rax, aSystem; "SYSTEM"
0x180011063  mov     [rbp+57h+var_50], rax
0x180011067  test    rdx, rdx
0x18001106a  jz      short loc_180011076
0x18001106c  mov     rax, [rdx+20h]
0x180011070  mov     [rbp+57h+var_48], rax
0x180011074  jmp     short loc_18001107A
0x180011076  mov     [rbp+57h+var_48], rdi
0x18001107a  lea     r12, [rcx+480h]
0x180011081  test    r15, r15
0x180011084  mov     rbx, r12
0x180011087  lea     r8, aMarkingEventSc_11; "Marking event [&SclEvent_ProcessSystemR"...
0x18001108e  cmovz   rbx, rdi
0x180011092  lea     rdx, SclEvent_ProcessSystemRegistry_Start
0x180011099  mov     rcx, rbx
0x18001109c  call    SclLogTimingEvent
0x1800110a1  lea     rcx, aProcessonliner; "ProcessOnlineRegistryHives"
0x1800110a8  cmp     edi, 5
0x1800110ab  jnb     loc_180011186
0x1800110b1  mov     esi, edi
0x1800110b3  shl     rsi, 5
0x1800110b7  mov     eax, [rsp+rsi+120h+var_E0]
0x1800110bb  test    [r15+8], eax
0x1800110bf  jz      short loc_18001113D
0x1800110c1  mov     r13, [rsp+rsi+120h+var_D8]
0x1800110c6  lea     rax, aProcessingSyst; "Processing system hive [%ws]..."
0x1800110cd  mov     [rsp+120h+var_F0], r13
0x1800110d2  lea     r8, SclEvent_Generic_Info
0x1800110d9  mov     [rsp+120h+var_F8], rax
0x1800110de  mov     r9d, 1F1h
0x1800110e4  mov     [rsp+120h+var_100], rcx
0x1800110e9  mov     edx, 1
0x1800110ee  mov     rcx, rbx
0x1800110f1  call    SclLogGenericMessage
0x1800110f6  mov     r8, [rbp+rsi+57h+var_D0]
0x1800110fb  lea     rdx, SclEvent_ProcessRegistryHive_Start
0x180011102  mov     rcx, r12
0x180011105  call    SclEtwWriteString
0x18001110a  mov     r8, [rbp+rsi+57h+var_C8]
0x18001110f  mov     rdx, r13
0x180011112  mov     rcx, r15
0x180011115  call    SclRegProcessKey
0x18001111a  mov     r8, [rbp+rsi+57h+var_D0]
0x18001111f  lea     rdx, SclEvent_ProcessRegistryHive_Stop
0x180011126  mov     rcx, r12
0x180011129  mov     r14d, eax
0x18001112c  call    SclEtwWriteString
0x180011131  test    r14d, r14d
0x180011134  js      short loc_18001114A
0x180011136  lea     rcx, aProcessonliner; "ProcessOnlineRegistryHives"
0x18001113d  inc     edi
0x18001113f  test    r14d, r14d
0x180011142  jns     loc_1800110A8
0x180011148  jmp     short loc_180011186
0x18001114a  mov     [rsp+120h+var_E8], r13
0x18001114f  lea     rax, aLxFailedToProc_1; "(%lx): Failed to process key [%ws]"
0x180011156  mov     dword ptr [rsp+120h+var_F0], r14d
0x18001115b  lea     r8, SclEvent_Generic_Error
0x180011162  mov     [rsp+120h+var_F8], rax
0x180011167  mov     r9d, 202h
0x18001116d  lea     rax, aProcessonliner; "ProcessOnlineRegistryHives"
0x180011174  mov     edx, 3
0x180011179  mov     rcx, rbx
0x18001117c  mov     [rsp+120h+var_100], rax
0x180011181  call    SclLogGenericMessage
0x180011186  lea     r8, aMarkingEventSc_2; "Marking event [&SclEvent_ProcessSystemR"...
0x18001118d  mov     rcx, rbx
0x180011190  lea     rdx, SclEvent_ProcessSystemRegistry_Stop
0x180011197  call    SclLogTimingEvent
0x18001119c  mov     eax, r14d
0x18001119f  add     rsp, 0E8h
0x1800111a6  pop     r15
0x1800111a8  pop     r14
0x1800111aa  pop     r13
0x1800111ac  pop     r12
0x1800111ae  pop     rdi
0x1800111af  pop     rsi
0x1800111b0  pop     rbx
0x1800111b1  pop     rbp
0x1800111b2  retn
```
