# UmpoInternalGetPowerModeSchema

- ea: `0x1800132cc`
- end: `0x180013373`
- name: `UmpoInternalGetPowerModeSchema`
- size: `167`
- prototype: `__int64 __fastcall(_BYTE *, __int64, __int64)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x1800012a0`
- `0x180001580`
- `0x1800027d4`
- `0x180002bc0`
- `0x18000e6e4`
- `0x18000f4f4`

## callees

- `0x180008044`
- `0x180010070`
- `0x1800132cc`
- `0x1800188bc`

## pseudocode

```c
__int64 __fastcall UmpoInternalGetPowerModeSchema(_BYTE *a1, __int64 a2, __int64 a3)
{
  unsigned int OverlaySchemes; // ebp
  unsigned int v5; // ebx
  _DWORD v7[4]; // [rsp+20h] [rbp-128h] BYREF
  _OWORD v8[16]; // [rsp+30h] [rbp-118h] BYREF

  v7[0] = 0;
  LOBYTE(a3) = 1;
  OverlaySchemes = UmpoInternalGetOverlaySchemes(v8, v7, a3);
  if ( !OverlaySchemes )
  {
    v5 = 0;
    for ( *a1 = 1; v5 < v7[0]; ++v5 )
    {
      if ( !memcmp_0(&GUID_POWER_MODE_PERFORMANCE, &v8[v5], 0x10u) )
        *a1 = 0;
    }
  }
  return OverlaySchemes;
}

```

## disassembly

```asm
0x1800132cc  mov     [rsp+arg_8], rbx
0x1800132d1  mov     [rsp+arg_10], rbp
0x1800132d6  push    rsi
0x1800132d7  sub     rsp, 140h
0x1800132de  mov     rax, cs:__security_cookie
0x1800132e5  xor     rax, rsp
0x1800132e8  mov     [rsp+148h+var_18], rax
0x1800132f0  mov     rsi, rcx
0x1800132f3  mov     [rsp+148h+var_128], 0
0x1800132fb  lea     rcx, [rsp+148h+var_118]
0x180013300  mov     r8b, 1
0x180013303  lea     rdx, [rsp+148h+var_128]
0x180013308  call    UmpoInternalGetOverlaySchemes
0x18001330d  mov     ebp, eax
0x18001330f  test    eax, eax
0x180013311  jnz     short loc_18001334C
0x180013313  xor     ebx, ebx
0x180013315  mov     byte ptr [rsi], 1
0x180013318  cmp     [rsp+148h+var_128], ebx
0x18001331c  jbe     short loc_18001334C
0x18001331e  mov     ecx, ebx
0x180013320  lea     rdx, [rsp+148h+var_118]
0x180013325  shl     rcx, 4
0x180013329  mov     r8d, 10h; Size
0x18001332f  add     rdx, rcx; Buf2
0x180013332  lea     rcx, GUID_POWER_MODE_PERFORMANCE; Buf1
0x180013339  call    memcmp_0
0x18001333e  test    eax, eax
0x180013340  jnz     short loc_180013344
0x180013342  mov     [rsi], al
0x180013344  inc     ebx
0x180013346  cmp     ebx, [rsp+148h+var_128]
0x18001334a  jb      short loc_18001331E
0x18001334c  mov     eax, ebp
0x18001334e  mov     rcx, [rsp+148h+var_18]
0x180013356  xor     rcx, rsp; StackCookie
0x180013359  call    __security_check_cookie
0x18001335e  lea     r11, [rsp+148h+var_8]
0x180013366  mov     rbx, [r11+18h]
0x18001336a  mov     rbp, [r11+20h]
0x18001336e  mov     rsp, r11
0x180013371  pop     rsi
0x180013372  retn
```
