# DigestOpenSam

- ea: `0x180023440`
- end: `0x180023576`
- name: `DigestOpenSam`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002357c`

## callees

- `0x180011fec`
- `0x1800185b8`
- `0x180023440`

## import_xrefs

- `SAMSRV!SamIConnect` at `0x1800234a8`
- `SAMSRV!SamIConnect` at `0x1800234a8`
- `SAMSRV!SamrCloseHandle` at `0x1800234fb`
- `SAMSRV!SamrCloseHandle` at `0x180023539`
- `SAMSRV!SamrCloseHandle` at `0x1800234fb`
- `SAMSRV!SamrCloseHandle` at `0x180023539`
- `SAMSRV!SamrOpenDomain` at `0x180023516`
- `SAMSRV!SamrOpenDomain` at `0x180023516`

## pseudocode

```c
__int64 __fastcall DigestOpenSam(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v5; // eax
  int v6; // ebx
  PVOID *v7; // rcx
  signed __int64 v8; // [rsp+30h] [rbp+8h] BYREF
  signed __int64 v9; // [rsp+38h] [rbp+10h] BYREF

  v8 = 0;
  v9 = 0;
  if ( l_AccountDomainHandle )
    return 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids);
  LOBYTE(a4) = 1;
  v5 = SamIConnect(0, &v8, 0, a4);
  v6 = v5;
  if ( v5 >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&l_AccountSamHandle, v8, 0) )
      SamrCloseHandle(&v8);
    v6 = SamrOpenDomain(l_AccountSamHandle, 0, hMem, &v9);
    if ( v6 >= 0 && _InterlockedCompareExchange64((volatile signed __int64 *)&l_AccountDomainHandle, v9, 0) )
      SamrCloseHandle(&v9);
    goto LABEL_15;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_16;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      60,
      &WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids,
      (unsigned int)v5);
LABEL_15:
    v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_16:
    if ( v7 != &WPP_GLOBAL_Control && *((char *)v7 + 28) < 0 )
      WPP_SF_d(v7[2], 61, &WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids, (unsigned int)v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180023440  mov     [rsp+arg_10], rbx
0x180023445  push    rsi
0x180023446  sub     rsp, 20h
0x18002344a  cmp     cs:?l_AccountDomainHandle@@3PEAXEA, 0; void * l_AccountDomainHandle
0x180023452  mov     [rsp+28h+arg_0], 0
0x18002345b  mov     [rsp+28h+arg_8], 0
0x180023464  jz      short loc_18002346D
0x180023466  xor     eax, eax
0x180023468  jmp     loc_18002356B
0x18002346d  mov     rcx, cs:WPP_GLOBAL_Control
0x180023474  lea     rsi, WPP_GLOBAL_Control
0x18002347b  cmp     rcx, rsi
0x18002347e  jz      short loc_18002349B
0x180023480  test    byte ptr [rcx+1Ch], 80h
0x180023484  jz      short loc_18002349B
0x180023486  mov     rcx, [rcx+10h]
0x18002348a  lea     r8, WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids
0x180023491  mov     edx, 3Bh ; ';'
0x180023496  call    WPP_SF_
0x18002349b  mov     r9b, 1
0x18002349e  lea     rdx, [rsp+28h+arg_0]
0x1800234a3  xor     r8d, r8d
0x1800234a6  xor     ecx, ecx
0x1800234a8  call    cs:__imp_SamIConnect
0x1800234ae  mov     ebx, eax
0x1800234b0  test    eax, eax
0x1800234b2  jns     short loc_1800234E4
0x1800234b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800234bb  cmp     rcx, rsi
0x1800234be  jz      loc_180023569
0x1800234c4  test    byte ptr [rcx+1Ch], 1
0x1800234c8  jz      short loc_180023546
0x1800234ca  mov     rcx, [rcx+10h]
0x1800234ce  lea     r8, WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids
0x1800234d5  mov     edx, 3Ch ; '<'
0x1800234da  mov     r9d, eax
0x1800234dd  call    WPP_SF_d
0x1800234e2  jmp     short loc_18002353F
0x1800234e4  mov     rcx, [rsp+28h+arg_0]
0x1800234e9  xor     eax, eax
0x1800234eb  lock cmpxchg cs:?l_AccountSamHandle@@3PEAXEA, rcx; void * l_AccountSamHandle
0x1800234f4  jz      short loc_180023501
0x1800234f6  lea     rcx, [rsp+28h+arg_0]
0x1800234fb  call    cs:__imp_SamrCloseHandle
0x180023501  mov     r8, cs:hMem
0x180023508  lea     r9, [rsp+28h+arg_8]
0x18002350d  mov     rcx, cs:?l_AccountSamHandle@@3PEAXEA; void * l_AccountSamHandle
0x180023514  xor     edx, edx
0x180023516  call    cs:__imp_SamrOpenDomain
0x18002351c  mov     ebx, eax
0x18002351e  test    eax, eax
0x180023520  js      short loc_18002353F
0x180023522  mov     rcx, [rsp+28h+arg_8]
0x180023527  xor     eax, eax
0x180023529  lock cmpxchg cs:?l_AccountDomainHandle@@3PEAXEA, rcx; void * l_AccountDomainHandle
0x180023532  jz      short loc_18002353F
0x180023534  lea     rcx, [rsp+28h+arg_8]
0x180023539  call    cs:__imp_SamrCloseHandle
0x18002353f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023546  cmp     rcx, rsi
0x180023549  jz      short loc_180023569
0x18002354b  test    byte ptr [rcx+1Ch], 80h
0x18002354f  jz      short loc_180023569
0x180023551  mov     rcx, [rcx+10h]
0x180023555  lea     r8, WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids
0x18002355c  mov     edx, 3Dh ; '='
0x180023561  mov     r9d, ebx
0x180023564  call    WPP_SF_d
0x180023569  mov     eax, ebx
0x18002356b  mov     rbx, [rsp+28h+arg_10]
0x180023570  add     rsp, 20h
0x180023574  pop     rsi
0x180023575  retn
```
