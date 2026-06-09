# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000ab0c`
- end: `0x18000ae1d`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `785`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b374`

## callees

- `0x1800040ac`
- `0x1800041f8`
- `0x18000ab0c`
- `0x18000d798`
- `0x180012db0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000ac58`
- `msvcrt!wcsncpy_s` at `0x18000ac58`
- `KERNEL32!lstrcmpiW` at `0x18000acb9`
- `KERNEL32!lstrcmpiW` at `0x18000acb9`
- `KERNEL32!LeaveCriticalSection` at `0x18000acd7`
- `KERNEL32!LeaveCriticalSection` at `0x18000acd7`
- `KERNEL32!EnterCriticalSection` at `0x18000ac94`
- `KERNEL32!EnterCriticalSection` at `0x18000ac94`
- `USER32!CharNextW` at `0x18000abdc`
- `USER32!CharNextW` at `0x18000ac13`
- `USER32!CharNextW` at `0x18000ad3a`
- `USER32!CharNextW` at `0x18000ad6a`
- `USER32!CharNextW` at `0x18000abdc`
- `USER32!CharNextW` at `0x18000ac13`
- `USER32!CharNextW` at `0x18000ad3a`
- `USER32!CharNextW` at `0x18000ad6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000aba3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000aba3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ab8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ad9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ab8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ad9d`

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
  errno_t v18; // eax
  LPCWSTR v19; // rsi
  int v20; // ebx
  unsigned int v21; // edx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  const WCHAR *i; // rax
  unsigned int v25; // ebx
  _DWORD v26[2]; // [rsp+20h] [rbp-88h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-80h]
  wchar_t Destination[32]; // [rsp+30h] [rbp-78h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  v26[0] = 0;
  if ( v7 < 100 )
    v7 = 1000;
  v26[1] = v7;
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
    v25 = 0;
    pv = 0;
    *a3 = (unsigned __int16 *)v9;
    goto LABEL_50;
  }
  while ( v12 != 37 )
  {
    v15 = v4;
LABEL_46:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v15, 1) )
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
    v25 = -2147467259;
    goto LABEL_50;
  }
  v18 = wcsncpy_s(Destination, 0x20u, *this, (int)v17);
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
  while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), Destination) )
  {
    if ( ++v20 >= *((_DWORD *)v19 + 6) )
      goto LABEL_32;
  }
  if ( v20 == -1 )
  {
LABEL_32:
    v22 = 0;
  }
  else
  {
    if ( v20 < 0 || v20 >= *((_DWORD *)v19 + 6) )
    {
      ATL::_AtlRaiseException(0xC000008C, v21);
      __debugbreak();
    }
    v22 = *(const unsigned __int16 **)(*((_QWORD *)v19 + 2) + 8LL * v20);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  if ( !v22 )
  {
LABEL_52:
    v25 = -2147352567;
    goto LABEL_50;
  }
  v23 = -1;
  do
    ++v23;
  while ( v22[v23] );
  if ( ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v22, v23) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
    goto LABEL_47;
  }
LABEL_53:
  v25 = -2147024882;
LABEL_50:
  CoTaskMemFree(pv);
  return v25;
}

```

## disassembly

```asm
0x18000ab0c  mov     [rsp+arg_8], rbx
0x18000ab11  mov     [rsp+arg_18], rbp
0x18000ab16  push    rsi
0x18000ab17  push    rdi
0x18000ab18  push    r12
0x18000ab1a  push    r14
0x18000ab1c  push    r15
0x18000ab1e  sub     rsp, 80h
0x18000ab25  mov     rax, cs:__security_cookie
0x18000ab2c  xor     rax, rsp
0x18000ab2f  mov     [rsp+0A8h+var_38], rax
0x18000ab34  xor     r12d, r12d
0x18000ab37  mov     r15, r8
0x18000ab3a  mov     rbx, rdx
0x18000ab3d  mov     r14, rcx
0x18000ab40  test    rdx, rdx
0x18000ab43  jz      loc_18000ADC2
0x18000ab49  test    r8, r8
0x18000ab4c  jz      loc_18000ADC2
0x18000ab52  mov     [r8], r12
0x18000ab55  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ab59  inc     rax
0x18000ab5c  cmp     [rdx+rax*2], r12w
0x18000ab61  jnz     short loc_18000AB59
0x18000ab63  add     eax, eax
0x18000ab65  mov     [rsp+0A8h+var_88], r12d
0x18000ab6a  cmp     eax, 64h ; 'd'
0x18000ab6d  mov     ecx, 3E8h
0x18000ab72  cmovl   eax, ecx
0x18000ab75  mov     ecx, eax
0x18000ab77  mov     [rsp+0A8h+var_84], eax
0x18000ab7b  add     rcx, rcx
0x18000ab7e  mov     eax, 0FFFFFFFFh
0x18000ab83  cmp     rcx, rax
0x18000ab86  jbe     short loc_18000ABA1
0x18000ab88  mov     rcx, r12; pv
0x18000ab8b  call    cs:__imp_CoTaskMemFree
0x18000ab92  nop     dword ptr [rax+rax+00h]
0x18000ab97  mov     eax, 8007000Eh
0x18000ab9c  jmp     loc_18000ADC7
0x18000aba1  mov     ecx, ecx; cb
0x18000aba3  call    cs:__imp_CoTaskMemAlloc
0x18000abaa  nop     dword ptr [rax+rax+00h]
0x18000abaf  mov     [rsp+0A8h+pv], rax
0x18000abb4  mov     rcx, rax
0x18000abb7  test    rax, rax
0x18000abba  jz      short loc_18000AB8B
0x18000abbc  mov     [rax], r12w
0x18000abc0  mov     [r14], rbx
0x18000abc3  movzx   eax, word ptr [rbx]
0x18000abc6  test    ax, ax
0x18000abc9  jz      loc_18000AD8D
0x18000abcf  cmp     ax, 25h ; '%'
0x18000abd3  jnz     loc_18000AD50
0x18000abd9  mov     rcx, rbx; lpsz
0x18000abdc  call    cs:__imp_CharNextW
0x18000abe3  nop     dword ptr [rax+rax+00h]
0x18000abe8  mov     [r14], rax
0x18000abeb  movzx   ecx, word ptr [rax]
0x18000abee  cmp     cx, 25h ; '%'
0x18000abf2  jnz     short loc_18000ABFC
0x18000abf4  mov     rdx, rax
0x18000abf7  jmp     loc_18000AD53
0x18000abfc  test    rax, rax
0x18000abff  jz      loc_18000ADB4
0x18000ac05  mov     rdi, r12
0x18000ac08  jmp     short loc_18000AC22
0x18000ac0a  cmp     cx, 25h ; '%'
0x18000ac0e  jz      short loc_18000AC29
0x18000ac10  mov     rcx, rax; lpsz
0x18000ac13  call    cs:__imp_CharNextW
0x18000ac1a  nop     dword ptr [rax+rax+00h]
0x18000ac1f  movzx   ecx, word ptr [rax]
0x18000ac22  test    cx, cx
0x18000ac25  jnz     short loc_18000AC0A
0x18000ac27  jmp     short loc_18000AC2C
0x18000ac29  mov     rdi, rax
0x18000ac2c  test    rdi, rdi
0x18000ac2f  jz      loc_18000ADB4
0x18000ac35  mov     rax, rdi
0x18000ac38  sub     rax, [r14]
0x18000ac3b  sar     rax, 1
0x18000ac3e  cmp     rax, 1Fh
0x18000ac42  jg      loc_18000ADAD
0x18000ac48  mov     r8, [r14]; Source
0x18000ac4b  lea     rcx, [rsp+0A8h+Destination]; Destination
0x18000ac50  movsxd  r9, eax; MaxCount
0x18000ac53  mov     edx, 20h ; ' '; SizeInWords
0x18000ac58  call    cs:__imp_wcsncpy_s
0x18000ac5f  nop     dword ptr [rax+rax+00h]
0x18000ac64  test    eax, eax
0x18000ac66  jz      short loc_18000AC8C
0x18000ac68  cmp     eax, 0Ch
0x18000ac6b  jz      loc_18000AE12
0x18000ac71  cmp     eax, 16h
0x18000ac74  jz      loc_18000AE07
0x18000ac7a  cmp     eax, 22h ; '"'
0x18000ac7d  jz      loc_18000AE07
0x18000ac83  cmp     eax, 50h ; 'P'
0x18000ac86  jnz     loc_18000ADFC
0x18000ac8c  mov     rsi, [r14+8]
0x18000ac90  lea     rcx, [rsi+20h]; lpCriticalSection
0x18000ac94  call    cs:__imp_EnterCriticalSection
0x18000ac9b  nop     dword ptr [rax+rax+00h]
0x18000aca0  mov     ebx, r12d
0x18000aca3  cmp     [rsi+18h], r12d
0x18000aca7  jle     short loc_18000ACD0
0x18000aca9  mov     rcx, [rsi+8]
0x18000acad  lea     rdx, [rsp+0A8h+Destination]; lpString2
0x18000acb2  movsxd  rax, ebx
0x18000acb5  mov     rcx, [rcx+rax*8]; lpString1
0x18000acb9  call    cs:__imp_lstrcmpiW
0x18000acc0  nop     dword ptr [rax+rax+00h]
0x18000acc5  test    eax, eax
0x18000acc7  jz      short loc_18000AD14
0x18000acc9  inc     ebx
0x18000accb  cmp     ebx, [rsi+18h]
0x18000acce  jl      short loc_18000ACA9
0x18000acd0  mov     rbx, r12
0x18000acd3  lea     rcx, [rsi+20h]; lpCriticalSection
0x18000acd7  call    cs:__imp_LeaveCriticalSection
0x18000acde  nop     dword ptr [rax+rax+00h]
0x18000ace3  test    rbx, rbx
0x18000ace6  jz      loc_18000ADB4
0x18000acec  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000acf0  inc     r8; int
0x18000acf3  cmp     [rbx+r8*2], r12w
0x18000acf8  jnz     short loc_18000ACF0
0x18000acfa  mov     rdx, rbx; unsigned __int16 *
0x18000acfd  lea     rcx, [rsp+0A8h+var_88]; this
0x18000ad02  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000ad07  test    eax, eax
0x18000ad09  jz      loc_18000ADBB
0x18000ad0f  mov     rax, [r14]
0x18000ad12  jmp     short loc_18000AD49
0x18000ad14  cmp     ebx, 0FFFFFFFFh
0x18000ad17  jz      short loc_18000ACD0
0x18000ad19  test    ebx, ebx
0x18000ad1b  js      loc_18000ADF1
0x18000ad21  cmp     ebx, [rsi+18h]
0x18000ad24  jge     loc_18000ADF1
0x18000ad2a  mov     rax, [rsi+10h]
0x18000ad2e  movsxd  rcx, ebx
0x18000ad31  mov     rbx, [rax+rcx*8]
0x18000ad35  jmp     short loc_18000ACD3
0x18000ad37  mov     rcx, rax; lpsz
0x18000ad3a  call    cs:__imp_CharNextW
0x18000ad41  nop     dword ptr [rax+rax+00h]
0x18000ad46  mov     [r14], rax
0x18000ad49  cmp     rax, rdi
0x18000ad4c  jnz     short loc_18000AD37
0x18000ad4e  jmp     short loc_18000AD67
0x18000ad50  mov     rdx, rbx; unsigned __int16 *
0x18000ad53  mov     r8d, 1; int
0x18000ad59  lea     rcx, [rsp+0A8h+var_88]; this
0x18000ad5e  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000ad63  test    eax, eax
0x18000ad65  jz      short loc_18000ADBB
0x18000ad67  mov     rcx, [r14]; lpsz
0x18000ad6a  call    cs:__imp_CharNextW
0x18000ad71  nop     dword ptr [rax+rax+00h]
0x18000ad76  mov     rbx, rax
0x18000ad79  mov     [r14], rax
0x18000ad7c  movzx   eax, word ptr [rax]
0x18000ad7f  test    ax, ax
0x18000ad82  jnz     loc_18000ABCF
0x18000ad88  mov     rcx, [rsp+0A8h+pv]
0x18000ad8d  mov     ebx, r12d
0x18000ad90  mov     [rsp+0A8h+pv], r12
0x18000ad95  mov     [r15], rcx
0x18000ad98  mov     rcx, [rsp+0A8h+pv]; pv
0x18000ad9d  call    cs:__imp_CoTaskMemFree
0x18000ada4  nop     dword ptr [rax+rax+00h]
0x18000ada9  mov     eax, ebx
0x18000adab  jmp     short loc_18000ADC7
0x18000adad  mov     ebx, 80004005h
0x18000adb2  jmp     short loc_18000AD98
0x18000adb4  mov     ebx, 80020009h
0x18000adb9  jmp     short loc_18000AD98
0x18000adbb  mov     ebx, 8007000Eh
0x18000adc0  jmp     short loc_18000AD98
0x18000adc2  mov     eax, 80004003h
0x18000adc7  mov     rcx, [rsp+0A8h+var_38]
0x18000adcc  xor     rcx, rsp; StackCookie
0x18000adcf  call    __security_check_cookie
0x18000add4  lea     r11, [rsp+0A8h+var_28]
0x18000addc  mov     rbx, [r11+38h]
0x18000ade0  mov     rbp, [r11+48h]
0x18000ade4  mov     rsp, r11
0x18000ade7  pop     r15
0x18000ade9  pop     r14
0x18000adeb  pop     r12
0x18000aded  pop     rdi
0x18000adee  pop     rsi
0x18000adef  retn
0x18000adf1  mov     ecx, 0C000008Ch; unsigned int
0x18000adf6  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000adfb  int     3; Trap to Debugger
0x18000adfc  mov     ecx, 80004005h; int
0x18000ae01  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000ae07  mov     ecx, 80070057h; int
0x18000ae0c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000ae12  mov     ecx, 8007000Eh; int
0x18000ae17  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
