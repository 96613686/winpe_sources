# VidTriggerIoctlUpdateParameters

- ea: `0x140097a68`
- end: `0x140097bfa`
- name: `VidTriggerIoctlUpdateParameters`
- size: `402`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x140035698`

## callees

- `0x140015154`
- `0x140024754`
- `0x140030790`
- `0x1400307d0`
- `0x140038630`
- `0x140097a68`
- `0x140097f7c`
- `0x1400efa10`

## import_xrefs

- `winhvr!WinHvSetPortProperty` at `0x140097b5d`
- `winhvr!WinHvSetPortProperty` at `0x140097b5d`

## string_xrefs

- `0x140097a98`: `VidTriggerIoctlUpdateParameters`
- `0x140097adc`: `VidTriggerIoctlUpdateParameters`
- `0x140097b0b`: `VidTriggerIoctlUpdateParameters`
- `0x140097b7c`: `VidTriggerIoctlUpdateParameters`
- `0x140097b9c`: `VidTriggerIoctlUpdateParameters`
- `0x140097bdf`: `VidTriggerIoctlUpdateParameters`

## pseudocode

```c
__int64 __fastcall VidTriggerIoctlUpdateParameters(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // ebx
  __int64 v7; // rax
  __int64 v8; // rdi
  int v9; // eax

  v6 = VidTriggerpValidateParameters(a3);
  if ( v6 < 0 )
  {
    VidTraceErrorInternal0("VidTriggerIoctlUpdateParameters", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 355);
LABEL_17:
    VidTraceErrorStatusPartitionInternal0(
      (unsigned int)"VidTriggerIoctlUpdateParameters",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\vidtrigger.c",
      426,
      v6,
      a1 + 656);
    return (unsigned int)v6;
  }
  VidLockAcquireExclusive(a1 + 3368);
  v7 = VidHandleTableLookupEntry(a1 + 3336, a2);
  v8 = v7;
  if ( !v7 )
  {
    VidTraceErrorInternal0("VidTriggerIoctlUpdateParameters", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 364);
    v6 = -1073741275;
    goto LABEL_16;
  }
  v9 = *(_DWORD *)(v7 + 104);
  if ( v9 != *(_DWORD *)a3 )
  {
    v6 = -1073741811;
    VidTraceErrorInternal0("VidTriggerIoctlUpdateParameters", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 376);
    goto LABEL_16;
  }
  if ( v9 == 3 )
  {
    if ( *(_BYTE *)(v8 + 116) != *(_BYTE *)(a3 + 12)
      || *(_BYTE *)(v8 + 117) != *(_BYTE *)(a3 + 13)
      || ((*(_DWORD *)(v8 + 124) ^ *(_DWORD *)(a3 + 20)) & 0xFFFFFF) != 0
      || *(_WORD *)(v8 + 118) != *(_WORD *)(a3 + 14) )
    {
      v6 = -1073741637;
      VidTraceErrorInternal0("VidTriggerIoctlUpdateParameters", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 399);
      goto LABEL_16;
    }
    v6 = WinHvSetPortProperty(*(_QWORD *)v8, *(unsigned int *)(v8 + 124), 4, *(unsigned int *)(v8 + 112));
    if ( v6 < 0 )
    {
      VidTraceErrorInternal0("VidTriggerIoctlUpdateParameters", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 411);
      goto LABEL_16;
    }
  }
  VidTriggerpUpdateParameters(v8, a3);
  v6 = 0;
LABEL_16:
  VidLockRelease(a1 + 3368);
  if ( v6 < 0 )
    goto LABEL_17;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140097a68  push    rbx
0x140097a6a  push    rsi
0x140097a6b  push    rdi
0x140097a6c  push    r12
0x140097a6e  push    r15
0x140097a70  sub     rsp, 30h
0x140097a74  mov     r15, rcx
0x140097a77  mov     rsi, r8
0x140097a7a  mov     rcx, r8
0x140097a7d  mov     rdi, rdx
0x140097a80  call    VidTriggerpValidateParameters
0x140097a85  mov     ebx, eax
0x140097a87  test    eax, eax
0x140097a89  jns     short loc_140097AA9
0x140097a8b  mov     r8d, 163h
0x140097a91  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140097a98  lea     rcx, aVidtriggerioct; "VidTriggerIoctlUpdateParameters"
0x140097a9f  call    VidTraceErrorInternal0
0x140097aa4  jmp     loc_140097BC3
0x140097aa9  lea     r12, [r15+0D28h]
0x140097ab0  mov     rcx, r12
0x140097ab3  call    VidLockAcquireExclusive
0x140097ab8  lea     rcx, [r15+0D08h]
0x140097abf  mov     rdx, rdi
0x140097ac2  call    VidHandleTableLookupEntry
0x140097ac7  mov     rdi, rax
0x140097aca  test    rax, rax
0x140097acd  jnz     short loc_140097AF2
0x140097acf  mov     r8d, 16Ch
0x140097ad5  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140097adc  lea     rcx, aVidtriggerioct; "VidTriggerIoctlUpdateParameters"
0x140097ae3  call    VidTraceErrorInternal0
0x140097ae8  mov     ebx, 0C0000225h
0x140097aed  jmp     loc_140097BB7
0x140097af2  mov     eax, [rax+68h]
0x140097af5  cmp     eax, [rsi]
0x140097af7  jz      short loc_140097B1C
0x140097af9  mov     ebx, 0C000000Dh
0x140097afe  mov     r8d, 178h
0x140097b04  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140097b0b  lea     rcx, aVidtriggerioct; "VidTriggerIoctlUpdateParameters"
0x140097b12  call    VidTraceErrorInternal0
0x140097b17  jmp     loc_140097BB7
0x140097b1c  cmp     eax, 3
0x140097b1f  jnz     loc_140097BAA
0x140097b25  mov     al, [rsi+0Ch]
0x140097b28  cmp     [rdi+74h], al
0x140097b2b  jnz     short loc_140097B8A
0x140097b2d  mov     al, [rsi+0Dh]
0x140097b30  cmp     [rdi+75h], al
0x140097b33  jnz     short loc_140097B8A
0x140097b35  mov     ecx, [rsi+14h]
0x140097b38  xor     ecx, [rdi+7Ch]
0x140097b3b  test    ecx, 0FFFFFFh
0x140097b41  jnz     short loc_140097B8A
0x140097b43  movzx   eax, word ptr [rsi+0Eh]
0x140097b47  cmp     [rdi+76h], ax
0x140097b4b  jnz     short loc_140097B8A
0x140097b4d  mov     r9d, [rdi+70h]
0x140097b51  mov     r8d, 4
0x140097b57  mov     edx, [rdi+7Ch]
0x140097b5a  mov     rcx, [rdi]
0x140097b5d  call    cs:__imp_WinHvSetPortProperty
0x140097b64  nop     dword ptr [rax+rax+00h]
0x140097b69  mov     ebx, eax
0x140097b6b  test    eax, eax
0x140097b6d  jns     short loc_140097BAA
0x140097b6f  mov     r8d, 19Bh
0x140097b75  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140097b7c  lea     rcx, aVidtriggerioct; "VidTriggerIoctlUpdateParameters"
0x140097b83  call    VidTraceErrorInternal0
0x140097b88  jmp     short loc_140097BB7
0x140097b8a  mov     ebx, 0C00000BBh
0x140097b8f  mov     r8d, 18Fh
0x140097b95  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140097b9c  lea     rcx, aVidtriggerioct; "VidTriggerIoctlUpdateParameters"
0x140097ba3  call    VidTraceErrorInternal0
0x140097ba8  jmp     short loc_140097BB7
0x140097baa  mov     rdx, rsi
0x140097bad  mov     rcx, rdi
0x140097bb0  call    VidTriggerpUpdateParameters
0x140097bb5  xor     ebx, ebx
0x140097bb7  mov     rcx, r12
0x140097bba  call    VidLockRelease
0x140097bbf  test    ebx, ebx
0x140097bc1  jns     short loc_140097BEB
0x140097bc3  lea     rax, [r15+290h]
0x140097bca  mov     r9d, ebx
0x140097bcd  mov     r8d, 1AAh
0x140097bd3  mov     [rsp+58h+var_38], rax
0x140097bd8  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140097bdf  lea     rcx, aVidtriggerioct; "VidTriggerIoctlUpdateParameters"
0x140097be6  call    VidTraceErrorStatusPartitionInternal0
0x140097beb  mov     eax, ebx
0x140097bed  add     rsp, 30h
0x140097bf1  pop     r15
0x140097bf3  pop     r12
0x140097bf5  pop     rdi
0x140097bf6  pop     rsi
0x140097bf7  pop     rbx
0x140097bf8  retn
```
