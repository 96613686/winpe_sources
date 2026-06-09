# TmpWaitForTransactionOutcome

- ea: `0x140011d48`
- end: `0x140011db3`
- name: `TmpWaitForTransactionOutcome`
- size: `107`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140010c70`
- `0x14001a2e0`

## callees

- `0x140011d48`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140011d6a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140011d6a`

## pseudocode

```c
NTSTATUS __fastcall TmpWaitForTransactionOutcome(_DWORD *a1, int a2)
{
  NTSTATUS result; // eax
  int v5; // ecx

  result = KeWaitForSingleObject(a1, UserRequest, 1, 0, 0);
  if ( !result )
  {
    v5 = a1[126];
    if ( v5 != a2 )
    {
      switch ( v5 )
      {
        case 3:
          return -1072103403;
        case 2:
          return -1072103402;
        case 4:
          return -1072103374;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140011d48  mov     [rsp+arg_0], rbx
0x140011d4d  push    rdi
0x140011d4e  sub     rsp, 30h
0x140011d52  xor     r9d, r9d; Alertable
0x140011d55  mov     [rsp+38h+Timeout], 0; Timeout
0x140011d5e  mov     edi, edx
0x140011d60  mov     r8b, 1; WaitMode
0x140011d63  mov     rbx, rcx
0x140011d66  lea     edx, [r9+6]; WaitReason
0x140011d6a  call    cs:__imp_KeWaitForSingleObject
0x140011d71  nop     dword ptr [rax+rax+00h]
0x140011d76  test    eax, eax
0x140011d78  jnz     short loc_140011DA7
0x140011d7a  mov     ecx, [rbx+1F8h]
0x140011d80  cmp     ecx, edi
0x140011d82  jz      short loc_140011DA7
0x140011d84  cmp     ecx, 3
0x140011d87  jnz     short loc_140011D90
0x140011d89  mov     eax, 0C0190015h
0x140011d8e  jmp     short loc_140011DA7
0x140011d90  cmp     ecx, 2
0x140011d93  jnz     short loc_140011D9C
0x140011d95  mov     eax, 0C0190016h
0x140011d9a  jmp     short loc_140011DA7
0x140011d9c  cmp     ecx, 4
0x140011d9f  mov     edx, 0C0190032h
0x140011da4  cmovz   eax, edx
0x140011da7  mov     rbx, [rsp+38h+arg_0]
0x140011dac  add     rsp, 30h
0x140011db0  pop     rdi
0x140011db1  retn
```
