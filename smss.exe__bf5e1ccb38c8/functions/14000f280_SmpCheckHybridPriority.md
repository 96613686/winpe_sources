# SmpCheckHybridPriority

- ea: `0x14000f280`
- end: `0x14000f3e4`
- name: `SmpCheckHybridPriority`
- size: `356`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000f6f4`
- `0x140010344`

## callees

- `0x14000f280`
- `0x14001cc40`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x14000f354`
- `ntdll!RtlComputeCrc32` at `0x14000f354`
- `ntdll!NtQueryValueKey` at `0x14000f2fe`
- `ntdll!NtQueryValueKey` at `0x14000f2fe`

## pseudocode

```c
NTSTATUS __fastcall SmpCheckHybridPriority(int a1, _DWORD *a2, int *a3)
{
  NTSTATUS result; // eax
  __int64 i; // rcx
  int v8; // ebx
  __int64 j; // rdx
  __int64 v10; // rcx
  unsigned int v11; // ecx
  ULONG ResultLength; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+38h] [rbp-48h] BYREF
  __int128 KeyValueInformation; // [rsp+48h] [rbp-38h] BYREF
  __int128 v15; // [rsp+58h] [rbp-28h]
  int v16; // [rsp+68h] [rbp-18h]

  *(_QWORD *)&ValueName.Length = 3014700;
  ResultLength = 0;
  ValueName.Buffer = L"PagefileHybridPriority";
  v16 = 0;
  KeyValueInformation = 0;
  v15 = 0;
  result = NtQueryValueKey(
             SmpMmKey,
             &ValueName,
             KeyValuePartialInformationAlign64,
             &KeyValueInformation,
             0x24u,
             &ResultLength);
  if ( result < 0 )
    return result;
  if ( (_QWORD)KeyValueInformation != 0x1800000003LL )
    return -1073741275;
  for ( i = 0; i != 20; ++i )
    *((_BYTE *)&KeyValueInformation + i + 12) ^= BYTE8(KeyValueInformation);
  if ( HIDWORD(KeyValueInformation) != 3 )
    return -1073741701;
  if ( BYTE4(v15) > 1u )
    return -1073741701;
  v8 = DWORD2(KeyValueInformation);
  DWORD2(KeyValueInformation) = 0;
  DWORD2(KeyValueInformation) = RtlComputeCrc32(0, (PUCHAR)&KeyValueInformation + 8, 0x18u);
  if ( DWORD2(KeyValueInformation) != v8 )
    return -1073741701;
  for ( j = 0; (unsigned int)j < BYTE4(v15); j = (unsigned int)(j + 1) )
  {
    if ( (unsigned int)*((unsigned __int16 *)&v15 + 4 * j + 6) - 1 > 0xFD )
      return -1073741701;
  }
  v10 = 0;
  if ( BYTE4(v15) )
  {
    while ( *((_DWORD *)&v15 + 2 * v10 + 2) != a1 )
    {
      v10 = (unsigned int)(v10 + 1);
      if ( (unsigned int)v10 >= BYTE4(v15) )
        goto LABEL_15;
    }
    goto LABEL_16;
  }
LABEL_15:
  if ( (unsigned int)v10 >= BYTE4(v15) )
    return -1073741275;
LABEL_16:
  v11 = *((_DWORD *)&v15 + 2 * v10 + 3);
  *a2 = (unsigned __int16)v11;
  if ( a3 )
    *a3 = HIWORD(v11) & 1;
  return 0;
}

```

## disassembly

```asm
0x14000f280  mov     [rsp-18h+arg_0], rbx
0x14000f285  mov     [rsp-18h+arg_18], rsi
0x14000f28a  push    rbp
0x14000f28b  push    rdi
0x14000f28c  push    r14
0x14000f28e  mov     rbp, rsp
0x14000f291  sub     rsp, 80h
0x14000f298  mov     rax, cs:__security_cookie
0x14000f29f  xor     rax, rsp
0x14000f2a2  mov     [rbp+var_10], rax
0x14000f2a6  xorps   xmm0, xmm0
0x14000f2a9  mov     qword ptr [rbp+ValueName.Length], 2E002Ch
0x14000f2b1  lea     rax, aPagefilehybrid; "PagefileHybridPriority"
0x14000f2b8  mov     [rbp+var_50], 0
0x14000f2bf  mov     [rbp+ValueName.Buffer], rax
0x14000f2c3  lea     r9, [rbp+KeyValueInformation]; KeyValueInformation
0x14000f2c7  xor     eax, eax
0x14000f2c9  mov     rdi, r8
0x14000f2cc  mov     [rbp+var_18], eax
0x14000f2cf  mov     r14, rdx
0x14000f2d2  lea     rax, [rbp+var_50]
0x14000f2d6  mov     esi, ecx
0x14000f2d8  mov     rcx, cs:SmpMmKey; KeyHandle
0x14000f2df  lea     rdx, [rbp+ValueName]; ValueName
0x14000f2e3  mov     [rsp+80h+ResultLength], rax; ResultLength
0x14000f2e8  mov     r8d, 4; KeyValueInformationClass
0x14000f2ee  mov     [rsp+80h+Length], 24h ; '$'; Length
0x14000f2f6  movups  [rbp+KeyValueInformation], xmm0
0x14000f2fa  movups  [rbp+var_28], xmm0
0x14000f2fe  call    cs:__imp_NtQueryValueKey
0x14000f304  test    eax, eax
0x14000f306  js      loc_14000F3C0
0x14000f30c  cmp     dword ptr [rbp+KeyValueInformation], 3
0x14000f310  jnz     loc_14000F3BB
0x14000f316  mov     r8d, 18h; Length
0x14000f31c  cmp     dword ptr [rbp+KeyValueInformation+4], r8d
0x14000f320  jnz     loc_14000F3BB
0x14000f326  xor     ecx, ecx
0x14000f328  mov     al, byte ptr [rbp+KeyValueInformation+8]
0x14000f32b  xor     byte ptr [rbp+rcx+KeyValueInformation+0Ch], al
0x14000f32f  inc     rcx
0x14000f332  cmp     rcx, 14h
0x14000f336  jnz     short loc_14000F328
0x14000f338  cmp     dword ptr [rbp+KeyValueInformation+0Ch], 3
0x14000f33c  jnz     short loc_14000F3B4
0x14000f33e  cmp     byte ptr [rbp+var_28+4], 1
0x14000f342  ja      short loc_14000F3B4
0x14000f344  mov     ebx, dword ptr [rbp+KeyValueInformation+8]
0x14000f347  lea     rdx, [rbp+KeyValueInformation+8]; Buffer
0x14000f34b  xor     ecx, ecx; InitialCrc
0x14000f34d  mov     dword ptr [rbp+KeyValueInformation+8], 0
0x14000f354  call    cs:__imp_RtlComputeCrc32
0x14000f35a  mov     dword ptr [rbp+KeyValueInformation+8], eax
0x14000f35d  cmp     eax, ebx
0x14000f35f  jnz     short loc_14000F3B4
0x14000f361  xor     edx, edx
0x14000f363  movzx   r8d, byte ptr [rbp+var_28+4]
0x14000f368  cmp     edx, r8d
0x14000f36b  jnb     short loc_14000F380
0x14000f36d  movzx   ecx, word ptr [rbp+rdx*8+var_28+0Ch]
0x14000f372  dec     ecx
0x14000f374  cmp     ecx, 0FDh
0x14000f37a  ja      short loc_14000F3B4
0x14000f37c  inc     edx
0x14000f37e  jmp     short loc_14000F363
0x14000f380  xor     ecx, ecx
0x14000f382  test    r8d, r8d
0x14000f385  jz      short loc_14000F394
0x14000f387  cmp     dword ptr [rbp+rcx*8+var_28+8], esi
0x14000f38b  jz      short loc_14000F399
0x14000f38d  inc     ecx
0x14000f38f  cmp     ecx, r8d
0x14000f392  jb      short loc_14000F387
0x14000f394  cmp     ecx, r8d
0x14000f397  jnb     short loc_14000F3BB
0x14000f399  mov     ecx, dword ptr [rbp+rcx*8+var_28+0Ch]
0x14000f39d  movzx   eax, cx
0x14000f3a0  mov     [r14], eax
0x14000f3a3  test    rdi, rdi
0x14000f3a6  jz      short loc_14000F3B0
0x14000f3a8  shr     ecx, 10h
0x14000f3ab  and     ecx, 1
0x14000f3ae  mov     [rdi], ecx
0x14000f3b0  xor     eax, eax
0x14000f3b2  jmp     short loc_14000F3C0
0x14000f3b4  mov     eax, 0C000007Bh
0x14000f3b9  jmp     short loc_14000F3C0
0x14000f3bb  mov     eax, 0C0000225h
0x14000f3c0  mov     rcx, [rbp+var_10]
0x14000f3c4  xor     rcx, rsp; StackCookie
0x14000f3c7  call    __security_check_cookie
0x14000f3cc  lea     r11, [rsp+80h+var_s0]
0x14000f3d4  mov     rbx, [r11+20h]
0x14000f3d8  mov     rsi, [r11+38h]
0x14000f3dc  mov     rsp, r11
0x14000f3df  pop     r14
0x14000f3e1  pop     rdi
0x14000f3e2  pop     rbp
0x14000f3e3  retn
```
