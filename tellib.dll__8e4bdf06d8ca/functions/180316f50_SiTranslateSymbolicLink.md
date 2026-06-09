# SiTranslateSymbolicLink

- ea: `0x180316f50`
- end: `0x18031714f`
- name: `SiTranslateSymbolicLink`
- size: `511`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180315c14`
- `0x180316430`
- `0x180318120`

## callees

- `0x180316f50`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180317038`
- `ntdll!RtlFreeHeap` at `0x18031712b`
- `ntdll!RtlFreeHeap` at `0x180317038`
- `ntdll!RtlFreeHeap` at `0x18031712b`
- `ntdll!NtClose` at `0x180317080`
- `ntdll!NtClose` at `0x180317102`
- `ntdll!NtClose` at `0x180317080`
- `ntdll!NtClose` at `0x180317102`
- `ntdll!RtlInitUnicodeString` at `0x180316f97`
- `ntdll!RtlInitUnicodeString` at `0x180316feb`
- `ntdll!RtlInitUnicodeString` at `0x180316f97`
- `ntdll!RtlInitUnicodeString` at `0x180316feb`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180316fd1`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1803170d7`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180316fd1`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1803170d7`
- `ntdll!NtQuerySymbolicLinkObject` at `0x18031700a`
- `ntdll!NtQuerySymbolicLinkObject` at `0x18031700a`
- `ntdll!RtlAllocateHeap` at `0x180317060`
- `ntdll!RtlAllocateHeap` at `0x180317060`

## pseudocode

```c
NTSTATUS __fastcall SiTranslateSymbolicLink(PCWSTR SourceString, PWSTR *a2)
{
  NTSTATUS result; // eax
  USHORT v4; // di
  NTSTATUS v5; // ebx
  struct _UNICODE_STRING LinkTarget; // [rsp+20h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  ULONG DataWritten; // [rsp+A0h] [rbp+30h] BYREF
  void *SymbolicLinkHandle; // [rsp+A8h] [rbp+38h] BYREF

  *(_QWORD *)&LinkTarget.Length = 0;
  DataWritten = 0;
  SymbolicLinkHandle = 0;
  LinkTarget.Buffer = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&LinkTarget, 0);
    v4 = 0;
    DataWritten = 0;
    do
    {
      while ( 1 )
      {
        v5 = NtQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, &DataWritten);
        if ( v5 != -1073741789 )
          break;
        if ( LinkTarget.Buffer )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, LinkTarget.Buffer);
        LinkTarget.MaximumLength = DataWritten;
        v4 = DataWritten + 2;
        LinkTarget.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, DataWritten + 2);
        if ( !LinkTarget.Buffer )
        {
          v5 = -1073741670;
          goto LABEL_11;
        }
      }
      NtClose(SymbolicLinkHandle);
      SymbolicLinkHandle = 0;
      if ( v5 < 0 )
        goto LABEL_13;
      LinkTarget.Buffer[(unsigned __int64)LinkTarget.Length >> 1] = 0;
      ObjectAttributes.ObjectName = &LinkTarget;
      LinkTarget.MaximumLength = v4;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    }
    while ( NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes) >= 0 );
    v5 = 0;
    *a2 = LinkTarget.Buffer;
    LinkTarget.Buffer = 0;
LABEL_11:
    if ( SymbolicLinkHandle )
    {
      NtClose(SymbolicLinkHandle);
      SymbolicLinkHandle = 0;
    }
LABEL_13:
    if ( LinkTarget.Buffer )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, LinkTarget.Buffer);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180316f50  mov     [rsp-18h+arg_0], rbx
0x180316f55  mov     [rsp-18h+arg_8], rsi
0x180316f5a  push    rbp
0x180316f5b  push    rdi
0x180316f5c  push    r14
0x180316f5e  mov     rbp, rsp
0x180316f61  sub     rsp, 70h
0x180316f65  xorps   xmm0, xmm0
0x180316f68  xor     r14d, r14d
0x180316f6b  mov     rsi, rdx
0x180316f6e  mov     qword ptr [rbp+LinkTarget.Length], r14
0x180316f72  mov     rdx, rcx; SourceString
0x180316f75  mov     [rbp+DataWritten], r14d
0x180316f79  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180316f7d  lea     rcx, [rbp+DestinationString]; DestinationString
0x180316f81  mov     [rbp+SymbolicLinkHandle], r14
0x180316f85  xor     eax, eax
0x180316f87  mov     [rbp+LinkTarget.Buffer], r14
0x180316f8b  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180316f8f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180316f93  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180316f97  call    cs:__imp_RtlInitUnicodeString
0x180316f9e  nop     dword ptr [rax+rax+00h]
0x180316fa3  lea     rax, [rbp+DestinationString]
0x180316fa7  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180316fae  xorps   xmm0, xmm0
0x180316fb1  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180316fb5  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180316fb9  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x180316fbd  lea     edx, [r14+1]; DesiredAccess
0x180316fc1  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180316fc8  lea     rcx, [rbp+SymbolicLinkHandle]; SymbolicLinkHandle
0x180316fcc  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180316fd1  call    cs:__imp_NtOpenSymbolicLinkObject
0x180316fd8  nop     dword ptr [rax+rax+00h]
0x180316fdd  test    eax, eax
0x180316fdf  js      loc_180317139
0x180316fe5  xor     edx, edx; SourceString
0x180316fe7  lea     rcx, [rbp+LinkTarget]; DestinationString
0x180316feb  call    cs:__imp_RtlInitUnicodeString
0x180316ff2  nop     dword ptr [rax+rax+00h]
0x180316ff7  mov     edi, r14d
0x180316ffa  mov     [rbp+DataWritten], r14d
0x180316ffe  mov     rcx, [rbp+SymbolicLinkHandle]; SymLinkObjHandle
0x180317002  lea     r8, [rbp+DataWritten]; DataWritten
0x180317006  lea     rdx, [rbp+LinkTarget]; LinkTarget
0x18031700a  call    cs:__imp_NtQuerySymbolicLinkObject
0x180317011  nop     dword ptr [rax+rax+00h]
0x180317016  mov     ebx, eax
0x180317018  cmp     eax, 0C0000023h
0x18031701d  jnz     short loc_18031707C
0x18031701f  cmp     [rbp+LinkTarget.Buffer], r14
0x180317023  jz      short loc_180317044
0x180317025  mov     rcx, gs:60h
0x18031702e  xor     edx, edx; Flags
0x180317030  mov     r8, [rbp+LinkTarget.Buffer]; P
0x180317034  mov     rcx, [rcx+30h]; HeapHandle
0x180317038  call    cs:__imp_RtlFreeHeap
0x18031703f  nop     dword ptr [rax+rax+00h]
0x180317044  mov     eax, [rbp+DataWritten]
0x180317047  xor     edx, edx; Flags
0x180317049  mov     [rbp+LinkTarget.MaximumLength], ax
0x18031704d  mov     rcx, gs:60h
0x180317056  lea     edi, [rax+2]
0x180317059  mov     r8d, edi; Size
0x18031705c  mov     rcx, [rcx+30h]; HeapHandle
0x180317060  call    cs:__imp_RtlAllocateHeap
0x180317067  nop     dword ptr [rax+rax+00h]
0x18031706c  mov     [rbp+LinkTarget.Buffer], rax
0x180317070  test    rax, rax
0x180317073  jnz     short loc_180316FFE
0x180317075  mov     ebx, 0C000009Ah
0x18031707a  jmp     short loc_1803170F9
0x18031707c  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x180317080  call    cs:__imp_NtClose
0x180317087  nop     dword ptr [rax+rax+00h]
0x18031708c  mov     [rbp+SymbolicLinkHandle], r14
0x180317090  test    ebx, ebx
0x180317092  js      short loc_180317112
0x180317094  movzx   edx, [rbp+LinkTarget.Length]
0x180317098  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18031709c  mov     rax, [rbp+LinkTarget.Buffer]
0x1803170a0  lea     rcx, [rbp+SymbolicLinkHandle]; SymbolicLinkHandle
0x1803170a4  shr     rdx, 1
0x1803170a7  xorps   xmm0, xmm0
0x1803170aa  mov     [rax+rdx*2], r14w
0x1803170af  lea     rax, [rbp+LinkTarget]
0x1803170b3  mov     edx, 1; DesiredAccess
0x1803170b8  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1803170bc  mov     [rbp+LinkTarget.MaximumLength], di
0x1803170c0  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1803170c7  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x1803170cb  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1803170d2  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1803170d7  call    cs:__imp_NtOpenSymbolicLinkObject
0x1803170de  nop     dword ptr [rax+rax+00h]
0x1803170e3  test    eax, eax
0x1803170e5  jns     loc_180316FFE
0x1803170eb  mov     rax, [rbp+LinkTarget.Buffer]
0x1803170ef  mov     ebx, r14d
0x1803170f2  mov     [rsi], rax
0x1803170f5  mov     [rbp+LinkTarget.Buffer], r14
0x1803170f9  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x1803170fd  test    rcx, rcx
0x180317100  jz      short loc_180317112
0x180317102  call    cs:__imp_NtClose
0x180317109  nop     dword ptr [rax+rax+00h]
0x18031710e  mov     [rbp+SymbolicLinkHandle], r14
0x180317112  cmp     [rbp+LinkTarget.Buffer], r14
0x180317116  jz      short loc_180317137
0x180317118  mov     rcx, gs:60h
0x180317121  xor     edx, edx; Flags
0x180317123  mov     r8, [rbp+LinkTarget.Buffer]; P
0x180317127  mov     rcx, [rcx+30h]; HeapHandle
0x18031712b  call    cs:__imp_RtlFreeHeap
0x180317132  nop     dword ptr [rax+rax+00h]
0x180317137  mov     eax, ebx
0x180317139  lea     r11, [rsp+70h+var_s0]
0x18031713e  mov     rbx, [r11+20h]
0x180317142  mov     rsi, [r11+28h]
0x180317146  mov     rsp, r11
0x180317149  pop     r14
0x18031714b  pop     rdi
0x18031714c  pop     rbp
0x18031714d  retn
```
