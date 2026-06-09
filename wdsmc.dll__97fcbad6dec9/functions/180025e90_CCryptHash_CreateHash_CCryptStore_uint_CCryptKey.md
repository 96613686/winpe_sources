# CCryptHash::CreateHash(CCryptStore *,uint,CCryptKey *)

- ea: `0x180025e90`
- end: `0x180025f36`
- name: `?CreateHash@CCryptHash@@QEAAKPEAVCCryptStore@@IPEAVCCryptKey@@@Z`
- size: `166`
- prototype: `unsigned int(CCryptHash *__hidden this, struct CCryptStore *, unsigned int, struct CCryptKey *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18001cac4`
- `0x18001d358`
- `0x18002607c`

## callees

- `0x180025850`
- `0x180025e90`
- `0x180025f3c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180025ef8`
- `KERNEL32!GetLastError` at `0x180025ef8`
- `ADVAPI32!CryptCreateHash` at `0x180025eee`
- `ADVAPI32!CryptCreateHash` at `0x180025eee`

## pseudocode

```c
__int64 __fastcall CCryptHash::CreateHash(HCRYPTHASH *this, HCRYPTPROV *a2, ALG_ID a3, struct CCryptKey *a4)
{
  unsigned int v8; // ebx
  unsigned int v9; // eax
  const char *v10; // rdx
  HCRYPTKEY v11; // r8
  DWORD LastError; // eax
  const char *v13; // rdx

  v8 = 0;
  v9 = CCryptHash::DestroyHash((CCryptHash *)this);
  ElValidateWin32(v9, v10, "base\\eco\\wds\\wdslib\\crypt\\lib\\crypthash.cpp", 0x3Cu);
  if ( a4 )
    v11 = *((_QWORD *)a4 + 2);
  else
    v11 = 0;
  if ( CryptCreateHash(*a2, a3, v11, 0, this + 1) )
  {
    *this = (HCRYPTHASH)a2;
  }
  else
  {
    LastError = GetLastError();
    return ElValidateWin32(LastError, v13, "base\\eco\\wds\\wdslib\\crypt\\lib\\crypthash.cpp", 0x44u);
  }
  return v8;
}

```

## disassembly

```asm
0x180025e90  mov     rax, rsp
0x180025e93  mov     [rax+8], rbx
0x180025e97  mov     [rax+10h], rbp
0x180025e9b  mov     [rax+18h], rsi
0x180025e9f  mov     [rax+20h], rdi
0x180025ea3  push    r14
0x180025ea5  sub     rsp, 30h
0x180025ea9  mov     rbp, r9
0x180025eac  mov     r14d, r8d
0x180025eaf  mov     rsi, rdx
0x180025eb2  mov     rdi, rcx
0x180025eb5  xor     ebx, ebx
0x180025eb7  call    ?DestroyHash@CCryptHash@@QEAAKXZ; CCryptHash::DestroyHash(void)
0x180025ebc  mov     ecx, eax; unsigned int
0x180025ebe  lea     r9d, [rbx+3Ch]; unsigned int
0x180025ec2  lea     r8, aBaseEcoWdsWdsl; "base\\eco\\wds\\wdslib\\crypt\\lib\\cry"...
0x180025ec9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180025ece  test    rbp, rbp
0x180025ed1  jz      short loc_180025ED9
0x180025ed3  mov     r8, [rbp+10h]
0x180025ed7  jmp     short loc_180025EDC
0x180025ed9  mov     r8, rbx; hKey
0x180025edc  mov     rcx, [rsi]; hProv
0x180025edf  lea     rax, [rdi+8]
0x180025ee3  xor     r9d, r9d; dwFlags
0x180025ee6  mov     [rsp+38h+phHash], rax; phHash
0x180025eeb  mov     edx, r14d; Algid
0x180025eee  call    cs:__imp_CryptCreateHash
0x180025ef4  test    eax, eax
0x180025ef6  jnz     short loc_180025F16
0x180025ef8  call    cs:__imp_GetLastError
0x180025efe  mov     r9d, 44h ; 'D'; unsigned int
0x180025f04  lea     r8, aBaseEcoWdsWdsl; "base\\eco\\wds\\wdslib\\crypt\\lib\\cry"...
0x180025f0b  mov     ecx, eax; unsigned int
0x180025f0d  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180025f12  mov     ebx, eax
0x180025f14  jmp     short loc_180025F19
0x180025f16  mov     [rdi], rsi
0x180025f19  mov     rbp, [rsp+38h+arg_8]
0x180025f1e  mov     eax, ebx
0x180025f20  mov     rbx, [rsp+38h+arg_0]
0x180025f25  mov     rsi, [rsp+38h+arg_10]
0x180025f2a  mov     rdi, [rsp+38h+arg_18]
0x180025f2f  add     rsp, 30h
0x180025f33  pop     r14
0x180025f35  retn
```
