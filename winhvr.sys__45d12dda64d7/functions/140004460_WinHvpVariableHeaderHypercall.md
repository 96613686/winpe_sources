# WinHvpVariableHeaderHypercall

- ea: `0x140004460`
- end: `0x1400044c6`
- name: `WinHvpVariableHeaderHypercall`
- size: `102`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x140008310`
- `0x1400088c0`
- `0x14001b700`
- `0x14001b890`
- `0x14001c470`
- `0x14001c5a0`
- `0x14001c670`
- `0x14001c8e0`
- `0x14001db10`
- `0x14001dd90`
- `0x14001fd40`
- `0x140020e60`
- `0x1400262f0`

## callees

- `0x140004460`

## import_xrefs

- `ntoskrnl!HvlInvokeHypercall` at `0x14000449b`
- `ntoskrnl!HvlInvokeHypercall` at `0x14000449b`

## pseudocode

```c
__int64 __fastcall WinHvpVariableHeaderHypercall(__int16 a1, int a2, __int64 a3, __int64 a4)
{
  unsigned __int16 v4; // ax

  if ( !WinHvpConnected )
    return 3224702976LL;
  v4 = HvlInvokeHypercall(a1 & 0x3FFF | ((a2 + 7) << 14) & 0x3FE0000u, a3, a4);
  if ( v4 )
    return v4 | 0xC0350000;
  else
    return 0;
}

```

## disassembly

```asm
0x140004460  push    rbx
0x140004462  sub     rsp, 30h
0x140004466  add     edx, 7
0x140004469  and     ecx, 3FFFh
0x14000446f  shl     edx, 0Eh
0x140004472  xor     ebx, ebx
0x140004474  and     edx, 3FE0000h
0x14000447a  mov     [rsp+38h+var_18], rbx
0x14000447f  or      edx, ecx
0x140004481  mov     rax, r8
0x140004484  cmp     cs:WinHvpConnected, bl
0x14000448a  mov     dword ptr [rsp+38h+var_18], edx
0x14000448e  jz      short loc_1400044BF
0x140004490  mov     rcx, [rsp+38h+var_18]
0x140004495  mov     r8, r9
0x140004498  mov     rdx, rax
0x14000449b  call    cs:__imp_HvlInvokeHypercall
0x1400044a2  nop     dword ptr [rax+rax+00h]
0x1400044a7  test    ax, ax
0x1400044aa  jnz     short loc_1400044B5
0x1400044ac  mov     eax, ebx
0x1400044ae  add     rsp, 30h
0x1400044b2  pop     rbx
0x1400044b3  retn
0x1400044b5  movzx   eax, ax
0x1400044b8  or      eax, 0C0350000h
0x1400044bd  jmp     short loc_1400044AE
0x1400044bf  mov     eax, 0C0351000h
0x1400044c4  jmp     short loc_1400044AE
```
