# NfsCfgMgrpReadRegistryValue

- ea: `0x140013de4`
- end: `0x140013fcc`
- name: `NfsCfgMgrpReadRegistryValue`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140014984`

## callees

- `0x1400122e0`
- `0x140013de4`
- `0x140013fd4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140013f82`
- `ntoskrnl!ZwClose` at `0x140013f82`
- `ntoskrnl!ZwOpenKey` at `0x140013ec5`
- `ntoskrnl!ZwOpenKey` at `0x140013ec5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013f12`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013f9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013f12`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013f9b`
- `ntoskrnl!ExAllocatePool2` at `0x140013e70`
- `ntoskrnl!ExAllocatePool2` at `0x140013f3c`
- `ntoskrnl!ExAllocatePool2` at `0x140013e70`
- `ntoskrnl!ExAllocatePool2` at `0x140013f3c`

## pseudocode

```c
__int64 __fastcall NfsCfgMgrpReadRegistryValue(__int64 a1)
{
  __int64 v2; // rdx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  unsigned __int16 *Pool2; // rsi
  NTSTATUS v10; // ebx
  ULONG v11; // r14d
  NTSTATUS v12; // eax
  unsigned int v13; // eax
  unsigned __int32 v14; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+70h] [rbp+20h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  v2 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 4));
  if ( NfsRefHistoryTracingpGlobal )
    NfsReferenceHistoryCaptureRecord(a1, v2, 0);
  v3 = *(_DWORD *)(a1 + 60);
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      v5 = v4 - 1;
      if ( v5 )
      {
        v6 = v5 - 1;
        if ( v6 )
        {
          v7 = v6 - 1;
          if ( v7 )
          {
            v8 = v7 - 1;
            if ( v8 )
            {
              if ( v8 != 2 )
              {
                Pool2 = 0;
                v10 = -1073741811;
                goto LABEL_20;
              }
            }
          }
        }
      }
    }
  }
  v11 = 128;
  Pool2 = (unsigned __int16 *)ExAllocatePool2(66, 128, 1363300931);
  if ( Pool2 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)((char *)NfsResMgrpRoot + 168);
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v10 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( v10 < 0 )
      goto LABEL_20;
    do
    {
      while ( 1 )
      {
        v12 = NfsCfgMgrpReadRegistryValueFetchAndValidate(a1, KeyHandle, v11, Pool2);
        v10 = v12;
        if ( (v12 == -2147483643 || v12 == -1073741789) && v11 < 0x2000 )
          break;
        if ( v12 != -1073741267 )
          goto LABEL_20;
      }
      ExFreePoolWithTag(Pool2, 0x51425243u);
      v13 = 0x2000;
      if ( 2 * v11 < 0x2000 )
        v13 = 2 * v11;
      v11 = v13;
      Pool2 = (unsigned __int16 *)ExAllocatePool2(66, v13, 1363300931);
    }
    while ( Pool2 );
  }
  v10 = -1073741670;
LABEL_20:
  v14 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 4), 0, 0);
  if ( NfsRefHistoryTracingpGlobal )
    NfsReferenceHistoryCaptureRecord(a1, v14, 1);
  _InterlockedDecrement((volatile signed __int32 *)(a1 + 4));
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x51425243u);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140013de4  mov     [rsp-18h+arg_8], rbx
0x140013de9  mov     [rsp-18h+arg_10], rsi
0x140013dee  push    rbp
0x140013def  push    rdi
0x140013df0  push    r14
0x140013df2  mov     rbp, rsp
0x140013df5  sub     rsp, 50h
0x140013df9  xorps   xmm0, xmm0
0x140013dfc  xor     eax, eax
0x140013dfe  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140013e02  mov     rdi, rcx
0x140013e05  mov     [rbp+KeyHandle], rax
0x140013e09  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140013e0d  lea     edx, [rax+1]
0x140013e10  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140013e14  lock xadd [rcx+4], edx
0x140013e19  inc     edx
0x140013e1b  cmp     cs:NfsRefHistoryTracingpGlobal, rax
0x140013e22  jz      short loc_140013E2C
0x140013e24  xor     r8d, r8d
0x140013e27  call    NfsReferenceHistoryCaptureRecord
0x140013e2c  mov     ecx, [rdi+3Ch]
0x140013e2f  test    ecx, ecx
0x140013e31  jz      short loc_140013E5D
0x140013e33  sub     ecx, 1
0x140013e36  jz      short loc_140013E5D
0x140013e38  sub     ecx, 1
0x140013e3b  jz      short loc_140013E5D
0x140013e3d  sub     ecx, 1
0x140013e40  jz      short loc_140013E5D
0x140013e42  sub     ecx, 1
0x140013e45  jz      short loc_140013E5D
0x140013e47  sub     ecx, 1
0x140013e4a  jz      short loc_140013E5D
0x140013e4c  cmp     ecx, 2
0x140013e4f  jz      short loc_140013E5D
0x140013e51  xor     esi, esi
0x140013e53  mov     ebx, 0C000000Dh
0x140013e58  jmp     loc_140013F55
0x140013e5d  mov     r14d, 80h
0x140013e63  mov     r8d, 51425243h
0x140013e69  mov     edx, r14d
0x140013e6c  lea     ecx, [r14-3Eh]
0x140013e70  call    cs:__imp_ExAllocatePool2
0x140013e77  nop     dword ptr [rax+rax+00h]
0x140013e7c  mov     rsi, rax
0x140013e7f  test    rax, rax
0x140013e82  jz      loc_140013F50
0x140013e88  mov     rcx, cs:NfsResMgrpRoot
0x140013e8f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140013e93  add     rcx, 0A8h
0x140013e9a  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140013ea1  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x140013ea5  xorps   xmm0, xmm0
0x140013ea8  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140013eac  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140013eb4  mov     edx, 20019h; DesiredAccess
0x140013eb9  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140013ec0  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140013ec5  call    cs:__imp_ZwOpenKey
0x140013ecc  nop     dword ptr [rax+rax+00h]
0x140013ed1  mov     ebx, eax
0x140013ed3  test    eax, eax
0x140013ed5  js      short loc_140013F55
0x140013ed7  mov     rdx, [rbp+KeyHandle]
0x140013edb  mov     r9, rsi
0x140013ede  mov     r8d, r14d
0x140013ee1  mov     rcx, rdi
0x140013ee4  call    NfsCfgMgrpReadRegistryValueFetchAndValidate
0x140013ee9  mov     ebx, eax
0x140013eeb  cmp     eax, 80000005h
0x140013ef0  jz      short loc_140013EFD
0x140013ef2  cmp     eax, 0C0000023h
0x140013ef7  jnz     loc_140013FBF
0x140013efd  cmp     r14d, 2000h
0x140013f04  jnb     loc_140013FBF
0x140013f0a  mov     edx, 51425243h; Tag
0x140013f0f  mov     rcx, rsi; P
0x140013f12  call    cs:__imp_ExFreePoolWithTag
0x140013f19  nop     dword ptr [rax+rax+00h]
0x140013f1e  lea     ecx, [r14+r14]
0x140013f22  mov     eax, 2000h
0x140013f27  cmp     ecx, eax
0x140013f29  mov     r8d, 51425243h
0x140013f2f  cmovb   eax, ecx
0x140013f32  mov     ecx, 42h ; 'B'
0x140013f37  mov     edx, eax
0x140013f39  mov     r14d, eax
0x140013f3c  call    cs:__imp_ExAllocatePool2
0x140013f43  nop     dword ptr [rax+rax+00h]
0x140013f48  mov     rsi, rax
0x140013f4b  test    rax, rax
0x140013f4e  jnz     short loc_140013ED7
0x140013f50  mov     ebx, 0C000009Ah
0x140013f55  xor     ecx, ecx
0x140013f57  xor     eax, eax
0x140013f59  lock cmpxchg [rdi+4], ecx
0x140013f5e  cmp     cs:NfsRefHistoryTracingpGlobal, rcx
0x140013f65  jz      short loc_140013F75
0x140013f67  lea     r8d, [rcx+1]
0x140013f6b  mov     edx, eax
0x140013f6d  mov     rcx, rdi
0x140013f70  call    NfsReferenceHistoryCaptureRecord
0x140013f75  lock dec dword ptr [rdi+4]
0x140013f79  mov     rcx, [rbp+KeyHandle]; Handle
0x140013f7d  test    rcx, rcx
0x140013f80  jz      short loc_140013F8E
0x140013f82  call    cs:__imp_ZwClose
0x140013f89  nop     dword ptr [rax+rax+00h]
0x140013f8e  test    rsi, rsi
0x140013f91  jz      short loc_140013FA7
0x140013f93  mov     edx, 51425243h; Tag
0x140013f98  mov     rcx, rsi; P
0x140013f9b  call    cs:__imp_ExFreePoolWithTag
0x140013fa2  nop     dword ptr [rax+rax+00h]
0x140013fa7  lea     r11, [rsp+50h+var_s0]
0x140013fac  mov     eax, ebx
0x140013fae  mov     rbx, [r11+28h]
0x140013fb2  mov     rsi, [r11+30h]
0x140013fb6  mov     rsp, r11
0x140013fb9  pop     r14
0x140013fbb  pop     rdi
0x140013fbc  pop     rbp
0x140013fbd  retn
0x140013fbf  cmp     eax, 0C000022Dh
0x140013fc4  jz      loc_140013ED7
0x140013fca  jmp     short loc_140013F55
```
