# HUBDTX_CacheBillboardInfo

- ea: `0x140029990`
- end: `0x140029aa1`
- name: `HUBDTX_CacheBillboardInfo`
- size: `273`
- prototype: `void __fastcall(__int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14002bc18`

## callees

- `0x1400067ac`
- `0x140029990`
- `0x140045640`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140029a6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029a6a`
- `ntoskrnl!ExAllocatePool2` at `0x1400299b3`
- `ntoskrnl!ExAllocatePool2` at `0x140029a18`
- `ntoskrnl!ExAllocatePool2` at `0x1400299b3`
- `ntoskrnl!ExAllocatePool2` at `0x140029a18`

## pseudocode

```c
void __fastcall HUBDTX_CacheBillboardInfo(__int64 a1, unsigned __int8 *a2)
{
  __int64 Pool2; // rax
  int v5; // edx
  _QWORD *v6; // rbx
  void *v7; // rax
  int v8; // edx

  Pool2 = ExAllocatePool2(64, 16, 1748191317);
  v6 = (_QWORD *)Pool2;
  if ( Pool2 )
  {
    *(_BYTE *)(Pool2 + 8) = -1;
    v7 = (void *)ExAllocatePool2(64, *a2, 1748191317);
    *v6 = v7;
    if ( v7 )
    {
      memmove(v7, a2, *a2);
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v8) = 2;
        WPP_RECORDER_SF_(
          *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
          v8,
          5,
          98,
          (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids);
      }
      ExFreePoolWithTag(v6, 0x68334855u);
      v6 = 0;
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_(
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
      v5,
      5,
      97,
      (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids);
  }
  *(_QWORD *)(a1 + 2656) = v6;
}

```

## disassembly

```asm
0x140029990  mov     [rsp+arg_0], rbx
0x140029995  mov     [rsp+arg_8], rsi
0x14002999a  push    rdi
0x14002999b  sub     rsp, 30h
0x14002999f  mov     rdi, rdx
0x1400299a2  mov     rsi, rcx
0x1400299a5  mov     edx, 10h
0x1400299aa  mov     r8d, 68334855h
0x1400299b0  lea     ecx, [rdx+30h]
0x1400299b3  call    cs:__imp_ExAllocatePool2
0x1400299ba  nop     dword ptr [rax+rax+00h]
0x1400299bf  mov     rbx, rax
0x1400299c2  test    rax, rax
0x1400299c5  jnz     short loc_140029A06
0x1400299c7  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400299ce  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400299d5  jz      loc_140029A89
0x1400299db  mov     rcx, [rsi+8]
0x1400299df  lea     r9d, [rax+61h]
0x1400299e3  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x1400299ea  mov     dl, 2
0x1400299ec  lea     r8d, [rbx+5]
0x1400299f0  mov     [rsp+38h+var_18], rax
0x1400299f5  mov     rcx, [rcx+598h]
0x1400299fc  call    WPP_RECORDER_SF_
0x140029a01  jmp     loc_140029A89
0x140029a06  mov     byte ptr [rax+8], 0FFh
0x140029a0a  mov     ecx, 40h ; '@'
0x140029a0f  movzx   edx, byte ptr [rdi]
0x140029a12  mov     r8d, 68334855h
0x140029a18  call    cs:__imp_ExAllocatePool2
0x140029a1f  nop     dword ptr [rax+rax+00h]
0x140029a24  mov     [rbx], rax
0x140029a27  test    rax, rax
0x140029a2a  jnz     short loc_140029A7A
0x140029a2c  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140029a33  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140029a3a  jz      short loc_140029A62
0x140029a3c  mov     rcx, [rsi+8]
0x140029a40  lea     r9d, [rax+62h]
0x140029a44  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x140029a4b  mov     dl, 2
0x140029a4d  lea     r8d, [r9-5Dh]
0x140029a51  mov     [rsp+38h+var_18], rax
0x140029a56  mov     rcx, [rcx+598h]
0x140029a5d  call    WPP_RECORDER_SF_
0x140029a62  mov     edx, 68334855h; Tag
0x140029a67  mov     rcx, rbx; P
0x140029a6a  call    cs:__imp_ExFreePoolWithTag
0x140029a71  nop     dword ptr [rax+rax+00h]
0x140029a76  xor     ebx, ebx
0x140029a78  jmp     short loc_140029A89
0x140029a7a  movzx   r8d, byte ptr [rdi]; Size
0x140029a7e  mov     rdx, rdi; Src
0x140029a81  mov     rcx, rax; void *
0x140029a84  call    memmove
0x140029a89  mov     [rsi+0A60h], rbx
0x140029a90  mov     rbx, [rsp+38h+arg_0]
0x140029a95  mov     rsi, [rsp+38h+arg_8]
0x140029a9a  add     rsp, 30h
0x140029a9e  pop     rdi
0x140029a9f  retn
```
