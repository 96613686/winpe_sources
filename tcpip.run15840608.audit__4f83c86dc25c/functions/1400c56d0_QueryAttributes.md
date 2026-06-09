# QueryAttributes

- ea: `0x1400c56d0`
- end: `0x1400c5972`
- name: `QueryAttributes`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400c51d0`

## callees

- `0x1400c56d0`
- `0x1401c0fd0`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x1400c5957`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x1400c5957`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x1400c5834`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x1400c5834`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400c57cb`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400c57cb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c573c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c576e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c57a4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c5916`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c5944`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c573c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c576e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c57a4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c5916`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c5944`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1400c5897`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1400c5897`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c5859`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c58b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c58ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c5859`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c58b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c58ea`
- `ntoskrnl!ExAllocatePool2` at `0x1400c57ea`
- `ntoskrnl!ExAllocatePool2` at `0x1400c57ea`

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
0x1400c56d0  mov     [rsp+arg_8], rbx
0x1400c56d5  push    rbp
0x1400c56d6  push    rsi
0x1400c56d7  push    rdi
0x1400c56d8  push    r12
0x1400c56da  push    r13
0x1400c56dc  push    r14
0x1400c56de  push    r15
0x1400c56e0  sub     rsp, 90h
0x1400c56e7  mov     rax, cs:__security_cookie
0x1400c56ee  xor     rax, rsp
0x1400c56f1  mov     [rsp+0C8h+var_48], rax
0x1400c56f9  mov     r15, r8
0x1400c56fc  mov     edi, edx
0x1400c56fe  mov     r14, rcx
0x1400c5701  xor     edx, edx; Val
0x1400c5703  mov     r8d, 40h ; '@'; Size
0x1400c5709  lea     rcx, [rsp+0C8h+DestinationString]; void *
0x1400c570e  call    memset
0x1400c5713  xor     r12d, r12d
0x1400c5716  mov     [rsp+0C8h+var_98], r12d
0x1400c571b  mov     ebp, r12d
0x1400c571e  mov     [r15], r12
0x1400c5721  test    dil, 1
0x1400c5725  jz      loc_1400C58C9
0x1400c572b  lea     rdx, aEdpPolicyflags; "EDP://PolicyFlags"
0x1400c5732  mov     esi, 64h ; 'd'
0x1400c5737  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x1400c573c  call    cs:__imp_RtlInitUnicodeString
0x1400c5743  nop     dword ptr [rax+rax+00h]
0x1400c5748  mov     ebx, 1
0x1400c574d  test    dil, 2
0x1400c5751  jz      short loc_1400C577C
0x1400c5753  mov     eax, ebx
0x1400c5755  lea     rcx, [rsp+0C8h+DestinationString]
0x1400c575a  shl     rax, 4
0x1400c575e  lea     rdx, aEdpEnterprisei; "EDP://EnterpriseIds"
0x1400c5765  add     rcx, rax; DestinationString
0x1400c5768  add     esi, 98h
0x1400c576e  call    cs:__imp_RtlInitUnicodeString
0x1400c5775  nop     dword ptr [rax+rax+00h]
0x1400c577a  inc     ebx
0x1400c577c  test    dil, 4
0x1400c5780  jnz     loc_1400C58FB
0x1400c5786  test    dil, 8
0x1400c578a  jz      short loc_1400C57B2
0x1400c578c  mov     eax, ebx
0x1400c578e  lea     rcx, [rsp+0C8h+DestinationString]
0x1400c5793  shl     rax, 4
0x1400c5797  lea     rdx, aEdpEvaluationf; "EDP://EvaluationFlags"
0x1400c579e  add     rcx, rax; DestinationString
0x1400c57a1  add     esi, 54h ; 'T'
0x1400c57a4  call    cs:__imp_RtlInitUnicodeString
0x1400c57ab  nop     dword ptr [rax+rax+00h]
0x1400c57b0  inc     ebx
0x1400c57b2  test    dil, 10h
0x1400c57b6  jnz     loc_1400C5929
0x1400c57bc  mov     r13d, 42h ; 'B'
0x1400c57c2  test    rbp, rbp
0x1400c57c5  jnz     loc_1400C58E5
0x1400c57cb  call    cs:__imp_KeGetCurrentIrql
0x1400c57d2  nop     dword ptr [rax+rax+00h]
0x1400c57d7  mov     ecx, 102h
0x1400c57dc  mov     edx, esi
0x1400c57de  cmp     al, 1
0x1400c57e0  mov     r8d, 74436E45h
0x1400c57e6  cmova   rcx, r13
0x1400c57ea  call    cs:__imp_ExAllocatePool2
0x1400c57f1  nop     dword ptr [rax+rax+00h]
0x1400c57f6  mov     rbp, rax
0x1400c57f9  test    rax, rax
0x1400c57fc  jz      loc_1400C58C2
0x1400c5802  mov     rcx, [r14]
0x1400c5805  lea     rax, [rsp+0C8h+var_98]
0x1400c580a  mov     [rsp+0C8h+var_A0], rax
0x1400c580f  mov     r9, rbp
0x1400c5812  mov     [rsp+0C8h+var_A8], esi
0x1400c5816  mov     r8d, ebx
0x1400c5819  lea     rdx, [rsp+0C8h+DestinationString]
0x1400c581e  test    rcx, rcx
0x1400c5821  jnz     short loc_1400C5897
0x1400c5823  mov     rcx, [r14+18h]
0x1400c5827  test    rcx, rcx
0x1400c582a  jnz     loc_1400C5957
0x1400c5830  mov     rcx, [r14+10h]
0x1400c5834  call    cs:__imp_SeQuerySecurityAttributesTokenAccessInformation
0x1400c583b  nop     dword ptr [rax+rax+00h]
0x1400c5840  mov     edi, eax
0x1400c5842  cmp     eax, 0C0000023h
0x1400c5847  jz      loc_1400C58D6
0x1400c584d  cmp     eax, 0C0000225h
0x1400c5852  jnz     short loc_1400C58A5
0x1400c5854  xor     edx, edx; Tag
0x1400c5856  mov     rcx, rbp; P
0x1400c5859  call    cs:__imp_ExFreePoolWithTag
0x1400c5860  nop     dword ptr [rax+rax+00h]
0x1400c5865  mov     eax, r12d
0x1400c5868  mov     [r15], r12
0x1400c586b  mov     rcx, [rsp+0C8h+var_48]
0x1400c5873  xor     rcx, rsp; StackCookie
0x1400c5876  call    __security_check_cookie
0x1400c587b  mov     rbx, [rsp+0C8h+arg_8]
0x1400c5883  add     rsp, 90h
0x1400c588a  pop     r15
0x1400c588c  pop     r14
0x1400c588e  pop     r13
0x1400c5890  pop     r12
0x1400c5892  pop     rdi
0x1400c5893  pop     rsi
0x1400c5894  pop     rbp
0x1400c5895  retn
0x1400c5897  call    cs:__imp_SeQuerySecurityAttributesToken
0x1400c589e  nop     dword ptr [rax+rax+00h]
0x1400c58a3  jmp     short loc_1400C5840
0x1400c58a5  test    edi, edi
0x1400c58a7  jns     loc_1400C5968
0x1400c58ad  xor     edx, edx; Tag
0x1400c58af  mov     rcx, rbp; P
0x1400c58b2  call    cs:__imp_ExFreePoolWithTag
0x1400c58b9  nop     dword ptr [rax+rax+00h]
0x1400c58be  mov     eax, edi
0x1400c58c0  jmp     short loc_1400C586B
0x1400c58c2  mov     eax, 0C0000017h
0x1400c58c7  jmp     short loc_1400C586B
0x1400c58c9  mov     ebx, r12d
0x1400c58cc  mov     esi, 10h
0x1400c58d1  jmp     loc_1400C574D
0x1400c58d6  mov     eax, [rsp+0C8h+var_98]
0x1400c58da  cmp     esi, eax
0x1400c58dc  jnb     short loc_1400C58AD
0x1400c58de  mov     esi, eax
0x1400c58e0  jmp     loc_1400C57C2
0x1400c58e5  xor     edx, edx; Tag
0x1400c58e7  mov     rcx, rbp; P
0x1400c58ea  call    cs:__imp_ExFreePoolWithTag
0x1400c58f1  nop     dword ptr [rax+rax+00h]
0x1400c58f6  jmp     loc_1400C57CB
0x1400c58fb  mov     eax, ebx
0x1400c58fd  lea     rcx, [rsp+0C8h+DestinationString]
0x1400c5902  shl     rax, 4
0x1400c5906  lea     rdx, aPedpIntentente; "PEDP://IntentEnterpriseId"
0x1400c590d  add     rcx, rax; DestinationString
0x1400c5910  add     esi, 98h
0x1400c5916  call    cs:__imp_RtlInitUnicodeString
0x1400c591d  nop     dword ptr [rax+rax+00h]
0x1400c5922  inc     ebx
0x1400c5924  jmp     loc_1400C5786
0x1400c5929  mov     eax, ebx
0x1400c592b  lea     rcx, [rsp+0C8h+DestinationString]
0x1400c5930  shl     rax, 4
0x1400c5934  lea     rdx, aEdpExemptenter; "EDP://ExemptEnterpriseIds"
0x1400c593b  add     rcx, rax; DestinationString
0x1400c593e  add     esi, 98h
0x1400c5944  call    cs:__imp_RtlInitUnicodeString
0x1400c594b  nop     dword ptr [rax+rax+00h]
0x1400c5950  inc     ebx
0x1400c5952  jmp     loc_1400C57BC
0x1400c5957  call    cs:__imp_ZwQuerySecurityAttributesToken
0x1400c595e  nop     dword ptr [rax+rax+00h]
0x1400c5963  jmp     loc_1400C5840
0x1400c5968  mov     [r15], rbp
0x1400c596b  mov     eax, edi
0x1400c596d  jmp     loc_1400C586B
```
