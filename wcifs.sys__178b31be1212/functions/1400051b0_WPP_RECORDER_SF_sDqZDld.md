# WPP_RECORDER_SF_sDqZDld

- ea: `0x1400051b0`
- end: `0x1400053ef`
- name: `WPP_RECORDER_SF_sDqZDld`
- size: `575`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int, int, int, char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140025270`

## callees

- `0x1400051b0`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400053d2`
- `WppRecorder!WppAutoLogTrace` at `0x1400053d2`

## string_xrefs

- `0x1400051eb`: `onecore\base\fs\wci\wcifs\create.c`
- `0x1400052d3`: `onecore\base\fs\wci\wcifs\create.c`
- `0x1400052fe`: `onecore\base\fs\wci\wcifs\create.c`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_sDqZDld(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        char a8)
{
  int v10; // [rsp+20h] [rbp-D8h]
  _DWORD v11[18]; // [rsp+B0h] [rbp-48h] BYREF

  v11[0] = 2711;
  if ( (HIDWORD(wil_details_featureDescriptors_a->Timer) & 0x10) != 0
    && BYTE1(wil_details_featureDescriptors_a->Timer) >= 4u )
  {
    pfnWppTraceMessage(
      wil_details_featureDescriptors_a->AttachedDevice,
      43,
      WPP_852a4bc871f63f63d337338550f67970_Traceguids,
      59,
      "onecore\\base\\fs\\wci\\wcifs\\create.c",
      35,
      v11,
      4,
      &a8);
  }
  LOWORD(v10) = 59;
  return WppAutoLogTrace(
           a1,
           4,
           5,
           WPP_852a4bc871f63f63d337338550f67970_Traceguids,
           v10,
           "onecore\\base\\fs\\wci\\wcifs\\create.c",
           35,
           v11,
           4,
           &a8);
}

```

## disassembly

```asm
0x1400051b0  mov     rax, rsp
0x1400051b3  push    rbx
0x1400051b4  push    rbp
0x1400051b5  push    rsi
0x1400051b6  push    rdi
0x1400051b7  push    r14
0x1400051b9  push    r15
0x1400051bb  sub     rsp, 0C8h
0x1400051c2  mov     r10, cs:wil_details_featureDescriptors_a
0x1400051c9  lea     rdi, aNull_0; "NULL"
0x1400051d0  mov     rbx, [rsp+0F8h+arg_40]
0x1400051d8  lea     r9, asc_14000A7D0; "\b"
0x1400051df  xor     ebp, ebp
0x1400051e1  mov     dword ptr [rax-48h], 0A97h
0x1400051e8  mov     rsi, rcx
0x1400051eb  lea     rdx, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x1400051f2  mov     eax, [r10+2Ch]
0x1400051f6  lea     r14d, [rbp+4]
0x1400051fa  lea     r15d, [rbp+8]
0x1400051fe  lea     r11d, [rbp+3Bh]
0x140005202  test    al, 10h
0x140005204  jz      loc_140005305
0x14000520a  cmp     [r10+29h], r14b
0x14000520e  jb      loc_140005305
0x140005214  test    rbx, rbx
0x140005217  jz      short loc_140005227
0x140005219  movzx   ecx, word ptr [rbx]
0x14000521c  cmp     [rbx], bp
0x14000521f  jz      short loc_14000522A
0x140005221  mov     r8, [rbx+8]
0x140005225  jmp     short loc_14000522D
0x140005227  mov     rcx, r15
0x14000522a  mov     r8, rdi
0x14000522d  mov     rax, cs:pfnWppTraceMessage
0x140005234  test    rbx, rbx
0x140005237  mov     [rsp+0F8h+var_58], rbp
0x14000523f  mov     rdx, rbx
0x140005242  mov     [rsp+0F8h+var_60], r14
0x14000524a  cmovz   rdx, r9
0x14000524e  lea     r9, [rsp+0F8h+arg_58]
0x140005256  mov     [rsp+0F8h+var_68], r9
0x14000525e  lea     r9, [rsp+0F8h+arg_50]
0x140005266  mov     [rsp+0F8h+var_70], r14
0x14000526e  mov     [rsp+0F8h+var_78], r9
0x140005276  lea     r9, [rsp+0F8h+arg_48]
0x14000527e  mov     [rsp+0F8h+var_80], r14
0x140005283  mov     [rsp+0F8h+var_88], r9
0x140005288  mov     r9d, r11d
0x14000528b  mov     [rsp+0F8h+var_90], rcx
0x140005290  lea     rcx, [rsp+0F8h+arg_38]
0x140005298  mov     [rsp+0F8h+var_98], r8
0x14000529d  lea     r8, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x1400052a4  mov     [rsp+0F8h+var_A0], 2
0x1400052ad  mov     [rsp+0F8h+var_A8], rdx
0x1400052b2  mov     edx, 2Bh ; '+'
0x1400052b7  mov     [rsp+0F8h+var_B0], r15
0x1400052bc  mov     [rsp+0F8h+var_B8], rcx
0x1400052c1  lea     rcx, [rsp+0F8h+var_48]
0x1400052c9  mov     [rsp+0F8h+var_C0], r14
0x1400052ce  mov     [rsp+0F8h+var_C8], rcx
0x1400052d3  lea     rcx, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x1400052da  mov     [rsp+0F8h+var_D0], 23h ; '#'
0x1400052e3  mov     [rsp+0F8h+var_D8], rcx
0x1400052e8  mov     rcx, [r10+18h]
0x1400052ec  call    _guard_dispatch_icall
0x1400052f1  lea     r9, asc_14000A7D0; "\b"
0x1400052f8  mov     r11d, 3Bh ; ';'
0x1400052fe  lea     rdx, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140005305  test    rbx, rbx
0x140005308  jz      short loc_140005318
0x14000530a  movzx   eax, word ptr [rbx]
0x14000530d  cmp     [rbx], bp
0x140005310  jz      short loc_14000531B
0x140005312  mov     rdi, [rbx+8]
0x140005316  jmp     short loc_14000531B
0x140005318  mov     rax, r15
0x14000531b  mov     [rsp+0F8h+var_50], rbp
0x140005323  lea     rcx, [rsp+0F8h+arg_58]
0x14000532b  mov     [rsp+0F8h+var_58], r14
0x140005333  test    rbx, rbx
0x140005336  mov     [rsp+0F8h+var_60], rcx
0x14000533e  mov     r8d, 5
0x140005344  mov     [rsp+0F8h+var_68], r14
0x14000534c  lea     rcx, [rsp+0F8h+arg_50]
0x140005354  mov     [rsp+0F8h+var_70], rcx
0x14000535c  cmovz   rbx, r9
0x140005360  mov     [rsp+0F8h+var_78], r14
0x140005368  lea     rcx, [rsp+0F8h+arg_48]
0x140005370  mov     [rsp+0F8h+var_80], rcx
0x140005375  lea     r9, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x14000537c  mov     [rsp+0F8h+var_88], rax
0x140005381  mov     rcx, rsi
0x140005384  mov     [rsp+0F8h+var_90], rdi
0x140005389  lea     rax, [rsp+0F8h+arg_38]
0x140005391  mov     [rsp+0F8h+var_98], 2
0x14000539a  mov     [rsp+0F8h+var_A0], rbx
0x14000539f  mov     [rsp+0F8h+var_A8], r15
0x1400053a4  mov     [rsp+0F8h+var_B0], rax
0x1400053a9  lea     rax, [rsp+0F8h+var_48]
0x1400053b1  mov     [rsp+0F8h+var_B8], r14
0x1400053b6  mov     [rsp+0F8h+var_C0], rax
0x1400053bb  mov     [rsp+0F8h+var_C8], 23h ; '#'
0x1400053c4  mov     [rsp+0F8h+var_D0], rdx
0x1400053c9  mov     edx, r14d
0x1400053cc  mov     word ptr [rsp+0F8h+var_D8], r11w
0x1400053d2  call    cs:__imp_WppAutoLogTrace
0x1400053d9  nop     dword ptr [rax+rax+00h]
0x1400053de  add     rsp, 0C8h
0x1400053e5  pop     r15
0x1400053e7  pop     r14
0x1400053e9  pop     rdi
0x1400053ea  pop     rsi
0x1400053eb  pop     rbp
0x1400053ec  pop     rbx
0x1400053ed  retn
```
