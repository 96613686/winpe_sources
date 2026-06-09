# TmpTransactionInitialization

- ea: `0x140024610`
- end: `0x140024725`
- name: `TmpTransactionInitialization`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140024080`

## callees

- `0x1400024e0`
- `0x140002940`
- `0x140024610`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140024655`
- `ntoskrnl!RtlInitUnicodeString` at `0x140024655`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140024679`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140024679`
- `ntoskrnl!ObCreateObjectType` at `0x1400246f2`
- `ntoskrnl!ObCreateObjectType` at `0x1400246f2`

## pseudocode

```c
bool TmpTransactionInitialization()
{
  UNICODE_STRING DestinationString; // [rsp+20h] [rbp-49h] BYREF
  _QWORD v2[16]; // [rsp+30h] [rbp-39h] BYREF

  memset(v2, 0, 0x78u);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"TmTx");
  TmpTransactionTypeName.Buffer = 0;
  if ( RtlDuplicateUnicodeString(0, &DestinationString, &TmpTransactionTypeName) < 0 )
    return 0;
  memset(v2, 0, 0x78u);
  LOWORD(v2[0]) = 120;
  v2[8] = &TmpCloseTransaction;
  LODWORD(v2[1]) = 256;
  v2[9] = TmpDeleteTransaction;
  HIDWORD(v2[4]) = 512;
  HIDWORD(v2[5]) = 728;
  *(_OWORD *)((char *)&v2[1] + 4) = TmpTransactionMapping;
  HIDWORD(v2[3]) = 2031743;
  BYTE2(v2[0]) = 8;
  return (int)ObCreateObjectType(&TmpTransactionTypeName, v2, 0, &TmTransactionObjectType) >= 0;
}

```

## disassembly

```asm
0x140024610  mov     [rsp-8+arg_0], rbx
0x140024615  push    rbp
0x140024616  lea     rbp, [rsp-57h]
0x14002461b  sub     rsp, 0C0h
0x140024622  mov     rax, cs:__security_cookie
0x140024629  xor     rax, rsp
0x14002462c  mov     [rbp+57h+var_10], rax
0x140024630  mov     ebx, 78h ; 'x'
0x140024635  lea     rcx, [rbp+57h+var_90]; void *
0x140024639  mov     r8d, ebx; Size
0x14002463c  xor     edx, edx; Val
0x14002463e  call    memset
0x140024643  xorps   xmm0, xmm0
0x140024646  lea     rdx, aTmtx; "TmTx"
0x14002464d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140024651  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140024655  call    cs:__imp_RtlInitUnicodeString
0x14002465c  nop     dword ptr [rax+rax+00h]
0x140024661  lea     r8, TmpTransactionTypeName; StringOut
0x140024668  mov     cs:TmpTransactionTypeName.Buffer, 0
0x140024673  lea     rdx, [rbp+57h+DestinationString]; StringIn
0x140024677  xor     ecx, ecx; Flags
0x140024679  call    cs:__imp_RtlDuplicateUnicodeString
0x140024680  nop     dword ptr [rax+rax+00h]
0x140024685  test    eax, eax
0x140024687  js      short loc_140024705
0x140024689  mov     r8d, ebx; Size
0x14002468c  lea     rcx, [rbp+57h+var_90]; void *
0x140024690  xor     edx, edx; Val
0x140024692  call    memset
0x140024697  movups  xmm0, cs:TmpTransactionMapping
0x14002469e  lea     rax, TmpCloseTransaction
0x1400246a5  mov     [rbp+57h+var_90], bx
0x1400246a9  mov     [rbp+57h+var_50], rax
0x1400246ad  lea     r9, TmTransactionObjectType
0x1400246b4  lea     rax, TmpDeleteTransaction
0x1400246bb  mov     [rbp+57h+var_88], 100h
0x1400246c2  xor     r8d, r8d
0x1400246c5  mov     [rbp+57h+var_48], rax
0x1400246c9  lea     rdx, [rbp+57h+var_90]
0x1400246cd  mov     [rbp+57h+var_6C], 200h
0x1400246d4  lea     rcx, TmpTransactionTypeName
0x1400246db  mov     [rbp+57h+var_64], 2D8h
0x1400246e2  movdqu  [rbp+57h+var_84], xmm0
0x1400246e7  mov     [rbp+57h+var_74], 1F007Fh
0x1400246ee  mov     [rbp+57h+var_8E], 8
0x1400246f2  call    cs:__imp_ObCreateObjectType
0x1400246f9  nop     dword ptr [rax+rax+00h]
0x1400246fe  test    eax, eax
0x140024700  setns   al
0x140024703  jmp     short loc_140024707
0x140024705  xor     al, al
0x140024707  mov     rcx, [rbp+57h+var_10]
0x14002470b  xor     rcx, rsp; StackCookie
0x14002470e  call    __security_check_cookie
0x140024713  mov     rbx, [rsp+0C0h+arg_0]
0x14002471b  add     rsp, 0C0h
0x140024722  pop     rbp
0x140024723  retn
```
