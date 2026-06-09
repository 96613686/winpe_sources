# SmbCompressionReadCompressionAlgorithmSuiteOrderPolicySetting

- ea: `0x140020fc0`
- end: `0x140021113`
- name: `SmbCompressionReadCompressionAlgorithmSuiteOrderPolicySetting`
- size: `339`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140020e70`
- `0x140020fc0`
- `0x14002a3e0`
- `0x14002a4c0`
- `0x14002a540`
- `0x14002a840`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1400210e5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400210e5`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140021070`
- `ntoskrnl!RtlInitUnicodeString` at `0x140021041`
- `ntoskrnl!RtlInitUnicodeString` at `0x140021041`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140021051`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140021051`

## string_xrefs

- `0x140021006`: `RtlQueryRegistryValuesEx`
- `0x14002101f`: `CompressionAlgorithmSuiteOrder`

## pseudocode

```c
__int64 __fastcall SmbCompressionReadCompressionAlgorithmSuiteOrderPolicySetting(
        __int64 a1,
        void *a2,
        unsigned __int16 *a3)
{
  PVOID SystemRoutineAddress; // rax
  int v7; // eax
  int v8; // ebx
  unsigned __int16 v9; // bx
  unsigned __int16 v11; // [rsp+30h] [rbp-79h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+38h] [rbp-71h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-61h] BYREF
  _QWORD v14[14]; // [rsp+60h] [rbp-49h] BYREF
  __int128 Src; // [rsp+D0h] [rbp+27h] BYREF
  int v16; // [rsp+E0h] [rbp+37h]

  memset(v14, 0, sizeof(v14));
  LODWORD(v14[1]) = 304;
  v16 = 0;
  v11 = 0;
  LODWORD(v14[4]) = 117440512;
  v14[2] = L"CompressionAlgorithmSuiteOrder";
  v14[3] = &UnicodeString;
  UnicodeString = 0;
  Src = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  v7 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(0, a1, v14, 0, 0);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( !UnicodeString.Buffer )
    {
      v8 = -1073741772;
      goto LABEL_11;
    }
    v8 = SmbCompressionParseAlgorithmSuiteOrder(&Src, &v11, UnicodeString.Buffer, UnicodeString.Length);
    if ( v8 < 0 )
      goto LABEL_11;
    v9 = v11;
    if ( v11 )
    {
      memmove(a2, &Src, 4LL * v11);
      *a3 = v9;
      v8 = 0;
      goto LABEL_11;
    }
    goto LABEL_5;
  }
  if ( v7 == -1073741788 )
LABEL_5:
    v8 = -1073739509;
LABEL_11:
  RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140020fc0  mov     [rsp-8+arg_18], rbx
0x140020fc5  push    rbp
0x140020fc6  push    rsi
0x140020fc7  push    rdi
0x140020fc8  lea     rbp, [rsp-47h]
0x140020fcd  sub     rsp, 0F0h
0x140020fd4  mov     rax, cs:__security_cookie
0x140020fdb  xor     rax, rsp
0x140020fde  mov     [rbp+57h+var_18], rax
0x140020fe2  mov     rdi, rdx
0x140020fe5  mov     rsi, r8
0x140020fe8  xor     edx, edx; Val
0x140020fea  mov     rbx, rcx
0x140020fed  lea     rcx, [rbp+57h+var_A0]; void *
0x140020ff1  lea     r8d, [rdx+70h]; Size
0x140020ff5  call    memset
0x140020ffa  xor     eax, eax
0x140020ffc  mov     [rbp+57h+var_98], 130h
0x140021003  mov     [rbp+57h+var_20], eax
0x140021006  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x14002100d  mov     [rbp+57h+var_D0], ax
0x140021011  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140021015  xorps   xmm0, xmm0
0x140021018  mov     [rbp+57h+var_80], 7000000h
0x14002101f  lea     rax, aCompressionalg; "CompressionAlgorithmSuiteOrder"
0x140021026  xorps   xmm1, xmm1
0x140021029  mov     [rbp+57h+var_90], rax
0x14002102d  lea     rax, [rbp+57h+UnicodeString]
0x140021031  mov     [rbp+57h+var_88], rax
0x140021035  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x140021039  movups  [rbp+57h+Src], xmm1
0x14002103d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140021041  call    cs:__imp_RtlInitUnicodeString
0x140021048  nop     dword ptr [rax+rax+00h]
0x14002104d  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x140021051  call    cs:__imp_MmGetSystemRoutineAddress
0x140021058  nop     dword ptr [rax+rax+00h]
0x14002105d  lea     r8, [rbp+57h+var_A0]
0x140021061  mov     [rsp+100h+var_E0], 0
0x14002106a  test    rax, rax
0x14002106d  mov     rdx, rbx
0x140021070  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140021078  xor     r9d, r9d
0x14002107b  xor     ecx, ecx
0x14002107d  call    _guard_dispatch_icall
0x140021082  mov     ebx, eax
0x140021084  test    eax, eax
0x140021086  jns     short loc_140021096
0x140021088  cmp     eax, 0C0000024h
0x14002108d  jnz     short loc_1400210E1
0x14002108f  mov     ebx, 0C000090Bh
0x140021094  jmp     short loc_1400210E1
0x140021096  mov     r8, [rbp+57h+UnicodeString.Buffer]
0x14002109a  test    r8, r8
0x14002109d  jnz     short loc_1400210A6
0x14002109f  mov     ebx, 0C0000034h
0x1400210a4  jmp     short loc_1400210E1
0x1400210a6  movzx   r9d, [rbp+57h+UnicodeString.Length]
0x1400210ab  lea     rdx, [rbp+57h+var_D0]
0x1400210af  lea     rcx, [rbp+57h+Src]
0x1400210b3  call    SmbCompressionParseAlgorithmSuiteOrder
0x1400210b8  mov     ebx, eax
0x1400210ba  test    eax, eax
0x1400210bc  js      short loc_1400210E1
0x1400210be  movzx   ebx, [rbp+57h+var_D0]
0x1400210c2  xor     eax, eax
0x1400210c4  cmp     ax, bx
0x1400210c7  jz      short loc_14002108F
0x1400210c9  mov     r8d, ebx
0x1400210cc  lea     rdx, [rbp+57h+Src]; Src
0x1400210d0  shl     r8, 2; Size
0x1400210d4  mov     rcx, rdi; void *
0x1400210d7  call    memmove
0x1400210dc  mov     [rsi], bx
0x1400210df  xor     ebx, ebx
0x1400210e1  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x1400210e5  call    cs:__imp_RtlFreeUnicodeString
0x1400210ec  nop     dword ptr [rax+rax+00h]
0x1400210f1  mov     eax, ebx
0x1400210f3  mov     rcx, [rbp+57h+var_18]
0x1400210f7  xor     rcx, rsp; StackCookie
0x1400210fa  call    __security_check_cookie
0x1400210ff  mov     rbx, [rsp+100h+arg_18]
0x140021107  add     rsp, 0F0h
0x14002110e  pop     rdi
0x14002110f  pop     rsi
0x140021110  pop     rbp
0x140021111  retn
```
