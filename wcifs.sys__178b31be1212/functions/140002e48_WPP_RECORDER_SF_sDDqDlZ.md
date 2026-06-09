# WPP_RECORDER_SF_sDDqDlZ

- ea: `0x140002e48`
- end: `0x140003085`
- name: `WPP_RECORDER_SF_sDDqDlZ`
- size: `573`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int, int, int, char, char, char, char, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140025270`

## callees

- `0x140002e48`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140003068`
- `WppRecorder!WppAutoLogTrace` at `0x140003068`

## string_xrefs

- `0x140002e83`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140002f66`: `onecore\base\fs\wci\wcifs\create.c`
- `0x140002f94`: `onecore\base\fs\wci\wcifs\create.c`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_sDDqDlZ(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        char a8,
        char a9,
        char a10,
        char a11,
        unsigned __int16 *a12)
{
  __int64 v13; // rcx
  const wchar_t *v14; // rdx
  const wchar_t *v15; // rax
  int v17; // [rsp+20h] [rbp-D8h]
  _DWORD v18[18]; // [rsp+B0h] [rbp-48h] BYREF

  v18[0] = 2768;
  if ( (HIDWORD(wil_details_featureDescriptors_a->Timer) & 0x10) == 0
    || BYTE1(wil_details_featureDescriptors_a->Timer) < 3u )
  {
    goto LABEL_11;
  }
  if ( !a12 )
  {
    v13 = 8;
    goto LABEL_7;
  }
  v13 = *a12;
  if ( !*a12 )
  {
LABEL_7:
    v14 = L"NULL";
    goto LABEL_8;
  }
  v14 = (const wchar_t *)*((_QWORD *)a12 + 1);
LABEL_8:
  v15 = a12;
  if ( !a12 )
    v15 = L"\b";
  ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, __int64, const char *, __int64, _DWORD *, __int64, char *, __int64, char *, __int64, char *, __int64, char *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, _QWORD))pfnWppTraceMessage)(
    wil_details_featureDescriptors_a->AttachedDevice,
    43,
    WPP_852a4bc871f63f63d337338550f67970_Traceguids,
    61,
    "onecore\\base\\fs\\wci\\wcifs\\create.c",
    35,
    v18,
    4,
    &a8,
    4,
    &a9,
    8,
    &a10,
    4,
    &a11,
    4,
    v15,
    2,
    v14,
    v13,
    0);
LABEL_11:
  LOWORD(v17) = 61;
  return WppAutoLogTrace(
           a1,
           3,
           5,
           WPP_852a4bc871f63f63d337338550f67970_Traceguids,
           v17,
           "onecore\\base\\fs\\wci\\wcifs\\create.c",
           35,
           v18,
           4,
           &a8);
}

```

## disassembly

```asm
0x140002e48  mov     rax, rsp
0x140002e4b  push    rbx
0x140002e4c  push    rbp
0x140002e4d  push    rsi
0x140002e4e  push    rdi
0x140002e4f  push    r14
0x140002e51  push    r15
0x140002e53  sub     rsp, 0C8h
0x140002e5a  mov     r11, cs:wil_details_featureDescriptors_a
0x140002e61  lea     rdi, aNull_0; "NULL"
0x140002e68  mov     rbx, [rsp+0F8h+arg_58]
0x140002e70  lea     r8, asc_14000A7D0; "\b"
0x140002e77  xor     ebp, ebp
0x140002e79  mov     dword ptr [rax-48h], 0AD0h
0x140002e80  mov     rsi, rcx
0x140002e83  lea     rcx, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140002e8a  mov     eax, [r11+2Ch]
0x140002e8e  lea     r14d, [rbp+8]
0x140002e92  lea     r9d, [rbp+3Dh]
0x140002e96  lea     r15d, [rbp+4]
0x140002e9a  test    al, 10h
0x140002e9c  jz      loc_140002F9B
0x140002ea2  cmp     byte ptr [r11+29h], 3
0x140002ea7  jb      loc_140002F9B
0x140002ead  test    rbx, rbx
0x140002eb0  jz      short loc_140002EC0
0x140002eb2  movzx   ecx, word ptr [rbx]
0x140002eb5  cmp     [rbx], bp
0x140002eb8  jz      short loc_140002EC3
0x140002eba  mov     rdx, [rbx+8]
0x140002ebe  jmp     short loc_140002EC6
0x140002ec0  mov     rcx, r14
0x140002ec3  mov     rdx, rdi
0x140002ec6  mov     [rsp+0F8h+var_58], rbp
0x140002ece  test    rbx, rbx
0x140002ed1  mov     [rsp+0F8h+var_60], rcx
0x140002ed9  mov     rax, rbx
0x140002edc  mov     rcx, [r11+18h]
0x140002ee0  cmovz   rax, r8
0x140002ee4  mov     [rsp+0F8h+var_68], rdx
0x140002eec  lea     r8, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140002ef3  mov     [rsp+0F8h+var_70], 2
0x140002eff  mov     edx, 2Bh ; '+'
0x140002f04  mov     [rsp+0F8h+var_78], rax
0x140002f0c  lea     rax, [rsp+0F8h+arg_50]
0x140002f14  mov     [rsp+0F8h+var_80], r15
0x140002f19  mov     [rsp+0F8h+var_88], rax
0x140002f1e  lea     rax, [rsp+0F8h+arg_48]
0x140002f26  mov     [rsp+0F8h+var_90], r15
0x140002f2b  mov     [rsp+0F8h+var_98], rax
0x140002f30  lea     rax, [rsp+0F8h+arg_40]
0x140002f38  mov     [rsp+0F8h+var_A0], r14
0x140002f3d  mov     [rsp+0F8h+var_A8], rax
0x140002f42  lea     rax, [rsp+0F8h+arg_38]
0x140002f4a  mov     [rsp+0F8h+var_B0], r15
0x140002f4f  mov     [rsp+0F8h+var_B8], rax
0x140002f54  lea     rax, [rsp+0F8h+var_48]
0x140002f5c  mov     [rsp+0F8h+var_C0], r15
0x140002f61  mov     [rsp+0F8h+var_C8], rax
0x140002f66  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140002f6d  mov     [rsp+0F8h+var_D0], 23h ; '#'
0x140002f76  mov     [rsp+0F8h+var_D8], rax
0x140002f7b  mov     rax, cs:pfnWppTraceMessage
0x140002f82  call    _guard_dispatch_icall
0x140002f87  lea     r8, asc_14000A7D0; "\b"
0x140002f8e  mov     r9d, 3Dh ; '='
0x140002f94  lea     rcx, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140002f9b  test    rbx, rbx
0x140002f9e  jz      short loc_140002FAE
0x140002fa0  movzx   eax, word ptr [rbx]
0x140002fa3  cmp     [rbx], bp
0x140002fa6  jz      short loc_140002FB1
0x140002fa8  mov     rdi, [rbx+8]
0x140002fac  jmp     short loc_140002FB1
0x140002fae  mov     rax, r14
0x140002fb1  mov     [rsp+0F8h+var_50], rbp
0x140002fb9  test    rbx, rbx
0x140002fbc  mov     [rsp+0F8h+var_58], rax
0x140002fc4  mov     edx, 3
0x140002fc9  mov     [rsp+0F8h+var_60], rdi
0x140002fd1  lea     rax, [rsp+0F8h+arg_50]
0x140002fd9  mov     [rsp+0F8h+var_68], 2
0x140002fe5  cmovz   rbx, r8
0x140002fe9  mov     [rsp+0F8h+var_70], rbx
0x140002ff1  mov     [rsp+0F8h+var_78], r15
0x140002ff9  lea     r8d, [rdx+2]
0x140002ffd  mov     [rsp+0F8h+var_80], rax
0x140003002  lea     rax, [rsp+0F8h+arg_48]
0x14000300a  mov     [rsp+0F8h+var_88], r15
0x14000300f  mov     [rsp+0F8h+var_90], rax
0x140003014  lea     rax, [rsp+0F8h+arg_40]
0x14000301c  mov     [rsp+0F8h+var_98], r14
0x140003021  mov     [rsp+0F8h+var_A0], rax
0x140003026  lea     rax, [rsp+0F8h+arg_38]
0x14000302e  mov     [rsp+0F8h+var_A8], r15
0x140003033  mov     [rsp+0F8h+var_B0], rax
0x140003038  lea     rax, [rsp+0F8h+var_48]
0x140003040  mov     [rsp+0F8h+var_B8], r15
0x140003045  mov     [rsp+0F8h+var_C0], rax
0x14000304a  mov     [rsp+0F8h+var_C8], 23h ; '#'
0x140003053  mov     [rsp+0F8h+var_D0], rcx
0x140003058  mov     rcx, rsi
0x14000305b  mov     word ptr [rsp+0F8h+var_D8], r9w
0x140003061  lea     r9, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140003068  call    cs:__imp_WppAutoLogTrace
0x14000306f  nop     dword ptr [rax+rax+00h]
0x140003074  add     rsp, 0C8h
0x14000307b  pop     r15
0x14000307d  pop     r14
0x14000307f  pop     rdi
0x140003080  pop     rsi
0x140003081  pop     rbp
0x140003082  pop     rbx
0x140003083  retn
```
