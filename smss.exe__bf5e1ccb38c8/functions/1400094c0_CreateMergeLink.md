# CreateMergeLink

- ea: `0x1400094c0`
- end: `0x140009698`
- name: `CreateMergeLink`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000b21c`

## callees

- `0x1400094c0`
- `0x1400096a0`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtClose` at `0x1400095b2`
- `ntdll!NtClose` at `0x1400095d4`
- `ntdll!NtClose` at `0x140009621`
- `ntdll!NtClose` at `0x14000962d`
- `ntdll!NtClose` at `0x140009655`
- `ntdll!NtClose` at `0x1400095b2`
- `ntdll!NtClose` at `0x1400095d4`
- `ntdll!NtClose` at `0x140009621`
- `ntdll!NtClose` at `0x14000962d`
- `ntdll!NtClose` at `0x140009655`
- `ntdll!NtOpenKey` at `0x140009578`
- `ntdll!NtOpenKey` at `0x140009578`
- `ntdll!NtSetValueKey` at `0x140009615`
- `ntdll!NtSetValueKey` at `0x140009615`
- `ntdll!NtQueryKey` at `0x1400095a2`
- `ntdll!NtQueryKey` at `0x1400095a2`
- `ntdll!NtDeleteKey` at `0x1400095c8`
- `ntdll!NtDeleteKey` at `0x1400095c8`

## pseudocode

```c
int __fastcall CreateMergeLink(__int128 *a1, PVOID *a2)
{
  int result; // eax
  void *v5; // rdx
  __int128 v6; // xmm0
  NTSTATUS v7; // esi
  void *v8; // rdx
  NTSTATUS v9; // ebx
  int v10; // eax
  void *KeyHandle; // [rsp+30h] [rbp-29h] BYREF
  ULONG ResultLength; // [rsp+38h] [rbp-21h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-11h] BYREF
  __int128 v15; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 KeyInformation; // [rsp+88h] [rbp+2Fh] BYREF
  int v17; // [rsp+90h] [rbp+37h]

  KeyInformation = 0;
  v17 = 0;
  ResultLength = 0;
  KeyHandle = 0;
  Handle = 0;
  memset(&ObjectAttributes, 0, 44);
  v15 = 0;
  result = CreateKeyRecursively(&KeyHandle, a2, a1, 1);
  if ( result != -1073741790 )
  {
    if ( result == -1073741771 )
    {
      v6 = *a1;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      v15 = v6;
      ObjectAttributes.Attributes = 320;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v15;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      result = NtOpenKey(&KeyHandle, 0x3001Fu, &ObjectAttributes);
      if ( result < 0 )
        return result;
      v7 = NtQueryKey(KeyHandle, KeyFlagsInformation, &KeyInformation, 0xCu, &ResultLength);
      if ( v7 < 0 )
      {
        NtClose(KeyHandle);
        return v7;
      }
      if ( (BYTE4(KeyInformation) & 3) != 2 )
      {
        NtClose(KeyHandle);
        goto LABEL_15;
      }
      v7 = NtDeleteKey(KeyHandle);
      NtClose(KeyHandle);
      if ( v7 < 0 )
        return v7;
      result = CreateKeyRecursively(&KeyHandle, v8, a1, 1);
    }
    if ( result < 0 )
    {
      if ( result != -1073741771 )
        return result;
    }
    else
    {
      v9 = NtSetValueKey(KeyHandle, &SymbolicLinkValueName, 0, 6u, a2[1], *(unsigned __int16 *)a2);
      NtClose(KeyHandle);
      if ( v9 < 0 )
        return v9;
    }
LABEL_15:
    v10 = CreateKeyRecursively(&Handle, v5, (__int128 *)a2, 0);
    v9 = v10;
    if ( v10 < 0 )
    {
      if ( v10 == -1073741771 || v10 == -1073741790 )
        return 0;
    }
    else
    {
      NtClose(Handle);
    }
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x1400094c0  mov     [rsp-8+arg_18], rbx
0x1400094c5  push    rbp
0x1400094c6  push    rdi
0x1400094c7  push    r14
0x1400094c9  lea     rbp, [rsp-47h]
0x1400094ce  sub     rsp, 0A0h
0x1400094d5  mov     rax, cs:__security_cookie
0x1400094dc  xor     rax, rsp
0x1400094df  mov     [rbp+57h+var_18], rax
0x1400094e3  xorps   xmm0, xmm0
0x1400094e6  xor     eax, eax
0x1400094e8  xor     r14d, r14d
0x1400094eb  mov     [rbp+57h+KeyInformation], rax
0x1400094ef  mov     rbx, rcx
0x1400094f2  mov     [rbp+57h+var_20], eax
0x1400094f5  mov     r8, rcx
0x1400094f8  mov     [rbp+57h+var_78], r14d
0x1400094fc  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140009500  mov     r9b, 1
0x140009503  mov     [rbp+57h+KeyHandle], r14
0x140009507  lea     rcx, [rbp+57h+KeyHandle]
0x14000950b  mov     [rbp+57h+Handle], r14
0x14000950f  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140009513  mov     rdi, rdx
0x140009516  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14000951a  movups  [rbp+57h+var_38], xmm0
0x14000951e  call    CreateKeyRecursively
0x140009523  cmp     eax, 0C0000022h
0x140009528  jnz     short loc_14000952F
0x14000952a  jmp     loc_140009678
0x14000952f  mov     [rsp+0B0h+arg_10], rsi
0x140009537  cmp     eax, 0C0000035h
0x14000953c  jnz     loc_1400095ED
0x140009542  movups  xmm0, xmmword ptr [rbx]
0x140009545  lea     rax, [rbp+57h+var_38]
0x140009549  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140009550  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140009554  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x140009558  movups  [rbp+57h+var_38], xmm0
0x14000955c  mov     [rbp+57h+ObjectAttributes.Attributes], 140h
0x140009563  mov     edx, 3001Fh; DesiredAccess
0x140009568  xorps   xmm0, xmm0
0x14000956b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000956f  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140009573  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140009578  call    cs:__imp_NtOpenKey
0x14000957e  test    eax, eax
0x140009580  js      loc_140009670
0x140009586  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000958a  lea     rax, [rbp+57h+var_78]
0x14000958e  mov     r9d, 0Ch; Length
0x140009594  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x140009599  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x14000959d  mov     edx, 5; KeyInformationClass
0x1400095a2  call    cs:__imp_NtQueryKey
0x1400095a8  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400095ac  mov     esi, eax
0x1400095ae  test    eax, eax
0x1400095b0  jns     short loc_1400095BF
0x1400095b2  call    cs:__imp_NtClose
0x1400095b8  mov     eax, esi
0x1400095ba  jmp     loc_140009670
0x1400095bf  mov     eax, dword ptr [rbp+57h+KeyInformation+4]
0x1400095c2  and     al, 3
0x1400095c4  cmp     al, 2
0x1400095c6  jnz     short loc_14000962D
0x1400095c8  call    cs:__imp_NtDeleteKey
0x1400095ce  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400095d2  mov     esi, eax
0x1400095d4  call    cs:__imp_NtClose
0x1400095da  test    esi, esi
0x1400095dc  js      short loc_1400095B8
0x1400095de  mov     r9b, 1
0x1400095e1  lea     rcx, [rbp+57h+KeyHandle]
0x1400095e5  mov     r8, rbx
0x1400095e8  call    CreateKeyRecursively
0x1400095ed  test    eax, eax
0x1400095ef  js      short loc_140009635
0x1400095f1  movzx   eax, word ptr [rdi]
0x1400095f4  lea     rdx, SymbolicLinkValueName; ValueName
0x1400095fb  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400095ff  mov     r9d, 6; Type
0x140009605  mov     [rsp+0B0h+DataSize], eax; DataSize
0x140009609  xor     r8d, r8d; TitleIndex
0x14000960c  mov     rax, [rdi+8]
0x140009610  mov     [rsp+0B0h+ResultLength], rax; Data
0x140009615  call    cs:__imp_NtSetValueKey
0x14000961b  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14000961f  mov     ebx, eax
0x140009621  call    cs:__imp_NtClose
0x140009627  test    ebx, ebx
0x140009629  jns     short loc_14000963C
0x14000962b  jmp     short loc_14000966E
0x14000962d  call    cs:__imp_NtClose
0x140009633  jmp     short loc_14000963C
0x140009635  cmp     eax, 0C0000035h
0x14000963a  jnz     short loc_140009670
0x14000963c  xor     r9d, r9d
0x14000963f  lea     rcx, [rbp+57h+Handle]
0x140009643  mov     r8, rdi
0x140009646  call    CreateKeyRecursively
0x14000964b  mov     ebx, eax
0x14000964d  test    eax, eax
0x14000964f  js      short loc_14000965D
0x140009651  mov     rcx, [rbp+57h+Handle]; Handle
0x140009655  call    cs:__imp_NtClose
0x14000965b  jmp     short loc_14000966E
0x14000965d  cmp     eax, 0C0000035h
0x140009662  jz      short loc_14000966B
0x140009664  cmp     eax, 0C0000022h
0x140009669  jnz     short loc_14000966E
0x14000966b  mov     ebx, r14d
0x14000966e  mov     eax, ebx
0x140009670  mov     rsi, [rsp+0B0h+arg_10]
0x140009678  mov     rcx, [rbp+57h+var_18]
0x14000967c  xor     rcx, rsp; StackCookie
0x14000967f  call    __security_check_cookie
0x140009684  mov     rbx, [rsp+0B0h+arg_18]
0x14000968c  add     rsp, 0A0h
0x140009693  pop     r14
0x140009695  pop     rdi
0x140009696  pop     rbp
0x140009697  retn
```
