# WerUIUpdateStateProgress

- ea: `0x180003e30`
- end: `0x180003ebf`
- name: `WerUIUpdateStateProgress`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800035dc`
- `0x180003604`
- `0x180003e30`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall WerUIUpdateStateProgress(__int64 a1)
{
  int v2; // ebx

  if ( a1 )
  {
    v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
    if ( v2 >= 0 )
    {
      return 0;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        WPP_6033c33a43ed34eac75e2601d252ec66_Traceguids,
        (unsigned int)v2);
    }
    return (unsigned int)v2;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_6033c33a43ed34eac75e2601d252ec66_Traceguids);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180003e30  push    rbx
0x180003e32  sub     rsp, 30h
0x180003e36  test    rcx, rcx
0x180003e39  jnz     short loc_180003E70
0x180003e3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e42  lea     rax, WPP_GLOBAL_Control
0x180003e49  cmp     rcx, rax
0x180003e4c  jz      short loc_180003E69
0x180003e4e  test    byte ptr [rcx+1Ch], 1
0x180003e52  jz      short loc_180003E69
0x180003e54  mov     rcx, [rcx+10h]
0x180003e58  lea     r8, WPP_6033c33a43ed34eac75e2601d252ec66_Traceguids
0x180003e5f  mov     edx, 1Ah
0x180003e64  call    WPP_SF_
0x180003e69  mov     eax, 80070057h
0x180003e6e  jmp     short loc_180003EB9
0x180003e70  mov     rax, [rcx]
0x180003e73  mov     rax, [rax+18h]
0x180003e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e7c  mov     ebx, eax
0x180003e7e  test    eax, eax
0x180003e80  jns     short loc_180003EB5
0x180003e82  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e89  lea     rax, WPP_GLOBAL_Control
0x180003e90  cmp     rcx, rax
0x180003e93  jz      short loc_180003EB7
0x180003e95  test    byte ptr [rcx+1Ch], 1
0x180003e99  jz      short loc_180003EB7
0x180003e9b  mov     rcx, [rcx+10h]
0x180003e9f  lea     r8, WPP_6033c33a43ed34eac75e2601d252ec66_Traceguids
0x180003ea6  mov     edx, 1Ch
0x180003eab  mov     r9d, ebx
0x180003eae  call    WPP_SF_d
0x180003eb3  jmp     short loc_180003EB7
0x180003eb5  xor     ebx, ebx
0x180003eb7  mov     eax, ebx
0x180003eb9  add     rsp, 30h
0x180003ebd  pop     rbx
0x180003ebe  retn
```
