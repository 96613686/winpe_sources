# CmRegUtilUcValueSetUcString

- ea: `0x140019728`
- end: `0x14001985b`
- name: `CmRegUtilUcValueSetUcString`
- size: `307`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140019034`
- `0x14001990c`

## callees

- `0x1400051c0`
- `0x1400054c0`
- `0x140019728`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400197b4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400197b4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140019838`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140019838`
- `ntoskrnl!ZwSetValueKey` at `0x140019786`
- `ntoskrnl!ZwSetValueKey` at `0x140019825`
- `ntoskrnl!ZwSetValueKey` at `0x140019786`
- `ntoskrnl!ZwSetValueKey` at `0x140019825`

## pseudocode

```c
__int64 __fastcall CmRegUtilUcValueSetUcString(HANDLE KeyHandle, PUNICODE_STRING ValueName, unsigned __int16 *a3)
{
  unsigned __int64 v3; // r9
  unsigned __int64 v4; // rax
  unsigned int v8; // ebx
  size_t v9; // rsi
  wchar_t *PoolWithTag; // rax
  const void *v11; // rdx
  struct _UNICODE_STRING Data; // [rsp+30h] [rbp-48h] BYREF

  v3 = *a3;
  v4 = a3[1] - v3;
  Data = 0;
  if ( v4 < 2 )
  {
    v9 = v3 + 2;
    Data.MaximumLength = v3 + 2;
    PoolWithTag = (wchar_t *)ExAllocatePoolWithTag(PagedPool, v3 + 2, 0x63557050u);
    Data.Buffer = PoolWithTag;
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, v9);
      v11 = (const void *)*((_QWORD *)a3 + 1);
      Data.Length = *a3;
      memmove(Data.Buffer, v11, Data.Length);
      Data.Buffer[(unsigned __int64)Data.Length >> 1] = 0;
      v8 = ZwSetValueKey(KeyHandle, ValueName, 0, 1u, Data.Buffer, Data.Length + 2);
      RtlFreeUnicodeString(&Data);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * (v3 >> 1)) = 0;
    return (unsigned int)ZwSetValueKey(KeyHandle, ValueName, 0, 1u, *((PVOID *)a3 + 1), *a3 + 2);
  }
  return v8;
}

```

## disassembly

```asm
0x140019728  push    rbx
0x14001972a  push    rbp
0x14001972b  push    rsi
0x14001972c  push    rdi
0x14001972d  push    r14
0x14001972f  push    r15
0x140019731  sub     rsp, 48h
0x140019735  movzx   r9d, word ptr [r8]
0x140019739  mov     r15d, 2
0x14001973f  movzx   eax, word ptr [r8+2]
0x140019744  xorps   xmm0, xmm0
0x140019747  sub     rax, r9
0x14001974a  mov     rbx, r8
0x14001974d  mov     rbp, rdx
0x140019750  mov     r14, rcx
0x140019753  movups  xmmword ptr [rsp+78h+var_48.Length], xmm0
0x140019758  cmp     rax, r15
0x14001975b  jb      short loc_140019799
0x14001975d  mov     rax, [r8+8]
0x140019761  xor     edi, edi
0x140019763  shr     r9, 1
0x140019766  mov     [rax+r9*2], di
0x14001976b  lea     r9d, [r15-1]; Type
0x14001976f  movzx   eax, word ptr [r8]
0x140019773  add     eax, r15d
0x140019776  mov     [rsp+78h+DataSize], eax; DataSize
0x14001977a  mov     rax, [r8+8]
0x14001977e  xor     r8d, r8d; TitleIndex
0x140019781  mov     [rsp+78h+Data], rax; Data
0x140019786  call    cs:__imp_ZwSetValueKey
0x14001978d  nop     dword ptr [rax+rax+00h]
0x140019792  mov     ebx, eax
0x140019794  jmp     loc_14001984B
0x140019799  lea     rsi, [r9+2]
0x14001979d  mov     r8d, 63557050h; Tag
0x1400197a3  lea     eax, [r15+r9]
0x1400197a7  mov     rdx, rsi; NumberOfBytes
0x1400197aa  mov     ecx, 1; PoolType
0x1400197af  mov     [rsp+78h+var_48.MaximumLength], ax
0x1400197b4  call    cs:__imp_ExAllocatePoolWithTag
0x1400197bb  nop     dword ptr [rax+rax+00h]
0x1400197c0  xor     edi, edi
0x1400197c2  mov     [rsp+78h+var_48.Buffer], rax
0x1400197c7  test    rax, rax
0x1400197ca  jz      short loc_140019846
0x1400197cc  mov     r8, rsi; Size
0x1400197cf  xor     edx, edx; Val
0x1400197d1  mov     rcx, rax; void *
0x1400197d4  call    memset
0x1400197d9  movzx   r8d, word ptr [rbx]; Size
0x1400197dd  mov     rdx, [rbx+8]; Src
0x1400197e1  mov     rcx, [rsp+78h+var_48.Buffer]; void *
0x1400197e6  mov     [rsp+78h+var_48.Length], r8w
0x1400197ec  call    memmove
0x1400197f1  mov     rax, [rsp+78h+var_48.Buffer]
0x1400197f6  lea     r9d, [rdi+1]; Type
0x1400197fa  movzx   ecx, [rsp+78h+var_48.Length]
0x1400197ff  xor     r8d, r8d; TitleIndex
0x140019802  shr     rcx, 1
0x140019805  mov     rdx, rbp; ValueName
0x140019808  mov     [rax+rcx*2], di
0x14001980c  mov     rcx, r14; KeyHandle
0x14001980f  movzx   eax, [rsp+78h+var_48.Length]
0x140019814  add     eax, r15d
0x140019817  mov     [rsp+78h+DataSize], eax; DataSize
0x14001981b  mov     rax, [rsp+78h+var_48.Buffer]
0x140019820  mov     [rsp+78h+Data], rax; Data
0x140019825  call    cs:__imp_ZwSetValueKey
0x14001982c  nop     dword ptr [rax+rax+00h]
0x140019831  lea     rcx, [rsp+78h+var_48]; UnicodeString
0x140019836  mov     ebx, eax
0x140019838  call    cs:__imp_RtlFreeUnicodeString
0x14001983f  nop     dword ptr [rax+rax+00h]
0x140019844  jmp     short loc_14001984B
0x140019846  mov     ebx, 0C000009Ah
0x14001984b  mov     eax, ebx
0x14001984d  add     rsp, 48h
0x140019851  pop     r15
0x140019853  pop     r14
0x140019855  pop     rdi
0x140019856  pop     rsi
0x140019857  pop     rbp
0x140019858  pop     rbx
0x140019859  retn
```
