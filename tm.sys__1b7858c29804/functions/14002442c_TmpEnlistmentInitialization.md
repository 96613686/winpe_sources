# TmpEnlistmentInitialization

- ea: `0x14002442c`
- end: `0x140024512`
- name: `TmpEnlistmentInitialization`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140024080`

## callees

- `0x1400024e0`
- `0x140002940`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140024471`
- `ntoskrnl!RtlInitUnicodeString` at `0x140024471`
- `ntoskrnl!ObCreateObjectType` at `0x1400244e3`
- `ntoskrnl!ObCreateObjectType` at `0x1400244e3`

## pseudocode

```c
bool TmpEnlistmentInitialization()
{
  UNICODE_STRING DestinationString; // [rsp+20h] [rbp-49h] BYREF
  _QWORD v2[16]; // [rsp+30h] [rbp-39h] BYREF

  memset(v2, 0, 0x78u);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"TmEn");
  memset(v2, 0, 0x78u);
  LOWORD(v2[0]) = 120;
  v2[8] = &TmpCloseEnlistment;
  LODWORD(v2[1]) = 256;
  v2[9] = TmpDeleteEnlistment;
  HIDWORD(v2[4]) = 512;
  HIDWORD(v2[5]) = 24;
  *(_OWORD *)((char *)&v2[1] + 4) = TmpEnlistmentMapping;
  HIDWORD(v2[3]) = 983071;
  BYTE2(v2[0]) = 8;
  return (int)ObCreateObjectType(&DestinationString, v2, 0, &TmEnlistmentObjectType) >= 0;
}

```

## disassembly

```asm
0x14002442c  mov     [rsp-8+arg_0], rbx
0x140024431  push    rbp
0x140024432  lea     rbp, [rsp-57h]
0x140024437  sub     rsp, 0C0h
0x14002443e  mov     rax, cs:__security_cookie
0x140024445  xor     rax, rsp
0x140024448  mov     [rbp+57h+var_10], rax
0x14002444c  mov     ebx, 78h ; 'x'
0x140024451  lea     rcx, [rbp+57h+var_90]; void *
0x140024455  mov     r8d, ebx; Size
0x140024458  xor     edx, edx; Val
0x14002445a  call    memset
0x14002445f  xorps   xmm0, xmm0
0x140024462  lea     rdx, aTmen; "TmEn"
0x140024469  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002446d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140024471  call    cs:__imp_RtlInitUnicodeString
0x140024478  nop     dword ptr [rax+rax+00h]
0x14002447d  mov     r8d, ebx; Size
0x140024480  lea     rcx, [rbp+57h+var_90]; void *
0x140024484  xor     edx, edx; Val
0x140024486  call    memset
0x14002448b  movups  xmm0, cs:TmpEnlistmentMapping
0x140024492  lea     rax, TmpCloseEnlistment
0x140024499  mov     [rbp+57h+var_90], bx
0x14002449d  mov     [rbp+57h+var_50], rax
0x1400244a1  lea     r9, TmEnlistmentObjectType
0x1400244a8  lea     rax, TmpDeleteEnlistment
0x1400244af  mov     [rbp+57h+var_88], 100h
0x1400244b6  xor     r8d, r8d
0x1400244b9  mov     [rbp+57h+var_48], rax
0x1400244bd  lea     rdx, [rbp+57h+var_90]
0x1400244c1  mov     [rbp+57h+var_6C], 200h
0x1400244c8  lea     rcx, [rbp+57h+DestinationString]
0x1400244cc  mov     [rbp+57h+var_64], 18h
0x1400244d3  movdqu  [rbp+57h+var_84], xmm0
0x1400244d8  mov     [rbp+57h+var_74], 0F001Fh
0x1400244df  mov     [rbp+57h+var_8E], 8
0x1400244e3  call    cs:__imp_ObCreateObjectType
0x1400244ea  nop     dword ptr [rax+rax+00h]
0x1400244ef  test    eax, eax
0x1400244f1  setns   al
0x1400244f4  mov     rcx, [rbp+57h+var_10]
0x1400244f8  xor     rcx, rsp; StackCookie
0x1400244fb  call    __security_check_cookie
0x140024500  mov     rbx, [rsp+0C0h+arg_0]
0x140024508  add     rsp, 0C0h
0x14002450f  pop     rbp
0x140024510  retn
```
