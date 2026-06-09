# IsStandardIconContrastRatioAcceptable(void)

- ea: `0x18002dc94`
- end: `0x18002dd3f`
- name: `?IsStandardIconContrastRatioAcceptable@@YA_NXZ`
- size: `171`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001297c`
- `0x1800174a4`

## callees

- `0x18002dc94`
- `0x18002dd48`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x18002dcbc`
- `USER32!SystemParametersInfoW` at `0x18002dcbc`
- `UxTheme!__imp_GetUserColorPreference` at `0x18002dcdc`
- `UxTheme!__imp_GetUserColorPreference` at `0x18002dcdc`
- `UxTheme!__imp_GetColorFromPreference` at `0x18002dcf0`
- `UxTheme!__imp_GetColorFromPreference` at `0x18002dcf0`

## pseudocode

```c
char IsStandardIconContrastRatioAcceptable(void)
{
  char v0; // bl
  unsigned int ColorFromPreference; // eax
  double v2; // xmm6_8
  double v3; // xmm0_8
  __int128 v5; // [rsp+20h] [rbp-28h] BYREF
  __int64 v6; // [rsp+50h] [rbp+8h] BYREF

  v5 = 0;
  LODWORD(v5) = 16;
  v0 = 1;
  if ( SystemParametersInfoW(0x42u, 0x10u, &v5, 0) && (BYTE4(v5) & 1) != 0 )
  {
    v6 = 0;
    GetUserColorPreference(&v6, 0);
    ColorFromPreference = GetColorFromPreference(&v6, 41, 0, 1);
    v2 = _CalculateLuminosity(ColorFromPreference);
    v3 = _CalculateLuminosity(0xFFFFFFFF);
    return (fmax(v2, v3) + 0.05) / (fmin(v2, v3) + 0.05) >= 4.5;
  }
  return v0;
}

```

## disassembly

```asm
0x18002dc94  mov     rax, rsp
0x18002dc97  push    rbx
0x18002dc98  sub     rsp, 40h
0x18002dc9c  mov     edx, 10h; uiParam
0x18002dca1  movaps  xmmword ptr [rax-18h], xmm6
0x18002dca5  xorps   xmm0, xmm0
0x18002dca8  lea     r8, [rax-28h]; pvParam
0x18002dcac  movups  xmmword ptr [rax-28h], xmm0
0x18002dcb0  xor     r9d, r9d; fWinIni
0x18002dcb3  mov     [rax-28h], edx
0x18002dcb6  lea     ecx, [rdx+32h]; uiAction
0x18002dcb9  lea     ebx, [rdx-0Fh]
0x18002dcbc  call    cs:__imp_SystemParametersInfoW
0x18002dcc2  test    eax, eax
0x18002dcc4  jz      short loc_18002DD32
0x18002dcc6  test    [rsp+48h+var_24], bl
0x18002dcca  jz      short loc_18002DD32
0x18002dccc  xor     edx, edx
0x18002dcce  mov     [rsp+48h+arg_0], 0
0x18002dcd7  lea     rcx, [rsp+48h+arg_0]
0x18002dcdc  call    cs:__imp_GetUserColorPreference
0x18002dce2  mov     r9d, ebx
0x18002dce5  lea     edx, [rbx+28h]
0x18002dce8  xor     r8d, r8d
0x18002dceb  lea     rcx, [rsp+48h+arg_0]
0x18002dcf0  call    cs:__imp_GetColorFromPreference
0x18002dcf6  mov     ecx, eax; unsigned int
0x18002dcf8  call    ?_CalculateLuminosity@@YANK@Z; _CalculateLuminosity(ulong)
0x18002dcfd  or      ecx, 0FFFFFFFFh; unsigned int
0x18002dd00  movaps  xmm6, xmm0
0x18002dd03  call    ?_CalculateLuminosity@@YANK@Z; _CalculateLuminosity(ulong)
0x18002dd08  movaps  xmm2, xmm6
0x18002dd0b  minsd   xmm6, xmm0
0x18002dd0f  maxsd   xmm2, xmm0
0x18002dd13  addsd   xmm6, cs:__real@3fa999999999999a
0x18002dd1b  addsd   xmm2, cs:__real@3fa999999999999a
0x18002dd23  divsd   xmm2, xmm6
0x18002dd27  comisd  xmm2, cs:__real@4012000000000000
0x18002dd2f  setnb   bl
0x18002dd32  movaps  xmm6, [rsp+48h+var_18]
0x18002dd37  mov     al, bl
0x18002dd39  add     rsp, 40h
0x18002dd3d  pop     rbx
0x18002dd3e  retn
```
