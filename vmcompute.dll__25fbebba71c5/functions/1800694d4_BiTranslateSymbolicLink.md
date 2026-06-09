# BiTranslateSymbolicLink

- ea: `0x1800694d4`
- end: `0x1800696cd`
- name: `BiTranslateSymbolicLink`
- size: `505`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `4`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180068264`
- `0x18006892c`
- `0x18006bca8`
- `0x18006c0f4`

## callees

- `0x1800694d4`

## import_xrefs

- `ntdll!ZwClose` at `0x1800695fd`
- `ntdll!ZwClose` at `0x18006967d`
- `ntdll!ZwClose` at `0x1800695fd`
- `ntdll!ZwClose` at `0x18006967d`
- `ntdll!ZwQuerySymbolicLinkObject` at `0x1800695e4`
- `ntdll!ZwQuerySymbolicLinkObject` at `0x1800695e4`
- `ntdll!ZwOpenSymbolicLinkObject` at `0x180069550`
- `ntdll!ZwOpenSymbolicLinkObject` at `0x180069657`
- `ntdll!ZwOpenSymbolicLinkObject` at `0x180069550`
- `ntdll!ZwOpenSymbolicLinkObject` at `0x180069657`
- `ntdll!RtlAllocateHeap` at `0x1800695bf`
- `ntdll!RtlAllocateHeap` at `0x1800695bf`
- `ntdll!RtlFreeHeap` at `0x180069597`
- `ntdll!RtlFreeHeap` at `0x1800696a7`
- `ntdll!RtlFreeHeap` at `0x180069597`
- `ntdll!RtlFreeHeap` at `0x1800696a7`
- `ntdll!RtlInitUnicodeString` at `0x180069511`
- `ntdll!RtlInitUnicodeString` at `0x18006956a`
- `ntdll!RtlInitUnicodeString` at `0x180069511`
- `ntdll!RtlInitUnicodeString` at `0x18006956a`

## pseudocode

```c
NTSTATUS __fastcall BiTranslateSymbolicLink(PCWSTR SourceString, PWSTR *a2)
{
  NTSTATUS result; // eax
  USHORT v4; // di
  NTSTATUS v5; // ebx
  struct _UNICODE_STRING LinkTarget; // [rsp+20h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  ULONG ReturnedLength; // [rsp+A0h] [rbp+30h] BYREF
  void *SymbolicLinkHandle; // [rsp+A8h] [rbp+38h] BYREF

  ReturnedLength = 0;
  *(_QWORD *)&LinkTarget.Length = 0;
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
  result = ZwOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&LinkTarget, 0);
    v4 = 0;
    ReturnedLength = 0;
    do
    {
      while ( 1 )
      {
        v5 = ZwQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, &ReturnedLength);
        if ( v5 == -1073741789 )
          break;
        ZwClose(SymbolicLinkHandle);
        SymbolicLinkHandle = 0;
        if ( v5 < 0 )
          goto LABEL_13;
        LinkTarget.Buffer[(unsigned __int64)LinkTarget.Length >> 1] = 0;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.ObjectName = &LinkTarget;
        LinkTarget.MaximumLength = v4;
        ObjectAttributes.Length = 48;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( ZwOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes) < 0 )
        {
          v5 = 0;
          *a2 = LinkTarget.Buffer;
          goto LABEL_10;
        }
      }
      if ( LinkTarget.Buffer )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, LinkTarget.Buffer);
      LinkTarget.MaximumLength = ReturnedLength;
      v4 = ReturnedLength + 2;
      LinkTarget.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, ReturnedLength + 2);
    }
    while ( LinkTarget.Buffer );
    v5 = -1073741670;
LABEL_10:
    if ( SymbolicLinkHandle )
      ZwClose(SymbolicLinkHandle);
    if ( v5 < 0 )
    {
LABEL_13:
      if ( LinkTarget.Buffer )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, LinkTarget.Buffer);
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800694d4  mov     [rsp-18h+arg_0], rbx
0x1800694d9  push    rbp
0x1800694da  push    rsi
0x1800694db  push    rdi
0x1800694dc  mov     rbp, rsp
0x1800694df  sub     rsp, 70h
0x1800694e3  xorps   xmm0, xmm0
0x1800694e6  xor     eax, eax
0x1800694e8  mov     rsi, rdx
0x1800694eb  mov     [rbp+ReturnedLength], eax
0x1800694ee  mov     rdx, rcx; SourceString
0x1800694f1  mov     qword ptr [rbp+LinkTarget.Length], rax
0x1800694f5  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800694f9  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800694fd  mov     [rbp+SymbolicLinkHandle], rax
0x180069501  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180069505  mov     [rbp+LinkTarget.Buffer], rax
0x180069509  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18006950d  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180069511  call    cs:__imp_RtlInitUnicodeString
0x180069518  nop     dword ptr [rax+rax+00h]
0x18006951d  lea     rax, [rbp+DestinationString]
0x180069521  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180069528  xorps   xmm0, xmm0
0x18006952b  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18006952f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180069533  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18006953b  mov     edx, 1; DesiredAccess
0x180069540  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180069547  lea     rcx, [rbp+SymbolicLinkHandle]; SymbolicLinkHandle
0x18006954b  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180069550  call    cs:__imp_ZwOpenSymbolicLinkObject
0x180069557  nop     dword ptr [rax+rax+00h]
0x18006955c  test    eax, eax
0x18006955e  js      loc_1800696B5
0x180069564  xor     edx, edx; SourceString
0x180069566  lea     rcx, [rbp+LinkTarget]; DestinationString
0x18006956a  call    cs:__imp_RtlInitUnicodeString
0x180069571  nop     dword ptr [rax+rax+00h]
0x180069576  xor     edi, edi
0x180069578  mov     [rbp+ReturnedLength], edi
0x18006957b  jmp     short loc_1800695D8
0x18006957d  cmp     [rbp+LinkTarget.Buffer], 0
0x180069582  jz      short loc_1800695A3
0x180069584  mov     rcx, gs:60h
0x18006958d  xor     edx, edx; Flags
0x18006958f  mov     r8, [rbp+LinkTarget.Buffer]; P
0x180069593  mov     rcx, [rcx+30h]; HeapHandle
0x180069597  call    cs:__imp_RtlFreeHeap
0x18006959e  nop     dword ptr [rax+rax+00h]
0x1800695a3  mov     eax, [rbp+ReturnedLength]
0x1800695a6  xor     edx, edx; Flags
0x1800695a8  mov     [rbp+LinkTarget.MaximumLength], ax
0x1800695ac  mov     rcx, gs:60h
0x1800695b5  lea     edi, [rax+2]
0x1800695b8  mov     r8d, edi; Size
0x1800695bb  mov     rcx, [rcx+30h]; HeapHandle
0x1800695bf  call    cs:__imp_RtlAllocateHeap
0x1800695c6  nop     dword ptr [rax+rax+00h]
0x1800695cb  mov     [rbp+LinkTarget.Buffer], rax
0x1800695cf  test    rax, rax
0x1800695d2  jz      loc_1800696C6
0x1800695d8  mov     rcx, [rbp+SymbolicLinkHandle]; LinkHandle
0x1800695dc  lea     r8, [rbp+ReturnedLength]; ReturnedLength
0x1800695e0  lea     rdx, [rbp+LinkTarget]; LinkTarget
0x1800695e4  call    cs:__imp_ZwQuerySymbolicLinkObject
0x1800695eb  nop     dword ptr [rax+rax+00h]
0x1800695f0  mov     ebx, eax
0x1800695f2  cmp     eax, 0C0000023h
0x1800695f7  jz      short loc_18006957D
0x1800695f9  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x1800695fd  call    cs:__imp_ZwClose
0x180069604  nop     dword ptr [rax+rax+00h]
0x180069609  mov     [rbp+SymbolicLinkHandle], 0
0x180069611  test    ebx, ebx
0x180069613  js      short loc_18006968D
0x180069615  movzx   edx, [rbp+LinkTarget.Length]
0x180069619  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18006961d  mov     rax, [rbp+LinkTarget.Buffer]
0x180069621  xor     ecx, ecx
0x180069623  shr     rdx, 1
0x180069626  xorps   xmm0, xmm0
0x180069629  mov     [rax+rdx*2], cx
0x18006962d  lea     rax, [rbp+LinkTarget]
0x180069631  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x180069635  lea     edx, [rcx+1]; DesiredAccess
0x180069638  lea     rcx, [rbp+SymbolicLinkHandle]; SymbolicLinkHandle
0x18006963c  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180069640  mov     [rbp+LinkTarget.MaximumLength], di
0x180069644  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18006964b  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180069652  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180069657  call    cs:__imp_ZwOpenSymbolicLinkObject
0x18006965e  nop     dword ptr [rax+rax+00h]
0x180069663  test    eax, eax
0x180069665  jns     loc_1800695D8
0x18006966b  mov     rax, [rbp+LinkTarget.Buffer]
0x18006966f  xor     ebx, ebx
0x180069671  mov     [rsi], rax
0x180069674  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x180069678  test    rcx, rcx
0x18006967b  jz      short loc_180069689
0x18006967d  call    cs:__imp_ZwClose
0x180069684  nop     dword ptr [rax+rax+00h]
0x180069689  test    ebx, ebx
0x18006968b  jns     short loc_1800696B3
0x18006968d  cmp     [rbp+LinkTarget.Buffer], 0
0x180069692  jz      short loc_1800696B3
0x180069694  mov     rcx, gs:60h
0x18006969d  xor     edx, edx; Flags
0x18006969f  mov     r8, [rbp+LinkTarget.Buffer]; P
0x1800696a3  mov     rcx, [rcx+30h]; HeapHandle
0x1800696a7  call    cs:__imp_RtlFreeHeap
0x1800696ae  nop     dword ptr [rax+rax+00h]
0x1800696b3  mov     eax, ebx
0x1800696b5  mov     rbx, [rsp+70h+arg_0]
0x1800696bd  add     rsp, 70h
0x1800696c1  pop     rdi
0x1800696c2  pop     rsi
0x1800696c3  pop     rbp
0x1800696c4  retn
0x1800696c6  mov     ebx, 0C000009Ah
0x1800696cb  jmp     short loc_180069674
```
