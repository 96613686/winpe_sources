# TmpTransactionManagerInitialization

- ea: `0x14002472c`
- end: `0x140024825`
- name: `TmpTransactionManagerInitialization`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140024080`

## callees

- `0x1400024e0`
- `0x140002940`
- `0x14002472c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140024771`
- `ntoskrnl!RtlInitUnicodeString` at `0x140024771`
- `ntoskrnl!ObCreateObjectType` at `0x1400247ee`
- `ntoskrnl!ObCreateObjectType` at `0x1400247ee`

## pseudocode

```c
bool TmpTransactionManagerInitialization()
{
  UNICODE_STRING DestinationString; // [rsp+20h] [rbp-49h] BYREF
  _QWORD v2[16]; // [rsp+30h] [rbp-39h] BYREF

  memset(v2, 0, 0x78u);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"TmTm");
  memset(v2, 0, 0x78u);
  BYTE2(v2[0]) = 10;
  v2[7] = TmpOpenTransactionManager;
  LOWORD(v2[0]) = 120;
  v2[8] = TmpCloseTransactionManager;
  LODWORD(v2[1]) = 256;
  v2[9] = TmpDeleteTransactionManager;
  HIDWORD(v2[4]) = 512;
  *(_OWORD *)((char *)&v2[1] + 4) = TmpTransactionManagerMapping;
  HIDWORD(v2[5]) = 960;
  HIDWORD(v2[3]) = 983103;
  return (int)ObCreateObjectType(&DestinationString, v2, 0, &TmTransactionManagerObjectType) >= 0;
}

```

## disassembly

```asm
0x14002472c  mov     [rsp-8+arg_0], rbx
0x140024731  push    rbp
0x140024732  lea     rbp, [rsp-57h]
0x140024737  sub     rsp, 0C0h
0x14002473e  mov     rax, cs:__security_cookie
0x140024745  xor     rax, rsp
0x140024748  mov     [rbp+57h+var_10], rax
0x14002474c  mov     ebx, 78h ; 'x'
0x140024751  lea     rcx, [rbp+57h+var_90]; void *
0x140024755  mov     r8d, ebx; Size
0x140024758  xor     edx, edx; Val
0x14002475a  call    memset
0x14002475f  xorps   xmm0, xmm0
0x140024762  lea     rdx, aTmtm; "TmTm"
0x140024769  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002476d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140024771  call    cs:__imp_RtlInitUnicodeString
0x140024778  nop     dword ptr [rax+rax+00h]
0x14002477d  mov     r8d, ebx; Size
0x140024780  lea     rcx, [rbp+57h+var_90]; void *
0x140024784  xor     edx, edx; Val
0x140024786  call    memset
0x14002478b  movups  xmm0, cs:TmpTransactionManagerMapping
0x140024792  lea     rax, TmpOpenTransactionManager
0x140024799  mov     [rbp+57h+var_8E], 0Ah
0x14002479d  mov     [rbp+57h+var_58], rax
0x1400247a1  lea     r9, TmTransactionManagerObjectType
0x1400247a8  lea     rax, TmpCloseTransactionManager
0x1400247af  mov     [rbp+57h+var_90], bx
0x1400247b3  mov     [rbp+57h+var_50], rax
0x1400247b7  lea     rdx, [rbp+57h+var_90]
0x1400247bb  lea     rax, TmpDeleteTransactionManager
0x1400247c2  mov     [rbp+57h+var_88], 100h
0x1400247c9  xor     r8d, r8d
0x1400247cc  mov     [rbp+57h+var_48], rax
0x1400247d0  lea     rcx, [rbp+57h+DestinationString]
0x1400247d4  mov     [rbp+57h+var_6C], 200h
0x1400247db  movdqu  [rbp+57h+var_84], xmm0
0x1400247e0  mov     [rbp+57h+var_64], 3C0h
0x1400247e7  mov     [rbp+57h+var_74], 0F003Fh
0x1400247ee  call    cs:__imp_ObCreateObjectType
0x1400247f5  nop     dword ptr [rax+rax+00h]
0x1400247fa  test    eax, eax
0x1400247fc  jns     short loc_140024802
0x1400247fe  xor     al, al
0x140024800  jmp     short loc_140024807
0x140024802  shr     eax, 1Fh
0x140024805  xor     al, 1
0x140024807  mov     rcx, [rbp+57h+var_10]
0x14002480b  xor     rcx, rsp; StackCookie
0x14002480e  call    __security_check_cookie
0x140024813  mov     rbx, [rsp+0C0h+arg_0]
0x14002481b  add     rsp, 0C0h
0x140024822  pop     rbp
0x140024823  retn
```
