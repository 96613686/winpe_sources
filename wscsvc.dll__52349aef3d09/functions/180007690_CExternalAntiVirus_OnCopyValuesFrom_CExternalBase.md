# CExternalAntiVirus::OnCopyValuesFrom(CExternalBase *)

- ea: `0x180007690`
- end: `0x180007c44`
- name: `?OnCopyValuesFrom@CExternalAntiVirus@@MEAAJPEAVCExternalBase@@@Z`
- size: `1460`
- prototype: `__int64 __fastcall(struct _FILETIME *this, struct CExternalBase *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x18000760c`
- `0x180007690`
- `0x1800088b0`
- `0x180008b80`
- `0x180008e48`
- `0x180029e74`
- `0x18002b1ac`
- `0x18003fc30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b5a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180007913`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180007961`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180007913`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180007961`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180007938`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180007982`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180007938`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180007982`
- `WINHTTP!WinHttpTimeFromSystemTime` at `0x180007921`
- `WINHTTP!WinHttpTimeFromSystemTime` at `0x18000796f`
- `WINHTTP!WinHttpTimeFromSystemTime` at `0x180007921`
- `WINHTTP!WinHttpTimeFromSystemTime` at `0x18000796f`
- `WINHTTP!WinHttpTimeToSystemTime` at `0x180007af2`
- `WINHTTP!WinHttpTimeToSystemTime` at `0x180007af2`

## pseudocode

```c
__int64 __fastcall CExternalAntiVirus::OnCopyValuesFrom(struct _FILETIME *this, struct CExternalBase *a2)
{
  unsigned int v4; // edi
  CThirdPartyManager *v5; // r10
  DWORD dwLowDateTime; // eax
  unsigned int v7; // ebp
  unsigned int v8; // esi
  int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // esi
  unsigned int v12; // ecx
  DWORD v13; // eax
  unsigned int v14; // ecx
  unsigned int v15; // eax
  unsigned int v16; // eax
  _WORD *v17; // rbx
  _WORD *v18; // rdi
  __int64 v19; // rax
  __int64 v20; // rdx
  _WORD *v21; // r8
  _WORD *v22; // rcx
  void *v24; // rsi
  void *v25; // rcx
  BOOL v26; // eax
  void *v27; // rcx
  struct _SYSTEMTIME SystemTime; // [rsp+20h] [rbp-48h] BYREF

  if ( a2 )
  {
    v4 = this[10].dwLowDateTime & 0xF000;
    if ( v4 == 4096 || v4 == 0x2000 || !v4 || v4 == 20480 || v4 == 12288 || v4 == 0x4000 || v4 == 0x8000 )
    {
      v5 = WPP_GLOBAL_Control;
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids, v4);
        v5 = WPP_GLOBAL_Control;
      }
      v4 = 0;
    }
    dwLowDateTime = this[10].dwLowDateTime;
    v7 = dwLowDateTime & 0xF00000;
    if ( (dwLowDateTime & 0xC00000) != 0 )
    {
      if ( v5 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)v5 + 2), 14, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids, v7);
        dwLowDateTime = this[10].dwLowDateTime;
        v5 = WPP_GLOBAL_Control;
      }
      v7 = 0;
    }
    v8 = *((_DWORD *)a2 + 20) & 0xF000;
    if ( v8 != 4096 && v8 != 0x2000 && v8 && v8 != 20480 && v8 != 12288 && v8 != 0x4000 && v8 != 0x8000 )
    {
      if ( v5 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)v5 + 2), 12, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids, v8);
        dwLowDateTime = this[10].dwLowDateTime;
        v5 = WPP_GLOBAL_Control;
      }
      v8 = 0;
    }
    v9 = dwLowDateTime & 0xF000;
    if ( v9 != 4096
      && v9 != 0x2000
      && (dwLowDateTime & 0xF000) != 0
      && v9 != 20480
      && v9 != 12288
      && v9 != 0x4000
      && v9 != 0x8000 )
    {
      if ( v5 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)v5 + 2), 12, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids, dwLowDateTime & 0xF000);
        dwLowDateTime = this[10].dwLowDateTime;
      }
      v9 = 0;
    }
    this[10].dwLowDateTime = v8 | dwLowDateTime & 0xFFFF0FFF;
    if ( v9 != v8 && (v8 || v9 != 0x4000) )
    {
      SystemTime = 0;
      v24 = operator new[](0x7Cu, (const struct std::nothrow_t *)&std::nothrow);
      if ( v24 )
      {
        GetSystemTime(&SystemTime);
        if ( WinHttpTimeFromSystemTime(&SystemTime, (LPWSTR)v24) && SystemTimeToFileTime(&SystemTime, this + 8) )
        {
          v25 = (void *)this[9];
          if ( v25 )
            operator delete(v25);
          this[9] = (struct _FILETIME)v24;
        }
        else
        {
          GetLastError();
          operator delete(v24);
        }
      }
    }
    v10 = this[10].dwLowDateTime & 0xFFFFFF0F | *((_DWORD *)a2 + 20) & 0x10;
    this[10].dwLowDateTime = v10;
    v11 = *((_DWORD *)a2 + 20) & 0xF00;
    if ( (*((_DWORD *)a2 + 20) & 0xE00) != 0 )
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids, v11);
        v10 = this[10].dwLowDateTime;
      }
      v11 = 0;
    }
    ExtractProductOwner(v10);
    v12 = v11 | this[10].dwLowDateTime & 0xFFFFF0FF;
    this[10].dwLowDateTime = v12;
    this[10].dwLowDateTime = v12 ^ (*((_DWORD *)a2 + 20) ^ v12) & 0xF0000;
    this[10].dwHighDateTime = *((_DWORD *)a2 + 21);
    this[11].dwLowDateTime = *((_DWORD *)a2 + 22);
    this[11].dwHighDateTime = *((_DWORD *)a2 + 23);
    v13 = *((_DWORD *)a2 + 27);
    if ( this[13].dwHighDateTime != v13 )
      this[13].dwHighDateTime = v13;
    if ( v4 != 0x4000 || (unsigned int)CExternalBase::GetProductState((__int64)this) )
    {
      v14 = *((_DWORD *)a2 + 20) & 0xF00000;
      if ( (*((_DWORD *)a2 + 20) & 0xC00000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids, v14);
        }
        v14 = 0;
      }
      v15 = v14 | this[10].dwLowDateTime & 0xFF0FFFFF;
    }
    else
    {
      v15 = v7 | this[10].dwLowDateTime & 0xFF0FFFFF;
    }
    this[10].dwLowDateTime = v15;
    if ( !*(_QWORD *)&this[9] )
      goto LABEL_51;
    v16 = v15 & 0xF000;
    if ( v16 != 4096 && v16 != 0x2000 && v16 && v16 != 20480 && v16 != 12288 && v16 != 0x4000 && v16 != 0x8000 )
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids, v16);
      }
      v16 = 0;
    }
    if ( v4 != v16 )
    {
LABEL_51:
      CExternalBase::SetTimestamp((CExternalBase *)this, *((const unsigned __int16 **)a2 + 9));
      return 0;
    }
    v17 = (_WORD *)this[9];
    SystemTime = 0;
    v18 = operator new[](0x7Cu, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v18 )
      return 0;
    if ( v17 )
    {
      v19 = 2147483646;
      v20 = 62;
      v21 = v18;
      do
      {
        if ( !v19 )
          break;
        if ( !*v17 )
          break;
        *v21++ = *v17++;
        --v19;
        --v20;
      }
      while ( v20 );
      v22 = v21 - 1;
      if ( v20 )
        v22 = v21;
      *v22 = 0;
      if ( !v20 )
      {
LABEL_34:
        operator delete(v18);
        return 0;
      }
      v26 = WinHttpTimeToSystemTime(v18, &SystemTime);
    }
    else
    {
      GetSystemTime(&SystemTime);
      v26 = WinHttpTimeFromSystemTime(&SystemTime, v18);
    }
    if ( v26 && SystemTimeToFileTime(&SystemTime, (LPFILETIME)a2 + 8) )
    {
      v27 = (void *)*((_QWORD *)a2 + 9);
      if ( v27 )
        operator delete(v27);
      *((_QWORD *)a2 + 9) = v18;
      return 0;
    }
    GetLastError();
    goto LABEL_34;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180007690  mov     r11, rsp
0x180007693  push    rbx
0x180007694  push    r14
0x180007696  sub     rsp, 58h
0x18000769a  mov     rax, cs:__security_cookie
0x1800076a1  xor     rax, rsp
0x1800076a4  mov     [rsp+68h+var_38], rax
0x1800076a9  mov     r14, rdx
0x1800076ac  mov     rbx, rcx
0x1800076af  test    rdx, rdx
0x1800076b2  jz      loc_180007B77
0x1800076b8  mov     [r11+18h], rbp
0x1800076bc  mov     [r11-18h], rsi
0x1800076c0  mov     [r11-20h], rdi
0x1800076c4  mov     edi, [rcx+50h]
0x1800076c7  and     edi, 0F000h
0x1800076cd  mov     [r11-28h], r15
0x1800076d1  lea     r15, WPP_GLOBAL_Control
0x1800076d8  cmp     edi, 1000h
0x1800076de  jz      short loc_1800076F0
0x1800076e0  cmp     edi, 2000h
0x1800076e6  jz      short loc_1800076F0
0x1800076e8  test    edi, edi
0x1800076ea  jnz     loc_1800079BE
0x1800076f0  mov     r10, cs:WPP_GLOBAL_Control
0x1800076f7  mov     eax, [rbx+50h]
0x1800076fa  mov     ebp, eax
0x1800076fc  and     ebp, 0F00000h
0x180007702  test    ebp, 0FFCFFFFFh
0x180007708  jnz     loc_180007B8B
0x18000770e  mov     esi, [r14+50h]
0x180007712  and     esi, 0F000h
0x180007718  cmp     esi, 1000h
0x18000771e  jz      short loc_180007730
0x180007720  cmp     esi, 2000h
0x180007726  jz      short loc_180007730
0x180007728  test    esi, esi
0x18000772a  jnz     loc_180007A27
0x180007730  mov     ecx, eax
0x180007732  and     ecx, 0F000h
0x180007738  cmp     ecx, 1000h
0x18000773e  jz      short loc_180007750
0x180007740  cmp     ecx, 2000h
0x180007746  jz      short loc_180007750
0x180007748  test    ecx, ecx
0x18000774a  jnz     loc_180007A8C
0x180007750  and     eax, 0FFFF0FFFh
0x180007755  or      eax, esi
0x180007757  mov     [rbx+50h], eax
0x18000775a  cmp     ecx, esi
0x18000775c  jnz     loc_1800078D9
0x180007762  mov     ecx, [r14+50h]
0x180007766  mov     eax, [rbx+50h]
0x180007769  and     ecx, 10h
0x18000776c  and     eax, 0FFFFFF0Fh
0x180007771  or      ecx, eax
0x180007773  mov     [rbx+50h], ecx
0x180007776  mov     esi, [r14+50h]
0x18000777a  and     esi, 0F00h
0x180007780  test    esi, 0FFFFFEFFh
0x180007786  jnz     loc_180007BC0
0x18000778c  call    ?ExtractProductOwner@@YA?AW4ProductOwner@@K@Z; ExtractProductOwner(ulong)
0x180007791  mov     ecx, [rbx+50h]
0x180007794  and     ecx, 0FFFFF0FFh
0x18000779a  or      ecx, esi
0x18000779c  mov     rsi, [rsp+68h+var_18]
0x1800077a1  mov     [rbx+50h], ecx
0x1800077a4  mov     eax, ecx
0x1800077a6  xor     eax, [r14+50h]
0x1800077aa  and     eax, 0F0000h
0x1800077af  xor     eax, ecx
0x1800077b1  mov     [rbx+50h], eax
0x1800077b4  mov     eax, [r14+54h]
0x1800077b8  mov     [rbx+54h], eax
0x1800077bb  mov     eax, [r14+58h]
0x1800077bf  mov     [rbx+58h], eax
0x1800077c2  mov     eax, [r14+5Ch]
0x1800077c6  mov     [rbx+5Ch], eax
0x1800077c9  mov     eax, [r14+6Ch]
0x1800077cd  cmp     [rbx+6Ch], eax
0x1800077d0  jz      short loc_1800077D5
0x1800077d2  mov     [rbx+6Ch], eax
0x1800077d5  cmp     edi, 4000h
0x1800077db  jz      loc_180007BF4
0x1800077e1  mov     ecx, [r14+50h]
0x1800077e5  and     ecx, 0F00000h
0x1800077eb  test    ecx, 0FFCFFFFFh
0x1800077f1  jnz     loc_180007C13
0x1800077f7  mov     eax, [rbx+50h]
0x1800077fa  and     eax, 0FF0FFFFFh
0x1800077ff  or      eax, ecx
0x180007801  mov     [rbx+50h], eax
0x180007804  cmp     qword ptr [rbx+48h], 0
0x180007809  mov     rbp, [rsp+68h+arg_10]
0x180007811  jz      loc_1800079AD
0x180007817  and     eax, 0F000h
0x18000781c  cmp     eax, 1000h
0x180007821  jz      short loc_180007832
0x180007823  cmp     eax, 2000h
0x180007828  jz      short loc_180007832
0x18000782a  test    eax, eax
0x18000782c  jnz     loc_180007AFD
0x180007832  cmp     edi, eax
0x180007834  jnz     loc_1800079AD
0x18000783a  mov     rbx, [rbx+48h]
0x18000783e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007845  xorps   xmm0, xmm0
0x180007848  mov     ecx, 7Ch ; '|'; unsigned __int64
0x18000784d  movups  xmmword ptr [rsp+68h+SystemTime.wYear], xmm0
0x180007852  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007857  mov     rdi, rax
0x18000785a  test    rax, rax
0x18000785d  jz      short loc_1800078B8
0x18000785f  test    rbx, rbx
0x180007862  jz      loc_18000795C
0x180007868  mov     eax, 7FFFFFFEh
0x18000786d  mov     edx, 3Eh ; '>'
0x180007872  mov     r8, rdi
0x180007875  test    rax, rax
0x180007878  jz      short loc_180007897
0x18000787a  movzx   ecx, word ptr [rbx]
0x18000787d  test    cx, cx
0x180007880  jz      short loc_180007897
0x180007882  mov     [r8], cx
0x180007886  add     rbx, 2
0x18000788a  add     r8, 2
0x18000788e  dec     rax
0x180007891  sub     rdx, 1
0x180007895  jnz     short loc_180007875
0x180007897  test    rdx, rdx
0x18000789a  lea     rcx, [r8-2]
0x18000789e  cmovnz  rcx, r8
0x1800078a2  xor     eax, eax
0x1800078a4  mov     [rcx], ax
0x1800078a7  test    rdx, rdx
0x1800078aa  jnz     loc_180007AEA
0x1800078b0  mov     rcx, rdi; Block
0x1800078b3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800078b8  mov     r15, [rsp+68h+var_28]
0x1800078bd  xor     eax, eax
0x1800078bf  mov     rdi, [rsp+68h+var_20]
0x1800078c4  mov     rcx, [rsp+68h+var_38]
0x1800078c9  xor     rcx, rsp; StackCookie
0x1800078cc  call    __security_check_cookie
0x1800078d1  add     rsp, 58h
0x1800078d5  pop     r14
0x1800078d7  pop     rbx
0x1800078d8  retn
0x1800078d9  test    esi, esi
0x1800078db  jnz     short loc_1800078E9
0x1800078dd  cmp     ecx, 4000h
0x1800078e3  jz      loc_180007762
0x1800078e9  xorps   xmm0, xmm0
0x1800078ec  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800078f3  mov     ecx, 7Ch ; '|'; unsigned __int64
0x1800078f8  movups  xmmword ptr [rsp+68h+SystemTime.wYear], xmm0
0x1800078fd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007902  mov     rsi, rax
0x180007905  test    rax, rax
0x180007908  jz      loc_180007762
0x18000790e  lea     rcx, [rsp+68h+SystemTime]; lpSystemTime
0x180007913  call    cs:__imp_GetSystemTime
0x180007919  mov     rdx, rsi; pwszTime
0x18000791c  lea     rcx, [rsp+68h+SystemTime]; pst
0x180007921  call    cs:__imp_WinHttpTimeFromSystemTime
0x180007927  test    eax, eax
0x180007929  jz      loc_180007B5A
0x18000792f  lea     rdx, [rbx+40h]; lpFileTime
0x180007933  lea     rcx, [rsp+68h+SystemTime]; lpSystemTime
0x180007938  call    cs:__imp_SystemTimeToFileTime
0x18000793e  test    eax, eax
0x180007940  jz      loc_180007B5A
0x180007946  mov     rcx, [rbx+48h]; Block
0x18000794a  test    rcx, rcx
0x18000794d  jnz     loc_180007B81
0x180007953  mov     [rbx+48h], rsi
0x180007957  jmp     loc_180007762
0x18000795c  lea     rcx, [rsp+68h+SystemTime]; lpSystemTime
0x180007961  call    cs:__imp_GetSystemTime
0x180007967  mov     rdx, rdi; pwszTime
0x18000796a  lea     rcx, [rsp+68h+SystemTime]; pst
0x18000796f  call    cs:__imp_WinHttpTimeFromSystemTime
0x180007975  test    eax, eax
0x180007977  jz      short loc_1800079A2
0x180007979  lea     rdx, [r14+40h]; lpFileTime
0x18000797d  lea     rcx, [rsp+68h+SystemTime]; lpSystemTime
0x180007982  call    cs:__imp_SystemTimeToFileTime
0x180007988  test    eax, eax
0x18000798a  jz      short loc_1800079A2
0x18000798c  mov     rcx, [r14+48h]; Block
0x180007990  test    rcx, rcx
0x180007993  jnz     loc_180007B6D
0x180007999  mov     [r14+48h], rdi
0x18000799d  jmp     loc_1800078B8
0x1800079a2  call    cs:__imp_GetLastError
0x1800079a8  jmp     loc_1800078B0
0x1800079ad  mov     rdx, [r14+48h]; unsigned __int16 *
0x1800079b1  mov     rcx, rbx; this
0x1800079b4  call    ?SetTimestamp@CExternalBase@@QEAAJPEBG@Z; CExternalBase::SetTimestamp(ushort const *)
0x1800079b9  jmp     loc_1800078B8
0x1800079be  cmp     edi, 5000h
0x1800079c4  jz      loc_1800076F0
0x1800079ca  cmp     edi, 3000h
0x1800079d0  jz      loc_1800076F0
0x1800079d6  cmp     edi, 4000h
0x1800079dc  jz      loc_1800076F0
0x1800079e2  cmp     edi, 8000h
0x1800079e8  jz      loc_1800076F0
0x1800079ee  mov     r10, cs:WPP_GLOBAL_Control
0x1800079f5  cmp     r10, r15
0x1800079f8  jz      short loc_180007A20
0x1800079fa  test    byte ptr [r10+1Ch], 1
0x1800079ff  jz      short loc_180007A20
0x180007a01  mov     rcx, [r10+10h]
0x180007a05  lea     r8, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids
0x180007a0c  mov     edx, 0Ch
0x180007a11  mov     r9d, edi
0x180007a14  call    WPP_SF_d
0x180007a19  mov     r10, cs:WPP_GLOBAL_Control
0x180007a20  xor     edi, edi
0x180007a22  jmp     loc_1800076F7
0x180007a27  cmp     esi, 5000h
0x180007a2d  jz      loc_180007730
0x180007a33  cmp     esi, 3000h
0x180007a39  jz      loc_180007730
0x180007a3f  cmp     esi, 4000h
0x180007a45  jz      loc_180007730
0x180007a4b  cmp     esi, 8000h
0x180007a51  jz      loc_180007730
0x180007a57  cmp     r10, r15
0x180007a5a  jz      short loc_180007A85
0x180007a5c  test    byte ptr [r10+1Ch], 1
0x180007a61  jz      short loc_180007A85
0x180007a63  mov     rcx, [r10+10h]
0x180007a67  lea     r8, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids
0x180007a6e  mov     edx, 0Ch
0x180007a73  mov     r9d, esi
0x180007a76  call    WPP_SF_d
0x180007a7b  mov     eax, [rbx+50h]
0x180007a7e  mov     r10, cs:WPP_GLOBAL_Control
0x180007a85  xor     esi, esi
0x180007a87  jmp     loc_180007730
0x180007a8c  cmp     ecx, 5000h
0x180007a92  jz      loc_180007750
0x180007a98  cmp     ecx, 3000h
0x180007a9e  jz      loc_180007750
0x180007aa4  cmp     ecx, 4000h
0x180007aaa  jz      loc_180007750
0x180007ab0  cmp     ecx, 8000h
0x180007ab6  jz      loc_180007750
0x180007abc  cmp     r10, r15
0x180007abf  jz      short loc_180007AE3
0x180007ac1  test    byte ptr [r10+1Ch], 1
0x180007ac6  jz      short loc_180007AE3
0x180007ac8  mov     r9d, ecx
0x180007acb  lea     r8, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids
0x180007ad2  mov     rcx, [r10+10h]
0x180007ad6  mov     edx, 0Ch
0x180007adb  call    WPP_SF_d
0x180007ae0  mov     eax, [rbx+50h]
0x180007ae3  xor     ecx, ecx
0x180007ae5  jmp     loc_180007750
0x180007aea  lea     rdx, [rsp+68h+SystemTime]; pst
0x180007aef  mov     rcx, rdi; pwszTime
0x180007af2  call    cs:__imp_WinHttpTimeToSystemTime
0x180007af8  jmp     loc_180007975
0x180007afd  cmp     eax, 5000h
0x180007b02  jz      loc_180007832
0x180007b08  cmp     eax, 3000h
0x180007b0d  jz      loc_180007832
0x180007b13  cmp     eax, 4000h
0x180007b18  jz      loc_180007832
0x180007b1e  cmp     eax, 8000h
0x180007b23  jz      loc_180007832
0x180007b29  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b30  cmp     rcx, r15
0x180007b33  jz      short loc_180007B53
0x180007b35  test    byte ptr [rcx+1Ch], 1
0x180007b39  jz      short loc_180007B53
0x180007b3b  mov     rcx, [rcx+10h]
0x180007b3f  lea     r8, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids
0x180007b46  mov     edx, 0Ch
0x180007b4b  mov     r9d, eax
0x180007b4e  call    WPP_SF_d
0x180007b53  xor     eax, eax
0x180007b55  jmp     loc_180007832
0x180007b5a  call    cs:__imp_GetLastError
0x180007b60  mov     rcx, rsi; Block
0x180007b63  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007b68  jmp     loc_180007762
0x180007b6d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007b72  jmp     loc_180007999
0x180007b77  mov     eax, 80070057h
0x180007b7c  jmp     loc_1800078C4
0x180007b81  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007b86  jmp     loc_180007953
0x180007b8b  cmp     r10, r15
0x180007b8e  jz      short loc_180007BB9
0x180007b90  test    byte ptr [r10+1Ch], 1
0x180007b95  jz      short loc_180007BB9
  ... truncated ...
```
