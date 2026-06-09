# SubscriptionConfigWriter::SavePassword(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x180017510`
- end: `0x180017643`
- name: `?SavePassword@SubscriptionConfigWriter@@AEAAXPEAUHKEY__@@PEBG11@Z`
- size: `307`
- prototype: `void __fastcall(SubscriptionConfigWriter *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800165c0`
- `0x1800178f0`

## callees

- `0x180003810`
- `0x1800062d4`
- `0x1800128c0`
- `0x180012b94`
- `0x180012f20`
- `0x180017510`
- `0x18001bdac`
- `0x18001fe50`

## pseudocode

```c
void __fastcall SubscriptionConfigWriter::SavePassword(
        SubscriptionConfigWriter *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  _QWORD *v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx
  _QWORD v14[2]; // [rsp+30h] [rbp-41h] BYREF
  __int64 v15; // [rsp+40h] [rbp-31h]
  unsigned __int64 v16; // [rsp+48h] [rbp-29h]
  _WORD v17[8]; // [rsp+50h] [rbp-21h] BYREF
  __int64 v18; // [rsp+60h] [rbp-11h]
  __int64 v19; // [rsp+68h] [rbp-9h]
  _BYTE v20[32]; // [rsp+70h] [rbp-1h] BYREF

  v16 = 7;
  v15 = 0;
  LOWORD(v14[0]) = 0;
  RegReadStringValue(a2, L"CredSourceId", v14);
  if ( !v15 )
  {
    CreateGuid(v14);
    v8 = v14;
    if ( v16 >= 8 )
      v8 = (_QWORD *)v14[0];
    std::wstring::wstring(v20, v8);
    RegWriteStringValue(a2, L"CredSourceId", v20);
    LOBYTE(v9) = 1;
    std::wstring::_Tidy(v20, v9, 0);
  }
  v19 = 7;
  v18 = 0;
  v17[0] = 0;
  std::wstring::wstring(v20, a3);
  CredentialManager::WriteCredential(v10, v14, v20, a5, v17);
  LOBYTE(v11) = 1;
  std::wstring::_Tidy(v20, v11, 0);
  RegWriteStringValue(a2, a4, v17);
  LOBYTE(v12) = 1;
  std::wstring::_Tidy(v17, v12, 0);
  LOBYTE(v13) = 1;
  std::wstring::_Tidy(v14, v13, 0);
}

```

## disassembly

```asm
0x180017510  push    rbp
0x180017512  push    rbx
0x180017513  push    rsi
0x180017514  push    rdi
0x180017515  push    r14
0x180017517  lea     rbp, [rsp-2Fh]
0x18001751c  sub     rsp, 0A0h
0x180017523  mov     rax, cs:__security_cookie
0x18001752a  xor     rax, rsp
0x18001752d  mov     [rbp+4Fh+var_30], rax
0x180017531  mov     rsi, r9
0x180017534  mov     rdi, r8
0x180017537  mov     rbx, rdx
0x18001753a  mov     r14, [rbp+4Fh+arg_20]
0x18001753e  mov     [rbp+4Fh+var_78], 7
0x180017546  mov     [rbp+4Fh+var_80], 0
0x18001754e  xor     eax, eax
0x180017550  mov     word ptr [rbp+4Fh+var_90], ax
0x180017554  lea     r8, [rbp+4Fh+var_90]
0x180017558  lea     rdx, aCredsourceid; "CredSourceId"
0x18001755f  mov     rcx, rbx
0x180017562  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x180017567  cmp     [rbp+4Fh+var_80], 0
0x18001756c  jnz     short loc_1800175B1
0x18001756e  lea     rcx, [rbp+4Fh+var_90]
0x180017572  call    ?CreateGuid@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CreateGuid(std::wstring &)
0x180017577  lea     rdx, [rbp+4Fh+var_90]
0x18001757b  cmp     [rbp+4Fh+var_78], 8
0x180017580  cmovnb  rdx, [rbp+4Fh+var_90]
0x180017585  lea     rcx, [rbp+4Fh+var_50]
0x180017589  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001758e  nop
0x18001758f  lea     r8, [rbp+4Fh+var_50]
0x180017593  lea     rdx, aCredsourceid; "CredSourceId"
0x18001759a  mov     rcx, rbx
0x18001759d  call    ?RegWriteStringValue@@YAXPEAUHKEY__@@PEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegWriteStringValue(HKEY__ *,ushort const *,std::wstring const &)
0x1800175a2  nop
0x1800175a3  xor     r8d, r8d
0x1800175a6  mov     dl, 1
0x1800175a8  lea     rcx, [rbp+4Fh+var_50]
0x1800175ac  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800175b1  mov     [rbp+4Fh+var_58], 7
0x1800175b9  mov     [rbp+4Fh+var_60], 0
0x1800175c1  xor     eax, eax
0x1800175c3  mov     [rbp+4Fh+var_70], ax
0x1800175c7  mov     rdx, rdi
0x1800175ca  lea     rcx, [rbp+4Fh+var_50]
0x1800175ce  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800175d3  nop
0x1800175d4  lea     rax, [rbp+4Fh+var_70]
0x1800175d8  mov     [rsp+0C0h+var_A0], rax
0x1800175dd  mov     r9, r14
0x1800175e0  lea     r8, [rbp+4Fh+var_50]
0x1800175e4  lea     rdx, [rbp+4Fh+var_90]
0x1800175e8  call    ?WriteCredential@CredentialManager@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEBGAEAV23@@Z; CredentialManager::WriteCredential(std::wstring const &,std::wstring const &,ushort const *,std::wstring &)
0x1800175ed  nop
0x1800175ee  xor     r8d, r8d
0x1800175f1  mov     dl, 1
0x1800175f3  lea     rcx, [rbp+4Fh+var_50]
0x1800175f7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800175fc  lea     r8, [rbp+4Fh+var_70]
0x180017600  mov     rdx, rsi
0x180017603  mov     rcx, rbx
0x180017606  call    ?RegWriteStringValue@@YAXPEAUHKEY__@@PEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegWriteStringValue(HKEY__ *,ushort const *,std::wstring const &)
0x18001760b  nop
0x18001760c  xor     r8d, r8d
0x18001760f  mov     dl, 1
0x180017611  lea     rcx, [rbp+4Fh+var_70]
0x180017615  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001761a  nop
0x18001761b  xor     r8d, r8d
0x18001761e  mov     dl, 1
0x180017620  lea     rcx, [rbp+4Fh+var_90]
0x180017624  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180017629  mov     rcx, [rbp+4Fh+var_30]
0x18001762d  xor     rcx, rsp; StackCookie
0x180017630  call    __security_check_cookie
0x180017635  add     rsp, 0A0h
0x18001763c  pop     r14
0x18001763e  pop     rdi
0x18001763f  pop     rsi
0x180017640  pop     rbx
0x180017641  pop     rbp
0x180017642  retn
```
