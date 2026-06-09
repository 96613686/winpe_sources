# EncodeIniKeyName(ushort const *,ushort const *,STRU *)

- ea: `0x180002b34`
- end: `0x180002c1a`
- name: `?EncodeIniKeyName@@YAJPEBG0PEAVSTRU@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct STRU *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180001a04`
- `0x180002220`
- `0x180003340`

## callees

- `0x180002b34`
- `0x180002f0c`
- `0x180003490`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180002b5f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002b6a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002b5f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002b6a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002bec`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002bf7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002bec`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002bf7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002bb9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002bb9`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180002ba3`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180002ba3`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180002bcd`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180002bcd`

## pseudocode

```c
__int64 __fastcall EncodeIniKeyName(const unsigned __int16 *a1, const unsigned __int16 *a2, struct STRU *a3)
{
  int v6; // ebx
  _BYTE v8[56]; // [rsp+20h] [rbp-98h] BYREF
  _BYTE v9[56]; // [rsp+58h] [rbp-60h] BYREF

  STRU::STRU((STRU *)v9);
  STRU::STRU((STRU *)v8);
  v6 = HexEncodeString(a1, (struct STRU *)v9);
  if ( v6 >= 0 )
  {
    if ( !a2 || (v6 = HexEncodeString(a2, (struct STRU *)v8), v6 >= 0) )
    {
      v6 = STRU::Copy(a3, (const struct STRU *)v9);
      if ( v6 >= 0 )
      {
        v6 = STRU::Append(a3, L".");
        if ( v6 >= 0 )
        {
          v6 = STRU::Append(a3, (const struct STRU *)v8);
          if ( v6 >= 0 && *((_DWORD *)a3 + 12) >= 0x7FBCu )
            v6 = -2147024888;
        }
      }
    }
  }
  STRU::~STRU((STRU *)v8);
  STRU::~STRU((STRU *)v9);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002b34  push    rbx
0x180002b36  push    rsi
0x180002b37  push    rdi
0x180002b38  sub     rsp, 0A0h
0x180002b3f  mov     rax, cs:__security_cookie
0x180002b46  xor     rax, rsp
0x180002b49  mov     [rsp+0B8h+var_28], rax
0x180002b51  mov     rbx, rcx
0x180002b54  mov     rdi, r8
0x180002b57  lea     rcx, [rsp+0B8h+var_60]
0x180002b5c  mov     rsi, rdx
0x180002b5f  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002b65  lea     rcx, [rsp+0B8h+var_98]
0x180002b6a  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002b70  lea     rdx, [rsp+0B8h+var_60]; struct STRU *
0x180002b75  mov     rcx, rbx; unsigned __int16 *
0x180002b78  call    ?HexEncodeString@@YAJPEBGPEAVSTRU@@@Z; HexEncodeString(ushort const *,STRU *)
0x180002b7d  mov     ebx, eax
0x180002b7f  test    eax, eax
0x180002b81  js      short loc_180002BE7
0x180002b83  test    rsi, rsi
0x180002b86  jz      short loc_180002B9B
0x180002b88  lea     rdx, [rsp+0B8h+var_98]; struct STRU *
0x180002b8d  mov     rcx, rsi; unsigned __int16 *
0x180002b90  call    ?HexEncodeString@@YAJPEBGPEAVSTRU@@@Z; HexEncodeString(ushort const *,STRU *)
0x180002b95  mov     ebx, eax
0x180002b97  test    eax, eax
0x180002b99  js      short loc_180002BE7
0x180002b9b  lea     rdx, [rsp+0B8h+var_60]
0x180002ba0  mov     rcx, rdi
0x180002ba3  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180002ba9  mov     ebx, eax
0x180002bab  test    eax, eax
0x180002bad  js      short loc_180002BE7
0x180002baf  lea     rdx, asc_180005588; "."
0x180002bb6  mov     rcx, rdi
0x180002bb9  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002bbf  mov     ebx, eax
0x180002bc1  test    eax, eax
0x180002bc3  js      short loc_180002BE7
0x180002bc5  lea     rdx, [rsp+0B8h+var_98]
0x180002bca  mov     rcx, rdi
0x180002bcd  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x180002bd3  mov     ebx, eax
0x180002bd5  test    eax, eax
0x180002bd7  js      short loc_180002BE7
0x180002bd9  cmp     dword ptr [rdi+30h], 7FBCh
0x180002be0  jb      short loc_180002BE7
0x180002be2  mov     ebx, 80070008h
0x180002be7  lea     rcx, [rsp+0B8h+var_98]
0x180002bec  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002bf2  lea     rcx, [rsp+0B8h+var_60]
0x180002bf7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002bfd  mov     eax, ebx
0x180002bff  mov     rcx, [rsp+0B8h+var_28]
0x180002c07  xor     rcx, rsp; StackCookie
0x180002c0a  call    __security_check_cookie
0x180002c0f  add     rsp, 0A0h
0x180002c16  pop     rdi
0x180002c17  pop     rsi
0x180002c18  pop     rbx
0x180002c19  retn
```
