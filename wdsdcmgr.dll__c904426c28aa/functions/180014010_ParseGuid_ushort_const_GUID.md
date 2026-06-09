# ParseGuid(ushort const *,_GUID *)

- ea: `0x180014010`
- end: `0x180014242`
- name: `?ParseGuid@@YAKPEBGPEAU_GUID@@@Z`
- size: `562`
- prototype: `__int64 __fastcall(wchar_t *String, struct _GUID *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009894`
- `0x18000f710`
- `0x1800102e0`

## callees

- `0x180013b48`
- `0x180013dcc`
- `0x180014010`
- `0x180014d58`
- `0x1800150b8`
- `0x180015660`
- `0x180015c9d`

## import_xrefs

- `msvcrt!wcstoul` at `0x180014173`
- `msvcrt!wcstoul` at `0x180014187`
- `msvcrt!wcstoul` at `0x18001419c`
- `msvcrt!wcstoul` at `0x180014173`
- `msvcrt!wcstoul` at `0x180014187`
- `msvcrt!wcstoul` at `0x18001419c`
- `msvcrt!wcschr` at `0x180014150`
- `msvcrt!wcschr` at `0x180014150`
- `msvcrt!wcsncat_s` at `0x1800141b9`
- `msvcrt!wcsncat_s` at `0x1800141cd`
- `msvcrt!wcsncat_s` at `0x1800141b9`
- `msvcrt!wcsncat_s` at `0x1800141cd`

## string_xrefs

- `0x1800140b7`: `onecore\base\eco\wds\wdslib\common\src\strutil.cpp`
- `0x1800141ea`: `onecore\base\eco\wds\wdslib\common\src\strutil.cpp`
- `0x18001420b`: `onecore\base\eco\wds\wdslib\common\src\strutil.cpp`

## pseudocode

```c
__int64 __fastcall ParseGuid(wchar_t *String, struct _GUID *a2)
{
  wchar_t *v4; // rdi
  unsigned __int8 *v5; // r14
  __int64 v6; // r15
  __int64 v7; // rax
  unsigned int v8; // ebx
  const char *v9; // rdx
  unsigned int v10; // eax
  unsigned __int64 i; // rbx
  __int64 v12; // rax
  const char *v14; // rdx
  const char *v15; // rdx
  unsigned __int8 *v16; // [rsp+20h] [rbp-60h] BYREF
  void *Block; // [rsp+28h] [rbp-58h] BYREF
  wchar_t *EndPtr; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int64 v19; // [rsp+38h] [rbp-48h] BYREF
  struct _GUID v20; // [rsp+40h] [rbp-40h]
  wchar_t Destination[20]; // [rsp+50h] [rbp-30h] BYREF

  v20 = (struct _GUID)0LL;
  Block = 0;
  EndPtr = 0;
  v16 = 0;
  v4 = 0;
  v19 = 0;
  v5 = 0;
  memset_0(Destination, 0, 0x22u);
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( String[v7] );
  if ( v7 != 36 )
  {
    if ( v7 != 38 || *String != 123 || String[37] != 125 )
      return 13;
    v8 = DuplicateStringW(String + 1, (unsigned __int16 **)&Block);
    v10 = ElValidateWin32(v8, v9, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\strutil.cpp", 0xA03u);
    v4 = (wchar_t *)Block;
    if ( v10 )
      goto LABEL_16;
    do
      ++v6;
    while ( *((_WORD *)Block + v6) );
    *((_WORD *)Block + v6 - 1) = 0;
    String = v4;
  }
  for ( i = 0; i < 0x24; ++i )
  {
    if ( i <= 0x17 && (v12 = 8659200, _bittest64(&v12, i)) )
    {
      if ( String[i] != 45 )
        goto LABEL_15;
    }
    else if ( !wcschr(L"0123456789abcdefABCDEF", String[i]) )
    {
LABEL_15:
      v8 = 13;
      goto LABEL_16;
    }
  }
  v20.Data1 = wcstoul(String, &EndPtr, 16);
  v20.Data2 = wcstoul(String + 9, &EndPtr, 16);
  v20.Data3 = wcstoul(String + 14, &EndPtr, 16);
  wcsncat_s(Destination, 0x11u, String + 19, 4u);
  wcsncat_s(Destination, 0x11u, String + 24, 0xCu);
  v8 = StringToHex(Destination, &v16, &v19);
  if ( !ElValidateWin32(v8, v14, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\strutil.cpp", 0xA36u) )
  {
    if ( v19 == 8 )
    {
      v5 = v16;
      *(_QWORD *)v20.Data4 = *(_QWORD *)v16;
      *a2 = v20;
      goto LABEL_16;
    }
    v8 = ElValidateWin32(0xDu, v15, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\strutil.cpp", 0xA40u);
  }
  v5 = v16;
LABEL_16:
  if ( v4 )
    operator delete(v4);
  if ( v5 )
    operator delete(v5);
  return v8;
}

```

## disassembly

```asm
0x180014010  mov     [rsp-38h+arg_10], rbx
0x180014015  push    rbp
0x180014016  push    rsi
0x180014017  push    rdi
0x180014018  push    r12
0x18001401a  push    r13
0x18001401c  push    r14
0x18001401e  push    r15
0x180014020  mov     rbp, rsp
0x180014023  sub     rsp, 80h
0x18001402a  mov     rax, cs:__security_cookie
0x180014031  xor     rax, rsp
0x180014034  mov     [rbp+var_8], rax
0x180014038  xor     r13d, r13d
0x18001403b  xor     eax, eax
0x18001403d  mov     r12, rdx
0x180014040  mov     qword ptr [rbp+var_40], rax
0x180014044  mov     rsi, rcx
0x180014047  mov     qword ptr [rbp+var_40+8], rax
0x18001404b  xor     edx, edx; Val
0x18001404d  mov     [rbp+Block], r13
0x180014051  lea     r8d, [rax+22h]; Size
0x180014055  mov     [rbp+EndPtr], r13
0x180014059  lea     rcx, [rbp+Destination]; void *
0x18001405d  mov     [rbp+var_60], r13
0x180014061  mov     edi, r13d
0x180014064  mov     [rbp+var_48], r13
0x180014068  mov     r14d, r13d
0x18001406b  call    memset_0
0x180014070  or      r15, 0FFFFFFFFFFFFFFFFh
0x180014074  mov     rax, r15
0x180014077  inc     rax
0x18001407a  cmp     [rsi+rax*2], r13w
0x18001407f  jnz     short loc_180014077
0x180014081  cmp     rax, 24h ; '$'
0x180014085  jz      short loc_1800140E2
0x180014087  cmp     rax, 26h ; '&'
0x18001408b  jz      short loc_180014097
0x18001408d  mov     ebx, 0Dh
0x180014092  jmp     loc_18001411C
0x180014097  cmp     word ptr [rsi], 7Bh ; '{'
0x18001409b  jnz     short loc_18001408D
0x18001409d  cmp     word ptr [rsi+4Ah], 7Dh ; '}'
0x1800140a2  jnz     short loc_18001408D
0x1800140a4  lea     rcx, [rsi+2]; unsigned __int16 *
0x1800140a8  lea     rdx, [rbp+Block]; unsigned __int16 **
0x1800140ac  call    ?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x1800140b1  mov     r9d, 0A03h; unsigned int
0x1800140b7  lea     r8, aOnecoreBaseEco_4; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800140be  mov     ecx, eax; unsigned int
0x1800140c0  mov     ebx, eax
0x1800140c2  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800140c7  mov     rdi, [rbp+Block]
0x1800140cb  test    eax, eax
0x1800140cd  jnz     short loc_180014102
0x1800140cf  inc     r15
0x1800140d2  cmp     [rdi+r15*2], r13w
0x1800140d7  jnz     short loc_1800140CF
0x1800140d9  mov     [rdi+r15*2-2], r13w
0x1800140df  mov     rsi, rdi
0x1800140e2  mov     rbx, r13
0x1800140e5  cmp     rbx, 17h
0x1800140e9  ja      short loc_180014145
0x1800140eb  mov     eax, 842100h
0x1800140f0  bt      rax, rbx
0x1800140f4  jnb     short loc_180014145
0x1800140f6  cmp     word ptr [rsi+rbx*2], 2Dh ; '-'
0x1800140fb  jz      short loc_18001415B
0x1800140fd  mov     ebx, 0Dh
0x180014102  test    rdi, rdi
0x180014105  jz      short loc_18001410F
0x180014107  mov     rcx, rdi; Block
0x18001410a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001410f  test    r14, r14
0x180014112  jz      short loc_18001411C
0x180014114  mov     rcx, r14; Block
0x180014117  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001411c  mov     eax, ebx
0x18001411e  mov     rcx, [rbp+var_8]
0x180014122  xor     rcx, rsp; StackCookie
0x180014125  call    __security_check_cookie
0x18001412a  mov     rbx, [rsp+80h+arg_10]
0x180014132  add     rsp, 80h
0x180014139  pop     r15
0x18001413b  pop     r14
0x18001413d  pop     r13
0x18001413f  pop     r12
0x180014141  pop     rdi
0x180014142  pop     rsi
0x180014143  pop     rbp
0x180014144  retn
0x180014145  movzx   edx, word ptr [rsi+rbx*2]; Ch
0x180014149  lea     rcx, a0123456789abcd; "0123456789abcdefABCDEF"
0x180014150  call    cs:__imp_wcschr
0x180014156  test    rax, rax
0x180014159  jz      short loc_1800140FD
0x18001415b  inc     rbx
0x18001415e  cmp     rbx, 24h ; '$'
0x180014162  jb      short loc_1800140E5
0x180014164  mov     ebx, 10h
0x180014169  lea     rdx, [rbp+EndPtr]; EndPtr
0x18001416d  mov     r8d, ebx; Radix
0x180014170  mov     rcx, rsi; String
0x180014173  call    cs:__imp_wcstoul
0x180014179  lea     rcx, [rsi+12h]; String
0x18001417d  mov     r8d, ebx; Radix
0x180014180  lea     rdx, [rbp+EndPtr]; EndPtr
0x180014184  mov     dword ptr [rbp+var_40], eax
0x180014187  call    cs:__imp_wcstoul
0x18001418d  lea     rcx, [rsi+1Ch]; String
0x180014191  mov     r8d, ebx; Radix
0x180014194  lea     rdx, [rbp+EndPtr]; EndPtr
0x180014198  mov     word ptr [rbp+var_40+4], ax
0x18001419c  call    cs:__imp_wcstoul
0x1800141a2  mov     ebx, 11h
0x1800141a7  lea     r8, [rsi+26h]; Source
0x1800141ab  lea     rcx, [rbp+Destination]; Destination
0x1800141af  mov     word ptr [rbp+var_40+6], ax
0x1800141b3  mov     edx, ebx; SizeInWords
0x1800141b5  lea     r9d, [rbx-0Dh]; MaxCount
0x1800141b9  call    cs:__imp_wcsncat_s
0x1800141bf  lea     r8, [rsi+30h]; Source
0x1800141c3  mov     edx, ebx; SizeInWords
0x1800141c5  lea     r9d, [rbx-5]; MaxCount
0x1800141c9  lea     rcx, [rbp+Destination]; Destination
0x1800141cd  call    cs:__imp_wcsncat_s
0x1800141d3  lea     r8, [rbp+var_48]; unsigned __int64 *
0x1800141d7  lea     rdx, [rbp+var_60]; unsigned __int8 **
0x1800141db  lea     rcx, [rbp+Destination]; unsigned __int16 *
0x1800141df  call    ?StringToHex@@YAKPEBGPEAPEAEPEA_K@Z; StringToHex(ushort const *,uchar * *,unsigned __int64 *)
0x1800141e4  mov     r9d, 0A36h; unsigned int
0x1800141ea  lea     r8, aOnecoreBaseEco_4; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800141f1  mov     ecx, eax; unsigned int
0x1800141f3  mov     ebx, eax
0x1800141f5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800141fa  test    eax, eax
0x1800141fc  jnz     short loc_18001421C
0x1800141fe  cmp     [rbp+var_48], 8
0x180014203  jz      short loc_180014225
0x180014205  mov     r9d, 0A40h; unsigned int
0x18001420b  lea     r8, aOnecoreBaseEco_4; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180014212  lea     ecx, [rax+0Dh]; unsigned int
0x180014215  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001421a  mov     ebx, eax
0x18001421c  mov     r14, [rbp+var_60]
0x180014220  jmp     loc_180014102
0x180014225  mov     r14, [rbp+var_60]
0x180014229  movsd   xmm0, qword ptr [r14]
0x18001422e  movsd   qword ptr [rbp+var_40+8], xmm0
0x180014233  movups  xmm1, [rbp+var_40]
0x180014237  movdqu  xmmword ptr [r12], xmm1
0x18001423d  jmp     loc_180014102
```
