# SmscpShouldRequireProcessMitigation

- ea: `0x140018458`
- end: `0x140018606`
- name: `SmscpShouldRequireProcessMitigation`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140007420`

## callees

- `0x140018458`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtClose` at `0x1400185b6`
- `ntdll!NtClose` at `0x1400185b6`
- `ntdll!NtOpenKey` at `0x14001857b`
- `ntdll!NtOpenKey` at `0x14001857b`
- `ntdll!NtQueryValueKey` at `0x1400185a9`
- `ntdll!NtQueryValueKey` at `0x1400185a9`
- `ntdll!RtlEqualUnicodeString` at `0x14001852f`
- `ntdll!RtlEqualUnicodeString` at `0x14001852f`

## string_xrefs

- `0x1400184a0`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\Policies\System`

## pseudocode

```c
__int64 __fastcall SmscpShouldRequireProcessMitigation(__int64 a1, struct _UNICODE_STRING *a2, bool *a3, bool *a4)
{
  char v8; // di
  NTSTATUS v9; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-C0h] BYREF
  UNICODE_STRING String2; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v15[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+A0h] [rbp-60h] BYREF
  int v18; // [rsp+A4h] [rbp-5Ch]
  int v19; // [rsp+A8h] [rbp-58h]
  int v20; // [rsp+ACh] [rbp-54h]

  *a3 = 0;
  *(_QWORD *)&String2.Length = 1703960;
  String2.Buffer = L"winlogon.exe";
  KeyHandle = 0;
  v15[1] = L"\\Registry\\Machine\\Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System";
  ResultLength = 0;
  v15[0] = 9961622;
  *(_DWORD *)(&String1.MaximumLength + 1) = 0;
  *a4 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset_0(KeyValueInformation, 0, 0x210u);
  String1.Buffer = *(PWSTR *)(a1 + 8);
  String1.Length = *(_WORD *)a1;
  if ( String1.Length >= 0x18u )
    String1.Length = 24;
  String1.MaximumLength = *(_WORD *)(a1 + 2);
  v8 = RtlEqualUnicodeString(&String1, &String2, 1u);
  if ( v8 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v15;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    v8 = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
    {
      v9 = NtQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, KeyValueInformation, 0x210u, &ResultLength);
      NtClose(KeyHandle);
      if ( v9 >= 0 && v18 == 4 && v19 == 4 )
        v8 = v20 != 0;
    }
  }
  *a3 = v8 != 0;
  *a4 = v8 == 0;
  return 0;
}

```

## disassembly

```asm
0x140018458  push    rbp
0x14001845a  push    rbx
0x14001845b  push    rsi
0x14001845c  push    rdi
0x14001845d  push    r14
0x14001845f  push    r15
0x140018461  lea     rbp, [rsp-1C8h]
0x140018469  sub     rsp, 2C8h
0x140018470  mov     rax, cs:__security_cookie
0x140018477  xor     rax, rsp
0x14001847a  mov     [rbp+1F0h+var_40], rax
0x140018481  xorps   xmm0, xmm0
0x140018484  mov     byte ptr [r8], 0
0x140018488  lea     rax, aWinlogonExe; "winlogon.exe"
0x14001848f  mov     qword ptr [rsp+2F0h+String2.Length], 1A0018h
0x140018498  mov     [rsp+2F0h+String2.Buffer], rax
0x14001849d  mov     rsi, r8
0x1400184a0  lea     rax, aRegistryMachin_13; "\\Registry\\Machine\\Software\\Microsof"...
0x1400184a7  mov     [rsp+2F0h+KeyHandle], 0
0x1400184b0  mov     r15, rdx
0x1400184b3  mov     [rsp+2F0h+var_288], rax
0x1400184b8  mov     rbx, rcx
0x1400184bb  mov     [rsp+2F0h+var_2C0], 0
0x1400184c3  xor     edx, edx; Val
0x1400184c5  mov     [rsp+2F0h+var_290], 980096h
0x1400184ce  mov     r8d, 210h; Size
0x1400184d4  mov     dword ptr [rsp+2F0h+String1+4], 0
0x1400184dc  lea     rcx, [rbp+1F0h+KeyValueInformation]; void *
0x1400184e0  mov     byte ptr [r9], 0
0x1400184e4  mov     r14, r9
0x1400184e7  mov     edi, 18h
0x1400184ec  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.Length], xmm0
0x1400184f1  movups  xmmword ptr [rbp+1F0h+ObjectAttributes.ObjectName], xmm0
0x1400184f5  movups  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400184f9  call    memset_0
0x1400184fe  mov     rax, [rbx+8]
0x140018502  mov     [rsp+2F0h+String1.Buffer], rax
0x140018507  movzx   eax, word ptr [rbx]
0x14001850a  mov     [rsp+2F0h+String1.Length], ax
0x14001850f  cmp     ax, di
0x140018512  jb      short loc_140018519
0x140018514  mov     [rsp+2F0h+String1.Length], di
0x140018519  movzx   eax, word ptr [rbx+2]
0x14001851d  lea     rdx, [rsp+2F0h+String2]; String2
0x140018522  mov     r8b, 1; CaseInSensitive
0x140018525  mov     [rsp+2F0h+String1.MaximumLength], ax
0x14001852a  lea     rcx, [rsp+2F0h+String1]; String1
0x14001852f  call    cs:__imp_RtlEqualUnicodeString
0x140018535  mov     dil, al
0x140018538  test    al, al
0x14001853a  jz      loc_1400185D4
0x140018540  lea     rax, [rsp+2F0h+var_290]
0x140018545  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x14001854d  xorps   xmm0, xmm0
0x140018550  mov     [rbp+1F0h+ObjectAttributes.ObjectName], rax
0x140018554  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x140018559  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], 0
0x140018562  mov     edx, 20019h; DesiredAccess
0x140018567  mov     [rbp+1F0h+ObjectAttributes.Attributes], 40h ; '@'
0x14001856e  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x140018573  xor     dil, dil
0x140018576  movdqu  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001857b  call    cs:__imp_NtOpenKey
0x140018581  test    eax, eax
0x140018583  js      short loc_1400185D4
0x140018585  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x14001858a  lea     rax, [rsp+2F0h+var_2C0]
0x14001858f  mov     [rsp+2F0h+ResultLength], rax; ResultLength
0x140018594  lea     r9, [rbp+1F0h+KeyValueInformation]; KeyValueInformation
0x140018598  mov     r8d, 2; KeyValueInformationClass
0x14001859e  mov     [rsp+2F0h+Length], 210h; Length
0x1400185a6  mov     rdx, r15; ValueName
0x1400185a9  call    cs:__imp_NtQueryValueKey
0x1400185af  mov     rcx, [rsp+2F0h+KeyHandle]; Handle
0x1400185b4  mov     ebx, eax
0x1400185b6  call    cs:__imp_NtClose
0x1400185bc  test    ebx, ebx
0x1400185be  js      short loc_1400185D4
0x1400185c0  cmp     [rbp+1F0h+var_24C], 4
0x1400185c4  jnz     short loc_1400185D4
0x1400185c6  cmp     [rbp+1F0h+var_248], 4
0x1400185ca  jnz     short loc_1400185D4
0x1400185cc  cmp     [rbp+1F0h+var_244], 0
0x1400185d0  setnz   dil
0x1400185d4  test    dil, dil
0x1400185d7  setnz   al
0x1400185da  test    dil, dil
0x1400185dd  mov     [rsi], al
0x1400185df  setz    al
0x1400185e2  mov     [r14], al
0x1400185e5  xor     eax, eax
0x1400185e7  mov     rcx, [rbp+1F0h+var_40]
0x1400185ee  xor     rcx, rsp; StackCookie
0x1400185f1  call    __security_check_cookie
0x1400185f6  add     rsp, 2C8h
0x1400185fd  pop     r15
0x1400185ff  pop     r14
0x140018601  pop     rdi
0x140018602  pop     rsi
0x140018603  pop     rbx
0x140018604  pop     rbp
0x140018605  retn
```
