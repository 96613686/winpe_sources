# CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)

- ea: `0x180004288`
- end: `0x180004337`
- name: `?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z`
- size: `175`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `204`
- callee_count: `3`
- tags: ``

## callers

- `0x180003020`
- `0x1800031fc`
- `0x1800032a0`
- `0x180003318`
- `0x180003540`
- `0x180003650`
- `0x1800036ec`
- `0x180003950`
- `0x180003c18`
- `0x180003d80`
- `0x180003e14`
- `0x180003ed8`
- `0x18000405c`
- `0x1800044d8`
- `0x180004520`
- `0x180004790`
- `0x1800047d0`
- `0x180004840`
- `0x180004880`
- `0x180004930`
- `0x180004ca8`
- `0x180004d60`
- `0x180004d98`
- `0x180004e18`
- `0x180004eb0`
- `0x180005050`
- `0x1800050f0`
- `0x180005260`
- `0x1800052a0`
- `0x180005490`
- `0x180005560`
- `0x1800056d0`
- `0x1800057d0`
- `0x180005810`
- `0x180005920`
- `0x180005960`
- `0x1800059f0`
- `0x180005ab0`
- `0x180005b30`
- `0x18000f3d0`
- `0x18000f530`
- `0x18000f5a0`
- `0x180018e30`
- `0x180018f80`
- `0x180019110`
- `0x180019170`
- `0x180019210`
- `0x1800192e0`
- `0x180019400`
- `0x180019530`

## callees

- `0x180004288`
- `0x18003c560`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(int a1)
{
  __int64 v1; // rdx
  __int64 result; // rax
  unsigned __int64 v3; // rcx
  __int128 v4; // [rsp+30h] [rbp-28h] BYREF

  v1 = (unsigned int)a1;
  result = 1;
  v4 = 0;
  BYTE2(v4) = 1;
  BYTE4(v4) = 1;
  if ( a1 < 0 )
  {
    v3 = 0x4000000000000000LL;
  }
  else
  {
    result = 0;
    v3 = 0x8000000000000000uLL;
  }
  LOWORD(v4) = result;
  *((_QWORD *)&v4 + 1) = v1 | v3;
  if ( CEtwProviderT<void>::g_etwApi && CChkMacroETWLoggerT<CEmptyType>::g_chkMacroETWProvider )
  {
    result = ((__int64 (__fastcall *)(__int64, __int128 *))qword_180046F30)(
               CChkMacroETWLoggerT<CEmptyType>::g_chkMacroETWProvider,
               &v4);
    if ( (_BYTE)result )
      return ((__int64 (__fastcall *)(__int64, __int128 *, _QWORD, _QWORD))qword_180046F38)(
               CChkMacroETWLoggerT<CEmptyType>::g_chkMacroETWProvider,
               &v4,
               0,
               0);
  }
  return result;
}

```

## disassembly

```asm
0x180004288  sub     rsp, 58h
0x18000428c  mov     rax, cs:__security_cookie
0x180004293  xor     rax, rsp
0x180004296  mov     [rsp+58h+var_18], rax
0x18000429b  mov     edx, ecx
0x18000429d  mov     eax, 1
0x1800042a2  xorps   xmm0, xmm0
0x1800042a5  movups  [rsp+58h+var_28], xmm0
0x1800042aa  mov     byte ptr [rsp+58h+var_28+2], al
0x1800042ae  mov     byte ptr [rsp+58h+var_28+4], al
0x1800042b2  test    ecx, ecx
0x1800042b4  js      short loc_1800042C4
0x1800042b6  xor     eax, eax
0x1800042b8  mov     rcx, 8000000000000000h
0x1800042c2  jmp     short loc_1800042CE
0x1800042c4  mov     rcx, 4000000000000000h
0x1800042ce  or      rcx, rdx
0x1800042d1  mov     word ptr [rsp+58h+var_28], ax
0x1800042d6  cmp     cs:?g_etwApi@?$CEtwProviderT@X@@1UCETWApiSet@1@A, 0; CEtwProviderT<void>::CETWApiSet CEtwProviderT<void>::g_etwApi
0x1800042de  mov     qword ptr [rsp+58h+var_28+8], rcx
0x1800042e3  jz      short loc_180004324
0x1800042e5  mov     rcx, cs:?g_chkMacroETWProvider@?$CChkMacroETWLoggerT@VCEmptyType@@@@0V?$CEtwProviderT@X@@A; CEtwProviderT<void> CChkMacroETWLoggerT<CEmptyType>::g_chkMacroETWProvider
0x1800042ec  test    rcx, rcx
0x1800042ef  jz      short loc_180004324
0x1800042f1  mov     rax, cs:qword_180046F30
0x1800042f8  lea     rdx, [rsp+58h+var_28]
0x1800042fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004302  test    al, al
0x180004304  jz      short loc_180004324
0x180004306  mov     rcx, cs:?g_chkMacroETWProvider@?$CChkMacroETWLoggerT@VCEmptyType@@@@0V?$CEtwProviderT@X@@A; CEtwProviderT<void> CChkMacroETWLoggerT<CEmptyType>::g_chkMacroETWProvider
0x18000430d  lea     rdx, [rsp+58h+var_28]
0x180004312  mov     rax, cs:qword_180046F38
0x180004319  xor     r9d, r9d
0x18000431c  xor     r8d, r8d
0x18000431f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004324  mov     rcx, [rsp+58h+var_18]
0x180004329  xor     rcx, rsp; StackCookie
0x18000432c  call    __security_check_cookie
0x180004331  add     rsp, 58h
0x180004335  retn
```
