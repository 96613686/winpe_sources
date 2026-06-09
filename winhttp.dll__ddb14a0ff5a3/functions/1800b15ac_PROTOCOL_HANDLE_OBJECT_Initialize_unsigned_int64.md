# PROTOCOL_HANDLE_OBJECT::Initialize(unsigned __int64 *)

- ea: `0x1800b15ac`
- end: `0x1800b1792`
- name: `?Initialize@PROTOCOL_HANDLE_OBJECT@@QEAAKPEA_K@Z`
- size: `486`
- prototype: `unsigned int __fastcall(PROTOCOL_HANDLE_OBJECT *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800b1124`

## callees

- `0x180041eb0`
- `0x1800a1d10`
- `0x1800b15ac`
- `0x1800d3a34`
- `0x1800db6b0`
- `0x1800db704`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800b16cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800b16ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800b16cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800b16ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b16dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b16dd`
- `webio!__imp_WebCloseHttpRequest` at `0x1800b173c`
- `webio!__imp_WebCloseHttpRequest` at `0x1800b173c`
- `webio!__imp_WebReceiveHttpResponseEntity` at `0x1800b1689`
- `webio!__imp_WebReceiveHttpResponseEntity` at `0x1800b1689`
- `webio!__imp_WebCompleteProtocolUpgrade` at `0x1800b169e`
- `webio!__imp_WebCompleteProtocolUpgrade` at `0x1800b169e`

## pseudocode

```c
__int64 __fastcall PROTOCOL_HANDLE_OBJECT::Initialize(PROTOCOL_HANDLE_OBJECT *this, unsigned __int64 *a2)
{
  unsigned int v4; // esi
  __int64 v5; // rbp
  __int64 v6; // rcx
  int v7; // eax
  HANDLE EventA; // rax
  HANDLE v9; // rax
  int v10; // eax
  int v11; // edx
  int v12; // ecx
  int v13; // r8d
  unsigned int v14; // eax
  __int64 v16; // [rsp+20h] [rbp-78h]
  __int128 v17; // [rsp+48h] [rbp-50h] BYREF
  __int64 v18; // [rsp+58h] [rbp-40h]
  char v19; // [rsp+60h] [rbp-38h] BYREF
  __int64 v20; // [rsp+68h] [rbp-30h] BYREF

  v20 = 0;
  v17 = 0;
  v18 = 0;
  if ( (xmmword_180107A60 & 2) != 0 )
    WPP_SF_q(1025, 12, WPP_918dff8dee053ecc13ef49af7a3537cb_Traceguids);
  if ( !a2 )
  {
    v4 = -2147024809;
    goto LABEL_19;
  }
  v5 = *a2;
  *a2 = 0;
  v6 = v5;
  if ( *((_DWORD *)this + 10) == 1852731203 )
    goto LABEL_8;
  *((_QWORD *)&v17 + 1) = &v19;
  LODWORD(v17) = 0;
  v18 = 1;
  v7 = WebReceiveHttpResponseEntity(v5, 0, &v17, 1, &v20, 0, 0);
  if ( v7 == 38 )
  {
    v6 = v5;
LABEL_8:
    v7 = WebCompleteProtocolUpgrade(v6, (char *)this + 432);
  }
  if ( v7 )
  {
    v4 = -2147012892;
  }
  else
  {
    v4 = 0;
    if ( *((_DWORD *)this + 35)
      || (EventA = CreateEventA(0, 0, 0, 0), (*((_QWORD *)this + 59) = EventA) != 0)
      && (v9 = CreateEventA(0, 0, 0, 0), (*((_QWORD *)this + 56) = v9) != 0) )
    {
      if ( (xmmword_180107A60 & 2) != 0 )
      {
        v10 = (*(__int64 (__fastcall **)(PROTOCOL_HANDLE_OBJECT *))(*(_QWORD *)this + 8LL))(this);
        WPP_SF_dqi(v12, v11, v13, v10, (__int64)this);
      }
    }
    else
    {
      GetLastError();
    }
  }
  if ( v5 )
    WebCloseHttpRequest(v5, 0);
LABEL_19:
  if ( (xmmword_180107A60 & 2) != 0 )
  {
    v14 = WX_WIN32_FROM_HR(v4);
    WPP_SF_d(1025, 14, WPP_918dff8dee053ecc13ef49af7a3537cb_Traceguids, v14, v16);
  }
  return WX_WIN32_FROM_HR(v4);
}

```

## disassembly

```asm
0x1800b15ac  mov     [rsp+arg_10], rbx
0x1800b15b1  push    rbp
0x1800b15b2  push    rsi
0x1800b15b3  push    rdi
0x1800b15b4  sub     rsp, 80h
0x1800b15bb  mov     rax, cs:__security_cookie
0x1800b15c2  xor     rax, rsp
0x1800b15c5  mov     [rsp+98h+var_28], rax
0x1800b15ca  xorps   xmm0, xmm0
0x1800b15cd  mov     [rsp+98h+var_54], 0
0x1800b15d5  xor     eax, eax
0x1800b15d7  mov     [rsp+98h+var_30], 0
0x1800b15e0  movups  [rsp+98h+var_50], xmm0
0x1800b15e5  mov     [rsp+98h+var_40], rax
0x1800b15ea  mov     rbx, rdx
0x1800b15ed  mov     rdi, rcx
0x1800b15f0  test    byte ptr cs:xmmword_180107A60, 2
0x1800b15f7  jz      short loc_1800B161C
0x1800b15f9  test    rdx, rdx
0x1800b15fc  jz      short loc_1800B1603
0x1800b15fe  mov     r9, [rdx]
0x1800b1601  jmp     short loc_1800B1606
0x1800b1603  xor     r9d, r9d
0x1800b1606  mov     edx, 0Ch
0x1800b160b  lea     r8, WPP_918dff8dee053ecc13ef49af7a3537cb_Traceguids
0x1800b1612  mov     ecx, 401h
0x1800b1617  call    WPP_SF_q
0x1800b161c  test    rbx, rbx
0x1800b161f  jnz     short loc_1800B1633
0x1800b1621  mov     esi, 80070057h
0x1800b1626  mov     [rsp+98h+var_54], 0C6h
0x1800b162e  jmp     loc_1800B1742
0x1800b1633  mov     rbp, [rbx]
0x1800b1636  mov     qword ptr [rbx], 0
0x1800b163d  mov     rcx, rbp
0x1800b1640  cmp     dword ptr [rdi+28h], 6E6E6F43h
0x1800b1647  jz      short loc_1800B1697
0x1800b1649  lea     rax, [rsp+98h+var_38]
0x1800b164e  mov     [rsp+98h+var_68], 0
0x1800b1657  mov     qword ptr [rsp+98h+var_50+8], rax
0x1800b165c  lea     r8, [rsp+98h+var_50]
0x1800b1661  lea     rax, [rsp+98h+var_30]
0x1800b1666  mov     [rsp+98h+var_70], 0
0x1800b166f  mov     r9d, 1
0x1800b1675  mov     [rsp+98h+var_78], rax
0x1800b167a  xor     edx, edx
0x1800b167c  mov     dword ptr [rsp+98h+var_50], 0
0x1800b1684  mov     [rsp+98h+var_40], r9
0x1800b1689  call    cs:__imp_WebReceiveHttpResponseEntity
0x1800b168f  cmp     eax, 26h ; '&'
0x1800b1692  jnz     short loc_1800B16A4
0x1800b1694  mov     rcx, rbp
0x1800b1697  lea     rdx, [rdi+1B0h]
0x1800b169e  call    cs:__imp_WebCompleteProtocolUpgrade
0x1800b16a4  test    eax, eax
0x1800b16a6  jz      short loc_1800B16B7
0x1800b16a8  mov     esi, 80072EE4h
0x1800b16ad  mov     [rsp+98h+var_54], 0EFh
0x1800b16b5  jmp     short loc_1800B1732
0x1800b16b7  xor     esi, esi
0x1800b16b9  cmp     [rdi+8Ch], esi
0x1800b16bf  jnz     short loc_1800B1701
0x1800b16c1  xor     r9d, r9d; lpName
0x1800b16c4  xor     r8d, r8d; bInitialState
0x1800b16c7  xor     edx, edx; bManualReset
0x1800b16c9  xor     ecx, ecx; lpEventAttributes
0x1800b16cb  call    cs:__imp_CreateEventA
0x1800b16d1  mov     [rdi+1D8h], rax
0x1800b16d8  test    rax, rax
0x1800b16db  jnz     short loc_1800B16E5
0x1800b16dd  call    cs:__imp_GetLastError
0x1800b16e3  jmp     short loc_1800B1732
0x1800b16e5  xor     r9d, r9d; lpName
0x1800b16e8  xor     r8d, r8d; bInitialState
0x1800b16eb  xor     edx, edx; bManualReset
0x1800b16ed  xor     ecx, ecx; lpEventAttributes
0x1800b16ef  call    cs:__imp_CreateEventA
0x1800b16f5  mov     [rdi+1C0h], rax
0x1800b16fc  test    rax, rax
0x1800b16ff  jz      short loc_1800B16DD
0x1800b1701  test    byte ptr cs:xmmword_180107A60, 2
0x1800b1708  jz      short loc_1800B1732
0x1800b170a  mov     rax, [rdi]
0x1800b170d  mov     rcx, rdi
0x1800b1710  mov     rbx, [rdi+1B0h]
0x1800b1717  mov     rax, [rax+8]
0x1800b171b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1720  mov     r9d, eax
0x1800b1723  mov     [rsp+98h+var_70], rbx
0x1800b1728  mov     [rsp+98h+var_78], rdi
0x1800b172d  call    WPP_SF_dqi
0x1800b1732  test    rbp, rbp
0x1800b1735  jz      short loc_1800B1742
0x1800b1737  xor     edx, edx
0x1800b1739  mov     rcx, rbp
0x1800b173c  call    cs:__imp_WebCloseHttpRequest
0x1800b1742  test    byte ptr cs:xmmword_180107A60, 2
0x1800b1749  jz      short loc_1800B176B
0x1800b174b  mov     ecx, esi
0x1800b174d  call    WX_WIN32_FROM_HR
0x1800b1752  mov     r9d, eax
0x1800b1755  lea     r8, WPP_918dff8dee053ecc13ef49af7a3537cb_Traceguids
0x1800b175c  mov     edx, 0Eh
0x1800b1761  mov     ecx, 401h
0x1800b1766  call    WPP_SF_d
0x1800b176b  mov     ecx, esi
0x1800b176d  call    WX_WIN32_FROM_HR
0x1800b1772  mov     rcx, [rsp+98h+var_28]
0x1800b1777  xor     rcx, rsp; StackCookie
0x1800b177a  call    __security_check_cookie
0x1800b177f  mov     rbx, [rsp+98h+arg_10]
0x1800b1787  add     rsp, 80h
0x1800b178e  pop     rdi
0x1800b178f  pop     rsi
0x1800b1790  pop     rbp
0x1800b1791  retn
```
