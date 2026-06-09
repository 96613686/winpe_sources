# IsOptInEnabledForHost

- ea: `0x180017054`
- end: `0x180017168`
- name: `IsOptInEnabledForHost`
- size: `276`
- prototype: `__int64 __fastcall(void *Buf1)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800201f4`

## callees

- `0x180017054`
- `0x1800229ec`
- `0x18002e5d0`
- `0x1800351e0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180017085`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180017085`

## string_xrefs

- `0x180017135`: `onecore\base\ngscb\wldp\dll\canexecute.cpp`

## pseudocode

```c
bool __fastcall IsOptInEnabledForHost(void *Buf1)
{
  const char *v2; // r9
  char v3; // bp
  __int64 *v4; // rsi
  __int64 *v5; // rbx
  __int64 *v6; // rdi
  char v7; // cl
  __int64 *v8; // rax
  const WCHAR *v9; // rcx
  const WCHAR *v11; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v13; // [rsp+68h] [rbp+10h] BYREF

  v13 = 0;
  if ( !InitOnceExecuteOnce(&InitOnce, (PINIT_ONCE_FN)ConstructHostList, 0, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\canexecute.cpp",
      v2);
  v3 = 1;
  v4 = *(__int64 **)qword_18005B060;
  v5 = *(__int64 **)qword_18005B060;
  v6 = *(__int64 **)(*(_QWORD *)qword_18005B060 + 8LL);
  if ( !*((_BYTE *)v6 + 25) )
  {
    do
    {
      if ( memcmp_0(v6 + 4, Buf1, 0x10u) < 0 )
      {
        v7 = 1;
      }
      else
      {
        v7 = 0;
        v5 = v6;
      }
      v8 = v6 + 2;
      if ( !v7 )
        v8 = v6;
      v6 = (__int64 *)*v8;
    }
    while ( !*(_BYTE *)(*v8 + 25) );
  }
  if ( *((_BYTE *)v5 + 25) || memcmp_0(Buf1, v5 + 4, 0x10u) < 0 )
    v3 = 0;
  if ( !v3 )
    v5 = v4;
  return v5 != v4
      && (v9 = (const WCHAR *)v5[7]) != 0
      && (v11 = (const WCHAR *)v5[8]) != 0
      && (int)WldpGetApplicationSettingBoolean(v9, v11, (__int64)&v13) >= 0
      && v13 != 0;
}

```

## disassembly

```asm
0x180017054  mov     [rsp+arg_0], rbx
0x180017059  mov     [rsp+arg_10], rbp
0x18001705e  push    rsi
0x18001705f  push    rdi
0x180017060  push    r14
0x180017062  sub     rsp, 40h
0x180017066  mov     r14, rcx
0x180017069  mov     [rsp+58h+arg_8], 0
0x180017071  lea     rcx, InitOnce; InitOnce
0x180017078  xor     r9d, r9d; Context
0x18001707b  xor     r8d, r8d; Parameter
0x18001707e  lea     rdx, ConstructHostList; InitFn
0x180017085  call    cs:__imp_InitOnceExecuteOnce
0x18001708b  test    eax, eax
0x18001708d  jz      loc_180017130
0x180017093  mov     rax, cs:qword_18005B060
0x18001709a  mov     bpl, 1
0x18001709d  mov     rsi, [rax]
0x1800170a0  xor     eax, eax
0x1800170a2  mov     [rsp+58h+var_2C], eax
0x1800170a6  mov     rbx, rsi
0x1800170a9  mov     rdi, [rsi+8]
0x1800170ad  cmp     [rdi+19h], al
0x1800170b0  jnz     short loc_1800170E0
0x1800170b2  lea     rcx, [rdi+20h]; Buf1
0x1800170b6  mov     r8d, 10h; Size
0x1800170bc  mov     rdx, r14; Buf2
0x1800170bf  call    memcmp_0
0x1800170c4  test    eax, eax
0x1800170c6  js      short loc_180017126
0x1800170c8  xor     cl, cl
0x1800170ca  mov     rbx, rdi
0x1800170cd  test    cl, cl
0x1800170cf  lea     rax, [rdi+10h]
0x1800170d3  cmovz   rax, rdi
0x1800170d7  mov     rdi, [rax]
0x1800170da  cmp     byte ptr [rdi+19h], 0
0x1800170de  jz      short loc_1800170B2
0x1800170e0  cmp     byte ptr [rbx+19h], 0
0x1800170e4  jnz     short loc_18001712B
0x1800170e6  lea     rdx, [rbx+20h]; Buf2
0x1800170ea  mov     r8d, 10h; Size
0x1800170f0  mov     rcx, r14; Buf1
0x1800170f3  call    memcmp_0
0x1800170f8  test    eax, eax
0x1800170fa  js      short loc_18001712B
0x1800170fc  test    bpl, bpl
0x1800170ff  cmovz   rbx, rsi
0x180017103  cmp     rbx, rsi
0x180017106  jz      short loc_180017111
0x180017108  mov     rcx, [rbx+38h]; SourceString
0x18001710c  test    rcx, rcx
0x18001710f  jnz     short loc_180017147
0x180017111  xor     al, al
0x180017113  mov     rbx, [rsp+58h+arg_0]
0x180017118  mov     rbp, [rsp+58h+arg_10]
0x18001711d  add     rsp, 40h
0x180017121  pop     r14
0x180017123  pop     rdi
0x180017124  pop     rsi
0x180017125  retn
0x180017126  mov     cl, bpl
0x180017129  jmp     short loc_1800170CD
0x18001712b  xor     bpl, bpl
0x18001712e  jmp     short loc_1800170FC
0x180017130  mov     rcx, [rsp+58h]; this
0x180017135  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\wldp\\dll\\canexe"...
0x18001713c  mov     edx, 98h; void *
0x180017141  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180017147  mov     rdx, [rbx+40h]; PCWSTR
0x18001714b  test    rdx, rdx
0x18001714e  jz      short loc_180017111
0x180017150  lea     r8, [rsp+58h+arg_8]; int
0x180017155  call    WldpGetApplicationSettingBoolean
0x18001715a  test    eax, eax
0x18001715c  js      short loc_180017111
0x18001715e  cmp     [rsp+58h+arg_8], 0
0x180017163  setnz   al
0x180017166  jmp     short loc_180017113
```
