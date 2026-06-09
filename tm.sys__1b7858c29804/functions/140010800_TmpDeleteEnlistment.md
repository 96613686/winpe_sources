# TmpDeleteEnlistment

- ea: `0x140010800`
- end: `0x1400108b7`
- name: `TmpDeleteEnlistment`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140010800`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001084c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010871`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001084c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010871`
- `ntoskrnl!ObfDereferenceObject` at `0x14001088b`
- `ntoskrnl!ObfDereferenceObject` at `0x14001089a`
- `ntoskrnl!ObfDereferenceObject` at `0x14001088b`
- `ntoskrnl!ObfDereferenceObject` at `0x14001089a`

## pseudocode

```c
LONG_PTR __fastcall TmpDeleteEnlistment(__int64 a1)
{
  void *v1; // rdi
  void *v3; // rsi
  void *v4; // rcx
  void *v5; // rcx
  LONG_PTR result; // rax

  v1 = *(void **)(a1 + 160);
  v3 = *(void **)(a1 + 152);
  _InterlockedOr((volatile signed __int32 *)(a1 + 172), 0x80000000);
  if ( *(_DWORD *)(a1 + 168) )
  {
    if ( (*(_DWORD *)(a1 + 172) & 8) == 0 )
    {
      v4 = *(void **)(a1 + 232);
      if ( v4 )
      {
        ExFreePoolWithTag(v4, 0);
        *(_QWORD *)(a1 + 232) = 0;
      }
    }
    v5 = *(void **)(a1 + 200);
    if ( v5 )
    {
      ExFreePoolWithTag(v5, 0);
      *(_QWORD *)(a1 + 200) = 0;
    }
    ObfDereferenceObject(v1);
    return ObfDereferenceObject(v3);
  }
  return result;
}

```

## disassembly

```asm
0x140010800  mov     [rsp+arg_0], rbx
0x140010805  mov     [rsp+arg_8], rsi
0x14001080a  push    rdi
0x14001080b  sub     rsp, 20h
0x14001080f  mov     rdi, [rcx+0A0h]
0x140010816  mov     rbx, rcx
0x140010819  mov     rsi, [rcx+98h]
0x140010820  lock or dword ptr [rcx+0ACh], 80000000h
0x14001082b  cmp     dword ptr [rcx+0A8h], 0
0x140010832  jz      short loc_1400108A6
0x140010834  mov     eax, [rcx+0ACh]
0x14001083a  test    al, 8
0x14001083c  jnz     short loc_140010863
0x14001083e  mov     rcx, [rcx+0E8h]; P
0x140010845  test    rcx, rcx
0x140010848  jz      short loc_140010863
0x14001084a  xor     edx, edx; Tag
0x14001084c  call    cs:__imp_ExFreePoolWithTag
0x140010853  nop     dword ptr [rax+rax+00h]
0x140010858  mov     qword ptr [rbx+0E8h], 0
0x140010863  mov     rcx, [rbx+0C8h]; P
0x14001086a  test    rcx, rcx
0x14001086d  jz      short loc_140010888
0x14001086f  xor     edx, edx; Tag
0x140010871  call    cs:__imp_ExFreePoolWithTag
0x140010878  nop     dword ptr [rax+rax+00h]
0x14001087d  mov     qword ptr [rbx+0C8h], 0
0x140010888  mov     rcx, rdi; Object
0x14001088b  call    cs:__imp_ObfDereferenceObject
0x140010892  nop     dword ptr [rax+rax+00h]
0x140010897  mov     rcx, rsi; Object
0x14001089a  call    cs:__imp_ObfDereferenceObject
0x1400108a1  nop     dword ptr [rax+rax+00h]
0x1400108a6  mov     rbx, [rsp+28h+arg_0]
0x1400108ab  mov     rsi, [rsp+28h+arg_8]
0x1400108b0  add     rsp, 20h
0x1400108b4  pop     rdi
0x1400108b5  retn
```
