# ConvertStringArrayToCommaDelimitedString(ushort * *,ulong)

- ea: `0x18000a72c`
- end: `0x18000a818`
- name: `?ConvertStringArrayToCommaDelimitedString@@YAPEAGPEAPEAGK@Z`
- size: `236`
- prototype: `unsigned __int16 *__fastcall(unsigned __int16 **, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ad88`

## callees

- `0x18000262c`
- `0x1800026c0`
- `0x1800098f8`
- `0x18000a4ec`
- `0x18000a72c`
- `0x18000ba60`

## pseudocode

```c
unsigned __int16 *__fastcall ConvertStringArrayToCommaDelimitedString(unsigned __int16 **a1, int a2)
{
  __int64 v3; // rbx
  unsigned int v4; // esi
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // rbx
  const unsigned __int16 *v7; // r8
  unsigned __int16 *Src[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v10; // [rsp+30h] [rbp-28h]
  unsigned __int64 v11; // [rsp+38h] [rbp-20h]

  if ( !a1 || !a2 )
    return 0;
  v11 = 7;
  v10 = 0;
  LOWORD(Src[0]) = 0;
  v3 = 0;
  v4 = a2 - 1;
  if ( a2 != 1 )
  {
    do
    {
      std::wstring::operator+=(Src, a1[v3]);
      std::wstring::operator+=(Src, L",");
      v3 = (unsigned int)(v3 + 1);
    }
    while ( (unsigned int)v3 < v4 );
  }
  std::wstring::operator+=(Src, a1[v3]);
  v5 = (unsigned __int16 *)operator new(saturated_mul(v10 + 1, 2u));
  v6 = v5;
  v7 = (const unsigned __int16 *)Src;
  if ( v11 >= 8 )
    v7 = Src[0];
  StringCchCopyW(v5, v10 + 1, v7);
  if ( v11 >= 8 )
    operator delete(Src[0]);
  return v6;
}

```

## disassembly

```asm
0x18000a72c  push    rbp
0x18000a72e  push    rbx
0x18000a72f  push    rsi
0x18000a730  push    rdi
0x18000a731  mov     rbp, rsp
0x18000a734  sub     rsp, 58h
0x18000a738  mov     rax, cs:__security_cookie
0x18000a73f  xor     rax, rsp
0x18000a742  mov     [rbp+var_18], rax
0x18000a746  mov     rdi, rcx
0x18000a749  test    rcx, rcx
0x18000a74c  jz      loc_18000A801
0x18000a752  test    edx, edx
0x18000a754  jz      loc_18000A801
0x18000a75a  mov     [rbp+var_20], 7
0x18000a762  mov     [rbp+var_28], 0
0x18000a76a  xor     eax, eax
0x18000a76c  mov     word ptr [rbp+Src], ax
0x18000a770  xor     ebx, ebx
0x18000a772  lea     esi, [rdx-1]
0x18000a775  test    esi, esi
0x18000a777  jz      short loc_18000A79C
0x18000a779  mov     rdx, [rdi+rbx*8]; void *
0x18000a77d  lea     rcx, [rbp+Src]; Src
0x18000a781  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x18000a786  lea     rdx, asc_180010C2C; ","
0x18000a78d  lea     rcx, [rbp+Src]; Src
0x18000a791  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x18000a796  inc     ebx
0x18000a798  cmp     ebx, esi
0x18000a79a  jb      short loc_18000A779
0x18000a79c  mov     rdx, [rdi+rbx*8]; void *
0x18000a7a0  lea     rcx, [rbp+Src]; Src
0x18000a7a4  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x18000a7a9  mov     rcx, [rbp+var_28]
0x18000a7ad  inc     rcx
0x18000a7b0  mov     eax, 2
0x18000a7b5  mul     rcx
0x18000a7b8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000a7bf  cmovb   rax, rcx
0x18000a7c3  mov     rcx, rax; dwBytes
0x18000a7c6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a7cb  mov     rbx, rax
0x18000a7ce  lea     r8, [rbp+Src]
0x18000a7d2  cmp     [rbp+var_20], 8
0x18000a7d7  cmovnb  r8, [rbp+Src]; unsigned __int16 *
0x18000a7dc  mov     rdx, [rbp+var_28]
0x18000a7e0  inc     rdx; unsigned __int64
0x18000a7e3  mov     rcx, rax; unsigned __int16 *
0x18000a7e6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a7eb  nop
0x18000a7ec  cmp     [rbp+var_20], 8
0x18000a7f1  jb      short loc_18000A7FC
0x18000a7f3  mov     rcx, [rbp+Src]; void *
0x18000a7f7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a7fc  mov     rax, rbx
0x18000a7ff  jmp     short loc_18000A803
0x18000a801  xor     eax, eax
0x18000a803  mov     rcx, [rbp+var_18]
0x18000a807  xor     rcx, rsp; StackCookie
0x18000a80a  call    __security_check_cookie
0x18000a80f  add     rsp, 58h
0x18000a813  pop     rdi
0x18000a814  pop     rsi
0x18000a815  pop     rbx
0x18000a816  pop     rbp
0x18000a817  retn
```
