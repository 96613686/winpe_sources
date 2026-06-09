# Srv2InitializeCryptoSupport

- ea: `0x14005f178`
- end: `0x14005f20d`
- name: `Srv2InitializeCryptoSupport`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14005f214`

## callees

- `0x14005efec`
- `0x14005f178`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14005f1a8`
- `ntoskrnl!ExAllocatePool2` at `0x14005f1a8`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x14005f187`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x14005f187`
- `srvnet!SmbCryptoKeyTableCreate` at `0x14005f1e3`
- `srvnet!SmbCryptoKeyTableCreate` at `0x14005f1e3`

## pseudocode

```c
__int64 Srv2InitializeCryptoSupport()
{
  unsigned __int16 v0; // si
  int v1; // edi
  unsigned __int16 i; // bx

  v0 = KeQueryHighestNodeNumber() + 1;
  Srv2DecryptionKeyTable = (PVOID)ExAllocatePool2(64, 8LL * v0, 607277900);
  if ( Srv2DecryptionKeyTable )
  {
    for ( i = 0; i < v0; ++i )
    {
      v1 = SmbCryptoKeyTableCreate((char *)Srv2DecryptionKeyTable + 8 * i);
      if ( v1 < 0 )
        goto LABEL_3;
    }
    return 0;
  }
  else
  {
    v1 = -1073741670;
LABEL_3:
    Srv2DeinitializeCryptoSupport();
    return (unsigned int)v1;
  }
}

```

## disassembly

```asm
0x14005f178  mov     [rsp+arg_0], rbx
0x14005f17d  mov     [rsp+arg_8], rsi
0x14005f182  push    rdi
0x14005f183  sub     rsp, 20h
0x14005f187  call    cs:__imp_KeQueryHighestNodeNumber
0x14005f18e  nop     dword ptr [rax+rax+00h]
0x14005f193  mov     ecx, 40h ; '@'
0x14005f198  mov     r8d, 2432534Ch
0x14005f19e  lea     esi, [rax+1]
0x14005f1a1  movzx   edx, si
0x14005f1a4  shl     rdx, 3
0x14005f1a8  call    cs:__imp_ExAllocatePool2
0x14005f1af  nop     dword ptr [rax+rax+00h]
0x14005f1b4  mov     cs:Srv2DecryptionKeyTable, rax
0x14005f1bb  test    rax, rax
0x14005f1be  jnz     short loc_14005F1CE
0x14005f1c0  mov     edi, 0C000009Ah
0x14005f1c5  call    Srv2DeinitializeCryptoSupport
0x14005f1ca  mov     eax, edi
0x14005f1cc  jmp     short loc_14005F1FC
0x14005f1ce  xor     ebx, ebx
0x14005f1d0  cmp     bx, si
0x14005f1d3  jnb     short loc_14005F1FA
0x14005f1d5  mov     rax, cs:Srv2DecryptionKeyTable
0x14005f1dc  movzx   ecx, bx
0x14005f1df  lea     rcx, [rax+rcx*8]
0x14005f1e3  call    cs:__imp_SmbCryptoKeyTableCreate
0x14005f1ea  nop     dword ptr [rax+rax+00h]
0x14005f1ef  mov     edi, eax
0x14005f1f1  test    eax, eax
0x14005f1f3  js      short loc_14005F1C5
0x14005f1f5  inc     bx
0x14005f1f8  jmp     short loc_14005F1D0
0x14005f1fa  xor     eax, eax
0x14005f1fc  mov     rbx, [rsp+28h+arg_0]
0x14005f201  mov     rsi, [rsp+28h+arg_8]
0x14005f206  add     rsp, 20h
0x14005f20a  pop     rdi
0x14005f20b  retn
```
