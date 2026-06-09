# LOG_WRITER::AppendTime(STRU *,_SYSTEMTIME *,ushort const *)

- ea: `0x180002f48`
- end: `0x18000306f`
- name: `?AppendTime@LOG_WRITER@@AEAAJPEAVSTRU@@PEAU_SYSTEMTIME@@PEBG@Z`
- size: `295`
- prototype: `int __fastcall(LOG_WRITER *this, struct STRU *, struct _SYSTEMTIME *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180003718`
- `0x180005f04`

## callees

- `0x180002b14`
- `0x180002f48`
- `0x18000e9a0`

## import_xrefs

- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002f8d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002fe5`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180003028`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002f8d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002fe5`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180003028`

## pseudocode

```c
int __fastcall LOG_WRITER::AppendTime(
        LOG_WRITER *this,
        struct STRU *a2,
        struct _SYSTEMTIME *a3,
        const unsigned __int16 *a4)
{
  bool v4; // cf
  int result; // eax
  LOG_WRITER *v9; // rcx
  LOG_WRITER *v10; // rcx
  unsigned __int16 v11[8]; // [rsp+40h] [rbp-48h] BYREF
  __int16 v12; // [rsp+50h] [rbp-38h]

  v4 = a3->wHour < 0xAu;
  v12 = 0;
  *(_OWORD *)v11 = 0;
  if ( !v4 || (result = STRU::Append(a2, L"0"), result >= 0) )
  {
    result = LOG_WRITER::AppendNum(this, a2, a3->wHour, v11, 9u, L":", 0);
    if ( result >= 0 )
    {
      if ( a3->wMinute >= 0xAu || (result = STRU::Append(a2, L"0"), result >= 0) )
      {
        result = LOG_WRITER::AppendNum(v9, a2, a3->wMinute, v11, 9u, L":", 0);
        if ( result >= 0 )
        {
          if ( a3->wSecond >= 0xAu )
            return LOG_WRITER::AppendNum(v10, a2, a3->wSecond, v11, 9u, a4, 0);
          result = STRU::Append(a2, L"0");
          if ( result >= 0 )
            return LOG_WRITER::AppendNum(v10, a2, a3->wSecond, v11, 9u, a4, 0);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002f48  push    rbx
0x180002f4a  push    rsi
0x180002f4b  push    rdi
0x180002f4c  push    r12
0x180002f4e  push    r15
0x180002f50  sub     rsp, 60h
0x180002f54  mov     rax, cs:__security_cookie
0x180002f5b  xor     rax, rsp
0x180002f5e  mov     [rsp+88h+var_30], rax
0x180002f63  xor     eax, eax
0x180002f65  xorps   xmm0, xmm0
0x180002f68  cmp     word ptr [r8+8], 0Ah
0x180002f6e  mov     rsi, r9
0x180002f71  mov     rdi, r8
0x180002f74  mov     [rsp+88h+var_38], ax
0x180002f79  mov     rbx, rdx
0x180002f7c  movups  xmmword ptr [rsp+88h+var_48], xmm0
0x180002f81  jnb     short loc_180002F9B
0x180002f83  lea     rdx, a0; "0"
0x180002f8a  mov     rcx, rbx
0x180002f8d  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002f93  test    eax, eax
0x180002f95  js      loc_180003056
0x180002f9b  movzx   r8d, word ptr [rdi+8]; unsigned __int64
0x180002fa0  lea     r12, asc_18001213C; ":"
0x180002fa7  mov     [rsp+88h+var_58], 0; int
0x180002faf  lea     r9, [rsp+88h+var_48]; unsigned __int16 *
0x180002fb4  mov     r15d, 9
0x180002fba  mov     [rsp+88h+var_60], r12; unsigned __int16 *
0x180002fbf  mov     rdx, rbx; struct STRU *
0x180002fc2  mov     [rsp+88h+var_68], r15; unsigned __int64
0x180002fc7  call    ?AppendNum@LOG_WRITER@@AEAAJPEAVSTRU@@_KPEAG1PEBGH@Z; LOG_WRITER::AppendNum(STRU *,unsigned __int64,ushort *,unsigned __int64,ushort const *,int)
0x180002fcc  test    eax, eax
0x180002fce  js      loc_180003056
0x180002fd4  cmp     word ptr [rdi+0Ah], 0Ah
0x180002fd9  jnb     short loc_180002FEF
0x180002fdb  lea     rdx, a0; "0"
0x180002fe2  mov     rcx, rbx
0x180002fe5  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002feb  test    eax, eax
0x180002fed  js      short loc_180003056
0x180002fef  movzx   r8d, word ptr [rdi+0Ah]; unsigned __int64
0x180002ff4  lea     r9, [rsp+88h+var_48]; unsigned __int16 *
0x180002ff9  mov     [rsp+88h+var_58], 0; int
0x180003001  mov     rdx, rbx; struct STRU *
0x180003004  mov     [rsp+88h+var_60], r12; unsigned __int16 *
0x180003009  mov     [rsp+88h+var_68], r15; unsigned __int64
0x18000300e  call    ?AppendNum@LOG_WRITER@@AEAAJPEAVSTRU@@_KPEAG1PEBGH@Z; LOG_WRITER::AppendNum(STRU *,unsigned __int64,ushort *,unsigned __int64,ushort const *,int)
0x180003013  test    eax, eax
0x180003015  js      short loc_180003056
0x180003017  cmp     word ptr [rdi+0Ch], 0Ah
0x18000301c  jnb     short loc_180003032
0x18000301e  lea     rdx, a0; "0"
0x180003025  mov     rcx, rbx
0x180003028  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000302e  test    eax, eax
0x180003030  js      short loc_180003056
0x180003032  movzx   r8d, word ptr [rdi+0Ch]; unsigned __int64
0x180003037  lea     r9, [rsp+88h+var_48]; unsigned __int16 *
0x18000303c  mov     [rsp+88h+var_58], 0; int
0x180003044  mov     rdx, rbx; struct STRU *
0x180003047  mov     [rsp+88h+var_60], rsi; unsigned __int16 *
0x18000304c  mov     [rsp+88h+var_68], r15; unsigned __int64
0x180003051  call    ?AppendNum@LOG_WRITER@@AEAAJPEAVSTRU@@_KPEAG1PEBGH@Z; LOG_WRITER::AppendNum(STRU *,unsigned __int64,ushort *,unsigned __int64,ushort const *,int)
0x180003056  mov     rcx, [rsp+88h+var_30]
0x18000305b  xor     rcx, rsp; StackCookie
0x18000305e  call    __security_check_cookie
0x180003063  add     rsp, 60h
0x180003067  pop     r15
0x180003069  pop     r12
0x18000306b  pop     rdi
0x18000306c  pop     rsi
0x18000306d  pop     rbx
0x18000306e  retn
```
