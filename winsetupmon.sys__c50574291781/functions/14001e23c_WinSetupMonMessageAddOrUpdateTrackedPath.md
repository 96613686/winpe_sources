# WinSetupMonMessageAddOrUpdateTrackedPath

- ea: `0x14001e23c`
- end: `0x14001e2e6`
- name: `WinSetupMonMessageAddOrUpdateTrackedPath`
- size: `170`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140007668`

## callees

- `0x140001220`
- `0x140005910`
- `0x14000f930`
- `0x14001e044`
- `0x14001e10c`
- `0x14001e23c`

## pseudocode

```c
__int64 __fastcall WinSetupMonMessageAddOrUpdateTrackedPath(char a1, void *a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  int updated; // ebx
  UNICODE_STRING v7; // [rsp+28h] [rbp-40h] BYREF
  __int128 v8; // [rsp+38h] [rbp-30h] BYREF
  __int128 v9; // [rsp+48h] [rbp-20h]

  v8 = 0;
  v9 = 0;
  v7 = 0;
  if ( a1 )
    RtlCopyFromUser(&v8, a2, 0x20u);
  else
    RtlCopyVolatileMemory(&v8, a2, 0x20u);
  if ( WORD4(v8) )
  {
    LOBYTE(v4) = a1;
    updated = WinSetupMonDuplicateCapturedUnicodeStringFromMode(&v7, (char *)&v8 + 8, v4);
    if ( updated >= 0 )
      updated = AddOrUpdateTrackedPath(&v7, SDWORD2(v9), SBYTE12(v9), 1);
  }
  else
  {
    updated = -1073741811;
  }
  LOBYTE(v3) = a1;
  WinSetupMonFreeCapturedUnicodeStringFromMode(&v7, v3);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x14001e23c  mov     rax, rsp
0x14001e23f  mov     [rax+10h], rbx
0x14001e243  mov     [rax+18h], rsi
0x14001e247  mov     [rax+8], cl
0x14001e24a  push    rdi
0x14001e24b  sub     rsp, 60h
0x14001e24f  mov     dil, cl
0x14001e252  xorps   xmm0, xmm0
0x14001e255  movups  xmmword ptr [rax-30h], xmm0
0x14001e259  movups  xmmword ptr [rax-20h], xmm0
0x14001e25d  movups  xmmword ptr [rax-40h], xmm0
0x14001e261  xor     esi, esi
0x14001e263  lea     r8d, [rsi+20h]; Size
0x14001e267  lea     rcx, [rax-30h]; void *
0x14001e26b  test    dil, dil
0x14001e26e  jz      short loc_14001E277
0x14001e270  call    RtlCopyFromUser
0x14001e275  jmp     short loc_14001E27D
0x14001e277  call    RtlCopyVolatileMemory
0x14001e27c  nop
0x14001e27d  cmp     [rsp+68h+var_28], si
0x14001e282  jnz     short loc_14001E28B
0x14001e284  mov     ebx, 0C000000Dh
0x14001e289  jmp     short loc_14001E2C4
0x14001e28b  mov     r8b, dil
0x14001e28e  lea     rdx, [rsp+68h+var_28]
0x14001e293  lea     rcx, [rsp+68h+var_40]
0x14001e298  call    WinSetupMonDuplicateCapturedUnicodeStringFromMode
0x14001e29d  mov     ebx, eax
0x14001e29f  test    eax, eax
0x14001e2a1  js      short loc_14001E2C4
0x14001e2a3  mov     r9b, 1
0x14001e2a6  mov     r8b, [rsp+68h+var_14]
0x14001e2ab  mov     edx, [rsp+68h+var_18]
0x14001e2af  lea     rcx, [rsp+68h+var_40]
0x14001e2b4  call    ?AddOrUpdateTrackedPath@@YAJPEBU_UNICODE_STRING@@W4_TRACKING_MODE@@EE@Z; AddOrUpdateTrackedPath(_UNICODE_STRING const *,_TRACKING_MODE,uchar,uchar)
0x14001e2b9  mov     ebx, eax
0x14001e2bb  jmp     short loc_14001E2C4
0x14001e2bd  mov     ebx, eax
0x14001e2bf  mov     dil, [rsp+68h+arg_0]
0x14001e2c4  mov     dl, dil
0x14001e2c7  lea     rcx, [rsp+68h+var_40]
0x14001e2cc  call    WinSetupMonFreeCapturedUnicodeStringFromMode
0x14001e2d1  mov     eax, ebx
0x14001e2d3  lea     r11, [rsp+68h+var_8]
0x14001e2d8  mov     rbx, [r11+18h]
0x14001e2dc  mov     rsi, [r11+20h]
0x14001e2e0  mov     rsp, r11
0x14001e2e3  pop     rdi
0x14001e2e4  retn
0x140021c14  push    rbp
0x140021c16  sub     rsp, 20h
0x140021c1a  mov     rbp, rdx
0x140021c1d  xor     eax, eax
0x140021c1f  cmp     [rbp+70h], al
0x140021c22  setnz   al
0x140021c25  mov     [rbp+20h], eax
0x140021c28  mov     eax, [rbp+20h]
0x140021c2b  add     rsp, 20h
0x140021c2f  pop     rbp
0x140021c30  retn
```
