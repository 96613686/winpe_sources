# Smb2ShareAddSnapShot

- ea: `0x1400644f4`
- end: `0x1400646d4`
- name: `Smb2ShareAddSnapShot`
- size: `480`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400646dc`

## callees

- `0x14001b5a8`
- `0x140038490`
- `0x1400644f4`
- `0x140064f90`
- `0x140065384`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14006454f`
- `ntoskrnl!ExAllocatePool2` at `0x14006454f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006466c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006466c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400645c5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400645d7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400645c5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400645d7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400645af`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400645af`
- `ntoskrnl!RtlTimeToTimeFields` at `0x140064600`
- `ntoskrnl!RtlTimeToTimeFields` at `0x140064600`
- `ntoskrnl!RtlTimeFieldsToTime` at `0x14006469f`
- `ntoskrnl!RtlTimeFieldsToTime` at `0x14006469f`

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
0x1400644f4  push    rbx
0x1400644f6  push    rbp
0x1400644f7  push    rsi
0x1400644f8  push    rdi
0x1400644f9  push    r12
0x1400644fb  push    r14
0x1400644fd  push    r15
0x1400644ff  sub     rsp, 70h
0x140064503  mov     rax, cs:__security_cookie
0x14006450a  xor     rax, rsp
0x14006450d  mov     [rsp+0A8h+var_48], rax
0x140064512  movzx   ebx, word ptr [r8]
0x140064516  mov     r15, rcx
0x140064519  movzx   edi, word ptr [rdx]
0x14006451c  xorps   xmm0, xmm0
0x14006451f  mov     rcx, rdx
0x140064522  mov     r14, r8
0x140064525  movups  xmmword ptr [rsp+0A8h+TimeFields.Year], xmm0
0x14006452a  mov     rsi, rdx
0x14006452d  call    Smb2SnapCheckAppInfoForTimeWarp
0x140064532  test    eax, eax
0x140064534  js      loc_14006467A
0x14006453a  lea     rdx, [rdi+86h]
0x140064541  mov     ecx, 100h
0x140064546  add     rdx, rbx
0x140064549  mov     r8d, 6832534Ch
0x14006454f  call    cs:__imp_ExAllocatePool2
0x140064556  nop     dword ptr [rax+rax+00h]
0x14006455b  mov     rdi, rax
0x14006455e  test    rax, rax
0x140064561  jnz     short loc_14006456D
0x140064563  mov     eax, 0C000009Ah
0x140064568  jmp     loc_14006467A
0x14006456d  mov     dword ptr [rax+30h], 320032h
0x140064574  lea     rbx, [rdi+40h]
0x140064578  add     rax, 50h ; 'P'
0x14006457c  mov     rdx, rsi; SourceString
0x14006457f  mov     [rdi+38h], rax
0x140064583  mov     rcx, rbx; DestinationString
0x140064586  movzx   eax, word ptr [rsi]
0x140064589  mov     r12d, 32h ; '2'
0x14006458f  movzx   r8d, word ptr [r14]
0x140064593  add     ax, 4
0x140064597  add     r8w, ax
0x14006459b  lea     rax, [rdi+82h]
0x1400645a2  mov     [rdi+48h], rax
0x1400645a6  mov     [rbx], r8w
0x1400645aa  mov     [rdi+42h], r8w
0x1400645af  call    cs:__imp_RtlCopyUnicodeString
0x1400645b6  nop     dword ptr [rax+rax+00h]
0x1400645bb  lea     rdx, Smb2PathSeparatorString; Source
0x1400645c2  mov     rcx, rbx; Destination
0x1400645c5  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400645cc  nop     dword ptr [rax+rax+00h]
0x1400645d1  mov     rdx, r14; Source
0x1400645d4  mov     rcx, rbx; Destination
0x1400645d7  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400645de  nop     dword ptr [rax+rax+00h]
0x1400645e3  lea     rbp, [rdi+20h]
0x1400645e7  mov     rcx, rsi
0x1400645ea  mov     rdx, rbp
0x1400645ed  call    Smb2ShareQuerySnapShotTimestamp
0x1400645f2  mov     ebx, eax
0x1400645f4  test    eax, eax
0x1400645f6  js      short loc_140064667
0x1400645f8  lea     rdx, [rsp+0A8h+TimeFields]; TimeFields
0x1400645fd  mov     rcx, rbp; Time
0x140064600  call    cs:__imp_RtlTimeToTimeFields
0x140064607  nop     dword ptr [rax+rax+00h]
0x14006460c  movsx   ecx, [rsp+0A8h+TimeFields.Minute]
0x140064611  xor     eax, eax
0x140064613  movsx   r8d, [rsp+0A8h+TimeFields.Hour]
0x140064619  mov     edx, r12d; cbDest
0x14006461c  movsx   r10d, [rsp+0A8h+TimeFields.Day]
0x140064622  movsx   r11d, [rsp+0A8h+TimeFields.Month]
0x140064628  movsx   r9d, [rsp+0A8h+TimeFields.Year]
0x14006462e  mov     dword ptr [rsp+0A8h+TimeFields.Milliseconds], eax
0x140064632  movsx   eax, [rsp+0A8h+TimeFields.Second]
0x140064637  mov     [rsp+0A8h+var_68], eax
0x14006463b  mov     [rsp+0A8h+var_70], ecx
0x14006463f  mov     rcx, [rdi+38h]; pszDest
0x140064643  mov     [rsp+0A8h+var_78], r8d
0x140064648  lea     r8, aGmt04d02d02d02; "@GMT-%04d.%02d.%02d-%02d.%02d.%02d"
0x14006464f  mov     [rsp+0A8h+var_80], r10d
0x140064654  mov     [rsp+0A8h+var_88], r11d
0x140064659  call    RtlStringCbPrintfW
0x14006465e  test    eax, eax
0x140064660  jns     short loc_140064697
0x140064662  mov     ebx, 0C00000E5h
0x140064667  xor     edx, edx; Tag
0x140064669  mov     rcx, rdi; P
0x14006466c  call    cs:__imp_ExFreePoolWithTag
0x140064673  nop     dword ptr [rax+rax+00h]
0x140064678  mov     eax, ebx
0x14006467a  mov     rcx, [rsp+0A8h+var_48]
0x14006467f  xor     rcx, rsp; StackCookie
0x140064682  call    __security_check_cookie
0x140064687  add     rsp, 70h
0x14006468b  pop     r15
0x14006468d  pop     r14
0x14006468f  pop     r12
0x140064691  pop     rdi
0x140064692  pop     rsi
0x140064693  pop     rbp
0x140064694  pop     rbx
0x140064695  retn
0x140064697  mov     rdx, rbp; Time
0x14006469a  lea     rcx, [rsp+0A8h+TimeFields]; TimeFields
0x14006469f  call    cs:__imp_RtlTimeFieldsToTime
0x1400646a6  nop     dword ptr [rax+rax+00h]
0x1400646ab  lea     rax, [r15+150h]
0x1400646b2  mov     rcx, [rax+8]
0x1400646b6  cmp     [rcx], rax
0x1400646b9  jz      short loc_1400646C2
0x1400646bb  mov     ecx, 3
0x1400646c0  int     29h; Win8: RtlFailFast(ecx)
0x1400646c2  mov     [rdi], rax
0x1400646c5  mov     [rdi+8], rcx
0x1400646c9  mov     [rcx], rdi
0x1400646cc  mov     [rax+8], rdi
0x1400646d0  xor     eax, eax
0x1400646d2  jmp     short loc_14006467A
```
