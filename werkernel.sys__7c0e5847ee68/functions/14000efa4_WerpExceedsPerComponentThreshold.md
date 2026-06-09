# WerpExceedsPerComponentThreshold

- ea: `0x14000efa4`
- end: `0x14000f13b`
- name: `WerpExceedsPerComponentThreshold`
- size: `407`
- prototype: `char __fastcall(PCWSTR SourceString, signed __int64, unsigned __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000f1f8`

## callees

- `0x14000efa4`
- `0x14000f6d8`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000effb`
- `ntoskrnl!DbgPrintEx` at `0x14000f09e`
- `ntoskrnl!DbgPrintEx` at `0x14000f0fc`
- `ntoskrnl!DbgPrintEx` at `0x14000f113`
- `ntoskrnl!DbgPrintEx` at `0x14000effb`
- `ntoskrnl!DbgPrintEx` at `0x14000f09e`
- `ntoskrnl!DbgPrintEx` at `0x14000f0fc`
- `ntoskrnl!DbgPrintEx` at `0x14000f113`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000f041`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000f041`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f00e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f02a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f00e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f02a`

## string_xrefs

- `0x14000eff1`: `WERKERNELHOST: WerpExceedsPerComponentThreshold: Invalid param OverrideSystemPolicy\n`
- `0x14000f088`: `WERKERNELHOST: Component %ws: OverridePolicy enabled. New threshold time %lli\n`
- `0x14000f0f2`: `WERKERNELHOST: Component %ws: Threshold time is not met. Threshold time %lli, Current time %lli\n`
- `0x14000f10a`: `WERKERNELHOST: Component %ws: Threshold time is met. Threshold time %lli, Current time %lli\n`

## pseudocode

```c
char __fastcall WerpExceedsPerComponentThreshold(
        PCWSTR SourceString,
        signed __int64 a2,
        unsigned __int64 a3,
        _BYTE *a4)
{
  unsigned __int64 v4; // r14
  PCWSTR i; // rsi
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // r14
  __int64 v13; // [rsp+30h] [rbp-30h] BYREF
  UNICODE_STRING String2; // [rsp+38h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF
  char v16; // [rsp+A8h] [rbp+48h] BYREF

  v4 = 0;
  v16 = 0;
  v13 = 0;
  DestinationString = 0;
  String2 = 0;
  if ( a4 )
    *a4 = 0;
  else
    DbgPrintEx(5u, 1u, "WERKERNELHOST: WerpExceedsPerComponentThreshold: Invalid param OverrideSystemPolicy\n");
  RtlInitUnicodeString(&DestinationString, SourceString);
  for ( i = ::SourceString; i; i = (PCWSTR)*((_QWORD *)i + 5) )
  {
    RtlInitUnicodeString(&String2, i);
    if ( RtlEqualUnicodeString(&DestinationString, &String2, 0) )
    {
      v4 = *((_QWORD *)i + 4);
      break;
    }
  }
  WerpQueryComponentOverridePolicy(SourceString, &v16, &v13);
  if ( v16 )
  {
    if ( a4 )
      *a4 = 1;
    a3 = v13;
    DbgPrintEx(
      5u,
      3u,
      "WERKERNELHOST: Component %ws: OverridePolicy enabled. New threshold time %lli\n",
      SourceString,
      v13);
  }
  if ( v4 )
  {
    v10 = v4 + a3;
    v11 = v4 >> 63;
    if ( (_DWORD)v11 == a3 >> 63 && (_DWORD)v11 != v10 > 0x7FFFFFFFFFFFFFFFLL )
      return 1;
    if ( (__int64)v10 > a2 )
    {
      DbgPrintEx(
        5u,
        1u,
        "WERKERNELHOST: Component %ws: Threshold time is not met. Threshold time %lli, Current time %lli\n",
        SourceString,
        v10,
        a2);
      return 1;
    }
    DbgPrintEx(
      5u,
      3u,
      "WERKERNELHOST: Component %ws: Threshold time is met. Threshold time %lli, Current time %lli\n",
      SourceString,
      v10,
      a2);
  }
  return 0;
}

```

## disassembly

```asm
0x14000efa4  mov     [rsp-28h+arg_0], rbx
0x14000efa9  mov     [rsp-28h+arg_8], rsi
0x14000efae  push    rbp
0x14000efaf  push    rdi
0x14000efb0  push    r12
0x14000efb2  push    r14
0x14000efb4  push    r15
0x14000efb6  mov     rbp, rsp
0x14000efb9  sub     rsp, 60h
0x14000efbd  xor     r14d, r14d
0x14000efc0  xorps   xmm0, xmm0
0x14000efc3  mov     [rbp+arg_18], r14b
0x14000efc7  xorps   xmm1, xmm1
0x14000efca  mov     [rbp+var_30], r14
0x14000efce  mov     r15, r9
0x14000efd1  mov     rbx, r8
0x14000efd4  mov     rdi, rdx
0x14000efd7  mov     r12, rcx
0x14000efda  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000efde  movups  xmmword ptr [rbp+String2.Length], xmm1
0x14000efe2  test    r9, r9
0x14000efe5  jz      short loc_14000EFEC
0x14000efe7  mov     [r9], r14b
0x14000efea  jmp     short loc_14000F007
0x14000efec  mov     edx, 1; Level
0x14000eff1  lea     r8, aWerkernelhostW_44; "WERKERNELHOST: WerpExceedsPerComponentT"...
0x14000eff8  lea     ecx, [rdx+4]; ComponentId
0x14000effb  call    cs:__imp_DbgPrintEx
0x14000f002  nop     dword ptr [rax+rax+00h]
0x14000f007  mov     rdx, r12; SourceString
0x14000f00a  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000f00e  call    cs:__imp_RtlInitUnicodeString
0x14000f015  nop     dword ptr [rax+rax+00h]
0x14000f01a  mov     rsi, cs:SourceString
0x14000f021  jmp     short loc_14000F055
0x14000f023  mov     rdx, rsi; SourceString
0x14000f026  lea     rcx, [rbp+String2]; DestinationString
0x14000f02a  call    cs:__imp_RtlInitUnicodeString
0x14000f031  nop     dword ptr [rax+rax+00h]
0x14000f036  xor     r8d, r8d; CaseInSensitive
0x14000f039  lea     rdx, [rbp+String2]; String2
0x14000f03d  lea     rcx, [rbp+DestinationString]; String1
0x14000f041  call    cs:__imp_RtlEqualUnicodeString
0x14000f048  nop     dword ptr [rax+rax+00h]
0x14000f04d  test    al, al
0x14000f04f  jnz     short loc_14000F05C
0x14000f051  mov     rsi, [rsi+28h]
0x14000f055  test    rsi, rsi
0x14000f058  jnz     short loc_14000F023
0x14000f05a  jmp     short loc_14000F060
0x14000f05c  mov     r14, [rsi+20h]
0x14000f060  lea     r8, [rbp+var_30]
0x14000f064  mov     rcx, r12
0x14000f067  lea     rdx, [rbp+arg_18]
0x14000f06b  call    WerpQueryComponentOverridePolicy
0x14000f070  cmp     [rbp+arg_18], 0
0x14000f074  mov     esi, 3
0x14000f079  jz      short loc_14000F0AA
0x14000f07b  test    r15, r15
0x14000f07e  jz      short loc_14000F084
0x14000f080  mov     byte ptr [r15], 1
0x14000f084  mov     rbx, [rbp+var_30]
0x14000f088  lea     r8, aWerkernelhostC_5; "WERKERNELHOST: Component %ws: OverrideP"...
0x14000f08f  mov     r9, r12
0x14000f092  mov     [rsp+60h+var_40], rbx
0x14000f097  mov     edx, esi; Level
0x14000f099  mov     ecx, 5; ComponentId
0x14000f09e  call    cs:__imp_DbgPrintEx
0x14000f0a5  nop     dword ptr [rax+rax+00h]
0x14000f0aa  test    r14, r14
0x14000f0ad  jz      short loc_14000F11F
0x14000f0af  lea     rdx, [r14+rbx]
0x14000f0b3  shr     r14, 3Fh
0x14000f0b7  shr     rbx, 3Fh
0x14000f0bb  cmp     r14d, ebx
0x14000f0be  jnz     short loc_14000F0DB
0x14000f0c0  xor     ecx, ecx
0x14000f0c2  mov     r8, 7FFFFFFFFFFFFFFFh
0x14000f0cc  cmp     rdx, r8
0x14000f0cf  setnbe  cl
0x14000f0d2  cmp     r14d, ecx
0x14000f0d5  jz      short loc_14000F0DB
0x14000f0d7  mov     al, 1
0x14000f0d9  jmp     short loc_14000F121
0x14000f0db  mov     [rsp+60h+var_38], rdi
0x14000f0e0  mov     r9, r12
0x14000f0e3  mov     [rsp+60h+var_40], rdx
0x14000f0e8  mov     ecx, 5; ComponentId
0x14000f0ed  cmp     rdx, rdi
0x14000f0f0  jle     short loc_14000F10A
0x14000f0f2  lea     r8, aWerkernelhostC_0; "WERKERNELHOST: Component %ws: Threshold"...
0x14000f0f9  lea     edx, [rcx-4]; Level
0x14000f0fc  call    cs:__imp_DbgPrintEx
0x14000f103  nop     dword ptr [rax+rax+00h]
0x14000f108  jmp     short loc_14000F0D7
0x14000f10a  lea     r8, aWerkernelhostC_1; "WERKERNELHOST: Component %ws: Threshold"...
0x14000f111  mov     edx, esi; Level
0x14000f113  call    cs:__imp_DbgPrintEx
0x14000f11a  nop     dword ptr [rax+rax+00h]
0x14000f11f  xor     al, al
0x14000f121  lea     r11, [rsp+60h+var_s0]
0x14000f126  mov     rbx, [r11+30h]
0x14000f12a  mov     rsi, [r11+38h]
0x14000f12e  mov     rsp, r11
0x14000f131  pop     r15
0x14000f133  pop     r14
0x14000f135  pop     r12
0x14000f137  pop     rdi
0x14000f138  pop     rbp
0x14000f139  retn
```
