# CCryptHMAC::CreateHash(CCryptStore *,CCryptKey *,uint,uint)

- ea: `0x18002607c`
- end: `0x180026143`
- name: `?CreateHash@CCryptHMAC@@QEAAKPEAVCCryptStore@@PEAVCCryptKey@@II@Z`
- size: `199`
- prototype: `unsigned int __fastcall(CCryptHMAC *__hidden this, struct CCryptStore *, struct CCryptKey *, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18001cac4`
- `0x18001ce5c`
- `0x18001d19c`

## callees

- `0x180025850`
- `0x180025e90`
- `0x18002607c`
- `0x180026d46`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800260fc`
- `KERNEL32!GetLastError` at `0x1800260fc`
- `ADVAPI32!CryptSetHashParam` at `0x1800260f2`
- `ADVAPI32!CryptSetHashParam` at `0x1800260f2`

## pseudocode

```c
__int64 __fastcall CCryptHMAC::CreateHash(
        HCRYPTHASH *this,
        HCRYPTPROV *a2,
        struct CCryptKey *a3,
        ALG_ID a4,
        unsigned int a5)
{
  unsigned int Hash; // ebx
  const char *v10; // rdx
  HCRYPTHASH v11; // rcx
  const char *v12; // rdx
  DWORD LastError; // eax
  const char *v14; // rdx
  BYTE pbData[56]; // [rsp+20h] [rbp-38h] BYREF

  memset_0(pbData, 0, 0x28u);
  Hash = CCryptHash::CreateHash(this, a2, a4, a3);
  if ( !ElValidateWin32(Hash, v10, "base\\eco\\wds\\wdslib\\crypt\\lib\\crypthmac.cpp", 0x40u) )
  {
    v11 = this[1];
    Hash = 0;
    *(_DWORD *)pbData = a5;
    if ( !CryptSetHashParam(v11, 5u, pbData, 0) )
    {
      LastError = GetLastError();
      Hash = ElValidateWin32(LastError, v14, "base\\eco\\wds\\wdslib\\crypt\\lib\\crypthash.cpp", 0x89u);
    }
    ElValidateWin32(Hash, v12, "base\\eco\\wds\\wdslib\\crypt\\lib\\crypthmac.cpp", 0x48u);
  }
  return Hash;
}

```

## disassembly

```asm
0x18002607c  mov     rax, rsp
0x18002607f  mov     [rax+8], rbx
0x180026083  mov     [rax+10h], rbp
0x180026087  mov     [rax+18h], rsi
0x18002608b  push    rdi
0x18002608c  sub     rsp, 50h
0x180026090  mov     rdi, rdx
0x180026093  mov     rbx, r8
0x180026096  xor     edx, edx; Val
0x180026098  mov     rbp, rcx
0x18002609b  lea     rcx, [rax-38h]; void *
0x18002609f  mov     esi, r9d
0x1800260a2  lea     r8d, [rdx+28h]; Size
0x1800260a6  call    memset_0
0x1800260ab  mov     r9, rbx; struct CCryptKey *
0x1800260ae  mov     r8d, esi; unsigned int
0x1800260b1  mov     rdx, rdi; struct CCryptStore *
0x1800260b4  mov     rcx, rbp; this
0x1800260b7  call    ?CreateHash@CCryptHash@@QEAAKPEAVCCryptStore@@IPEAVCCryptKey@@@Z; CCryptHash::CreateHash(CCryptStore *,uint,CCryptKey *)
0x1800260bc  mov     r9d, 40h ; '@'; unsigned int
0x1800260c2  lea     r8, aBaseEcoWdsWdsl_2; "base\\eco\\wds\\wdslib\\crypt\\lib\\cry"...
0x1800260c9  mov     ecx, eax; unsigned int
0x1800260cb  mov     ebx, eax
0x1800260cd  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800260d2  test    eax, eax
0x1800260d4  jnz     short loc_18002612C
0x1800260d6  mov     eax, [rsp+58h+arg_20]
0x1800260dd  lea     r8, [rsp+58h+pbData]; pbData
0x1800260e2  mov     rcx, [rbp+8]; hHash
0x1800260e6  xor     ebx, ebx
0x1800260e8  xor     r9d, r9d; dwFlags
0x1800260eb  mov     dword ptr [rsp+58h+pbData], eax
0x1800260ef  lea     edx, [rbx+5]; dwParam
0x1800260f2  call    cs:__imp_CryptSetHashParam
0x1800260f8  test    eax, eax
0x1800260fa  jnz     short loc_180026118
0x1800260fc  call    cs:__imp_GetLastError
0x180026102  mov     r9d, 89h; unsigned int
0x180026108  lea     r8, aBaseEcoWdsWdsl; "base\\eco\\wds\\wdslib\\crypt\\lib\\cry"...
0x18002610f  mov     ecx, eax; unsigned int
0x180026111  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180026116  mov     ebx, eax
0x180026118  mov     r9d, 48h ; 'H'; unsigned int
0x18002611e  lea     r8, aBaseEcoWdsWdsl_2; "base\\eco\\wds\\wdslib\\crypt\\lib\\cry"...
0x180026125  mov     ecx, ebx; unsigned int
0x180026127  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18002612c  mov     rbp, [rsp+58h+arg_8]
0x180026131  mov     eax, ebx
0x180026133  mov     rbx, [rsp+58h+arg_0]
0x180026138  mov     rsi, [rsp+58h+arg_10]
0x18002613d  add     rsp, 50h
0x180026141  pop     rdi
0x180026142  retn
```
