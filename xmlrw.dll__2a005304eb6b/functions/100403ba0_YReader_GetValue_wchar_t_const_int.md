# YReader::GetValue(wchar_t const * *,int *)

- ea: `0x100403ba0`
- end: `0x100403c9b`
- name: `?GetValue@YReader@@UEAAJPEAPEB_WPEAH@Z`
- size: `251`
- prototype: `__int64 __fastcall(YReader *__hidden this, const wchar_t **, int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x100402d90`
- `0x100403ba0`
- `0x100404670`
- `0x100404a40`
- `0x100404c10`
- `0x100408580`
- `0x10040b880`
- `0x100415430`
- `0x100423dd0`

## pseudocode

```c
__int64 __fastcall YReader::GetValue(void **this, const wchar_t **a2, int *a3)
{
  int v6; // ecx
  __int64 result; // rax

  if ( *((_BYTE *)this + 1761) )
  {
    BlockAlloc::PopScope((BlockAlloc *)(this + 48), this[226]);
    switch ( *((_DWORD *)this + 436) )
    {
      case 4:
        YReader::ParseAttributeValue((YReader *)(this - 4), 1);
        YReader::NormalizeAttributeValue((YReader *)(this - 4), (struct StringPtr *)(this + 200));
        break;
      case 7:
        YReader::ParseCdSect((YReader *)(this - 4));
        break;
      case 9:
        YReader::ParsePiData((YReader *)(this - 4));
        break;
      case 0xA:
        YReader::ParseComment((YReader *)(this - 4));
        break;
    }
  }
  *a2 = (const wchar_t *)this[200];
  *a3 = *((_DWORD *)this + 402);
  v6 = *((_DWORD *)this + 70);
  *((_BYTE *)this + 1761) = v6 > 0;
  result = *((unsigned int *)this + 437);
  if ( (int)result >= 0 )
    return v6 > 0;
  return result;
}

```

## disassembly

```asm
0x100403ba0  mov     [rsp+arg_18], rbx
0x100403ba5  mov     [rsp+arg_10], r8
0x100403baa  mov     [rsp+arg_8], rdx
0x100403baf  mov     [rsp+arg_0], rcx
0x100403bb4  push    rsi
0x100403bb5  push    rdi
0x100403bb6  push    r14
0x100403bb8  sub     rsp, 40h
0x100403bbc  mov     rsi, r8
0x100403bbf  mov     r14, rdx
0x100403bc2  mov     rdi, rcx
0x100403bc5  cmp     byte ptr [rcx+6E1h], 0
0x100403bcc  jz      loc_100403C59
0x100403bd2  add     rcx, 180h; this
0x100403bd9  mov     rdx, [rdi+710h]; void *
0x100403be0  call    ?PopScope@BlockAlloc@@QEAAXPEAX@Z; BlockAlloc::PopScope(void *)
0x100403be5  mov     ecx, [rdi+6D0h]
0x100403beb  sub     ecx, 4
0x100403bee  jz      short loc_100403C20
0x100403bf0  sub     ecx, 3
0x100403bf3  jz      short loc_100403C15
0x100403bf5  sub     ecx, 2
0x100403bf8  jz      short loc_100403C0A
0x100403bfa  cmp     ecx, 1
0x100403bfd  jnz     short loc_100403C3B
0x100403bff  lea     rcx, [rdi-20h]; this
0x100403c03  call    ?ParseComment@YReader@@AEAAXXZ; YReader::ParseComment(void)
0x100403c08  jmp     short loc_100403C3B
0x100403c0a  lea     rcx, [rdi-20h]; this
0x100403c0e  call    ?ParsePiData@YReader@@AEAAXXZ; YReader::ParsePiData(void)
0x100403c13  jmp     short loc_100403C3B
0x100403c15  lea     rcx, [rdi-20h]; this
0x100403c19  call    ?ParseCdSect@YReader@@AEAAXXZ; YReader::ParseCdSect(void)
0x100403c1e  jmp     short loc_100403C3B
0x100403c20  mov     dl, 1; bool
0x100403c22  lea     rcx, [rdi-20h]; this
0x100403c26  call    ?ParseAttributeValue@YReader@@AEAAX_N@Z; YReader::ParseAttributeValue(bool)
0x100403c2b  lea     rdx, [rdi+640h]; struct StringPtr *
0x100403c32  lea     rcx, [rdi-20h]; this
0x100403c36  call    ?NormalizeAttributeValue@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::NormalizeAttributeValue(StringPtr *)
0x100403c3b  jmp     short loc_100403C59
0x100403c3d  mov     rdi, [rsp+58h+arg_0]
0x100403c42  lea     rcx, [rdi-20h]; this
0x100403c46  mov     edx, [rsp+58h+var_38]; int
0x100403c4a  call    ?HandleException@YReader@@AEAAXJ@Z; YReader::HandleException(long)
0x100403c4f  mov     rsi, [rsp+58h+arg_10]
0x100403c54  mov     r14, [rsp+58h+arg_8]
0x100403c59  mov     rax, [rdi+640h]
0x100403c60  mov     [r14], rax
0x100403c63  mov     eax, [rdi+648h]
0x100403c69  mov     [rsi], eax
0x100403c6b  mov     ecx, [rdi+118h]
0x100403c71  test    ecx, ecx
0x100403c73  setnle  al
0x100403c76  mov     [rdi+6E1h], al
0x100403c7c  mov     eax, [rdi+6D4h]
0x100403c82  test    eax, eax
0x100403c84  js      short loc_100403C8D
0x100403c86  xor     eax, eax
0x100403c88  test    ecx, ecx
0x100403c8a  setnle  al
0x100403c8d  mov     rbx, [rsp+58h+arg_18]
0x100403c92  add     rsp, 40h
0x100403c96  pop     r14
0x100403c98  pop     rdi
0x100403c99  pop     rsi
0x100403c9a  retn
0x100439f20  push    rbp
0x100439f22  sub     rsp, 20h
0x100439f26  mov     rbp, rdx
0x100439f29  mov     [rbp+38h], rcx
0x100439f2d  mov     [rbp+30h], rcx
0x100439f31  mov     rax, [rbp+30h]
0x100439f35  mov     rcx, [rax]
0x100439f38  mov     [rbp+28h], rcx
0x100439f3c  mov     rax, [rbp+28h]
0x100439f40  mov     eax, [rax]
0x100439f42  cmp     eax, 0C0000005h
0x100439f47  jz      short loc_100439F79
0x100439f49  add     eax, 1FFFFFFFh
0x100439f4e  cmp     eax, 1
0x100439f51  ja      short loc_100439F69
0x100439f53  mov     rax, [rbp+28h]
0x100439f57  cmp     dword ptr [rax+18h], 1
0x100439f5b  jnz     short loc_100439F69
0x100439f5d  mov     rax, [rbp+28h]
0x100439f61  mov     ecx, [rax+20h]
0x100439f64  mov     [rbp+20h], ecx
0x100439f67  jmp     short loc_100439F70
0x100439f69  mov     dword ptr [rbp+20h], 8000FFFFh
0x100439f70  mov     dword ptr [rbp+24h], 1
0x100439f77  jmp     short loc_100439F80
0x100439f79  mov     dword ptr [rbp+24h], 0
0x100439f80  mov     eax, [rbp+24h]
0x100439f83  add     rsp, 20h
0x100439f87  pop     rbp
0x100439f88  retn
```
