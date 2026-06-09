# VmpDeleteGptAttributesRevertRecord(uchar,uchar,_GUID *,_GUID *,ulong)

- ea: `0x140011bd8`
- end: `0x140011d8c`
- name: `?VmpDeleteGptAttributesRevertRecord@@YAXEEPEAU_GUID@@0K@Z`
- size: `436`
- prototype: `void __fastcall(unsigned __int8, unsigned __int8, struct _GUID *, struct _GUID *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140013ba0`
- `0x140013e00`

## callees

- `0x140005240`
- `0x140011bd8`
- `0x1400131f0`

## import_xrefs

- `ntoskrnl!RtlWriteRegistryValue` at `0x140011d2d`
- `ntoskrnl!RtlWriteRegistryValue` at `0x140011d2d`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x140011d3b`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x140011d3b`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140011cf4`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140011cf4`
- `ntoskrnl!ZwFlushKey` at `0x140011d4f`
- `ntoskrnl!ZwFlushKey` at `0x140011d4f`
- `ntoskrnl!ZwClose` at `0x140011d5f`
- `ntoskrnl!ZwClose` at `0x140011d5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011d70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011d70`

## pseudocode

```c
void __fastcall VmpDeleteGptAttributesRevertRecord(
        char a1,
        char a2,
        struct _GUID *a3,
        struct _GUID *a4,
        unsigned int a5)
{
  unsigned int v9; // edi
  unsigned int v10; // r9d
  PVOID ValueData; // rbx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rdx
  bool v15; // zf
  NTSTATUS v16; // eax
  unsigned int v17; // [rsp+30h] [rbp-20h] BYREF
  PCWSTR Path; // [rsp+38h] [rbp-18h]
  PVOID P; // [rsp+40h] [rbp-10h] BYREF

  Path = 0;
  P = 0;
  v17 = 0;
  if ( (int)VmpQueryRegistryRevertEntries((struct VM_GPT_ATTRIBUTES_REVERT_ENTRY **)&P, &v17) >= 0 )
  {
    v9 = v17;
    v10 = 0;
    ValueData = P;
    while ( v10 < v17 )
    {
      v12 = 32LL * v10;
      if ( a1 )
      {
        if ( *(_DWORD *)((char *)P + v12 + 24) )
        {
          v13 = *(_QWORD *)&a3->Data1 - *(_QWORD *)((char *)P + v12);
          if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)((char *)P + v12) )
          {
            v14 = *(_QWORD *)a3->Data4;
            goto LABEL_7;
          }
          goto LABEL_8;
        }
      }
      else if ( a2 )
      {
        if ( *(_DWORD *)((char *)P + v12 + 28) )
        {
          v13 = *(_QWORD *)&a4->Data1 - *(_QWORD *)((char *)P + v12);
          if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)((char *)P + v12) )
          {
            v14 = *(_QWORD *)a4->Data4;
LABEL_7:
            v13 = v14 - *(_QWORD *)((char *)P + v12 + 8);
          }
LABEL_8:
          v15 = v13 == 0;
          goto LABEL_16;
        }
      }
      else if ( !*(_DWORD *)((char *)P + v12 + 24) && !*(_DWORD *)((char *)P + v12 + 28) )
      {
        v15 = a5 == *(_DWORD *)((char *)P + v12);
LABEL_16:
        if ( v15 )
          break;
      }
      ++v10;
    }
    if ( v10 == v17 )
    {
      if ( !P )
        return;
      goto LABEL_30;
    }
    if ( v10 + 1 < v17 )
      memmove((char *)P + 32 * v10, (char *)P + 32 * v10 + 32, 32LL * (v17 - v10 - 1));
    if ( (int)IoOpenDriverRegistryKey(*((_QWORD *)VmRootExtension + 4), 1, 2) >= 0 )
    {
      if ( v9 == 1 )
        v16 = RtlDeleteRegistryValue(0x40000000u, Path, L"GptAttributeRevertEntries");
      else
        v16 = RtlWriteRegistryValue(0x40000000u, Path, L"GptAttributeRevertEntries", 3u, ValueData, 32 * (v9 - 1));
      if ( v16 >= 0 )
        ZwFlushKey((HANDLE)Path);
      ZwClose((HANDLE)Path);
LABEL_30:
      ExFreePoolWithTag(ValueData, 0);
    }
  }
}

```

## disassembly

```asm
0x140011bd8  push    rbp
0x140011bda  push    rbx
0x140011bdb  push    rsi
0x140011bdc  push    rdi
0x140011bdd  push    r12
0x140011bdf  push    r14
0x140011be1  push    r15
0x140011be3  mov     rbp, rsp
0x140011be6  sub     rsp, 50h
0x140011bea  mov     r15b, dl
0x140011bed  mov     [rbp+Path], 0
0x140011bf5  mov     r12b, cl
0x140011bf8  mov     [rbp+P], 0
0x140011c00  lea     rdx, [rbp+var_20]; unsigned int *
0x140011c04  mov     [rbp+var_20], 0
0x140011c0b  lea     rcx, [rbp+P]; struct VM_GPT_ATTRIBUTES_REVERT_ENTRY **
0x140011c0f  mov     rsi, r9
0x140011c12  mov     r14, r8
0x140011c15  call    ?VmpQueryRegistryRevertEntries@@YAJPEAPEAVVM_GPT_ATTRIBUTES_REVERT_ENTRY@@PEAK@Z; VmpQueryRegistryRevertEntries(VM_GPT_ATTRIBUTES_REVERT_ENTRY * *,ulong *)
0x140011c1a  test    eax, eax
0x140011c1c  js      loc_140011D7C
0x140011c22  mov     edi, [rbp+var_20]
0x140011c25  xor     r9d, r9d
0x140011c28  mov     rbx, [rbp+P]
0x140011c2c  test    edi, edi
0x140011c2e  jz      short loc_140011C95
0x140011c30  mov     r8d, [rbp+arg_20]
0x140011c34  mov     ecx, r9d
0x140011c37  shl     rcx, 5
0x140011c3b  test    r12b, r12b
0x140011c3e  jz      short loc_140011C5E
0x140011c40  cmp     dword ptr [rcx+rbx+18h], 0
0x140011c45  jz      short loc_140011C8D
0x140011c47  mov     rdx, [r14]
0x140011c4a  sub     rdx, [rcx+rbx]
0x140011c4e  jnz     short loc_140011C59
0x140011c50  mov     rdx, [r14+8]
0x140011c54  sub     rdx, [rcx+rbx+8]
0x140011c59  test    rdx, rdx
0x140011c5c  jmp     short loc_140011C8B
0x140011c5e  test    r15b, r15b
0x140011c61  jz      short loc_140011C79
0x140011c63  cmp     dword ptr [rcx+rbx+1Ch], 0
0x140011c68  jz      short loc_140011C8D
0x140011c6a  mov     rdx, [rsi]
0x140011c6d  sub     rdx, [rcx+rbx]
0x140011c71  jnz     short loc_140011C59
0x140011c73  mov     rdx, [rsi+8]
0x140011c77  jmp     short loc_140011C54
0x140011c79  cmp     dword ptr [rcx+rbx+18h], 0
0x140011c7e  jnz     short loc_140011C8D
0x140011c80  cmp     dword ptr [rcx+rbx+1Ch], 0
0x140011c85  jnz     short loc_140011C8D
0x140011c87  cmp     r8d, [rcx+rbx]
0x140011c8b  jz      short loc_140011C95
0x140011c8d  inc     r9d
0x140011c90  cmp     r9d, edi
0x140011c93  jb      short loc_140011C34
0x140011c95  cmp     r9d, edi
0x140011c98  jnz     short loc_140011CA8
0x140011c9a  test    rbx, rbx
0x140011c9d  jz      loc_140011D7C
0x140011ca3  jmp     loc_140011D6B
0x140011ca8  lea     ecx, [r9+1]
0x140011cac  cmp     ecx, edi
0x140011cae  jnb     short loc_140011CD5
0x140011cb0  mov     edx, ecx
0x140011cb2  mov     r8d, edi
0x140011cb5  sub     r8d, r9d
0x140011cb8  mov     ecx, r9d
0x140011cbb  dec     r8d
0x140011cbe  shl     rdx, 5
0x140011cc2  shl     rcx, 5
0x140011cc6  add     rdx, rbx; Src
0x140011cc9  shl     r8, 5; Size
0x140011ccd  add     rcx, rbx; void *
0x140011cd0  call    memmove
0x140011cd5  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x140011cdc  lea     rax, [rbp+Path]
0x140011ce0  xor     r9d, r9d
0x140011ce3  mov     [rsp+50h+ValueData], rax
0x140011ce8  mov     rcx, [rcx+20h]
0x140011cec  lea     edx, [r9+1]
0x140011cf0  lea     r8d, [r9+2]
0x140011cf4  call    cs:__imp_IoOpenDriverRegistryKey
0x140011cfb  nop     dword ptr [rax+rax+00h]
0x140011d00  test    eax, eax
0x140011d02  js      short loc_140011D7C
0x140011d04  mov     rdx, [rbp+Path]; Path
0x140011d08  lea     eax, [rdi-1]
0x140011d0b  lea     r8, ValueName; "GptAttributeRevertEntries"
0x140011d12  mov     ecx, 40000000h; RelativeTo
0x140011d17  test    eax, eax
0x140011d19  jz      short loc_140011D3B
0x140011d1b  shl     eax, 5
0x140011d1e  mov     r9d, 3; ValueType
0x140011d24  mov     [rsp+50h+ValueLength], eax; ValueLength
0x140011d28  mov     [rsp+50h+ValueData], rbx; ValueData
0x140011d2d  call    cs:__imp_RtlWriteRegistryValue
0x140011d34  nop     dword ptr [rax+rax+00h]
0x140011d39  jmp     short loc_140011D47
0x140011d3b  call    cs:__imp_RtlDeleteRegistryValue
0x140011d42  nop     dword ptr [rax+rax+00h]
0x140011d47  test    eax, eax
0x140011d49  js      short loc_140011D5B
0x140011d4b  mov     rcx, [rbp+Path]; KeyHandle
0x140011d4f  call    cs:__imp_ZwFlushKey
0x140011d56  nop     dword ptr [rax+rax+00h]
0x140011d5b  mov     rcx, [rbp+Path]; Handle
0x140011d5f  call    cs:__imp_ZwClose
0x140011d66  nop     dword ptr [rax+rax+00h]
0x140011d6b  xor     edx, edx; Tag
0x140011d6d  mov     rcx, rbx; P
0x140011d70  call    cs:__imp_ExFreePoolWithTag
0x140011d77  nop     dword ptr [rax+rax+00h]
0x140011d7c  add     rsp, 50h
0x140011d80  pop     r15
0x140011d82  pop     r14
0x140011d84  pop     r12
0x140011d86  pop     rdi
0x140011d87  pop     rsi
0x140011d88  pop     rbx
0x140011d89  pop     rbp
0x140011d8a  retn
```
