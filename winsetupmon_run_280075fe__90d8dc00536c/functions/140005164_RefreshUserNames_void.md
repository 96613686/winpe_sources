# RefreshUserNames(void *)

- ea: `0x140005164`
- end: `0x14000553c`
- name: `?RefreshUserNames@@YAJPEAX@Z`
- size: `984`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140004e30`

## callees

- `0x140003944`
- `0x140005164`
- `0x14000563c`
- `0x14000f9e0`
- `0x14000fd40`

## import_xrefs

- `ntoskrnl!ZwEnumerateKey` at `0x140005287`
- `ntoskrnl!ZwEnumerateKey` at `0x14000542d`
- `ntoskrnl!ZwEnumerateKey` at `0x140005287`
- `ntoskrnl!ZwEnumerateKey` at `0x14000542d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400051d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400051e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005239`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000530a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000546d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005486`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400051d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400051e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005239`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000530a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000546d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005486`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140005255`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140005330`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140005255`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140005330`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400052e1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400052e1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400053c1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400053c1`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400053d1`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400053d1`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400053ef`
- `FLTMGR!FltReleasePushLockEx` at `0x140005451`
- `FLTMGR!FltReleasePushLockEx` at `0x1400054a0`
- `FLTMGR!FltReleasePushLockEx` at `0x140005451`
- `FLTMGR!FltReleasePushLockEx` at `0x1400054a0`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400051a3`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400051a3`

## string_xrefs

- `0x140005393`: `RtlQueryRegistryValuesEx`
- `0x1400054cc`: `Could not build relative path to ProfileList sub-key %wZ (0x%08X)`
- `0x14000539a`: `ProfileImagePath`

## pseudocode

```c
__int64 __fastcall RefreshUserNames(HANDLE KeyHandle)
{
  unsigned __int16 *PoolWithTag; // rdi
  ULONG Length; // r12d
  unsigned __int16 *v4; // rsi
  char v5; // r14
  void *v6; // rcx
  _QWORD *v7; // rbx
  ULONG v8; // r15d
  NTSTATUS v9; // eax
  NTSTATUS v10; // ebx
  BOOLEAN v11; // r8
  __int64 v12; // rbx
  const UNICODE_STRING *v13; // rdx
  unsigned __int16 *v14; // rax
  int v15; // eax
  PVOID SystemRoutineAddress; // rax
  int v17; // eax
  UNICODE_STRING String1; // [rsp+30h] [rbp-89h] BYREF
  _QWORD v20[2]; // [rsp+40h] [rbp-79h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-69h] BYREF
  _QWORD v22[22]; // [rsp+60h] [rbp-59h] BYREF
  SIZE_T NumberOfBytes; // [rsp+128h] [rbp+6Fh] BYREF

  v20[0] = 1572886;
  PoolWithTag = 0;
  v20[1] = L"ProfileList";
  Length = 0;
  v4 = 0;
  FltAcquirePushLockExclusiveEx(&PushLock, 0);
  v5 = 1;
  while ( 1 )
  {
    v7 = qword_140019420;
    if ( !qword_140019420 )
      break;
    qword_140019420 = *(PVOID *)qword_140019420;
    v6 = (void *)v7[2];
    if ( v6 )
    {
      ExFreePoolWithTag(v6, 0x6E6D7377u);
      v7[2] = 0;
    }
    ExFreePoolWithTag(v7, 0x6E6D7377u);
  }
  LODWORD(NumberOfBytes) = 0;
  v8 = 0;
  v9 = ZwEnumerateKey(KeyHandle, 0, KeyBasicInformation, 0, 0, (PULONG)&NumberOfBytes);
  while ( 2 )
  {
    v10 = v9;
    if ( v9 == -2147483622 )
    {
      v10 = 0;
      FltReleasePushLockEx(&PushLock, 0);
      v5 = 0;
      goto LABEL_30;
    }
    if ( v9 == -2147483643 || v9 == -1073741789 )
    {
      if ( PoolWithTag )
        ExFreePoolWithTag(PoolWithTag, 0x6E6D7377u);
      Length = NumberOfBytes;
      PoolWithTag = (unsigned __int16 *)ExAllocatePoolWithTag(PagedPool, (unsigned int)NumberOfBytes, 0x6E6D7377u);
      if ( !PoolWithTag )
      {
        WriteLogMessage(3, L"Failed to allocate memory for the ProfileList sub-key name");
        v10 = -1073741670;
LABEL_30:
        if ( !v4 )
          goto LABEL_32;
        goto LABEL_31;
      }
      v10 = ZwEnumerateKey(KeyHandle, v8, KeyBasicInformation, PoolWithTag, Length, (PULONG)&NumberOfBytes);
    }
    if ( v10 < 0 )
    {
      WriteLogMessage(3, L"Could not enumerate sub-key of ProfileList key at index %u (0x%08X)", v8, (unsigned int)v10);
      goto LABEL_30;
    }
    v11 = 0;
    String1 = 0;
    v12 = 0;
    String1.Length = PoolWithTag[6];
    String1.MaximumLength = String1.Length;
    String1.Buffer = PoolWithTag + 8;
    while ( (unsigned int)v12 < dword_140019408 )
    {
      v13 = (const UNICODE_STRING *)*((_QWORD *)qword_140019410 + v12);
      if ( v13 )
        v11 = RtlEqualUnicodeString(&String1, v13, 0);
      v12 = (unsigned int)(v12 + 1);
      if ( v11 )
        goto LABEL_27;
    }
    if ( v4 )
      ExFreePoolWithTag(v4, 0x6E6D7377u);
    LODWORD(NumberOfBytes) = String1.Length + 4 + LOWORD(v20[0]);
    v14 = (unsigned __int16 *)ExAllocatePoolWithTag(PagedPool, (unsigned int)NumberOfBytes, 0x6E6D7377u);
    v4 = v14;
    if ( v14 )
    {
      *v14 = 0;
      v15 = RtlStringCbPrintfW(v14, (unsigned int)NumberOfBytes, L"%wZ\\%wZ", v20, &String1);
      v10 = v15;
      if ( v15 < 0 )
      {
        WriteLogMessage(
          3,
          L"Could not build relative path to ProfileList sub-key %wZ (0x%08X)",
          &String1,
          (unsigned int)v15);
      }
      else
      {
        memset(v22, 0, 0x70u);
        v22[0] = ProfileImagePathQueryRoutine;
        LODWORD(v22[1]) = 0;
        v22[2] = L"ProfileImagePath";
        v22[3] = 0;
        LODWORD(v22[4]) = 0;
        v22[5] = 0;
        LODWORD(v22[6]) = 0;
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
        SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
        if ( !SystemRoutineAddress )
          SystemRoutineAddress = RtlQueryRegistryValues;
        v17 = ((__int64 (__fastcall *)(__int64, unsigned __int16 *, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(
                3,
                v4,
                v22,
                0,
                0);
        v10 = v17;
        if ( v17 >= 0 )
        {
LABEL_27:
          LODWORD(NumberOfBytes) = 0;
          v9 = ZwEnumerateKey(KeyHandle, ++v8, KeyBasicInformation, PoolWithTag, Length, (PULONG)&NumberOfBytes);
          continue;
        }
        WriteLogMessage(3, L"Could not query value under ProfileList sub-key %wZ (0x%08X)", &String1, (unsigned int)v17);
      }
LABEL_31:
      ExFreePoolWithTag(v4, 0x6E6D7377u);
      goto LABEL_32;
    }
    break;
  }
  WriteLogMessage(3, L"Failed to allocate memory for the ProfileList sub-key relative name");
  v10 = -1073741670;
LABEL_32:
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0x6E6D7377u);
  if ( v5 )
    FltReleasePushLockEx(&PushLock, 0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140005164  push    rbp
0x140005166  push    rbx
0x140005167  push    rsi
0x140005168  push    rdi
0x140005169  push    r12
0x14000516b  push    r13
0x14000516d  push    r14
0x14000516f  push    r15
0x140005171  lea     rbp, [rsp-1Fh]
0x140005176  sub     rsp, 0D8h
0x14000517d  mov     r13, rcx
0x140005180  mov     [rbp+57h+var_D0], 180016h
0x140005188  lea     rax, aProfilelist; "ProfileList"
0x14000518f  xor     edi, edi
0x140005191  lea     rcx, PushLock
0x140005198  mov     [rbp+57h+var_C8], rax
0x14000519c  xor     r12d, r12d
0x14000519f  xor     esi, esi
0x1400051a1  xor     edx, edx
0x1400051a3  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400051aa  nop     dword ptr [rax+rax+00h]
0x1400051af  lea     r14d, [rdi+1]
0x1400051b3  mov     r15d, 6E6D7377h
0x1400051b9  jmp     short loc_1400051F3
0x1400051bb  mov     rax, [rbx]
0x1400051be  mov     cs:qword_140019420, rax
0x1400051c5  mov     rcx, [rbx+10h]; P
0x1400051c9  test    rcx, rcx
0x1400051cc  jz      short loc_1400051E1
0x1400051ce  mov     edx, r15d; Tag
0x1400051d1  call    cs:__imp_ExFreePoolWithTag
0x1400051d8  nop     dword ptr [rax+rax+00h]
0x1400051dd  mov     [rbx+10h], rsi
0x1400051e1  mov     edx, r15d; Tag
0x1400051e4  mov     rcx, rbx; P
0x1400051e7  call    cs:__imp_ExFreePoolWithTag
0x1400051ee  nop     dword ptr [rax+rax+00h]
0x1400051f3  mov     rbx, cs:qword_140019420
0x1400051fa  test    rbx, rbx
0x1400051fd  jnz     short loc_1400051BB
0x1400051ff  lea     rax, [rbp+57h+NumberOfBytes]
0x140005203  mov     dword ptr [rbp+57h+NumberOfBytes], esi
0x140005206  xor     r15d, r15d
0x140005209  mov     [rsp+110h+ResultLength], rax
0x14000520e  xor     r9d, r9d
0x140005211  mov     [rsp+110h+Length], esi
0x140005215  xor     edx, edx
0x140005217  jmp     loc_140005427
0x14000521c  cmp     ebx, 80000005h
0x140005222  jz      short loc_14000522C
0x140005224  cmp     ebx, 0C0000023h
0x14000522a  jnz     short loc_140005295
0x14000522c  test    rdi, rdi
0x14000522f  jz      short loc_140005245
0x140005231  mov     edx, 6E6D7377h; Tag
0x140005236  mov     rcx, rdi; P
0x140005239  call    cs:__imp_ExFreePoolWithTag
0x140005240  nop     dword ptr [rax+rax+00h]
0x140005245  mov     r12d, dword ptr [rbp+57h+NumberOfBytes]
0x140005249  mov     r8d, 6E6D7377h; Tag
0x14000524f  mov     edx, r12d; NumberOfBytes
0x140005252  mov     ecx, r14d; PoolType
0x140005255  call    cs:__imp_ExAllocatePoolWithTag
0x14000525c  nop     dword ptr [rax+rax+00h]
0x140005261  mov     rdi, rax
0x140005264  test    rax, rax
0x140005267  jz      loc_140005521
0x14000526d  lea     rax, [rbp+57h+NumberOfBytes]
0x140005271  mov     r9, rdi; KeyInformation
0x140005274  mov     [rsp+110h+ResultLength], rax; ResultLength
0x140005279  xor     r8d, r8d; KeyInformationClass
0x14000527c  mov     edx, r15d; Index
0x14000527f  mov     [rsp+110h+Length], r12d; Length
0x140005284  mov     rcx, r13; KeyHandle
0x140005287  call    cs:__imp_ZwEnumerateKey
0x14000528e  nop     dword ptr [rax+rax+00h]
0x140005293  mov     ebx, eax
0x140005295  test    ebx, ebx
0x140005297  js      loc_140005505
0x14000529d  xorps   xmm0, xmm0
0x1400052a0  xor     r8b, r8b
0x1400052a3  movups  xmmword ptr [rsp+110h+String1.Length], xmm0
0x1400052a8  movzx   eax, word ptr [rdi+0Ch]
0x1400052ac  xor     ebx, ebx
0x1400052ae  mov     [rsp+110h+String1.Length], ax
0x1400052b3  mov     [rsp+110h+String1.MaximumLength], ax
0x1400052b8  lea     rax, [rdi+10h]
0x1400052bc  mov     [rsp+110h+String1.Buffer], rax
0x1400052c1  cmp     ebx, cs:dword_140019408
0x1400052c7  jnb     short loc_1400052FD
0x1400052c9  mov     rax, cs:qword_140019410
0x1400052d0  mov     rdx, [rax+rbx*8]; String2
0x1400052d4  test    rdx, rdx
0x1400052d7  jz      short loc_1400052F0
0x1400052d9  xor     r8d, r8d; CaseInSensitive
0x1400052dc  lea     rcx, [rsp+110h+String1]; String1
0x1400052e1  call    cs:__imp_RtlEqualUnicodeString
0x1400052e8  nop     dword ptr [rax+rax+00h]
0x1400052ed  mov     r8b, al
0x1400052f0  add     ebx, r14d
0x1400052f3  test    r8b, r8b
0x1400052f6  jz      short loc_1400052C1
0x1400052f8  jmp     loc_140005409
0x1400052fd  test    rsi, rsi
0x140005300  jz      short loc_140005316
0x140005302  mov     edx, 6E6D7377h; Tag
0x140005307  mov     rcx, rsi; P
0x14000530a  call    cs:__imp_ExFreePoolWithTag
0x140005311  nop     dword ptr [rax+rax+00h]
0x140005316  movzx   ecx, [rsp+110h+String1.Length]
0x14000531b  mov     r8d, 6E6D7377h; Tag
0x140005321  movzx   edx, word ptr [rbp+57h+var_D0]
0x140005325  add     ecx, 4
0x140005328  add     edx, ecx; NumberOfBytes
0x14000532a  mov     ecx, r14d; PoolType
0x14000532d  mov     dword ptr [rbp+57h+NumberOfBytes], edx
0x140005330  call    cs:__imp_ExAllocatePoolWithTag
0x140005337  nop     dword ptr [rax+rax+00h]
0x14000533c  mov     rsi, rax
0x14000533f  test    rax, rax
0x140005342  jz      loc_1400054EA
0x140005348  xor     eax, eax
0x14000534a  lea     r9, [rbp+57h+var_D0]
0x14000534e  mov     [rsi], ax
0x140005351  lea     r8, aWzWz; "%wZ\\%wZ"
0x140005358  mov     edx, dword ptr [rbp+57h+NumberOfBytes]; unsigned __int64
0x14000535b  lea     rax, [rsp+110h+String1]
0x140005360  mov     rcx, rsi; unsigned __int16 *
0x140005363  mov     qword ptr [rsp+110h+Length], rax
0x140005368  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000536d  mov     ebx, eax
0x14000536f  test    eax, eax
0x140005371  js      loc_1400054CC
0x140005377  xor     edx, edx; Val
0x140005379  lea     rcx, [rbp+57h+var_B0]; void *
0x14000537d  lea     r8d, [rdx+70h]; Size
0x140005381  call    memset
0x140005386  xor     ebx, ebx
0x140005388  lea     rax, ?ProfileImagePathQueryRoutine@@YAJPEAGKPEAXK11@Z; ProfileImagePathQueryRoutine(ushort *,ulong,void *,ulong,void *,void *)
0x14000538f  mov     [rbp+57h+var_B0], rax
0x140005393  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x14000539a  lea     rax, aProfileimagepa; "ProfileImagePath"
0x1400053a1  mov     [rbp+57h+var_A8], ebx
0x1400053a4  xorps   xmm0, xmm0
0x1400053a7  mov     [rbp+57h+var_A0], rax
0x1400053ab  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400053af  mov     [rbp+57h+var_98], rbx
0x1400053b3  mov     [rbp+57h+var_90], ebx
0x1400053b6  mov     [rbp+57h+var_88], rbx
0x1400053ba  mov     [rbp+57h+var_80], ebx
0x1400053bd  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400053c1  call    cs:__imp_RtlInitUnicodeString
0x1400053c8  nop     dword ptr [rax+rax+00h]
0x1400053cd  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x1400053d1  call    cs:__imp_MmGetSystemRoutineAddress
0x1400053d8  nop     dword ptr [rax+rax+00h]
0x1400053dd  lea     r8, [rbp+57h+var_B0]
0x1400053e1  mov     qword ptr [rsp+110h+Length], rbx
0x1400053e6  test    rax, rax
0x1400053e9  lea     ecx, [rbx+3]
0x1400053ec  mov     rdx, rsi
0x1400053ef  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x1400053f7  xor     r9d, r9d
0x1400053fa  call    _guard_dispatch_icall
0x1400053ff  mov     ebx, eax
0x140005401  test    eax, eax
0x140005403  js      loc_1400054C3
0x140005409  lea     rax, [rbp+57h+NumberOfBytes]
0x14000540d  mov     dword ptr [rbp+57h+NumberOfBytes], 0
0x140005414  add     r15d, r14d
0x140005417  mov     [rsp+110h+ResultLength], rax; ResultLength
0x14000541c  mov     [rsp+110h+Length], r12d; Length
0x140005421  mov     r9, rdi; KeyInformation
0x140005424  mov     edx, r15d; Index
0x140005427  xor     r8d, r8d; KeyInformationClass
0x14000542a  mov     rcx, r13; KeyHandle
0x14000542d  call    cs:__imp_ZwEnumerateKey
0x140005434  nop     dword ptr [rax+rax+00h]
0x140005439  mov     ebx, eax
0x14000543b  cmp     eax, 8000001Ah
0x140005440  jnz     loc_14000521C
0x140005446  xor     edx, edx
0x140005448  lea     rcx, PushLock
0x14000544f  xor     ebx, ebx
0x140005451  call    cs:__imp_FltReleasePushLockEx
0x140005458  nop     dword ptr [rax+rax+00h]
0x14000545d  xor     r14b, r14b
0x140005460  test    rsi, rsi
0x140005463  jz      short loc_140005479
0x140005465  mov     edx, 6E6D7377h; Tag
0x14000546a  mov     rcx, rsi; P
0x14000546d  call    cs:__imp_ExFreePoolWithTag
0x140005474  nop     dword ptr [rax+rax+00h]
0x140005479  test    rdi, rdi
0x14000547c  jz      short loc_140005492
0x14000547e  mov     edx, 6E6D7377h; Tag
0x140005483  mov     rcx, rdi; P
0x140005486  call    cs:__imp_ExFreePoolWithTag
0x14000548d  nop     dword ptr [rax+rax+00h]
0x140005492  test    r14b, r14b
0x140005495  jz      short loc_1400054AC
0x140005497  xor     edx, edx
0x140005499  lea     rcx, PushLock
0x1400054a0  call    cs:__imp_FltReleasePushLockEx
0x1400054a7  nop     dword ptr [rax+rax+00h]
0x1400054ac  mov     eax, ebx
0x1400054ae  add     rsp, 0D8h
0x1400054b5  pop     r15
0x1400054b7  pop     r14
0x1400054b9  pop     r13
0x1400054bb  pop     r12
0x1400054bd  pop     rdi
0x1400054be  pop     rsi
0x1400054bf  pop     rbx
0x1400054c0  pop     rbp
0x1400054c1  retn
0x1400054c3  lea     rdx, aCouldNotQueryV; "Could not query value under ProfileList"...
0x1400054ca  jmp     short loc_1400054D3
0x1400054cc  lea     rdx, aCouldNotBuildR; "Could not build relative path to Profil"...
0x1400054d3  lea     r8, [rsp+110h+String1]
0x1400054d8  mov     r9d, eax
0x1400054db  mov     ecx, 3
0x1400054e0  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x1400054e5  jmp     loc_140005465
0x1400054ea  lea     rdx, aFailedToAlloca_2; "Failed to allocate memory for the Profi"...
0x1400054f1  mov     ecx, 3
0x1400054f6  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x1400054fb  mov     ebx, 0C000009Ah
0x140005500  jmp     loc_140005479
0x140005505  mov     r9d, ebx
0x140005508  lea     rdx, aCouldNotEnumer; "Could not enumerate sub-key of ProfileL"...
0x14000550f  mov     r8d, r15d
0x140005512  mov     ecx, 3
0x140005517  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x14000551c  jmp     loc_140005460
0x140005521  lea     rdx, aFailedToAlloca_3; "Failed to allocate memory for the Profi"...
0x140005528  mov     ecx, 3
0x14000552d  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140005532  mov     ebx, 0C000009Ah
0x140005537  jmp     loc_140005460
```
