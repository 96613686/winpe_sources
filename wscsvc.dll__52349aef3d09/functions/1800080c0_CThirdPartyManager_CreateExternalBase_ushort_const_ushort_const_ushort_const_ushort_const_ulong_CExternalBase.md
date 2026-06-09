# CThirdPartyManager::CreateExternalBase(ushort const *,ushort const *,ushort const *,ushort const *,ulong,CExternalBase * *)

- ea: `0x1800080c0`
- end: `0x1800088a4`
- name: `?CreateExternalBase@CThirdPartyManager@@QEAAJPEBG000KPEAPEAVCExternalBase@@@Z`
- size: `2020`
- prototype: `__int64 __fastcall(CThirdPartyManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, struct CExternalBase **)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180036adc`
- `0x180039b80`

## callees

- `0x1800080c0`
- `0x1800088b0`
- `0x180008910`
- `0x180008e48`
- `0x1800202e8`
- `0x180029e74`
- `0x18002b1ac`
- `0x18002fbb4`
- `0x18003fc30`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008666`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008666`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180008558`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180008558`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000857d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000857d`
- `WINHTTP!WinHttpTimeFromSystemTime` at `0x180008566`
- `WINHTTP!WinHttpTimeFromSystemTime` at `0x180008566`

## pseudocode

```c
__int64 __fastcall CThirdPartyManager::CreateExternalBase(
        CThirdPartyManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned int a6,
        struct CExternalBase **a7)
{
  const unsigned __int16 *v8; // rsi
  __int64 v10; // rax
  unsigned __int16 *v11; // rdx
  CThirdPartyManager **v12; // r8
  int v13; // r15d
  CExternalBase *v14; // r13
  __int64 v15; // rbp
  unsigned __int64 v16; // rbp
  size_t v17; // rax
  const unsigned __int16 *v18; // rax
  unsigned __int16 *v19; // r12
  __int64 v20; // rdi
  __int64 v21; // rcx
  unsigned __int16 *v22; // rcx
  CExternalBase *v23; // r13
  __int64 v24; // rbp
  unsigned __int64 v25; // rbp
  unsigned __int64 v26; // rbx
  size_t v27; // rax
  void *v28; // rax
  void *v29; // r12
  __int64 v30; // rcx
  _WORD *v31; // rdx
  _WORD *v32; // rcx
  void *v33; // rbp
  void *v34; // rcx
  CExternalBase *v35; // rbp
  __int64 v36; // rax
  unsigned __int64 v37; // rax
  size_t v38; // rax
  void *v39; // rax
  void *v40; // r14
  _WORD *v41; // rdx
  _WORD *v42; // rcx
  void *v43; // rbx
  void *v44; // rcx
  unsigned int v45; // ebx
  CThirdPartyManager *v46; // rcx
  CExternalBase *v47; // rdi
  unsigned int v48; // eax
  CExternalBase *v49; // rcx
  unsigned int v50; // edi
  CExternalBase *v51; // rbx
  CThirdPartyManager *v53; // rcx
  bool v54; // zf
  void *v55; // rbx
  void *v56; // rcx
  void *v57; // rcx
  __int64 v58; // rax
  CExternalBase *v59; // [rsp+30h] [rbp-78h] BYREF
  struct CExternalBase **v60; // [rsp+38h] [rbp-70h]
  struct _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-68h] BYREF

  v8 = a5;
  v60 = a7;
  v10 = *(_QWORD *)this;
  *(_QWORD *)&SystemTime.wYear = a4;
  v59 = 0;
  v13 = (*(__int64 (__fastcall **)(CThirdPartyManager *, CExternalBase **))(v10 + 40))(this, &v59);
  if ( v13 < 0 )
    goto LABEL_35;
  v14 = v59;
  if ( a2 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a2[v15] );
    v16 = v15 + 1;
    v17 = 2 * v16;
    if ( !is_mul_ok(v16, 2u) )
      v17 = -1;
    v18 = (const unsigned __int16 *)operator new[](v17, (const struct std::nothrow_t *)&std::nothrow);
    v19 = (unsigned __int16 *)v18;
    if ( !v18 )
    {
      v53 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_76;
      }
LABEL_73:
      WPP_SF_(*((_QWORD *)v53 + 2), 12, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids);
LABEL_76:
      v13 = -2147024882;
      goto LABEL_35;
    }
    v12 = &WPP_GLOBAL_Control;
    v20 = 2147483646;
    if ( v16 )
    {
      if ( v16 <= 0x7FFFFFFF )
      {
        v21 = 2147483646;
        v11 = (unsigned __int16 *)v18;
        do
        {
          if ( !v21 )
            break;
          if ( !*a2 )
            break;
          *v11++ = *a2++;
          --v21;
          --v16;
        }
        while ( v16 );
        v22 = v11 - 1;
        a2 = v18;
        if ( v16 )
          v22 = v11;
        v13 = 0;
        *v22 = 0;
        goto LABEL_17;
      }
      v13 = -2147024809;
      *v18 = 0;
    }
    else
    {
      v13 = -2147024809;
    }
    a2 = 0;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids, 2147942487LL);
    }
    operator delete(v19);
    v12 = &WPP_GLOBAL_Control;
LABEL_17:
    if ( v13 < 0 )
      goto LABEL_18;
    goto LABEL_104;
  }
  v20 = 2147483646;
LABEL_104:
  v57 = (void *)*((_QWORD *)v14 + 1);
  if ( v57 )
    operator delete(v57);
  v58 = *(_QWORD *)v14;
  *((_QWORD *)v14 + 1) = a2;
  v13 = (*(__int64 (__fastcall **)(CExternalBase *, unsigned __int16 *, CThirdPartyManager **))(v58 + 32))(
          v14,
          v11,
          v12);
LABEL_18:
  if ( v13 < 0 )
    goto LABEL_35;
  v23 = v59;
  if ( a3 )
  {
    v24 = -1;
    do
      ++v24;
    while ( a3[v24] );
    v25 = v24 + 1;
    v26 = 255;
    if ( v25 >= 0xFF )
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids,
          (unsigned int)v25,
          255);
      }
      v25 = 255;
    }
    v27 = 2 * v25;
    if ( !is_mul_ok(v25, 2u) )
      v27 = -1;
    v28 = operator new[](v27, (const struct std::nothrow_t *)&std::nothrow);
    v29 = v28;
    if ( !v28 )
    {
      v53 = WPP_GLOBAL_Control;
      v54 = WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control;
      goto LABEL_75;
    }
    if ( v25 )
    {
      v30 = 2147483646;
      v31 = v28;
      do
      {
        if ( !v30 )
          break;
        if ( !*a3 )
          break;
        *v31++ = *a3++;
        --v30;
        --v25;
      }
      while ( v25 );
      v54 = v25 == 0;
      v32 = v31 - 1;
      v33 = v28;
      if ( !v54 )
        v32 = v31;
      v13 = 0;
      *v32 = 0;
    }
    else
    {
      v13 = -2147024809;
      v33 = 0;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids, 2147942487LL);
      }
      operator delete(v29);
    }
    if ( v13 < 0 )
      goto LABEL_35;
  }
  else
  {
    v33 = 0;
    v26 = 255;
  }
  v34 = (void *)*((_QWORD *)v23 + 2);
  if ( v34 )
    operator delete(v34);
  *((_QWORD *)v23 + 2) = v33;
  v13 = CExternalBase::SetPath(v59, *(const unsigned __int16 **)&SystemTime.wYear);
  if ( v13 < 0 )
    goto LABEL_35;
  v35 = v59;
  if ( a5 )
  {
    v36 = -1;
    do
      ++v36;
    while ( a5[v36] );
    v37 = v36 + 1;
    if ( v37 >= 0xFF )
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids,
          (unsigned int)v37,
          255);
      }
    }
    else
    {
      v26 = v37;
    }
    v38 = 2 * v26;
    if ( !is_mul_ok(v26, 2u) )
      v38 = -1;
    v39 = operator new[](v38, (const struct std::nothrow_t *)&std::nothrow);
    v40 = v39;
    if ( v39 )
    {
      if ( v26 )
      {
        v41 = v39;
        do
        {
          if ( !v20 )
            break;
          if ( !*v8 )
            break;
          *v41++ = *v8++;
          --v20;
          --v26;
        }
        while ( v26 );
        v54 = v26 == 0;
        v42 = v41 - 1;
        v43 = v39;
        if ( !v54 )
          v42 = v41;
        v13 = 0;
        *v42 = 0;
      }
      else
      {
        v13 = -2147024809;
        v43 = 0;
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids,
            2147942487LL);
        }
        operator delete(v40);
      }
      if ( v13 >= 0 )
        goto LABEL_58;
LABEL_35:
      if ( v59 )
        (**(void (__fastcall ***)(CExternalBase *, __int64))v59)(v59, 1);
      return (unsigned int)v13;
    }
    v53 = WPP_GLOBAL_Control;
    v54 = WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control;
LABEL_75:
    if ( v54 || (*((_BYTE *)v53 + 28) & 1) == 0 )
      goto LABEL_76;
    goto LABEL_73;
  }
  v43 = 0;
  v13 = 0;
LABEL_58:
  v44 = (void *)*((_QWORD *)v35 + 4);
  if ( v44 )
    operator delete(v44);
  *((_QWORD *)v35 + 4) = v43;
  v45 = a6 & 0xF000;
  if ( v45 == 4096
    || v45 == 0x2000
    || (a6 & 0xF000) == 0
    || v45 == 20480
    || v45 == 12288
    || v45 == 0x4000
    || v45 == 0x8000 )
  {
    v46 = WPP_GLOBAL_Control;
  }
  else
  {
    v46 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids, a6 & 0xF000);
      v46 = WPP_GLOBAL_Control;
    }
    v45 = 0;
  }
  v47 = v59;
  v48 = *((_DWORD *)v59 + 20) & 0xF000;
  if ( v48 != 4096 && v48 != 0x2000 && v48 && v48 != 20480 && v48 != 12288 && v48 != 0x4000 && v48 != 0x8000 )
  {
    if ( v46 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v46 + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v46 + 2), 12, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids, v48);
    v48 = 0;
  }
  *((_DWORD *)v47 + 20) &= 0xFFFF0FFF;
  *((_DWORD *)v47 + 20) |= v45;
  if ( v48 != v45 && (v45 || v48 != 0x4000) )
  {
    SystemTime = 0;
    v55 = operator new[](0x7Cu, (const struct std::nothrow_t *)&std::nothrow);
    if ( v55 )
    {
      GetSystemTime(&SystemTime);
      if ( WinHttpTimeFromSystemTime(&SystemTime, (LPWSTR)v55) && SystemTimeToFileTime(&SystemTime, (LPFILETIME)v47 + 8) )
      {
        v56 = (void *)*((_QWORD *)v47 + 9);
        if ( v56 )
          operator delete(v56);
        *((_QWORD *)v47 + 9) = v55;
      }
      else
      {
        GetLastError();
        operator delete(v55);
      }
    }
  }
  v49 = v59;
  v50 = a6 & 0xF00;
  *((_DWORD *)v59 + 20) &= 0xFFFFFF0F;
  *((_DWORD *)v49 + 20) |= a6 & 0x10;
  if ( (a6 & 0xE00) != 0 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids, a6 & 0xF00);
    }
    v50 = 0;
  }
  v51 = v59;
  ExtractProductOwner(*((unsigned int *)v59 + 20));
  *((_DWORD *)v51 + 20) = v50 | *((_DWORD *)v51 + 20) & 0xFFFFF0FF;
  *((_DWORD *)v59 + 20) ^= (a6 ^ *((_DWORD *)v59 + 20)) & 0xF0000;
  *v60 = v59;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800080c0  push    rbx
0x1800080c2  push    rbp
0x1800080c3  push    rsi
0x1800080c4  push    rdi
0x1800080c5  push    r12
0x1800080c7  push    r13
0x1800080c9  push    r14
0x1800080cb  push    r15
0x1800080cd  sub     rsp, 68h
0x1800080d1  mov     rax, cs:__security_cookie
0x1800080d8  xor     rax, rsp
0x1800080db  mov     [rsp+0A8h+var_58], rax
0x1800080e0  mov     rax, [rsp+0A8h+arg_30]
0x1800080e8  mov     rbx, rdx
0x1800080eb  mov     rsi, [rsp+0A8h+arg_20]
0x1800080f3  lea     rdx, [rsp+0A8h+var_78]
0x1800080f8  mov     [rsp+0A8h+var_70], rax
0x1800080fd  mov     r14, r8
0x180008100  mov     rax, [rcx]
0x180008103  mov     qword ptr [rsp+0A8h+SystemTime.wYear], r9
0x180008108  mov     [rsp+0A8h+var_78], 0
0x180008111  mov     rax, [rax+28h]
0x180008115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000811a  mov     r15d, eax
0x18000811d  test    eax, eax
0x18000811f  js      loc_18000829D
0x180008125  mov     r13, [rsp+0A8h+var_78]
0x18000812a  test    rbx, rbx
0x18000812d  jz      loc_1800086C4
0x180008133  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000813a  mov     rbp, rcx
0x18000813d  nop     dword ptr [rax]
0x180008140  inc     rbp
0x180008143  cmp     word ptr [rbx+rbp*2], 0
0x180008148  jnz     short loc_180008140
0x18000814a  inc     rbp
0x18000814d  mov     eax, 2
0x180008152  mul     rbp
0x180008155  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000815c  cmovb   rax, rcx
0x180008160  mov     rcx, rax; unsigned __int64
0x180008163  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180008168  mov     r12, rax
0x18000816b  test    rax, rax
0x18000816e  jz      loc_1800084C1
0x180008174  lea     r8, WPP_GLOBAL_Control
0x18000817b  mov     edi, 7FFFFFFEh
0x180008180  test    rbp, rbp
0x180008183  jz      loc_1800086D3
0x180008189  cmp     rbp, 7FFFFFFFh
0x180008190  ja      loc_1800086CB
0x180008196  mov     ecx, edi
0x180008198  mov     rdx, rax
0x18000819b  nop     dword ptr [rax+rax+00h]
0x1800081a0  test    rcx, rcx
0x1800081a3  jz      short loc_1800081C1
0x1800081a5  movzx   eax, word ptr [rbx]
0x1800081a8  test    ax, ax
0x1800081ab  jz      short loc_1800081C1
0x1800081ad  mov     [rdx], ax
0x1800081b0  add     rbx, 2
0x1800081b4  add     rdx, 2
0x1800081b8  dec     rcx
0x1800081bb  sub     rbp, 1
0x1800081bf  jnz     short loc_1800081A0
0x1800081c1  test    rbp, rbp
0x1800081c4  lea     rcx, [rdx-2]
0x1800081c8  mov     rbx, r12
0x1800081cb  cmovnz  rcx, rdx
0x1800081cf  xor     eax, eax
0x1800081d1  xor     r15d, r15d
0x1800081d4  mov     [rcx], ax
0x1800081d7  test    r15d, r15d
0x1800081da  jns     loc_18000868D
0x1800081e0  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800081e7  test    r15d, r15d
0x1800081ea  js      loc_18000829D
0x1800081f0  mov     r13, [rsp+0A8h+var_78]
0x1800081f5  test    r14, r14
0x1800081f8  jz      loc_1800082C0
0x1800081fe  mov     rbp, r12
0x180008201  inc     rbp
0x180008204  cmp     word ptr [r14+rbp*2], 0
0x18000820a  jnz     short loc_180008201
0x18000820c  inc     rbp
0x18000820f  mov     ebx, 0FFh
0x180008214  cmp     rbp, rbx
0x180008217  jnb     loc_18000872F
0x18000821d  mov     eax, 2
0x180008222  mul     rbp
0x180008225  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000822c  cmovb   rax, r12
0x180008230  mov     rcx, rax; unsigned __int64
0x180008233  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180008238  mov     r12, rax
0x18000823b  test    rax, rax
0x18000823e  jz      loc_18000850C
0x180008244  test    rbp, rbp
0x180008247  jz      loc_18000876D
0x18000824d  cmp     rbp, 7FFFFFFFh
0x180008254  ja      loc_180008765
0x18000825a  mov     rcx, rdi
0x18000825d  mov     rdx, rax
0x180008260  test    rcx, rcx
0x180008263  jz      short loc_180008282
0x180008265  movzx   eax, word ptr [r14]
0x180008269  test    ax, ax
0x18000826c  jz      short loc_180008282
0x18000826e  mov     [rdx], ax
0x180008271  add     r14, 2
0x180008275  add     rdx, 2
0x180008279  dec     rcx
0x18000827c  sub     rbp, 1
0x180008280  jnz     short loc_180008260
0x180008282  test    rbp, rbp
0x180008285  lea     rcx, [rdx-2]
0x180008289  mov     rbp, r12
0x18000828c  cmovnz  rcx, rdx
0x180008290  xor     eax, eax
0x180008292  xor     r15d, r15d
0x180008295  mov     [rcx], ax
0x180008298  test    r15d, r15d
0x18000829b  jns     short loc_1800082CA
0x18000829d  mov     rcx, [rsp+0A8h+var_78]
0x1800082a2  test    rcx, rcx
0x1800082a5  jz      loc_180008496
0x1800082ab  mov     rax, [rcx]
0x1800082ae  mov     edx, 1
0x1800082b3  mov     rax, [rax]
0x1800082b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082bb  jmp     loc_180008496
0x1800082c0  xor     ebp, ebp
0x1800082c2  mov     ebx, 0FFh
0x1800082c7  xor     r15d, r15d
0x1800082ca  mov     rcx, [r13+10h]; Block
0x1800082ce  test    rcx, rcx
0x1800082d1  jnz     loc_1800084B7
0x1800082d7  mov     [r13+10h], rbp
0x1800082db  test    r15d, r15d
0x1800082de  js      short loc_18000829D
0x1800082e0  mov     rdx, qword ptr [rsp+0A8h+SystemTime.wYear]; unsigned __int16 *
0x1800082e5  mov     rcx, [rsp+0A8h+var_78]; this
0x1800082ea  call    ?SetPath@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetPath(ushort const *)
0x1800082ef  mov     r15d, eax
0x1800082f2  test    eax, eax
0x1800082f4  js      short loc_18000829D
0x1800082f6  mov     rbp, [rsp+0A8h+var_78]
0x1800082fb  test    rsi, rsi
0x1800082fe  jz      loc_180008683
0x180008304  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000830b  mov     rax, r8
0x18000830e  inc     rax
0x180008311  cmp     word ptr [rsi+rax*2], 0
0x180008316  jnz     short loc_18000830E
0x180008318  inc     rax
0x18000831b  cmp     rax, rbx
0x18000831e  jnb     loc_1800087BF
0x180008324  mov     rbx, rax
0x180008327  lea     r12, WPP_GLOBAL_Control
0x18000832e  mov     eax, 2
0x180008333  mul     rbx
0x180008336  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000833d  cmovb   rax, r8
0x180008341  mov     rcx, rax; unsigned __int64
0x180008344  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180008349  mov     r14, rax
0x18000834c  test    rax, rax
0x18000834f  jz      loc_1800084F1
0x180008355  test    rbx, rbx
0x180008358  jz      loc_180008810
0x18000835e  cmp     rbx, 7FFFFFFFh
0x180008365  ja      loc_180008808
0x18000836b  mov     rdx, rax
0x18000836e  xchg    ax, ax
0x180008370  test    rdi, rdi
0x180008373  jz      short loc_180008391
0x180008375  movzx   eax, word ptr [rsi]
0x180008378  test    ax, ax
0x18000837b  jz      short loc_180008391
0x18000837d  mov     [rdx], ax
0x180008380  add     rsi, 2
0x180008384  add     rdx, 2
0x180008388  dec     rdi
0x18000838b  sub     rbx, 1
0x18000838f  jnz     short loc_180008370
0x180008391  test    rbx, rbx
0x180008394  lea     rcx, [rdx-2]
0x180008398  mov     rbx, r14
0x18000839b  cmovnz  rcx, rdx
0x18000839f  xor     eax, eax
0x1800083a1  xor     r15d, r15d
0x1800083a4  mov     [rcx], ax
0x1800083a7  test    r15d, r15d
0x1800083aa  js      loc_18000829D
0x1800083b0  mov     rcx, [rbp+20h]; Block
0x1800083b4  test    rcx, rcx
0x1800083b7  jnz     loc_18000885A
0x1800083bd  mov     [rbp+20h], rbx
0x1800083c1  test    r15d, r15d
0x1800083c4  js      loc_18000829D
0x1800083ca  mov     esi, [rsp+0A8h+arg_28]
0x1800083d1  mov     ebx, esi
0x1800083d3  and     ebx, 0F000h
0x1800083d9  cmp     ebx, 1000h
0x1800083df  jz      short loc_1800083F1
0x1800083e1  cmp     ebx, 2000h
0x1800083e7  jz      short loc_1800083F1
0x1800083e9  test    ebx, ebx
0x1800083eb  jnz     loc_1800085A1
0x1800083f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800083f8  lea     rbp, WPP_GLOBAL_Control
0x1800083ff  mov     rdi, [rsp+0A8h+var_78]
0x180008404  mov     eax, [rdi+50h]
0x180008407  and     eax, 0F000h
0x18000840c  cmp     eax, 1000h
0x180008411  jz      short loc_180008422
0x180008413  cmp     eax, 2000h
0x180008418  jz      short loc_180008422
0x18000841a  test    eax, eax
0x18000841c  jnz     loc_180008610
0x180008422  and     dword ptr [rdi+50h], 0FFFF0FFFh
0x180008429  or      [rdi+50h], ebx
0x18000842c  cmp     eax, ebx
0x18000842e  jnz     loc_18000851F
0x180008434  mov     rcx, [rsp+0A8h+var_78]
0x180008439  mov     eax, esi
0x18000843b  and     eax, 10h
0x18000843e  mov     edi, esi
0x180008440  and     edi, 0F00h
0x180008446  and     dword ptr [rcx+50h], 0FFFFFF0Fh
0x18000844d  or      [rcx+50h], eax
0x180008450  test    edi, 0FFFFFEFFh
0x180008456  jnz     loc_180008864
0x18000845c  mov     rbx, [rsp+0A8h+var_78]
0x180008461  mov     ecx, [rbx+50h]
0x180008464  call    ?ExtractProductOwner@@YA?AW4ProductOwner@@K@Z; ExtractProductOwner(ulong)
0x180008469  mov     eax, [rbx+50h]
0x18000846c  and     eax, 0FFFFF0FFh
0x180008471  or      eax, edi
0x180008473  mov     [rbx+50h], eax
0x180008476  mov     rdx, [rsp+0A8h+var_78]
0x18000847b  mov     ecx, [rdx+50h]
0x18000847e  xor     ecx, esi
0x180008480  and     ecx, 0F0000h
0x180008486  xor     [rdx+50h], ecx
0x180008489  mov     rcx, [rsp+0A8h+var_70]
0x18000848e  mov     rax, [rsp+0A8h+var_78]
0x180008493  mov     [rcx], rax
0x180008496  mov     eax, r15d
0x180008499  mov     rcx, [rsp+0A8h+var_58]
0x18000849e  xor     rcx, rsp; StackCookie
0x1800084a1  call    __security_check_cookie
0x1800084a6  add     rsp, 68h
0x1800084aa  pop     r15
0x1800084ac  pop     r14
0x1800084ae  pop     r13
0x1800084b0  pop     r12
0x1800084b2  pop     rdi
0x1800084b3  pop     rsi
0x1800084b4  pop     rbp
0x1800084b5  pop     rbx
0x1800084b6  retn
0x1800084b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800084bc  jmp     loc_1800082D7
0x1800084c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084c8  lea     rax, WPP_GLOBAL_Control
0x1800084cf  cmp     rcx, rax
0x1800084d2  jz      short loc_180008501
0x1800084d4  test    byte ptr [rcx+1Ch], 1
0x1800084d8  jz      short loc_180008501
0x1800084da  mov     rcx, [rcx+10h]
0x1800084de  lea     r8, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids
0x1800084e5  mov     edx, 0Ch
0x1800084ea  call    WPP_SF_
0x1800084ef  jmp     short loc_180008501
0x1800084f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084f8  cmp     rcx, r12
0x1800084fb  jnz     loc_180008895
0x180008501  mov     r15d, 8007000Eh
0x180008507  jmp     loc_18000829D
0x18000850c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008513  lea     rax, WPP_GLOBAL_Control
0x18000851a  cmp     rcx, rax
0x18000851d  jmp     short loc_1800084FB
0x18000851f  test    ebx, ebx
0x180008521  jnz     short loc_18000852E
0x180008523  cmp     eax, 4000h
0x180008528  jz      loc_180008434
0x18000852e  xorps   xmm0, xmm0
0x180008531  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008538  mov     ecx, 7Ch ; '|'; unsigned __int64
0x18000853d  movups  xmmword ptr [rsp+0A8h+SystemTime.wYear], xmm0
0x180008542  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180008547  mov     rbx, rax
0x18000854a  test    rax, rax
0x18000854d  jz      loc_180008434
0x180008553  lea     rcx, [rsp+0A8h+SystemTime]; lpSystemTime
0x180008558  call    cs:__imp_GetSystemTime
0x18000855e  mov     rdx, rbx; pwszTime
0x180008561  lea     rcx, [rsp+0A8h+SystemTime]; pst
  ... truncated ...
```
