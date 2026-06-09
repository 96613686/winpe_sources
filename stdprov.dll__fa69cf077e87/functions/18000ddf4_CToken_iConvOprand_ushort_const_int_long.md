# CToken::iConvOprand(ushort const *,int,long &)

- ea: `0x18000ddf4`
- end: `0x18000deab`
- name: `?iConvOprand@CToken@@QEAAJPEBGHAEAJ@Z`
- size: `183`
- prototype: `__int64 __fastcall(CToken *__hidden this, const unsigned __int16 *, int, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000dbf8`

## callees

- `0x1800087f0`
- `0x18000b458`
- `0x18000ddf4`

## import_xrefs

- `msvcrt!_wtoi` at `0x18000de85`
- `msvcrt!_wtoi` at `0x18000de85`
- `api-ms-win-core-string-l1-1-0!GetStringTypeExW` at `0x18000de57`
- `api-ms-win-core-string-l1-1-0!GetStringTypeExW` at `0x18000de57`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CToken::iConvOprand(CToken *this, const unsigned __int16 *a2, int a3, int *a4)
{
  const unsigned __int16 *v5; // rbx
  unsigned int v6; // edi
  unsigned __int16 i; // ax
  wchar_t *String; // [rsp+30h] [rbp-10h] BYREF
  __int16 v10; // [rsp+38h] [rbp-8h] BYREF
  int v11; // [rsp+3Ch] [rbp-4h]
  CToken *SrcStr; // [rsp+60h] [rbp+20h] BYREF
  int CharType; // [rsp+70h] [rbp+30h] BYREF

  CharType = a3;
  SrcStr = this;
  v5 = a2;
  v10 = 0;
  String = (wchar_t *)&v10;
  v11 = 0;
  v6 = 0;
  for ( i = *a2; i; i = *v5 )
  {
    LOWORD(SrcStr) = i;
    LOWORD(CharType) = 0;
    if ( !GetStringTypeExW(0x7Fu, 1u, (LPCWCH)&SrcStr, 1, (LPWORD)&CharType) || (CharType & 4) == 0 )
      break;
    TString::operator+=((TString *)&String);
    ++v6;
    ++v5;
  }
  *a4 = _wtoi(String);
  TString::Empty((TString *)&String);
  return v6;
}

```

## disassembly

```asm
0x18000ddf4  mov     rax, rsp
0x18000ddf7  mov     [rax+10h], rbx
0x18000ddfb  mov     [rax+20h], rsi
0x18000ddff  mov     [rax+18h], r8d
0x18000de03  mov     [rax+8], rcx
0x18000de07  push    rbp
0x18000de08  push    rdi
0x18000de09  push    r14
0x18000de0b  mov     rbp, rsp
0x18000de0e  sub     rsp, 40h
0x18000de12  mov     rsi, r9
0x18000de15  mov     rbx, rdx
0x18000de18  xor     r14d, r14d
0x18000de1b  mov     [rbp+var_8], r14w
0x18000de20  lea     rax, [rbp+var_8]
0x18000de24  mov     [rbp+String], rax
0x18000de28  mov     [rbp+var_4], r14d
0x18000de2c  mov     edi, r14d
0x18000de2f  movzx   eax, word ptr [rdx]
0x18000de32  jmp     short loc_18000DE7C
0x18000de34  mov     word ptr [rbp+SrcStr], ax
0x18000de38  mov     word ptr [rbp+CharType], r14w
0x18000de3d  lea     rax, [rbp+CharType]
0x18000de41  mov     [rsp+40h+lpCharType], rax; lpCharType
0x18000de46  mov     r9d, 1; cchSrc
0x18000de4c  lea     r8, [rbp+SrcStr]; lpSrcStr
0x18000de50  mov     edx, r9d; dwInfoType
0x18000de53  lea     ecx, [r9+7Eh]; Locale
0x18000de57  call    cs:__imp_GetStringTypeExW
0x18000de5d  test    eax, eax
0x18000de5f  jz      short loc_18000DE81
0x18000de61  test    byte ptr [rbp+CharType], 4
0x18000de65  jz      short loc_18000DE81
0x18000de67  movzx   edx, word ptr [rbx]
0x18000de6a  lea     rcx, [rbp+String]; this
0x18000de6e  call    ??YTString@@QEAAAEAV0@G@Z; TString::operator+=(ushort)
0x18000de73  inc     edi
0x18000de75  add     rbx, 2
0x18000de79  movzx   eax, word ptr [rbx]
0x18000de7c  test    ax, ax
0x18000de7f  jnz     short loc_18000DE34
0x18000de81  mov     rcx, [rbp+String]; String
0x18000de85  call    cs:__imp__wtoi
0x18000de8b  mov     [rsi], eax
0x18000de8d  lea     rcx, [rbp+String]; this
0x18000de91  call    ?Empty@TString@@QEAAXXZ; TString::Empty(void)
0x18000de96  mov     eax, edi
0x18000de98  mov     rbx, [rsp+40h+arg_8]
0x18000de9d  mov     rsi, [rsp+40h+arg_18]
0x18000dea2  add     rsp, 40h
0x18000dea6  pop     r14
0x18000dea8  pop     rdi
0x18000dea9  pop     rbp
0x18000deaa  retn
```
