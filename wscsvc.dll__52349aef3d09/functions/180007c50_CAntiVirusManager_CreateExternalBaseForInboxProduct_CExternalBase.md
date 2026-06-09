# CAntiVirusManager::CreateExternalBaseForInboxProduct(CExternalBase * *)

- ea: `0x180007c50`
- end: `0x1800080ac`
- name: `?CreateExternalBaseForInboxProduct@CAntiVirusManager@@UEAAJPEAPEAVCExternalBase@@@Z`
- size: `1116`
- prototype: `__int64 __fastcall(CAntiVirusManager *__hidden this, struct CExternalBase **)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x180007c50`
- `0x1800088b0`
- `0x180008910`
- `0x180008e48`
- `0x1800202e8`
- `0x180029e74`
- `0x18002b1ac`
- `0x18003fc30`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007fca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007fca`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180007f23`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180007f23`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180007f48`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180007f48`
- `WINHTTP!WinHttpTimeFromSystemTime` at `0x180007f31`
- `WINHTTP!WinHttpTimeFromSystemTime` at `0x180007f31`

## pseudocode

```c
__int64 __fastcall CAntiVirusManager::CreateExternalBaseForInboxProduct(
        CAntiVirusManager *this,
        struct CExternalBase **a2)
{
  __int64 v4; // rax
  int v5; // edi
  CExternalBase *v6; // rsi
  _WORD *v7; // rax
  _WORD *v8; // rdi
  __int64 v9; // rbx
  const wchar_t *v10; // rdx
  __int64 v11; // rcx
  _WORD *v12; // r8
  __int64 v13; // r9
  _WORD *v14; // rcx
  void *v15; // rcx
  __int64 v16; // rax
  CExternalBase *v17; // rsi
  _WORD *v18; // rax
  _WORD *v19; // rdi
  __int64 v20; // rdx
  const unsigned __int16 *v21; // r8
  __int64 v22; // r10
  _WORD *v23; // r9
  _WORD *v24; // rcx
  void *v25; // rcx
  CExternalBase *v26; // rsi
  _WORD *v27; // rax
  _WORD *v28; // rdi
  const unsigned __int16 *v29; // rdx
  __int64 v30; // r9
  _WORD *v31; // r8
  _WORD *v32; // rcx
  void *v33; // rcx
  CExternalBase *v34; // rbx
  unsigned int v35; // eax
  CExternalBase *v36; // rax
  CExternalBase *v37; // rbx
  void *v39; // rdi
  void *v40; // rcx
  CThirdPartyManager *v41; // rcx
  bool v42; // zf
  CExternalBase *v43; // [rsp+20h] [rbp-38h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+28h] [rbp-30h] BYREF

  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
  }
  if ( a2 )
  {
    v4 = *(_QWORD *)this;
    v43 = 0;
    v5 = (*(__int64 (__fastcall **)(CAntiVirusManager *, CExternalBase **))(v4 + 40))(this, &v43);
    if ( v5 < 0 )
      goto LABEL_57;
    v6 = v43;
    v7 = operator new[](0x4Eu, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    if ( v7 )
    {
      v9 = 2147483646;
      v10 = L"{D68DDC3A-831F-4fae-9E44-DA132C1ACF46}";
      v11 = 2147483646;
      v12 = v7;
      v13 = 39;
      do
      {
        if ( !v11 )
          break;
        if ( !*v10 )
          break;
        *v12++ = *v10++;
        --v11;
        --v13;
      }
      while ( v13 );
      v14 = v12 - 1;
      if ( v13 )
        v14 = v12;
      *v14 = 0;
      v15 = (void *)*((_QWORD *)v6 + 1);
      if ( v15 )
        operator delete(v15);
      v16 = *(_QWORD *)v6;
      *((_QWORD *)v6 + 1) = v8;
      v5 = (*(__int64 (__fastcall **)(CExternalBase *, const wchar_t *))(v16 + 32))(v6, v10);
      if ( v5 < 0 )
        goto LABEL_57;
      v17 = v43;
      v18 = operator new[](0x22u, (const struct std::nothrow_t *)&std::nothrow);
      v19 = v18;
      if ( v18 )
      {
        v20 = 2147483646;
        v21 = L"Windows Defender";
        v22 = 17;
        v23 = v18;
        do
        {
          if ( !v20 )
            break;
          if ( !*v21 )
            break;
          *v23++ = *v21++;
          --v20;
          --v22;
        }
        while ( v22 );
        v24 = v23 - 1;
        if ( v22 )
          v24 = v23;
        *v24 = 0;
        v25 = (void *)*((_QWORD *)v17 + 2);
        if ( v25 )
          operator delete(v25);
        *((_QWORD *)v17 + 2) = v19;
        v5 = CExternalBase::SetPath(v43, L"windowsdefender://");
        if ( v5 < 0 )
          goto LABEL_57;
        v26 = v43;
        v27 = operator new[](0x58u, (const struct std::nothrow_t *)&std::nothrow);
        v28 = v27;
        if ( v27 )
        {
          v29 = L"%ProgramFiles%\\Windows Defender\\MsMpeng.exe";
          v30 = 44;
          v31 = v27;
          do
          {
            if ( !v9 )
              break;
            if ( !*v29 )
              break;
            *v31++ = *v29++;
            --v9;
            --v30;
          }
          while ( v30 );
          v32 = v31 - 1;
          if ( v30 )
            v32 = v31;
          *v32 = 0;
          v33 = (void *)*((_QWORD *)v26 + 4);
          if ( v33 )
            operator delete(v33);
          *((_QWORD *)v26 + 4) = v28;
          v34 = v43;
          v35 = *((_DWORD *)v43 + 20) & 0xF000;
          if ( v35 == 4096 || v35 == 0x2000 || !v35 || v35 == 20480 || v35 == 12288 || v35 == 0x4000 || v35 == 0x8000 )
          {
            *((_DWORD *)v43 + 20) &= 0xFFFF0FFF;
            if ( (v35 & 0xFFFFBFFF) != 0 )
            {
              SystemTime = 0;
              v39 = operator new[](0x7Cu, (const struct std::nothrow_t *)&std::nothrow);
              if ( v39 )
              {
                GetSystemTime(&SystemTime);
                if ( WinHttpTimeFromSystemTime(&SystemTime, (LPWSTR)v39)
                  && SystemTimeToFileTime(&SystemTime, (LPFILETIME)v34 + 8) )
                {
                  v40 = (void *)*((_QWORD *)v34 + 9);
                  if ( v40 )
                    operator delete(v40);
                  *((_QWORD *)v34 + 9) = v39;
                }
                else
                {
                  GetLastError();
                  operator delete(v39);
                }
              }
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids, v35);
            }
            *((_DWORD *)v34 + 20) &= 0xFFFF0FFF;
          }
          v36 = v43;
          *((_DWORD *)v43 + 20) &= 0xFFFFFF1F;
          *((_DWORD *)v36 + 20) |= 0x10u;
          v37 = v43;
          ExtractProductOwner(*((unsigned int *)v43 + 20));
          *((_DWORD *)v37 + 20) = *((_DWORD *)v37 + 20) & 0xFFFFF0FF | 0x100;
          *((_DWORD *)v43 + 20) &= 0xFFF0FFFF;
          v5 = 0;
          *a2 = v43;
          return (unsigned int)v5;
        }
        v41 = WPP_GLOBAL_Control;
        v42 = WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control;
      }
      else
      {
        v41 = WPP_GLOBAL_Control;
        v42 = WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control;
      }
      if ( v42 || (*((_BYTE *)v41 + 28) & 1) == 0 )
        goto LABEL_56;
    }
    else
    {
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_56;
      }
    }
    WPP_SF_(*((_QWORD *)v41 + 2), 12, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids);
LABEL_56:
    v5 = -2147024882;
LABEL_57:
    if ( v43 )
      (**(void (__fastcall ***)(CExternalBase *, __int64))v43)(v43, 1);
    return (unsigned int)v5;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180007c50  push    rbx
0x180007c52  push    rbp
0x180007c53  push    r14
0x180007c55  sub     rsp, 40h
0x180007c59  mov     rax, cs:__security_cookie
0x180007c60  xor     rax, rsp
0x180007c63  mov     [rsp+58h+var_20], rax
0x180007c68  mov     r14, rdx
0x180007c6b  mov     rbx, rcx
0x180007c6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c75  lea     rbp, WPP_GLOBAL_Control
0x180007c7c  cmp     rcx, rbp
0x180007c7f  jnz     loc_180008068
0x180007c85  test    r14, r14
0x180007c88  jz      loc_180008054
0x180007c8e  mov     rax, [rbx]
0x180007c91  lea     rdx, [rsp+58h+var_38]
0x180007c96  mov     [rsp+58h+arg_10], rsi
0x180007c9b  mov     rcx, rbx
0x180007c9e  mov     [rsp+58h+arg_18], rdi
0x180007ca3  mov     [rsp+58h+var_38], 0
0x180007cac  mov     rax, [rax+28h]
0x180007cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cb5  mov     edi, eax
0x180007cb7  test    eax, eax
0x180007cb9  js      loc_180007FFC
0x180007cbf  mov     rsi, [rsp+58h+var_38]
0x180007cc4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007ccb  mov     ecx, 4Eh ; 'N'; unsigned __int64
0x180007cd0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007cd5  mov     rdi, rax
0x180007cd8  test    rax, rax
0x180007cdb  jz      loc_18000802B
0x180007ce1  mov     ebx, 7FFFFFFEh
0x180007ce6  lea     rdx, aD68ddc3a831f4f; "{D68DDC3A-831F-4fae-9E44-DA132C1ACF46}"
0x180007ced  mov     ecx, ebx
0x180007cef  mov     r8, rax
0x180007cf2  mov     r9d, 27h ; '''
0x180007cf8  test    rcx, rcx
0x180007cfb  jz      short loc_180007D1A
0x180007cfd  movzx   eax, word ptr [rdx]
0x180007d00  test    ax, ax
0x180007d03  jz      short loc_180007D1A
0x180007d05  mov     [r8], ax
0x180007d09  add     rdx, 2
0x180007d0d  add     r8, 2
0x180007d11  dec     rcx
0x180007d14  sub     r9, 1
0x180007d18  jnz     short loc_180007CF8
0x180007d1a  test    r9, r9
0x180007d1d  lea     rcx, [r8-2]
0x180007d21  cmovnz  rcx, r8
0x180007d25  xor     eax, eax
0x180007d27  mov     [rcx], ax
0x180007d2a  mov     rcx, [rsi+8]; Block
0x180007d2e  test    rcx, rcx
0x180007d31  jnz     loc_18000808C
0x180007d37  mov     rax, [rsi]
0x180007d3a  mov     rcx, rsi
0x180007d3d  mov     [rsi+8], rdi
0x180007d41  mov     rax, [rax+20h]
0x180007d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d4a  mov     edi, eax
0x180007d4c  test    eax, eax
0x180007d4e  js      loc_180007FFC
0x180007d54  mov     rsi, [rsp+58h+var_38]
0x180007d59  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007d60  mov     ecx, 22h ; '"'; unsigned __int64
0x180007d65  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007d6a  mov     rdi, rax
0x180007d6d  test    rax, rax
0x180007d70  jz      loc_18000801F
0x180007d76  mov     rdx, rbx
0x180007d79  lea     r8, aWindowsDefende; "Windows Defender"
0x180007d80  mov     r10d, 11h
0x180007d86  mov     r9, rax
0x180007d89  nop     dword ptr [rax+00000000h]
0x180007d90  test    rdx, rdx
0x180007d93  jz      short loc_180007DB3
0x180007d95  movzx   ecx, word ptr [r8]
0x180007d99  test    cx, cx
0x180007d9c  jz      short loc_180007DB3
0x180007d9e  mov     [r9], cx
0x180007da2  add     r8, 2
0x180007da6  add     r9, 2
0x180007daa  dec     rdx
0x180007dad  sub     r10, 1
0x180007db1  jnz     short loc_180007D90
0x180007db3  test    r10, r10
0x180007db6  lea     rcx, [r9-2]
0x180007dba  cmovnz  rcx, r9
0x180007dbe  xor     eax, eax
0x180007dc0  mov     [rcx], ax
0x180007dc3  mov     rcx, [rsi+10h]; Block
0x180007dc7  test    rcx, rcx
0x180007dca  jnz     loc_180007FDD
0x180007dd0  mov     [rsi+10h], rdi
0x180007dd4  lea     rdx, aWindowsdefende_0; "windowsdefender://"
0x180007ddb  mov     rcx, [rsp+58h+var_38]; this
0x180007de0  call    ?SetPath@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetPath(ushort const *)
0x180007de5  mov     edi, eax
0x180007de7  test    eax, eax
0x180007de9  js      loc_180007FFC
0x180007def  mov     rsi, [rsp+58h+var_38]
0x180007df4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007dfb  mov     ecx, 58h ; 'X'; unsigned __int64
0x180007e00  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007e05  mov     rdi, rax
0x180007e08  test    rax, rax
0x180007e0b  jz      loc_180007FE7
0x180007e11  lea     rdx, aProgramfilesWi_0; "%ProgramFiles%\\Windows Defender\\MsMpe"...
0x180007e18  mov     r9d, 2Ch ; ','
0x180007e1e  mov     r8, rax
0x180007e21  test    rbx, rbx
0x180007e24  jz      short loc_180007E43
0x180007e26  movzx   ecx, word ptr [rdx]
0x180007e29  test    cx, cx
0x180007e2c  jz      short loc_180007E43
0x180007e2e  mov     [r8], cx
0x180007e32  add     rdx, 2
0x180007e36  add     r8, 2
0x180007e3a  dec     rbx
0x180007e3d  sub     r9, 1
0x180007e41  jnz     short loc_180007E21
0x180007e43  test    r9, r9
0x180007e46  lea     rcx, [r8-2]
0x180007e4a  cmovnz  rcx, r8
0x180007e4e  xor     eax, eax
0x180007e50  mov     [rcx], ax
0x180007e53  mov     rcx, [rsi+20h]; Block
0x180007e57  test    rcx, rcx
0x180007e5a  jnz     loc_180008096
0x180007e60  mov     [rsi+20h], rdi
0x180007e64  mov     rbx, [rsp+58h+var_38]
0x180007e69  mov     eax, [rbx+50h]
0x180007e6c  and     eax, 0F000h
0x180007e71  cmp     eax, 1000h
0x180007e76  jz      short loc_180007E87
0x180007e78  cmp     eax, 2000h
0x180007e7d  jz      short loc_180007E87
0x180007e7f  test    eax, eax
0x180007e81  jnz     loc_180007F68
0x180007e87  and     dword ptr [rbx+50h], 0FFFF0FFFh
0x180007e8e  test    eax, 0FFFFBFFFh
0x180007e93  jnz     short loc_180007EF9
0x180007e95  mov     rax, [rsp+58h+var_38]
0x180007e9a  and     dword ptr [rax+50h], 0FFFFFF1Fh
0x180007ea1  or      dword ptr [rax+50h], 10h
0x180007ea5  mov     rbx, [rsp+58h+var_38]
0x180007eaa  mov     ecx, [rbx+50h]
0x180007ead  call    ?ExtractProductOwner@@YA?AW4ProductOwner@@K@Z; ExtractProductOwner(ulong)
0x180007eb2  mov     eax, [rbx+50h]
0x180007eb5  and     eax, 0FFFFF1FFh
0x180007eba  bts     eax, 8
0x180007ebe  mov     [rbx+50h], eax
0x180007ec1  mov     rax, [rsp+58h+var_38]
0x180007ec6  and     dword ptr [rax+50h], 0FFF0FFFFh
0x180007ecd  mov     rax, [rsp+58h+var_38]
0x180007ed2  xor     edi, edi
0x180007ed4  mov     [r14], rax
0x180007ed7  mov     rsi, [rsp+58h+arg_10]
0x180007edc  mov     eax, edi
0x180007ede  mov     rdi, [rsp+58h+arg_18]
0x180007ee3  mov     rcx, [rsp+58h+var_20]
0x180007ee8  xor     rcx, rsp; StackCookie
0x180007eeb  call    __security_check_cookie
0x180007ef0  add     rsp, 40h
0x180007ef4  pop     r14
0x180007ef6  pop     rbp
0x180007ef7  pop     rbx
0x180007ef8  retn
0x180007ef9  xorps   xmm0, xmm0
0x180007efc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007f03  mov     ecx, 7Ch ; '|'; unsigned __int64
0x180007f08  movups  xmmword ptr [rsp+58h+SystemTime.wYear], xmm0
0x180007f0d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007f12  mov     rdi, rax
0x180007f15  test    rax, rax
0x180007f18  jz      loc_180007E95
0x180007f1e  lea     rcx, [rsp+58h+SystemTime]; lpSystemTime
0x180007f23  call    cs:__imp_GetSystemTime
0x180007f29  mov     rdx, rdi; pwszTime
0x180007f2c  lea     rcx, [rsp+58h+SystemTime]; pst
0x180007f31  call    cs:__imp_WinHttpTimeFromSystemTime
0x180007f37  test    eax, eax
0x180007f39  jz      loc_180007FCA
0x180007f3f  lea     rdx, [rbx+40h]; lpFileTime
0x180007f43  lea     rcx, [rsp+58h+SystemTime]; lpSystemTime
0x180007f48  call    cs:__imp_SystemTimeToFileTime
0x180007f4e  test    eax, eax
0x180007f50  jz      short loc_180007FCA
0x180007f52  mov     rcx, [rbx+48h]; Block
0x180007f56  test    rcx, rcx
0x180007f59  jnz     loc_18000805E
0x180007f5f  mov     [rbx+48h], rdi
0x180007f63  jmp     loc_180007E95
0x180007f68  cmp     eax, 5000h
0x180007f6d  jz      loc_180007E87
0x180007f73  cmp     eax, 3000h
0x180007f78  jz      loc_180007E87
0x180007f7e  cmp     eax, 4000h
0x180007f83  jz      loc_180007E87
0x180007f89  cmp     eax, 8000h
0x180007f8e  jz      loc_180007E87
0x180007f94  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f9b  cmp     rcx, rbp
0x180007f9e  jz      short loc_180007FBE
0x180007fa0  test    byte ptr [rcx+1Ch], 1
0x180007fa4  jz      short loc_180007FBE
0x180007fa6  mov     rcx, [rcx+10h]
0x180007faa  lea     r8, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids
0x180007fb1  mov     edx, 0Ch
0x180007fb6  mov     r9d, eax
0x180007fb9  call    WPP_SF_d
0x180007fbe  and     dword ptr [rbx+50h], 0FFFF0FFFh
0x180007fc5  jmp     loc_180007E95
0x180007fca  call    cs:__imp_GetLastError
0x180007fd0  mov     rcx, rdi; Block
0x180007fd3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007fd8  jmp     loc_180007E95
0x180007fdd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007fe2  jmp     loc_180007DD0
0x180007fe7  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fee  cmp     rcx, rbp
0x180007ff1  jnz     loc_1800080A0
0x180007ff7  mov     edi, 8007000Eh
0x180007ffc  mov     rcx, [rsp+58h+var_38]
0x180008001  test    rcx, rcx
0x180008004  jz      loc_180007ED7
0x18000800a  mov     rax, [rcx]
0x18000800d  mov     edx, 1
0x180008012  mov     rax, [rax]
0x180008015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000801a  jmp     loc_180007ED7
0x18000801f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008026  cmp     rcx, rbp
0x180008029  jmp     short loc_180007FF1
0x18000802b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008032  cmp     rcx, rbp
0x180008035  jz      short loc_180007FF7
0x180008037  test    byte ptr [rcx+1Ch], 1
0x18000803b  jz      short loc_180007FF7
0x18000803d  mov     rcx, [rcx+10h]
0x180008041  lea     r8, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids
0x180008048  mov     edx, 0Ch
0x18000804d  call    WPP_SF_
0x180008052  jmp     short loc_180007FF7
0x180008054  mov     eax, 80070057h
0x180008059  jmp     loc_180007EE3
0x18000805e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008063  jmp     loc_180007F5F
0x180008068  test    byte ptr [rcx+1Ch], 10h
0x18000806c  jz      loc_180007C85
0x180008072  mov     rcx, [rcx+10h]
0x180008076  lea     r8, WPP_728c66c465713f49a85befae87578f6c_Traceguids
0x18000807d  mov     edx, 0Ah
0x180008082  call    WPP_SF_
0x180008087  jmp     loc_180007C85
0x18000808c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008091  jmp     loc_180007D37
0x180008096  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000809b  jmp     loc_180007E60
0x1800080a0  test    byte ptr [rcx+1Ch], 1
0x1800080a4  jz      loc_180007FF7
0x1800080aa  jmp     short loc_18000803D
```
