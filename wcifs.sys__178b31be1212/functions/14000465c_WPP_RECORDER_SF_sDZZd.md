# WPP_RECORDER_SF_sDZZd

- ea: `0x14000465c`
- end: `0x14000489c`
- name: `WPP_RECORDER_SF_sDZZd`
- size: `576`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned __int16, __int64, __int64, char, const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140026260`

## callees

- `0x14000465c`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000487b`
- `WppRecorder!WppAutoLogTrace` at `0x14000487b`

## string_xrefs

- `0x140004695`: `onecore\base\fs\wci\wcifs\create.c`
- `0x14000478a`: `onecore\base\fs\wci\wcifs\create.c`
- `0x1400047a8`: `onecore\base\fs\wci\wcifs\create.c`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_sDZZd(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        __int64 a5,
        __int64 a6,
        char a7,
        const wchar_t *a8)
{
  const wchar_t *v8; // rdi
  const wchar_t *v10; // rdx
  bool v11; // zf
  int v13; // [rsp+20h] [rbp-C8h]

  v8 = a8;
  if ( (HIDWORD(wil_details_featureDescriptors_a->Timer) & 0x200) != 0
    && BYTE1(wil_details_featureDescriptors_a->Timer) >= 5u )
  {
    v10 = a8;
    if ( !a8 )
      v10 = L"\b";
    pfnWppTraceMessage(
      wil_details_featureDescriptors_a->AttachedDevice,
      43,
      WPP_852a4bc871f63f63d337338550f67970_Traceguids,
      a4,
      "onecore\\base\\fs\\wci\\wcifs\\create.c",
      35,
      &a7,
      4,
      v10);
  }
  v11 = v8 == 0;
  if ( v8 )
    v11 = 0;
  if ( v11 )
    v8 = L"\b";
  LOWORD(v13) = a4;
  return WppAutoLogTrace(
           0,
           5,
           10,
           WPP_852a4bc871f63f63d337338550f67970_Traceguids,
           v13,
           "onecore\\base\\fs\\wci\\wcifs\\create.c",
           35,
           &a7,
           4,
           v8);
}

```

## disassembly

```asm
0x14000465c  push    rbx
0x14000465e  push    rbp
0x14000465f  push    rsi
0x140004660  push    rdi
0x140004661  push    r12
0x140004663  push    r13
0x140004665  push    r14
0x140004667  push    r15
0x140004669  sub     rsp, 0A8h
0x140004670  mov     r11, cs:wil_details_featureDescriptors_a
0x140004677  lea     rbp, aNull_0; "NULL"
0x14000467e  mov     rbx, [rsp+0E8h+arg_40]
0x140004686  lea     r12, asc_14000A7D0; "\b"
0x14000468d  mov     rdi, [rsp+0E8h+arg_38]
0x140004695  lea     r8, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x14000469c  xor     r13d, r13d
0x14000469f  movzx   r15d, r9w
0x1400046a3  test    dword ptr [r11+2Ch], 200h
0x1400046ab  lea     esi, [r13+8]
0x1400046af  lea     r14d, [r13+2]
0x1400046b3  jz      loc_1400047B6
0x1400046b9  cmp     byte ptr [r11+29h], 5
0x1400046be  jb      loc_1400047B6
0x1400046c4  test    rbx, rbx
0x1400046c7  jz      short loc_1400046D8
0x1400046c9  movzx   ecx, word ptr [rbx]
0x1400046cc  cmp     [rbx], r13w
0x1400046d0  jz      short loc_1400046DB
0x1400046d2  mov     r14, [rbx+8]
0x1400046d6  jmp     short loc_1400046DE
0x1400046d8  mov     rcx, rsi
0x1400046db  mov     r14, rbp
0x1400046de  test    rbx, rbx
0x1400046e1  mov     r9, rbx
0x1400046e4  cmovz   r9, r12
0x1400046e8  test    rdi, rdi
0x1400046eb  jz      short loc_1400046FD
0x1400046ed  movzx   r8d, word ptr [rdi]
0x1400046f1  cmp     [rdi], r13w
0x1400046f5  jz      short loc_140004700
0x1400046f7  mov     r10, [rdi+8]
0x1400046fb  jmp     short loc_140004703
0x1400046fd  mov     r8, rsi
0x140004700  mov     r10, rbp
0x140004703  mov     rax, cs:pfnWppTraceMessage
0x14000470a  test    rdi, rdi
0x14000470d  mov     [rsp+0E8h+var_58], r13
0x140004715  mov     rdx, rdi
0x140004718  mov     [rsp+0E8h+var_60], 4
0x140004724  cmovz   rdx, r12
0x140004728  lea     r12, [rsp+0E8h+arg_48]
0x140004730  mov     [rsp+0E8h+var_68], r12
0x140004738  mov     [rsp+0E8h+var_70], rcx
0x14000473d  lea     rcx, [rsp+0E8h+arg_30]
0x140004745  mov     [rsp+0E8h+var_78], r14
0x14000474a  mov     r14d, 2
0x140004750  mov     [rsp+0E8h+var_80], r14
0x140004755  mov     [rsp+0E8h+var_88], r9
0x14000475a  mov     r9d, r15d
0x14000475d  mov     [rsp+0E8h+var_90], r8
0x140004762  lea     r8, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140004769  mov     [rsp+0E8h+var_98], r10
0x14000476e  mov     [rsp+0E8h+var_A0], r14
0x140004773  mov     [rsp+0E8h+var_A8], rdx
0x140004778  lea     edx, [r14+29h]
0x14000477c  mov     [rsp+0E8h+var_B0], 4
0x140004785  mov     [rsp+0E8h+var_B8], rcx
0x14000478a  lea     rcx, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140004791  mov     [rsp+0E8h+var_C0], 23h ; '#'
0x14000479a  mov     [rsp+0E8h+var_C8], rcx
0x14000479f  mov     rcx, [r11+18h]
0x1400047a3  call    _guard_dispatch_icall
0x1400047a8  lea     r8, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x1400047af  lea     r12, asc_14000A7D0; "\b"
0x1400047b6  test    rbx, rbx
0x1400047b9  jz      short loc_1400047CA
0x1400047bb  movzx   eax, word ptr [rbx]
0x1400047be  cmp     [rbx], r13w
0x1400047c2  jz      short loc_1400047CD
0x1400047c4  mov     rcx, [rbx+8]
0x1400047c8  jmp     short loc_1400047D0
0x1400047ca  mov     rax, rsi
0x1400047cd  mov     rcx, rbp
0x1400047d0  test    rbx, rbx
0x1400047d3  cmovz   rbx, r12
0x1400047d7  test    rdi, rdi
0x1400047da  jz      short loc_1400047EC
0x1400047dc  movzx   esi, word ptr [rdi]
0x1400047df  cmp     [rdi], r13w
0x1400047e3  jz      short loc_1400047E9
0x1400047e5  mov     rbp, [rdi+8]
0x1400047e9  test    rdi, rdi
0x1400047ec  mov     [rsp+0E8h+var_50], r13
0x1400047f4  lea     rdx, [rsp+0E8h+arg_48]
0x1400047fc  mov     [rsp+0E8h+var_58], 4
0x140004808  lea     r9, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x14000480f  mov     [rsp+0E8h+var_60], rdx
0x140004817  cmovz   rdi, r12
0x14000481b  mov     [rsp+0E8h+var_68], rax
0x140004823  mov     edx, 5
0x140004828  mov     [rsp+0E8h+var_70], rcx
0x14000482d  lea     rax, [rsp+0E8h+arg_30]
0x140004835  mov     [rsp+0E8h+var_78], r14
0x14000483a  xor     ecx, ecx
0x14000483c  mov     [rsp+0E8h+var_80], rbx
0x140004841  mov     [rsp+0E8h+var_88], rsi
0x140004846  mov     [rsp+0E8h+var_90], rbp
0x14000484b  mov     [rsp+0E8h+var_98], r14
0x140004850  mov     [rsp+0E8h+var_A0], rdi
0x140004855  mov     [rsp+0E8h+var_A8], 4
0x14000485e  mov     [rsp+0E8h+var_B0], rax
0x140004863  mov     [rsp+0E8h+var_B8], 23h ; '#'
0x14000486c  mov     [rsp+0E8h+var_C0], r8
0x140004871  lea     r8d, [rdx+5]
0x140004875  mov     word ptr [rsp+0E8h+var_C8], r15w
0x14000487b  call    cs:__imp_WppAutoLogTrace
0x140004882  nop     dword ptr [rax+rax+00h]
0x140004887  add     rsp, 0A8h
0x14000488e  pop     r15
0x140004890  pop     r14
0x140004892  pop     r13
0x140004894  pop     r12
0x140004896  pop     rdi
0x140004897  pop     rsi
0x140004898  pop     rbp
0x140004899  pop     rbx
0x14000489a  retn
```
