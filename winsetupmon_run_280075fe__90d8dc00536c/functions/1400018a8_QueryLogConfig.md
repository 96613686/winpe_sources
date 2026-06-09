# QueryLogConfig

- ea: `0x1400018a8`
- end: `0x140001a09`
- name: `QueryLogConfig`
- size: `353`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140001674`
- `0x140001748`

## callees

- `0x1400018a8`
- `0x140003944`
- `0x14000f9e0`
- `0x14000fd40`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140001936`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001936`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140001946`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140001946`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140001969`

## string_xrefs

- `0x14000198a`: `Registry log configuration does not exit; skipping query`
- `0x1400019f2`: `Failed to query registry log configuration (0x%08X)`
- `0x1400018f7`: `RtlQueryRegistryValuesEx`
- `0x1400018fe`: `LogConfig`

## pseudocode

```c
__int64 __fastcall QueryLogConfig(_QWORD *a1)
{
  __int64 (__fastcall *SystemRoutineAddress)(__int64, const WCHAR *, _QWORD *); // rax
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rcx
  char v7; // [rsp+30h] [rbp-49h] BYREF
  int v8; // [rsp+31h] [rbp-48h]
  __int16 v9; // [rsp+35h] [rbp-44h]
  char v10; // [rsp+37h] [rbp-42h]
  __int128 v11; // [rsp+38h] [rbp-41h]
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-31h] BYREF
  _QWORD v13[14]; // [rsp+60h] [rbp-19h] BYREF

  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  memset(v13, 0, sizeof(v13));
  LODWORD(v13[1]) = 256;
  v13[0] = ConfigQueryRoutine;
  v7 = 1;
  v13[2] = L"LogConfig";
  LODWORD(v13[4]) = 3;
  v13[3] = &v7;
  v13[5] = 0;
  LODWORD(v13[6]) = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = (__int64 (__fastcall *)(__int64, const WCHAR *, _QWORD *))MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = (__int64 (__fastcall *)(__int64, const WCHAR *, _QWORD *))RtlQueryRegistryValues;
  v3 = SystemRoutineAddress(2, L"WinSetupMon", v13);
  v4 = v3;
  if ( v3 >= 0 )
    goto LABEL_6;
  if ( v3 == -1073741772 )
  {
    WriteLogMessage(1, L"Registry log configuration does not exit; skipping query");
    v4 = 0;
LABEL_6:
    v5 = 0;
    *a1 = v11;
    *(_QWORD *)&v11 = 0;
    goto LABEL_7;
  }
  WriteLogMessage(3, L"Failed to query registry log configuration (0x%08X)", (unsigned int)v3);
  v5 = v11;
LABEL_7:
  if ( *((_QWORD *)&v11 + 1) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v11 + 1) + 8LL))(*((_QWORD *)&v11 + 1));
    v5 = v11;
  }
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  return v4;
}

```

## disassembly

```asm
0x1400018a8  mov     [rsp-8+arg_0], rbx
0x1400018ad  mov     [rsp-8+arg_8], rdi
0x1400018b2  push    rbp
0x1400018b3  lea     rbp, [rsp-57h]
0x1400018b8  sub     rsp, 0D0h
0x1400018bf  xor     eax, eax
0x1400018c1  mov     rdi, rcx
0x1400018c4  xorps   xmm0, xmm0
0x1400018c7  mov     [rbp+57h+var_9F], eax
0x1400018ca  xor     edx, edx; Val
0x1400018cc  mov     [rbp+57h+var_9B], ax
0x1400018d0  lea     rcx, [rbp+57h+var_70]; void *
0x1400018d4  mov     [rbp+57h+var_99], al
0x1400018d7  lea     r8d, [rax+70h]; Size
0x1400018db  movdqu  [rbp+57h+var_98], xmm0
0x1400018e0  call    memset
0x1400018e5  lea     rax, ?ConfigQueryRoutine@@YAJPEAGKPEAXK11@Z; ConfigQueryRoutine(ushort *,ulong,void *,ulong,void *,void *)
0x1400018ec  mov     [rbp+57h+var_68], 100h
0x1400018f3  mov     [rbp+57h+var_70], rax
0x1400018f7  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x1400018fe  lea     rax, ValueName; "LogConfig"
0x140001905  mov     [rbp+57h+var_A0], 1
0x140001909  mov     [rbp+57h+var_60], rax
0x14000190d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140001911  lea     rax, [rbp+57h+var_A0]
0x140001915  mov     [rbp+57h+var_50], 3
0x14000191c  xorps   xmm0, xmm0
0x14000191f  mov     [rbp+57h+var_58], rax
0x140001923  mov     [rbp+57h+var_48], 0
0x14000192b  mov     [rbp+57h+var_40], 0
0x140001932  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140001936  call    cs:__imp_RtlInitUnicodeString
0x14000193d  nop     dword ptr [rax+rax+00h]
0x140001942  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x140001946  call    cs:__imp_MmGetSystemRoutineAddress
0x14000194d  nop     dword ptr [rax+rax+00h]
0x140001952  lea     r8, [rbp+57h+var_70]
0x140001956  mov     [rsp+0D0h+var_B0], 0
0x14000195f  test    rax, rax
0x140001962  lea     rdx, Path; "WinSetupMon"
0x140001969  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140001971  xor     r9d, r9d
0x140001974  lea     ecx, [r9+2]
0x140001978  call    _guard_dispatch_icall
0x14000197d  mov     ebx, eax
0x14000197f  test    eax, eax
0x140001981  jns     short loc_14000199D
0x140001983  cmp     eax, 0C0000034h
0x140001988  jnz     short loc_1400019EF
0x14000198a  lea     rdx, aRegistryLogCon; "Registry log configuration does not exi"...
0x140001991  mov     ecx, 1
0x140001996  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x14000199b  xor     ebx, ebx
0x14000199d  mov     rax, qword ptr [rbp+57h+var_98]
0x1400019a1  xor     ecx, ecx
0x1400019a3  mov     [rdi], rax
0x1400019a6  mov     qword ptr [rbp+57h+var_98], rcx
0x1400019aa  mov     rdx, qword ptr [rbp+57h+var_98+8]
0x1400019ae  test    rdx, rdx
0x1400019b1  jz      short loc_1400019C6
0x1400019b3  mov     rax, [rdx]
0x1400019b6  mov     rcx, rdx
0x1400019b9  mov     rax, [rax+8]
0x1400019bd  call    _guard_dispatch_icall
0x1400019c2  mov     rcx, qword ptr [rbp+57h+var_98]
0x1400019c6  test    rcx, rcx
0x1400019c9  jz      short loc_1400019D7
0x1400019cb  mov     rax, [rcx]
0x1400019ce  mov     rax, [rax+8]
0x1400019d2  call    _guard_dispatch_icall
0x1400019d7  lea     r11, [rsp+0D0h+var_s0]
0x1400019df  mov     eax, ebx
0x1400019e1  mov     rbx, [r11+10h]
0x1400019e5  mov     rdi, [r11+18h]
0x1400019e9  mov     rsp, r11
0x1400019ec  pop     rbp
0x1400019ed  retn
0x1400019ef  mov     r8d, eax
0x1400019f2  lea     rdx, aFailedToQueryR; "Failed to query registry log configurat"...
0x1400019f9  mov     ecx, 3
0x1400019fe  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140001a03  mov     rcx, qword ptr [rbp+57h+var_98]
0x140001a07  jmp     short loc_1400019AA
```
