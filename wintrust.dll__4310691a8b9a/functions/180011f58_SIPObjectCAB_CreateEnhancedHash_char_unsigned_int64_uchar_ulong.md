# SIPObjectCAB_::CreateEnhancedHash(char *,unsigned __int64,uchar * *,ulong *)

- ea: `0x180011f58`
- end: `0x18001203d`
- name: `?CreateEnhancedHash@SIPObjectCAB_@@AEAAHPEAD_KPEAPEAEPEAK@Z`
- size: `229`
- prototype: `__int64 __fastcall(const BYTE *this, char *, HCRYPTPROV, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180011c80`
- `0x18001238c`

## callees

- `0x180011f58`
- `0x180012044`
- `0x180012280`
- `0x18004de6a`
- `0x18004deb0`

## import_xrefs

- `CRYPTSP!CryptDestroyHash` at `0x180012017`
- `CRYPTSP!CryptDestroyHash` at `0x180012017`
- `CRYPTSP!CryptHashData` at `0x180011fea`
- `CRYPTSP!CryptHashData` at `0x180011fea`
- `CRYPTSP!CryptCreateHash` at `0x180011fd0`
- `CRYPTSP!CryptCreateHash` at `0x180011fd0`

## pseudocode

```c
__int64 __fastcall SIPObjectCAB_::CreateEnhancedHash(
        const BYTE *this,
        char *a2,
        HCRYPTPROV a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  unsigned int v9; // ebx
  unsigned __int8 *HashValue; // rax
  HCRYPTHASH hHash[17]; // [rsp+30h] [rbp-D8h] BYREF
  ALG_ID Algid; // [rsp+BCh] [rbp-4Ch]

  memset_0(hHash, 0, 0x98u);
  v9 = SIPObject_::BuildDataDigest(a2, (struct DIGEST_DATA *)hHash);
  if ( v9 )
  {
    if ( !a3
      || !CryptCreateHash(a3, Algid, 0, 0, hHash)
      || (v9 = CryptHashData(hHash[0], this + 88, 4u, 0)) != 0
      && (HashValue = SipGetHashValue((struct DIGEST_DATA *)hHash, a5), (*a4 = HashValue) == 0) )
    {
      v9 = 0;
    }
  }
  if ( hHash[0] )
    CryptDestroyHash(hHash[0]);
  return v9;
}

```

## disassembly

```asm
0x180011f58  push    rbx
0x180011f5a  push    rbp
0x180011f5b  push    rsi
0x180011f5c  push    rdi
0x180011f5d  push    r14
0x180011f5f  sub     rsp, 0E0h
0x180011f66  mov     rax, cs:__security_cookie
0x180011f6d  xor     rax, rsp
0x180011f70  mov     [rsp+108h+var_38], rax
0x180011f78  mov     rbp, [rsp+108h+arg_20]
0x180011f80  mov     rdi, r8
0x180011f83  mov     rbx, rdx
0x180011f86  mov     r14, rcx
0x180011f89  xor     edx, edx; Val
0x180011f8b  lea     rcx, [rsp+108h+hHash]; void *
0x180011f90  mov     r8d, 98h; Size
0x180011f96  mov     rsi, r9
0x180011f99  call    memset_0
0x180011f9e  lea     rdx, [rsp+108h+hHash]; struct DIGEST_DATA *
0x180011fa3  mov     rcx, rbx; pvKey
0x180011fa6  call    ?BuildDataDigest@SIPObject_@@KAHPEADPEAUDIGEST_DATA@@@Z; SIPObject_::BuildDataDigest(char *,DIGEST_DATA *)
0x180011fab  mov     ebx, eax
0x180011fad  test    eax, eax
0x180011faf  jz      short loc_18001200D
0x180011fb1  test    rdi, rdi
0x180011fb4  jz      short loc_18001200B
0x180011fb6  mov     edx, [rsp+108h+Algid]; Algid
0x180011fbd  lea     rax, [rsp+108h+hHash]
0x180011fc2  xor     r9d, r9d; dwFlags
0x180011fc5  mov     [rsp+108h+phHash], rax; phHash
0x180011fca  xor     r8d, r8d; hKey
0x180011fcd  mov     rcx, rdi; hProv
0x180011fd0  call    cs:__imp_CryptCreateHash
0x180011fd6  test    eax, eax
0x180011fd8  jz      short loc_18001200B
0x180011fda  mov     rcx, [rsp+108h+hHash]; hHash
0x180011fdf  lea     rdx, [r14+58h]; pbData
0x180011fe3  xor     r9d, r9d; dwFlags
0x180011fe6  lea     r8d, [r9+4]; dwDataLen
0x180011fea  call    cs:__imp_CryptHashData
0x180011ff0  mov     ebx, eax
0x180011ff2  test    eax, eax
0x180011ff4  jz      short loc_18001200D
0x180011ff6  mov     rdx, rbp; unsigned int *
0x180011ff9  lea     rcx, [rsp+108h+hHash]; struct DIGEST_DATA *
0x180011ffe  call    ?SipGetHashValue@@YAPEAEPEAUDIGEST_DATA@@PEAK@Z; SipGetHashValue(DIGEST_DATA *,ulong *)
0x180012003  mov     [rsi], rax
0x180012006  test    rax, rax
0x180012009  jnz     short loc_18001200D
0x18001200b  xor     ebx, ebx
0x18001200d  mov     rcx, [rsp+108h+hHash]; hHash
0x180012012  test    rcx, rcx
0x180012015  jz      short loc_18001201D
0x180012017  call    cs:__imp_CryptDestroyHash
0x18001201d  mov     eax, ebx
0x18001201f  mov     rcx, [rsp+108h+var_38]
0x180012027  xor     rcx, rsp; StackCookie
0x18001202a  call    __security_check_cookie
0x18001202f  add     rsp, 0E0h
0x180012036  pop     r14
0x180012038  pop     rdi
0x180012039  pop     rsi
0x18001203a  pop     rbp
0x18001203b  pop     rbx
0x18001203c  retn
```
