# IsDisplaySettingsGroupPolicyFlagSet(ushort const *)

- ea: `0x18001df80`
- end: `0x18001e1bf`
- name: `?IsDisplaySettingsGroupPolicyFlagSet@@YAHPEBG@Z`
- size: `575`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001dd74`
- `0x18001de68`

## callees

- `0x18001df80`
- `0x180096e00`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18009a150`
- `ntdll!RtlEqualUnicodeString` at `0x18009a167`
- `ntdll!RtlEqualUnicodeString` at `0x18009a150`
- `ntdll!RtlEqualUnicodeString` at `0x18009a167`
- `ntdll!NtQueryValueKey` at `0x18001e0b5`
- `ntdll!NtQueryValueKey` at `0x18001e10e`
- `ntdll!NtQueryValueKey` at `0x18001e0b5`
- `ntdll!NtQueryValueKey` at `0x18001e10e`
- `ntdll!NtClose` at `0x18001e1b7`
- `ntdll!NtClose` at `0x18001e1b7`
- `ntdll!NtOpenKey` at `0x18001e04d`
- `ntdll!NtOpenKey` at `0x18001e04d`
- `ntdll!RtlInitUnicodeString` at `0x18001e006`
- `ntdll!RtlInitUnicodeString` at `0x18001e017`
- `ntdll!RtlInitUnicodeString` at `0x18001e08f`
- `ntdll!RtlInitUnicodeString` at `0x18001e006`
- `ntdll!RtlInitUnicodeString` at `0x18001e017`
- `ntdll!RtlInitUnicodeString` at `0x18001e08f`
- `ntdll!RtlFreeHeap` at `0x18001e176`
- `ntdll!RtlFreeHeap` at `0x18001e176`
- `ntdll!RtlAllocateHeap` at `0x18001e0d7`
- `ntdll!RtlAllocateHeap` at `0x18001e0d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001dff3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001dff3`

## string_xrefs

- `0x18001e00c`: `\Registry\Machine\Software\Policies\Microsoft\Windows\Display`

## pseudocode

```c
__int64 __fastcall IsDisplaySettingsGroupPolicyFlagSet(PCWSTR SourceString)
{
  unsigned int v3; // esi
  _DWORD *Heap; // rbx
  WCHAR *i; // rcx
  _WORD *v6; // rdi
  unsigned __int64 v7; // r14
  _WORD *v8; // rdx
  WCHAR *v9; // rcx
  WCHAR *v10; // rax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  UNICODE_STRING String2; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v17; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Filename[264]; // [rsp+C0h] [rbp-40h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ResultLength = 0;
  v17 = 0;
  ValueName = 0;
  String2 = 0;
  DestinationString = 0;
  if ( !GetModuleFileNameW(0, Filename, 0x104u) )
    return 0;
  RtlInitUnicodeString(&DestinationString, Filename);
  RtlInitUnicodeString(&v17, L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\Display");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &v17;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
    return 0;
  v3 = 0;
  RtlInitUnicodeString(&ValueName, SourceString);
  if ( NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, 0, 0, &ResultLength) == -1073741789 )
  {
    Heap = RtlAllocateHeap(pUserHeap, 8u, ResultLength);
    if ( Heap )
    {
      if ( NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, Heap, ResultLength, &ResultLength) >= 0
        && Heap[1] == 1 )
      {
        for ( i = &DestinationString.Buffer[(unsigned __int64)DestinationString.Length >> 1];
              i > DestinationString.Buffer;
              --i )
        {
          if ( *i == 92 || *i == 58 )
          {
            ++i;
            break;
          }
        }
        String2.Buffer = i;
        v6 = Heap + 3;
        String2.Length = DestinationString.Length - 2 * (i - DestinationString.Buffer);
        String2.MaximumLength = String2.Length;
        v7 = (unsigned __int64)Heap + 2 * ((unsigned __int64)(unsigned int)Heap[2] >> 1) + 12;
        while ( (unsigned __int64)v6 < v7 )
        {
          v8 = v6;
          String1 = 0;
          do
          {
            if ( *v8 == 59 )
              break;
            if ( !*v8 )
              break;
            ++v8;
          }
          while ( (unsigned __int64)v8 < v7 );
          v9 = v6;
          v10 = v8 - 1;
          v6 = v8 + 1;
          while ( v10 >= v9 && (*v10 == 32 || *v10 == 9) )
            --v10;
          if ( v10 > v9 )
          {
            do
            {
              if ( *v9 != 32 && *v9 != 9 )
                break;
              ++v9;
            }
            while ( v10 > v9 );
            if ( v9 < v10 )
            {
              String1.Buffer = v9;
              String1.Length = 2 * (v10 - v9 + 1);
              String1.MaximumLength = String1.Length;
              if ( RtlEqualUnicodeString(&String1, &DestinationString, 1u)
                || RtlEqualUnicodeString(&String1, &String2, 1u) )
              {
                v3 = 1;
                break;
              }
            }
          }
        }
      }
      RtlFreeHeap(pUserHeap, 0, Heap);
    }
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  return v3;
}

```

## disassembly

```asm
0x18001df80  mov     [rsp-8+arg_8], rbx
0x18001df85  mov     [rsp-8+arg_10], rsi
0x18001df8a  push    rbp
0x18001df8b  push    rdi
0x18001df8c  push    r13
0x18001df8e  push    r14
0x18001df90  push    r15
0x18001df92  lea     rbp, [rsp-1E0h]
0x18001df9a  sub     rsp, 2E0h
0x18001dfa1  mov     rax, cs:__security_cookie
0x18001dfa8  xor     rax, rsp
0x18001dfab  mov     [rbp+200h+var_30], rax
0x18001dfb2  xorps   xmm0, xmm0
0x18001dfb5  lea     rdx, [rbp+200h+Filename]; lpFilename
0x18001dfb9  xorps   xmm1, xmm1
0x18001dfbc  mov     rbx, rcx
0x18001dfbf  xor     r15d, r15d
0x18001dfc2  xor     ecx, ecx; hModule
0x18001dfc4  mov     r8d, 104h; nSize
0x18001dfca  mov     [rsp+300h+KeyHandle], r15
0x18001dfcf  movups  xmmword ptr [rbp+200h+ObjectAttributes.Length], xmm0
0x18001dfd3  mov     [rsp+300h+var_2D0], r15d
0x18001dfd8  movups  xmmword ptr [rbp+200h+ObjectAttributes.ObjectName], xmm0
0x18001dfdc  movups  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001dfe0  movups  xmmword ptr [rbp+200h+var_280.Length], xmm0
0x18001dfe4  movups  xmmword ptr [rsp+300h+ValueName.Length], xmm1
0x18001dfe9  movups  xmmword ptr [rsp+300h+String2.Length], xmm0
0x18001dfee  movups  xmmword ptr [rsp+300h+DestinationString.Length], xmm1
0x18001dff3  call    cs:__imp_GetModuleFileNameW
0x18001dff9  test    eax, eax
0x18001dffb  jz      short loc_18001E057
0x18001dffd  lea     rdx, [rbp+200h+Filename]; SourceString
0x18001e001  lea     rcx, [rsp+300h+DestinationString]; DestinationString
0x18001e006  call    cs:__imp_RtlInitUnicodeString
0x18001e00c  lea     rdx, aRegistryMachin_3; "\\Registry\\Machine\\Software\\Policies"...
0x18001e013  lea     rcx, [rbp+200h+var_280]; DestinationString
0x18001e017  call    cs:__imp_RtlInitUnicodeString
0x18001e01d  lea     rax, [rbp+200h+var_280]
0x18001e021  mov     [rbp+200h+ObjectAttributes.Length], 30h ; '0'
0x18001e028  xorps   xmm0, xmm0
0x18001e02b  mov     [rbp+200h+ObjectAttributes.ObjectName], rax
0x18001e02f  lea     r8, [rbp+200h+ObjectAttributes]; ObjectAttributes
0x18001e033  mov     [rbp+200h+ObjectAttributes.RootDirectory], r15
0x18001e037  mov     edx, 20019h; DesiredAccess
0x18001e03c  mov     [rbp+200h+ObjectAttributes.Attributes], 240h
0x18001e043  lea     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x18001e048  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001e04d  call    cs:__imp_NtOpenKey
0x18001e053  test    eax, eax
0x18001e055  jns     short loc_18001E084
0x18001e057  xor     eax, eax
0x18001e059  mov     rcx, [rbp+200h+var_30]
0x18001e060  xor     rcx, rsp; StackCookie
0x18001e063  call    __security_check_cookie
0x18001e068  lea     r11, [rsp+300h+var_20]
0x18001e070  mov     rbx, [r11+38h]
0x18001e074  mov     rsi, [r11+40h]
0x18001e078  mov     rsp, r11
0x18001e07b  pop     r15
0x18001e07d  pop     r14
0x18001e07f  pop     r13
0x18001e081  pop     rdi
0x18001e082  pop     rbp
0x18001e083  retn
0x18001e084  mov     rdx, rbx; SourceString
0x18001e087  lea     rcx, [rsp+300h+ValueName]; DestinationString
0x18001e08c  mov     esi, r15d
0x18001e08f  call    cs:__imp_RtlInitUnicodeString
0x18001e095  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x18001e09a  lea     rax, [rsp+300h+var_2D0]
0x18001e09f  xor     r9d, r9d; KeyValueInformation
0x18001e0a2  mov     [rsp+300h+ResultLength], rax; ResultLength
0x18001e0a7  lea     rdx, [rsp+300h+ValueName]; ValueName
0x18001e0ac  mov     [rsp+300h+Length], r15d; Length
0x18001e0b1  lea     r8d, [r9+2]; KeyValueInformationClass
0x18001e0b5  call    cs:__imp_NtQueryValueKey
0x18001e0bb  cmp     eax, 0C0000023h
0x18001e0c0  jnz     loc_18001E17C
0x18001e0c6  mov     r8d, [rsp+300h+var_2D0]; Size
0x18001e0cb  mov     edx, 8; Flags
0x18001e0d0  mov     rcx, cs:pUserHeap; HeapHandle
0x18001e0d7  call    cs:__imp_RtlAllocateHeap
0x18001e0dd  mov     rbx, rax
0x18001e0e0  test    rax, rax
0x18001e0e3  jz      loc_18001E17C
0x18001e0e9  mov     ecx, [rsp+300h+var_2D0]
0x18001e0ed  lea     rax, [rsp+300h+var_2D0]
0x18001e0f2  mov     [rsp+300h+ResultLength], rax; ResultLength
0x18001e0f7  lea     rdx, [rsp+300h+ValueName]; ValueName
0x18001e0fc  mov     [rsp+300h+Length], ecx; Length
0x18001e100  mov     r9, rbx; KeyValueInformation
0x18001e103  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x18001e108  mov     r8d, 2; KeyValueInformationClass
0x18001e10e  call    cs:__imp_NtQueryValueKey
0x18001e114  test    eax, eax
0x18001e116  js      short loc_18001E16A
0x18001e118  mov     r13d, 1
0x18001e11e  cmp     [rbx+4], r13d
0x18001e122  jnz     short loc_18001E16A
0x18001e124  movzx   edx, [rsp+300h+DestinationString.Length]
0x18001e129  mov     r8, [rsp+300h+DestinationString.Buffer]
0x18001e12e  mov     eax, edx
0x18001e130  shr     rax, 1
0x18001e133  lea     rcx, [r8+rax*2]
0x18001e137  cmp     rcx, r8
0x18001e13a  ja      short loc_18001E18D
0x18001e13c  mov     [rsp+300h+String2.Buffer], rcx
0x18001e141  lea     rdi, [rbx+0Ch]
0x18001e145  sub     rcx, r8
0x18001e148  sar     rcx, 1
0x18001e14b  add     cx, cx
0x18001e14e  sub     dx, cx
0x18001e151  mov     [rsp+300h+String2.Length], dx
0x18001e156  mov     [rsp+300h+String2.MaximumLength], dx
0x18001e15b  mov     eax, [rbx+8]
0x18001e15e  shr     rax, 1
0x18001e161  lea     r14, [rdi+rax*2]
0x18001e165  cmp     rdi, r14
0x18001e168  jb      short loc_18001E1A7
0x18001e16a  mov     rcx, cs:pUserHeap; HeapHandle
0x18001e171  mov     r8, rbx; P
0x18001e174  xor     edx, edx; Flags
0x18001e176  call    cs:__imp_RtlFreeHeap
0x18001e17c  mov     rcx, [rsp+300h+KeyHandle]; Handle
0x18001e181  test    rcx, rcx
0x18001e184  jnz     short loc_18001E1B7
0x18001e186  mov     eax, esi
0x18001e188  jmp     loc_18001E059
0x18001e18d  cmp     word ptr [rcx], 5Ch ; '\'
0x18001e191  jz      loc_18009A0C0
0x18001e197  cmp     word ptr [rcx], 3Ah ; ':'
0x18001e19b  jz      loc_18009A0C0
0x18001e1a1  sub     rcx, 2
0x18001e1a5  jmp     short loc_18001E137
0x18001e1a7  xorps   xmm0, xmm0
0x18001e1aa  mov     rdx, rdi
0x18001e1ad  movups  xmmword ptr [rsp+300h+String1.Length], xmm0
0x18001e1b2  jmp     loc_18009A0C9
0x18001e1b7  call    cs:__imp_NtClose
0x18001e1bd  jmp     short loc_18001E186
0x18009a0c0  add     rcx, 2
0x18009a0c4  jmp     loc_18001E13C
0x18009a0c9  cmp     word ptr [rdx], 3Bh ; ';'
0x18009a0cd  jz      short loc_18009A0DE
0x18009a0cf  cmp     [rdx], r15w
0x18009a0d3  jz      short loc_18009A0DE
0x18009a0d5  add     rdx, 2
0x18009a0d9  cmp     rdx, r14
0x18009a0dc  jb      short loc_18009A0C9
0x18009a0de  mov     rcx, rdi
0x18009a0e1  lea     rax, [rdx-2]
0x18009a0e5  lea     rdi, [rdx+2]
0x18009a0e9  jmp     short loc_18009A0FB
0x18009a0eb  cmp     word ptr [rax], 20h ; ' '
0x18009a0ef  jz      short loc_18009A0F7
0x18009a0f1  cmp     word ptr [rax], 9
0x18009a0f5  jnz     short loc_18009A100
0x18009a0f7  sub     rax, 2
0x18009a0fb  cmp     rax, rcx
0x18009a0fe  jnb     short loc_18009A0EB
0x18009a100  cmp     rax, rcx
0x18009a103  jbe     loc_18001E165
0x18009a109  cmp     word ptr [rcx], 20h ; ' '
0x18009a10d  jz      short loc_18009A115
0x18009a10f  cmp     word ptr [rcx], 9
0x18009a113  jnz     short loc_18009A11E
0x18009a115  add     rcx, 2
0x18009a119  cmp     rax, rcx
0x18009a11c  ja      short loc_18009A109
0x18009a11e  cmp     rcx, rax
0x18009a121  jnb     loc_18001E165
0x18009a127  sub     rax, rcx
0x18009a12a  mov     [rsp+300h+String1.Buffer], rcx
0x18009a12f  sar     rax, 1
0x18009a132  lea     rdx, [rsp+300h+DestinationString]; String2
0x18009a137  add     ax, r13w
0x18009a13b  lea     rcx, [rsp+300h+String1]; String1
0x18009a140  add     ax, ax
0x18009a143  mov     r8b, r13b; CaseInsensitive
0x18009a146  mov     [rsp+300h+String1.Length], ax
0x18009a14b  mov     [rsp+300h+String1.MaximumLength], ax
0x18009a150  call    cs:__imp_RtlEqualUnicodeString
0x18009a156  test    al, al
0x18009a158  jnz     short loc_18009A175
0x18009a15a  mov     r8b, r13b; CaseInsensitive
0x18009a15d  lea     rdx, [rsp+300h+String2]; String2
0x18009a162  lea     rcx, [rsp+300h+String1]; String1
0x18009a167  call    cs:__imp_RtlEqualUnicodeString
0x18009a16d  test    al, al
0x18009a16f  jz      loc_18001E165
0x18009a175  mov     esi, r13d
0x18009a178  jmp     loc_18001E16A
```
