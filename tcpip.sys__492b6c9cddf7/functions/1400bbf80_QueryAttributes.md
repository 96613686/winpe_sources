# QueryAttributes

- ea: `0x1400bbf80`
- end: `0x1400bc222`
- name: `QueryAttributes`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400bba80`

## callees

- `0x1400bbf80`
- `0x1401bf390`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x1400bc207`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x1400bc207`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x1400bc0e4`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x1400bc0e4`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400bc07b`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400bc07b`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1400bc147`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1400bc147`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bbfec`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bc01e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bc054`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bc1c6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bc1f4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bbfec`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bc01e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bc054`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bc1c6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bc1f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bc109`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bc162`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bc19a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bc109`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bc162`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bc19a`
- `ntoskrnl!ExAllocatePool2` at `0x1400bc09a`
- `ntoskrnl!ExAllocatePool2` at `0x1400bc09a`

## pseudocode

```c
__int64 __fastcall QueryAttributes(_QWORD *a1, char a2, _QWORD *a3)
{
  void *Pool2; // rbp
  unsigned int v7; // esi
  unsigned int v8; // ebx
  KIRQL CurrentIrql; // al
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 result; // rax
  unsigned int v13; // edi
  _DWORD v14[4]; // [rsp+30h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString[4]; // [rsp+40h] [rbp-88h] BYREF

  memset(DestinationString, 0, sizeof(DestinationString));
  v14[0] = 0;
  Pool2 = 0;
  *a3 = 0;
  if ( (a2 & 1) != 0 )
  {
    v7 = 100;
    RtlInitUnicodeString(DestinationString, L"EDP://PolicyFlags");
    v8 = 1;
  }
  else
  {
    v8 = 0;
    v7 = 16;
  }
  if ( (a2 & 2) != 0 )
  {
    v7 += 152;
    RtlInitUnicodeString(&DestinationString[v8++], L"EDP://EnterpriseIds");
  }
  if ( (a2 & 4) != 0 )
  {
    v7 += 152;
    RtlInitUnicodeString(&DestinationString[v8++], L"PEDP://IntentEnterpriseId");
  }
  if ( (a2 & 8) != 0 )
  {
    v7 += 84;
    RtlInitUnicodeString(&DestinationString[v8++], L"EDP://EvaluationFlags");
  }
  if ( (a2 & 0x10) != 0 )
  {
    v7 += 152;
    RtlInitUnicodeString(&DestinationString[v8++], L"EDP://ExemptEnterpriseIds");
  }
  while ( 1 )
  {
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0);
    CurrentIrql = KeGetCurrentIrql();
    v10 = 258;
    if ( CurrentIrql > 1u )
      v10 = 66;
    Pool2 = (void *)ExAllocatePool2(v10, v7, 1950576197);
    if ( !Pool2 )
      return 3221225495LL;
    if ( *a1 )
    {
      LODWORD(result) = SeQuerySecurityAttributesToken(*a1, DestinationString, v8, Pool2, v7, v14);
    }
    else
    {
      v11 = a1[3];
      LODWORD(result) = v11
                      ? ZwQuerySecurityAttributesToken(v11, DestinationString, v8, Pool2, v7, v14)
                      : (unsigned int)SeQuerySecurityAttributesTokenAccessInformation(
                                        a1[2],
                                        DestinationString,
                                        v8,
                                        Pool2,
                                        v7,
                                        v14);
    }
    v13 = result;
    if ( (_DWORD)result != -1073741789 )
      break;
    if ( v7 >= v14[0] )
      goto LABEL_24;
    v7 = v14[0];
  }
  if ( (_DWORD)result == -1073741275 )
  {
    ExFreePoolWithTag(Pool2, 0);
    result = 0;
    *a3 = 0;
    return result;
  }
  if ( (int)result < 0 )
  {
LABEL_24:
    ExFreePoolWithTag(Pool2, 0);
    return v13;
  }
  *a3 = Pool2;
  return (unsigned int)result;
}

```

## disassembly

```asm
0x1400bbf80  mov     [rsp+arg_8], rbx
0x1400bbf85  push    rbp
0x1400bbf86  push    rsi
0x1400bbf87  push    rdi
0x1400bbf88  push    r12
0x1400bbf8a  push    r13
0x1400bbf8c  push    r14
0x1400bbf8e  push    r15
0x1400bbf90  sub     rsp, 90h
0x1400bbf97  mov     rax, cs:__security_cookie
0x1400bbf9e  xor     rax, rsp
0x1400bbfa1  mov     [rsp+0C8h+var_48], rax
0x1400bbfa9  mov     r15, r8
0x1400bbfac  mov     edi, edx
0x1400bbfae  mov     r14, rcx
0x1400bbfb1  xor     edx, edx; Val
0x1400bbfb3  mov     r8d, 40h ; '@'; Size
0x1400bbfb9  lea     rcx, [rsp+0C8h+DestinationString]; void *
0x1400bbfbe  call    memset
0x1400bbfc3  xor     r12d, r12d
0x1400bbfc6  mov     [rsp+0C8h+var_98], r12d
0x1400bbfcb  mov     ebp, r12d
0x1400bbfce  mov     [r15], r12
0x1400bbfd1  test    dil, 1
0x1400bbfd5  jz      loc_1400BC179
0x1400bbfdb  lea     rdx, aEdpPolicyflags; "EDP://PolicyFlags"
0x1400bbfe2  mov     esi, 64h ; 'd'
0x1400bbfe7  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x1400bbfec  call    cs:__imp_RtlInitUnicodeString
0x1400bbff3  nop     dword ptr [rax+rax+00h]
0x1400bbff8  mov     ebx, 1
0x1400bbffd  test    dil, 2
0x1400bc001  jz      short loc_1400BC02C
0x1400bc003  mov     eax, ebx
0x1400bc005  lea     rcx, [rsp+0C8h+DestinationString]
0x1400bc00a  shl     rax, 4
0x1400bc00e  lea     rdx, aEdpEnterprisei; "EDP://EnterpriseIds"
0x1400bc015  add     rcx, rax; DestinationString
0x1400bc018  add     esi, 98h
0x1400bc01e  call    cs:__imp_RtlInitUnicodeString
0x1400bc025  nop     dword ptr [rax+rax+00h]
0x1400bc02a  inc     ebx
0x1400bc02c  test    dil, 4
0x1400bc030  jnz     loc_1400BC1AB
0x1400bc036  test    dil, 8
0x1400bc03a  jz      short loc_1400BC062
0x1400bc03c  mov     eax, ebx
0x1400bc03e  lea     rcx, [rsp+0C8h+DestinationString]
0x1400bc043  shl     rax, 4
0x1400bc047  lea     rdx, aEdpEvaluationf; "EDP://EvaluationFlags"
0x1400bc04e  add     rcx, rax; DestinationString
0x1400bc051  add     esi, 54h ; 'T'
0x1400bc054  call    cs:__imp_RtlInitUnicodeString
0x1400bc05b  nop     dword ptr [rax+rax+00h]
0x1400bc060  inc     ebx
0x1400bc062  test    dil, 10h
0x1400bc066  jnz     loc_1400BC1D9
0x1400bc06c  mov     r13d, 42h ; 'B'
0x1400bc072  test    rbp, rbp
0x1400bc075  jnz     loc_1400BC195
0x1400bc07b  call    cs:__imp_KeGetCurrentIrql
0x1400bc082  nop     dword ptr [rax+rax+00h]
0x1400bc087  mov     ecx, 102h
0x1400bc08c  mov     edx, esi
0x1400bc08e  cmp     al, 1
0x1400bc090  mov     r8d, 74436E45h
0x1400bc096  cmova   rcx, r13
0x1400bc09a  call    cs:__imp_ExAllocatePool2
0x1400bc0a1  nop     dword ptr [rax+rax+00h]
0x1400bc0a6  mov     rbp, rax
0x1400bc0a9  test    rax, rax
0x1400bc0ac  jz      loc_1400BC172
0x1400bc0b2  mov     rcx, [r14]
0x1400bc0b5  lea     rax, [rsp+0C8h+var_98]
0x1400bc0ba  mov     [rsp+0C8h+var_A0], rax
0x1400bc0bf  mov     r9, rbp
0x1400bc0c2  mov     [rsp+0C8h+var_A8], esi
0x1400bc0c6  mov     r8d, ebx
0x1400bc0c9  lea     rdx, [rsp+0C8h+DestinationString]
0x1400bc0ce  test    rcx, rcx
0x1400bc0d1  jnz     short loc_1400BC147
0x1400bc0d3  mov     rcx, [r14+18h]
0x1400bc0d7  test    rcx, rcx
0x1400bc0da  jnz     loc_1400BC207
0x1400bc0e0  mov     rcx, [r14+10h]
0x1400bc0e4  call    cs:__imp_SeQuerySecurityAttributesTokenAccessInformation
0x1400bc0eb  nop     dword ptr [rax+rax+00h]
0x1400bc0f0  mov     edi, eax
0x1400bc0f2  cmp     eax, 0C0000023h
0x1400bc0f7  jz      loc_1400BC186
0x1400bc0fd  cmp     eax, 0C0000225h
0x1400bc102  jnz     short loc_1400BC155
0x1400bc104  xor     edx, edx; Tag
0x1400bc106  mov     rcx, rbp; P
0x1400bc109  call    cs:__imp_ExFreePoolWithTag
0x1400bc110  nop     dword ptr [rax+rax+00h]
0x1400bc115  mov     eax, r12d
0x1400bc118  mov     [r15], r12
0x1400bc11b  mov     rcx, [rsp+0C8h+var_48]
0x1400bc123  xor     rcx, rsp; StackCookie
0x1400bc126  call    __security_check_cookie
0x1400bc12b  mov     rbx, [rsp+0C8h+arg_8]
0x1400bc133  add     rsp, 90h
0x1400bc13a  pop     r15
0x1400bc13c  pop     r14
0x1400bc13e  pop     r13
0x1400bc140  pop     r12
0x1400bc142  pop     rdi
0x1400bc143  pop     rsi
0x1400bc144  pop     rbp
0x1400bc145  retn
0x1400bc147  call    cs:__imp_SeQuerySecurityAttributesToken
0x1400bc14e  nop     dword ptr [rax+rax+00h]
0x1400bc153  jmp     short loc_1400BC0F0
0x1400bc155  test    edi, edi
0x1400bc157  jns     loc_1400BC218
0x1400bc15d  xor     edx, edx; Tag
0x1400bc15f  mov     rcx, rbp; P
0x1400bc162  call    cs:__imp_ExFreePoolWithTag
0x1400bc169  nop     dword ptr [rax+rax+00h]
0x1400bc16e  mov     eax, edi
0x1400bc170  jmp     short loc_1400BC11B
0x1400bc172  mov     eax, 0C0000017h
0x1400bc177  jmp     short loc_1400BC11B
0x1400bc179  mov     ebx, r12d
0x1400bc17c  mov     esi, 10h
0x1400bc181  jmp     loc_1400BBFFD
0x1400bc186  mov     eax, [rsp+0C8h+var_98]
0x1400bc18a  cmp     esi, eax
0x1400bc18c  jnb     short loc_1400BC15D
0x1400bc18e  mov     esi, eax
0x1400bc190  jmp     loc_1400BC072
0x1400bc195  xor     edx, edx; Tag
0x1400bc197  mov     rcx, rbp; P
0x1400bc19a  call    cs:__imp_ExFreePoolWithTag
0x1400bc1a1  nop     dword ptr [rax+rax+00h]
0x1400bc1a6  jmp     loc_1400BC07B
0x1400bc1ab  mov     eax, ebx
0x1400bc1ad  lea     rcx, [rsp+0C8h+DestinationString]
0x1400bc1b2  shl     rax, 4
0x1400bc1b6  lea     rdx, aPedpIntentente; "PEDP://IntentEnterpriseId"
0x1400bc1bd  add     rcx, rax; DestinationString
0x1400bc1c0  add     esi, 98h
0x1400bc1c6  call    cs:__imp_RtlInitUnicodeString
0x1400bc1cd  nop     dword ptr [rax+rax+00h]
0x1400bc1d2  inc     ebx
0x1400bc1d4  jmp     loc_1400BC036
0x1400bc1d9  mov     eax, ebx
0x1400bc1db  lea     rcx, [rsp+0C8h+DestinationString]
0x1400bc1e0  shl     rax, 4
0x1400bc1e4  lea     rdx, aEdpExemptenter; "EDP://ExemptEnterpriseIds"
0x1400bc1eb  add     rcx, rax; DestinationString
0x1400bc1ee  add     esi, 98h
0x1400bc1f4  call    cs:__imp_RtlInitUnicodeString
0x1400bc1fb  nop     dword ptr [rax+rax+00h]
0x1400bc200  inc     ebx
0x1400bc202  jmp     loc_1400BC06C
0x1400bc207  call    cs:__imp_ZwQuerySecurityAttributesToken
0x1400bc20e  nop     dword ptr [rax+rax+00h]
0x1400bc213  jmp     loc_1400BC0F0
0x1400bc218  mov     [r15], rbp
0x1400bc21b  mov     eax, edi
0x1400bc21d  jmp     loc_1400BC11B
```
