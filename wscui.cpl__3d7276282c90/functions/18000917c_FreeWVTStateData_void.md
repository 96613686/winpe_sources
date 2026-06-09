# FreeWVTStateData(void *)

- ea: `0x18000917c`
- end: `0x180009228`
- name: `?FreeWVTStateData@@YAJPEAX@Z`
- size: `172`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180007854`
- `0x180007938`
- `0x180009ac8`

## callees

- `0x18000917c`
- `0x18000a616`
- `0x18000a640`

## import_xrefs

- `WINTRUST!WinVerifyTrust` at `0x1800091ea`
- `WINTRUST!WinVerifyTrust` at `0x1800091ea`

## pseudocode

```c
LONG __fastcall FreeWVTStateData(void *a1)
{
  LONG result; // eax
  _DWORD pWVTData[14]; // [rsp+20h] [rbp-29h] BYREF
  void *v4; // [rsp+58h] [rbp+Fh]
  GUID pgActionID; // [rsp+80h] [rbp+37h] BYREF

  pgActionID.Data1 = 11191659;
  *(_DWORD *)&pgActionID.Data2 = 298896708;
  *(_DWORD *)pgActionID.Data4 = -1073692020;
  *(_DWORD *)&pgActionID.Data4[4] = -292175281;
  memset_0(pWVTData, 0, 0x58u);
  pWVTData[0] = 88;
  pWVTData[6] = 2;
  pWVTData[12] = 2;
  v4 = a1;
  result = WinVerifyTrust(0, &pgActionID, pWVTData);
  if ( result )
    return (unsigned __int16)result | (((result >> 16) & 0x1FFF) << 16) | 0x80000000;
  return result;
}

```

## disassembly

```asm
0x18000917c  mov     [rsp-8+arg_8], rbx
0x180009181  push    rbp
0x180009182  lea     rbp, [rsp-57h]
0x180009187  sub     rsp, 0A0h
0x18000918e  mov     rax, cs:__security_cookie
0x180009195  xor     rax, rsp
0x180009198  mov     [rbp+57h+var_10], rax
0x18000919c  xor     edx, edx; Val
0x18000919e  mov     [rbp+57h+pgActionID.Data1], 0AAC56Bh
0x1800091a5  mov     rbx, rcx
0x1800091a8  mov     dword ptr [rbp+57h+pgActionID.Data2], 11D0CD44h
0x1800091af  lea     rcx, [rbp+57h+pWVTData]; void *
0x1800091b3  mov     dword ptr [rbp+57h+pgActionID.Data4], 0C000C28Ch
0x1800091ba  mov     dword ptr [rbp+57h+pgActionID.Data4+4], 0EE95C24Fh
0x1800091c1  lea     r8d, [rdx+58h]; Size
0x1800091c5  call    memset_0
0x1800091ca  mov     eax, 2
0x1800091cf  mov     [rbp+57h+pWVTData], 58h ; 'X'
0x1800091d6  lea     r8, [rbp+57h+pWVTData]; pWVTData
0x1800091da  mov     [rbp+57h+var_68], eax
0x1800091dd  lea     rdx, [rbp+57h+pgActionID]; pgActionID
0x1800091e1  mov     [rbp+57h+var_50], eax
0x1800091e4  xor     ecx, ecx; hwnd
0x1800091e6  mov     [rbp+57h+var_48], rbx
0x1800091ea  call    cs:__imp_WinVerifyTrust
0x1800091f0  mov     ecx, eax
0x1800091f2  test    eax, eax
0x1800091f4  jz      short loc_18000920B
0x1800091f6  sar     eax, 10h
0x1800091f9  and     eax, 1FFFh
0x1800091fe  movzx   ecx, cx
0x180009201  shl     eax, 10h
0x180009204  or      eax, ecx
0x180009206  or      eax, 80000000h
0x18000920b  mov     rcx, [rbp+57h+var_10]
0x18000920f  xor     rcx, rsp; StackCookie
0x180009212  call    __security_check_cookie
0x180009217  mov     rbx, [rsp+0A0h+arg_8]
0x18000921f  add     rsp, 0A0h
0x180009226  pop     rbp
0x180009227  retn
```
