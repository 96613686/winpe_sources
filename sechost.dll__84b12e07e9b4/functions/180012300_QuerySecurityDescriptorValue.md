# QuerySecurityDescriptorValue

- ea: `0x180012300`
- end: `0x1800125c1`
- name: `QuerySecurityDescriptorValue`
- size: `705`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012100`

## callees

- `0x180012300`
- `0x1800125c8`
- `0x1800195b8`
- `0x18004fa50`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800124b2`
- `ntdll!RtlInitUnicodeString` at `0x1800124b2`
- `ntdll!NtClose` at `0x180012568`
- `ntdll!NtClose` at `0x180012568`
- `ntdll!NtOpenKey` at `0x180012497`
- `ntdll!NtOpenKey` at `0x180012497`
- `ntdll!RtlFreeHeap` at `0x18001254e`
- `ntdll!RtlFreeHeap` at `0x180012591`
- `ntdll!RtlFreeHeap` at `0x18001254e`
- `ntdll!RtlFreeHeap` at `0x180012591`
- `ntdll!NtQueryValueKey` at `0x1800124d8`
- `ntdll!NtQueryValueKey` at `0x18001252b`
- `ntdll!NtQueryValueKey` at `0x1800124d8`
- `ntdll!NtQueryValueKey` at `0x18001252b`

## string_xrefs

- `0x180012401`: `\REGISTRY\MACHINE\Software\Microsoft\SecurityManager\TransientObjects\`
- `0x1800124a7`: `SecurityDescriptor`

## pseudocode

```c
__int64 __fastcall QuerySecurityDescriptorValue(_WORD *a1, _QWORD *a2)
{
  __int64 v4; // rcx
  _WORD *v5; // rax
  NTSTATUS v6; // ebx
  unsigned __int64 v7; // rdi
  _WORD *v8; // r8
  unsigned __int64 v9; // rdx
  __int64 v10; // rax
  const wchar_t *v11; // rcx
  _WORD *v12; // rcx
  NTSTATUS v13; // eax
  void *v14; // rdi
  ULONG ResultLength; // [rsp+30h] [rbp-49h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-41h] BYREF
  PVOID P[2]; // [rsp+40h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-29h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-19h] BYREF
  __int128 KeyValueInformation; // [rsp+90h] [rbp+17h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  *(_OWORD *)P = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  KeyValueInformation = 0;
  if ( !a1 )
  {
    v6 = -1073741811;
    goto LABEL_33;
  }
  v4 = 0x3FFFFFFF;
  v5 = a1;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v4;
  }
  while ( v4 );
  v6 = -1073741811;
  if ( !v4 )
  {
    v6 = -1073741811;
    goto LABEL_33;
  }
  v7 = (-(__int64)(v4 != 0) & (2 * (0x3FFFFFFF - v4))) + 142;
  P[1] = (PVOID)AccessHlprAlloc(v7);
  v8 = P[1];
  if ( !P[1] )
    goto LABEL_7;
  WORD1(P[0]) = v7;
  v9 = v7 >> 1;
  LOWORD(P[0]) = v7 - 2;
  if ( v7 >> 1 )
  {
    if ( v9 > 0x7FFFFFFF )
    {
      *(_WORD *)P[1] = 0;
    }
    else
    {
      v10 = 2147483646;
      v11 = L"\\REGISTRY\\MACHINE\\Software\\Microsoft\\SecurityManager\\TransientObjects\\";
      do
      {
        if ( !v10 )
          break;
        if ( !*v11 )
          break;
        *v8++ = *v11++;
        --v10;
        --v9;
      }
      while ( v9 );
      v12 = v8 - 1;
      v6 = v9 == 0 ? 0x80000005 : 0;
      if ( v9 )
        v12 = v8;
      *v12 = 0;
      if ( !v9 )
        goto LABEL_29;
      v6 = RtlStringCbCatW(P[1], v7, a1);
      if ( v6 < 0 )
        goto LABEL_29;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v6 = NtOpenKey(&KeyHandle, 0x80000000, &ObjectAttributes);
      if ( v6 < 0 )
        goto LABEL_29;
      RtlInitUnicodeString(&DestinationString, L"SecurityDescriptor");
      v13 = NtQueryValueKey(
              KeyHandle,
              &DestinationString,
              KeyValuePartialInformation,
              &KeyValueInformation,
              0x10u,
              &ResultLength);
      v6 = v13;
      if ( v13 < 0 )
      {
        if ( v13 == -2147483643 || v13 == -1073741789 )
        {
          v14 = (void *)AccessHlprAlloc(ResultLength);
          if ( !v14 )
          {
LABEL_7:
            v6 = -1073741801;
            goto LABEL_29;
          }
          v6 = NtQueryValueKey(
                 KeyHandle,
                 &DestinationString,
                 KeyValuePartialInformation,
                 v14,
                 ResultLength,
                 &ResultLength);
          if ( v6 < 0 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
          else
            *a2 = v14;
        }
      }
      else
      {
        v6 = -1073739509;
      }
    }
  }
LABEL_29:
  if ( KeyHandle )
    NtClose(KeyHandle);
LABEL_33:
  if ( P[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180012300  mov     [rsp-8+arg_10], rbx
0x180012305  mov     [rsp-8+arg_18], rsi
0x18001230a  push    rbp
0x18001230b  push    rdi
0x18001230c  push    r12
0x18001230e  push    r14
0x180012310  push    r15
0x180012312  lea     rbp, [rsp-37h]
0x180012317  sub     rsp, 0B0h
0x18001231e  mov     rax, cs:__security_cookie
0x180012325  xor     rax, rsp
0x180012328  mov     [rbp+57h+var_30], rax
0x18001232c  xorps   xmm0, xmm0
0x18001232f  xor     r15d, r15d
0x180012332  xor     eax, eax
0x180012334  mov     [rbp+57h+KeyHandle], r15
0x180012338  mov     [rbp+57h+var_A0], r15d
0x18001233c  xorps   xmm1, xmm1
0x18001233f  mov     r14, rdx
0x180012342  mov     rsi, rcx
0x180012345  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180012349  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18001234d  movups  xmmword ptr [rbp+57h+P], xmm0
0x180012351  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180012355  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180012359  movups  [rbp+57h+KeyValueInformation], xmm1
0x18001235d  test    rcx, rcx
0x180012360  jz      loc_180012574
0x180012366  mov     r8d, 3FFFFFFFh
0x18001236c  lea     r12d, [r15+2]
0x180012370  mov     ecx, r8d
0x180012373  mov     rax, rsi
0x180012376  cmp     [rax], r15w
0x18001237a  jz      short loc_180012385
0x18001237c  add     rax, r12
0x18001237f  sub     rcx, 1
0x180012383  jnz     short loc_180012376
0x180012385  mov     rax, rcx
0x180012388  mov     ebx, 0C000000Dh
0x18001238d  neg     rax
0x180012390  sbb     edx, edx
0x180012392  not     edx
0x180012394  and     edx, ebx
0x180012396  test    rcx, rcx
0x180012399  jz      loc_180012570
0x18001239f  sub     r8, rcx
0x1800123a2  neg     rcx
0x1800123a5  sbb     rax, rax
0x1800123a8  lea     rdi, [r8+r8]
0x1800123ac  and     rdi, rax
0x1800123af  add     rdi, 8Eh
0x1800123b6  mov     rcx, rdi
0x1800123b9  call    AccessHlprAlloc
0x1800123be  mov     [rbp+57h+P+8], rax
0x1800123c2  mov     r8, rax
0x1800123c5  test    rax, rax
0x1800123c8  jnz     short loc_1800123D4
0x1800123ca  mov     ebx, 0C0000017h
0x1800123cf  jmp     loc_18001255F
0x1800123d4  movzx   eax, di
0x1800123d7  mov     word ptr [rbp+57h+P+2], di
0x1800123db  sub     ax, r12w
0x1800123df  mov     rdx, rdi
0x1800123e2  shr     rdx, 1
0x1800123e5  mov     word ptr [rbp+57h+P], ax
0x1800123e9  jz      loc_180012556
0x1800123ef  cmp     rdx, 7FFFFFFFh
0x1800123f6  ja      loc_18001255B
0x1800123fc  mov     eax, 7FFFFFFEh
0x180012401  lea     rcx, aRegistryMachin; "\\REGISTRY\\MACHINE\\Software\\Microsof"...
0x180012408  test    rax, rax
0x18001240b  jz      short loc_18001242A
0x18001240d  movzx   r9d, word ptr [rcx]
0x180012411  test    r9w, r9w
0x180012415  jz      short loc_18001242A
0x180012417  mov     [r8], r9w
0x18001241b  add     rcx, r12
0x18001241e  add     r8, r12
0x180012421  dec     rax
0x180012424  sub     rdx, 1
0x180012428  jnz     short loc_180012408
0x18001242a  mov     rax, rdx
0x18001242d  lea     rcx, [r8-2]
0x180012431  neg     rax
0x180012434  sbb     ebx, ebx
0x180012436  not     ebx
0x180012438  and     ebx, 80000005h
0x18001243e  test    rdx, rdx
0x180012441  cmovnz  rcx, r8
0x180012445  mov     [rcx], r15w
0x180012449  jz      loc_18001255F
0x18001244f  mov     rcx, [rbp+57h+P+8]
0x180012453  mov     r8, rsi
0x180012456  mov     rdx, rdi
0x180012459  call    RtlStringCbCatW
0x18001245e  mov     ebx, eax
0x180012460  test    eax, eax
0x180012462  js      loc_18001255F
0x180012468  lea     rax, [rbp+57h+P]
0x18001246c  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180012473  xorps   xmm0, xmm0
0x180012476  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18001247a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001247e  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x180012482  mov     edx, 80000000h; DesiredAccess
0x180012487  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18001248e  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180012492  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180012497  call    cs:__imp_NtOpenKey
0x18001249d  mov     ebx, eax
0x18001249f  test    eax, eax
0x1800124a1  js      loc_18001255F
0x1800124a7  lea     rdx, aSecuritydescri; "SecurityDescriptor"
0x1800124ae  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800124b2  call    cs:__imp_RtlInitUnicodeString
0x1800124b8  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800124bc  lea     rax, [rbp+57h+var_A0]
0x1800124c0  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x1800124c5  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1800124c9  mov     r8d, r12d; KeyValueInformationClass
0x1800124cc  mov     [rsp+0D0h+Length], 10h; Length
0x1800124d4  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1800124d8  call    cs:__imp_NtQueryValueKey
0x1800124de  mov     ebx, eax
0x1800124e0  test    eax, eax
0x1800124e2  js      short loc_1800124EB
0x1800124e4  mov     ebx, 0C000090Bh
0x1800124e9  jmp     short loc_18001255F
0x1800124eb  cmp     eax, 80000005h
0x1800124f0  jz      short loc_1800124F9
0x1800124f2  cmp     eax, 0C0000023h
0x1800124f7  jnz     short loc_18001255F
0x1800124f9  mov     ecx, [rbp+57h+var_A0]
0x1800124fc  call    AccessHlprAlloc
0x180012501  mov     rdi, rax
0x180012504  test    rax, rax
0x180012507  jz      loc_1800123CA
0x18001250d  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180012511  lea     rax, [rbp+57h+var_A0]
0x180012515  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x18001251a  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18001251e  mov     eax, [rbp+57h+var_A0]
0x180012521  mov     r9, rdi; KeyValueInformation
0x180012524  mov     r8d, r12d; KeyValueInformationClass
0x180012527  mov     [rsp+0D0h+Length], eax; Length
0x18001252b  call    cs:__imp_NtQueryValueKey
0x180012531  mov     ebx, eax
0x180012533  test    eax, eax
0x180012535  js      short loc_18001253C
0x180012537  mov     [r14], rdi
0x18001253a  jmp     short loc_18001255F
0x18001253c  mov     rcx, gs:60h
0x180012545  mov     r8, rdi; P
0x180012548  xor     edx, edx; Flags
0x18001254a  mov     rcx, [rcx+30h]; HeapHandle
0x18001254e  call    cs:__imp_RtlFreeHeap
0x180012554  jmp     short loc_18001255F
0x180012556  test    rdx, rdx
0x180012559  jz      short loc_18001255F
0x18001255b  mov     [r8], r15w
0x18001255f  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180012563  test    rcx, rcx
0x180012566  jz      short loc_180012579
0x180012568  call    cs:__imp_NtClose
0x18001256e  jmp     short loc_180012579
0x180012570  mov     ebx, edx
0x180012572  jmp     short loc_180012579
0x180012574  mov     ebx, 0C000000Dh
0x180012579  mov     r8, [rbp+57h+P+8]; P
0x18001257d  test    r8, r8
0x180012580  jz      short loc_180012597
0x180012582  mov     rcx, gs:60h
0x18001258b  xor     edx, edx; Flags
0x18001258d  mov     rcx, [rcx+30h]; HeapHandle
0x180012591  call    cs:__imp_RtlFreeHeap
0x180012597  mov     eax, ebx
0x180012599  mov     rcx, [rbp+57h+var_30]
0x18001259d  xor     rcx, rsp; StackCookie
0x1800125a0  call    __security_check_cookie
0x1800125a5  lea     r11, [rsp+0D0h+var_20]
0x1800125ad  mov     rbx, [r11+40h]
0x1800125b1  mov     rsi, [r11+48h]
0x1800125b5  mov     rsp, r11
0x1800125b8  pop     r15
0x1800125ba  pop     r14
0x1800125bc  pop     r12
0x1800125be  pop     rdi
0x1800125bf  pop     rbp
0x1800125c0  retn
```
