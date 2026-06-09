# CLI::RequiredError::Subcommand(unsigned __int64)

- ea: `0x14001e850`
- end: `0x14001ea69`
- name: `?Subcommand@RequiredError@CLI@@SA?AV12@_K@Z`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140025b40`

## callees

- `0x14000f7e0`
- `0x14000fab8`
- `0x140010620`
- `0x1400198c0`
- `0x1400199a0`
- `0x14001e850`
- `0x140043df0`
- `0x1400456c4`
- `0x14005e4d8`

## string_xrefs

- `0x14001e898`: `A subcommand`
- `0x14001e93d`: ` subcommands`
- `0x14001e95f`: ` subcommands`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CLI::RequiredError::Subcommand(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // rax
  __int128 v5; // kr00_16
  void **v6; // rbx
  _BYTE *v7; // rbx
  void **v8; // rax
  unsigned __int64 v9; // rdx
  void *v10; // rcx
  unsigned __int64 v11; // rdx
  _BYTE *v12; // rcx
  __int128 v14; // [rsp+40h] [rbp-29h] BYREF
  __int128 v15; // [rsp+50h] [rbp-19h]
  void *Src[2]; // [rsp+60h] [rbp-9h] BYREF
  __int128 v17; // [rsp+70h] [rbp+7h]
  void *v18; // [rsp+80h] [rbp+17h] BYREF
  unsigned __int64 v19; // [rsp+98h] [rbp+2Fh]

  if ( a2 == 1 )
  {
    *(_QWORD *)&v17 = 12;
    *((_QWORD *)&v17 + 1) = 15;
    Src[0] = *(void **)"A subcommand";
    Src[1] = (void *)*(unsigned int *)"mand";
    CLI::RequiredError::RequiredError(a1, Src);
  }
  else
  {
    v3 = std::to_string(&v18);
    v4 = std::string::insert(v3, 0, "Requires at least ");
    *(_OWORD *)Src = 0;
    v17 = 0u;
    *(_OWORD *)Src = *(_OWORD *)v4;
    v17 = *(_OWORD *)(v4 + 16);
    *(_QWORD *)(v4 + 16) = 0;
    *(_QWORD *)(v4 + 24) = 15;
    *(_BYTE *)v4 = 0;
    v5 = v17;
    if ( *((_QWORD *)&v17 + 1) - (_QWORD)v17 < 0xCu )
    {
      v8 = (void **)std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
                      Src,
                      0xCu);
    }
    else
    {
      *(_QWORD *)&v17 = v17 + 12;
      v6 = Src;
      if ( *((_QWORD *)&v5 + 1) > 0xFu )
        v6 = (void **)Src[0];
      v7 = (char *)v6 + v5;
      memmove_0(v7, " subcommands", 0xCu);
      v7[12] = 0;
      v8 = Src;
    }
    v14 = 0;
    v15 = 0u;
    v14 = *(_OWORD *)v8;
    v15 = *((_OWORD *)v8 + 1);
    v8[2] = 0;
    v8[3] = (void *)15;
    *(_BYTE *)v8 = 0;
    CLI::RequiredError::RequiredError(a1, &v14, 106);
    if ( *((_QWORD *)&v17 + 1) > 0xFu )
    {
      v9 = *((_QWORD *)&v17 + 1) + 1LL;
      if ( (unsigned __int64)(*((_QWORD *)&v17 + 1) + 1LL) < 0x1000 )
      {
        v10 = Src[0];
      }
      else
      {
        v10 = (void *)*((_QWORD *)Src[0] - 1);
        if ( (unsigned __int64)((char *)Src[0] - (char *)v10 - 8) > 0x1F )
          __fastfail(5u);
        v9 = *((_QWORD *)&v17 + 1) + 40LL;
      }
      operator delete(v10, v9);
    }
    *(_QWORD *)&v17 = 0;
    *((_QWORD *)&v17 + 1) = 15;
    LOBYTE(Src[0]) = 0;
    if ( v19 > 0xF )
    {
      v11 = v19 + 1;
      if ( v19 + 1 < 0x1000 )
      {
        v12 = v18;
      }
      else
      {
        v12 = (_BYTE *)*((_QWORD *)v18 - 1);
        if ( (unsigned __int64)((_BYTE *)v18 - v12 - 8) > 0x1F )
          __fastfail(5u);
        v11 = v19 + 40;
      }
      operator delete(v12, v11);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x14001e850  mov     [rsp-8+arg_10], rbx
0x14001e855  push    rbp
0x14001e856  push    rsi
0x14001e857  push    rdi
0x14001e858  lea     rbp, [rsp-47h]
0x14001e85d  sub     rsp, 0B0h
0x14001e864  mov     rax, cs:__security_cookie
0x14001e86b  xor     rax, rsp
0x14001e86e  mov     [rbp+57h+var_20], rax
0x14001e872  mov     rdi, rcx
0x14001e875  mov     [rbp+57h+var_90], rcx
0x14001e879  xor     esi, esi
0x14001e87b  cmp     rdx, 1
0x14001e87f  jnz     short loc_14001E8C3
0x14001e881  xorps   xmm0, xmm0
0x14001e884  movups  xmmword ptr [rbp+57h+Src], xmm0
0x14001e888  mov     qword ptr [rbp+57h+var_50], 0Ch
0x14001e890  mov     qword ptr [rbp+57h+var_50+8], 0Fh
0x14001e898  movsd   xmm0, qword ptr cs:aASubcommand; "A subcommand"
0x14001e8a0  movsd   [rbp+57h+Src], xmm0
0x14001e8a5  mov     ecx, dword ptr cs:aASubcommand+8; "mand"
0x14001e8ab  mov     dword ptr [rbp+57h+Src+8], ecx
0x14001e8ae  mov     byte ptr [rbp+57h+Src+0Ch], sil
0x14001e8b2  lea     rdx, [rbp+57h+Src]
0x14001e8b6  mov     rcx, rdi
0x14001e8b9  call    ??0RequiredError@CLI@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::RequiredError::RequiredError(std::string)
0x14001e8be  jmp     loc_14001EA47
0x14001e8c3  lea     rcx, [rbp+57h+var_40]
0x14001e8c7  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@_K@Z; std::to_string(unsigned __int64)
0x14001e8cc  nop
0x14001e8cd  lea     r8, aRequiresAtLeas; "Requires at least "
0x14001e8d4  xor     edx, edx
0x14001e8d6  mov     rcx, rax
0x14001e8d9  call    ?insert@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KQEBD@Z; std::string::insert(unsigned __int64,char const * const)
0x14001e8de  xorps   xmm0, xmm0
0x14001e8e1  movups  xmmword ptr [rbp+57h+Src], xmm0
0x14001e8e5  mov     qword ptr [rbp+57h+var_50], rsi
0x14001e8e9  mov     qword ptr [rbp+57h+var_50+8], rsi
0x14001e8ed  movups  xmm0, xmmword ptr [rax]
0x14001e8f0  movups  xmmword ptr [rbp+57h+Src], xmm0
0x14001e8f4  movups  xmm1, xmmword ptr [rax+10h]
0x14001e8f8  movups  [rbp+57h+var_50], xmm1
0x14001e8fc  mov     [rax+10h], rsi
0x14001e900  mov     qword ptr [rax+18h], 0Fh
0x14001e908  mov     byte ptr [rax], 0
0x14001e90b  mov     rcx, qword ptr [rbp+57h+var_50]
0x14001e90f  mov     rdx, qword ptr [rbp+57h+var_50+8]
0x14001e913  mov     rax, rdx
0x14001e916  sub     rax, rcx
0x14001e919  cmp     rax, 0Ch
0x14001e91d  jb      short loc_14001E956
0x14001e91f  lea     rax, [rcx+0Ch]
0x14001e923  mov     qword ptr [rbp+57h+var_50], rax
0x14001e927  lea     rbx, [rbp+57h+Src]
0x14001e92b  cmp     rdx, 0Fh
0x14001e92f  cmova   rbx, [rbp+57h+Src]
0x14001e934  add     rbx, rcx
0x14001e937  mov     r8d, 0Ch; Size
0x14001e93d  lea     rdx, aSubcommands_1; " subcommands"
0x14001e944  mov     rcx, rbx; void *
0x14001e947  call    memmove_0
0x14001e94c  mov     byte ptr [rbx+0Ch], 0
0x14001e950  lea     rax, [rbp+57h+Src]
0x14001e954  jmp     short loc_14001E977
0x14001e956  mov     [rsp+0C0h+Size], 0Ch; Size
0x14001e95f  lea     r9, aSubcommands_1; " subcommands"
0x14001e966  xor     r8d, r8d
0x14001e969  mov     edx, 0Ch
0x14001e96e  lea     rcx, [rbp+57h+Src]; Src
0x14001e972  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x14001e977  xorps   xmm0, xmm0
0x14001e97a  movups  [rbp+57h+var_80], xmm0
0x14001e97e  mov     qword ptr [rbp+57h+var_70], rsi
0x14001e982  mov     qword ptr [rbp+57h+var_70+8], rsi
0x14001e986  movups  xmm0, xmmword ptr [rax]
0x14001e989  movups  [rbp+57h+var_80], xmm0
0x14001e98d  movups  xmm1, xmmword ptr [rax+10h]
0x14001e991  movups  [rbp+57h+var_70], xmm1
0x14001e995  mov     [rax+10h], rsi
0x14001e999  mov     qword ptr [rax+18h], 0Fh
0x14001e9a1  mov     byte ptr [rax], 0
0x14001e9a4  mov     r8d, 6Ah ; 'j'
0x14001e9aa  lea     rdx, [rbp+57h+var_80]
0x14001e9ae  mov     rcx, rdi
0x14001e9b1  call    ??0RequiredError@CLI@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ExitCodes@1@@Z; CLI::RequiredError::RequiredError(std::string,CLI::ExitCodes)
0x14001e9b6  nop
0x14001e9b7  mov     rdx, qword ptr [rbp+57h+var_50+8]
0x14001e9bb  cmp     rdx, 0Fh
0x14001e9bf  jbe     short loc_14001E9F7
0x14001e9c1  mov     rax, [rbp+57h+Src]
0x14001e9c5  inc     rdx; unsigned __int64
0x14001e9c8  cmp     rdx, 1000h
0x14001e9cf  jb      short loc_14001E9EF
0x14001e9d1  mov     rcx, [rax-8]
0x14001e9d5  sub     rax, rcx
0x14001e9d8  sub     rax, 8
0x14001e9dc  cmp     rax, 1Fh
0x14001e9e0  ja      short loc_14001E9E8
0x14001e9e2  add     rdx, 27h ; '''
0x14001e9e6  jmp     short loc_14001E9F2
0x14001e9e8  mov     ecx, 5
0x14001e9ed  int     29h; Win8: RtlFailFast(ecx)
0x14001e9ef  mov     rcx, rax; void *
0x14001e9f2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001e9f7  mov     qword ptr [rbp+57h+var_50], rsi
0x14001e9fb  mov     qword ptr [rbp+57h+var_50+8], 0Fh
0x14001ea03  mov     byte ptr [rbp+57h+Src], 0
0x14001ea07  mov     rdx, [rbp+57h+var_28]
0x14001ea0b  cmp     rdx, 0Fh
0x14001ea0f  jbe     short loc_14001EA47
0x14001ea11  mov     rax, [rbp+57h+var_40]
0x14001ea15  inc     rdx; unsigned __int64
0x14001ea18  cmp     rdx, 1000h
0x14001ea1f  jb      short loc_14001EA3F
0x14001ea21  mov     rcx, [rax-8]
0x14001ea25  sub     rax, rcx
0x14001ea28  sub     rax, 8
0x14001ea2c  cmp     rax, 1Fh
0x14001ea30  ja      short loc_14001EA38
0x14001ea32  add     rdx, 27h ; '''
0x14001ea36  jmp     short loc_14001EA42
0x14001ea38  mov     ecx, 5
0x14001ea3d  int     29h; Win8: RtlFailFast(ecx)
0x14001ea3f  mov     rcx, rax; void *
0x14001ea42  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001ea47  mov     rax, rdi
0x14001ea4a  mov     rcx, [rbp+57h+var_20]
0x14001ea4e  xor     rcx, rsp; StackCookie
0x14001ea51  call    __security_check_cookie
0x14001ea56  mov     rbx, [rsp+0C0h+arg_10]
0x14001ea5e  add     rsp, 0B0h
0x14001ea65  pop     rdi
0x14001ea66  pop     rsi
0x14001ea67  pop     rbp
0x14001ea68  retn
```
