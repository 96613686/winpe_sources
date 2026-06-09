# CHost::LoadSourceFromMoniker(IMoniker *,ushort * *)

- ea: `0x140007c14`
- end: `0x140007daa`
- name: `?LoadSourceFromMoniker@CHost@@IEAAJPEAUIMoniker@@PEAPEAG@Z`
- size: `406`
- prototype: `__int64 __fastcall(CHost *__hidden this, struct IMoniker *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000757c`

## callees

- `0x14000708c`
- `0x140007c14`
- `0x14001755a`
- `0x1400175a0`
- `0x140018010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140007d55`
- `OLEAUT32!__imp_SysFreeString` at `0x140007d55`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140007d08`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140007d08`
- `ole32!CreateBindCtx` at `0x140007c71`
- `ole32!CreateBindCtx` at `0x140007c71`

## pseudocode

```c
__int64 __fastcall CHost::LoadSourceFromMoniker(CHost *this, struct IMoniker *a2, unsigned __int16 **a3)
{
  char *v6; // rdi
  int v7; // ebx
  UINT v8; // esi
  BSTR v9; // rax
  int v10; // eax
  __int64 v12; // [rsp+30h] [rbp-49h] BYREF
  LPBC ppbc; // [rsp+38h] [rbp-41h] BYREF
  __int128 v14; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v15[16]; // [rsp+50h] [rbp-29h] BYREF
  UINT len; // [rsp+60h] [rbp-19h]
  int v17; // [rsp+64h] [rbp-15h]

  ppbc = 0;
  v12 = 0;
  memset_0(v15, 0, 0x50u);
  v6 = 0;
  v14 = 0;
  v7 = CreateBindCtx(0, &ppbc);
  if ( v7 >= 0 )
  {
    v14 = 0x10u;
    v7 = ((__int64 (__fastcall *)(LPBC, __int128 *))ppbc->lpVtbl->SetBindOptions)(ppbc, &v14);
    if ( v7 >= 0 )
    {
      v7 = ((__int64 (__fastcall *)(struct IMoniker *, LPBC, _QWORD, GUID *, __int64 *))a2->lpVtbl->BindToStorage)(
             a2,
             ppbc,
             0,
             &IID_IStream,
             &v12);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v12 + 96LL))(v12, v15, 1);
        if ( v7 >= 0 )
        {
          if ( v17 || (v8 = len, v9 = SysAllocStringByteLen(0, len), (v6 = (char *)v9) == 0) )
          {
            v7 = -2147024882;
          }
          else
          {
            v10 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD, _QWORD))(*(_QWORD *)v12 + 24LL))(v12, v9, v8, 0);
            v7 = v10;
            if ( v10 >= 0 )
            {
              if ( v10 )
                v7 = -2147467259;
              else
                v7 = ConvertTextToUnicode(*((_DWORD *)this + 15), v6, v8, a3);
            }
          }
        }
      }
    }
  }
  SysFreeString((BSTR)v6);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( ppbc )
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140007c14  mov     [rsp-8+arg_18], rbx
0x140007c19  push    rbp
0x140007c1a  push    rsi
0x140007c1b  push    rdi
0x140007c1c  push    r14
0x140007c1e  push    r15
0x140007c20  lea     rbp, [rsp-37h]
0x140007c25  sub     rsp, 0B0h
0x140007c2c  mov     rax, cs:__security_cookie
0x140007c33  xor     rax, rsp
0x140007c36  mov     [rbp+57h+var_30], rax
0x140007c3a  mov     rsi, rdx
0x140007c3d  mov     [rbp+57h+ppbc], 0
0x140007c45  xor     edx, edx; Val
0x140007c47  mov     [rbp+57h+var_A0], 0
0x140007c4f  mov     r15, r8
0x140007c52  mov     r14, rcx
0x140007c55  lea     rcx, [rbp+57h+var_80]; void *
0x140007c59  lea     r8d, [rdx+50h]; Size
0x140007c5d  call    memset_0
0x140007c62  xorps   xmm0, xmm0
0x140007c65  lea     rdx, [rbp+57h+ppbc]; ppbc
0x140007c69  xor     ecx, ecx; reserved
0x140007c6b  xor     edi, edi
0x140007c6d  movups  [rbp+57h+var_90], xmm0
0x140007c71  call    cs:__imp_CreateBindCtx
0x140007c77  mov     ebx, eax
0x140007c79  test    eax, eax
0x140007c7b  js      loc_140007D52
0x140007c81  mov     rcx, [rbp+57h+ppbc]
0x140007c85  lea     rdx, [rbp+57h+var_90]
0x140007c89  mov     qword ptr [rbp+57h+var_90], 10h
0x140007c91  mov     qword ptr [rbp+57h+var_90+8], rdi
0x140007c95  mov     rax, [rcx]
0x140007c98  mov     rax, [rax+30h]
0x140007c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007ca1  mov     ebx, eax
0x140007ca3  test    eax, eax
0x140007ca5  js      loc_140007D52
0x140007cab  mov     rax, [rsi]
0x140007cae  lea     rcx, [rbp+57h+var_A0]
0x140007cb2  mov     rdx, [rbp+57h+ppbc]
0x140007cb6  lea     r9, IID_IStream
0x140007cbd  mov     [rsp+0D0h+var_B0], rcx
0x140007cc2  xor     r8d, r8d
0x140007cc5  mov     rcx, rsi
0x140007cc8  mov     rax, [rax+48h]
0x140007ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007cd1  mov     ebx, eax
0x140007cd3  test    eax, eax
0x140007cd5  js      short loc_140007D52
0x140007cd7  mov     rcx, [rbp+57h+var_A0]
0x140007cdb  lea     r8d, [rdi+1]
0x140007cdf  lea     rdx, [rbp+57h+var_80]
0x140007ce3  mov     rax, [rcx]
0x140007ce6  mov     rax, [rax+60h]
0x140007cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007cef  mov     ebx, eax
0x140007cf1  test    eax, eax
0x140007cf3  js      short loc_140007D52
0x140007cf5  cmp     [rbp+57h+var_6C], edi
0x140007cf8  jz      short loc_140007D01
0x140007cfa  mov     ebx, 8007000Eh
0x140007cff  jmp     short loc_140007D52
0x140007d01  mov     esi, [rbp+57h+len]
0x140007d04  xor     ecx, ecx; psz
0x140007d06  mov     edx, esi; len
0x140007d08  call    cs:__imp_SysAllocStringByteLen
0x140007d0e  mov     rdi, rax
0x140007d11  test    rax, rax
0x140007d14  jz      short loc_140007CFA
0x140007d16  mov     rcx, [rbp+57h+var_A0]
0x140007d1a  xor     r9d, r9d
0x140007d1d  mov     r8d, esi
0x140007d20  mov     rdx, rdi
0x140007d23  mov     rax, [rcx]
0x140007d26  mov     rax, [rax+18h]
0x140007d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007d2f  mov     ebx, eax
0x140007d31  test    eax, eax
0x140007d33  js      short loc_140007D52
0x140007d35  jz      short loc_140007D3E
0x140007d37  mov     ebx, 80004005h
0x140007d3c  jmp     short loc_140007D52
0x140007d3e  mov     ecx, [r14+3Ch]; CodePage
0x140007d42  mov     r9, r15
0x140007d45  mov     r8d, esi; cbMultiByte
0x140007d48  mov     rdx, rdi; Src
0x140007d4b  call    ConvertTextToUnicode
0x140007d50  mov     ebx, eax
0x140007d52  mov     rcx, rdi; bstrString
0x140007d55  call    cs:__imp_SysFreeString
0x140007d5b  mov     rcx, [rbp+57h+var_A0]
0x140007d5f  test    rcx, rcx
0x140007d62  jz      short loc_140007D70
0x140007d64  mov     rax, [rcx]
0x140007d67  mov     rax, [rax+10h]
0x140007d6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007d70  mov     rcx, [rbp+57h+ppbc]
0x140007d74  test    rcx, rcx
0x140007d77  jz      short loc_140007D85
0x140007d79  mov     rax, [rcx]
0x140007d7c  mov     rax, [rax+10h]
0x140007d80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007d85  mov     eax, ebx
0x140007d87  mov     rcx, [rbp+57h+var_30]
0x140007d8b  xor     rcx, rsp; StackCookie
0x140007d8e  call    __security_check_cookie
0x140007d93  mov     rbx, [rsp+0D0h+arg_18]
0x140007d9b  add     rsp, 0B0h
0x140007da2  pop     r15
0x140007da4  pop     r14
0x140007da6  pop     rdi
0x140007da7  pop     rsi
0x140007da8  pop     rbp
0x140007da9  retn
```
