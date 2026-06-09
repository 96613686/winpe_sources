# UdfSeqCacheTruncateDataForFile

- ea: `0x14003be8c`
- end: `0x14003bf86`
- name: `UdfSeqCacheTruncateDataForFile`
- size: `250`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400175d0`
- `0x140051d74`

## callees

- `0x14002c7d8`
- `0x14003be8c`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14003bf51`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003bf60`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003bf51`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003bf60`

## pseudocode

```c
void __fastcall UdfSeqCacheTruncateDataForFile(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // rbx
  __int64 v7; // rdi
  int v8; // r9d
  int v9; // [rsp+20h] [rbp-58h]
  int v10; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v11; // [rsp+98h] [rbp+20h] BYREF

  v3 = *(_QWORD *)(a1 + 16);
  v7 = *(_QWORD *)(v3 + 104);
  if ( (*(_DWORD *)(v3 + 48) & 0x20000000) != 0 )
  {
    if ( a2 == *(_QWORD *)(v3 + 320) || a2 == *(_QWORD *)(v3 + 272) )
    {
      v7 = *(_QWORD *)(v3 + 112);
    }
    else if ( a2 == *(_QWORD *)(v3 + 328) )
    {
      v7 = *(_QWORD *)(v3 + 120);
    }
  }
  UdfAcquireResource(a1, v7 + 344, 0, 0);
  UdfAcquireResource(a1, v7 + 448, 0, 0);
  if ( (*(_DWORD *)(*(_QWORD *)(v3 + 104) + 4LL) & 0x10) == 0 )
    UdfSeqCacheScanTags(v7, a2, a3, v8, v9, &v11, &v10);
  ExReleaseResourceLite((PERESOURCE)(v7 + 448));
  ExReleaseResourceLite((PERESOURCE)(v7 + 344));
}

```

## disassembly

```asm
0x14003be8c  mov     [rsp+arg_8], rbx
0x14003be91  mov     [rsp+arg_10], rbp
0x14003be96  push    rsi
0x14003be97  push    rdi
0x14003be98  push    r12
0x14003be9a  push    r14
0x14003be9c  push    r15
0x14003be9e  sub     rsp, 50h
0x14003bea2  mov     rbx, [rcx+10h]
0x14003bea6  mov     r12d, r8d
0x14003bea9  mov     rsi, rdx
0x14003beac  mov     rbp, rcx
0x14003beaf  test    dword ptr [rbx+30h], 20000000h
0x14003beb6  mov     rdi, [rbx+68h]
0x14003beba  jz      short loc_14003BEE1
0x14003bebc  cmp     rdx, [rbx+140h]
0x14003bec3  jz      short loc_14003BEDD
0x14003bec5  cmp     rdx, [rbx+110h]
0x14003becc  jz      short loc_14003BEDD
0x14003bece  cmp     rdx, [rbx+148h]
0x14003bed5  jnz     short loc_14003BEE1
0x14003bed7  mov     rdi, [rbx+78h]
0x14003bedb  jmp     short loc_14003BEE1
0x14003bedd  mov     rdi, [rbx+70h]
0x14003bee1  lea     r14, [rdi+158h]
0x14003bee8  xor     r9d, r9d
0x14003beeb  mov     rdx, r14
0x14003beee  xor     r8d, r8d
0x14003bef1  call    UdfAcquireResource
0x14003bef6  lea     r15, [rdi+1C0h]
0x14003befd  xor     r9d, r9d
0x14003bf00  mov     rdx, r15
0x14003bf03  xor     r8d, r8d
0x14003bf06  mov     rcx, rbp
0x14003bf09  call    UdfAcquireResource
0x14003bf0e  mov     rax, [rbx+68h]
0x14003bf12  mov     ecx, [rax+4]
0x14003bf15  and     ecx, 10h
0x14003bf18  test    ecx, ecx
0x14003bf1a  jnz     short loc_14003BF4E
0x14003bf1c  mov     eax, [rsi+178h]
0x14003bf22  mov     r8d, r12d
0x14003bf25  mov     [rsp+78h+var_40], eax
0x14003bf29  mov     rdx, rsi
0x14003bf2c  lea     rax, [rsp+78h+arg_0]
0x14003bf34  mov     rcx, rdi
0x14003bf37  mov     [rsp+78h+var_48], rax
0x14003bf3c  lea     rax, [rsp+78h+arg_18]
0x14003bf44  mov     [rsp+78h+var_50], rax
0x14003bf49  call    UdfSeqCacheScanTags
0x14003bf4e  mov     rcx, r15; Resource
0x14003bf51  call    cs:__imp_ExReleaseResourceLite
0x14003bf58  nop     dword ptr [rax+rax+00h]
0x14003bf5d  mov     rcx, r14; Resource
0x14003bf60  call    cs:__imp_ExReleaseResourceLite
0x14003bf67  nop     dword ptr [rax+rax+00h]
0x14003bf6c  lea     r11, [rsp+78h+var_28]
0x14003bf71  mov     rbx, [r11+38h]
0x14003bf75  mov     rbp, [r11+40h]
0x14003bf79  mov     rsp, r11
0x14003bf7c  pop     r15
0x14003bf7e  pop     r14
0x14003bf80  pop     r12
0x14003bf82  pop     rdi
0x14003bf83  pop     rsi
0x14003bf84  retn
```
