# SampIsSetupInProgress(uchar *)

- ea: `0x1800ac464`
- end: `0x1800ac743`
- name: `?SampIsSetupInProgress@@YAEPEAE@Z`
- size: `735`
- prototype: `unsigned __int8 __fastcall(unsigned __int8 *)`
- caller_count: `10`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006ce50`
- `0x1800792dc`
- `0x1800799a8`
- `0x18007bd40`
- `0x18007c584`
- `0x180087e50`
- `0x1800888c0`
- `0x18008e510`
- `0x180095290`
- `0x180098c94`

## callees

- `0x18002cd80`
- `0x1800372ac`
- `0x1800ac464`

## import_xrefs

- `ntdll!NtOpenKey` at `0x1800ac4ff`
- `ntdll!NtOpenKey` at `0x1800ac4ff`
- `ntdll!NtQueryValueKey` at `0x1800ac54d`
- `ntdll!NtQueryValueKey` at `0x1800ac5a0`
- `ntdll!NtQueryValueKey` at `0x1800ac623`
- `ntdll!NtQueryValueKey` at `0x1800ac672`
- `ntdll!NtQueryValueKey` at `0x1800ac54d`
- `ntdll!NtQueryValueKey` at `0x1800ac5a0`
- `ntdll!NtQueryValueKey` at `0x1800ac623`
- `ntdll!NtQueryValueKey` at `0x1800ac672`
- `ntdll!RtlFreeHeap` at `0x1800ac5dd`
- `ntdll!RtlFreeHeap` at `0x1800ac6af`
- `ntdll!RtlFreeHeap` at `0x1800ac5dd`
- `ntdll!RtlFreeHeap` at `0x1800ac6af`
- `ntdll!RtlAllocateHeap` at `0x1800ac573`
- `ntdll!RtlAllocateHeap` at `0x1800ac643`
- `ntdll!RtlAllocateHeap` at `0x1800ac573`
- `ntdll!RtlAllocateHeap` at `0x1800ac643`
- `ntdll!NtClose` at `0x1800ac6b9`
- `ntdll!NtClose` at `0x1800ac6b9`
- `ntdll!RtlInitUnicodeString` at `0x1800ac4c4`
- `ntdll!RtlInitUnicodeString` at `0x1800ac518`
- `ntdll!RtlInitUnicodeString` at `0x1800ac5ee`
- `ntdll!RtlInitUnicodeString` at `0x1800ac4c4`
- `ntdll!RtlInitUnicodeString` at `0x1800ac518`
- `ntdll!RtlInitUnicodeString` at `0x1800ac5ee`

## string_xrefs

- `0x1800ac4a3`: `\Registry\Machine\System\Setup`

## pseudocode

```c
bool __fastcall SampIsSetupInProgress(bool *a1)
{
  bool v2; // di
  bool v3; // si
  NTSTATUS v4; // eax
  NTSTATUS v5; // eax
  __int128 *Heap; // rbx
  NTSTATUS v7; // eax
  __int128 *p_KeyValueInformation; // rbx
  PUNICODE_STRING v9; // rcx
  ULONG ResultLength; // [rsp+30h] [rbp-59h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-51h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-9h] BYREF
  __int128 KeyValueInformation; // [rsp+90h] [rbp+7h] BYREF
  int v17; // [rsp+A0h] [rbp+17h]

  KeyHandle = 0;
  ResultLength = 0;
  v2 = 0;
  v3 = 0;
  DestinationString = 0;
  ValueName = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\Setup");
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v4 >= 0 )
  {
    RtlInitUnicodeString(&ValueName, L"SystemSetupInProgress");
    v17 = 0;
    KeyValueInformation = 0;
    ResultLength = 20;
    v5 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x14u, &ResultLength);
    if ( v5 == -1073741789 )
    {
      Heap = (__int128 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, ResultLength);
      if ( !Heap )
        goto LABEL_9;
      v5 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, Heap, ResultLength, &ResultLength);
    }
    else
    {
      Heap = &KeyValueInformation;
    }
    if ( v5 >= 0 && *((_DWORD *)Heap + 2) == 4 )
      v2 = *((_DWORD *)Heap + 3) != 0;
LABEL_9:
    if ( Heap != &KeyValueInformation )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    RtlInitUnicodeString(&ValueName, L"UpgradeInProgress");
    v17 = 0;
    KeyValueInformation = 0;
    ResultLength = 20;
    v7 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x14u, &ResultLength);
    if ( v7 == -1073741789 )
    {
      p_KeyValueInformation = (__int128 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, ResultLength);
      if ( !p_KeyValueInformation )
      {
LABEL_18:
        if ( p_KeyValueInformation != &KeyValueInformation )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, p_KeyValueInformation);
        NtClose(KeyHandle);
        goto LABEL_24;
      }
      v7 = NtQueryValueKey(
             KeyHandle,
             &ValueName,
             KeyValuePartialInformation,
             p_KeyValueInformation,
             ResultLength,
             &ResultLength);
    }
    else
    {
      p_KeyValueInformation = &KeyValueInformation;
    }
    if ( v7 >= 0 && *((_DWORD *)p_KeyValueInformation + 2) == 4 )
      v3 = *((_DWORD *)p_KeyValueInformation + 3) != 0;
    goto LABEL_18;
  }
  v9 = WPP_GLOBAL_Control;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 4) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 173, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, (unsigned int)v4);
LABEL_24:
    v9 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    *a1 = v3;
    v9 = WPP_GLOBAL_Control;
  }
  if ( (*(_DWORD *)(&v9[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_d(v9[3].Buffer, 174, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x1800ac464  push    rbp
0x1800ac466  push    rbx
0x1800ac467  push    rsi
0x1800ac468  push    rdi
0x1800ac469  push    r13
0x1800ac46b  push    r15
0x1800ac46d  lea     rbp, [rsp-2Fh]
0x1800ac472  sub     rsp, 0B8h
0x1800ac479  mov     rax, cs:__security_cookie
0x1800ac480  xor     rax, rsp
0x1800ac483  mov     [rbp+57h+var_38], rax
0x1800ac487  xorps   xmm0, xmm0
0x1800ac48a  mov     [rbp+57h+KeyHandle], 0
0x1800ac492  mov     r15, rcx
0x1800ac495  mov     [rbp+57h+var_B0], 0
0x1800ac49c  xorps   xmm1, xmm1
0x1800ac49f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800ac4a3  lea     rdx, aRegistryMachin_4; "\\Registry\\Machine\\System\\Setup"
0x1800ac4aa  xor     dil, dil
0x1800ac4ad  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800ac4b1  xor     sil, sil
0x1800ac4b4  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800ac4b8  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ac4bc  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800ac4c0  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x1800ac4c4  call    cs:__imp_RtlInitUnicodeString
0x1800ac4ca  lea     rax, [rbp+57h+DestinationString]
0x1800ac4ce  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800ac4d6  xorps   xmm0, xmm0
0x1800ac4d9  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800ac4dd  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800ac4e1  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800ac4e9  mov     edx, 20019h; DesiredAccess
0x1800ac4ee  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800ac4f6  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800ac4fa  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ac4ff  call    cs:__imp_NtOpenKey
0x1800ac505  test    eax, eax
0x1800ac507  js      loc_1800AC6C1
0x1800ac50d  lea     rdx, aSystemsetupinp; "SystemSetupInProgress"
0x1800ac514  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1800ac518  call    cs:__imp_RtlInitUnicodeString
0x1800ac51e  xor     eax, eax
0x1800ac520  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1800ac524  mov     [rbp+57h+var_40], eax
0x1800ac527  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1800ac52b  xorps   xmm0, xmm0
0x1800ac52e  movups  [rbp+57h+KeyValueInformation], xmm0
0x1800ac532  lea     ecx, [rax+14h]
0x1800ac535  lea     rax, [rbp+57h+var_B0]
0x1800ac539  mov     [rbp+57h+var_B0], ecx
0x1800ac53c  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1800ac541  lea     r8d, [rcx-12h]; KeyValueInformationClass
0x1800ac545  mov     [rsp+0E0h+Length], ecx; Length
0x1800ac549  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800ac54d  call    cs:__imp_NtQueryValueKey
0x1800ac553  mov     r13d, 1
0x1800ac559  cmp     eax, 0C0000023h
0x1800ac55e  jnz     short loc_1800AC5A8
0x1800ac560  mov     rcx, gs:60h
0x1800ac569  xor     edx, edx; Flags
0x1800ac56b  mov     r8d, [rbp+57h+var_B0]; Size
0x1800ac56f  mov     rcx, [rcx+30h]; HeapHandle
0x1800ac573  call    cs:__imp_RtlAllocateHeap
0x1800ac579  mov     rbx, rax
0x1800ac57c  test    rax, rax
0x1800ac57f  jz      short loc_1800AC5C2
0x1800ac581  mov     ecx, [rbp+57h+var_B0]
0x1800ac584  lea     rax, [rbp+57h+var_B0]
0x1800ac588  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1800ac58d  lea     r8d, [r13+1]; KeyValueInformationClass
0x1800ac591  mov     [rsp+0E0h+Length], ecx; Length
0x1800ac595  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1800ac599  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800ac59d  mov     r9, rbx; KeyValueInformation
0x1800ac5a0  call    cs:__imp_NtQueryValueKey
0x1800ac5a6  jmp     short loc_1800AC5AC
0x1800ac5a8  lea     rbx, [rbp+57h+KeyValueInformation]
0x1800ac5ac  test    eax, eax
0x1800ac5ae  js      short loc_1800AC5C2
0x1800ac5b0  cmp     dword ptr [rbx+8], 4
0x1800ac5b4  jnz     short loc_1800AC5C2
0x1800ac5b6  cmp     dword ptr [rbx+0Ch], 0
0x1800ac5ba  movzx   edi, dil
0x1800ac5be  cmovnz  edi, r13d
0x1800ac5c2  lea     rax, [rbp+57h+KeyValueInformation]
0x1800ac5c6  cmp     rbx, rax
0x1800ac5c9  jz      short loc_1800AC5E3
0x1800ac5cb  mov     rcx, gs:60h
0x1800ac5d4  mov     r8, rbx; P
0x1800ac5d7  xor     edx, edx; Flags
0x1800ac5d9  mov     rcx, [rcx+30h]; HeapHandle
0x1800ac5dd  call    cs:__imp_RtlFreeHeap
0x1800ac5e3  lea     rdx, aUpgradeinprogr; "UpgradeInProgress"
0x1800ac5ea  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1800ac5ee  call    cs:__imp_RtlInitUnicodeString
0x1800ac5f4  xor     eax, eax
0x1800ac5f6  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1800ac5fa  mov     [rbp+57h+var_40], eax
0x1800ac5fd  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1800ac601  xorps   xmm0, xmm0
0x1800ac604  movups  [rbp+57h+KeyValueInformation], xmm0
0x1800ac608  lea     ecx, [rax+14h]
0x1800ac60b  lea     rax, [rbp+57h+var_B0]
0x1800ac60f  mov     [rbp+57h+var_B0], ecx
0x1800ac612  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1800ac617  lea     r8d, [rcx-12h]; KeyValueInformationClass
0x1800ac61b  mov     [rsp+0E0h+Length], ecx; Length
0x1800ac61f  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800ac623  call    cs:__imp_NtQueryValueKey
0x1800ac629  cmp     eax, 0C0000023h
0x1800ac62e  jnz     short loc_1800AC67A
0x1800ac630  mov     rcx, gs:60h
0x1800ac639  xor     edx, edx; Flags
0x1800ac63b  mov     r8d, [rbp+57h+var_B0]; Size
0x1800ac63f  mov     rcx, [rcx+30h]; HeapHandle
0x1800ac643  call    cs:__imp_RtlAllocateHeap
0x1800ac649  mov     rbx, rax
0x1800ac64c  test    rax, rax
0x1800ac64f  jz      short loc_1800AC694
0x1800ac651  mov     ecx, [rbp+57h+var_B0]
0x1800ac654  lea     rax, [rbp+57h+var_B0]
0x1800ac658  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1800ac65d  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1800ac661  mov     [rsp+0E0h+Length], ecx; Length
0x1800ac665  mov     r9, rbx; KeyValueInformation
0x1800ac668  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800ac66c  mov     r8d, 2; KeyValueInformationClass
0x1800ac672  call    cs:__imp_NtQueryValueKey
0x1800ac678  jmp     short loc_1800AC67E
0x1800ac67a  lea     rbx, [rbp+57h+KeyValueInformation]
0x1800ac67e  test    eax, eax
0x1800ac680  js      short loc_1800AC694
0x1800ac682  cmp     dword ptr [rbx+8], 4
0x1800ac686  jnz     short loc_1800AC694
0x1800ac688  cmp     dword ptr [rbx+0Ch], 0
0x1800ac68c  movzx   esi, sil
0x1800ac690  cmovnz  esi, r13d
0x1800ac694  lea     rax, [rbp+57h+KeyValueInformation]
0x1800ac698  cmp     rbx, rax
0x1800ac69b  jz      short loc_1800AC6B5
0x1800ac69d  mov     rcx, gs:60h
0x1800ac6a6  mov     r8, rbx; P
0x1800ac6a9  xor     edx, edx; Flags
0x1800ac6ab  mov     rcx, [rcx+30h]; HeapHandle
0x1800ac6af  call    cs:__imp_RtlFreeHeap
0x1800ac6b5  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800ac6b9  call    cs:__imp_NtClose
0x1800ac6bf  jmp     short loc_1800AC6EC
0x1800ac6c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac6c8  test    byte ptr [rcx+44h], 4
0x1800ac6cc  jz      short loc_1800AC6F3
0x1800ac6ce  cmp     byte ptr [rcx+41h], 2
0x1800ac6d2  jb      short loc_1800AC6F3
0x1800ac6d4  mov     rcx, [rcx+38h]
0x1800ac6d8  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x1800ac6df  mov     edx, 0ADh
0x1800ac6e4  mov     r9d, eax
0x1800ac6e7  call    WPP_SF_d
0x1800ac6ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac6f3  test    r15, r15
0x1800ac6f6  jz      short loc_1800AC702
0x1800ac6f8  mov     [r15], sil
0x1800ac6fb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ac702  test    dword ptr [rcx+44h], 20000h
0x1800ac709  jz      short loc_1800AC724
0x1800ac70b  mov     rcx, [rcx+38h]
0x1800ac70f  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x1800ac716  movzx   r9d, dil
0x1800ac71a  mov     edx, 0AEh
0x1800ac71f  call    WPP_SF_d
0x1800ac724  mov     al, dil
0x1800ac727  mov     rcx, [rbp+57h+var_38]
0x1800ac72b  xor     rcx, rsp; StackCookie
0x1800ac72e  call    __security_check_cookie
0x1800ac733  add     rsp, 0B8h
0x1800ac73a  pop     r15
0x1800ac73c  pop     r13
0x1800ac73e  pop     rdi
0x1800ac73f  pop     rsi
0x1800ac740  pop     rbx
0x1800ac741  pop     rbp
0x1800ac742  retn
```
