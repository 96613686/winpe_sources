# SlbNatFillChecksumAtOffset

- ea: `0x1400156e4`
- end: `0x1400157ab`
- name: `SlbNatFillChecksumAtOffset`
- size: `199`
- prototype: `char *__fastcall(__int64, unsigned __int16, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400157b4`

## callees

- `0x1400156e4`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001573b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001573b`
- `NETIO!RtlCopyBufferToMdl` at `0x14001578e`
- `NETIO!RtlCopyBufferToMdl` at `0x14001578e`

## pseudocode

```c
char *__fastcall SlbNatFillChecksumAtOffset(__int64 a1, unsigned __int16 a2, __int64 a3)
{
  __int64 v3; // r10
  __int16 v4; // r9
  int v5; // r11d
  __int64 v7; // rdi
  char *result; // rax
  __int64 v9; // rcx
  char *v10; // rdx
  __int64 v11; // rdx
  __int16 v12[12]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v13; // [rsp+60h] [rbp+18h] BYREF

  v3 = *(_QWORD *)(a3 + 8);
  v4 = 0;
  v5 = *(_DWORD *)(a3 + 16);
  v7 = a2;
  v12[0] = 0;
  if ( *(_DWORD *)(v3 + 40) - v5 < (unsigned int)a2 + 2 )
  {
    LODWORD(v9) = v5;
  }
  else
  {
    if ( (*(_BYTE *)(v3 + 10) & 5) != 0 )
    {
      result = *(char **)(v3 + 24);
    }
    else
    {
      result = (char *)MmMapLockedPagesSpecifyCache((PMDL)v3, 0, MmCached, 0, 0, 0x40000000u);
      v4 = v12[0];
    }
    v9 = *(unsigned int *)(a3 + 16);
    v10 = &result[v9];
    if ( (((_BYTE)v9 + (_BYTE)result) & 1) == 0 && v10 )
    {
      *(_WORD *)&v10[v7] = v4;
      return result;
    }
  }
  v11 = *(_QWORD *)(a3 + 8);
  v13 = 0;
  return (char *)RtlCopyBufferToMdl(v12, v11, (unsigned int)(v7 + v9), 2, &v13);
}

```

## disassembly

```asm
0x1400156e4  mov     [rsp+arg_0], rbx
0x1400156e9  mov     [rsp+arg_8], rsi
0x1400156ee  push    rdi
0x1400156ef  sub     rsp, 40h
0x1400156f3  mov     r10, [r8+8]
0x1400156f7  xor     r9d, r9d; RequestedAddress
0x1400156fa  mov     r11d, [r8+10h]
0x1400156fe  mov     rbx, r8
0x140015701  movzx   edi, dx
0x140015704  mov     [rsp+48h+var_18], r9w
0x14001570a  mov     ecx, [r10+28h]
0x14001570e  sub     ecx, r11d
0x140015711  lea     eax, [rdi+2]
0x140015714  cmp     ecx, eax
0x140015716  jb      short loc_140015765
0x140015718  test    byte ptr [r10+0Ah], 5
0x14001571d  jz      short loc_140015725
0x14001571f  mov     rax, [r10+18h]
0x140015723  jmp     short loc_14001574D
0x140015725  xor     edx, edx; AccessMode
0x140015727  mov     [rsp+48h+Priority], 40000000h; Priority
0x14001572f  mov     rcx, r10; MemoryDescriptorList
0x140015732  mov     [rsp+48h+BugCheckOnFailure], r9d; BugCheckOnFailure
0x140015737  lea     r8d, [rdx+1]; CacheType
0x14001573b  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140015742  nop     dword ptr [rax+rax+00h]
0x140015747  movzx   r9d, [rsp+48h+var_18]
0x14001574d  mov     ecx, [rbx+10h]
0x140015750  lea     rdx, [rcx+rax]
0x140015754  test    dl, 1
0x140015757  jnz     short loc_140015768
0x140015759  test    rdx, rdx
0x14001575c  jz      short loc_140015768
0x14001575e  mov     [rdi+rdx], r9w
0x140015763  jmp     short loc_14001579A
0x140015765  mov     ecx, r11d
0x140015768  mov     rdx, [rbx+8]
0x14001576c  lea     r8d, [rdi+rcx]
0x140015770  lea     rax, [rsp+48h+arg_10]
0x140015775  mov     [rsp+48h+arg_10], 0
0x14001577e  lea     rcx, [rsp+48h+var_18]
0x140015783  mov     qword ptr [rsp+48h+BugCheckOnFailure], rax
0x140015788  mov     r9d, 2
0x14001578e  call    cs:__imp_RtlCopyBufferToMdl
0x140015795  nop     dword ptr [rax+rax+00h]
0x14001579a  mov     rbx, [rsp+48h+arg_0]
0x14001579f  mov     rsi, [rsp+48h+arg_8]
0x1400157a4  add     rsp, 40h
0x1400157a8  pop     rdi
0x1400157a9  retn
```
