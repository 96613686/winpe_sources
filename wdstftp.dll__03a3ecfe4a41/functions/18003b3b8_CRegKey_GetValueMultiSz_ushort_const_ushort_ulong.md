# CRegKey::GetValueMultiSz(ushort const *,ushort * * *,ulong *)

- ea: `0x18003b3b8`
- end: `0x18003b69e`
- name: `?GetValueMultiSz@CRegKey@@QEAAKPEBGPEAPEAPEAGPEAK@Z`
- size: `742`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a9f0`

## callees

- `0x18000a960`
- `0x18000fd58`
- `0x18003b3b8`
- `0x18003b6a4`
- `0x18003cf50`
- `0x18003d028`
- `0x180060808`
- `0x180060e5a`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18003b403`
- `ADVAPI32!RegQueryValueExW` at `0x18003b445`
- `ADVAPI32!RegQueryValueExW` at `0x18003b4b7`
- `ADVAPI32!RegQueryValueExW` at `0x18003b403`
- `ADVAPI32!RegQueryValueExW` at `0x18003b445`
- `ADVAPI32!RegQueryValueExW` at `0x18003b4b7`

## string_xrefs

- `0x18003b3d5`: `ReadFilter`
- `0x18003b56b`: `onecore\base\eco\wds\wdslib\common\src\regkey.cpp`

## pseudocode

```c
__int64 __fastcall CRegKey::GetValueMultiSz(
        HKEY *this,
        const unsigned __int16 *a2,
        unsigned __int16 ***a3,
        unsigned int *a4)
{
  int v4; // r13d
  unsigned int v8; // edi
  unsigned int Value; // ebx
  unsigned __int64 v10; // rax
  BYTE *lpData; // rbp
  BYTE *v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // rax
  unsigned __int16 **v15; // rax
  const char *v16; // rdx
  const unsigned __int16 *v17; // r14
  unsigned __int64 v18; // rsi
  int v19; // eax
  int v20; // edi
  const char *v21; // rdx
  const char *v22; // r8
  unsigned int v23; // r9d
  int v24; // eax
  unsigned __int64 v25; // rax
  unsigned __int16 *v26; // rcx
  int v27; // eax
  DWORD v29; // [rsp+70h] [rbp+8h] BYREF
  const unsigned __int16 *cbData; // [rsp+78h] [rbp+10h] BYREF

  cbData = a2;
  v4 = 0;
  *a4 = 0;
  *a3 = 0;
  v8 = 0;
  Value = RegQueryValueExW(*this, L"ReadFilter", 0, &v29, 0, 0);
  if ( Value )
    goto LABEL_43;
  if ( v29 != 7 )
  {
    Value = 1804;
    goto LABEL_43;
  }
  Value = RegQueryValueExW(*this, L"ReadFilter", 0, 0, 0, (LPDWORD)&cbData);
  if ( Value )
  {
LABEL_43:
    if ( *a4 )
    {
      CRegKey::FreeMultiSz(*a3, *a4);
      *a4 = 0;
      *a3 = 0;
    }
    return Value;
  }
  if ( !(_DWORD)cbData )
    return Value;
  v10 = 2 * ((unsigned __int64)(unsigned int)cbData >> 1);
  if ( !is_mul_ok((unsigned __int64)(unsigned int)cbData >> 1, 2u) )
    v10 = -1;
  lpData = (BYTE *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
  if ( !lpData )
  {
    Value = 8;
    goto LABEL_43;
  }
  Value = RegQueryValueExW(*this, L"ReadFilter", 0, 0, lpData, (LPDWORD)&cbData);
  if ( !Value )
  {
    v12 = lpData;
    if ( *(_WORD *)lpData )
    {
      do
      {
        ++v8;
        v13 = -1;
        do
          ++v13;
        while ( *(_WORD *)&v12[2 * v13] );
        v12 += 2 * v13 + 2;
      }
      while ( *(_WORD *)v12 );
      if ( v8 )
      {
        v14 = 8LL * v8;
        if ( !is_mul_ok(v8, 8u) )
          v14 = -1;
        v15 = (unsigned __int16 **)operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
        *a3 = v15;
        if ( v15 )
        {
          memset_0(v15, 0, 8LL * v8);
          *a4 = v8;
          v17 = (const unsigned __int16 *)lpData;
          if ( *(_WORD *)lpData )
          {
            while ( 1 )
            {
              v18 = -1;
              do
                ++v18;
              while ( v17[v18] );
              v19 = -1;
              if ( v18 <= 0xFFFFFFFF )
                v19 = v18;
              LODWORD(cbData) = v19;
              v20 = v18 > 0xFFFFFFFF ? 0x80070216 : 0;
              ElValidateHrLite(v20, v16, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\regkey.cpp", 0x4B3u);
              v24 = v18 <= 0xFFFFFFFF ? (v18 > 0xFFFFFFFF ? 0x80070216 : 0) : ElValidateHr(v20, v21, v22, v23);
              if ( v24 < 0 )
                break;
              v25 = 2LL * (unsigned int)((_DWORD)cbData + 1);
              if ( !is_mul_ok((unsigned int)((_DWORD)cbData + 1), 2u) )
                v25 = -1;
              (*a3)[v4] = (unsigned __int16 *)operator new[](v25, (const struct std::nothrow_t *)&std::nothrow);
              v26 = (*a3)[v4];
              if ( !v26 )
              {
                Value = 8;
                goto LABEL_42;
              }
              v27 = StringCchCopyW(v26, (unsigned int)((_DWORD)cbData + 1), v17);
              if ( v27 < 0 )
              {
                if ( (v27 & 0x1FFF0000) == 0x70000 )
                  Value = (unsigned __int16)v27;
                else
                  Value = v27;
                goto LABEL_42;
              }
              ++v4;
              v17 += (unsigned int)((_DWORD)cbData + 1);
              if ( !*v17 )
                goto LABEL_42;
            }
            if ( v18 <= 0xFFFFFFFF || (Value = (unsigned __int16)v20, (v18 > 0xFFFFFFFF ? 0x70000 : 0) != 0x70000) )
              Value = v18 > 0xFFFFFFFF ? 0x80070216 : 0;
          }
        }
        else
        {
          Value = 8;
        }
      }
    }
  }
LABEL_42:
  operator delete(lpData);
  if ( Value )
    goto LABEL_43;
  return Value;
}

```

## disassembly

```asm
0x18003b3b8  mov     rax, rsp
0x18003b3bb  mov     [rax+18h], rbx
0x18003b3bf  mov     [rax+10h], rdx
0x18003b3c3  push    rbp
0x18003b3c4  push    rsi
0x18003b3c5  push    rdi
0x18003b3c6  push    r12
0x18003b3c8  push    r13
0x18003b3ca  push    r14
0x18003b3cc  push    r15
0x18003b3ce  sub     rsp, 30h
0x18003b3d2  xor     r13d, r13d
0x18003b3d5  lea     r14, aReadfilter; "ReadFilter"
0x18003b3dc  mov     [r9], r13d
0x18003b3df  mov     r12, r9
0x18003b3e2  mov     [r8], r13
0x18003b3e5  lea     r9, [rax+8]; lpType
0x18003b3e9  mov     r15, r8
0x18003b3ec  mov     [rax-40h], r13
0x18003b3f0  mov     rsi, rcx
0x18003b3f3  mov     [rax-48h], r13
0x18003b3f7  mov     rcx, [rcx]; hKey
0x18003b3fa  xor     r8d, r8d; lpReserved
0x18003b3fd  mov     rdx, r14; lpValueName
0x18003b400  mov     edi, r13d
0x18003b403  call    cs:__imp_RegQueryValueExW
0x18003b40a  nop     dword ptr [rax+rax+00h]
0x18003b40f  mov     ebx, eax
0x18003b411  test    eax, eax
0x18003b413  jnz     loc_18003B66D
0x18003b419  cmp     [rsp+68h+arg_0], 7
0x18003b41e  jz      short loc_18003B42A
0x18003b420  mov     ebx, 70Ch
0x18003b425  jmp     loc_18003B66D
0x18003b42a  mov     rcx, [rsi]; hKey
0x18003b42d  lea     rax, [rsp+68h+cbData]
0x18003b432  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18003b437  xor     r9d, r9d; lpType
0x18003b43a  xor     r8d, r8d; lpReserved
0x18003b43d  mov     [rsp+68h+lpData], r13; lpData
0x18003b442  mov     rdx, r14; lpValueName
0x18003b445  call    cs:__imp_RegQueryValueExW
0x18003b44c  nop     dword ptr [rax+rax+00h]
0x18003b451  mov     ebx, eax
0x18003b453  test    eax, eax
0x18003b455  jnz     loc_18003B66D
0x18003b45b  mov     eax, dword ptr [rsp+68h+cbData]
0x18003b45f  test    eax, eax
0x18003b461  jz      loc_18003B684
0x18003b467  mov     ecx, eax
0x18003b469  lea     eax, [rbx+2]
0x18003b46c  shr     rcx, 1
0x18003b46f  mul     rcx
0x18003b472  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003b479  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003b480  cmovo   rax, rcx
0x18003b484  mov     rcx, rax; unsigned __int64
0x18003b487  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003b48c  mov     rbp, rax
0x18003b48f  test    rax, rax
0x18003b492  jnz     short loc_18003B49C
0x18003b494  lea     ebx, [rax+8]
0x18003b497  jmp     loc_18003B66D
0x18003b49c  mov     rcx, [rsi]; hKey
0x18003b49f  lea     rax, [rsp+68h+cbData]
0x18003b4a4  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18003b4a9  xor     r9d, r9d; lpType
0x18003b4ac  xor     r8d, r8d; lpReserved
0x18003b4af  mov     [rsp+68h+lpData], rbp; lpData
0x18003b4b4  mov     rdx, r14; lpValueName
0x18003b4b7  call    cs:__imp_RegQueryValueExW
0x18003b4be  nop     dword ptr [rax+rax+00h]
0x18003b4c3  mov     ebx, eax
0x18003b4c5  test    eax, eax
0x18003b4c7  jnz     loc_18003B661
0x18003b4cd  mov     rax, rbp
0x18003b4d0  cmp     [rbp+0], r13w
0x18003b4d5  jz      loc_18003B661
0x18003b4db  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003b4df  inc     edi
0x18003b4e1  mov     rcx, r8
0x18003b4e4  inc     rcx
0x18003b4e7  cmp     [rax+rcx*2], r13w
0x18003b4ec  jnz     short loc_18003B4E4
0x18003b4ee  lea     rax, [rax+rcx*2]
0x18003b4f2  add     rax, 2
0x18003b4f6  cmp     [rax], r13w
0x18003b4fa  jnz     short loc_18003B4DF
0x18003b4fc  test    edi, edi
0x18003b4fe  jz      loc_18003B661
0x18003b504  mov     esi, edi
0x18003b506  mov     eax, 8
0x18003b50b  mul     rsi
0x18003b50e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003b515  cmovo   rax, r8
0x18003b519  mov     rcx, rax; unsigned __int64
0x18003b51c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003b521  mov     [r15], rax
0x18003b524  test    rax, rax
0x18003b527  jnz     short loc_18003B531
0x18003b529  lea     ebx, [rax+8]
0x18003b52c  jmp     loc_18003B661
0x18003b531  mov     r8, rsi
0x18003b534  xor     edx, edx; Val
0x18003b536  shl     r8, 3; Size
0x18003b53a  mov     rcx, rax; void *
0x18003b53d  call    memset_0
0x18003b542  mov     [r12], edi
0x18003b546  mov     r14, rbp
0x18003b549  xor     edi, edi
0x18003b54b  cmp     [rbp+0], di
0x18003b54f  jz      loc_18003B661
0x18003b555  mov     ecx, 0FFFFFFFFh
0x18003b55a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003b55e  inc     rsi
0x18003b561  cmp     [r14+rsi*2], di
0x18003b566  jnz     short loc_18003B55E
0x18003b568  cmp     rsi, rcx
0x18003b56b  lea     r8, aOnecoreBaseEco_4; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18003b572  mov     eax, ecx
0x18003b574  mov     r9d, 4B3h; unsigned int
0x18003b57a  cmovbe  eax, esi
0x18003b57d  cmp     rcx, rsi
0x18003b580  mov     dword ptr [rsp+68h+cbData], eax
0x18003b584  sbb     edi, edi
0x18003b586  and     edi, 80070216h
0x18003b58c  mov     ecx, edi; int
0x18003b58e  call    ?ElValidateHrLite@@YAJJPEBD0K@Z; ElValidateHrLite(long,char const *,char const *,ulong)
0x18003b593  mov     ecx, 0FFFFFFFFh
0x18003b598  cmp     rsi, rcx
0x18003b59b  jbe     short loc_18003B5AB
0x18003b59d  mov     ecx, edi; int
0x18003b59f  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18003b5a4  mov     ecx, 0FFFFFFFFh
0x18003b5a9  jmp     short loc_18003B5AD
0x18003b5ab  mov     eax, edi
0x18003b5ad  test    eax, eax
0x18003b5af  js      loc_18003B646
0x18003b5b5  mov     ecx, dword ptr [rsp+68h+cbData]
0x18003b5b9  mov     eax, 2
0x18003b5be  inc     ecx
0x18003b5c0  mul     rcx
0x18003b5c3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003b5ca  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003b5d1  cmovo   rax, rcx
0x18003b5d5  mov     rcx, rax; unsigned __int64
0x18003b5d8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003b5dd  mov     rcx, [r15]
0x18003b5e0  xor     edi, edi
0x18003b5e2  mov     edx, r13d
0x18003b5e5  mov     [rcx+rdx*8], rax
0x18003b5e9  mov     rax, [r15]
0x18003b5ec  mov     rcx, [rax+rdx*8]; unsigned __int16 *
0x18003b5f0  test    rcx, rcx
0x18003b5f3  jz      short loc_18003B63F
0x18003b5f5  mov     edx, dword ptr [rsp+68h+cbData]
0x18003b5f9  mov     r8, r14; unsigned __int16 *
0x18003b5fc  inc     edx; unsigned __int64
0x18003b5fe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003b603  mov     ecx, eax
0x18003b605  test    eax, eax
0x18003b607  js      short loc_18003B627
0x18003b609  mov     eax, dword ptr [rsp+68h+cbData]
0x18003b60d  inc     r13d
0x18003b610  inc     eax
0x18003b612  mov     ecx, 0FFFFFFFFh
0x18003b617  lea     r14, [r14+rax*2]
0x18003b61b  cmp     [r14], di
0x18003b61f  jnz     loc_18003B55A
0x18003b625  jmp     short loc_18003B65E
0x18003b627  and     eax, 1FFF0000h
0x18003b62c  xor     r13d, r13d
0x18003b62f  cmp     eax, 70000h
0x18003b634  jnz     short loc_18003B63B
0x18003b636  movzx   ebx, cx
0x18003b639  jmp     short loc_18003B661
0x18003b63b  mov     ebx, ecx
0x18003b63d  jmp     short loc_18003B661
0x18003b63f  mov     ebx, 8
0x18003b644  jmp     short loc_18003B65E
0x18003b646  cmp     rsi, rcx
0x18003b649  jbe     short loc_18003B65C
0x18003b64b  mov     eax, edi
0x18003b64d  movzx   ebx, di
0x18003b650  and     eax, 1FFF0000h
0x18003b655  cmp     eax, 70000h
0x18003b65a  jz      short loc_18003B65E
0x18003b65c  mov     ebx, edi
0x18003b65e  xor     r13d, r13d
0x18003b661  mov     rcx, rbp; void *
0x18003b664  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003b669  test    ebx, ebx
0x18003b66b  jz      short loc_18003B684
0x18003b66d  mov     edx, [r12]; unsigned int
0x18003b671  test    edx, edx
0x18003b673  jz      short loc_18003B684
0x18003b675  mov     rcx, [r15]; unsigned __int16 **
0x18003b678  call    ?FreeMultiSz@CRegKey@@SAKPEAPEAGK@Z; CRegKey::FreeMultiSz(ushort * *,ulong)
0x18003b67d  mov     [r12], r13d
0x18003b681  mov     [r15], r13
0x18003b684  mov     eax, ebx
0x18003b686  mov     rbx, [rsp+68h+arg_10]
0x18003b68e  add     rsp, 30h
0x18003b692  pop     r15
0x18003b694  pop     r14
0x18003b696  pop     r13
0x18003b698  pop     r12
0x18003b69a  pop     rdi
0x18003b69b  pop     rsi
0x18003b69c  pop     rbp
0x18003b69d  retn
```
