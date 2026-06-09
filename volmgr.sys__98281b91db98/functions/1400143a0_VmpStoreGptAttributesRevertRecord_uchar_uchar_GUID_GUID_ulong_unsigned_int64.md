# VmpStoreGptAttributesRevertRecord(uchar,uchar,_GUID *,_GUID *,ulong,unsigned __int64)

- ea: `0x1400143a0`
- end: `0x140014624`
- name: `?VmpStoreGptAttributesRevertRecord@@YAJEEPEAU_GUID@@0K_K@Z`
- size: `644`
- prototype: `__int64 __fastcall(unsigned __int8, unsigned __int8, struct _GUID *, struct _GUID *, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140013e00`

## callees

- `0x140005240`
- `0x1400131f0`
- `0x1400143a0`

## import_xrefs

- `ntoskrnl!RtlWriteRegistryValue` at `0x1400145ba`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1400145ba`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140014585`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140014585`
- `ntoskrnl!ZwFlushKey` at `0x1400145d1`
- `ntoskrnl!ZwFlushKey` at `0x1400145d1`
- `ntoskrnl!ZwClose` at `0x1400145e7`
- `ntoskrnl!ZwClose` at `0x1400145e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400144aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400144e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400145fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400144aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400144e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400145fd`
- `ntoskrnl!ExAllocatePool2` at `0x14001448c`
- `ntoskrnl!ExAllocatePool2` at `0x14001448c`

## pseudocode

```c
__int64 __fastcall VmpStoreGptAttributesRevertRecord(
        char a1,
        char a2,
        struct _GUID *a3,
        struct _GUID *a4,
        unsigned int a5,
        unsigned __int64 a6)
{
  char v6; // bp
  char v7; // r14
  struct VM_GPT_ATTRIBUTES_REVERT_ENTRY *ValueData; // rbx
  unsigned int v11; // edi
  unsigned int i; // esi
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  bool v16; // zf
  struct VM_GPT_ATTRIBUTES_REVERT_ENTRY *Pool2; // rax
  struct VM_GPT_ATTRIBUTES_REVERT_ENTRY *v18; // rbp
  NTSTATUS v19; // esi
  __int64 v20; // rcx
  __int128 v21; // xmm0
  unsigned int v23; // [rsp+30h] [rbp-58h] BYREF
  PCWSTR Path; // [rsp+38h] [rbp-50h]
  struct VM_GPT_ATTRIBUTES_REVERT_ENTRY *v25; // [rsp+40h] [rbp-48h] BYREF

  v6 = a2;
  v25 = 0;
  v7 = a1;
  v23 = 0;
  Path = 0;
  if ( (int)VmpQueryRegistryRevertEntries(&v25, &v23) >= 0 )
  {
    ValueData = v25;
    v11 = v23;
  }
  else
  {
    ValueData = 0;
    v11 = 0;
  }
  for ( i = 0; i < v11; ++i )
  {
    v13 = 32LL * i;
    if ( v7 )
    {
      if ( *(_DWORD *)((char *)ValueData + v13 + 24) )
      {
        v14 = *(_QWORD *)&a3->Data1 - *(_QWORD *)((char *)ValueData + v13);
        if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)((char *)ValueData + v13) )
        {
          v15 = *(_QWORD *)a3->Data4;
          goto LABEL_9;
        }
        goto LABEL_10;
      }
    }
    else if ( v6 )
    {
      if ( *(_DWORD *)((char *)ValueData + v13 + 28) )
      {
        v14 = *(_QWORD *)&a4->Data1 - *(_QWORD *)((char *)ValueData + v13);
        if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)((char *)ValueData + v13) )
        {
          v15 = *(_QWORD *)a4->Data4;
LABEL_9:
          v14 = v15 - *(_QWORD *)((char *)ValueData + v13 + 8);
        }
LABEL_10:
        v16 = v14 == 0;
        goto LABEL_18;
      }
    }
    else if ( !*(_DWORD *)((char *)ValueData + v13 + 24) && !*(_DWORD *)((char *)ValueData + v13 + 28) )
    {
      v16 = a5 == *(_DWORD *)((char *)ValueData + v13);
LABEL_18:
      if ( v16 )
        break;
    }
  }
  if ( i == v11 )
  {
    Pool2 = (struct VM_GPT_ATTRIBUTES_REVERT_ENTRY *)ExAllocatePool2(258, 32LL * (v11 + 1), 538987862);
    v18 = Pool2;
    if ( !Pool2 )
    {
      if ( ValueData )
        ExFreePoolWithTag(ValueData, 0);
      v19 = -1073741670;
      goto LABEL_40;
    }
    if ( v11 )
    {
      if ( !ValueData )
      {
LABEL_30:
        ValueData = v18;
        ++v11;
        v6 = a2;
        v7 = a1;
        goto LABEL_31;
      }
      memmove(Pool2, ValueData, 32LL * v11);
    }
    if ( ValueData )
      ExFreePoolWithTag(ValueData, 0);
    goto LABEL_30;
  }
LABEL_31:
  v20 = 32LL * i;
  *(_QWORD *)((char *)ValueData + v20) = 0;
  *(_QWORD *)((char *)ValueData + v20 + 8) = 0;
  *(_QWORD *)((char *)ValueData + v20 + 24) = 0;
  *(_QWORD *)((char *)ValueData + v20 + 16) = a6;
  if ( v7 )
  {
    *(_DWORD *)((char *)ValueData + v20 + 24) = 1;
    v21 = (__int128)*a3;
  }
  else
  {
    if ( !v6 )
    {
      *(_DWORD *)((char *)ValueData + v20) = a5;
      goto LABEL_37;
    }
    *(_DWORD *)((char *)ValueData + v20 + 28) = 1;
    v21 = (__int128)*a4;
  }
  *(_OWORD *)((char *)ValueData + v20) = v21;
LABEL_37:
  v19 = IoOpenDriverRegistryKey(*((_QWORD *)VmRootExtension + 4), 1, 2);
  if ( v19 >= 0 )
  {
    v19 = RtlWriteRegistryValue(0x40000000u, Path, L"GptAttributeRevertEntries", 3u, ValueData, 32 * v11);
    if ( v19 >= 0 )
      ZwFlushKey((HANDLE)Path);
  }
LABEL_40:
  if ( Path )
    ZwClose((HANDLE)Path);
  if ( ValueData )
    ExFreePoolWithTag(ValueData, 0);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1400143a0  mov     rax, rsp
0x1400143a3  mov     [rax+18h], rbx
0x1400143a7  mov     [rax+10h], dl
0x1400143aa  mov     [rax+8], cl
0x1400143ad  push    rbp
0x1400143ae  push    rsi
0x1400143af  push    rdi
0x1400143b0  push    r12
0x1400143b2  push    r13
0x1400143b4  push    r14
0x1400143b6  push    r15
0x1400143b8  sub     rsp, 50h
0x1400143bc  mov     bpl, dl
0x1400143bf  mov     qword ptr [rax-48h], 0
0x1400143c7  mov     r14b, cl
0x1400143ca  mov     dword ptr [rax-58h], 0
0x1400143d1  lea     rdx, [rax-58h]; unsigned int *
0x1400143d5  mov     qword ptr [rax-50h], 0
0x1400143dd  lea     rcx, [rax-48h]; struct VM_GPT_ATTRIBUTES_REVERT_ENTRY **
0x1400143e1  mov     r13, r9
0x1400143e4  mov     r12, r8
0x1400143e7  call    ?VmpQueryRegistryRevertEntries@@YAJPEAPEAVVM_GPT_ATTRIBUTES_REVERT_ENTRY@@PEAK@Z; VmpQueryRegistryRevertEntries(VM_GPT_ATTRIBUTES_REVERT_ENTRY * *,ulong *)
0x1400143ec  test    eax, eax
0x1400143ee  jns     short loc_1400143F6
0x1400143f0  xor     ebx, ebx
0x1400143f2  xor     edi, edi
0x1400143f4  jmp     short loc_1400143FF
0x1400143f6  mov     rbx, [rsp+88h+var_48]
0x1400143fb  mov     edi, [rsp+88h+var_58]
0x1400143ff  mov     r15d, [rsp+88h+arg_20]
0x140014407  xor     esi, esi
0x140014409  test    edi, edi
0x14001440b  jz      short loc_14001446E
0x14001440d  mov     ecx, esi
0x14001440f  shl     rcx, 5
0x140014413  test    r14b, r14b
0x140014416  jz      short loc_140014438
0x140014418  cmp     dword ptr [rcx+rbx+18h], 0
0x14001441d  jz      short loc_140014468
0x14001441f  mov     rdx, [r12]
0x140014423  sub     rdx, [rcx+rbx]
0x140014427  jnz     short loc_140014433
0x140014429  mov     rdx, [r12+8]
0x14001442e  sub     rdx, [rcx+rbx+8]
0x140014433  test    rdx, rdx
0x140014436  jmp     short loc_140014466
0x140014438  test    bpl, bpl
0x14001443b  jz      short loc_140014454
0x14001443d  cmp     dword ptr [rcx+rbx+1Ch], 0
0x140014442  jz      short loc_140014468
0x140014444  mov     rdx, [r13+0]
0x140014448  sub     rdx, [rcx+rbx]
0x14001444c  jnz     short loc_140014433
0x14001444e  mov     rdx, [r13+8]
0x140014452  jmp     short loc_14001442E
0x140014454  cmp     dword ptr [rcx+rbx+18h], 0
0x140014459  jnz     short loc_140014468
0x14001445b  cmp     dword ptr [rcx+rbx+1Ch], 0
0x140014460  jnz     short loc_140014468
0x140014462  cmp     r15d, [rcx+rbx]
0x140014466  jz      short loc_14001446E
0x140014468  inc     esi
0x14001446a  cmp     esi, edi
0x14001446c  jb      short loc_14001440D
0x14001446e  cmp     esi, edi
0x140014470  jnz     loc_140014507
0x140014476  lea     r14d, [rdi+1]
0x14001447a  mov     ecx, 102h
0x14001447f  mov     edx, r14d
0x140014482  mov     r8d, 20204D56h
0x140014488  shl     rdx, 5
0x14001448c  call    cs:__imp_ExAllocatePool2
0x140014493  nop     dword ptr [rax+rax+00h]
0x140014498  mov     rbp, rax
0x14001449b  test    rax, rax
0x14001449e  jnz     short loc_1400144C0
0x1400144a0  test    rbx, rbx
0x1400144a3  jz      short loc_1400144B6
0x1400144a5  xor     edx, edx; Tag
0x1400144a7  mov     rcx, rbx; P
0x1400144aa  call    cs:__imp_ExFreePoolWithTag
0x1400144b1  nop     dword ptr [rax+rax+00h]
0x1400144b6  mov     esi, 0C000009Ah
0x1400144bb  jmp     loc_1400145DD
0x1400144c0  test    edi, edi
0x1400144c2  jz      short loc_1400144DB
0x1400144c4  test    rbx, rbx
0x1400144c7  jz      short loc_1400144F1
0x1400144c9  mov     r8d, edi
0x1400144cc  mov     rdx, rbx; Src
0x1400144cf  shl     r8, 5; Size
0x1400144d3  mov     rcx, rbp; void *
0x1400144d6  call    memmove
0x1400144db  test    rbx, rbx
0x1400144de  jz      short loc_1400144F1
0x1400144e0  xor     edx, edx; Tag
0x1400144e2  mov     rcx, rbx; P
0x1400144e5  call    cs:__imp_ExFreePoolWithTag
0x1400144ec  nop     dword ptr [rax+rax+00h]
0x1400144f1  mov     rbx, rbp
0x1400144f4  mov     edi, r14d
0x1400144f7  mov     bpl, [rsp+88h+arg_8]
0x1400144ff  mov     r14b, [rsp+88h+arg_0]
0x140014507  mov     rax, [rsp+88h+arg_28]
0x14001450f  mov     ecx, esi
0x140014511  shl     rcx, 5
0x140014515  mov     qword ptr [rcx+rbx], 0
0x14001451d  mov     qword ptr [rcx+rbx+8], 0
0x140014526  mov     qword ptr [rcx+rbx+18h], 0
0x14001452f  mov     [rcx+rbx+10h], rax
0x140014534  test    r14b, r14b
0x140014537  jz      short loc_140014548
0x140014539  mov     dword ptr [rcx+rbx+18h], 1
0x140014541  movups  xmm0, xmmword ptr [r12]
0x140014546  jmp     short loc_14001455A
0x140014548  test    bpl, bpl
0x14001454b  jz      short loc_140014561
0x14001454d  mov     dword ptr [rcx+rbx+1Ch], 1
0x140014555  movups  xmm0, xmmword ptr [r13+0]
0x14001455a  movdqu  xmmword ptr [rcx+rbx], xmm0
0x14001455f  jmp     short loc_140014565
0x140014561  mov     [rcx+rbx], r15d
0x140014565  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x14001456c  lea     rax, [rsp+88h+Path]
0x140014571  xor     r9d, r9d
0x140014574  mov     [rsp+88h+ValueData], rax
0x140014579  mov     rcx, [rcx+20h]
0x14001457d  lea     edx, [r9+1]
0x140014581  lea     r8d, [r9+2]
0x140014585  call    cs:__imp_IoOpenDriverRegistryKey
0x14001458c  nop     dword ptr [rax+rax+00h]
0x140014591  mov     esi, eax
0x140014593  test    eax, eax
0x140014595  js      short loc_1400145DD
0x140014597  mov     rdx, [rsp+88h+Path]; Path
0x14001459c  lea     r8, ValueName; "GptAttributeRevertEntries"
0x1400145a3  shl     edi, 5
0x1400145a6  mov     r9d, 3; ValueType
0x1400145ac  mov     [rsp+88h+ValueLength], edi; ValueLength
0x1400145b0  mov     ecx, 40000000h; RelativeTo
0x1400145b5  mov     [rsp+88h+ValueData], rbx; ValueData
0x1400145ba  call    cs:__imp_RtlWriteRegistryValue
0x1400145c1  nop     dword ptr [rax+rax+00h]
0x1400145c6  mov     esi, eax
0x1400145c8  test    eax, eax
0x1400145ca  js      short loc_1400145DD
0x1400145cc  mov     rcx, [rsp+88h+Path]; KeyHandle
0x1400145d1  call    cs:__imp_ZwFlushKey
0x1400145d8  nop     dword ptr [rax+rax+00h]
0x1400145dd  mov     rcx, [rsp+88h+Path]; Handle
0x1400145e2  test    rcx, rcx
0x1400145e5  jz      short loc_1400145F3
0x1400145e7  call    cs:__imp_ZwClose
0x1400145ee  nop     dword ptr [rax+rax+00h]
0x1400145f3  test    rbx, rbx
0x1400145f6  jz      short loc_140014609
0x1400145f8  xor     edx, edx; Tag
0x1400145fa  mov     rcx, rbx; P
0x1400145fd  call    cs:__imp_ExFreePoolWithTag
0x140014604  nop     dword ptr [rax+rax+00h]
0x140014609  mov     rbx, [rsp+88h+arg_10]
0x140014611  mov     eax, esi
0x140014613  add     rsp, 50h
0x140014617  pop     r15
0x140014619  pop     r14
0x14001461b  pop     r13
0x14001461d  pop     r12
0x14001461f  pop     rdi
0x140014620  pop     rsi
0x140014621  pop     rbp
0x140014622  retn
```
