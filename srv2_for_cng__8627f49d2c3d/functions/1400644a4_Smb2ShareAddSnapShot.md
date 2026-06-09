# Smb2ShareAddSnapShot

- ea: `0x1400644a4`
- end: `0x140064684`
- name: `Smb2ShareAddSnapShot`
- size: `480`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14006468c`

## callees

- `0x14001b5a8`
- `0x140038490`
- `0x1400644a4`
- `0x140064f40`
- `0x140065334`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400644ff`
- `ntoskrnl!ExAllocatePool2` at `0x1400644ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006461c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006461c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140064575`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140064587`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140064575`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140064587`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006455f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006455f`
- `ntoskrnl!RtlTimeToTimeFields` at `0x1400645b0`
- `ntoskrnl!RtlTimeToTimeFields` at `0x1400645b0`
- `ntoskrnl!RtlTimeFieldsToTime` at `0x14006464f`
- `ntoskrnl!RtlTimeFieldsToTime` at `0x14006464f`

## pseudocode

```c
__int64 __fastcall Smb2ShareAddSnapShot(__int64 a1, const UNICODE_STRING *a2, const UNICODE_STRING *a3)
{
  __int64 Length; // rbx
  __int64 v5; // rdi
  __int64 result; // rax
  __int64 Pool2; // rax
  _QWORD *v10; // rdi
  __int16 v11; // r8
  int SnapShotTimestamp; // ebx
  _QWORD *v13; // rcx
  _TIME_FIELDS TimeFields; // [rsp+50h] [rbp-58h] BYREF

  Length = a3->Length;
  v5 = a2->Length;
  TimeFields = 0;
  result = Smb2SnapCheckAppInfoForTimeWarp(a2);
  if ( (int)result >= 0 )
  {
    Pool2 = ExAllocatePool2(256, Length + v5 + 134, 1748128588);
    v10 = (_QWORD *)Pool2;
    if ( !Pool2 )
      return 3221225626LL;
    *(_DWORD *)(Pool2 + 48) = 3276850;
    *(_QWORD *)(Pool2 + 56) = Pool2 + 80;
    v11 = a2->Length + 4 + a3->Length;
    *(_QWORD *)(Pool2 + 72) = Pool2 + 130;
    *(_WORD *)(Pool2 + 64) = v11;
    *(_WORD *)(Pool2 + 66) = v11;
    RtlCopyUnicodeString((PUNICODE_STRING)(Pool2 + 64), a2);
    RtlAppendUnicodeStringToString((PUNICODE_STRING)v10 + 4, &Smb2PathSeparatorString);
    RtlAppendUnicodeStringToString((PUNICODE_STRING)v10 + 4, a3);
    SnapShotTimestamp = Smb2ShareQuerySnapShotTimestamp(a2, v10 + 4);
    if ( SnapShotTimestamp < 0 )
      goto LABEL_7;
    RtlTimeToTimeFields((PLARGE_INTEGER)v10 + 4, &TimeFields);
    *(_DWORD *)&TimeFields.Milliseconds = 0;
    if ( RtlStringCbPrintfW(
           (NTSTRSAFE_PWSTR)v10[7],
           0x32u,
           L"@GMT-%04d.%02d.%02d-%02d.%02d.%02d",
           (unsigned int)TimeFields.Year,
           TimeFields.Month,
           TimeFields.Day,
           TimeFields.Hour,
           TimeFields.Minute,
           TimeFields.Second) < 0 )
    {
      SnapShotTimestamp = -1073741595;
LABEL_7:
      ExFreePoolWithTag(v10, 0);
      return (unsigned int)SnapShotTimestamp;
    }
    RtlTimeFieldsToTime(&TimeFields, (PLARGE_INTEGER)v10 + 4);
    v13 = *(_QWORD **)(a1 + 344);
    if ( *v13 != a1 + 336 )
      __fastfail(3u);
    *v10 = a1 + 336;
    v10[1] = v13;
    *v13 = v10;
    *(_QWORD *)(a1 + 344) = v10;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400644a4  push    rbx
0x1400644a6  push    rbp
0x1400644a7  push    rsi
0x1400644a8  push    rdi
0x1400644a9  push    r12
0x1400644ab  push    r14
0x1400644ad  push    r15
0x1400644af  sub     rsp, 70h
0x1400644b3  mov     rax, cs:__security_cookie
0x1400644ba  xor     rax, rsp
0x1400644bd  mov     [rsp+0A8h+var_48], rax
0x1400644c2  movzx   ebx, word ptr [r8]
0x1400644c6  mov     r15, rcx
0x1400644c9  movzx   edi, word ptr [rdx]
0x1400644cc  xorps   xmm0, xmm0
0x1400644cf  mov     rcx, rdx
0x1400644d2  mov     r14, r8
0x1400644d5  movups  xmmword ptr [rsp+0A8h+TimeFields.Year], xmm0
0x1400644da  mov     rsi, rdx
0x1400644dd  call    Smb2SnapCheckAppInfoForTimeWarp
0x1400644e2  test    eax, eax
0x1400644e4  js      loc_14006462A
0x1400644ea  lea     rdx, [rdi+86h]
0x1400644f1  mov     ecx, 100h
0x1400644f6  add     rdx, rbx
0x1400644f9  mov     r8d, 6832534Ch
0x1400644ff  call    cs:__imp_ExAllocatePool2
0x140064506  nop     dword ptr [rax+rax+00h]
0x14006450b  mov     rdi, rax
0x14006450e  test    rax, rax
0x140064511  jnz     short loc_14006451D
0x140064513  mov     eax, 0C000009Ah
0x140064518  jmp     loc_14006462A
0x14006451d  mov     dword ptr [rax+30h], 320032h
0x140064524  lea     rbx, [rdi+40h]
0x140064528  add     rax, 50h ; 'P'
0x14006452c  mov     rdx, rsi; SourceString
0x14006452f  mov     [rdi+38h], rax
0x140064533  mov     rcx, rbx; DestinationString
0x140064536  movzx   eax, word ptr [rsi]
0x140064539  mov     r12d, 32h ; '2'
0x14006453f  movzx   r8d, word ptr [r14]
0x140064543  add     ax, 4
0x140064547  add     r8w, ax
0x14006454b  lea     rax, [rdi+82h]
0x140064552  mov     [rdi+48h], rax
0x140064556  mov     [rbx], r8w
0x14006455a  mov     [rdi+42h], r8w
0x14006455f  call    cs:__imp_RtlCopyUnicodeString
0x140064566  nop     dword ptr [rax+rax+00h]
0x14006456b  lea     rdx, Smb2PathSeparatorString; Source
0x140064572  mov     rcx, rbx; Destination
0x140064575  call    cs:__imp_RtlAppendUnicodeStringToString
0x14006457c  nop     dword ptr [rax+rax+00h]
0x140064581  mov     rdx, r14; Source
0x140064584  mov     rcx, rbx; Destination
0x140064587  call    cs:__imp_RtlAppendUnicodeStringToString
0x14006458e  nop     dword ptr [rax+rax+00h]
0x140064593  lea     rbp, [rdi+20h]
0x140064597  mov     rcx, rsi
0x14006459a  mov     rdx, rbp
0x14006459d  call    Smb2ShareQuerySnapShotTimestamp
0x1400645a2  mov     ebx, eax
0x1400645a4  test    eax, eax
0x1400645a6  js      short loc_140064617
0x1400645a8  lea     rdx, [rsp+0A8h+TimeFields]; TimeFields
0x1400645ad  mov     rcx, rbp; Time
0x1400645b0  call    cs:__imp_RtlTimeToTimeFields
0x1400645b7  nop     dword ptr [rax+rax+00h]
0x1400645bc  movsx   ecx, [rsp+0A8h+TimeFields.Minute]
0x1400645c1  xor     eax, eax
0x1400645c3  movsx   r8d, [rsp+0A8h+TimeFields.Hour]
0x1400645c9  mov     edx, r12d; cbDest
0x1400645cc  movsx   r10d, [rsp+0A8h+TimeFields.Day]
0x1400645d2  movsx   r11d, [rsp+0A8h+TimeFields.Month]
0x1400645d8  movsx   r9d, [rsp+0A8h+TimeFields.Year]
0x1400645de  mov     dword ptr [rsp+0A8h+TimeFields.Milliseconds], eax
0x1400645e2  movsx   eax, [rsp+0A8h+TimeFields.Second]
0x1400645e7  mov     [rsp+0A8h+var_68], eax
0x1400645eb  mov     [rsp+0A8h+var_70], ecx
0x1400645ef  mov     rcx, [rdi+38h]; pszDest
0x1400645f3  mov     [rsp+0A8h+var_78], r8d
0x1400645f8  lea     r8, aGmt04d02d02d02; "@GMT-%04d.%02d.%02d-%02d.%02d.%02d"
0x1400645ff  mov     [rsp+0A8h+var_80], r10d
0x140064604  mov     [rsp+0A8h+var_88], r11d
0x140064609  call    RtlStringCbPrintfW
0x14006460e  test    eax, eax
0x140064610  jns     short loc_140064647
0x140064612  mov     ebx, 0C00000E5h
0x140064617  xor     edx, edx; Tag
0x140064619  mov     rcx, rdi; P
0x14006461c  call    cs:__imp_ExFreePoolWithTag
0x140064623  nop     dword ptr [rax+rax+00h]
0x140064628  mov     eax, ebx
0x14006462a  mov     rcx, [rsp+0A8h+var_48]
0x14006462f  xor     rcx, rsp; StackCookie
0x140064632  call    __security_check_cookie
0x140064637  add     rsp, 70h
0x14006463b  pop     r15
0x14006463d  pop     r14
0x14006463f  pop     r12
0x140064641  pop     rdi
0x140064642  pop     rsi
0x140064643  pop     rbp
0x140064644  pop     rbx
0x140064645  retn
0x140064647  mov     rdx, rbp; Time
0x14006464a  lea     rcx, [rsp+0A8h+TimeFields]; TimeFields
0x14006464f  call    cs:__imp_RtlTimeFieldsToTime
0x140064656  nop     dword ptr [rax+rax+00h]
0x14006465b  lea     rax, [r15+150h]
0x140064662  mov     rcx, [rax+8]
0x140064666  cmp     [rcx], rax
0x140064669  jz      short loc_140064672
0x14006466b  mov     ecx, 3
0x140064670  int     29h; Win8: RtlFailFast(ecx)
0x140064672  mov     [rdi], rax
0x140064675  mov     [rdi+8], rcx
0x140064679  mov     [rcx], rdi
0x14006467c  mov     [rax+8], rdi
0x140064680  xor     eax, eax
0x140064682  jmp     short loc_14006462A
```
