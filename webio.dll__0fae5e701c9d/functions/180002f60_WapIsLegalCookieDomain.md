# WapIsLegalCookieDomain

- ea: `0x180002f60`
- end: `0x18000308e`
- name: `WapIsLegalCookieDomain`
- size: `302`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003a4c`
- `0x180003fb0`

## callees

- `0x180002f60`
- `0x180004040`
- `0x18000ebd0`

## import_xrefs

- `ntdll!RtlCompareUnicodeStrings` at `0x180003026`
- `ntdll!RtlCompareUnicodeStrings` at `0x180003079`
- `ntdll!RtlCompareUnicodeStrings` at `0x180003026`
- `ntdll!RtlCompareUnicodeStrings` at `0x180003079`

## pseudocode

```c
__int64 __fastcall WapIsLegalCookieDomain(__int64 a1, __int64 a2, _BYTE *a3)
{
  unsigned int v6; // ebx
  int v7; // eax
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rax
  unsigned __int64 v11; // [rsp+30h] [rbp-20h] BYREF
  __int64 v12; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int64 v13; // [rsp+40h] [rbp-10h] BYREF
  __int64 v14; // [rsp+48h] [rbp-8h] BYREF
  unsigned __int64 v15; // [rsp+80h] [rbp+30h] BYREF
  __int64 v16; // [rsp+88h] [rbp+38h] BYREF

  *a3 = 0;
  v12 = 0;
  v16 = 0;
  v11 = 0;
  v15 = 0;
  v14 = 0;
  v13 = 0;
  v6 = WaQueryUriCookieDomainHost(a2, &v12, &v11);
  if ( v6 )
    return v6;
  v6 = WaQueryUriCookieDomainHost(a1, &v16, &v15);
  if ( v6 )
    return v6;
  v7 = *(_DWORD *)(a1 + 64);
  if ( v7 != *(_DWORD *)(a2 + 64) )
    return v6;
  if ( (unsigned int)(v7 - 1) <= 1 )
  {
    if ( (unsigned int)RtlCompareUnicodeStrings(v12, v11, v16, v15, 0) )
      return v6;
LABEL_13:
    *a3 = 1;
    return v6;
  }
  v8 = v11;
  if ( v11 <= v15 )
  {
    v9 = v15 - v11;
    if ( (v15 == v11 || *(_WORD *)(v16 + 2 * v9 - 2) == 46)
      && !(unsigned int)RtlCompareUnicodeStrings(v12, v11, v16 + 2 * v9, v11, 1) )
    {
      v6 = WaDetermineMinimizedDomain(a1, &v14, &v13);
      if ( !v6 && v8 >= v13 )
        goto LABEL_13;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180002f60  mov     [rsp-18h+arg_0], rbx
0x180002f65  mov     [rsp-18h+arg_8], rsi
0x180002f6a  push    rbp
0x180002f6b  push    rdi
0x180002f6c  push    r14
0x180002f6e  mov     rbp, rsp
0x180002f71  sub     rsp, 50h
0x180002f75  mov     rdi, rdx
0x180002f78  mov     byte ptr [r8], 0
0x180002f7c  mov     rsi, r8
0x180002f7f  mov     [rbp+var_18], 0
0x180002f87  mov     r14, rcx
0x180002f8a  mov     [rbp+arg_18], 0
0x180002f92  mov     rcx, rdi
0x180002f95  mov     [rbp+var_20], 0
0x180002f9d  lea     r8, [rbp+var_20]
0x180002fa1  mov     [rbp+arg_10], 0
0x180002fa9  lea     rdx, [rbp+var_18]
0x180002fad  mov     [rbp+var_8], 0
0x180002fb5  mov     [rbp+var_10], 0
0x180002fbd  call    WaQueryUriCookieDomainHost
0x180002fc2  mov     ebx, eax
0x180002fc4  test    eax, eax
0x180002fc6  jnz     loc_180003052
0x180002fcc  lea     r8, [rbp+arg_10]
0x180002fd0  mov     rcx, r14
0x180002fd3  lea     rdx, [rbp+arg_18]
0x180002fd7  call    WaQueryUriCookieDomainHost
0x180002fdc  mov     ebx, eax
0x180002fde  test    eax, eax
0x180002fe0  jnz     short loc_180003052
0x180002fe2  mov     eax, [r14+40h]
0x180002fe6  cmp     eax, [rdi+40h]
0x180002fe9  jnz     short loc_180003052
0x180002feb  mov     r9, [rbp+arg_10]
0x180002fef  dec     eax
0x180002ff1  cmp     eax, 1
0x180002ff4  jbe     short loc_180003068
0x180002ff6  mov     rdi, [rbp+var_20]
0x180002ffa  cmp     rdi, r9
0x180002ffd  ja      short loc_180003052
0x180002fff  mov     rcx, [rbp+arg_18]
0x180003003  mov     rax, r9
0x180003006  sub     rax, rdi
0x180003009  jz      short loc_180003013
0x18000300b  cmp     word ptr [rcx+rax*2-2], 2Eh ; '.'
0x180003011  jnz     short loc_180003052
0x180003013  lea     r8, [rcx+rax*2]
0x180003017  mov     [rsp+50h+var_30], 1
0x18000301c  mov     rcx, [rbp+var_18]
0x180003020  sub     r9, rax
0x180003023  mov     rdx, rdi
0x180003026  call    cs:__imp_RtlCompareUnicodeStrings
0x18000302d  nop     dword ptr [rax+rax+00h]
0x180003032  test    eax, eax
0x180003034  jnz     short loc_180003052
0x180003036  lea     r8, [rbp+var_10]
0x18000303a  mov     rcx, r14
0x18000303d  lea     rdx, [rbp+var_8]
0x180003041  call    WaDetermineMinimizedDomain
0x180003046  mov     ebx, eax
0x180003048  test    eax, eax
0x18000304a  jnz     short loc_180003052
0x18000304c  cmp     rdi, [rbp+var_10]
0x180003050  jnb     short loc_180003089
0x180003052  mov     rsi, [rsp+50h+arg_8]
0x180003057  mov     eax, ebx
0x180003059  mov     rbx, [rsp+50h+arg_0]
0x18000305e  add     rsp, 50h
0x180003062  pop     r14
0x180003064  pop     rdi
0x180003065  pop     rbp
0x180003066  retn
0x180003068  mov     r8, [rbp+arg_18]
0x18000306c  mov     rdx, [rbp+var_20]
0x180003070  mov     rcx, [rbp+var_18]
0x180003074  mov     [rsp+50h+var_30], 0
0x180003079  call    cs:__imp_RtlCompareUnicodeStrings
0x180003080  nop     dword ptr [rax+rax+00h]
0x180003085  test    eax, eax
0x180003087  jnz     short loc_180003052
0x180003089  mov     byte ptr [rsi], 1
0x18000308c  jmp     short loc_180003052
```
