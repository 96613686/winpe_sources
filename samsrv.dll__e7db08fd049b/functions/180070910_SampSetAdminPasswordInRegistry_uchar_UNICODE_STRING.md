# SampSetAdminPasswordInRegistry(uchar,_UNICODE_STRING *)

- ea: `0x180070910`
- end: `0x180070b4e`
- name: `?SampSetAdminPasswordInRegistry@@YAJEPEAU_UNICODE_STRING@@@Z`
- size: `574`
- prototype: `__int64 __fastcall(unsigned __int8, struct _UNICODE_STRING *)`
- caller_count: `3`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800715d0`
- `0x180071af0`
- `0x1800722d0`

## callees

- `0x180027e24`
- `0x18002cd80`
- `0x1800372ac`
- `0x18006e5b0`
- `0x180070910`
- `0x1800a46c0`

## import_xrefs

- `ntdll!NtSetValueKey` at `0x180070a34`
- `ntdll!NtSetValueKey` at `0x180070a34`
- `ntdll!NtOpenKey` at `0x1800709f5`
- `ntdll!NtOpenKey` at `0x1800709f5`
- `ntdll!NtFlushKey` at `0x180070a44`
- `ntdll!NtFlushKey` at `0x180070a44`
- `ntdll!NtClose` at `0x180070a93`
- `ntdll!NtClose` at `0x180070a93`
- `ntdll!RtlInitUnicodeString` at `0x1800709bc`
- `ntdll!RtlInitUnicodeString` at `0x180070a10`
- `ntdll!RtlInitUnicodeString` at `0x1800709bc`
- `ntdll!RtlInitUnicodeString` at `0x180070a10`

## string_xrefs

- `0x1800709b1`: `\Registry\Machine\System\CurrentControlSet\Services\SAMSS`

## pseudocode

```c
__int64 __fastcall SampSetAdminPasswordInRegistry(char a1, struct _UNICODE_STRING *a2)
{
  __int64 v4; // rdi
  __int64 v5; // rcx
  __int128 *p_Data; // rax
  int CurrentAdminPassword; // eax
  unsigned int v8; // ebx
  NTSTATUS v9; // eax
  PUNICODE_STRING v10; // rcx
  __int64 v11; // rdx
  PUNICODE_STRING v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  __int128 *v15; // rax
  void *KeyHandle; // [rsp+30h] [rbp-59h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-51h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+48h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-31h] BYREF
  __int128 Data; // [rsp+88h] [rbp-1h] BYREF
  _BYTE v22[19]; // [rsp+98h] [rbp+Fh] BYREF

  KeyHandle = 0;
  memset(v22, 0, sizeof(v22));
  v4 = 35;
  v5 = 35;
  p_Data = &Data;
  Data = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  ValueName = 0;
  do
  {
    *(_BYTE *)p_Data = 0;
    p_Data = (__int128 *)((char *)p_Data + 1);
    --v5;
  }
  while ( v5 );
  if ( a1 )
  {
    CurrentAdminPassword = SampGetCurrentAdminPassword((struct _USER_INTERNAL1_INFORMATION *)&Data);
  }
  else
  {
    v22[18] = 0;
    v22[16] = 1;
    CurrentAdminPassword = SampCalculateLmAndNtOwfPasswords(a2, &v22[17], v22, &Data);
  }
  v8 = CurrentAdminPassword;
  if ( CurrentAdminPassword < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      v13 = 139;
      v14 = (unsigned int)CurrentAdminPassword;
      goto LABEL_28;
    }
    goto LABEL_30;
  }
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\SAMSS");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = NtOpenKey(&KeyHandle, 0x10000000u, &ObjectAttributes);
  v8 = v9;
  if ( v9 >= 0 )
  {
    RtlInitUnicodeString(&ValueName, L"AdminInfo");
    v8 = NtSetValueKey(KeyHandle, &ValueName, 0, 3u, &Data, 0x23u);
    if ( (v8 & 0x80000000) != 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        v11 = 136;
        goto LABEL_16;
      }
    }
    else if ( NtFlushKey(KeyHandle) < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        v11 = 135;
LABEL_16:
        WPP_SF_d(v10[3].Buffer, v11, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v8);
      }
    }
    v9 = NtClose(KeyHandle);
    if ( v9 >= 0 )
    {
LABEL_29:
      v12 = WPP_GLOBAL_Control;
      goto LABEL_30;
    }
    v12 = WPP_GLOBAL_Control;
    if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      v13 = 137;
LABEL_21:
      v14 = (unsigned int)v9;
LABEL_28:
      WPP_SF_d(v12[3].Buffer, v13, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v14);
      goto LABEL_29;
    }
    goto LABEL_30;
  }
  v12 = WPP_GLOBAL_Control;
  if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
  {
    v13 = 138;
    goto LABEL_21;
  }
LABEL_30:
  v15 = &Data;
  do
  {
    *(_BYTE *)v15 = 0;
    v15 = (__int128 *)((char *)v15 + 1);
    --v4;
  }
  while ( v4 );
  if ( (*(_DWORD *)(&v12[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v12[3].Buffer, 140, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v8, v8);
  return v8;
}

```

## disassembly

```asm
0x180070910  push    rbp
0x180070912  push    rbx
0x180070913  push    rdi
0x180070914  push    r14
0x180070916  lea     rbp, [rsp-3Fh]
0x18007091b  sub     rsp, 0C8h
0x180070922  mov     rax, cs:__security_cookie
0x180070929  xor     rax, rsp
0x18007092c  mov     [rbp+57h+var_30], rax
0x180070930  xor     eax, eax
0x180070932  xorps   xmm0, xmm0
0x180070935  xorps   xmm1, xmm1
0x180070938  mov     [rbp+57h+KeyHandle], rax
0x18007093c  mov     r10, rdx
0x18007093f  mov     dl, cl
0x180070941  movups  [rbp+57h+var_48], xmm0
0x180070945  lea     edi, [rax+23h]
0x180070948  mov     dword ptr [rbp+57h+var_48+0Fh], eax
0x18007094b  mov     ecx, edi
0x18007094d  lea     rax, [rbp+57h+var_58]
0x180070951  movups  [rbp+57h+var_58], xmm0
0x180070955  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x180070959  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18007095d  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x180070961  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180070965  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x180070969  mov     byte ptr [rax], 0
0x18007096c  inc     rax
0x18007096f  sub     rcx, 1
0x180070973  jnz     short loc_180070969
0x180070975  test    dl, dl
0x180070977  jz      short loc_180070984
0x180070979  lea     rcx, [rbp+57h+var_58]; struct _USER_INTERNAL1_INFORMATION *
0x18007097d  call    ?SampGetCurrentAdminPassword@@YAJPEAU_USER_INTERNAL1_INFORMATION@@@Z; SampGetCurrentAdminPassword(_USER_INTERNAL1_INFORMATION *)
0x180070982  jmp     short loc_1800709A0
0x180070984  lea     r9, [rbp+57h+var_58]
0x180070988  mov     [rbp+57h+var_36], 0
0x18007098c  lea     r8, [rbp+57h+var_48]
0x180070990  mov     [rbp+57h+var_38], 1
0x180070994  lea     rdx, [rbp+57h+var_37]
0x180070998  mov     rcx, r10
0x18007099b  call    SampCalculateLmAndNtOwfPasswords
0x1800709a0  lea     r14, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x1800709a7  mov     ebx, eax
0x1800709a9  test    eax, eax
0x1800709ab  js      loc_180070AD4
0x1800709b1  lea     rdx, aRegistryMachin_7; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800709b8  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800709bc  call    cs:__imp_RtlInitUnicodeString
0x1800709c2  lea     rax, [rbp+57h+DestinationString]
0x1800709c6  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800709cd  xorps   xmm0, xmm0
0x1800709d0  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800709d4  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800709d8  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800709e0  mov     edx, 10000000h; DesiredAccess
0x1800709e5  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800709ec  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800709f0  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800709f5  call    cs:__imp_NtOpenKey
0x1800709fb  mov     ebx, eax
0x1800709fd  test    eax, eax
0x1800709ff  js      loc_180070ABA
0x180070a05  lea     rdx, aAdmininfo; "AdminInfo"
0x180070a0c  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x180070a10  call    cs:__imp_RtlInitUnicodeString
0x180070a16  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180070a1a  lea     rax, [rbp+57h+var_58]
0x180070a1e  mov     [rsp+0E0h+DataSize], edi; DataSize
0x180070a22  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180070a26  mov     r9d, 3; Type
0x180070a2c  mov     [rsp+0E0h+Data], rax; Data
0x180070a31  xor     r8d, r8d; TitleIndex
0x180070a34  call    cs:__imp_NtSetValueKey
0x180070a3a  mov     ebx, eax
0x180070a3c  test    eax, eax
0x180070a3e  js      short loc_180070A68
0x180070a40  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180070a44  call    cs:__imp_NtFlushKey
0x180070a4a  test    eax, eax
0x180070a4c  jns     short loc_180070A8F
0x180070a4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180070a55  test    byte ptr [rcx+44h], 80h
0x180070a59  jz      short loc_180070A8F
0x180070a5b  cmp     byte ptr [rcx+41h], 2
0x180070a5f  jb      short loc_180070A8F
0x180070a61  mov     edx, 87h
0x180070a66  jmp     short loc_180070A80
0x180070a68  mov     rcx, cs:WPP_GLOBAL_Control
0x180070a6f  test    byte ptr [rcx+44h], 80h
0x180070a73  jz      short loc_180070A8F
0x180070a75  cmp     byte ptr [rcx+41h], 2
0x180070a79  jb      short loc_180070A8F
0x180070a7b  mov     edx, 88h
0x180070a80  mov     rcx, [rcx+38h]
0x180070a84  mov     r9d, ebx
0x180070a87  mov     r8, r14
0x180070a8a  call    WPP_SF_d
0x180070a8f  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180070a93  call    cs:__imp_NtClose
0x180070a99  test    eax, eax
0x180070a9b  jns     short loc_180070AFB
0x180070a9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180070aa4  test    byte ptr [rcx+44h], 80h
0x180070aa8  jz      short loc_180070B02
0x180070aaa  cmp     byte ptr [rcx+41h], 2
0x180070aae  jb      short loc_180070B02
0x180070ab0  mov     edx, 89h
0x180070ab5  mov     r9d, eax
0x180070ab8  jmp     short loc_180070AEF
0x180070aba  mov     rcx, cs:WPP_GLOBAL_Control
0x180070ac1  test    byte ptr [rcx+44h], 80h
0x180070ac5  jz      short loc_180070B02
0x180070ac7  cmp     byte ptr [rcx+41h], 2
0x180070acb  jb      short loc_180070B02
0x180070acd  mov     edx, 8Ah
0x180070ad2  jmp     short loc_180070AB5
0x180070ad4  mov     rcx, cs:WPP_GLOBAL_Control
0x180070adb  test    byte ptr [rcx+44h], 80h
0x180070adf  jz      short loc_180070B02
0x180070ae1  cmp     byte ptr [rcx+41h], 2
0x180070ae5  jb      short loc_180070B02
0x180070ae7  mov     edx, 8Bh
0x180070aec  mov     r9d, ebx
0x180070aef  mov     rcx, [rcx+38h]
0x180070af3  mov     r8, r14
0x180070af6  call    WPP_SF_d
0x180070afb  mov     rcx, cs:WPP_GLOBAL_Control
0x180070b02  lea     rax, [rbp+57h+var_58]
0x180070b06  mov     byte ptr [rax], 0
0x180070b09  inc     rax
0x180070b0c  sub     rdi, 1
0x180070b10  jnz     short loc_180070B06
0x180070b12  test    dword ptr [rcx+44h], 20000h
0x180070b19  jz      short loc_180070B33
0x180070b1b  mov     rcx, [rcx+38h]
0x180070b1f  mov     edx, 8Ch
0x180070b24  mov     r9d, ebx
0x180070b27  mov     dword ptr [rsp+0E0h+Data], ebx
0x180070b2b  mov     r8, r14
0x180070b2e  call    WPP_SF_Dd
0x180070b33  mov     eax, ebx
0x180070b35  mov     rcx, [rbp+57h+var_30]
0x180070b39  xor     rcx, rsp; StackCookie
0x180070b3c  call    __security_check_cookie
0x180070b41  add     rsp, 0C8h
0x180070b48  pop     r14
0x180070b4a  pop     rdi
0x180070b4b  pop     rbx
0x180070b4c  pop     rbp
0x180070b4d  retn
```
