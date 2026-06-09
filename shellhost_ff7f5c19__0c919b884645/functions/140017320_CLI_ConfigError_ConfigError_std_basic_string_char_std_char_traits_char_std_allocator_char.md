# CLI::ConfigError::ConfigError(std::basic_string<char,std::char_traits<char>,std::allocator<char>>)

- ea: `0x140017320`
- end: `0x1400174d2`
- name: `??0ConfigError@CLI@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `434`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x14001cd10`
- `0x14001d120`

## callees

- `0x1400083f0`
- `0x140008a50`
- `0x14000f7e0`
- `0x14000fab8`
- `0x140017320`
- `0x1400195a0`

## string_xrefs

- `0x140017383`: `ConfigError`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall CLI::ConfigError::ConfigError(_QWORD *a1, void *a2)
{
  __int64 v4; // rbx
  unsigned __int64 v5; // rdx
  void *v6; // rcx
  unsigned __int64 v7; // rdx
  __int64 v8; // rax
  unsigned __int64 v9; // rdx
  void *v10; // rcx
  void *v12[2]; // [rsp+20h] [rbp-79h] BYREF
  __int128 v13; // [rsp+30h] [rbp-69h]
  __int64 v14; // [rsp+40h] [rbp-59h]
  void **v15; // [rsp+50h] [rbp-49h]
  _OWORD v16[2]; // [rsp+58h] [rbp-41h] BYREF
  _OWORD v17[2]; // [rsp+78h] [rbp-21h] BYREF
  _BYTE v18[32]; // [rsp+98h] [rbp-1h] BYREF
  void *v19; // [rsp+B8h] [rbp+1Fh]

  v19 = a2;
  v4 = std::string::string(v18, a2);
  v14 = v4;
  HIDWORD(v12[1]) = 0;
  *(_QWORD *)&v13 = 11;
  *((_QWORD *)&v13 + 1) = 15;
  strcpy((char *)v12, "ConfigError");
  v15 = v12;
  v16[0] = *(_OWORD *)v4;
  v16[1] = *(_OWORD *)(v4 + 16);
  *(_QWORD *)(v4 + 16) = 0;
  *(_QWORD *)(v4 + 24) = 15;
  *(_BYTE *)v4 = 0;
  v17[0] = *(_OWORD *)v12;
  v17[1] = v13;
  *(_QWORD *)&v13 = 0;
  *((_QWORD *)&v13 + 1) = 15;
  LOBYTE(v12[0]) = 0;
  CLI::ParseError::ParseError(a1, v17, v16, 110);
  *a1 = &CLI::ConfigError::`vftable';
  if ( *((_QWORD *)&v13 + 1) > 0xFu )
  {
    v5 = *((_QWORD *)&v13 + 1) + 1LL;
    if ( (unsigned __int64)(*((_QWORD *)&v13 + 1) + 1LL) < 0x1000 )
    {
      v6 = v12[0];
    }
    else
    {
      v6 = (void *)*((_QWORD *)v12[0] - 1);
      if ( (unsigned __int64)((char *)v12[0] - (char *)v6 - 8) > 0x1F )
        __fastfail(5u);
      v5 = *((_QWORD *)&v13 + 1) + 40LL;
    }
    operator delete(v6, v5);
  }
  *(_QWORD *)&v13 = 0;
  *((_QWORD *)&v13 + 1) = 15;
  LOBYTE(v12[0]) = 0;
  v7 = *(_QWORD *)(v4 + 24);
  if ( v7 > 0xF )
  {
    v8 = *(_QWORD *)v4;
    v9 = v7 + 1;
    if ( v9 < 0x1000 )
    {
      v10 = *(void **)v4;
    }
    else
    {
      v10 = *(void **)(v8 - 8);
      if ( (unsigned __int64)(v8 - (_QWORD)v10 - 8) > 0x1F )
        __fastfail(5u);
      v9 += 39LL;
    }
    operator delete(v10, v9);
  }
  *(_QWORD *)(v4 + 16) = 0;
  *(_QWORD *)(v4 + 24) = 15;
  *(_BYTE *)v4 = 0;
  *a1 = &CLI::ConfigError::`vftable';
  std::string::_Tidy_deallocate(a2);
  return a1;
}

```

## disassembly

```asm
0x140017320  mov     [rsp-8+arg_10], rbx
0x140017325  push    rbp
0x140017326  push    rsi
0x140017327  push    rdi
0x140017328  push    r14
0x14001732a  push    r15
0x14001732c  lea     rbp, [rsp-37h]
0x140017331  sub     rsp, 0D0h
0x140017338  mov     rax, cs:__security_cookie
0x14001733f  xor     rax, rsp
0x140017342  mov     [rbp+57h+var_30], rax
0x140017346  mov     rsi, rdx
0x140017349  mov     rdi, rcx
0x14001734c  mov     [rbp+57h+var_38], rcx
0x140017350  mov     [rbp+57h+var_38], rdx
0x140017354  lea     rax, [rbp+57h+var_58]
0x140017358  mov     [rbp+57h+var_B0], rax
0x14001735c  lea     rcx, [rbp+57h+var_58]
0x140017360  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x140017365  mov     rbx, rax
0x140017368  mov     [rbp+57h+var_B0], rax
0x14001736c  xor     r14d, r14d
0x14001736f  mov     dword ptr [rbp+57h+var_D0+0Ch], r14d
0x140017373  mov     qword ptr [rbp+57h+var_C0], 0Bh
0x14001737b  mov     qword ptr [rbp+57h+var_C0+8], 0Fh
0x140017383  movsd   xmm0, qword ptr cs:aConfigerror; "ConfigError"
0x14001738b  movsd   [rbp+57h+var_D0], xmm0
0x140017390  mov     eax, dword ptr cs:aConfigerror+7; "rror"
0x140017396  mov     dword ptr [rbp+57h+var_D0+7], eax
0x140017399  mov     byte ptr [rbp+57h+var_D0+0Bh], r14b
0x14001739d  lea     rax, [rbp+57h+var_D0]
0x1400173a1  mov     [rbp+57h+var_A0], rax
0x1400173a5  movups  xmm0, xmmword ptr [rbx]
0x1400173a8  movups  [rbp+57h+var_98], xmm0
0x1400173ac  movups  xmm1, xmmword ptr [rbx+10h]
0x1400173b0  movups  [rbp+57h+var_88], xmm1
0x1400173b4  mov     [rbx+10h], r14
0x1400173b8  mov     qword ptr [rbx+18h], 0Fh
0x1400173c0  mov     [rbx], r14b
0x1400173c3  movups  xmm0, xmmword ptr [rbp+57h+var_D0]
0x1400173c7  movups  [rbp+57h+var_78], xmm0
0x1400173cb  movups  xmm1, [rbp+57h+var_C0]
0x1400173cf  movups  [rbp+57h+var_68], xmm1
0x1400173d3  mov     qword ptr [rbp+57h+var_C0], r14
0x1400173d7  mov     qword ptr [rbp+57h+var_C0+8], 0Fh
0x1400173df  mov     byte ptr [rbp+57h+var_D0], r14b
0x1400173e3  mov     r9d, 6Eh ; 'n'
0x1400173e9  lea     r8, [rbp+57h+var_98]
0x1400173ed  lea     rdx, [rbp+57h+var_78]
0x1400173f1  mov     rcx, rdi
0x1400173f4  call    ??0ParseError@CLI@@IEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0W4ExitCodes@1@@Z; CLI::ParseError::ParseError(std::string,std::string,CLI::ExitCodes)
0x1400173f9  lea     r15, ??_7ConfigError@CLI@@6B@; const CLI::ConfigError::`vftable'
0x140017400  mov     [rdi], r15
0x140017403  mov     rdx, qword ptr [rbp+57h+var_C0+8]
0x140017407  cmp     rdx, 0Fh
0x14001740b  jbe     short loc_140017443
0x14001740d  mov     rax, [rbp+57h+var_D0]
0x140017411  inc     rdx; unsigned __int64
0x140017414  cmp     rdx, 1000h
0x14001741b  jb      short loc_14001743B
0x14001741d  mov     rcx, [rax-8]
0x140017421  sub     rax, rcx
0x140017424  sub     rax, 8
0x140017428  cmp     rax, 1Fh
0x14001742c  ja      short loc_140017434
0x14001742e  add     rdx, 27h ; '''
0x140017432  jmp     short loc_14001743E
0x140017434  mov     ecx, 5
0x140017439  int     29h; Win8: RtlFailFast(ecx)
0x14001743b  mov     rcx, rax; void *
0x14001743e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140017443  mov     qword ptr [rbp+57h+var_C0], r14
0x140017447  mov     qword ptr [rbp+57h+var_C0+8], 0Fh
0x14001744f  mov     byte ptr [rbp+57h+var_D0], 0
0x140017453  mov     rdx, [rbx+18h]
0x140017457  cmp     rdx, 0Fh
0x14001745b  jbe     short loc_140017492
0x14001745d  mov     rax, [rbx]
0x140017460  inc     rdx; unsigned __int64
0x140017463  cmp     rdx, 1000h
0x14001746a  jb      short loc_14001748A
0x14001746c  mov     rcx, [rax-8]
0x140017470  sub     rax, rcx
0x140017473  sub     rax, 8
0x140017477  cmp     rax, 1Fh
0x14001747b  ja      short loc_140017483
0x14001747d  add     rdx, 27h ; '''
0x140017481  jmp     short loc_14001748D
0x140017483  mov     ecx, 5
0x140017488  int     29h; Win8: RtlFailFast(ecx)
0x14001748a  mov     rcx, rax; void *
0x14001748d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140017492  mov     [rbx+10h], r14
0x140017496  mov     qword ptr [rbx+18h], 0Fh
0x14001749e  mov     byte ptr [rbx], 0
0x1400174a1  mov     [rdi], r15
0x1400174a4  mov     rcx, rsi; void *
0x1400174a7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400174ac  mov     rax, rdi
0x1400174af  mov     rcx, [rbp+57h+var_30]
0x1400174b3  xor     rcx, rsp; StackCookie
0x1400174b6  call    __security_check_cookie
0x1400174bb  mov     rbx, [rsp+0F0h+arg_10]
0x1400174c3  add     rsp, 0D0h
0x1400174ca  pop     r15
0x1400174cc  pop     r14
0x1400174ce  pop     rdi
0x1400174cf  pop     rsi
0x1400174d0  pop     rbp
0x1400174d1  retn
```
