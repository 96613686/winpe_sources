# MinAsn1ExtractParsedCertificatesFromSignedData

- ea: `0x18004ddfc`
- end: `0x18004de72`
- name: `MinAsn1ExtractParsedCertificatesFromSignedData`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180017cd4`

## callees

- `0x180033980`
- `0x18004cffc`
- `0x18004d040`
- `0x18004ddfc`

## pseudocode

```c
__int64 __fastcall MinAsn1ExtractParsedCertificatesFromSignedData(__int64 a1, __int64 a2, _DWORD *a3, __int64 a4)
{
  int v6; // ebx
  __int64 result; // rax
  _BYTE v8[112]; // [rsp+20h] [rbp-158h] BYREF
  _BYTE v9[8]; // [rsp+90h] [rbp-E8h] BYREF
  int v10; // [rsp+98h] [rbp-E0h]

  v6 = a1;
  result = MinAsn1ParseSignedData(a1, a2, v8);
  if ( (int)result > 0 )
  {
    result = MinAsn1ParseSignedDataCertificatesEx(v9, a3, a4);
    if ( (int)result >= 0 )
      return result;
    result = (unsigned int)(v6 - v10 + result);
  }
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x18004ddfc  push    rbx
0x18004ddfe  push    rsi
0x18004ddff  push    rdi
0x18004de00  sub     rsp, 160h
0x18004de07  mov     rax, cs:__security_cookie
0x18004de0e  xor     rax, rsp
0x18004de11  mov     [rsp+178h+var_28], rax
0x18004de19  mov     rdi, r8
0x18004de1c  mov     rsi, r9
0x18004de1f  lea     r8, [rsp+178h+var_158]
0x18004de24  mov     rbx, rcx
0x18004de27  call    MinAsn1ParseSignedData
0x18004de2c  test    eax, eax
0x18004de2e  jle     short loc_18004DE50
0x18004de30  mov     r8, rsi
0x18004de33  lea     rcx, [rsp+178h+var_E8]
0x18004de3b  mov     rdx, rdi
0x18004de3e  call    MinAsn1ParseSignedDataCertificatesEx
0x18004de43  test    eax, eax
0x18004de45  jns     short loc_18004DE56
0x18004de47  sub     ebx, [rsp+178h+var_E0]
0x18004de4e  add     eax, ebx
0x18004de50  mov     dword ptr [rdi], 0
0x18004de56  mov     rcx, [rsp+178h+var_28]
0x18004de5e  xor     rcx, rsp; StackCookie
0x18004de61  call    __security_check_cookie
0x18004de66  add     rsp, 160h
0x18004de6d  pop     rdi
0x18004de6e  pop     rsi
0x18004de6f  pop     rbx
0x18004de70  retn
```
