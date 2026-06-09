# PnpOobeCompleteStateChangeCallback

- ea: `0x180011890`
- end: `0x180011914`
- name: `PnpOobeCompleteStateChangeCallback`
- size: `132`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned int *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180011890`
- `0x18001191c`
- `0x1800133a0`

## pseudocode

```c
__int64 __fastcall PnpOobeCompleteStateChangeCallback(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int *a5,
        int a6)
{
  unsigned int v6; // edi
  unsigned int v7; // ebx
  unsigned int v8; // eax

  if ( a5 && a6 == 4 )
  {
    v6 = *a5;
    v7 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, v6);
    if ( v6 )
    {
      v8 = PnpGlobalFlags;
      if ( (PnpGlobalFlags & 4) != 0 )
      {
        v8 = PnpGlobalFlags & 0xFFFFFFFB;
        PnpGlobalFlags &= ~4u;
      }
      if ( (v8 & 8) != 0 )
      {
        PnpGlobalFlags = v8 & 0xFFFFFFF7;
        SignalSetupEvent();
      }
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v7;
}

```

## disassembly

```asm
0x180011890  mov     [rsp+arg_0], rbx
0x180011895  push    rdi
0x180011896  sub     rsp, 20h
0x18001189a  mov     rdi, [rsp+28h+arg_20]
0x18001189f  test    rdi, rdi
0x1800118a2  jz      short loc_180011902
0x1800118a4  cmp     [rsp+28h+arg_28], 4
0x1800118a9  jnz     short loc_180011902
0x1800118ab  mov     edi, [rdi]
0x1800118ad  xor     ebx, ebx
0x1800118af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118b6  lea     rax, WPP_GLOBAL_Control
0x1800118bd  cmp     rcx, rax
0x1800118c0  jz      short loc_1800118D7
0x1800118c2  test    dword ptr [rcx+1Ch], 40000h
0x1800118c9  jz      short loc_1800118D7
0x1800118cb  mov     rcx, [rcx+10h]
0x1800118cf  mov     r9d, edi
0x1800118d2  call    WPP_SF_D
0x1800118d7  test    edi, edi
0x1800118d9  jz      short loc_180011907
0x1800118db  mov     eax, cs:PnpGlobalFlags
0x1800118e1  test    al, 4
0x1800118e3  jz      short loc_1800118EE
0x1800118e5  and     eax, 0FFFFFFFBh
0x1800118e8  mov     cs:PnpGlobalFlags, eax
0x1800118ee  test    al, 8
0x1800118f0  jz      short loc_180011907
0x1800118f2  and     eax, 0FFFFFFF7h
0x1800118f5  mov     cs:PnpGlobalFlags, eax
0x1800118fb  call    SignalSetupEvent
0x180011900  jmp     short loc_180011907
0x180011902  mov     ebx, 0C000000Dh
0x180011907  mov     eax, ebx
0x180011909  mov     rbx, [rsp+28h+arg_0]
0x18001190e  add     rsp, 20h
0x180011912  pop     rdi
0x180011913  retn
```
