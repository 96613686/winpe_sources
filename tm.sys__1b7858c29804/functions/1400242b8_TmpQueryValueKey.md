# TmpQueryValueKey

- ea: `0x1400242b8`
- end: `0x140024423`
- name: `TmpQueryValueKey`
- size: `363`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400018f8`
- `0x14000dff0`

## callees

- `0x1400242b8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002438c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002438c`
- `ntoskrnl!ZwOpenKey` at `0x140024318`
- `ntoskrnl!ZwOpenKey` at `0x140024318`
- `ntoskrnl!ZwClose` at `0x140024335`
- `ntoskrnl!ZwClose` at `0x1400243e8`
- `ntoskrnl!ZwClose` at `0x140024335`
- `ntoskrnl!ZwClose` at `0x1400243e8`
- `ntoskrnl!ZwQueryValueKey` at `0x14002436c`
- `ntoskrnl!ZwQueryValueKey` at `0x14002436c`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x1400243bd`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x1400243bd`

## pseudocode

```c
NTSTATUS __fastcall TmpQueryValueKey(UNICODE_STRING *a1, UNICODE_STRING *a2, ULONG *a3, PVOID *a4, _BYTE *a5)
{
  NTSTATUS result; // eax
  ULONG Length; // edi
  _BYTE *i; // r14
  NTSTATUS v11; // ebx
  PVOID PoolWithQuotaTag; // rax
  void *KeyHandle; // [rsp+30h] [rbp-40h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+A0h] [rbp+30h] BYREF

  ObjectAttributes.ObjectName = a1;
  KeyHandle = 0;
  ResultLength = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    if ( a2 )
    {
      Length = *a3;
      for ( i = a5; ; *i = 1 )
      {
        v11 = ZwQueryValueKey(KeyHandle, a2, KeyValueFullInformation, *a4, Length, &ResultLength);
        if ( v11 != -2147483643 )
          break;
        if ( *i )
        {
          ExFreePoolWithTag(*a4, 0);
          *a3 = 0;
          *a4 = 0;
          *i = 0;
        }
        Length += 256;
        PoolWithQuotaTag = ExAllocatePoolWithQuotaTag((POOL_TYPE)9, Length, 0x78706D54u);
        if ( !PoolWithQuotaTag )
          return -1073741801;
        *a4 = PoolWithQuotaTag;
        *a3 = Length;
      }
      ZwClose(KeyHandle);
      if ( v11 >= 0 && !*((_DWORD *)*a4 + 3) )
        return -1073741772;
      return v11;
    }
    else
    {
      ZwClose(KeyHandle);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400242b8  mov     [rsp-28h+arg_8], rbx
0x1400242bd  mov     [rsp-28h+arg_10], rsi
0x1400242c2  push    rbp
0x1400242c3  push    rdi
0x1400242c4  push    r12
0x1400242c6  push    r14
0x1400242c8  push    r15
0x1400242ca  mov     rbp, rsp
0x1400242cd  sub     rsp, 70h
0x1400242d1  mov     r15, r8
0x1400242d4  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x1400242d8  mov     r12, rdx
0x1400242db  mov     [rbp+KeyHandle], 0
0x1400242e3  xor     eax, eax
0x1400242e5  mov     [rbp+arg_0], 0
0x1400242ec  xorps   xmm0, xmm0
0x1400242ef  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x1400242f3  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400242f7  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400242ff  mov     edx, 20019h; DesiredAccess
0x140024304  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14002430c  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140024310  mov     rsi, r9
0x140024313  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140024318  call    cs:__imp_ZwOpenKey
0x14002431f  nop     dword ptr [rax+rax+00h]
0x140024324  test    eax, eax
0x140024326  js      loc_140024409
0x14002432c  test    r12, r12
0x14002432f  jnz     short loc_140024348
0x140024331  mov     rcx, [rbp+KeyHandle]; Handle
0x140024335  call    cs:__imp_ZwClose
0x14002433c  nop     dword ptr [rax+rax+00h]
0x140024341  xor     eax, eax
0x140024343  jmp     loc_140024409
0x140024348  mov     edi, [r15]
0x14002434b  mov     r14, [rbp+arg_20]
0x14002434f  mov     r9, [rsi]; KeyValueInformation
0x140024352  lea     rax, [rbp+arg_0]
0x140024356  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14002435a  mov     r8d, 1; KeyValueInformationClass
0x140024360  mov     [rsp+70h+ResultLength], rax; ResultLength
0x140024365  mov     rdx, r12; ValueName
0x140024368  mov     [rsp+70h+Length], edi; Length
0x14002436c  call    cs:__imp_ZwQueryValueKey
0x140024373  nop     dword ptr [rax+rax+00h]
0x140024378  mov     ebx, eax
0x14002437a  cmp     eax, 80000005h
0x14002437f  jnz     short loc_1400243E4
0x140024381  cmp     byte ptr [r14], 0
0x140024385  jz      short loc_1400243AA
0x140024387  mov     rcx, [rsi]; P
0x14002438a  xor     edx, edx; Tag
0x14002438c  call    cs:__imp_ExFreePoolWithTag
0x140024393  nop     dword ptr [rax+rax+00h]
0x140024398  mov     dword ptr [r15], 0
0x14002439f  mov     qword ptr [rsi], 0
0x1400243a6  mov     byte ptr [r14], 0
0x1400243aa  add     edi, 100h
0x1400243b0  mov     ecx, 9; PoolType
0x1400243b5  mov     edx, edi; NumberOfBytes
0x1400243b7  mov     r8d, 78706D54h; Tag
0x1400243bd  call    cs:__imp_ExAllocatePoolWithQuotaTag
0x1400243c4  nop     dword ptr [rax+rax+00h]
0x1400243c9  test    rax, rax
0x1400243cc  jz      short loc_1400243DD
0x1400243ce  mov     [rsi], rax
0x1400243d1  mov     [r15], edi
0x1400243d4  mov     byte ptr [r14], 1
0x1400243d8  jmp     loc_14002434F
0x1400243dd  mov     eax, 0C0000017h
0x1400243e2  jmp     short loc_140024409
0x1400243e4  mov     rcx, [rbp+KeyHandle]; Handle
0x1400243e8  call    cs:__imp_ZwClose
0x1400243ef  nop     dword ptr [rax+rax+00h]
0x1400243f4  test    ebx, ebx
0x1400243f6  js      short loc_140024407
0x1400243f8  mov     rax, [rsi]
0x1400243fb  mov     ecx, 0C0000034h
0x140024400  cmp     dword ptr [rax+0Ch], 0
0x140024404  cmovz   ebx, ecx
0x140024407  mov     eax, ebx
0x140024409  lea     r11, [rsp+70h+var_s0]
0x14002440e  mov     rbx, [r11+38h]
0x140024412  mov     rsi, [r11+40h]
0x140024416  mov     rsp, r11
0x140024419  pop     r15
0x14002441b  pop     r14
0x14002441d  pop     r12
0x14002441f  pop     rdi
0x140024420  pop     rbp
0x140024421  retn
```
