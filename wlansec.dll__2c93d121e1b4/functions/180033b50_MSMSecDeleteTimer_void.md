# MSMSecDeleteTimer(void *)

- ea: `0x180033b50`
- end: `0x180033bda`
- name: `?MSMSecDeleteTimer@@YAXPEAX@Z`
- size: `138`
- prototype: `void __fastcall(void *)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x18000367c`
- `0x18000485c`
- `0x1800055d0`
- `0x1800063f4`
- `0x1800065a4`
- `0x18001c8a8`
- `0x180033a54`
- `0x180035ae0`

## callees

- `0x18000892c`
- `0x180008998`
- `0x180033b50`

## import_xrefs

- `MobileNetworking!DeleteTimer` at `0x180033b73`
- `MobileNetworking!DeleteTimer` at `0x180033b73`

## pseudocode

```c
void __fastcall MSMSecDeleteTimer(void *a1)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, WPP_af9f9ec4a94e340b956c894f3cebdf2e_Traceguids);
  DeleteTimer(a1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, WPP_af9f9ec4a94e340b956c894f3cebdf2e_Traceguids, 0);
}

```

## disassembly

```asm
0x180033b50  mov     [rsp+arg_0], rbx
0x180033b55  push    rsi
0x180033b56  sub     rsp, 20h
0x180033b5a  mov     rbx, rcx
0x180033b5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180033b64  lea     rsi, WPP_GLOBAL_Control
0x180033b6b  cmp     rcx, rsi
0x180033b6e  jnz     short loc_180033BA0
0x180033b70  mov     rcx, rbx
0x180033b73  call    cs:__imp_DeleteTimer
0x180033b7a  nop     dword ptr [rax+rax+00h]
0x180033b7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180033b86  cmp     rcx, rsi
0x180033b89  jz      short loc_180033B94
0x180033b8b  test    dword ptr [rcx+44h], 100h
0x180033b92  jnz     short loc_180033BC0
0x180033b94  mov     rbx, [rsp+28h+arg_0]
0x180033b99  add     rsp, 20h
0x180033b9d  pop     rsi
0x180033b9e  retn
0x180033ba0  test    dword ptr [rcx+44h], 100h
0x180033ba7  jz      short loc_180033B70
0x180033ba9  mov     rcx, [rcx+38h]
0x180033bad  lea     r8, WPP_af9f9ec4a94e340b956c894f3cebdf2e_Traceguids
0x180033bb4  mov     edx, 15h
0x180033bb9  call    WPP_SF_
0x180033bbe  jmp     short loc_180033B70
0x180033bc0  mov     rcx, [rcx+38h]
0x180033bc4  lea     r8, WPP_af9f9ec4a94e340b956c894f3cebdf2e_Traceguids
0x180033bcb  mov     edx, 16h
0x180033bd0  xor     r9d, r9d
0x180033bd3  call    WPP_SF_d
0x180033bd8  jmp     short loc_180033B94
```
