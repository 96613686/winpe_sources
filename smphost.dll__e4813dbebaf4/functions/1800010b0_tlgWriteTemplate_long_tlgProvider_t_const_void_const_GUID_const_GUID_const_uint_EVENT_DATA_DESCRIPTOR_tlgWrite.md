# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800010b0`
- end: `0x1800011b7`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@444@Z`
- size: `263`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int16 **, __int64, char **, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001bb8`

## callees

- `0x1800010b0`
- `0x18000123c`
- `0x180002890`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int16 **a5,
        __int64 a6,
        char **a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  __int64 v11; // rcx
  char *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  __int16 *v15; // rdx
  int v16; // ecx
  _BYTE v18[32]; // [rsp+30h] [rbp-69h] BYREF
  __int16 *v19; // [rsp+50h] [rbp-49h]
  int v20; // [rsp+58h] [rbp-41h]
  int v21; // [rsp+5Ch] [rbp-3Dh]
  __int64 v22; // [rsp+60h] [rbp-39h]
  __int64 v23; // [rsp+68h] [rbp-31h]
  char *v24; // [rsp+70h] [rbp-29h]
  int v25; // [rsp+78h] [rbp-21h]
  int v26; // [rsp+7Ch] [rbp-1Dh]
  __int64 v27; // [rsp+80h] [rbp-19h]
  __int64 v28; // [rsp+88h] [rbp-11h]
  __int64 v29; // [rsp+90h] [rbp-9h]
  __int64 v30; // [rsp+98h] [rbp-1h]
  __int64 v31; // [rsp+A0h] [rbp+7h]
  __int64 v32; // [rsp+A8h] [rbp+Fh]

  v31 = a10;
  v11 = -1;
  v29 = a9;
  v27 = a8;
  v32 = 4;
  v30 = 4;
  v28 = 4;
  v12 = *a7;
  if ( *a7 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)&v12[2 * v13] );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v12 = byte_180004438;
    v14 = 2;
  }
  v25 = v14;
  v22 = a6;
  v24 = v12;
  v26 = 0;
  v23 = 4;
  v15 = *a5;
  if ( *a5 )
  {
    do
      ++v11;
    while ( *((_BYTE *)v15 + v11) );
    v16 = v11 + 1;
  }
  else
  {
    v15 = word_18000443A;
    v16 = 1;
  }
  v19 = v15;
  v20 = v16;
  v21 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180006048, a2, 0, 0, 8, v18);
}

```

## disassembly

```asm
0x1800010b0  push    rbp
0x1800010b2  lea     rbp, [rsp-27h]
0x1800010b7  sub     rsp, 0C0h
0x1800010be  mov     rax, cs:__security_cookie
0x1800010c5  xor     rax, rsp
0x1800010c8  mov     [rbp+27h+var_10], rax
0x1800010cc  mov     rax, [rbp+27h+arg_48]
0x1800010d0  mov     r10, rdx
0x1800010d3  mov     [rbp+27h+var_20], rax
0x1800010d7  xor     r8d, r8d
0x1800010da  mov     rax, [rbp+27h+arg_40]
0x1800010de  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800010e2  mov     [rbp+27h+var_30], rax
0x1800010e6  mov     rax, [rbp+27h+arg_38]
0x1800010ea  mov     [rbp+27h+var_40], rax
0x1800010ee  mov     rax, [rbp+27h+arg_30]
0x1800010f2  mov     [rbp+27h+var_18], 4
0x1800010fa  mov     [rbp+27h+var_28], 4
0x180001102  mov     [rbp+27h+var_38], 4
0x18000110a  mov     rdx, [rax]
0x18000110d  test    rdx, rdx
0x180001110  jz      short loc_180001128
0x180001112  mov     rax, rcx
0x180001115  inc     rax
0x180001118  cmp     [rdx+rax*2], r8w
0x18000111d  jnz     short loc_180001115
0x18000111f  lea     eax, ds:2[rax*2]
0x180001126  jmp     short loc_180001134
0x180001128  lea     rdx, byte_180004438
0x18000112f  mov     eax, 2
0x180001134  mov     [rbp+27h+var_48], eax
0x180001137  mov     rax, [rbp+27h+arg_28]
0x18000113b  mov     [rbp+27h+var_60], rax
0x18000113f  mov     rax, [rbp+27h+arg_20]
0x180001143  mov     [rbp+27h+var_50], rdx
0x180001147  mov     [rbp+27h+var_44], r8d
0x18000114b  mov     [rbp+27h+var_58], 4
0x180001153  mov     rdx, [rax]
0x180001156  test    rdx, rdx
0x180001159  jz      short loc_180001168
0x18000115b  inc     rcx
0x18000115e  cmp     [rdx+rcx], r8b
0x180001162  jnz     short loc_18000115B
0x180001164  inc     ecx
0x180001166  jmp     short loc_180001174
0x180001168  lea     rdx, word_18000443A
0x18000116f  mov     ecx, 1
0x180001174  lea     rax, [rbp+27h+var_90]
0x180001178  mov     [rbp+27h+var_70], rdx
0x18000117c  mov     [rbp+27h+var_68], ecx
0x18000117f  xor     r9d, r9d
0x180001182  mov     [rsp+0C0h+var_98], rax
0x180001187  lea     rcx, dword_180006048
0x18000118e  mov     rdx, r10
0x180001191  mov     [rsp+0C0h+var_A0], 8
0x180001199  mov     [rbp+27h+var_64], r8d
0x18000119d  call    _tlgWriteTransfer_EventWriteTransfer
0x1800011a2  mov     rcx, [rbp+27h+var_10]
0x1800011a6  xor     rcx, rsp; StackCookie
0x1800011a9  call    __security_check_cookie
0x1800011ae  add     rsp, 0C0h
0x1800011b5  pop     rbp
0x1800011b6  retn
```
