# TmpResourceManagerInitialization

- ea: `0x140024518`
- end: `0x140024609`
- name: `TmpResourceManagerInitialization`
- size: `241`
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

- `ntoskrnl!RtlInitUnicodeString` at `0x14002455d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002455d`
- `ntoskrnl!ObCreateObjectType` at `0x1400245da`
- `ntoskrnl!ObCreateObjectType` at `0x1400245da`

## pseudocode

```c
bool TmpResourceManagerInitialization()
{
  UNICODE_STRING DestinationString; // [rsp+20h] [rbp-49h] BYREF
  _QWORD v2[16]; // [rsp+30h] [rbp-39h] BYREF

  memset(v2, 0, 0x78u);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"TmRm");
  memset(v2, 0, 0x78u);
  LOWORD(v2[0]) = 120;
  v2[7] = &TmpOpenResourceManager;
  LODWORD(v2[1]) = 256;
  v2[8] = TmpCloseResourceManager;
  HIDWORD(v2[4]) = 512;
  v2[9] = TmpDeleteResourceManager;
  HIDWORD(v2[5]) = 24;
  *(struct _GENERIC_MAPPING *)((char *)&v2[1] + 4) = TmpResourceManagerMapping;
  HIDWORD(v2[3]) = 2031743;
  BYTE2(v2[0]) = 24;
  return (int)ObCreateObjectType(&DestinationString, v2, 0, &TmResourceManagerObjectType) >= 0;
}

```

## disassembly

```asm
0x140024518  mov     [rsp-8+arg_0], rbx
0x14002451d  push    rbp
0x14002451e  lea     rbp, [rsp-57h]
0x140024523  sub     rsp, 0C0h
0x14002452a  mov     rax, cs:__security_cookie
0x140024531  xor     rax, rsp
0x140024534  mov     [rbp+57h+var_10], rax
0x140024538  mov     ebx, 78h ; 'x'
0x14002453d  lea     rcx, [rbp+57h+var_90]; void *
0x140024541  mov     r8d, ebx; Size
0x140024544  xor     edx, edx; Val
0x140024546  call    memset
0x14002454b  xorps   xmm0, xmm0
0x14002454e  lea     rdx, aTmrm; "TmRm"
0x140024555  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140024559  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14002455d  call    cs:__imp_RtlInitUnicodeString
0x140024564  nop     dword ptr [rax+rax+00h]
0x140024569  mov     r8d, ebx; Size
0x14002456c  lea     rcx, [rbp+57h+var_90]; void *
0x140024570  xor     edx, edx; Val
0x140024572  call    memset
0x140024577  movups  xmm0, xmmword ptr cs:TmpResourceManagerMapping.GenericRead
0x14002457e  lea     rax, TmpOpenResourceManager
0x140024585  mov     [rbp+57h+var_90], bx
0x140024589  mov     [rbp+57h+var_58], rax
0x14002458d  lea     r9, TmResourceManagerObjectType
0x140024594  lea     rax, TmpCloseResourceManager
0x14002459b  mov     [rbp+57h+var_88], 100h
0x1400245a2  mov     [rbp+57h+var_50], rax
0x1400245a6  lea     rdx, [rbp+57h+var_90]
0x1400245aa  lea     rax, TmpDeleteResourceManager
0x1400245b1  mov     [rbp+57h+var_6C], 200h
0x1400245b8  xor     r8d, r8d
0x1400245bb  mov     [rbp+57h+var_48], rax
0x1400245bf  lea     rcx, [rbp+57h+DestinationString]
0x1400245c3  mov     [rbp+57h+var_64], 18h
0x1400245ca  movdqu  [rbp+57h+var_84], xmm0
0x1400245cf  mov     [rbp+57h+var_74], 1F007Fh
0x1400245d6  mov     [rbp+57h+var_8E], 18h
0x1400245da  call    cs:__imp_ObCreateObjectType
0x1400245e1  nop     dword ptr [rax+rax+00h]
0x1400245e6  test    eax, eax
0x1400245e8  setns   al
0x1400245eb  mov     rcx, [rbp+57h+var_10]
0x1400245ef  xor     rcx, rsp; StackCookie
0x1400245f2  call    __security_check_cookie
0x1400245f7  mov     rbx, [rsp+0C0h+arg_0]
0x1400245ff  add     rsp, 0C0h
0x140024606  pop     rbp
0x140024607  retn
```
