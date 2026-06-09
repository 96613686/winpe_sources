# ResumeProtection(_UNICODE_STRING const *)

- ea: `0x1400071f4`
- end: `0x14000737b`
- name: `?ResumeProtection@@YAJPEBU_UNICODE_STRING@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x14001e524`

## callees

- `0x140003944`
- `0x1400071f4`
- `0x14000e1d0`

## import_xrefs

- `ntoskrnl!RtlNextUnicodePrefix` at `0x1400072a5`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x1400072a5`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x1400072ff`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x1400072ff`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400072c0`
- `ntoskrnl!ExReleaseFastMutex` at `0x140007312`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400072c0`
- `ntoskrnl!ExReleaseFastMutex` at `0x140007312`
- `ntoskrnl!ExAcquireFastMutex` at `0x140007270`
- `ntoskrnl!ExAcquireFastMutex` at `0x140007270`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400072db`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000732c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000734e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000736a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400072db`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000732c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000734e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000736a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000728c`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000728c`

## string_xrefs

- `0x140007227`: `Failed to convert path [%wZ] to NT (0x%08X)`

## pseudocode

```c
__int64 __fastcall ResumeProtection(const struct _UNICODE_STRING *a1)
{
  int NtPath; // eax
  unsigned int v3; // edi
  BOOLEAN i; // dl
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  struct _UNICODE_PREFIX_TABLE_ENTRY *v6; // rbx
  struct _RTL_SPLAY_LINKS *Parent; // rcx
  struct _UNICODE_PREFIX_TABLE_ENTRY *NextPrefixTree; // rcx
  UNICODE_STRING String2; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING v11; // [rsp+30h] [rbp-18h] BYREF

  String2 = 0;
  v11 = 0;
  NtPath = GetNtPath(a1, &String2, &v11);
  v3 = NtPath;
  if ( NtPath >= 0 )
  {
    if ( String2.Length >= 2u && String2.Buffer[((unsigned __int64)String2.Length >> 1) - 1] == 92 )
      String2.Length -= 2;
    ExAcquireFastMutex(&stru_140019468);
    for ( i = 1; ; i = 0 )
    {
      UnicodePrefix = RtlNextUnicodePrefix(&PrefixTable, i);
      v6 = UnicodePrefix;
      if ( !UnicodePrefix )
      {
        ExReleaseFastMutex(&stru_140019468);
        goto LABEL_11;
      }
      if ( RtlEqualUnicodeString((PCUNICODE_STRING)&UnicodePrefix[1], &String2, 1u) )
        break;
    }
    RtlRemoveUnicodePrefix(&PrefixTable, v6);
    ExReleaseFastMutex(&stru_140019468);
    Parent = v6[1].Links.Parent;
    if ( Parent )
    {
      ExFreePoolWithTag(Parent, 0x6E6D7377u);
      v6[1].Links.Parent = 0;
    }
    NextPrefixTree = v6[1].NextPrefixTree;
    if ( NextPrefixTree )
    {
      ExFreePoolWithTag(NextPrefixTree, 0x6E6D7377u);
      v6[1].NextPrefixTree = 0;
    }
    ExFreePoolWithTag(v6, 0x6E6D7377u);
  }
  else
  {
    WriteLogMessage(3, L"Failed to convert path [%wZ] to NT (0x%08X)", a1, (unsigned int)NtPath);
  }
LABEL_11:
  if ( String2.Buffer )
    ExFreePoolWithTag(String2.Buffer, 0x6E6D7377u);
  return v3;
}

```

## disassembly

```asm
0x1400071f4  mov     rax, rsp
0x1400071f7  mov     [rax+8], rbx
0x1400071fb  push    rdi
0x1400071fc  sub     rsp, 40h
0x140007200  xorps   xmm0, xmm0
0x140007203  lea     r8, [rax-18h]; struct _UNICODE_STRING *
0x140007207  xorps   xmm1, xmm1
0x14000720a  lea     rdx, [rax-28h]; DestinationString
0x14000720e  movups  xmmword ptr [rax-28h], xmm0
0x140007212  mov     rbx, rcx
0x140007215  movups  xmmword ptr [rax-18h], xmm1
0x140007219  call    ?GetNtPath@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z; GetNtPath(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x14000721e  mov     edi, eax
0x140007220  test    eax, eax
0x140007222  jns     short loc_140007240
0x140007224  mov     r9d, eax
0x140007227  lea     rdx, aFailedToConver; "Failed to convert path [%wZ] to NT (0x%"...
0x14000722e  mov     r8, rbx
0x140007231  mov     ecx, 3
0x140007236  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x14000723b  jmp     loc_1400072CC
0x140007240  movzx   edx, [rsp+48h+String2.Length]
0x140007245  cmp     edx, 2
0x140007248  jb      short loc_140007269
0x14000724a  mov     rax, [rsp+48h+String2.Buffer]
0x14000724f  mov     ecx, edx
0x140007251  shr     rcx, 1
0x140007254  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14000725a  jnz     short loc_140007269
0x14000725c  mov     eax, 0FFFEh
0x140007261  add     dx, ax
0x140007264  mov     [rsp+48h+String2.Length], dx
0x140007269  lea     rcx, stru_140019468; FastMutex
0x140007270  call    cs:__imp_ExAcquireFastMutex
0x140007277  nop     dword ptr [rax+rax+00h]
0x14000727c  mov     dl, 1
0x14000727e  jmp     short loc_14000729E
0x140007280  lea     rcx, [rbx+38h]; String1
0x140007284  mov     r8b, 1; CaseInSensitive
0x140007287  lea     rdx, [rsp+48h+String2]; String2
0x14000728c  call    cs:__imp_RtlEqualUnicodeString
0x140007293  nop     dword ptr [rax+rax+00h]
0x140007298  test    al, al
0x14000729a  jnz     short loc_1400072F5
0x14000729c  xor     edx, edx; Restart
0x14000729e  lea     rcx, PrefixTable; PrefixTable
0x1400072a5  call    cs:__imp_RtlNextUnicodePrefix
0x1400072ac  nop     dword ptr [rax+rax+00h]
0x1400072b1  mov     rbx, rax
0x1400072b4  test    rax, rax
0x1400072b7  jnz     short loc_140007280
0x1400072b9  lea     rcx, stru_140019468; FastMutex
0x1400072c0  call    cs:__imp_ExReleaseFastMutex
0x1400072c7  nop     dword ptr [rax+rax+00h]
0x1400072cc  mov     rcx, [rsp+48h+String2.Buffer]; P
0x1400072d1  test    rcx, rcx
0x1400072d4  jz      short loc_1400072E7
0x1400072d6  mov     edx, 6E6D7377h; Tag
0x1400072db  call    cs:__imp_ExFreePoolWithTag
0x1400072e2  nop     dword ptr [rax+rax+00h]
0x1400072e7  mov     rbx, [rsp+48h+arg_0]
0x1400072ec  mov     eax, edi
0x1400072ee  add     rsp, 40h
0x1400072f2  pop     rdi
0x1400072f3  retn
0x1400072f5  mov     rdx, rbx; PrefixTableEntry
0x1400072f8  lea     rcx, PrefixTable; PrefixTable
0x1400072ff  call    cs:__imp_RtlRemoveUnicodePrefix
0x140007306  nop     dword ptr [rax+rax+00h]
0x14000730b  lea     rcx, stru_140019468; FastMutex
0x140007312  call    cs:__imp_ExReleaseFastMutex
0x140007319  nop     dword ptr [rax+rax+00h]
0x14000731e  mov     rcx, [rbx+50h]; P
0x140007322  test    rcx, rcx
0x140007325  jz      short loc_140007340
0x140007327  mov     edx, 6E6D7377h; Tag
0x14000732c  call    cs:__imp_ExFreePoolWithTag
0x140007333  nop     dword ptr [rax+rax+00h]
0x140007338  mov     qword ptr [rbx+50h], 0
0x140007340  mov     rcx, [rbx+40h]; P
0x140007344  test    rcx, rcx
0x140007347  jz      short loc_140007362
0x140007349  mov     edx, 6E6D7377h; Tag
0x14000734e  call    cs:__imp_ExFreePoolWithTag
0x140007355  nop     dword ptr [rax+rax+00h]
0x14000735a  mov     qword ptr [rbx+40h], 0
0x140007362  mov     edx, 6E6D7377h; Tag
0x140007367  mov     rcx, rbx; P
0x14000736a  call    cs:__imp_ExFreePoolWithTag
0x140007371  nop     dword ptr [rax+rax+00h]
0x140007376  jmp     loc_1400072CC
```
