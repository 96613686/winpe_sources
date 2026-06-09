# GetBootstrapDataSourcePath

- ea: `0x100438ed0`
- end: `0x100439045`
- name: `GetBootstrapDataSourcePath`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x100439330`

## callees

- `0x100401580`
- `0x100401800`
- `0x100402080`
- `0x1004021d0`
- `0x100438ed0`
- `0x1004534f8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100438f54`
- `KERNEL32!GetLastError` at `0x100438f54`
- `svl!SvlPathAppendTrailingSeparator` at `0x100439004`
- `svl!SvlPathAppendTrailingSeparator` at `0x100439004`
- `svl!SvlPathAppend` at `0x100438fef`
- `svl!SvlPathAppend` at `0x100438fef`
- `svl!SvlPathGetParent` at `0x100438fc0`
- `svl!SvlPathGetParent` at `0x100438fc0`

## string_xrefs

- `0x100438fe2`: `templatedata`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetBootstrapDataSourcePath(_WORD *a1, __int64 a2)
{
  signed int LastError; // eax
  unsigned int appended; // ebx
  int Parent; // edi
  _BYTE v8[8]; // [rsp+30h] [rbp-248h] BYREF
  HKEY v9; // [rsp+38h] [rbp-240h] BYREF
  DWORD v10; // [rsp+40h] [rbp-238h] BYREF
  __int64 v11; // [rsp+48h] [rbp-230h]
  BYTE v12[520]; // [rsp+50h] [rbp-228h] BYREF
  __int16 v13; // [rsp+258h] [rbp-20h]

  v11 = -2;
  v9 = 0;
  memset_0(v12, 0, 0x20Au);
  v10 = 522;
  if ( (unsigned int)IniRegOpenKeyExW(-2147483646, (int)qword_10049F360 + 44822, 0, 1, &v9)
    || (unsigned int)IniRegQueryValueExW((int)v9, (int)L"SQLBinRoot", 0, 0, v12, &v10) )
  {
    LastError = GetLastError();
    appended = LastError;
    if ( LastError > 0 )
      appended = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_11;
  }
  v13 = 0;
  *a1 = 0;
  v8[0] = 0;
  Parent = SvlPathGetParent(v12, a1, a2, v8);
  _mm_lfence();
  if ( Parent >= 0 )
  {
    Parent = SvlPathAppend(a1, a2, L"templatedata");
    _mm_lfence();
    if ( Parent >= 0 )
    {
      appended = SvlPathAppendTrailingSeparator(a1, a2);
      _mm_lfence();
LABEL_11:
      if ( v9 )
        IniRegCloseKey(v9);
      return appended;
    }
  }
  if ( v9 )
    IniRegCloseKey(v9);
  return (unsigned int)Parent;
}

```

## disassembly

```asm
0x100438ed0  mov     rax, rsp
0x100438ed3  push    rdi
0x100438ed4  sub     rsp, 270h
0x100438edb  mov     [rsp+278h+var_230], 0FFFFFFFFFFFFFFFEh
0x100438ee4  mov     [rax+18h], rbx
0x100438ee8  mov     [rax+20h], rsi
0x100438eec  mov     rax, cs:__security_cookie
0x100438ef3  xor     rax, rsp
0x100438ef6  mov     [rsp+278h+var_18], rax
0x100438efe  mov     rsi, rdx
0x100438f01  mov     rbx, rcx
0x100438f04  xor     edi, edi
0x100438f06  mov     [rsp+278h+var_240], rdi
0x100438f0b  xor     edx, edx; Val
0x100438f0d  mov     r8d, 20Ah; Size
0x100438f13  lea     rcx, [rsp+278h+var_228]; void *
0x100438f18  call    memset_0
0x100438f1d  mov     [rsp+278h+var_238], 20Ah
0x100438f25  mov     rdx, cs:qword_10049F360
0x100438f2c  add     rdx, 0AF16h; int
0x100438f33  lea     rax, [rsp+278h+var_240]
0x100438f38  mov     [rsp+278h+var_258], rax; PHKEY
0x100438f3d  lea     r9d, [rdi+1]; int
0x100438f41  xor     r8d, r8d; int
0x100438f44  mov     rcx, 0FFFFFFFF80000002h; int
0x100438f4b  call    IniRegOpenKeyExW
0x100438f50  test    eax, eax
0x100438f52  jz      short loc_100438F72
0x100438f54  call    cs:__imp_GetLastError
0x100438f5a  mov     ebx, eax
0x100438f5c  test    eax, eax
0x100438f5e  jle     loc_10043900F
0x100438f64  movzx   ebx, ax
0x100438f67  or      ebx, 80070000h
0x100438f6d  jmp     loc_10043900F
0x100438f72  lea     rax, [rsp+278h+var_238]
0x100438f77  mov     [rsp+278h+var_250], rax; LPDWORD
0x100438f7c  lea     rax, [rsp+278h+var_228]
0x100438f81  mov     [rsp+278h+var_258], rax; LPBYTE
0x100438f86  xor     r9d, r9d; int
0x100438f89  xor     r8d, r8d; int
0x100438f8c  lea     rdx, aSqlbinroot; "SQLBinRoot"
0x100438f93  mov     rcx, [rsp+278h+var_240]; int
0x100438f98  call    IniRegQueryValueExW
0x100438f9d  test    eax, eax
0x100438f9f  jnz     short loc_100438F54
0x100438fa1  mov     [rsp+278h+var_20], di
0x100438fa9  mov     [rbx], di
0x100438fac  mov     [rsp+278h+var_248], al
0x100438fb0  lea     r9, [rsp+278h+var_248]
0x100438fb5  mov     r8, rsi
0x100438fb8  mov     rdx, rbx
0x100438fbb  lea     rcx, [rsp+278h+var_228]
0x100438fc0  call    cs:__imp_SvlPathGetParent
0x100438fc6  mov     edi, eax
0x100438fc8  lfence
0x100438fcb  test    eax, eax
0x100438fcd  jns     short loc_100438FE2
0x100438fcf  mov     rcx, [rsp+278h+var_240]
0x100438fd4  test    rcx, rcx
0x100438fd7  jz      short loc_100438FDE
0x100438fd9  call    IniRegCloseKey
0x100438fde  mov     eax, edi
0x100438fe0  jmp     short loc_100439020
0x100438fe2  lea     r8, aTemplatedata; "templatedata"
0x100438fe9  mov     rdx, rsi
0x100438fec  mov     rcx, rbx
0x100438fef  call    cs:__imp_SvlPathAppend
0x100438ff5  mov     edi, eax
0x100438ff7  lfence
0x100438ffa  test    eax, eax
0x100438ffc  js      short loc_100438FCF
0x100438ffe  mov     rdx, rsi
0x100439001  mov     rcx, rbx
0x100439004  call    cs:__imp_SvlPathAppendTrailingSeparator
0x10043900a  mov     ebx, eax
0x10043900c  lfence
0x10043900f  mov     rcx, [rsp+278h+var_240]
0x100439014  test    rcx, rcx
0x100439017  jz      short loc_10043901E
0x100439019  call    IniRegCloseKey
0x10043901e  mov     eax, ebx
0x100439020  mov     rcx, [rsp+278h+var_18]
0x100439028  xor     rcx, rsp; StackCookie
0x10043902b  call    __security_check_cookie
0x100439030  lea     r11, [rsp+278h+var_8]
0x100439038  mov     rbx, [r11+20h]
0x10043903c  mov     rsi, [r11+28h]
0x100439040  mov     rsp, r11
0x100439043  pop     rdi
0x100439044  retn
```
