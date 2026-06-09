# CMcTpConstructor::SignPacket(CMemoryBuffer *)

- ea: `0x18001d358`
- end: `0x18001d4ed`
- name: `?SignPacket@CMcTpConstructor@@AEAAKPEAVCMemoryBuffer@@@Z`
- size: `405`
- prototype: `unsigned int __fastcall(CMcTpConstructor *__hidden this, struct CMemoryBuffer *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d4f4`

## callees

- `0x18001a9a8`
- `0x18001d358`
- `0x1800227d4`
- `0x180025850`
- `0x180025d8c`
- `0x180025e90`
- `0x180025f3c`
- `0x180026d3a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001d411`
- `KERNEL32!GetLastError` at `0x18001d411`
- `ADVAPI32!CryptHashData` at `0x18001d407`
- `ADVAPI32!CryptHashData` at `0x18001d407`
- `WS2_32!__imp_htons` at `0x18001d4a2`
- `WS2_32!__imp_htons` at `0x18001d4a2`

## string_xrefs

- `0x18001d3a3`: `(m_bServerMode) && ((((m_uSecurityMode)>>16)&0xffff) == 2)`

## pseudocode

```c
__int64 __fastcall CMcTpConstructor::SignPacket(CMcTpConstructor *this, struct CMemoryBuffer *a2, __int64 a3, int a4)
{
  __int64 v6; // r15
  DWORD v7; // esi
  __int64 v8; // r14
  unsigned int v9; // ebx
  const char *v10; // rdx
  const char *v11; // rdx
  DWORD LastError; // eax
  const char *v13; // rdx
  CCryptSignKey *v14; // rcx
  const char *v15; // rdx
  unsigned int v16; // eax
  int v17; // r9d
  void *v18; // rsi
  size_t v19; // r15
  u_short v20; // cx
  HCRYPTHASH v22; // [rsp+30h] [rbp-10h] BYREF
  HCRYPTHASH hHash; // [rsp+38h] [rbp-8h]
  size_t Size; // [rsp+70h] [rbp+30h] BYREF
  void *Src; // [rsp+78h] [rbp+38h] BYREF

  Src = 0;
  LODWORD(Size) = 0;
  v22 = 0;
  hHash = 0;
  if ( !*((_DWORD *)this + 24) || *((_WORD *)this + 1) != 2 )
    WdsAssert(
      "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp",
      0x3E5u,
      "(m_bServerMode) && ((((m_uSecurityMode)>>16)&0xffff) == 2)",
      a4,
      0);
  v6 = *((unsigned int *)this + 25);
  v7 = *((_DWORD *)a2 + 12) - v6;
  v8 = *((_QWORD *)a2 + 5);
  v9 = CCryptHash::CreateHash(&v22, *(HCRYPTPROV **)(*((_QWORD *)this + 2) + 8LL), *((_DWORD *)this + 22), 0);
  if ( !ElValidateWin32(v9, v10, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", 0x3F1u) )
  {
    v9 = 0;
    if ( !CryptHashData(hHash, (const BYTE *)(v8 + v6), v7, 0) )
    {
      LastError = GetLastError();
      v9 = ElValidateWin32(LastError, v13, "base\\eco\\wds\\wdslib\\crypt\\lib\\crypthash.cpp", 0xF7u);
    }
    if ( !ElValidateWin32(v9, v11, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", 0x3F8u) )
    {
      v9 = CCryptSignKey::SignHash(v14, (struct CCryptHash *)&v22, &Src, (unsigned int *)&Size);
      v16 = ElValidateWin32(v9, v15, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", 0x3FFu);
      v18 = Src;
      if ( !v16 )
      {
        v19 = (unsigned int)Size;
        if ( (unsigned int)Size != *((unsigned int *)this + 25) - 5LL )
          WdsAssert(
            "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp",
            0x402u,
            "uSignLen == (m_uSecHeaderLen - (size_t)(&(((WDSMCTP_SEC_HEADER*)0)->bSecData)))",
            v17,
            0);
        v20 = Size;
        *(_BYTE *)(v8 + 2) = 1;
        *(_WORD *)(v8 + 3) = htons(v20);
        memmove_0((void *)(v8 + 5), v18, v19);
      }
      if ( v18 )
        operator delete(v18);
    }
  }
  CCryptHash::DestroyHash((CCryptHash *)&v22);
  return v9;
}

```

## disassembly

```asm
0x18001d358  mov     [rsp-28h+arg_10], rbx
0x18001d35d  mov     [rsp-28h+arg_18], rsi
0x18001d362  push    rbp
0x18001d363  push    rdi
0x18001d364  push    r13
0x18001d366  push    r14
0x18001d368  push    r15
0x18001d36a  mov     rbp, rsp
0x18001d36d  sub     rsp, 40h
0x18001d371  and     [rbp+Src], 0
0x18001d376  lea     r13, aBaseEcoWdsTran_17; "base\\eco\\wds\\transport\\lib\\mctpcon"...
0x18001d37d  and     dword ptr [rbp+Size], 0
0x18001d381  mov     rbx, rdx
0x18001d384  and     [rbp+var_10], 0
0x18001d389  mov     rdi, rcx
0x18001d38c  and     [rbp+hHash], 0
0x18001d391  cmp     dword ptr [rcx+60h], 0
0x18001d395  jz      short loc_18001D39E
0x18001d397  cmp     word ptr [rcx+2], 2
0x18001d39c  jz      short loc_18001D3B7
0x18001d39e  and     [rsp+40h+var_20], 0
0x18001d3a3  lea     r8, aMBservermodeMU; "(m_bServerMode) && ((((m_uSecurityMode)"...
0x18001d3aa  mov     edx, 3E5h; unsigned int
0x18001d3af  mov     rcx, r13; char *
0x18001d3b2  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001d3b7  mov     rax, [rdi+10h]
0x18001d3bb  lea     rcx, [rbp+var_10]; this
0x18001d3bf  mov     r15d, [rdi+64h]
0x18001d3c3  xor     r9d, r9d; struct CCryptKey *
0x18001d3c6  mov     esi, [rbx+30h]
0x18001d3c9  mov     r8d, [rdi+58h]; unsigned int
0x18001d3cd  sub     esi, r15d
0x18001d3d0  mov     rdx, [rax+8]; struct CCryptStore *
0x18001d3d4  mov     r14, [rbx+28h]
0x18001d3d8  call    ?CreateHash@CCryptHash@@QEAAKPEAVCCryptStore@@IPEAVCCryptKey@@@Z; CCryptHash::CreateHash(CCryptStore *,uint,CCryptKey *)
0x18001d3dd  mov     r9d, 3F1h; unsigned int
0x18001d3e3  mov     r8, r13; char *
0x18001d3e6  mov     ecx, eax; unsigned int
0x18001d3e8  mov     ebx, eax
0x18001d3ea  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001d3ef  test    eax, eax
0x18001d3f1  jnz     loc_18001D4C9
0x18001d3f7  mov     rcx, [rbp+hHash]; hHash
0x18001d3fb  lea     rdx, [r14+r15]; pbData
0x18001d3ff  xor     r9d, r9d; dwFlags
0x18001d402  mov     r8d, esi; dwDataLen
0x18001d405  xor     ebx, ebx
0x18001d407  call    cs:__imp_CryptHashData
0x18001d40d  test    eax, eax
0x18001d40f  jnz     short loc_18001D42D
0x18001d411  call    cs:__imp_GetLastError
0x18001d417  mov     r9d, 0F7h; unsigned int
0x18001d41d  lea     r8, aBaseEcoWdsWdsl; "base\\eco\\wds\\wdslib\\crypt\\lib\\cry"...
0x18001d424  mov     ecx, eax; unsigned int
0x18001d426  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001d42b  mov     ebx, eax
0x18001d42d  mov     r9d, 3F8h; unsigned int
0x18001d433  mov     r8, r13; char *
0x18001d436  mov     ecx, ebx; unsigned int
0x18001d438  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001d43d  test    eax, eax
0x18001d43f  jnz     loc_18001D4C9
0x18001d445  lea     r9, [rbp+Size]; unsigned int *
0x18001d449  lea     r8, [rbp+Src]; void **
0x18001d44d  lea     rdx, [rbp+var_10]; struct CCryptHash *
0x18001d451  call    ?SignHash@CCryptSignKey@@QEAAKPEAVCCryptHash@@PEAPEAXPEAK@Z; CCryptSignKey::SignHash(CCryptHash *,void * *,ulong *)
0x18001d456  mov     r9d, 3FFh; unsigned int
0x18001d45c  mov     r8, r13; char *
0x18001d45f  mov     ecx, eax; unsigned int
0x18001d461  mov     ebx, eax
0x18001d463  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001d468  mov     rsi, [rbp+Src]
0x18001d46c  test    eax, eax
0x18001d46e  jnz     short loc_18001D4BC
0x18001d470  mov     eax, [rdi+64h]
0x18001d473  mov     r15d, dword ptr [rbp+Size]
0x18001d477  sub     rax, 5
0x18001d47b  cmp     r15, rax
0x18001d47e  jz      short loc_18001D499
0x18001d480  and     [rsp+40h+var_20], 0
0x18001d485  lea     r8, aUsignlenMUsech; "uSignLen == (m_uSecHeaderLen - (size_t)"...
0x18001d48c  mov     edx, 402h; unsigned int
0x18001d491  mov     rcx, r13; char *
0x18001d494  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001d499  movzx   ecx, word ptr [rbp+Size]; hostshort
0x18001d49d  mov     byte ptr [r14+2], 1
0x18001d4a2  call    cs:__imp_htons
0x18001d4a8  lea     rcx, [r14+5]; void *
0x18001d4ac  mov     r8, r15; Size
0x18001d4af  mov     rdx, rsi; Src
0x18001d4b2  mov     [r14+3], ax
0x18001d4b7  call    memmove_0
0x18001d4bc  test    rsi, rsi
0x18001d4bf  jz      short loc_18001D4C9
0x18001d4c1  mov     rcx, rsi; void *
0x18001d4c4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d4c9  lea     rcx, [rbp+var_10]; this
0x18001d4cd  call    ?DestroyHash@CCryptHash@@QEAAKXZ; CCryptHash::DestroyHash(void)
0x18001d4d2  lea     r11, [rsp+40h+var_s0]
0x18001d4d7  mov     eax, ebx
0x18001d4d9  mov     rbx, [r11+40h]
0x18001d4dd  mov     rsi, [r11+48h]
0x18001d4e1  mov     rsp, r11
0x18001d4e4  pop     r15
0x18001d4e6  pop     r14
0x18001d4e8  pop     r13
0x18001d4ea  pop     rdi
0x18001d4eb  pop     rbp
0x18001d4ec  retn
```
