# EncodePropertyToString(IPubProperty *,STRU *)

- ea: `0x180002c84`
- end: `0x180002de8`
- name: `?EncodePropertyToString@@YAJPEAVIPubProperty@@PEAVSTRU@@@Z`
- size: `356`
- prototype: `__int64 __fastcall(struct IPubProperty *, struct STRU *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180001a04`
- `0x180002520`

## callees

- `0x180002c20`
- `0x180002c84`
- `0x180003490`
- `0x180004010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180002cb0`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002cba`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002cc4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002cb0`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002cba`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002cc4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002dad`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002db7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002dc1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002dad`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002db7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002dc1`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002d52`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002d7b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002d52`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002d7b`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180002d3c`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180002d3c`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180002d65`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180002d8e`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180002d65`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180002d8e`

## pseudocode

```c
__int64 __fastcall EncodePropertyToString(struct IPubProperty *a1, struct STRU *a2)
{
  const unsigned __int16 *v4; // rax
  int v5; // ebx
  const unsigned __int16 *v6; // rax
  const unsigned __int16 *v7; // rax
  _BYTE v9[56]; // [rsp+20h] [rbp-69h] BYREF
  _BYTE v10[56]; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v11[56]; // [rsp+90h] [rbp+7h] BYREF

  STRU::STRU((STRU *)v11);
  STRU::STRU((STRU *)v10);
  STRU::STRU((STRU *)v9);
  v4 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IPubProperty *))(*(_QWORD *)a1 + 8LL))(a1);
  v5 = EncodeOneField(v4, (struct STRU *)v11);
  if ( v5 >= 0 )
  {
    v6 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IPubProperty *))(*(_QWORD *)a1 + 16LL))(a1);
    v5 = EncodeOneField(v6, (struct STRU *)v10);
    if ( v5 >= 0 )
    {
      v7 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IPubProperty *))(*(_QWORD *)a1 + 24LL))(a1);
      v5 = EncodeOneField(v7, (struct STRU *)v9);
      if ( v5 >= 0 )
      {
        v5 = STRU::Copy(a2, (const struct STRU *)v11);
        if ( v5 >= 0 )
        {
          v5 = STRU::Append(a2, L"!");
          if ( v5 >= 0 )
          {
            v5 = STRU::Append(a2, (const struct STRU *)v10);
            if ( v5 >= 0 )
            {
              v5 = STRU::Append(a2, L"!");
              if ( v5 >= 0 )
              {
                v5 = STRU::Append(a2, (const struct STRU *)v9);
                if ( v5 >= 0 && *((_DWORD *)a2 + 12) >= 0x7FBCu )
                  v5 = -2147024888;
              }
            }
          }
        }
      }
    }
  }
  STRU::~STRU((STRU *)v9);
  STRU::~STRU((STRU *)v10);
  STRU::~STRU((STRU *)v11);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180002c84  mov     [rsp-8+arg_10], rbx
0x180002c89  push    rbp
0x180002c8a  push    rsi
0x180002c8b  push    rdi
0x180002c8c  lea     rbp, [rsp-47h]
0x180002c91  sub     rsp, 0D0h
0x180002c98  mov     rax, cs:__security_cookie
0x180002c9f  xor     rax, rsp
0x180002ca2  mov     [rbp+57h+var_18], rax
0x180002ca6  mov     rsi, rcx
0x180002ca9  mov     rdi, rdx
0x180002cac  lea     rcx, [rbp+57h+var_50]
0x180002cb0  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002cb6  lea     rcx, [rbp+57h+var_88]
0x180002cba  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002cc0  lea     rcx, [rbp+57h+var_C0]
0x180002cc4  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002cca  mov     rax, [rsi]
0x180002ccd  mov     rcx, rsi
0x180002cd0  mov     rax, [rax+8]
0x180002cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cd9  mov     rcx, rax; unsigned __int16 *
0x180002cdc  lea     rdx, [rbp+57h+var_50]; struct STRU *
0x180002ce0  call    ?EncodeOneField@@YAJPEBGPEAVSTRU@@@Z; EncodeOneField(ushort const *,STRU *)
0x180002ce5  mov     ebx, eax
0x180002ce7  test    eax, eax
0x180002ce9  js      loc_180002DA9
0x180002cef  mov     rax, [rsi]
0x180002cf2  mov     rcx, rsi
0x180002cf5  mov     rax, [rax+10h]
0x180002cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cfe  mov     rcx, rax; unsigned __int16 *
0x180002d01  lea     rdx, [rbp+57h+var_88]; struct STRU *
0x180002d05  call    ?EncodeOneField@@YAJPEBGPEAVSTRU@@@Z; EncodeOneField(ushort const *,STRU *)
0x180002d0a  mov     ebx, eax
0x180002d0c  test    eax, eax
0x180002d0e  js      loc_180002DA9
0x180002d14  mov     rax, [rsi]
0x180002d17  mov     rcx, rsi
0x180002d1a  mov     rax, [rax+18h]
0x180002d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d23  mov     rcx, rax; unsigned __int16 *
0x180002d26  lea     rdx, [rbp+57h+var_C0]; struct STRU *
0x180002d2a  call    ?EncodeOneField@@YAJPEBGPEAVSTRU@@@Z; EncodeOneField(ushort const *,STRU *)
0x180002d2f  mov     ebx, eax
0x180002d31  test    eax, eax
0x180002d33  js      short loc_180002DA9
0x180002d35  lea     rdx, [rbp+57h+var_50]
0x180002d39  mov     rcx, rdi
0x180002d3c  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180002d42  mov     ebx, eax
0x180002d44  test    eax, eax
0x180002d46  js      short loc_180002DA9
0x180002d48  lea     rdx, asc_18000558C; "!"
0x180002d4f  mov     rcx, rdi
0x180002d52  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002d58  mov     ebx, eax
0x180002d5a  test    eax, eax
0x180002d5c  js      short loc_180002DA9
0x180002d5e  lea     rdx, [rbp+57h+var_88]
0x180002d62  mov     rcx, rdi
0x180002d65  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x180002d6b  mov     ebx, eax
0x180002d6d  test    eax, eax
0x180002d6f  js      short loc_180002DA9
0x180002d71  lea     rdx, asc_18000558C; "!"
0x180002d78  mov     rcx, rdi
0x180002d7b  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002d81  mov     ebx, eax
0x180002d83  test    eax, eax
0x180002d85  js      short loc_180002DA9
0x180002d87  lea     rdx, [rbp+57h+var_C0]
0x180002d8b  mov     rcx, rdi
0x180002d8e  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x180002d94  mov     ebx, eax
0x180002d96  test    eax, eax
0x180002d98  js      short loc_180002DA9
0x180002d9a  cmp     dword ptr [rdi+30h], 7FBCh
0x180002da1  mov     eax, 80070008h
0x180002da6  cmovnb  ebx, eax
0x180002da9  lea     rcx, [rbp+57h+var_C0]
0x180002dad  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002db3  lea     rcx, [rbp+57h+var_88]
0x180002db7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002dbd  lea     rcx, [rbp+57h+var_50]
0x180002dc1  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002dc7  mov     eax, ebx
0x180002dc9  mov     rcx, [rbp+57h+var_18]
0x180002dcd  xor     rcx, rsp; StackCookie
0x180002dd0  call    __security_check_cookie
0x180002dd5  mov     rbx, [rsp+0E0h+arg_10]
0x180002ddd  add     rsp, 0D0h
0x180002de4  pop     rdi
0x180002de5  pop     rsi
0x180002de6  pop     rbp
0x180002de7  retn
```
