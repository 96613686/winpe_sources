# WerUIUpdateUIForState

- ea: `0x180003ed0`
- end: `0x180003f5f`
- name: `WerUIUpdateUIForState`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800035dc`
- `0x180003604`
- `0x180003ed0`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall WerUIUpdateUIForState(__int64 a1)
{
  int v2; // ebx

  if ( a1 )
  {
    v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
    if ( v2 >= 0 )
    {
      return 0;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        WPP_6033c33a43ed34eac75e2601d252ec66_Traceguids,
        (unsigned int)v2);
    }
    return (unsigned int)v2;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_6033c33a43ed34eac75e2601d252ec66_Traceguids);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180003ed0  push    rbx
0x180003ed2  sub     rsp, 20h
0x180003ed6  test    rcx, rcx
0x180003ed9  jnz     short loc_180003F10
0x180003edb  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ee2  lea     rax, WPP_GLOBAL_Control
0x180003ee9  cmp     rcx, rax
0x180003eec  jz      short loc_180003F09
0x180003eee  test    byte ptr [rcx+1Ch], 1
0x180003ef2  jz      short loc_180003F09
0x180003ef4  mov     rcx, [rcx+10h]
0x180003ef8  lea     r8, WPP_6033c33a43ed34eac75e2601d252ec66_Traceguids
0x180003eff  mov     edx, 17h
0x180003f04  call    WPP_SF_
0x180003f09  mov     eax, 80070057h
0x180003f0e  jmp     short loc_180003F59
0x180003f10  mov     rax, [rcx]
0x180003f13  mov     rax, [rax+10h]
0x180003f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f1c  mov     ebx, eax
0x180003f1e  test    eax, eax
0x180003f20  jns     short loc_180003F55
0x180003f22  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f29  lea     rax, WPP_GLOBAL_Control
0x180003f30  cmp     rcx, rax
0x180003f33  jz      short loc_180003F57
0x180003f35  test    byte ptr [rcx+1Ch], 1
0x180003f39  jz      short loc_180003F57
0x180003f3b  mov     rcx, [rcx+10h]
0x180003f3f  lea     r8, WPP_6033c33a43ed34eac75e2601d252ec66_Traceguids
0x180003f46  mov     edx, 19h
0x180003f4b  mov     r9d, ebx
0x180003f4e  call    WPP_SF_d
0x180003f53  jmp     short loc_180003F57
0x180003f55  xor     ebx, ebx
0x180003f57  mov     eax, ebx
0x180003f59  add     rsp, 20h
0x180003f5d  pop     rbx
0x180003f5e  retn
```
