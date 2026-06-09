# DwmGetIdealIconicThumbnailSize(bool,tagSIZE *)

- ea: `0x18006c1dc`
- end: `0x18006c2d8`
- name: `?DwmGetIdealIconicThumbnailSize@@YAH_NPEAUtagSIZE@@@Z`
- size: `252`
- prototype: `__int64 __fastcall(bool, struct tagSIZE *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a690`
- `0x1800403a0`
- `0x18004220c`

## callees

- `0x18006c1dc`
- `0x180095130`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18006c214`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18006c28b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18006c2a6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18006c2ba`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18006c2cd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18006c214`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18006c28b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18006c2a6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18006c2ba`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18006c2cd`
- `USER32!SystemParametersInfoW` at `0x18006c234`
- `USER32!SystemParametersInfoW` at `0x18006c234`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetDpiForSystem` at `0x18006c1fc`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetDpiForSystem` at `0x18006c1fc`

## pseudocode

```c
__int64 __fastcall DwmGetIdealIconicThumbnailSize(char a1, struct tagSIZE *a2)
{
  unsigned int v4; // edi
  int DpiForSystem; // eax
  int v6; // esi
  LONG v7; // eax
  int v9; // ecx
  int v10; // r10d
  LONG v11; // eax
  LONG cy; // ecx
  __int128 pvParam; // [rsp+20h] [rbp-48h] BYREF

  v4 = 0;
  DpiForSystem = GetDpiForSystem();
  a2->cy = 200;
  a2->cx = 200;
  v6 = DpiForSystem;
  v7 = MulDiv(200, DpiForSystem, 96);
  a2->cx = v7;
  a2->cy = v7;
  pvParam = 0;
  if ( SystemParametersInfoW(0x30u, 0, &pvParam, 0) )
  {
    v9 = 0;
    v10 = 0;
    if ( HIDWORD(pvParam) - DWORD1(pvParam) >= 0 )
      v9 = HIDWORD(pvParam) - DWORD1(pvParam);
    if ( DWORD2(pvParam) - (int)pvParam >= 0 )
      v10 = DWORD2(pvParam) - pvParam;
    if ( v9 * a2->cx >= v10 * a2->cy )
      a2->cx = MulDiv(v10, a2->cy, v9);
    else
      a2->cy = MulDiv(v9, a2->cx, v10);
    if ( !a1 )
    {
      v11 = MulDiv(a2->cx, 96, v6);
      cy = a2->cy;
      a2->cx = v11;
      a2->cy = MulDiv(cy, 96, v6);
    }
    return 1;
  }
  return v4;
}

```

## disassembly

```asm
0x18006c1dc  push    rbx
0x18006c1de  push    rbp
0x18006c1df  push    rsi
0x18006c1e0  push    rdi
0x18006c1e1  sub     rsp, 48h
0x18006c1e5  mov     rax, cs:__security_cookie
0x18006c1ec  xor     rax, rsp
0x18006c1ef  mov     [rsp+68h+var_38], rax
0x18006c1f4  mov     rbx, rdx
0x18006c1f7  mov     bpl, cl
0x18006c1fa  xor     edi, edi
0x18006c1fc  call    cs:__imp_GetDpiForSystem
0x18006c202  mov     ecx, 0C8h; nNumber
0x18006c207  lea     r8d, [rdi+60h]; nDenominator
0x18006c20b  mov     edx, eax; nNumerator
0x18006c20d  mov     [rbx+4], ecx
0x18006c210  mov     [rbx], ecx
0x18006c212  mov     esi, eax
0x18006c214  call    cs:__imp_MulDiv
0x18006c21a  xorps   xmm0, xmm0
0x18006c21d  lea     r8, [rsp+68h+pvParam]; pvParam
0x18006c222  lea     ecx, [rdi+30h]; uiAction
0x18006c225  mov     [rbx], eax
0x18006c227  xor     r9d, r9d; fWinIni
0x18006c22a  mov     [rbx+4], eax
0x18006c22d  xor     edx, edx; uiParam
0x18006c22f  movups  [rsp+68h+pvParam], xmm0
0x18006c234  call    cs:__imp_SystemParametersInfoW
0x18006c23a  test    eax, eax
0x18006c23c  jnz     short loc_18006C256
0x18006c23e  mov     eax, edi
0x18006c240  mov     rcx, [rsp+68h+var_38]
0x18006c245  xor     rcx, rsp; StackCookie
0x18006c248  call    __security_check_cookie
0x18006c24d  add     rsp, 48h
0x18006c251  pop     rdi
0x18006c252  pop     rsi
0x18006c253  pop     rbp
0x18006c254  pop     rbx
0x18006c255  retn
0x18006c256  mov     eax, dword ptr [rsp+68h+pvParam+0Ch]
0x18006c25a  mov     ecx, edi
0x18006c25c  sub     eax, dword ptr [rsp+68h+pvParam+4]
0x18006c260  mov     r10d, edi
0x18006c263  mov     edx, [rbx+4]; nNumerator
0x18006c266  mov     r9d, edx
0x18006c269  cmovns  ecx, eax; nNumber
0x18006c26c  mov     eax, dword ptr [rsp+68h+pvParam+8]
0x18006c270  sub     eax, dword ptr [rsp+68h+pvParam]
0x18006c274  cmovns  r10d, eax
0x18006c278  mov     eax, [rbx]
0x18006c27a  imul    eax, ecx
0x18006c27d  imul    r9d, r10d
0x18006c281  cmp     eax, r9d
0x18006c284  jge     short loc_18006C2A0
0x18006c286  mov     edx, [rbx]; nNumerator
0x18006c288  mov     r8d, r10d; nDenominator
0x18006c28b  call    cs:__imp_MulDiv
0x18006c291  mov     [rbx+4], eax
0x18006c294  test    bpl, bpl
0x18006c297  jz      short loc_18006C2B0
0x18006c299  mov     edi, 1
0x18006c29e  jmp     short loc_18006C23E
0x18006c2a0  mov     r8d, ecx; nDenominator
0x18006c2a3  mov     ecx, r10d; nNumber
0x18006c2a6  call    cs:__imp_MulDiv
0x18006c2ac  mov     [rbx], eax
0x18006c2ae  jmp     short loc_18006C294
0x18006c2b0  mov     ecx, [rbx]; nNumber
0x18006c2b2  mov     r8d, esi; nDenominator
0x18006c2b5  mov     edx, 60h ; '`'; nNumerator
0x18006c2ba  call    cs:__imp_MulDiv
0x18006c2c0  mov     ecx, [rbx+4]; nNumber
0x18006c2c3  mov     r8d, esi; nDenominator
0x18006c2c6  mov     edx, 60h ; '`'; nNumerator
0x18006c2cb  mov     [rbx], eax
0x18006c2cd  call    cs:__imp_MulDiv
0x18006c2d3  mov     [rbx+4], eax
0x18006c2d6  jmp     short loc_18006C299
```
