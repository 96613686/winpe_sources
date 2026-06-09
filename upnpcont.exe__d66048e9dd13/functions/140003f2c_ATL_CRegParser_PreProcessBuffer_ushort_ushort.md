# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x140003f2c`
- end: `0x1400041fa`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `718`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400043a8`

## callees

- `0x140001490`
- `0x14000295c`
- `0x140003298`
- `0x140003f2c`
- `0x140005b9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140004060`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140004060`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400040cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400040cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140004096`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140004096`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140003fbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140003fbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140003fab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004181`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140003fab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004181`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140003ff0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140004021`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000412a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140004154`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140003ff0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140004021`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000412a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140004154`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1400040b5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1400040b5`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  void *v9; // rcx
  _WORD *v11; // rax
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
  __int64 v25; // [rsp+20h] [rbp-88h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-80h]
  WCHAR String2[32]; // [rsp+30h] [rbp-78h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  LODWORD(v25) = 0;
  if ( v7 < 100 )
    v7 = 1000;
  HIDWORD(v25) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 > 0xFFFFFFFF )
  {
    v9 = 0;
LABEL_9:
    CoTaskMemFree(v9);
    return 2147942414LL;
  }
  v11 = CoTaskMemAlloc((unsigned int)v8);
  pv = v11;
  v9 = v11;
  if ( !v11 )
    goto LABEL_9;
  *v11 = 0;
  *this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_49:
    v24 = 0;
    pv = 0;
    *a3 = (unsigned __int16 *)v9;
    goto LABEL_50;
  }
  while ( v12 != 37 )
  {
    v15 = v4;
LABEL_46:
    if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v25, v15, 1) )
      goto LABEL_53;
LABEL_47:
    v4 = CharNextW(*this);
    *this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v9 = pv;
      goto LABEL_49;
    }
  }
  v13 = CharNextW(v4);
  *this = v13;
  v14 = *v13;
  if ( *v13 == 37 )
  {
    v15 = v13;
    goto LABEL_46;
  }
  if ( !v13 )
    goto LABEL_52;
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
    goto LABEL_52;
  v17 = v16 - *this;
  if ( v17 > 31 )
  {
    v24 = -2147467259;
    goto LABEL_50;
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
    goto LABEL_32;
  while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), String2) )
  {
    if ( ++v20 >= *((_DWORD *)v19 + 6) )
      goto LABEL_32;
  }
  if ( v20 == -1 )
  {
LABEL_32:
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
LABEL_52:
    v24 = -2147352567;
    goto LABEL_50;
  }
  v22 = -1;
  do
    ++v22;
  while ( v21[v22] );
  if ( (unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v25, v21, v22) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
    goto LABEL_47;
  }
LABEL_53:
  v24 = -2147024882;
LABEL_50:
  CoTaskMemFree(pv);
  return v24;
}

```

## disassembly

```asm
0x140003f2c  mov     [rsp+arg_8], rbx
0x140003f31  mov     [rsp+arg_18], rbp
0x140003f36  push    rsi
0x140003f37  push    rdi
0x140003f38  push    r12
0x140003f3a  push    r14
0x140003f3c  push    r15
0x140003f3e  sub     rsp, 80h
0x140003f45  mov     rax, cs:__security_cookie
0x140003f4c  xor     rax, rsp
0x140003f4f  mov     [rsp+0A8h+var_38], rax
0x140003f54  xor     r12d, r12d
0x140003f57  mov     r15, r8
0x140003f5a  mov     rbx, rdx
0x140003f5d  mov     r14, rcx
0x140003f60  test    rdx, rdx
0x140003f63  jz      loc_1400041A0
0x140003f69  test    r8, r8
0x140003f6c  jz      loc_1400041A0
0x140003f72  mov     [r8], r12
0x140003f75  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003f79  inc     rax
0x140003f7c  cmp     [rdx+rax*2], r12w
0x140003f81  jnz     short loc_140003F79
0x140003f83  add     eax, eax
0x140003f85  mov     [rsp+0A8h+var_88], r12d
0x140003f8a  cmp     eax, 64h ; 'd'
0x140003f8d  mov     ecx, 3E8h
0x140003f92  cmovl   eax, ecx
0x140003f95  mov     ecx, eax
0x140003f97  mov     [rsp+0A8h+var_84], eax
0x140003f9b  add     rcx, rcx
0x140003f9e  mov     eax, 0FFFFFFFFh
0x140003fa3  cmp     rcx, rax
0x140003fa6  jbe     short loc_140003FBB
0x140003fa8  mov     rcx, r12; pv
0x140003fab  call    cs:__imp_CoTaskMemFree
0x140003fb1  mov     eax, 8007000Eh
0x140003fb6  jmp     loc_1400041A5
0x140003fbb  mov     ecx, ecx; cb
0x140003fbd  call    cs:__imp_CoTaskMemAlloc
0x140003fc3  mov     [rsp+0A8h+pv], rax
0x140003fc8  mov     rcx, rax
0x140003fcb  test    rax, rax
0x140003fce  jz      short loc_140003FAB
0x140003fd0  mov     [rax], r12w
0x140003fd4  mov     [r14], rbx
0x140003fd7  movzx   eax, word ptr [rbx]
0x140003fda  test    ax, ax
0x140003fdd  jz      loc_140004171
0x140003fe3  cmp     ax, 25h ; '%'
0x140003fe7  jnz     loc_14000413A
0x140003fed  mov     rcx, rbx; lpsz
0x140003ff0  call    cs:__imp_CharNextW
0x140003ff6  mov     [r14], rax
0x140003ff9  movzx   ecx, word ptr [rax]
0x140003ffc  cmp     cx, 25h ; '%'
0x140004000  jnz     short loc_14000400A
0x140004002  mov     rdx, rax
0x140004005  jmp     loc_14000413D
0x14000400a  test    rax, rax
0x14000400d  jz      loc_140004192
0x140004013  mov     rdi, r12
0x140004016  jmp     short loc_14000402A
0x140004018  cmp     cx, 25h ; '%'
0x14000401c  jz      short loc_140004031
0x14000401e  mov     rcx, rax; lpsz
0x140004021  call    cs:__imp_CharNextW
0x140004027  movzx   ecx, word ptr [rax]
0x14000402a  test    cx, cx
0x14000402d  jnz     short loc_140004018
0x14000402f  jmp     short loc_140004034
0x140004031  mov     rdi, rax
0x140004034  test    rdi, rdi
0x140004037  jz      loc_140004192
0x14000403d  mov     rax, rdi
0x140004040  sub     rax, [r14]
0x140004043  sar     rax, 1
0x140004046  cmp     rax, 1Fh
0x14000404a  jg      loc_14000418B
0x140004050  mov     r8, [r14]
0x140004053  lea     rcx, [rsp+0A8h+String2]
0x140004058  movsxd  r9, eax
0x14000405b  mov     edx, 20h ; ' '
0x140004060  call    cs:__imp__o_wcsncpy_s
0x140004066  test    eax, eax
0x140004068  jz      short loc_14000408E
0x14000406a  cmp     eax, 0Ch
0x14000406d  jz      loc_1400041EF
0x140004073  cmp     eax, 16h
0x140004076  jz      loc_1400041E4
0x14000407c  cmp     eax, 22h ; '"'
0x14000407f  jz      loc_1400041E4
0x140004085  cmp     eax, 50h ; 'P'
0x140004088  jnz     loc_1400041D9
0x14000408e  mov     rsi, [r14+8]
0x140004092  lea     rcx, [rsi+20h]; lpCriticalSection
0x140004096  call    cs:__imp_EnterCriticalSection
0x14000409c  mov     ebx, r12d
0x14000409f  cmp     [rsi+18h], r12d
0x1400040a3  jle     short loc_1400040C6
0x1400040a5  mov     rcx, [rsi+8]
0x1400040a9  lea     rdx, [rsp+0A8h+String2]; lpString2
0x1400040ae  movsxd  rax, ebx
0x1400040b1  mov     rcx, [rcx+rax*8]; lpString1
0x1400040b5  call    cs:__imp_lstrcmpiW
0x1400040bb  test    eax, eax
0x1400040bd  jz      short loc_140004104
0x1400040bf  inc     ebx
0x1400040c1  cmp     ebx, [rsi+18h]
0x1400040c4  jl      short loc_1400040A5
0x1400040c6  mov     rbx, r12
0x1400040c9  lea     rcx, [rsi+20h]; lpCriticalSection
0x1400040cd  call    cs:__imp_LeaveCriticalSection
0x1400040d3  test    rbx, rbx
0x1400040d6  jz      loc_140004192
0x1400040dc  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400040e0  inc     r8; int
0x1400040e3  cmp     [rbx+r8*2], r12w
0x1400040e8  jnz     short loc_1400040E0
0x1400040ea  mov     rdx, rbx; unsigned __int16 *
0x1400040ed  lea     rcx, [rsp+0A8h+var_88]; this
0x1400040f2  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1400040f7  test    eax, eax
0x1400040f9  jz      loc_140004199
0x1400040ff  mov     rax, [r14]
0x140004102  jmp     short loc_140004133
0x140004104  cmp     ebx, 0FFFFFFFFh
0x140004107  jz      short loc_1400040C6
0x140004109  test    ebx, ebx
0x14000410b  js      loc_1400041CE
0x140004111  cmp     ebx, [rsi+18h]
0x140004114  jge     loc_1400041CE
0x14000411a  mov     rax, [rsi+10h]
0x14000411e  movsxd  rcx, ebx
0x140004121  mov     rbx, [rax+rcx*8]
0x140004125  jmp     short loc_1400040C9
0x140004127  mov     rcx, rax; lpsz
0x14000412a  call    cs:__imp_CharNextW
0x140004130  mov     [r14], rax
0x140004133  cmp     rax, rdi
0x140004136  jnz     short loc_140004127
0x140004138  jmp     short loc_140004151
0x14000413a  mov     rdx, rbx; unsigned __int16 *
0x14000413d  mov     r8d, 1; int
0x140004143  lea     rcx, [rsp+0A8h+var_88]; this
0x140004148  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x14000414d  test    eax, eax
0x14000414f  jz      short loc_140004199
0x140004151  mov     rcx, [r14]; lpsz
0x140004154  call    cs:__imp_CharNextW
0x14000415a  mov     rbx, rax
0x14000415d  mov     [r14], rax
0x140004160  movzx   eax, word ptr [rax]
0x140004163  test    ax, ax
0x140004166  jnz     loc_140003FE3
0x14000416c  mov     rcx, [rsp+0A8h+pv]
0x140004171  mov     ebx, r12d
0x140004174  mov     [rsp+0A8h+pv], r12
0x140004179  mov     [r15], rcx
0x14000417c  mov     rcx, [rsp+0A8h+pv]; pv
0x140004181  call    cs:__imp_CoTaskMemFree
0x140004187  mov     eax, ebx
0x140004189  jmp     short loc_1400041A5
0x14000418b  mov     ebx, 80004005h
0x140004190  jmp     short loc_14000417C
0x140004192  mov     ebx, 80020009h
0x140004197  jmp     short loc_14000417C
0x140004199  mov     ebx, 8007000Eh
0x14000419e  jmp     short loc_14000417C
0x1400041a0  mov     eax, 80004003h
0x1400041a5  mov     rcx, [rsp+0A8h+var_38]
0x1400041aa  xor     rcx, rsp; StackCookie
0x1400041ad  call    __security_check_cookie
0x1400041b2  lea     r11, [rsp+0A8h+var_28]
0x1400041ba  mov     rbx, [r11+38h]
0x1400041be  mov     rbp, [r11+48h]
0x1400041c2  mov     rsp, r11
0x1400041c5  pop     r15
0x1400041c7  pop     r14
0x1400041c9  pop     r12
0x1400041cb  pop     rdi
0x1400041cc  pop     rsi
0x1400041cd  retn
0x1400041ce  mov     ecx, 0C000008Ch; unsigned int
0x1400041d3  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x1400041d8  int     3; Trap to Debugger
0x1400041d9  mov     ecx, 80004005h; int
0x1400041de  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400041e4  mov     ecx, 80070057h; int
0x1400041e9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400041ef  mov     ecx, 8007000Eh; int
0x1400041f4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
