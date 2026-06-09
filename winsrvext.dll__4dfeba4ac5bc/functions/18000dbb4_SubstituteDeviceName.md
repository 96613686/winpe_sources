# SubstituteDeviceName

- ea: `0x18000dbb4`
- end: `0x18000dd7b`
- name: `SubstituteDeviceName`
- size: `455`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000c050`

## callees

- `0x18000dbb4`
- `0x1800138c5`
- `0x1800138f0`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18000dd0c`
- `ntdll!RtlEqualUnicodeString` at `0x18000dd0c`
- `ntdll!NtOpenSymbolicLinkObject` at `0x18000dcb0`
- `ntdll!NtOpenSymbolicLinkObject` at `0x18000dcb0`
- `ntdll!NtQuerySymbolicLinkObject` at `0x18000dcde`
- `ntdll!NtQuerySymbolicLinkObject` at `0x18000dcde`
- `ntdll!RtlInitUnicodeString` at `0x18000dc5f`
- `ntdll!RtlInitUnicodeString` at `0x18000dc5f`
- `ntdll!NtClose` at `0x18000dcf1`
- `ntdll!NtClose` at `0x18000dcf1`

## pseudocode

```c
__int64 __fastcall SubstituteDeviceName(PCUNICODE_STRING String1, __int64 a2)
{
  bool v4; // cf
  __int64 result; // rax
  int v6; // edi
  NTSTATUS v7; // ebx
  void *SymbolicLinkHandle; // [rsp+20h] [rbp-E0h] BYREF
  struct _UNICODE_STRING LinkTarget; // [rsp+28h] [rbp-D8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SourceString[12]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v13[512]; // [rsp+90h] [rbp-70h] BYREF

  SymbolicLinkHandle = 0;
  DestinationString = 0;
  LinkTarget = 0;
  memset(&ObjectAttributes, 0, 44);
  memset_0(v13, 0, sizeof(v13));
  v4 = *(_WORD *)(a2 + 2) < 3u;
  wcscpy(SourceString, L"\\??\\A:");
  if ( v4 )
    return 3221225507LL;
  RtlInitUnicodeString(&DestinationString, SourceString);
  v6 = 0;
  while ( 1 )
  {
    ObjectAttributes.Length = 48;
    SourceString[4] = v6 + 65;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes) >= 0 )
    {
      LinkTarget.Buffer = (PWSTR)v13;
      *(_DWORD *)&LinkTarget.Length = 0x2000000;
      v7 = NtQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, 0);
      NtClose(SymbolicLinkHandle);
      if ( v7 >= 0 )
      {
        if ( RtlEqualUnicodeString(String1, &LinkTarget, 1u) )
          break;
      }
    }
    if ( (unsigned int)++v6 >= 0x1A )
      return 3221225530LL;
  }
  **(_BYTE **)(a2 + 8) = v6 + 65;
  *(_BYTE *)(*(_QWORD *)(a2 + 8) + 1LL) = 58;
  *(_BYTE *)(*(_QWORD *)(a2 + 8) + 2LL) = 0;
  result = 0;
  *(_WORD *)a2 = 2;
  return result;
}

```

## disassembly

```asm
0x18000dbb4  mov     [rsp-8+arg_10], rbx
0x18000dbb9  mov     [rsp-8+arg_18], rsi
0x18000dbbe  push    rbp
0x18000dbbf  push    rdi
0x18000dbc0  push    r12
0x18000dbc2  push    r13
0x18000dbc4  push    r14
0x18000dbc6  lea     rbp, [rsp-1A0h]
0x18000dbce  sub     rsp, 2A0h
0x18000dbd5  mov     rax, cs:__security_cookie
0x18000dbdc  xor     rax, rsp
0x18000dbdf  mov     [rbp+1C0h+var_30], rax
0x18000dbe6  xorps   xmm0, xmm0
0x18000dbe9  mov     rsi, rdx
0x18000dbec  mov     r14, rcx
0x18000dbef  xorps   xmm1, xmm1
0x18000dbf2  xor     eax, eax
0x18000dbf4  lea     rcx, [rbp+1C0h+var_230]; void *
0x18000dbf8  movups  xmmword ptr [rsp+2C0h+ObjectAttributes.ObjectName], xmm0
0x18000dbfd  xor     edx, edx; Val
0x18000dbff  mov     [rsp+2C0h+SymbolicLinkHandle], rax
0x18000dc04  mov     r8d, 200h; Size
0x18000dc0a  movups  xmmword ptr [rsp+2C0h+ObjectAttributes+1Ch], xmm0
0x18000dc0f  movups  xmmword ptr [rsp+2C0h+DestinationString.Length], xmm0
0x18000dc14  movups  xmmword ptr [rsp+2C0h+LinkTarget.Length], xmm1
0x18000dc19  movups  xmmword ptr [rsp+2C0h+ObjectAttributes.Length], xmm0
0x18000dc1e  call    memset_0
0x18000dc23  cmp     word ptr [rsi+2], 3
0x18000dc28  mov     rax, 5C003F003F005Ch
0x18000dc32  mov     r12d, 41h ; 'A'
0x18000dc38  mov     qword ptr [rsp+2C0h+SourceString], rax
0x18000dc3d  mov     [rbp+1C0h+var_240], r12w
0x18000dc42  mov     [rbp+1C0h+var_23E], 3Ah ; ':'
0x18000dc49  jnb     short loc_18000DC55
0x18000dc4b  mov     eax, 0C0000023h
0x18000dc50  jmp     loc_18000DD2C
0x18000dc55  lea     rdx, [rsp+2C0h+SourceString]; SourceString
0x18000dc5a  lea     rcx, [rsp+2C0h+DestinationString]; DestinationString
0x18000dc5f  call    cs:__imp_RtlInitUnicodeString
0x18000dc66  nop     dword ptr [rax+rax+00h]
0x18000dc6b  xor     edi, edi
0x18000dc6d  lea     eax, [r12+rdi]
0x18000dc71  mov     [rsp+2C0h+ObjectAttributes.Length], 30h ; '0'
0x18000dc79  mov     [rbp+1C0h+var_240], ax
0x18000dc7d  lea     r8, [rsp+2C0h+ObjectAttributes]; ObjectAttributes
0x18000dc82  lea     rax, [rsp+2C0h+DestinationString]
0x18000dc87  mov     [rsp+2C0h+ObjectAttributes.RootDirectory], 0
0x18000dc90  xorps   xmm0, xmm0
0x18000dc93  mov     [rsp+2C0h+ObjectAttributes.ObjectName], rax
0x18000dc98  mov     edx, 1; DesiredAccess
0x18000dc9d  mov     [rsp+2C0h+ObjectAttributes.Attributes], 40h ; '@'
0x18000dca5  lea     rcx, [rsp+2C0h+SymbolicLinkHandle]; SymbolicLinkHandle
0x18000dcaa  movdqu  xmmword ptr [rsp+2C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000dcb0  call    cs:__imp_NtOpenSymbolicLinkObject
0x18000dcb7  nop     dword ptr [rax+rax+00h]
0x18000dcbc  test    eax, eax
0x18000dcbe  js      short loc_18000DD1C
0x18000dcc0  mov     rcx, [rsp+2C0h+SymbolicLinkHandle]; SymLinkObjHandle
0x18000dcc5  lea     rax, [rbp+1C0h+var_230]
0x18000dcc9  xor     r8d, r8d; DataWritten
0x18000dccc  mov     [rsp+2C0h+LinkTarget.Buffer], rax
0x18000dcd1  lea     rdx, [rsp+2C0h+LinkTarget]; LinkTarget
0x18000dcd6  mov     dword ptr [rsp+2C0h+LinkTarget.Length], 2000000h
0x18000dcde  call    cs:__imp_NtQuerySymbolicLinkObject
0x18000dce5  nop     dword ptr [rax+rax+00h]
0x18000dcea  mov     rcx, [rsp+2C0h+SymbolicLinkHandle]; Handle
0x18000dcef  mov     ebx, eax
0x18000dcf1  call    cs:__imp_NtClose
0x18000dcf8  nop     dword ptr [rax+rax+00h]
0x18000dcfd  test    ebx, ebx
0x18000dcff  js      short loc_18000DD1C
0x18000dd01  mov     r8b, 1; CaseInsensitive
0x18000dd04  lea     rdx, [rsp+2C0h+LinkTarget]; String2
0x18000dd09  mov     rcx, r14; String1
0x18000dd0c  call    cs:__imp_RtlEqualUnicodeString
0x18000dd13  nop     dword ptr [rax+rax+00h]
0x18000dd18  test    al, al
0x18000dd1a  jnz     short loc_18000DD58
0x18000dd1c  inc     edi
0x18000dd1e  cmp     edi, 1Ah
0x18000dd21  jb      loc_18000DC6D
0x18000dd27  mov     eax, 0C000003Ah
0x18000dd2c  mov     rcx, [rbp+1C0h+var_30]
0x18000dd33  xor     rcx, rsp; StackCookie
0x18000dd36  call    __security_check_cookie
0x18000dd3b  lea     r11, [rsp+2C0h+var_20]
0x18000dd43  mov     rbx, [r11+40h]
0x18000dd47  mov     rsi, [r11+48h]
0x18000dd4b  mov     rsp, r11
0x18000dd4e  pop     r14
0x18000dd50  pop     r13
0x18000dd52  pop     r12
0x18000dd54  pop     rdi
0x18000dd55  pop     rbp
0x18000dd56  retn
0x18000dd58  mov     rax, [rsi+8]
0x18000dd5c  add     dil, r12b
0x18000dd5f  mov     [rax], dil
0x18000dd62  mov     rax, [rsi+8]
0x18000dd66  mov     byte ptr [rax+1], 3Ah ; ':'
0x18000dd6a  mov     rax, [rsi+8]
0x18000dd6e  mov     byte ptr [rax+2], 0
0x18000dd72  xor     eax, eax
0x18000dd74  mov     word ptr [rsi], 2
0x18000dd79  jmp     short loc_18000DD2C
```
