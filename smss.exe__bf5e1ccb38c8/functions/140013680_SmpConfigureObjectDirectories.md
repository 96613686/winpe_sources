# SmpConfigureObjectDirectories

- ea: `0x140013680`
- end: `0x1400137a4`
- name: `SmpConfigureObjectDirectories`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1400010ec`
- `0x140013680`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1400136e6`
- `ntdll!RtlInitUnicodeString` at `0x1400136e6`
- `ntdll!NtClose` at `0x14001377b`
- `ntdll!NtClose` at `0x14001377b`
- `ntdll!NtCreateDirectoryObject` at `0x140013753`
- `ntdll!NtCreateDirectoryObject` at `0x140013753`
- `ntdll!RtlEqualUnicodeString` at `0x1400136fe`
- `ntdll!RtlEqualUnicodeString` at `0x140013713`
- `ntdll!RtlEqualUnicodeString` at `0x1400136fe`
- `ntdll!RtlEqualUnicodeString` at `0x140013713`

## string_xrefs

- `0x140013761`: `SmpConfigureObjectDirectories`

## pseudocode

```c
__int64 __fastcall SmpConfigureObjectDirectories(__int64 a1, __int64 a2, const WCHAR *a3)
{
  const WCHAR *v3; // rbx
  PSECURITY_DESCRIPTOR v4; // rdi
  NTSTATUS v5; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-39h] BYREF
  UNICODE_STRING String2; // [rsp+30h] [rbp-29h] BYREF
  UNICODE_STRING v10; // [rsp+40h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-9h] BYREF
  void *DirectoryHandle; // [rsp+C0h] [rbp+67h] BYREF

  *(_QWORD *)&String2.Length = 1703960;
  *(_QWORD *)&v10.Length = 1179664;
  v3 = a3;
  String2.Buffer = L"\\RPC Control";
  DirectoryHandle = 0;
  v10.Buffer = L"\\Windows";
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( *a3 )
  {
    do
    {
      RtlInitUnicodeString(&DestinationString, v3);
      v4 = SmpPrimarySecurityDescriptor;
      if ( RtlEqualUnicodeString(&DestinationString, &String2, 1u)
        || RtlEqualUnicodeString(&DestinationString, &v10, 1u) )
      {
        v4 = SmpLiberalSecurityDescriptor;
      }
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 208;
      ObjectAttributes.SecurityDescriptor = v4;
      ObjectAttributes.SecurityQualityOfService = 0;
      v5 = NtCreateDirectoryObject(&DirectoryHandle, 0xF000Fu, &ObjectAttributes);
      if ( v5 >= 0 )
        NtClose(DirectoryHandle);
      else
        SmpLogFailureString("SmpConfigureObjectDirectories", 7384, DestinationString.Buffer, (unsigned int)v5);
      while ( *v3++ )
        ;
    }
    while ( *v3 );
  }
  return 0;
}

```

## disassembly

```asm
0x140013680  push    rbp
0x140013682  push    rbx
0x140013683  push    rsi
0x140013684  push    rdi
0x140013685  lea     rbp, [rsp-2Fh]
0x14001368a  sub     rsp, 88h
0x140013691  xorps   xmm0, xmm0
0x140013694  mov     qword ptr [rbp+47h+String2.Length], 1A0018h
0x14001369c  xor     eax, eax
0x14001369e  mov     qword ptr [rbp+47h+var_60.Length], 120010h
0x1400136a6  lea     rax, aRpcControl; "\\RPC Control"
0x1400136ad  xor     esi, esi
0x1400136af  mov     rbx, r8
0x1400136b2  mov     [rbp+47h+String2.Buffer], rax
0x1400136b6  lea     rax, aWindows; "\\Windows"
0x1400136bd  mov     [rbp+47h+DirectoryHandle], rsi
0x1400136c1  movups  xmmword ptr [rbp+47h+ObjectAttributes.ObjectName], xmm0
0x1400136c5  mov     [rbp+47h+var_60.Buffer], rax
0x1400136c9  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x1400136cd  movups  xmmword ptr [rbp+47h+ObjectAttributes.Length], xmm0
0x1400136d1  movups  xmmword ptr [rbp+47h+ObjectAttributes+1Ch], xmm0
0x1400136d5  cmp     [r8], si
0x1400136d9  jz      loc_140013796
0x1400136df  mov     rdx, rbx; SourceString
0x1400136e2  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x1400136e6  call    cs:__imp_RtlInitUnicodeString
0x1400136ec  mov     rdi, cs:SmpPrimarySecurityDescriptor
0x1400136f3  lea     rdx, [rbp+47h+String2]; String2
0x1400136f7  mov     r8b, 1; CaseInSensitive
0x1400136fa  lea     rcx, [rbp+47h+DestinationString]; String1
0x1400136fe  call    cs:__imp_RtlEqualUnicodeString
0x140013704  test    al, al
0x140013706  jnz     short loc_14001371D
0x140013708  mov     r8b, 1; CaseInSensitive
0x14001370b  lea     rdx, [rbp+47h+var_60]; String2
0x14001370f  lea     rcx, [rbp+47h+DestinationString]; String1
0x140013713  call    cs:__imp_RtlEqualUnicodeString
0x140013719  test    al, al
0x14001371b  jz      short loc_140013724
0x14001371d  mov     rdi, cs:SmpLiberalSecurityDescriptor
0x140013724  lea     rax, [rbp+47h+DestinationString]
0x140013728  mov     [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x14001372f  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x140013733  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x140013737  mov     edx, 0F000Fh; DesiredAccess
0x14001373c  mov     [rbp+47h+ObjectAttributes.RootDirectory], rsi
0x140013740  lea     rcx, [rbp+47h+DirectoryHandle]; DirectoryHandle
0x140013744  mov     [rbp+47h+ObjectAttributes.Attributes], 0D0h
0x14001374b  mov     [rbp+47h+ObjectAttributes.SecurityDescriptor], rdi
0x14001374f  mov     [rbp+47h+ObjectAttributes.SecurityQualityOfService], rsi
0x140013753  call    cs:__imp_NtCreateDirectoryObject
0x140013759  test    eax, eax
0x14001375b  jns     short loc_140013777
0x14001375d  mov     r8, [rbp+47h+DestinationString.Buffer]
0x140013761  lea     rcx, aSmpconfigureob; "SmpConfigureObjectDirectories"
0x140013768  mov     r9d, eax
0x14001376b  mov     edx, 1CD8h
0x140013770  call    SmpLogFailureString
0x140013775  jmp     short loc_140013781
0x140013777  mov     rcx, [rbp+47h+DirectoryHandle]; Handle
0x14001377b  call    cs:__imp_NtClose
0x140013781  movzx   eax, word ptr [rbx]
0x140013784  add     rbx, 2
0x140013788  test    ax, ax
0x14001378b  jnz     short loc_140013781
0x14001378d  cmp     [rbx], si
0x140013790  jnz     loc_1400136DF
0x140013796  xor     eax, eax
0x140013798  add     rsp, 88h
0x14001379f  pop     rdi
0x1400137a0  pop     rsi
0x1400137a1  pop     rbx
0x1400137a2  pop     rbp
0x1400137a3  retn
```
