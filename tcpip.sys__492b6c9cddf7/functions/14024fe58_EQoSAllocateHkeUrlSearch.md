# EQoSAllocateHkeUrlSearch

- ea: `0x14024fe58`
- end: `0x14025003b`
- name: `EQoSAllocateHkeUrlSearch`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140259e30`

## callees

- `0x1401bf640`
- `0x14024fe58`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x14024ff02`
- `ntoskrnl!RtlLengthSid` at `0x14024ff02`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14024ff3a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14024ff3a`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x14024ffc5`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x14024ffc5`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14024fec6`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14024fee5`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14024fec6`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14024fee5`
- `ntoskrnl!RtlCopySid` at `0x14024ff82`
- `ntoskrnl!RtlCopySid` at `0x14024ff82`
- `ntoskrnl!ExAllocatePool2` at `0x14024ff53`
- `ntoskrnl!ExAllocatePool2` at `0x14024ff53`

## pseudocode

```c
__int64 __fastcall EQoSAllocateHkeUrlSearch(__int64 a1, void *a2, __int64 a3, __int64 a4, char *a5)
{
  char v7; // bl
  char v9; // al
  ULONG v10; // eax
  size_t v11; // r15
  __int64 v12; // r13
  __int64 v13; // rdx
  char *Pool2; // rax
  char *v15; // rsi
  char *v17; // rbx
  UNICODE_STRING String2; // [rsp+20h] [rbp-38h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-28h] BYREF
  UNICODE_STRING v20; // [rsp+40h] [rbp-18h] BYREF

  *(_DWORD *)(&String2.MaximumLength + 1) = 0;
  String1.Buffer = L"http:";
  *(_QWORD *)&String1.Length = 786442;
  v20.Buffer = L"https:";
  String2.Buffer = *(PWSTR *)(a1 + 16);
  v7 = 1;
  String2.Length = *(_WORD *)a1;
  String2.MaximumLength = String2.Length;
  *(_QWORD *)&v20.Length = 917516;
  if ( RtlPrefixUnicodeString(&String1, &String2, 1u) )
  {
    v9 = 0;
  }
  else
  {
    if ( !RtlPrefixUnicodeString(&v20, &String2, 1u) )
      return 3221226021LL;
    v9 = 1;
  }
  *(_BYTE *)(a4 + 34) = v9;
  v10 = RtlLengthSid(a2);
  v11 = (unsigned __int16)(*(_WORD *)(a1 + 32) + *(_WORD *)(a1 + 4) - *(_WORD *)(a1 + 16));
  v12 = v10;
  v13 = (unsigned int)v11 + ((v10 + 7) & 0xFFFFFFF8);
  if ( (unsigned int)v13 > 0x100 )
  {
    Pool2 = (char *)ExAllocatePool2(64, v13, 1883787589);
    v7 = 0;
  }
  else
  {
    Pool2 = (char *)ExAllocateFromNPagedLookasideList(&EQoSHkeAcquireQoSParametersLookaside);
  }
  v15 = Pool2;
  *a5 = v7;
  if ( !Pool2 )
    return 3221225626LL;
  RtlCopySid(v12, Pool2, a2);
  *(_QWORD *)(a4 + 48) = v15;
  v17 = &v15[(v12 + 7) & 0xFFFFFFFFFFFFFFF8uLL];
  memmove(v17, *(const void **)(a1 + 16), v11);
  String2.Buffer = (PWSTR)v17;
  String2.Length = v11;
  String2.MaximumLength = v11;
  RtlDowncaseUnicodeString(&String2, &String2, 0);
  *(_QWORD *)(a4 + 8) = &v17[*(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 16)];
  *(_WORD *)a4 = *(_WORD *)(a1 + 2);
  *(_WORD *)(a4 + 2) = *(_WORD *)(a1 + 2);
  *(_QWORD *)(a4 + 24) = &v17[*(_QWORD *)(a1 + 32) - *(_QWORD *)(a1 + 16)];
  *(_WORD *)(a4 + 16) = *(_WORD *)(a1 + 4);
  *(_WORD *)(a4 + 18) = *(_WORD *)(a1 + 4);
  *(_WORD *)(a4 + 32) = *(_WORD *)(a1 + 8);
  *(_QWORD *)(a4 + 40) = a3;
  return 0;
}

```

## disassembly

```asm
0x14024fe58  mov     [rsp-40h+arg_10], r8
0x14024fe5d  push    rbp
0x14024fe5e  push    rbx
0x14024fe5f  push    rsi
0x14024fe60  push    rdi
0x14024fe61  push    r12
0x14024fe63  push    r13
0x14024fe65  push    r14
0x14024fe67  push    r15
0x14024fe69  mov     rbp, rsp
0x14024fe6c  sub     rsp, 58h
0x14024fe70  lea     rax, aHttp; "http:"
0x14024fe77  mov     dword ptr [rbp+String2+4], 0
0x14024fe7e  mov     [rbp+String1.Buffer], rax
0x14024fe82  mov     r12, rdx
0x14024fe85  lea     rax, aHttps; "https:"
0x14024fe8c  mov     qword ptr [rbp+String1.Length], 0C000Ah
0x14024fe94  mov     [rbp+var_18.Buffer], rax
0x14024fe98  lea     rdx, [rbp+String2]; String2
0x14024fe9c  mov     rax, [rcx+10h]
0x14024fea0  mov     rdi, rcx
0x14024fea3  mov     [rbp+String2.Buffer], rax
0x14024fea7  mov     bl, 1
0x14024fea9  movzx   eax, word ptr [rcx]
0x14024feac  mov     r8b, bl; CaseInSensitive
0x14024feaf  lea     rcx, [rbp+String1]; String1
0x14024feb3  mov     [rbp+String2.Length], ax
0x14024feb7  mov     [rbp+String2.MaximumLength], ax
0x14024febb  mov     r14, r9
0x14024febe  mov     qword ptr [rbp+var_18.Length], 0E000Ch
0x14024fec6  call    cs:__imp_RtlPrefixUnicodeString
0x14024fecd  nop     dword ptr [rax+rax+00h]
0x14024fed2  test    al, al
0x14024fed4  jz      short loc_14024FEDA
0x14024fed6  xor     al, al
0x14024fed8  jmp     short loc_14024FEFB
0x14024feda  mov     r8b, bl; CaseInSensitive
0x14024fedd  lea     rdx, [rbp+String2]; String2
0x14024fee1  lea     rcx, [rbp+var_18]; String1
0x14024fee5  call    cs:__imp_RtlPrefixUnicodeString
0x14024feec  nop     dword ptr [rax+rax+00h]
0x14024fef1  test    al, al
0x14024fef3  jz      loc_140250024
0x14024fef9  mov     al, bl
0x14024fefb  mov     rcx, r12; Sid
0x14024fefe  mov     [r14+22h], al
0x14024ff02  call    cs:__imp_RtlLengthSid
0x14024ff09  nop     dword ptr [rax+rax+00h]
0x14024ff0e  movzx   edx, word ptr [rdi+4]
0x14024ff12  sub     dx, [rdi+10h]
0x14024ff16  add     dx, [rdi+20h]
0x14024ff1a  movzx   r15d, dx
0x14024ff1e  mov     r13d, eax
0x14024ff21  lea     edx, [r13+7]
0x14024ff25  and     edx, 0FFFFFFF8h
0x14024ff28  add     edx, r15d
0x14024ff2b  cmp     edx, 100h
0x14024ff31  ja      short loc_14024FF48
0x14024ff33  lea     rcx, EQoSHkeAcquireQoSParametersLookaside; Lookaside
0x14024ff3a  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14024ff41  nop     dword ptr [rax+rax+00h]
0x14024ff46  jmp     short loc_14024FF61
0x14024ff48  mov     ecx, 40h ; '@'
0x14024ff4d  mov     r8d, 70485145h
0x14024ff53  call    cs:__imp_ExAllocatePool2
0x14024ff5a  nop     dword ptr [rax+rax+00h]
0x14024ff5f  xor     bl, bl
0x14024ff61  mov     rsi, rax
0x14024ff64  mov     rax, [rbp+arg_20]
0x14024ff68  mov     [rax], bl
0x14024ff6a  test    rsi, rsi
0x14024ff6d  jnz     short loc_14024FF79
0x14024ff6f  mov     eax, 0C000009Ah
0x14024ff74  jmp     loc_140250029
0x14024ff79  mov     r8, r12; SourceSid
0x14024ff7c  mov     rdx, rsi; DestinationSid
0x14024ff7f  mov     ecx, r13d; DestinationSidLength
0x14024ff82  call    cs:__imp_RtlCopySid
0x14024ff89  nop     dword ptr [rax+rax+00h]
0x14024ff8e  mov     [r14+30h], rsi
0x14024ff92  lea     rbx, [r13+7]
0x14024ff96  mov     rdx, [rdi+10h]; Src
0x14024ff9a  and     rbx, 0FFFFFFFFFFFFFFF8h
0x14024ff9e  add     rbx, rsi
0x14024ffa1  mov     r8, r15; Size
0x14024ffa4  mov     rcx, rbx; void *
0x14024ffa7  call    memmove
0x14024ffac  xor     r8d, r8d; AllocateDestinationString
0x14024ffaf  mov     [rbp+String2.Buffer], rbx
0x14024ffb3  lea     rdx, [rbp+String2]; SourceString
0x14024ffb7  mov     [rbp+String2.Length], r15w
0x14024ffbc  lea     rcx, [rbp+String2]; DestinationString
0x14024ffc0  mov     [rbp+String2.MaximumLength], r15w
0x14024ffc5  call    cs:__imp_RtlDowncaseUnicodeString
0x14024ffcc  nop     dword ptr [rax+rax+00h]
0x14024ffd1  mov     rcx, [rdi+18h]
0x14024ffd5  sub     rcx, [rdi+10h]
0x14024ffd9  add     rcx, rbx
0x14024ffdc  mov     [r14+8], rcx
0x14024ffe0  movzx   eax, word ptr [rdi+2]
0x14024ffe4  mov     [r14], ax
0x14024ffe8  movzx   eax, word ptr [rdi+2]
0x14024ffec  mov     [r14+2], ax
0x14024fff1  sub     rbx, [rdi+10h]
0x14024fff5  add     rbx, [rdi+20h]
0x14024fff9  mov     [r14+18h], rbx
0x14024fffd  movzx   eax, word ptr [rdi+4]
0x140250001  mov     [r14+10h], ax
0x140250006  movzx   eax, word ptr [rdi+4]
0x14025000a  mov     [r14+12h], ax
0x14025000f  movzx   eax, word ptr [rdi+8]
0x140250013  mov     [r14+20h], ax
0x140250018  mov     rax, [rbp+arg_10]
0x14025001c  mov     [r14+28h], rax
0x140250020  xor     eax, eax
0x140250022  jmp     short loc_140250029
0x140250024  mov     eax, 0C0000225h
0x140250029  add     rsp, 58h
0x14025002d  pop     r15
0x14025002f  pop     r14
0x140250031  pop     r13
0x140250033  pop     r12
0x140250035  pop     rdi
0x140250036  pop     rsi
0x140250037  pop     rbx
0x140250038  pop     rbp
0x140250039  retn
```
