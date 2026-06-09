# IsTrackedPath(_UNICODE_STRING const *,uchar *)

- ea: `0x140006924`
- end: `0x140006a10`
- name: `?IsTrackedPath@@YAJPEBU_UNICODE_STRING@@PEAE@Z`
- size: `236`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x140001a94`

## callees

- `0x140003944`
- `0x140006924`
- `0x14000e1d0`

## import_xrefs

- `ntoskrnl!RtlNextUnicodePrefix` at `0x1400069bd`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x1400069bd`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400069da`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400069da`
- `ntoskrnl!ExAcquireFastMutex` at `0x140006988`
- `ntoskrnl!ExAcquireFastMutex` at `0x140006988`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400069f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400069f8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400069a4`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400069a4`

## string_xrefs

- `0x140006963`: `Failed to convert path [%wZ] to NT (0x%08X)`

## pseudocode

```c
__int64 __fastcall IsTrackedPath(const struct _UNICODE_STRING *a1, unsigned __int8 *a2)
{
  int NtPath; // eax
  int v5; // ebx
  unsigned __int8 v6; // di
  BOOLEAN i; // dl
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  UNICODE_STRING String2; // [rsp+20h] [rbp-48h] BYREF
  struct _UNICODE_STRING v11; // [rsp+30h] [rbp-38h] BYREF

  String2 = 0;
  v11 = 0;
  NtPath = GetNtPath(a1, &String2, &v11);
  v5 = 0;
  if ( NtPath != -1073741772 )
    v5 = NtPath;
  if ( v5 >= 0 )
  {
    v6 = 0;
    if ( String2.Length )
    {
      ExAcquireFastMutex(&stru_140019468);
      for ( i = 1; ; i = 0 )
      {
        UnicodePrefix = RtlNextUnicodePrefix(&g_TrackingInfo, i);
        if ( !UnicodePrefix )
          break;
        if ( RtlEqualUnicodeString((PCUNICODE_STRING)&UnicodePrefix[1], &String2, 1u) )
        {
          v6 = 1;
          break;
        }
      }
      ExReleaseFastMutex(&stru_140019468);
    }
    *a2 = v6;
  }
  else
  {
    WriteLogMessage(3, L"Failed to convert path [%wZ] to NT (0x%08X)", a1, (unsigned int)v5);
  }
  if ( String2.Buffer )
    ExFreePoolWithTag(String2.Buffer, 0x6E6D7377u);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140006924  mov     rax, rsp
0x140006927  push    rbx
0x140006928  push    rbp
0x140006929  push    rsi
0x14000692a  push    rdi
0x14000692b  sub     rsp, 48h
0x14000692f  mov     rsi, rdx
0x140006932  lea     r8, [rax-38h]; struct _UNICODE_STRING *
0x140006936  xorps   xmm0, xmm0
0x140006939  lea     rdx, [rax-48h]; DestinationString
0x14000693d  xorps   xmm1, xmm1
0x140006940  mov     rdi, rcx
0x140006943  movups  xmmword ptr [rax-48h], xmm0
0x140006947  movups  xmmword ptr [rax-38h], xmm1
0x14000694b  call    ?GetNtPath@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z; GetNtPath(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x140006950  xor     ebp, ebp
0x140006952  cmp     eax, 0C0000034h
0x140006957  mov     ebx, ebp
0x140006959  cmovnz  ebx, eax
0x14000695c  test    ebx, ebx
0x14000695e  jns     short loc_140006977
0x140006960  mov     r9d, ebx
0x140006963  lea     rdx, aFailedToConver; "Failed to convert path [%wZ] to NT (0x%"...
0x14000696a  mov     r8, rdi
0x14000696d  lea     ecx, [rbp+3]
0x140006970  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140006975  jmp     short loc_1400069E9
0x140006977  mov     dil, bpl
0x14000697a  cmp     [rsp+68h+String2.Length], bp
0x14000697f  jbe     short loc_1400069E6
0x140006981  lea     rcx, stru_140019468; FastMutex
0x140006988  call    cs:__imp_ExAcquireFastMutex
0x14000698f  nop     dword ptr [rax+rax+00h]
0x140006994  mov     dl, 1
0x140006996  jmp     short loc_1400069B6
0x140006998  lea     rcx, [rax+38h]; String1
0x14000699c  mov     r8b, 1; CaseInSensitive
0x14000699f  lea     rdx, [rsp+68h+String2]; String2
0x1400069a4  call    cs:__imp_RtlEqualUnicodeString
0x1400069ab  nop     dword ptr [rax+rax+00h]
0x1400069b0  test    al, al
0x1400069b2  jnz     short loc_1400069D0
0x1400069b4  xor     edx, edx; Restart
0x1400069b6  lea     rcx, ?g_TrackingInfo@@3U_TRACKED_PATHS_TABLE@@A; PrefixTable
0x1400069bd  call    cs:__imp_RtlNextUnicodePrefix
0x1400069c4  nop     dword ptr [rax+rax+00h]
0x1400069c9  test    rax, rax
0x1400069cc  jnz     short loc_140006998
0x1400069ce  jmp     short loc_1400069D3
0x1400069d0  mov     dil, 1
0x1400069d3  lea     rcx, stru_140019468; FastMutex
0x1400069da  call    cs:__imp_ExReleaseFastMutex
0x1400069e1  nop     dword ptr [rax+rax+00h]
0x1400069e6  mov     [rsi], dil
0x1400069e9  mov     rcx, [rsp+68h+String2.Buffer]; P
0x1400069ee  test    rcx, rcx
0x1400069f1  jz      short loc_140006A04
0x1400069f3  mov     edx, 6E6D7377h; Tag
0x1400069f8  call    cs:__imp_ExFreePoolWithTag
0x1400069ff  nop     dword ptr [rax+rax+00h]
0x140006a04  mov     eax, ebx
0x140006a06  add     rsp, 48h
0x140006a0a  pop     rdi
0x140006a0b  pop     rsi
0x140006a0c  pop     rbp
0x140006a0d  pop     rbx
0x140006a0e  retn
```
