# LOG_WRITER::AppendDate(STRU *,_SYSTEMTIME *)

- ea: `0x180002704`
- end: `0x180002800`
- name: `?AppendDate@LOG_WRITER@@AEAAJPEAVSTRU@@PEAU_SYSTEMTIME@@@Z`
- size: `252`
- prototype: `int __fastcall(LOG_WRITER *this, struct STRU *, struct _SYSTEMTIME *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180003718`
- `0x180005f04`

## callees

- `0x180002704`
- `0x180002b14`
- `0x18000e9a0`

## import_xrefs

- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000276a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800027ad`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000276a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800027ad`

## pseudocode

```c
int __fastcall LOG_WRITER::AppendDate(LOG_WRITER *this, struct STRU *a2, struct _SYSTEMTIME *a3)
{
  int result; // eax
  LOG_WRITER *v6; // rcx
  LOG_WRITER *v7; // rcx
  unsigned __int16 v8[8]; // [rsp+40h] [rbp-38h] BYREF

  result = LOG_WRITER::AppendNum(this, a2, a3->wYear, v8, 5u, L"-", 0);
  if ( result >= 0 )
  {
    if ( a3->wMonth >= 0xAu || (result = STRU::Append(a2, L"0"), result >= 0) )
    {
      result = LOG_WRITER::AppendNum(v6, a2, a3->wMonth, v8, 5u, L"-", 0);
      if ( result >= 0 )
      {
        if ( a3->wDay >= 0xAu )
          return LOG_WRITER::AppendNum(v7, a2, a3->wDay, v8, 5u, L" ", 0);
        result = STRU::Append(a2, L"0");
        if ( result >= 0 )
          return LOG_WRITER::AppendNum(v7, a2, a3->wDay, v8, 5u, L" ", 0);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002704  mov     r11, rsp
0x180002707  mov     [r11+8], rbx
0x18000270b  push    rbp
0x18000270c  push    rdi
0x18000270d  push    r14
0x18000270f  sub     rsp, 60h
0x180002713  mov     rax, cs:__security_cookie
0x18000271a  xor     rax, rsp
0x18000271d  mov     [rsp+78h+var_28], rax
0x180002722  mov     rbx, r8
0x180002725  mov     [rsp+78h+var_48], 0; int
0x18000272d  movzx   r8d, word ptr [r8]; unsigned __int64
0x180002731  lea     r14, asc_18001208C; "-"
0x180002738  mov     [r11-50h], r14
0x18000273c  lea     r9, [r11-38h]; unsigned __int16 *
0x180002740  mov     ebp, 5
0x180002745  mov     rdi, rdx
0x180002748  mov     [r11-58h], rbp
0x18000274c  call    ?AppendNum@LOG_WRITER@@AEAAJPEAVSTRU@@_KPEAG1PEBGH@Z; LOG_WRITER::AppendNum(STRU *,unsigned __int64,ushort *,unsigned __int64,ushort const *,int)
0x180002751  test    eax, eax
0x180002753  js      loc_1800027E2
0x180002759  cmp     word ptr [rbx+2], 0Ah
0x18000275e  jnb     short loc_180002774
0x180002760  lea     rdx, a0; "0"
0x180002767  mov     rcx, rdi
0x18000276a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002770  test    eax, eax
0x180002772  js      short loc_1800027E2
0x180002774  movzx   r8d, word ptr [rbx+2]; unsigned __int64
0x180002779  lea     r9, [rsp+78h+var_38]; unsigned __int16 *
0x18000277e  mov     [rsp+78h+var_48], 0; int
0x180002786  mov     rdx, rdi; struct STRU *
0x180002789  mov     [rsp+78h+var_50], r14; unsigned __int16 *
0x18000278e  mov     [rsp+78h+var_58], rbp; unsigned __int64
0x180002793  call    ?AppendNum@LOG_WRITER@@AEAAJPEAVSTRU@@_KPEAG1PEBGH@Z; LOG_WRITER::AppendNum(STRU *,unsigned __int64,ushort *,unsigned __int64,ushort const *,int)
0x180002798  test    eax, eax
0x18000279a  js      short loc_1800027E2
0x18000279c  cmp     word ptr [rbx+6], 0Ah
0x1800027a1  jnb     short loc_1800027B7
0x1800027a3  lea     rdx, a0; "0"
0x1800027aa  mov     rcx, rdi
0x1800027ad  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800027b3  test    eax, eax
0x1800027b5  js      short loc_1800027E2
0x1800027b7  movzx   r8d, word ptr [rbx+6]; unsigned __int64
0x1800027bc  lea     rax, asc_180012138; " "
0x1800027c3  mov     [rsp+78h+var_48], 0; int
0x1800027cb  lea     r9, [rsp+78h+var_38]; unsigned __int16 *
0x1800027d0  mov     [rsp+78h+var_50], rax; unsigned __int16 *
0x1800027d5  mov     rdx, rdi; struct STRU *
0x1800027d8  mov     [rsp+78h+var_58], rbp; unsigned __int64
0x1800027dd  call    ?AppendNum@LOG_WRITER@@AEAAJPEAVSTRU@@_KPEAG1PEBGH@Z; LOG_WRITER::AppendNum(STRU *,unsigned __int64,ushort *,unsigned __int64,ushort const *,int)
0x1800027e2  mov     rcx, [rsp+78h+var_28]
0x1800027e7  xor     rcx, rsp; StackCookie
0x1800027ea  call    __security_check_cookie
0x1800027ef  mov     rbx, [rsp+78h+arg_0]
0x1800027f7  add     rsp, 60h
0x1800027fb  pop     r14
0x1800027fd  pop     rdi
0x1800027fe  pop     rbp
0x1800027ff  retn
```
