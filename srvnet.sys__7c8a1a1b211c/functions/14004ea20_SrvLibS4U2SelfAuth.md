# SrvLibS4U2SelfAuth

- ea: `0x14004ea20`
- end: `0x14004ec5d`
- name: `SrvLibS4U2SelfAuth`
- size: `573`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14002a3e0`
- `0x14004ea20`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14004eb2c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14004eb66`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14004eb2c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14004eb66`
- `ntoskrnl!RtlInitAnsiString` at `0x14004eb7d`
- `ntoskrnl!RtlInitAnsiString` at `0x14004eb7d`
- `ntoskrnl!NtAllocateVirtualMemory` at `0x14004eade`
- `ntoskrnl!NtAllocateVirtualMemory` at `0x14004eade`
- `ntoskrnl!LsaLogonUser` at `0x14004ebf5`
- `ntoskrnl!LsaLogonUser` at `0x14004ebf5`
- `ntoskrnl!NtFreeVirtualMemory` at `0x14004ec15`
- `ntoskrnl!NtFreeVirtualMemory` at `0x14004ec15`
- `ntoskrnl!LsaFreeReturnBuffer` at `0x14004ec29`
- `ntoskrnl!LsaFreeReturnBuffer` at `0x14004ec29`

## pseudocode

```c
__int64 __fastcall SrvLibS4U2SelfAuth(
        struct _TOKEN_SOURCE *a1,
        const UNICODE_STRING *a2,
        const UNICODE_STRING *a3,
        void **a4)
{
  int Length; // r14d
  int v5; // eax
  __int64 v7; // rax
  __int16 v8; // r15
  __int64 v9; // r14
  NTSTATUS v14; // edi
  PVOID BaseAddress; // [rsp+70h] [rbp-59h] BYREF
  int SubStatus; // [rsp+78h] [rbp-51h] BYREF
  ULONG ProfileBufferLength; // [rsp+7Ch] [rbp-4Dh] BYREF
  ULONG_PTR RegionSize; // [rsp+80h] [rbp-49h] BYREF
  PVOID Buffer; // [rsp+88h] [rbp-41h] BYREF
  void *Token; // [rsp+90h] [rbp-39h] BYREF
  struct _LUID LogonId; // [rsp+98h] [rbp-31h] BYREF
  struct _STRING DestinationString; // [rsp+A0h] [rbp-29h] BYREF
  struct _QUOTA_LIMITS Quotas; // [rsp+B0h] [rbp-19h] BYREF

  Length = a3->Length;
  v5 = a2->Length + 5;
  *a4 = 0;
  v7 = v5 & 0xFFFFFFFC;
  BaseAddress = 0;
  v8 = v7;
  v9 = (Length + 5) & 0xFFFFFFFC;
  Buffer = 0;
  ProfileBufferLength = 0;
  LogonId = 0;
  RegionSize = v9 + v7 + 48;
  Token = 0;
  SubStatus = 0;
  memset(&Quotas, 0, sizeof(Quotas));
  DestinationString = 0;
  if ( NtAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, 0, &RegionSize, 0x1000u, 4u) < 0 )
    return 3221225626LL;
  *(_DWORD *)BaseAddress = 12;
  *((_WORD *)BaseAddress + 4) = 0;
  *((_WORD *)BaseAddress + 5) = v8;
  *((_QWORD *)BaseAddress + 2) = (char *)BaseAddress + 40;
  RtlCopyUnicodeString((PUNICODE_STRING)((char *)BaseAddress + 8), a2);
  *((_WORD *)BaseAddress + 12) = 0;
  *((_WORD *)BaseAddress + 13) = v9;
  *((_QWORD *)BaseAddress + 4) = *((_QWORD *)BaseAddress + 2) + *((unsigned __int16 *)BaseAddress + 5);
  RtlCopyUnicodeString((PUNICODE_STRING)((char *)BaseAddress + 24), a3);
  RtlInitAnsiString(&DestinationString, "Unspecified");
  v14 = LsaLogonUser(
          *(HANDLE *)a1->SourceName,
          &DestinationString,
          Network,
          a1->SourceIdentifier.HighPart,
          BaseAddress,
          RegionSize,
          0,
          a1 + 1,
          &Buffer,
          &ProfileBufferLength,
          &LogonId,
          &Token,
          &Quotas,
          &SubStatus);
  NtFreeVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, &RegionSize, 0x8000u);
  if ( v14 >= 0 )
  {
    LsaFreeReturnBuffer(Buffer);
    *a4 = Token;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14004ea20  push    rbp
0x14004ea22  push    rbx
0x14004ea23  push    rsi
0x14004ea24  push    rdi
0x14004ea25  push    r12
0x14004ea27  push    r14
0x14004ea29  push    r15
0x14004ea2b  lea     rbp, [rsp-27h]
0x14004ea30  sub     rsp, 0F0h
0x14004ea37  mov     rax, cs:__security_cookie
0x14004ea3e  xor     rax, rsp
0x14004ea41  mov     [rbp+57h+var_40], rax
0x14004ea45  movzx   eax, word ptr [rdx]
0x14004ea48  xorps   xmm0, xmm0
0x14004ea4b  movzx   r14d, word ptr [r8]
0x14004ea4f  add     eax, 5
0x14004ea52  mov     r12, rcx
0x14004ea55  mov     qword ptr [r9], 0
0x14004ea5c  mov     ecx, 0FFFFFFFCh
0x14004ea61  mov     [rsp+120h+Protect], 4; Protect
0x14004ea69  and     eax, ecx
0x14004ea6b  mov     [rbp+57h+BaseAddress], 0
0x14004ea73  mov     r15d, eax
0x14004ea76  add     r14d, 5
0x14004ea7a  and     r14d, ecx
0x14004ea7d  mov     [rbp+57h+Buffer], 0
0x14004ea85  add     rax, 30h ; '0'
0x14004ea89  mov     [rbp+57h+var_A4], 0
0x14004ea90  add     rax, r14
0x14004ea93  mov     qword ptr [rbp+57h+var_88.LowPart], 0
0x14004ea9b  mov     rbx, r9
0x14004ea9e  mov     [rbp+57h+RegionSize], rax
0x14004eaa2  mov     rsi, r8
0x14004eaa5  mov     [rbp+57h+var_90], 0
0x14004eaad  mov     rdi, rdx
0x14004eab0  mov     [rbp+57h+var_A8], 0
0x14004eab7  lea     r9, [rbp+57h+RegionSize]; RegionSize
0x14004eabb  mov     [rsp+120h+AllocationType], 1000h; AllocationType
0x14004eac3  xor     r8d, r8d; ZeroBits
0x14004eac6  lea     rdx, [rbp+57h+BaseAddress]; BaseAddress
0x14004eaca  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14004eace  movups  xmmword ptr [rbp+57h+var_70.PagedPoolLimit], xmm0
0x14004ead2  movups  xmmword ptr [rbp+57h+var_70.MinimumWorkingSetSize], xmm0
0x14004ead6  movups  xmmword ptr [rbp+57h+var_70.PagefileLimit], xmm0
0x14004eada  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14004eade  call    cs:__imp_NtAllocateVirtualMemory
0x14004eae5  nop     dword ptr [rax+rax+00h]
0x14004eaea  test    eax, eax
0x14004eaec  jns     short loc_14004EAF8
0x14004eaee  mov     eax, 0C000009Ah
0x14004eaf3  jmp     loc_14004EC3E
0x14004eaf8  mov     rax, [rbp+57h+BaseAddress]
0x14004eafc  xor     ecx, ecx
0x14004eafe  mov     rdx, rdi; SourceString
0x14004eb01  mov     dword ptr [rax], 0Ch
0x14004eb07  mov     rax, [rbp+57h+BaseAddress]
0x14004eb0b  mov     [rax+8], cx
0x14004eb0f  mov     rax, [rbp+57h+BaseAddress]
0x14004eb13  mov     [rax+0Ah], r15w
0x14004eb18  mov     rcx, [rbp+57h+BaseAddress]
0x14004eb1c  lea     rax, [rcx+28h]
0x14004eb20  mov     [rcx+10h], rax
0x14004eb24  mov     rcx, [rbp+57h+BaseAddress]
0x14004eb28  add     rcx, 8; DestinationString
0x14004eb2c  call    cs:__imp_RtlCopyUnicodeString
0x14004eb33  nop     dword ptr [rax+rax+00h]
0x14004eb38  mov     rax, [rbp+57h+BaseAddress]
0x14004eb3c  xor     ecx, ecx
0x14004eb3e  mov     rdx, rsi; SourceString
0x14004eb41  mov     [rax+18h], cx
0x14004eb45  mov     rax, [rbp+57h+BaseAddress]
0x14004eb49  mov     [rax+1Ah], r14w
0x14004eb4e  mov     rcx, [rbp+57h+BaseAddress]
0x14004eb52  movzx   eax, word ptr [rcx+0Ah]
0x14004eb56  add     rax, [rcx+10h]
0x14004eb5a  mov     [rcx+20h], rax
0x14004eb5e  mov     rcx, [rbp+57h+BaseAddress]
0x14004eb62  add     rcx, 18h; DestinationString
0x14004eb66  call    cs:__imp_RtlCopyUnicodeString
0x14004eb6d  nop     dword ptr [rax+rax+00h]
0x14004eb72  lea     rdx, aUnspecified; "Unspecified"
0x14004eb79  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14004eb7d  call    cs:__imp_RtlInitAnsiString
0x14004eb84  nop     dword ptr [rax+rax+00h]
0x14004eb89  mov     r9d, [r12+0Ch]; AuthenticationPackage
0x14004eb8e  lea     rax, [r12+10h]
0x14004eb93  lea     rcx, [rbp+57h+var_A8]
0x14004eb97  mov     r8d, 3; LogonType
0x14004eb9d  mov     [rsp+120h+SubStatus], rcx; SubStatus
0x14004eba2  lea     rdx, [rbp+57h+DestinationString]; OriginName
0x14004eba6  lea     rcx, [rbp+57h+var_70]
0x14004ebaa  mov     [rsp+120h+Quotas], rcx; Quotas
0x14004ebaf  lea     rcx, [rbp+57h+var_90]
0x14004ebb3  mov     [rsp+120h+Token], rcx; Token
0x14004ebb8  lea     rcx, [rbp+57h+var_88]
0x14004ebbc  mov     [rsp+120h+LogonId], rcx; LogonId
0x14004ebc1  lea     rcx, [rbp+57h+var_A4]
0x14004ebc5  mov     [rsp+120h+ProfileBufferLength], rcx; ProfileBufferLength
0x14004ebca  lea     rcx, [rbp+57h+Buffer]
0x14004ebce  mov     [rsp+120h+ProfileBuffer], rcx; ProfileBuffer
0x14004ebd3  mov     rcx, [r12]; LsaHandle
0x14004ebd7  mov     [rsp+120h+SourceContext], rax; SourceContext
0x14004ebdc  mov     eax, dword ptr [rbp+57h+RegionSize]
0x14004ebdf  mov     [rsp+120h+LocalGroups], 0; LocalGroups
0x14004ebe8  mov     [rsp+120h+Protect], eax; AuthenticationInformationLength
0x14004ebec  mov     rax, [rbp+57h+BaseAddress]
0x14004ebf0  mov     qword ptr [rsp+120h+AllocationType], rax; AuthenticationInformation
0x14004ebf5  call    cs:__imp_LsaLogonUser
0x14004ebfc  nop     dword ptr [rax+rax+00h]
0x14004ec01  mov     r9d, 8000h; FreeType
0x14004ec07  lea     r8, [rbp+57h+RegionSize]; RegionSize
0x14004ec0b  lea     rdx, [rbp+57h+BaseAddress]; BaseAddress
0x14004ec0f  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14004ec13  mov     edi, eax
0x14004ec15  call    cs:__imp_NtFreeVirtualMemory
0x14004ec1c  nop     dword ptr [rax+rax+00h]
0x14004ec21  test    edi, edi
0x14004ec23  js      short loc_14004EC3C
0x14004ec25  mov     rcx, [rbp+57h+Buffer]; Buffer
0x14004ec29  call    cs:__imp_LsaFreeReturnBuffer
0x14004ec30  nop     dword ptr [rax+rax+00h]
0x14004ec35  mov     rcx, [rbp+57h+var_90]
0x14004ec39  mov     [rbx], rcx
0x14004ec3c  mov     eax, edi
0x14004ec3e  mov     rcx, [rbp+57h+var_40]
0x14004ec42  xor     rcx, rsp; StackCookie
0x14004ec45  call    __security_check_cookie
0x14004ec4a  add     rsp, 0F0h
0x14004ec51  pop     r15
0x14004ec53  pop     r14
0x14004ec55  pop     r12
0x14004ec57  pop     rdi
0x14004ec58  pop     rsi
0x14004ec59  pop     rbx
0x14004ec5a  pop     rbp
0x14004ec5b  retn
```
