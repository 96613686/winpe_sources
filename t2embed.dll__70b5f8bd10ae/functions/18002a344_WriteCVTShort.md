# WriteCVTShort

- ea: `0x18002a344`
- end: `0x18002a430`
- name: `WriteCVTShort`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b540`

## callees

- `0x18001c9ec`
- `0x18002a344`

## pseudocode

```c
_BYTE *__fastcall WriteCVTShort(_BYTE **a1, __int16 a2)
{
  __int16 v2; // bx
  __int16 v4; // si
  _BYTE *v5; // rdi
  _BYTE *v6; // rcx
  _BYTE *result; // rax

  v2 = -a2;
  if ( a2 > 0 )
    v2 = a2;
  v4 = v2 / 238;
  if ( v2 / 238 > 8 || a2 == (__int16)0x8000 )
  {
    v6 = *a1;
    *v6 = -18;
    v5 = v6 + 2;
    v6[2] = a2;
    v6[1] = HIBYTE(a2);
    goto LABEL_18;
  }
  v5 = *a1;
  if ( a2 >= 0 )
  {
    if ( v4 > 0 )
    {
      if ( (unsigned __int8)(v4 - 9) < 0xF8u )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      *v5++ = v4 - 9;
      v2 %= 238;
    }
    if ( (unsigned __int16)v2 <= 0xEDu )
      goto LABEL_16;
  }
  else
  {
    if ( (unsigned __int8)v4 > 8u )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    *v5++ = v4 - 17;
    v2 %= 238;
    if ( (unsigned __int16)v2 <= 0xEDu )
      goto LABEL_16;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_16:
  *v5 = v2;
LABEL_18:
  result = v5 + 1;
  *a1 = v5 + 1;
  return result;
}

```

## disassembly

```asm
0x18002a344  push    rbx
0x18002a346  push    rbp
0x18002a347  push    rsi
0x18002a348  push    rdi
0x18002a349  push    r14
0x18002a34b  sub     rsp, 20h
0x18002a34f  movzx   ebx, dx
0x18002a352  mov     eax, 44D72045h
0x18002a357  neg     bx
0x18002a35a  movzx   r9d, dx
0x18002a35e  mov     r14, rcx
0x18002a361  cmovs   bx, dx
0x18002a365  movsx   r8d, bx
0x18002a369  imul    r8d
0x18002a36c  mov     esi, edx
0x18002a36e  sar     esi, 6
0x18002a371  mov     eax, esi
0x18002a373  shr     eax, 1Fh
0x18002a376  add     esi, eax
0x18002a378  cmp     si, 8
0x18002a37c  jg      loc_18002A406
0x18002a382  mov     eax, 0FFFF8000h
0x18002a387  cmp     r9w, ax
0x18002a38b  jz      short loc_18002A406
0x18002a38d  mov     rdi, [rcx]
0x18002a390  test    r9w, r9w
0x18002a394  jns     short loc_18002A3CB
0x18002a396  lea     ebp, [rsi-11h]
0x18002a399  lea     eax, [rbp+11h]
0x18002a39c  cmp     al, 8
0x18002a39e  jbe     short loc_18002A3A5
0x18002a3a0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002a3a5  mov     eax, 0EEh
0x18002a3aa  movsx   ecx, si
0x18002a3ad  cwde
0x18002a3ae  imul    ecx, eax
0x18002a3b1  mov     eax, 0EDh
0x18002a3b6  mov     [rdi], bpl
0x18002a3b9  inc     rdi
0x18002a3bc  sub     bx, cx
0x18002a3bf  cmp     bx, ax
0x18002a3c2  jbe     short loc_18002A402
0x18002a3c4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002a3c9  jmp     short loc_18002A402
0x18002a3cb  test    si, si
0x18002a3ce  jle     short loc_18002A3F3
0x18002a3d0  lea     ebp, [rsi-9]
0x18002a3d3  cmp     bpl, 0F8h
0x18002a3d7  jnb     short loc_18002A3DE
0x18002a3d9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002a3de  mov     eax, 0EEh
0x18002a3e3  movsx   ecx, si
0x18002a3e6  cwde
0x18002a3e7  imul    ecx, eax
0x18002a3ea  mov     [rdi], bpl
0x18002a3ed  inc     rdi
0x18002a3f0  sub     bx, cx
0x18002a3f3  mov     eax, 0EDh
0x18002a3f8  cmp     bx, ax
0x18002a3fb  jbe     short loc_18002A402
0x18002a3fd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002a402  mov     [rdi], bl
0x18002a404  jmp     short loc_18002A41E
0x18002a406  mov     rcx, [rcx]
0x18002a409  movzx   eax, r9w
0x18002a40d  shr     ax, 8
0x18002a411  mov     byte ptr [rcx], 0EEh
0x18002a414  lea     rdi, [rcx+2]
0x18002a418  mov     [rdi], r9b
0x18002a41b  mov     [rcx+1], al
0x18002a41e  lea     rax, [rdi+1]
0x18002a422  mov     [r14], rax
0x18002a425  add     rsp, 20h
0x18002a429  pop     r14
0x18002a42b  pop     rdi
0x18002a42c  pop     rsi
0x18002a42d  pop     rbp
0x18002a42e  pop     rbx
0x18002a42f  retn
```
