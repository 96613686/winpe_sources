# WcnOneXDeInitializeGlobals

- ea: `0x18007b260`
- end: `0x18007b2f8`
- name: `WcnOneXDeInitializeGlobals`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18007a0d4`
- `0x18007a2e4`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18007b260`

## import_xrefs

- `MobileNetworking!DeleteReadWriteLock` at `0x18007b2b9`
- `MobileNetworking!DeleteReadWriteLock` at `0x18007b2b9`

## pseudocode

```c
__int64 WcnOneXDeInitializeGlobals()
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_bcd439bcbb1139129627a8519bf42888_Traceguids);
  qword_1800BB504 = 0;
  qword_1800BB588 = 0;
  qword_1800BB5A8 = 0;
  hLibModule = 0;
  DeleteReadWriteLock(qword_1800BB520);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_bcd439bcbb1139129627a8519bf42888_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x18007b260  push    rbx
0x18007b262  sub     rsp, 20h
0x18007b266  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b26d  lea     rbx, WPP_GLOBAL_Control
0x18007b274  cmp     rcx, rbx
0x18007b277  jz      short loc_18007B294
0x18007b279  test    byte ptr [rcx+1Ch], 1
0x18007b27d  jz      short loc_18007B294
0x18007b27f  mov     rcx, [rcx+10h]
0x18007b283  lea     r8, WPP_bcd439bcbb1139129627a8519bf42888_Traceguids
0x18007b28a  mov     edx, 0Eh
0x18007b28f  call    WPP_SF_
0x18007b294  xor     eax, eax
0x18007b296  lea     rcx, qword_1800BB520
0x18007b29d  mov     cs:qword_1800BB504, rax
0x18007b2a4  mov     cs:qword_1800BB588, rax
0x18007b2ab  mov     cs:qword_1800BB5A8, rax
0x18007b2b2  mov     cs:hLibModule, rax
0x18007b2b9  call    cs:__imp_DeleteReadWriteLock
0x18007b2c0  nop     dword ptr [rax+rax+00h]
0x18007b2c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b2cc  cmp     rcx, rbx
0x18007b2cf  jz      short loc_18007B2EF
0x18007b2d1  test    byte ptr [rcx+1Ch], 1
0x18007b2d5  jz      short loc_18007B2EF
0x18007b2d7  mov     rcx, [rcx+10h]
0x18007b2db  lea     r8, WPP_bcd439bcbb1139129627a8519bf42888_Traceguids
0x18007b2e2  mov     edx, 0Fh
0x18007b2e7  xor     r9d, r9d
0x18007b2ea  call    WPP_SF_d
0x18007b2ef  xor     eax, eax
0x18007b2f1  add     rsp, 20h
0x18007b2f5  pop     rbx
0x18007b2f6  retn
```
