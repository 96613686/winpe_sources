# SqospAllocateUnicodeString

- ea: `0x140003a80`
- end: `0x140003b61`
- name: `SqospAllocateUnicodeString`
- size: `225`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140003a10`
- `0x1400046d0`
- `0x140011b00`

## callees

- `0x140003a80`
- `0x14000666c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140003aaa`
- `ntoskrnl!ExAllocatePool2` at `0x140003aaa`

## pseudocode

```c
__int64 __fastcall SqospAllocateUnicodeString(__int64 a1, unsigned __int16 a2)
{
  _WORD *Pool2; // rcx
  __int64 result; // rax

  if ( (unsigned __int16)(a2 - 1) > 0xFFFDu )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0xEu,
        (__int64)WPP_b8a405419f5733ac566e8c3690148060_Traceguids,
        -1073741811);
    }
    return 3221225485LL;
  }
  else
  {
    Pool2 = (_WORD *)ExAllocatePool2(64, a2, 1179865427);
    if ( Pool2 )
    {
      result = 0;
      *Pool2 = 0;
      *(_QWORD *)(a1 + 8) = Pool2;
      *(_WORD *)(a1 + 2) = a2;
      *(_WORD *)a1 = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0xFu,
          (__int64)WPP_b8a405419f5733ac566e8c3690148060_Traceguids,
          -1073741670);
      }
      return 3221225626LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140003a80  mov     [rsp+arg_0], rbx
0x140003a85  push    rdi
0x140003a86  sub     rsp, 20h
0x140003a8a  movzx   edi, dx
0x140003a8d  mov     rbx, rcx
0x140003a90  mov     ecx, 0FFFDh
0x140003a95  lea     eax, [rdi-1]
0x140003a98  cmp     ax, cx
0x140003a9b  ja      short loc_140003B1C
0x140003a9d  mov     edx, edi
0x140003a9f  mov     ecx, 40h ; '@'
0x140003aa4  mov     r8d, 46535153h
0x140003aaa  call    cs:__imp_ExAllocatePool2
0x140003ab1  nop     dword ptr [rax+rax+00h]
0x140003ab6  mov     rcx, rax
0x140003ab9  test    rax, rax
0x140003abc  jz      short loc_140003ADA
0x140003abe  xor     eax, eax
0x140003ac0  mov     [rcx], ax
0x140003ac3  mov     [rbx+8], rcx
0x140003ac7  mov     [rbx+2], di
0x140003acb  mov     [rbx], ax
0x140003ace  mov     rbx, [rsp+28h+arg_0]
0x140003ad3  add     rsp, 20h
0x140003ad7  pop     rdi
0x140003ad8  retn
0x140003ada  mov     rcx, cs:WPP_GLOBAL_Control
0x140003ae1  lea     rax, WPP_GLOBAL_Control
0x140003ae8  cmp     rcx, rax
0x140003aeb  jz      short loc_140003B15
0x140003aed  mov     edx, [rcx+2Ch]
0x140003af0  test    dl, dl
0x140003af2  jns     short loc_140003B15
0x140003af4  cmp     byte ptr [rcx+29h], 2
0x140003af8  jb      short loc_140003B15
0x140003afa  mov     rcx, [rcx+18h]
0x140003afe  lea     r8, WPP_b8a405419f5733ac566e8c3690148060_Traceguids
0x140003b05  mov     edx, 0Fh
0x140003b0a  mov     r9d, 0C000009Ah
0x140003b10  call    WPP_SF_d
0x140003b15  mov     eax, 0C000009Ah
0x140003b1a  jmp     short loc_140003ACE
0x140003b1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140003b23  lea     rax, WPP_GLOBAL_Control
0x140003b2a  cmp     rcx, rax
0x140003b2d  jz      short loc_140003B57
0x140003b2f  mov     edx, [rcx+2Ch]
0x140003b32  test    dl, dl
0x140003b34  jns     short loc_140003B57
0x140003b36  cmp     byte ptr [rcx+29h], 2
0x140003b3a  jb      short loc_140003B57
0x140003b3c  mov     rcx, [rcx+18h]
0x140003b40  lea     r8, WPP_b8a405419f5733ac566e8c3690148060_Traceguids
0x140003b47  mov     edx, 0Eh
0x140003b4c  mov     r9d, 0C000000Dh
0x140003b52  call    WPP_SF_d
0x140003b57  mov     eax, 0C000000Dh
0x140003b5c  jmp     loc_140003ACE
```
