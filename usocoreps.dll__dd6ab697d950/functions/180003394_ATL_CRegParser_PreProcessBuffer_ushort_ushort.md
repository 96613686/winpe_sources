# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180003394`
- end: `0x18000366f`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `731`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800037e8`

## callees

- `0x180001510`
- `0x180002d2c`
- `0x180002f30`
- `0x180003394`
- `0x180004a7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800034d7`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800034d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000350d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000350d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003543`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003543`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000343c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800035f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000343c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800035f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000341e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000341e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003468`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003499`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800035a4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800035cd`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003468`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003499`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800035a4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800035cd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000352b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000352b`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rdx
  WCHAR v12; // ax
  LPWSTR v13; // rax
  WCHAR v14; // cx
  const unsigned __int16 *v15; // rdx
  const WCHAR *v16; // rdi
  __int64 v17; // rax
  int v18; // eax
  LPCWSTR v19; // rsi
  int v20; // ebx
  const unsigned __int16 *v21; // rbx
  __int64 v22; // r8
  const WCHAR *i; // rax
  unsigned int v24; // ebx
  __int64 v25; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v27; // [rsp+30h] [rbp-39h]
  WCHAR String2[32]; // [rsp+40h] [rbp-29h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  if ( v7 < 100 )
    v7 = 1000;
  LODWORD(v25) = 0;
  HIDWORD(v25) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)v8);
    v10 = v9;
    pv = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    v10 = 0;
    pv = 0;
  }
  if ( !v9 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_51:
    v24 = 0;
    pv = 0;
    *a3 = v10;
    goto LABEL_52;
  }
  while ( v12 != 37 )
  {
    v15 = v4;
LABEL_48:
    if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v25, v15, 1) )
      goto LABEL_55;
LABEL_49:
    v4 = CharNextW(*this);
    *this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v10 = (unsigned __int16 *)pv;
      goto LABEL_51;
    }
  }
  v13 = CharNextW(v4);
  *this = v13;
  v14 = *v13;
  if ( *v13 == 37 )
  {
    v15 = v13;
    goto LABEL_48;
  }
  if ( !v13 )
    goto LABEL_54;
  v16 = 0;
  while ( v14 )
  {
    if ( v14 == 37 )
    {
      v16 = v13;
      break;
    }
    v13 = CharNextW(v13);
    v14 = *v13;
  }
  if ( !v16 )
    goto LABEL_54;
  v17 = v16 - *this;
  if ( v17 > 31 )
  {
    v24 = -2147467259;
    goto LABEL_52;
  }
  v18 = _o_wcsncpy_s(String2, 32, *this, (int)v17, v25);
  if ( v18 )
  {
    if ( v18 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v18 == 22 || v18 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v18 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  v19 = this[1];
  EnterCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  v20 = 0;
  if ( *((int *)v19 + 6) <= 0 )
    goto LABEL_34;
  while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), String2) )
  {
    if ( ++v20 >= *((_DWORD *)v19 + 6) )
      goto LABEL_34;
  }
  if ( v20 == -1 )
  {
LABEL_34:
    v21 = 0;
  }
  else
  {
    if ( v20 < 0 || v20 >= *((_DWORD *)v19 + 6) )
    {
      ATL::_AtlRaiseException(0xC000008C);
      __debugbreak();
    }
    v21 = *(const unsigned __int16 **)(*((_QWORD *)v19 + 2) + 8LL * v20);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  if ( !v21 )
  {
LABEL_54:
    v24 = -2147352567;
    goto LABEL_52;
  }
  v27 = 0;
  v22 = -1;
  do
    ++v22;
  while ( v21[v22] );
  if ( (unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v25, v21, v22) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
    goto LABEL_49;
  }
LABEL_55:
  v24 = -2147024882;
LABEL_52:
  CoTaskMemFree(pv);
  return v24;
}

```

## disassembly

```asm
0x180003394  mov     [rsp-8+arg_8], rbx
0x180003399  push    rbp
0x18000339a  push    rsi
0x18000339b  push    rdi
0x18000339c  push    r12
0x18000339e  push    r13
0x1800033a0  push    r14
0x1800033a2  push    r15
0x1800033a4  lea     rbp, [rsp-27h]
0x1800033a9  sub     rsp, 90h
0x1800033b0  mov     rax, cs:__security_cookie
0x1800033b7  xor     rax, rsp
0x1800033ba  mov     [rbp+57h+var_40], rax
0x1800033be  mov     r12, r8
0x1800033c1  mov     rbx, rdx
0x1800033c4  mov     r14, rcx
0x1800033c7  xor     r13d, r13d
0x1800033ca  test    rdx, rdx
0x1800033cd  jz      loc_180003617
0x1800033d3  test    r8, r8
0x1800033d6  jz      loc_180003617
0x1800033dc  mov     [r8], r13
0x1800033df  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800033e3  inc     rax
0x1800033e6  cmp     [rdx+rax*2], r13w
0x1800033eb  jnz     short loc_1800033E3
0x1800033ed  add     eax, eax
0x1800033ef  mov     ecx, 3E8h
0x1800033f4  cmp     eax, 64h ; 'd'
0x1800033f7  cmovl   eax, ecx
0x1800033fa  mov     [rbp+57h+var_A0], r13d
0x1800033fe  mov     [rbp+57h+var_9C], eax
0x180003401  mov     ecx, eax
0x180003403  add     rcx, rcx
0x180003406  mov     eax, 0FFFFFFFFh
0x18000340b  cmp     rcx, rax
0x18000340e  jbe     short loc_18000341C
0x180003410  mov     rax, r13
0x180003413  mov     rdx, r13
0x180003416  mov     [rbp+57h+pv], rdx
0x18000341a  jmp     short loc_180003434
0x18000341c  mov     ecx, ecx; cb
0x18000341e  call    cs:__imp_CoTaskMemAlloc
0x180003424  mov     rdx, rax
0x180003427  mov     [rbp+57h+pv], rax
0x18000342b  test    rax, rax
0x18000342e  jz      short loc_180003434
0x180003430  mov     [rax], r13w
0x180003434  test    rax, rax
0x180003437  jnz     short loc_18000344C
0x180003439  mov     rcx, rax; pv
0x18000343c  call    cs:__imp_CoTaskMemFree
0x180003442  mov     eax, 8007000Eh
0x180003447  jmp     loc_18000361C
0x18000344c  mov     [r14], rbx
0x18000344f  movzx   eax, word ptr [rbx]
0x180003452  test    ax, ax
0x180003455  jz      loc_1800035E9
0x18000345b  cmp     ax, 25h ; '%'
0x18000345f  jnz     loc_1800035B4
0x180003465  mov     rcx, rbx; lpsz
0x180003468  call    cs:__imp_CharNextW
0x18000346e  mov     [r14], rax
0x180003471  movzx   ecx, word ptr [rax]
0x180003474  cmp     cx, 25h ; '%'
0x180003478  jnz     short loc_180003482
0x18000347a  mov     rdx, rax
0x18000347d  jmp     loc_1800035B7
0x180003482  test    rax, rax
0x180003485  jz      loc_180003609
0x18000348b  mov     rdi, r13
0x18000348e  jmp     short loc_1800034A2
0x180003490  cmp     cx, 25h ; '%'
0x180003494  jz      short loc_1800034A9
0x180003496  mov     rcx, rax; lpsz
0x180003499  call    cs:__imp_CharNextW
0x18000349f  movzx   ecx, word ptr [rax]
0x1800034a2  test    cx, cx
0x1800034a5  jnz     short loc_180003490
0x1800034a7  jmp     short loc_1800034AC
0x1800034a9  mov     rdi, rax
0x1800034ac  test    rdi, rdi
0x1800034af  jz      loc_180003609
0x1800034b5  mov     rax, rdi
0x1800034b8  sub     rax, [r14]
0x1800034bb  sar     rax, 1
0x1800034be  cmp     rax, 1Fh
0x1800034c2  jg      loc_180003602
0x1800034c8  movsxd  r9, eax
0x1800034cb  mov     r8, [r14]
0x1800034ce  mov     edx, 20h ; ' '
0x1800034d3  lea     rcx, [rbp+57h+String2]
0x1800034d7  call    cs:__imp__o_wcsncpy_s
0x1800034dd  test    eax, eax
0x1800034df  jz      short loc_180003505
0x1800034e1  cmp     eax, 0Ch
0x1800034e4  jz      loc_180003664
0x1800034ea  cmp     eax, 16h
0x1800034ed  jz      loc_180003659
0x1800034f3  cmp     eax, 22h ; '"'
0x1800034f6  jz      loc_180003659
0x1800034fc  cmp     eax, 50h ; 'P'
0x1800034ff  jnz     loc_18000364E
0x180003505  mov     rsi, [r14+8]
0x180003509  lea     rcx, [rsi+20h]; lpCriticalSection
0x18000350d  call    cs:__imp_EnterCriticalSection
0x180003513  mov     ebx, r13d
0x180003516  cmp     [rsi+18h], r13d
0x18000351a  jle     short loc_18000353C
0x18000351c  movsxd  rax, ebx
0x18000351f  mov     rcx, [rsi+8]
0x180003523  lea     rdx, [rbp+57h+String2]; lpString2
0x180003527  mov     rcx, [rcx+rax*8]; lpString1
0x18000352b  call    cs:__imp_lstrcmpiW
0x180003531  test    eax, eax
0x180003533  jz      short loc_18000357E
0x180003535  inc     ebx
0x180003537  cmp     ebx, [rsi+18h]
0x18000353a  jl      short loc_18000351C
0x18000353c  mov     rbx, r13
0x18000353f  lea     rcx, [rsi+20h]; lpCriticalSection
0x180003543  call    cs:__imp_LeaveCriticalSection
0x180003549  test    rbx, rbx
0x18000354c  jz      loc_180003609
0x180003552  mov     [rbp+57h+var_90], r13
0x180003556  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000355a  inc     r8; int
0x18000355d  cmp     [rbx+r8*2], r13w
0x180003562  jnz     short loc_18000355A
0x180003564  mov     rdx, rbx; unsigned __int16 *
0x180003567  lea     rcx, [rbp+57h+var_A0]; this
0x18000356b  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180003570  nop
0x180003571  test    eax, eax
0x180003573  jz      loc_180003610
0x180003579  mov     rax, [r14]
0x18000357c  jmp     short loc_1800035AD
0x18000357e  cmp     ebx, 0FFFFFFFFh
0x180003581  jz      short loc_18000353C
0x180003583  test    ebx, ebx
0x180003585  js      loc_180003643
0x18000358b  cmp     ebx, [rsi+18h]
0x18000358e  jge     loc_180003643
0x180003594  movsxd  rcx, ebx
0x180003597  mov     rax, [rsi+10h]
0x18000359b  mov     rbx, [rax+rcx*8]
0x18000359f  jmp     short loc_18000353F
0x1800035a1  mov     rcx, rax; lpsz
0x1800035a4  call    cs:__imp_CharNextW
0x1800035aa  mov     [r14], rax
0x1800035ad  cmp     rax, rdi
0x1800035b0  jnz     short loc_1800035A1
0x1800035b2  jmp     short loc_1800035CA
0x1800035b4  mov     rdx, rbx; unsigned __int16 *
0x1800035b7  mov     r8d, 1; int
0x1800035bd  lea     rcx, [rbp+57h+var_A0]; this
0x1800035c1  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800035c6  test    eax, eax
0x1800035c8  jz      short loc_180003610
0x1800035ca  mov     rcx, [r14]; lpsz
0x1800035cd  call    cs:__imp_CharNextW
0x1800035d3  mov     rbx, rax
0x1800035d6  mov     [r14], rax
0x1800035d9  movzx   eax, word ptr [rax]
0x1800035dc  test    ax, ax
0x1800035df  jnz     loc_18000345B
0x1800035e5  mov     rdx, [rbp+57h+pv]
0x1800035e9  mov     ebx, r13d
0x1800035ec  mov     [rbp+57h+pv], r13
0x1800035f0  mov     [r12], rdx
0x1800035f4  mov     rcx, [rbp+57h+pv]; pv
0x1800035f8  call    cs:__imp_CoTaskMemFree
0x1800035fe  mov     eax, ebx
0x180003600  jmp     short loc_18000361C
0x180003602  mov     ebx, 80004005h
0x180003607  jmp     short loc_1800035F4
0x180003609  mov     ebx, 80020009h
0x18000360e  jmp     short loc_1800035F4
0x180003610  mov     ebx, 8007000Eh
0x180003615  jmp     short loc_1800035F4
0x180003617  mov     eax, 80004003h
0x18000361c  mov     rcx, [rbp+57h+var_40]
0x180003620  xor     rcx, rsp; StackCookie
0x180003623  call    __security_check_cookie
0x180003628  mov     rbx, [rsp+0C0h+arg_8]
0x180003630  add     rsp, 90h
0x180003637  pop     r15
0x180003639  pop     r14
0x18000363b  pop     r13
0x18000363d  pop     r12
0x18000363f  pop     rdi
0x180003640  pop     rsi
0x180003641  pop     rbp
0x180003642  retn
0x180003643  mov     ecx, 0C000008Ch; unsigned int
0x180003648  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000364d  int     3; Trap to Debugger
0x18000364e  mov     ecx, 80004005h; int
0x180003653  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003659  mov     ecx, 80070057h; int
0x18000365e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003664  mov     ecx, 8007000Eh; int
0x180003669  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
