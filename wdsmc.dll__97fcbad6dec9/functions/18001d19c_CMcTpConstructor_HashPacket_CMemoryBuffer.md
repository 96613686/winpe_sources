# CMcTpConstructor::HashPacket(CMemoryBuffer *)

- ea: `0x18001d19c`
- end: `0x18001d350`
- name: `?HashPacket@CMcTpConstructor@@AEAAKPEAVCMemoryBuffer@@@Z`
- size: `436`
- prototype: `unsigned int __fastcall(CMcTpConstructor *__hidden this, struct CMemoryBuffer *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d4f4`

## callees

- `0x18001a9a8`
- `0x18001d19c`
- `0x1800227d4`
- `0x180025850`
- `0x180025f3c`
- `0x180025f94`
- `0x18002607c`
- `0x180026d3a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001d275`
- `KERNEL32!GetLastError` at `0x18001d275`
- `ADVAPI32!CryptHashData` at `0x18001d26b`
- `ADVAPI32!CryptHashData` at `0x18001d26b`
- `WS2_32!__imp_htons` at `0x18001d305`
- `WS2_32!__imp_htons` at `0x18001d305`

## string_xrefs

- `0x18001d1f0`: `((((m_uSecurityMode) & 0xffff) == (1)) || ((((m_uSecurityMode)>>16)&0xffff) == (1)))`

## pseudocode

```c
__int64 __fastcall CMcTpConstructor::HashPacket(CMcTpConstructor *this, struct CMemoryBuffer *a2, __int64 a3, int a4)
{
  int v5; // ecx
  __int64 v7; // rax
  __int64 v8; // r14
  DWORD v9; // r15d
  const BYTE *v10; // rsi
  struct CCryptKey *v11; // r8
  struct CCryptStore *v12; // rdx
  unsigned int Hash; // edi
  const char *v14; // rdx
  const char *v15; // rdx
  DWORD LastError; // eax
  const char *v17; // rdx
  const char *v18; // rdx
  unsigned int v19; // eax
  int v20; // r9d
  void *v21; // rsi
  size_t v22; // r15
  u_short v23; // cx
  __int64 v25; // [rsp+30h] [rbp-10h] BYREF
  HCRYPTHASH hHash; // [rsp+38h] [rbp-8h]
  size_t Size; // [rsp+70h] [rbp+30h] BYREF
  void *Src; // [rsp+78h] [rbp+38h] BYREF

  Src = 0;
  LODWORD(Size) = 0;
  v5 = *(_DWORD *)this;
  v25 = 0;
  hHash = 0;
  if ( (unsigned __int16)v5 != 1 && HIWORD(v5) != 1 )
    WdsAssert(
      "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp",
      0x393u,
      "((((m_uSecurityMode) & 0xffff) == (1)) || ((((m_uSecurityMode)>>16)&0xffff) == (1)))",
      a4,
      0);
  v7 = *((unsigned int *)this + 25);
  v8 = *((_QWORD *)a2 + 5);
  v9 = *((_DWORD *)a2 + 12) - v7;
  v10 = (const BYTE *)(v8 + v7);
  if ( *((_DWORD *)this + 24) )
  {
    v11 = (struct CCryptKey *)*((_QWORD *)this + 3);
    v12 = (struct CCryptStore *)*((_QWORD *)v11 + 1);
  }
  else
  {
    v12 = (CMcTpConstructor *)((char *)this + 32);
    v11 = (CMcTpConstructor *)((char *)this + 64);
  }
  Hash = CCryptHMAC::CreateHash((CCryptHMAC *)&v25, v12, v11, *((_DWORD *)this + 23), *((_DWORD *)this + 22));
  if ( !ElValidateWin32(Hash, v14, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", 0x3ABu) )
  {
    Hash = 0;
    if ( !CryptHashData(hHash, v10, v9, 0) )
    {
      LastError = GetLastError();
      Hash = ElValidateWin32(LastError, v17, "base\\eco\\wds\\wdslib\\crypt\\lib\\crypthash.cpp", 0xF7u);
    }
    if ( !ElValidateWin32(Hash, v15, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", 0x3B2u) )
    {
      Hash = CCryptHash::GetHashValue((CCryptHash *)&v25, &Src, (unsigned int *)&Size);
      v19 = ElValidateWin32(Hash, v18, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", 0x3B9u);
      v21 = Src;
      if ( !v19 )
      {
        v22 = (unsigned int)Size;
        if ( (unsigned int)Size != *((unsigned int *)this + 25) - 5LL )
          WdsAssert(
            "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp",
            0x3BCu,
            "uHashLen == (m_uSecHeaderLen - (size_t)(&(((WDSMCTP_SEC_HEADER*)0)->bSecData)))",
            v20,
            0);
        v23 = Size;
        *(_BYTE *)(v8 + 2) = 2;
        *(_WORD *)(v8 + 3) = htons(v23);
        memmove_0((void *)(v8 + 5), v21, v22);
      }
      if ( v21 )
        operator delete(v21);
    }
  }
  CCryptHash::DestroyHash((CCryptHash *)&v25);
  return Hash;
}

```

## disassembly

```asm
0x18001d19c  mov     [rsp-28h+arg_10], rbx
0x18001d1a1  mov     [rsp-28h+arg_18], rsi
0x18001d1a6  push    rbp
0x18001d1a7  push    rdi
0x18001d1a8  push    r13
0x18001d1aa  push    r14
0x18001d1ac  push    r15
0x18001d1ae  mov     rbp, rsp
0x18001d1b1  sub     rsp, 40h
0x18001d1b5  and     [rbp+Src], 0
0x18001d1ba  lea     r13, aBaseEcoWdsTran_17; "base\\eco\\wds\\transport\\lib\\mctpcon"...
0x18001d1c1  and     dword ptr [rbp+Size], 0
0x18001d1c5  mov     rbx, rcx
0x18001d1c8  mov     ecx, [rcx]
0x18001d1ca  mov     rdi, rdx
0x18001d1cd  and     [rbp+var_10], 0
0x18001d1d2  mov     edx, 1
0x18001d1d7  and     [rbp+hHash], 0
0x18001d1dc  movzx   eax, cx
0x18001d1df  cmp     eax, edx
0x18001d1e1  jz      short loc_18001D204
0x18001d1e3  shr     ecx, 10h
0x18001d1e6  cmp     cx, dx
0x18001d1e9  jz      short loc_18001D204
0x18001d1eb  and     [rsp+40h+var_20], 0
0x18001d1f0  lea     r8, aMUsecuritymode; "((((m_uSecurityMode) & 0xffff) == (1)) "...
0x18001d1f7  mov     edx, 393h; unsigned int
0x18001d1fc  mov     rcx, r13; char *
0x18001d1ff  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001d204  mov     eax, [rbx+64h]
0x18001d207  mov     r14, [rdi+28h]
0x18001d20b  mov     r15d, [rdi+30h]
0x18001d20f  sub     r15d, eax
0x18001d212  cmp     dword ptr [rbx+60h], 0
0x18001d216  lea     rsi, [r14+rax]
0x18001d21a  jz      short loc_18001D226
0x18001d21c  mov     r8, [rbx+18h]
0x18001d220  mov     rdx, [r8+8]
0x18001d224  jmp     short loc_18001D22E
0x18001d226  lea     rdx, [rbx+20h]; struct CCryptStore *
0x18001d22a  lea     r8, [rbx+40h]; struct CCryptKey *
0x18001d22e  mov     eax, [rbx+58h]
0x18001d231  lea     rcx, [rbp+var_10]; this
0x18001d235  mov     r9d, [rbx+5Ch]; unsigned int
0x18001d239  mov     [rsp+40h+var_20], eax; int
0x18001d23d  call    ?CreateHash@CCryptHMAC@@QEAAKPEAVCCryptStore@@PEAVCCryptKey@@II@Z; CCryptHMAC::CreateHash(CCryptStore *,CCryptKey *,uint,uint)
0x18001d242  mov     r9d, 3ABh; unsigned int
0x18001d248  mov     r8, r13; char *
0x18001d24b  mov     ecx, eax; unsigned int
0x18001d24d  mov     edi, eax
0x18001d24f  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001d254  test    eax, eax
0x18001d256  jnz     loc_18001D32C
0x18001d25c  mov     rcx, [rbp+hHash]; hHash
0x18001d260  xor     r9d, r9d; dwFlags
0x18001d263  mov     r8d, r15d; dwDataLen
0x18001d266  mov     rdx, rsi; pbData
0x18001d269  xor     edi, edi
0x18001d26b  call    cs:__imp_CryptHashData
0x18001d271  test    eax, eax
0x18001d273  jnz     short loc_18001D291
0x18001d275  call    cs:__imp_GetLastError
0x18001d27b  mov     r9d, 0F7h; unsigned int
0x18001d281  lea     r8, aBaseEcoWdsWdsl; "base\\eco\\wds\\wdslib\\crypt\\lib\\cry"...
0x18001d288  mov     ecx, eax; unsigned int
0x18001d28a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001d28f  mov     edi, eax
0x18001d291  mov     r9d, 3B2h; unsigned int
0x18001d297  mov     r8, r13; char *
0x18001d29a  mov     ecx, edi; unsigned int
0x18001d29c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001d2a1  test    eax, eax
0x18001d2a3  jnz     loc_18001D32C
0x18001d2a9  lea     r8, [rbp+Size]; unsigned int *
0x18001d2ad  lea     rdx, [rbp+Src]; void **
0x18001d2b1  lea     rcx, [rbp+var_10]; this
0x18001d2b5  call    ?GetHashValue@CCryptHash@@QEAAKPEAPEAXPEAK@Z; CCryptHash::GetHashValue(void * *,ulong *)
0x18001d2ba  mov     r9d, 3B9h; unsigned int
0x18001d2c0  mov     r8, r13; char *
0x18001d2c3  mov     ecx, eax; unsigned int
0x18001d2c5  mov     edi, eax
0x18001d2c7  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001d2cc  mov     rsi, [rbp+Src]
0x18001d2d0  test    eax, eax
0x18001d2d2  jnz     short loc_18001D31F
0x18001d2d4  mov     edx, [rbx+64h]
0x18001d2d7  mov     r15d, dword ptr [rbp+Size]
0x18001d2db  sub     rdx, 5
0x18001d2df  cmp     r15, rdx
0x18001d2e2  jz      short loc_18001D2FC
0x18001d2e4  and     [rsp+40h+var_20], eax
0x18001d2e8  lea     r8, aUhashlenMUsech; "uHashLen == (m_uSecHeaderLen - (size_t)"...
0x18001d2ef  mov     edx, 3BCh; unsigned int
0x18001d2f4  mov     rcx, r13; char *
0x18001d2f7  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001d2fc  movzx   ecx, word ptr [rbp+Size]; hostshort
0x18001d300  mov     byte ptr [r14+2], 2
0x18001d305  call    cs:__imp_htons
0x18001d30b  lea     rcx, [r14+5]; void *
0x18001d30f  mov     r8, r15; Size
0x18001d312  mov     rdx, rsi; Src
0x18001d315  mov     [r14+3], ax
0x18001d31a  call    memmove_0
0x18001d31f  test    rsi, rsi
0x18001d322  jz      short loc_18001D32C
0x18001d324  mov     rcx, rsi; void *
0x18001d327  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d32c  lea     rcx, [rbp+var_10]; this
0x18001d330  call    ?DestroyHash@CCryptHash@@QEAAKXZ; CCryptHash::DestroyHash(void)
0x18001d335  lea     r11, [rsp+40h+var_s0]
0x18001d33a  mov     eax, edi
0x18001d33c  mov     rbx, [r11+40h]
0x18001d340  mov     rsi, [r11+48h]
0x18001d344  mov     rsp, r11
0x18001d347  pop     r15
0x18001d349  pop     r14
0x18001d34b  pop     r13
0x18001d34d  pop     rdi
0x18001d34e  pop     rbp
0x18001d34f  retn
```
