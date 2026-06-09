# CSWbemObjectPath::get_DisplayName(ushort * *)

- ea: `0x18002e7a0`
- end: `0x18002e9b9`
- name: `?get_DisplayName@CSWbemObjectPath@@UEAAJPEAPEAG@Z`
- size: `537`
- prototype: `__int64 __fastcall(CSWbemObjectPath *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000d2c0`
- `0x18000d878`
- `0x18000d980`
- `0x180014da0`
- `0x180018460`
- `0x18002e7a0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002e963`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e963`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e9a0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e9a0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002e8c5`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002e8c5`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002e978`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002e987`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002e996`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002e978`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002e987`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002e996`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSWbemObjectPath::get_DisplayName(CSWbemObjectPath *this, unsigned __int16 **a2)
{
  unsigned int v4; // edi
  __int64 v5; // rax
  bool PathText; // al
  unsigned __int16 *v7; // rbx
  __int64 v8; // r14
  __int64 v9; // rdi
  unsigned __int64 v10; // rdi
  unsigned __int16 *SecurityString; // r15
  __int64 v12; // rax
  unsigned __int16 *LocaleString; // rbp
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // rsi
  __int64 v18; // rax
  BSTR bstrString; // [rsp+88h] [rbp+10h] BYREF

  if ( a2 )
  {
    v4 = -2147217407;
    v5 = *((_QWORD *)this + 14);
    if ( v5 && *(_QWORD *)(v5 + 120) )
    {
      bstrString = 0;
      PathText = CWbemPathCracker::GetPathText(
                   *((CWbemPathCracker **)this + 18),
                   (struct ATL::CComBSTR *)&bstrString,
                   0,
                   1,
                   0);
      v7 = bstrString;
      if ( PathText )
      {
        v8 = -1;
        v9 = -1;
        do
          ++v9;
        while ( bstrString[v9] );
        v10 = v9 + 10;
        SecurityString = CWbemParseDN::GetSecurityString(
                           *(_BYTE *)(*((_QWORD *)this + 14) + 108LL),
                           (enum WbemAuthenticationLevelEnum)*(_DWORD *)(*((_QWORD *)this + 14) + 112LL),
                           *(_BYTE *)(*((_QWORD *)this + 14) + 109LL),
                           (enum WbemImpersonationLevelEnum)*(_DWORD *)(*((_QWORD *)this + 14) + 116LL),
                           *(struct CSWbemPrivilegeSet **)(*((_QWORD *)this + 14) + 120LL),
                           (const unsigned __int16 **)this + 16);
        if ( SecurityString )
        {
          v12 = -1;
          do
            ++v12;
          while ( SecurityString[v12] );
          v10 += v12;
        }
        LocaleString = CWbemParseDN::GetLocaleString(*((unsigned __int16 **)this + 15));
        if ( LocaleString )
        {
          v14 = -1;
          do
            ++v14;
          while ( LocaleString[v14] );
          v10 += v14;
        }
        v15 = -1;
        do
          ++v15;
        while ( v7[v15] );
        if ( v15 && (SecurityString || LocaleString) )
          ++v10;
        v16 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v10, 2u));
        v17 = v16;
        if ( v16 )
        {
          StringCchCopyW(v16, v10, L"WINMGMTS:");
          if ( SecurityString )
            StringCchCatW(v17, v10, SecurityString);
          if ( LocaleString )
            StringCchCatW(v17, v10, LocaleString);
          v18 = -1;
          do
            ++v18;
          while ( v7[v18] );
          if ( v18 && (SecurityString || LocaleString) )
            StringCchCatW(v17, v10, L"!");
          do
            ++v8;
          while ( v7[v8] );
          if ( v8 )
            StringCchCatW(v17, v10, v7);
          *a2 = SysAllocString(v17);
          v4 = 0;
        }
        else
        {
          v4 = -2147217402;
        }
        if ( SecurityString )
          CWin32DefaultArena::WbemMemFree(SecurityString);
        if ( LocaleString )
          CWin32DefaultArena::WbemMemFree(LocaleString);
        if ( v17 )
          CWin32DefaultArena::WbemMemFree(v17);
      }
      SysFreeString(v7);
    }
  }
  else
  {
    return (unsigned int)-2147217400;
  }
  return v4;
}

```

## disassembly

```asm
0x18002e7a0  push    rbx
0x18002e7a2  push    rbp
0x18002e7a3  push    rsi
0x18002e7a4  push    rdi
0x18002e7a5  push    r12
0x18002e7a7  push    r13
0x18002e7a9  push    r14
0x18002e7ab  push    r15
0x18002e7ad  sub     rsp, 38h
0x18002e7b1  mov     r12, rdx
0x18002e7b4  mov     rsi, rcx
0x18002e7b7  xor     r13d, r13d
0x18002e7ba  test    rdx, rdx
0x18002e7bd  jnz     short loc_18002E7C9
0x18002e7bf  mov     edi, 80041008h
0x18002e7c4  jmp     loc_18002E9A6
0x18002e7c9  mov     edi, 80041001h
0x18002e7ce  mov     rax, [rcx+70h]
0x18002e7d2  test    rax, rax
0x18002e7d5  jz      loc_18002E9A6
0x18002e7db  cmp     [rax+78h], r13
0x18002e7df  jz      loc_18002E9A6
0x18002e7e5  mov     [rsp+78h+bstrString], r13
0x18002e7ed  mov     byte ptr [rsp+78h+var_58], r13b; bool
0x18002e7f2  mov     r9b, 1; bool
0x18002e7f5  xor     r8d, r8d; bool
0x18002e7f8  lea     rdx, [rsp+78h+bstrString]; struct ATL::CComBSTR *
0x18002e800  mov     rcx, [rcx+90h]; this
0x18002e807  call    ?GetPathText@CWbemPathCracker@@QEAA_NAEAVCComBSTR@ATL@@_N11@Z; CWbemPathCracker::GetPathText(ATL::CComBSTR &,bool,bool,bool)
0x18002e80c  mov     rbx, [rsp+78h+bstrString]
0x18002e814  test    al, al
0x18002e816  jz      loc_18002E99D
0x18002e81c  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002e820  mov     rdi, r14
0x18002e823  inc     rdi
0x18002e826  cmp     [rbx+rdi*2], r13w
0x18002e82b  jnz     short loc_18002E823
0x18002e82d  add     rdi, 0Ah
0x18002e831  mov     rcx, [rsi+70h]
0x18002e835  lea     rax, [rsi+80h]
0x18002e83c  mov     [rsp+78h+var_50], rax; unsigned __int16 **
0x18002e841  mov     rax, [rcx+78h]
0x18002e845  mov     [rsp+78h+var_58], rax; struct CSWbemPrivilegeSet *
0x18002e84a  mov     r9d, [rcx+74h]; enum WbemImpersonationLevelEnum
0x18002e84e  mov     r8b, [rcx+6Dh]; bool
0x18002e852  mov     edx, [rcx+70h]; enum WbemAuthenticationLevelEnum
0x18002e855  mov     cl, [rcx+6Ch]; bool
0x18002e858  call    ?GetSecurityString@CWbemParseDN@@SAPEAG_NW4WbemAuthenticationLevelEnum@@0W4WbemImpersonationLevelEnum@@AEAVCSWbemPrivilegeSet@@AEAPEAG@Z; CWbemParseDN::GetSecurityString(bool,WbemAuthenticationLevelEnum,bool,WbemImpersonationLevelEnum,CSWbemPrivilegeSet &,ushort * &)
0x18002e85d  mov     r15, rax
0x18002e860  test    rax, rax
0x18002e863  jz      short loc_18002E875
0x18002e865  mov     rax, r14
0x18002e868  inc     rax
0x18002e86b  cmp     [r15+rax*2], r13w
0x18002e870  jnz     short loc_18002E868
0x18002e872  add     rdi, rax
0x18002e875  mov     rcx, [rsi+78h]; unsigned __int16 *
0x18002e879  call    ?GetLocaleString@CWbemParseDN@@SAPEAGPEAG@Z; CWbemParseDN::GetLocaleString(ushort *)
0x18002e87e  mov     rbp, rax
0x18002e881  test    rax, rax
0x18002e884  jz      short loc_18002E897
0x18002e886  mov     rax, r14
0x18002e889  inc     rax
0x18002e88c  cmp     [rbp+rax*2+0], r13w
0x18002e892  jnz     short loc_18002E889
0x18002e894  add     rdi, rax
0x18002e897  mov     rax, r14
0x18002e89a  inc     rax
0x18002e89d  cmp     [rbx+rax*2], r13w
0x18002e8a2  jnz     short loc_18002E89A
0x18002e8a4  test    rax, rax
0x18002e8a7  jz      short loc_18002E8B6
0x18002e8a9  test    r15, r15
0x18002e8ac  jnz     short loc_18002E8B3
0x18002e8ae  test    rbp, rbp
0x18002e8b1  jz      short loc_18002E8B6
0x18002e8b3  inc     rdi
0x18002e8b6  mov     eax, 2
0x18002e8bb  mul     rdi
0x18002e8be  cmovb   rax, r14
0x18002e8c2  mov     rcx, rax
0x18002e8c5  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002e8cb  mov     rsi, rax
0x18002e8ce  test    rax, rax
0x18002e8d1  jnz     short loc_18002E8DD
0x18002e8d3  mov     edi, 80041006h
0x18002e8d8  jmp     loc_18002E970
0x18002e8dd  lea     r8, aWinmgmts_0; "WINMGMTS:"
0x18002e8e4  mov     rdx, rdi; unsigned __int64
0x18002e8e7  mov     rcx, rsi; unsigned __int16 *
0x18002e8ea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002e8ef  test    r15, r15
0x18002e8f2  jz      short loc_18002E902
0x18002e8f4  mov     r8, r15; unsigned __int16 *
0x18002e8f7  mov     rdx, rdi; unsigned __int64
0x18002e8fa  mov     rcx, rsi; unsigned __int16 *
0x18002e8fd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002e902  test    rbp, rbp
0x18002e905  jz      short loc_18002E915
0x18002e907  mov     r8, rbp; unsigned __int16 *
0x18002e90a  mov     rdx, rdi; unsigned __int64
0x18002e90d  mov     rcx, rsi; unsigned __int16 *
0x18002e910  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002e915  mov     rax, r14
0x18002e918  inc     rax
0x18002e91b  cmp     [rbx+rax*2], r13w
0x18002e920  jnz     short loc_18002E918
0x18002e922  test    rax, rax
0x18002e925  jz      short loc_18002E943
0x18002e927  test    r15, r15
0x18002e92a  jnz     short loc_18002E931
0x18002e92c  test    rbp, rbp
0x18002e92f  jz      short loc_18002E943
0x18002e931  lea     r8, asc_18003AEE8; "!"
0x18002e938  mov     rdx, rdi; unsigned __int64
0x18002e93b  mov     rcx, rsi; unsigned __int16 *
0x18002e93e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002e943  inc     r14
0x18002e946  cmp     [rbx+r14*2], r13w
0x18002e94b  jnz     short loc_18002E943
0x18002e94d  test    r14, r14
0x18002e950  jz      short loc_18002E960
0x18002e952  mov     r8, rbx; unsigned __int16 *
0x18002e955  mov     rdx, rdi; unsigned __int64
0x18002e958  mov     rcx, rsi; unsigned __int16 *
0x18002e95b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002e960  mov     rcx, rsi; psz
0x18002e963  call    cs:__imp_SysAllocString
0x18002e969  mov     [r12], rax
0x18002e96d  mov     edi, r13d
0x18002e970  test    r15, r15
0x18002e973  jz      short loc_18002E97F
0x18002e975  mov     rcx, r15
0x18002e978  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002e97e  nop
0x18002e97f  test    rbp, rbp
0x18002e982  jz      short loc_18002E98E
0x18002e984  mov     rcx, rbp
0x18002e987  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002e98d  nop
0x18002e98e  test    rsi, rsi
0x18002e991  jz      short loc_18002E99D
0x18002e993  mov     rcx, rsi
0x18002e996  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002e99c  nop
0x18002e99d  mov     rcx, rbx; bstrString
0x18002e9a0  call    cs:__imp_SysFreeString
0x18002e9a6  mov     eax, edi
0x18002e9a8  add     rsp, 38h
0x18002e9ac  pop     r15
0x18002e9ae  pop     r14
0x18002e9b0  pop     r13
0x18002e9b2  pop     r12
0x18002e9b4  pop     rdi
0x18002e9b5  pop     rsi
0x18002e9b6  pop     rbp
0x18002e9b7  pop     rbx
0x18002e9b8  retn
```
