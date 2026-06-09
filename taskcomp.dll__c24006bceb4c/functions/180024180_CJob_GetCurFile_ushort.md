# CJob::GetCurFile(ushort * *)

- ea: `0x180024180`
- end: `0x18002424f`
- name: `?GetCurFile@CJob@@UEAAJPEAPEAG@Z`
- size: `207`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003ef0`
- `0x180024180`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800241ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800241ff`

## pseudocode

```c
__int64 __fastcall CJob::GetCurFile(CJob *this, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rbx
  unsigned int v4; // edi
  __int64 v5; // rax
  unsigned __int64 v6; // r14
  unsigned __int16 *v7; // rax
  __int64 result; // rax
  unsigned __int16 *v9; // r10
  unsigned __int16 v10[8]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v11; // [rsp+30h] [rbp-38h]

  v2 = (unsigned __int16 *)*((_QWORD *)this + 18);
  *(_OWORD *)v10 = 0;
  v11 = 0;
  if ( v2 && *v2 )
  {
    v4 = 0;
  }
  else
  {
    StringCchCopyW(v10, 0x10u, L"*.job");
    v2 = v10;
    v4 = 1;
  }
  v5 = -1;
  do
    ++v5;
  while ( v2[v5] );
  v6 = (int)v5 + 1LL;
  v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v6);
  if ( v7 )
  {
    *v7 = 0;
    StringCchCopyW(v7, v6, v2);
    result = v4;
    *a2 = v9;
  }
  else
  {
    *a2 = 0;
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180024180  mov     [rsp+arg_10], rbx
0x180024185  mov     [rsp+arg_18], rbp
0x18002418a  push    rsi
0x18002418b  push    rdi
0x18002418c  push    r14
0x18002418e  sub     rsp, 50h
0x180024192  mov     rax, cs:__security_cookie
0x180024199  xor     rax, rsp
0x18002419c  mov     [rsp+68h+var_28], rax
0x1800241a1  mov     rbx, [rcx+90h]
0x1800241a8  xorps   xmm0, xmm0
0x1800241ab  xor     ebp, ebp
0x1800241ad  mov     rsi, rdx
0x1800241b0  movups  xmmword ptr [rsp+68h+var_48], xmm0
0x1800241b5  movups  [rsp+68h+var_38], xmm0
0x1800241ba  test    rbx, rbx
0x1800241bd  jz      short loc_1800241C8
0x1800241bf  cmp     [rbx], bp
0x1800241c2  jz      short loc_1800241C8
0x1800241c4  mov     edi, ebp
0x1800241c6  jmp     short loc_1800241E8
0x1800241c8  lea     r8, aJob_2; "*.job"
0x1800241cf  mov     edx, 10h; unsigned __int64
0x1800241d4  lea     rcx, [rsp+68h+var_48]; unsigned __int16 *
0x1800241d9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800241de  lea     rbx, [rsp+68h+var_48]
0x1800241e3  mov     edi, 1
0x1800241e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800241ec  inc     rax
0x1800241ef  cmp     [rbx+rax*2], bp
0x1800241f3  jnz     short loc_1800241EC
0x1800241f5  movsxd  r14, eax
0x1800241f8  inc     r14
0x1800241fb  lea     rcx, [r14+r14]; cb
0x1800241ff  call    cs:__imp_CoTaskMemAlloc
0x180024205  mov     r10, rax
0x180024208  test    rax, rax
0x18002420b  jnz     short loc_180024217
0x18002420d  mov     [rsi], rbp
0x180024210  mov     eax, 8007000Eh
0x180024215  jmp     short loc_18002422D
0x180024217  mov     r8, rbx; unsigned __int16 *
0x18002421a  mov     [rax], bp
0x18002421d  mov     rdx, r14; unsigned __int64
0x180024220  mov     rcx, r10; unsigned __int16 *
0x180024223  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180024228  mov     eax, edi
0x18002422a  mov     [rsi], r10
0x18002422d  mov     rcx, [rsp+68h+var_28]
0x180024232  xor     rcx, rsp; StackCookie
0x180024235  call    __security_check_cookie
0x18002423a  lea     r11, [rsp+68h+var_18]
0x18002423f  mov     rbx, [r11+30h]
0x180024243  mov     rbp, [r11+38h]
0x180024247  mov     rsp, r11
0x18002424a  pop     r14
0x18002424c  pop     rdi
0x18002424d  pop     rsi
0x18002424e  retn
```
