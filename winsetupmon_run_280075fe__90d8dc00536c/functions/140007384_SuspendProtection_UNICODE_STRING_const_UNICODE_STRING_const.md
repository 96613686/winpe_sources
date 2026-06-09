# SuspendProtection(_UNICODE_STRING const *,_UNICODE_STRING const *)

- ea: `0x140007384`
- end: `0x14000765f`
- name: `?SuspendProtection@@YAJPEBU_UNICODE_STRING@@0@Z`
- size: `731`
- prototype: `int(const struct _UNICODE_STRING *, const struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x14001e630`

## callees

- `0x140003944`
- `0x140007384`
- `0x14000dd24`
- `0x14000e1d0`
- `0x14000fd40`

## import_xrefs

- `ntoskrnl!RtlNextUnicodePrefix` at `0x1400074ac`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x1400074ac`
- `ntoskrnl!RtlInsertUnicodePrefix` at `0x140007529`
- `ntoskrnl!RtlInsertUnicodePrefix` at `0x140007529`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000755a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000760d`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000755a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000760d`
- `ntoskrnl!ExAcquireFastMutex` at `0x140007474`
- `ntoskrnl!ExAcquireFastMutex` at `0x140007474`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000757b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000759b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400075b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007625`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007645`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000757b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000759b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400075b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007625`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007645`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400074ca`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400074ca`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140007417`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000748f`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140007417`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000748f`

## string_xrefs

- `0x1400073c9`: `Failed to convert path [%wZ] to NT (0x%08X)`
- `0x1400075c5`: `Path [%wZ] already suspended, cannot suspend again`
- `0x1400075ed`: `Failed to allocate memory for the suspended path entry`
- `0x14000753d`: `Failed to insert suspended path prefix entry`

## pseudocode

```c
__int64 __fastcall SuspendProtection(const struct _UNICODE_STRING *a1, const struct _UNICODE_STRING *a2)
{
  int NtPath; // eax
  int v5; // edi
  const struct _UNICODE_STRING *v6; // r8
  BOOLEAN i; // dl
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  char *PoolWithTag; // rax
  char *v10; // rsi
  char *v11; // rbx
  void *v12; // rcx
  void *v13; // rcx
  UNICODE_STRING String2; // [rsp+20h] [rbp-30h] BYREF
  PVOID P[2]; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING v17; // [rsp+40h] [rbp-10h] BYREF

  String2 = 0;
  v17 = 0;
  *(_OWORD *)P = 0;
  NtPath = GetNtPath(a1, &String2, &v17);
  v5 = NtPath;
  if ( NtPath < 0 )
  {
    v6 = a1;
LABEL_3:
    WriteLogMessage(
      3,
      L"Failed to convert path [%wZ] to NT (0x%08X)",
      v6,
      (unsigned int)NtPath,
      *(_QWORD *)&String2.Length);
    goto LABEL_32;
  }
  if ( String2.Length >= 2u && String2.Buffer[((unsigned __int64)String2.Length >> 1) - 1] == 92 )
    String2.Length -= 2;
  if ( a2 )
  {
    if ( RtlEqualUnicodeString(a2, &stru_1400123F0, 1u) )
    {
      v5 = Duplicate(&stru_1400123F0, (PUNICODE_STRING)P);
      if ( v5 < 0 )
      {
        WriteLogMessage(3, L"Failed to duplicate system process name");
        goto LABEL_32;
      }
    }
    else
    {
      NtPath = GetNtPath(a2, (PUNICODE_STRING)P, &v17);
      v5 = NtPath;
      if ( NtPath < 0 )
      {
        v6 = a2;
        goto LABEL_3;
      }
    }
  }
  ExAcquireFastMutex(&stru_140019468);
  for ( i = 1; ; i = 0 )
  {
    UnicodePrefix = RtlNextUnicodePrefix(&PrefixTable, i);
    if ( !UnicodePrefix )
      break;
    if ( RtlEqualUnicodeString((PCUNICODE_STRING)&UnicodePrefix[1], &String2, 1u) )
    {
      v11 = 0;
      v5 = -1073741771;
      WriteLogMessage(3, L"Path [%wZ] already suspended, cannot suspend again", a1);
      goto LABEL_22;
    }
  }
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1025, 0x58u, 0x6E6D7377u);
  v10 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
  {
    memset(PoolWithTag, 0, 0x58u);
    v11 = v10;
LABEL_20:
    *(UNICODE_STRING *)(v10 + 56) = String2;
    String2 = 0;
    *(_OWORD *)(v10 + 72) = *(_OWORD *)P;
    *(_OWORD *)P = 0;
    if ( RtlInsertUnicodePrefix(&PrefixTable, (PUNICODE_STRING)(v10 + 56), (PUNICODE_PREFIX_TABLE_ENTRY)v10) )
    {
      ExReleaseFastMutex(&stru_140019468);
      goto LABEL_32;
    }
    WriteLogMessage(3, L"Failed to insert suspended path prefix entry");
    v5 = -1073741616;
    goto LABEL_22;
  }
  v11 = PoolWithTag;
  if ( PoolWithTag )
    goto LABEL_20;
  WriteLogMessage(3, L"Failed to allocate memory for the suspended path entry");
  v5 = -1073741670;
LABEL_22:
  ExReleaseFastMutex(&stru_140019468);
  if ( v11 )
  {
    v12 = (void *)*((_QWORD *)v11 + 10);
    if ( v12 )
    {
      ExFreePoolWithTag(v12, 0x6E6D7377u);
      *((_QWORD *)v11 + 10) = 0;
    }
    v13 = (void *)*((_QWORD *)v11 + 8);
    if ( v13 )
    {
      ExFreePoolWithTag(v13, 0x6E6D7377u);
      *((_QWORD *)v11 + 8) = 0;
    }
    ExFreePoolWithTag(v11, 0x6E6D7377u);
  }
LABEL_32:
  if ( P[1] )
  {
    ExFreePoolWithTag(P[1], 0x6E6D7377u);
    P[1] = 0;
  }
  if ( String2.Buffer )
    ExFreePoolWithTag(String2.Buffer, 0x6E6D7377u);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140007384  push    rbp
0x140007386  push    rbx
0x140007387  push    rsi
0x140007388  push    rdi
0x140007389  push    r15
0x14000738b  mov     rbp, rsp
0x14000738e  sub     rsp, 50h
0x140007392  xorps   xmm0, xmm0
0x140007395  lea     r8, [rbp+var_10]; struct _UNICODE_STRING *
0x140007399  mov     rbx, rdx
0x14000739c  xorps   xmm1, xmm1
0x14000739f  lea     rdx, [rbp+String2]; DestinationString
0x1400073a3  mov     rsi, rcx
0x1400073a6  movups  xmmword ptr [rbp+String2.Length], xmm0
0x1400073aa  movups  xmmword ptr [rbp+var_10.Length], xmm1
0x1400073ae  movups  xmmword ptr [rbp+P], xmm0
0x1400073b2  call    ?GetNtPath@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z; GetNtPath(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x1400073b7  mov     edi, eax
0x1400073b9  mov     r15d, 6E6D7377h
0x1400073bf  test    eax, eax
0x1400073c1  jns     short loc_1400073DF
0x1400073c3  mov     r8, rsi
0x1400073c6  mov     r9d, eax
0x1400073c9  lea     rdx, aFailedToConver; "Failed to convert path [%wZ] to NT (0x%"...
0x1400073d0  mov     ecx, 3
0x1400073d5  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x1400073da  jmp     loc_140007619
0x1400073df  movzx   edx, [rbp+String2.Length]
0x1400073e3  cmp     edx, 2
0x1400073e6  jb      short loc_140007405
0x1400073e8  mov     rax, [rbp+String2.Buffer]
0x1400073ec  mov     ecx, edx
0x1400073ee  shr     rcx, 1
0x1400073f1  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1400073f7  jnz     short loc_140007405
0x1400073f9  mov     eax, 0FFFEh
0x1400073fe  add     dx, ax
0x140007401  mov     [rbp+String2.Length], dx
0x140007405  test    rbx, rbx
0x140007408  jz      short loc_14000746D
0x14000740a  mov     r8b, 1; CaseInSensitive
0x14000740d  lea     rdx, stru_1400123F0; String2
0x140007414  mov     rcx, rbx; String1
0x140007417  call    cs:__imp_RtlEqualUnicodeString
0x14000741e  nop     dword ptr [rax+rax+00h]
0x140007423  lea     rdx, [rbp+P]; DestinationString
0x140007427  test    al, al
0x140007429  jz      short loc_140007453
0x14000742b  lea     rcx, stru_1400123F0; SourceString
0x140007432  call    ?Duplicate@@YAJPEBU_UNICODE_STRING@@PEAU1@@Z; Duplicate(_UNICODE_STRING const *,_UNICODE_STRING *)
0x140007437  mov     edi, eax
0x140007439  test    eax, eax
0x14000743b  jns     short loc_14000746D
0x14000743d  lea     rdx, aFailedToDuplic_2; "Failed to duplicate system process name"
0x140007444  mov     ecx, 3
0x140007449  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x14000744e  jmp     loc_140007619
0x140007453  lea     r8, [rbp+var_10]; struct _UNICODE_STRING *
0x140007457  mov     rcx, rbx; String2
0x14000745a  call    ?GetNtPath@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z; GetNtPath(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x14000745f  mov     edi, eax
0x140007461  test    eax, eax
0x140007463  jns     short loc_14000746D
0x140007465  mov     r8, rbx
0x140007468  jmp     loc_1400073C6
0x14000746d  lea     rcx, stru_140019468; FastMutex
0x140007474  call    cs:__imp_ExAcquireFastMutex
0x14000747b  nop     dword ptr [rax+rax+00h]
0x140007480  mov     dl, 1
0x140007482  jmp     short loc_1400074A5
0x140007484  lea     rcx, [rax+38h]; String1
0x140007488  mov     r8b, 1; CaseInSensitive
0x14000748b  lea     rdx, [rbp+String2]; String2
0x14000748f  call    cs:__imp_RtlEqualUnicodeString
0x140007496  nop     dword ptr [rax+rax+00h]
0x14000749b  test    al, al
0x14000749d  jnz     loc_1400075C3
0x1400074a3  xor     edx, edx; Restart
0x1400074a5  lea     rcx, PrefixTable; PrefixTable
0x1400074ac  call    cs:__imp_RtlNextUnicodePrefix
0x1400074b3  nop     dword ptr [rax+rax+00h]
0x1400074b8  test    rax, rax
0x1400074bb  jnz     short loc_140007484
0x1400074bd  lea     ebx, [rax+58h]
0x1400074c0  mov     r8d, r15d; Tag
0x1400074c3  mov     edx, ebx; NumberOfBytes
0x1400074c5  mov     ecx, 401h; PoolType
0x1400074ca  call    cs:__imp_ExAllocatePoolWithTag
0x1400074d1  nop     dword ptr [rax+rax+00h]
0x1400074d6  cmp     cs:ExPoolZeroingNativelySupported, 0
0x1400074dd  mov     rsi, rax
0x1400074e0  jnz     loc_1400075E1
0x1400074e6  test    rax, rax
0x1400074e9  jz      loc_1400075E1
0x1400074ef  mov     r8d, ebx; Size
0x1400074f2  xor     edx, edx; Val
0x1400074f4  mov     rcx, rax; void *
0x1400074f7  call    memset
0x1400074fc  mov     rbx, rsi
0x1400074ff  movups  xmm0, xmmword ptr [rbp+String2.Length]
0x140007503  lea     rdx, [rsi+38h]; Prefix
0x140007507  mov     r8, rsi; PrefixTableEntry
0x14000750a  xorps   xmm1, xmm1
0x14000750d  lea     rcx, PrefixTable; PrefixTable
0x140007514  movdqu  xmmword ptr [rdx], xmm0
0x140007518  movups  xmm0, xmmword ptr [rbp+P]
0x14000751c  movups  xmmword ptr [rbp+String2.Length], xmm1
0x140007520  movdqu  xmmword ptr [rsi+48h], xmm0
0x140007525  movups  xmmword ptr [rbp+P], xmm1
0x140007529  call    cs:__imp_RtlInsertUnicodePrefix
0x140007530  nop     dword ptr [rax+rax+00h]
0x140007535  test    al, al
0x140007537  jnz     loc_140007606
0x14000753d  lea     rdx, aFailedToInsert; "Failed to insert suspended path prefix "...
0x140007544  mov     ecx, 3
0x140007549  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x14000754e  mov     edi, 0C00000D0h
0x140007553  lea     rcx, stru_140019468; FastMutex
0x14000755a  call    cs:__imp_ExReleaseFastMutex
0x140007561  nop     dword ptr [rax+rax+00h]
0x140007566  test    rbx, rbx
0x140007569  jz      loc_140007619
0x14000756f  mov     rcx, [rbx+50h]; P
0x140007573  test    rcx, rcx
0x140007576  jz      short loc_14000758F
0x140007578  mov     edx, r15d; Tag
0x14000757b  call    cs:__imp_ExFreePoolWithTag
0x140007582  nop     dword ptr [rax+rax+00h]
0x140007587  mov     qword ptr [rbx+50h], 0
0x14000758f  mov     rcx, [rbx+40h]; P
0x140007593  test    rcx, rcx
0x140007596  jz      short loc_1400075AF
0x140007598  mov     edx, r15d; Tag
0x14000759b  call    cs:__imp_ExFreePoolWithTag
0x1400075a2  nop     dword ptr [rax+rax+00h]
0x1400075a7  mov     qword ptr [rbx+40h], 0
0x1400075af  mov     edx, r15d; Tag
0x1400075b2  mov     rcx, rbx; P
0x1400075b5  call    cs:__imp_ExFreePoolWithTag
0x1400075bc  nop     dword ptr [rax+rax+00h]
0x1400075c1  jmp     short loc_140007619
0x1400075c3  xor     ebx, ebx
0x1400075c5  lea     rdx, aPathWzAlreadyS; "Path [%wZ] already suspended, cannot su"...
0x1400075cc  mov     r8, rsi
0x1400075cf  mov     edi, 0C0000035h
0x1400075d4  lea     ecx, [rbx+3]
0x1400075d7  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x1400075dc  jmp     loc_140007553
0x1400075e1  mov     rbx, rsi
0x1400075e4  test    rsi, rsi
0x1400075e7  jnz     loc_1400074FF
0x1400075ed  lea     rdx, aFailedToAlloca_5; "Failed to allocate memory for the suspe"...
0x1400075f4  lea     ecx, [rsi+3]
0x1400075f7  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x1400075fc  mov     edi, 0C000009Ah
0x140007601  jmp     loc_140007553
0x140007606  lea     rcx, stru_140019468; FastMutex
0x14000760d  call    cs:__imp_ExReleaseFastMutex
0x140007614  nop     dword ptr [rax+rax+00h]
0x140007619  mov     rcx, [rbp+P+8]; P
0x14000761d  test    rcx, rcx
0x140007620  jz      short loc_140007639
0x140007622  mov     edx, r15d; Tag
0x140007625  call    cs:__imp_ExFreePoolWithTag
0x14000762c  nop     dword ptr [rax+rax+00h]
0x140007631  mov     [rbp+P+8], 0
0x140007639  mov     rcx, [rbp+String2.Buffer]; P
0x14000763d  test    rcx, rcx
0x140007640  jz      short loc_140007651
0x140007642  mov     edx, r15d; Tag
0x140007645  call    cs:__imp_ExFreePoolWithTag
0x14000764c  nop     dword ptr [rax+rax+00h]
0x140007651  mov     eax, edi
0x140007653  add     rsp, 50h
0x140007657  pop     r15
0x140007659  pop     rdi
0x14000765a  pop     rsi
0x14000765b  pop     rbx
0x14000765c  pop     rbp
0x14000765d  retn
```
