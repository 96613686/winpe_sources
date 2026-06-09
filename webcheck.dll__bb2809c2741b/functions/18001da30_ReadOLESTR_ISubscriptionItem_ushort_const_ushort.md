# ReadOLESTR(ISubscriptionItem *,ushort const *,ushort * *)

- ea: `0x18001da30`
- end: `0x18001dab7`
- name: `?ReadOLESTR@@YAJPEAUISubscriptionItem@@PEBGPEAPEAG@Z`
- size: `135`
- prototype: `__int64 __fastcall(struct ISubscriptionItem *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800048f0`
- `0x18000501c`
- `0x18000cc84`
- `0x1800106d0`
- `0x1800209e0`

## callees

- `0x18001d7c8`
- `0x18001da30`
- `0x180029242`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18001da75`
- `ole32!CoTaskMemAlloc` at `0x18001da75`
- `OLEAUT32!__imp_SysFreeString` at `0x18001da99`
- `OLEAUT32!__imp_SysFreeString` at `0x18001da99`
- `OLEAUT32!__imp_SysStringLen` at `0x18001da66`
- `OLEAUT32!__imp_SysStringLen` at `0x18001da66`

## pseudocode

```c
__int64 __fastcall ReadOLESTR(struct ISubscriptionItem *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  int v4; // eax
  BSTR v5; // rbx
  SIZE_T v6; // rdi
  unsigned __int16 *v7; // rax
  BSTR pbstr; // [rsp+60h] [rbp+18h] BYREF

  *a3 = 0;
  pbstr = 0;
  v4 = ReadBSTR(a1, a2, &pbstr);
  v5 = pbstr;
  if ( v4 >= 0 )
  {
    if ( !pbstr )
      return *a3 == 0 ? 0x80004005 : 0;
    if ( *pbstr )
    {
      v6 = 2LL * (SysStringLen(pbstr) + 1);
      v7 = (unsigned __int16 *)CoTaskMemAlloc(v6);
      *a3 = v7;
      if ( v7 )
        memcpy_0(v7, v5, v6);
    }
  }
  if ( v5 )
    SysFreeString(v5);
  return *a3 == 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x18001da30  push    rbx
0x18001da32  push    rbp
0x18001da33  push    rsi
0x18001da34  push    rdi
0x18001da35  sub     rsp, 28h
0x18001da39  xor     ebp, ebp
0x18001da3b  mov     rsi, r8
0x18001da3e  mov     [r8], rbp
0x18001da41  lea     r8, [rsp+48h+pbstr]; unsigned __int16 **
0x18001da46  mov     [rsp+48h+pbstr], rbp
0x18001da4b  call    ?ReadBSTR@@YAJPEAUISubscriptionItem@@PEBGPEAPEAG@Z; ReadBSTR(ISubscriptionItem *,ushort const *,ushort * *)
0x18001da50  mov     rbx, [rsp+48h+pbstr]
0x18001da55  test    eax, eax
0x18001da57  js      short loc_18001DA91
0x18001da59  test    rbx, rbx
0x18001da5c  jz      short loc_18001DA9F
0x18001da5e  cmp     [rbx], bp
0x18001da61  jz      short loc_18001DA91
0x18001da63  mov     rcx, rbx; pbstr
0x18001da66  call    cs:__imp_SysStringLen
0x18001da6c  lea     edi, [rax+1]
0x18001da6f  add     rdi, rdi
0x18001da72  mov     rcx, rdi; cb
0x18001da75  call    cs:__imp_CoTaskMemAlloc
0x18001da7b  mov     [rsi], rax
0x18001da7e  test    rax, rax
0x18001da81  jz      short loc_18001DA91
0x18001da83  mov     r8, rdi; Size
0x18001da86  mov     rdx, rbx; Src
0x18001da89  mov     rcx, rax; void *
0x18001da8c  call    memcpy_0
0x18001da91  test    rbx, rbx
0x18001da94  jz      short loc_18001DA9F
0x18001da96  mov     rcx, rbx; bstrString
0x18001da99  call    cs:__imp_SysFreeString
0x18001da9f  mov     rax, [rsi]
0x18001daa2  neg     rax
0x18001daa5  sbb     eax, eax
0x18001daa7  not     eax
0x18001daa9  and     eax, 80004005h
0x18001daae  add     rsp, 28h
0x18001dab2  pop     rdi
0x18001dab3  pop     rsi
0x18001dab4  pop     rbp
0x18001dab5  pop     rbx
0x18001dab6  retn
```
