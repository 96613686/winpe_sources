# SpDeleteContext(unsigned __int64)

- ea: `0x180003e30`
- end: `0x180003e91`
- name: `?SpDeleteContext@@YAJ_K@Z`
- size: `97`
- prototype: `__int64 __fastcall(struct _TS_CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003e30`
- `0x180004170`
- `0x180016650`

## pseudocode

```c
__int64 __fastcall SpDeleteContext(struct _TS_CONTEXT *a1)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_82746c11848034a638789f4e0723fe0c_Traceguids, a1);
  if ( a1 && _InterlockedExchangeAdd((volatile signed __int32 *)a1, 0xFFFFFFFF) <= 1 )
    TSFreeContext(a1);
  return 0;
}

```

## disassembly

```asm
0x180003e30  push    rbx
0x180003e32  sub     rsp, 20h
0x180003e36  mov     rbx, rcx
0x180003e39  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e40  lea     rax, WPP_GLOBAL_Control
0x180003e47  cmp     rcx, rax
0x180003e4a  jz      short loc_180003E52
0x180003e4c  test    byte ptr [rcx+1Ch], 20h
0x180003e50  jnz     short loc_180003E77
0x180003e52  test    rbx, rbx
0x180003e55  jz      short loc_180003E65
0x180003e57  mov     eax, 0FFFFFFFFh
0x180003e5c  lock xadd [rbx], eax
0x180003e60  sub     eax, 1
0x180003e63  jle     short loc_180003E6D
0x180003e65  xor     eax, eax
0x180003e67  add     rsp, 20h
0x180003e6b  pop     rbx
0x180003e6c  retn
0x180003e6d  mov     rcx, rbx; struct _TS_CONTEXT *
0x180003e70  call    ?TSFreeContext@@YAXPEAU_TS_CONTEXT@@@Z; TSFreeContext(_TS_CONTEXT *)
0x180003e75  jmp     short loc_180003E65
0x180003e77  mov     rcx, [rcx+10h]
0x180003e7b  lea     r8, WPP_82746c11848034a638789f4e0723fe0c_Traceguids
0x180003e82  mov     edx, 18h
0x180003e87  mov     r9, rbx
0x180003e8a  call    WPP_SF_q
0x180003e8f  jmp     short loc_180003E52
```
