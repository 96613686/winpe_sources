# WerUIDelete

- ea: `0x1800039e0`
- end: `0x180003a35`
- name: `WerUIDelete`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800035dc`
- `0x1800039e0`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall WerUIDelete(void (__fastcall ***a1)(_QWORD, __int64))
{
  if ( a1 )
  {
    (**a1)(a1, 1);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_6033c33a43ed34eac75e2601d252ec66_Traceguids);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800039e0  sub     rsp, 28h
0x1800039e4  test    rcx, rcx
0x1800039e7  jnz     short loc_180003A1E
0x1800039e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039f0  lea     rax, WPP_GLOBAL_Control
0x1800039f7  cmp     rcx, rax
0x1800039fa  jz      short loc_180003A17
0x1800039fc  test    byte ptr [rcx+1Ch], 1
0x180003a00  jz      short loc_180003A17
0x180003a02  mov     rcx, [rcx+10h]
0x180003a06  lea     r8, WPP_6033c33a43ed34eac75e2601d252ec66_Traceguids
0x180003a0d  mov     edx, 0Bh
0x180003a12  call    WPP_SF_
0x180003a17  mov     eax, 80070057h
0x180003a1c  jmp     short loc_180003A30
0x180003a1e  mov     rax, [rcx]
0x180003a21  mov     edx, 1
0x180003a26  mov     rax, [rax]
0x180003a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a2e  xor     eax, eax
0x180003a30  add     rsp, 28h
0x180003a34  retn
```
