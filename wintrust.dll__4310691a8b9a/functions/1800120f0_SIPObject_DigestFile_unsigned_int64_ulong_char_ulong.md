# SIPObject_::DigestFile(unsigned __int64,ulong,char *,ulong *)

- ea: `0x1800120f0`
- end: `0x18001227a`
- name: `?DigestFile@SIPObject_@@MEAAPEAE_KKPEADPEAK@Z`
- size: `394`
- prototype: `unsigned __int8 *__fastcall(SIPObject_ *this, HCRYPTPROV, unsigned int, char *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800120f0`
- `0x180012280`
- `0x18001232c`
- `0x18004de6a`
- `0x18004deb0`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012242`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012242`
- `CRYPTSP!CryptDestroyHash` at `0x1800121e2`
- `CRYPTSP!CryptDestroyHash` at `0x180012251`
- `CRYPTSP!CryptDestroyHash` at `0x1800121e2`
- `CRYPTSP!CryptDestroyHash` at `0x180012251`
- `CRYPTSP!CryptHashData` at `0x180012214`
- `CRYPTSP!CryptHashData` at `0x180012214`
- `CRYPTSP!CryptCreateHash` at `0x18001218f`
- `CRYPTSP!CryptCreateHash` at `0x18001218f`
- `CRYPT32!CryptFindOIDInfo` at `0x180012150`
- `CRYPT32!CryptFindOIDInfo` at `0x180012266`
- `CRYPT32!CryptFindOIDInfo` at `0x180012150`
- `CRYPT32!CryptFindOIDInfo` at `0x180012266`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
unsigned __int8 *__fastcall SIPObject_::DigestFile(
        SIPObject_ *this,
        HCRYPTPROV a2,
        unsigned int a3,
        char *a4,
        unsigned int *a5)
{
  PCCRYPT_OID_INFO OIDInfo; // rcx
  ALG_ID dwValue; // eax
  unsigned __int8 *HashValue; // rbx
  DWORD v13; // ecx
  HCRYPTHASH hHash; // [rsp+30h] [rbp-91h] BYREF
  DWORD dwDataLen; // [rsp+38h] [rbp-89h]
  BYTE pbData[128]; // [rsp+3Ch] [rbp-85h] BYREF
  ALG_ID v17; // [rsp+BCh] [rbp-5h]

  *a5 = 0;
  if ( !a4 )
  {
    v13 = 87;
    goto LABEL_16;
  }
  memset_0(&hHash, 0, 0x98u);
  OIDInfo = CryptFindOIDInfo(1u, a4, 1u);
  if ( !OIDInfo )
  {
    OIDInfo = CryptFindOIDInfo(1u, a4, 4u);
    if ( !OIDInfo )
    {
LABEL_14:
      v13 = -2146893816;
LABEL_16:
      SetLastError(v13);
      return 0;
    }
  }
  dwValue = OIDInfo->dwValue;
  if ( dwValue == -1 )
  {
    dwValue = SIPObject_::CalgId(*(wchar_t **)&OIDInfo[1].cbSize);
    v17 = dwValue;
    if ( !dwValue )
      goto LABEL_14;
  }
  else
  {
    v17 = OIDInfo->dwValue;
  }
  if ( !a2 || !CryptCreateHash(a2, dwValue, 0, 0, &hHash) )
    return 0;
  if ( !(*(unsigned int (__fastcall **)(SIPObject_ *, HCRYPTHASH *, int (*)(void *, const unsigned __int8 *, unsigned int), _QWORD))(*(_QWORD *)this + 120LL))(
          this,
          &hHash,
          DigestFileData,
          a3) )
  {
    CryptDestroyHash(hHash);
    return 0;
  }
  if ( !dwDataLen || CryptHashData(hHash, pbData, dwDataLen, 0) )
    HashValue = SipGetHashValue((struct DIGEST_DATA *)&hHash, a5);
  else
    HashValue = 0;
  CryptDestroyHash(hHash);
  return HashValue;
}

```

## disassembly

```asm
0x1800120f0  push    rbp
0x1800120f2  push    rbx
0x1800120f3  push    rsi
0x1800120f4  push    rdi
0x1800120f5  push    r14
0x1800120f7  push    r15
0x1800120f9  lea     rbp, [rsp-27h]
0x1800120fe  sub     rsp, 0E8h
0x180012105  mov     rax, cs:__security_cookie
0x18001210c  xor     rax, rsp
0x18001210f  mov     [rbp+4Fh+var_40], rax
0x180012113  mov     rsi, [rbp+4Fh+arg_20]
0x180012117  mov     rbx, r9
0x18001211a  mov     r15d, r8d
0x18001211d  mov     rdi, rdx
0x180012120  mov     r14, rcx
0x180012123  mov     dword ptr [rsi], 0
0x180012129  test    r9, r9
0x18001212c  jz      loc_18001223D
0x180012132  xor     edx, edx; Val
0x180012134  lea     rcx, [rsp+110h+hHash]; void *
0x180012139  mov     r8d, 98h; Size
0x18001213f  call    memset_0
0x180012144  mov     r8d, 1; dwGroupId
0x18001214a  mov     rdx, rbx; pvKey
0x18001214d  mov     ecx, r8d; dwKeyType
0x180012150  call    cs:__imp_CryptFindOIDInfo
0x180012156  mov     rcx, rax
0x180012159  test    rax, rax
0x18001215c  jz      loc_180012259
0x180012162  mov     eax, [rcx+1Ch]
0x180012165  cmp     eax, 0FFFFFFFFh
0x180012168  jz      loc_180012222
0x18001216e  mov     [rbp+4Fh+var_54], eax
0x180012171  test    rdi, rdi
0x180012174  jz      loc_180012248
0x18001217a  lea     rcx, [rsp+110h+hHash]
0x18001217f  xor     r9d, r9d; dwFlags
0x180012182  mov     [rsp+110h+phHash], rcx; phHash
0x180012187  xor     r8d, r8d; hKey
0x18001218a  mov     rcx, rdi; hProv
0x18001218d  mov     edx, eax; Algid
0x18001218f  call    cs:__imp_CryptCreateHash
0x180012195  test    eax, eax
0x180012197  jz      loc_180012248
0x18001219d  mov     rax, [r14]
0x1800121a0  lea     r8, ?DigestFileData@@YAHPEAXPEBEK@Z; DigestFileData(void *,uchar const *,ulong)
0x1800121a7  mov     r9d, r15d
0x1800121aa  lea     rdx, [rsp+110h+hHash]
0x1800121af  mov     rcx, r14
0x1800121b2  mov     rax, [rax+78h]
0x1800121b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121bb  test    eax, eax
0x1800121bd  jz      loc_18001224C
0x1800121c3  mov     r8d, [rsp+110h+dwDataLen]; dwDataLen
0x1800121c8  test    r8d, r8d
0x1800121cb  jnz     short loc_180012207
0x1800121cd  mov     rdx, rsi; unsigned int *
0x1800121d0  lea     rcx, [rsp+110h+hHash]; struct DIGEST_DATA *
0x1800121d5  call    ?SipGetHashValue@@YAPEAEPEAUDIGEST_DATA@@PEAK@Z; SipGetHashValue(DIGEST_DATA *,ulong *)
0x1800121da  mov     rbx, rax
0x1800121dd  mov     rcx, [rsp+110h+hHash]; hHash
0x1800121e2  call    cs:__imp_CryptDestroyHash
0x1800121e8  mov     rax, rbx
0x1800121eb  mov     rcx, [rbp+4Fh+var_40]
0x1800121ef  xor     rcx, rsp; StackCookie
0x1800121f2  call    __security_check_cookie
0x1800121f7  add     rsp, 0E8h
0x1800121fe  pop     r15
0x180012200  pop     r14
0x180012202  pop     rdi
0x180012203  pop     rsi
0x180012204  pop     rbx
0x180012205  pop     rbp
0x180012206  retn
0x180012207  mov     rcx, [rsp+110h+hHash]; hHash
0x18001220c  lea     rdx, [rsp+110h+pbData]; pbData
0x180012211  xor     r9d, r9d; dwFlags
0x180012214  call    cs:__imp_CryptHashData
0x18001221a  test    eax, eax
0x18001221c  jnz     short loc_1800121CD
0x18001221e  xor     ebx, ebx
0x180012220  jmp     short loc_1800121DD
0x180012222  mov     rcx, [rcx+30h]; String1
0x180012226  call    ?CalgId@SIPObject_@@KAIPEBG@Z; SIPObject_::CalgId(ushort const *)
0x18001222b  mov     [rbp+4Fh+var_54], eax
0x18001222e  test    eax, eax
0x180012230  jnz     loc_180012171
0x180012236  mov     ecx, 80090008h
0x18001223b  jmp     short loc_180012242
0x18001223d  mov     ecx, 57h ; 'W'; dwErrCode
0x180012242  call    cs:__imp_SetLastError
0x180012248  xor     eax, eax
0x18001224a  jmp     short loc_1800121EB
0x18001224c  mov     rcx, [rsp+110h+hHash]; hHash
0x180012251  call    cs:__imp_CryptDestroyHash
0x180012257  jmp     short loc_180012248
0x180012259  mov     r8d, 4; dwGroupId
0x18001225f  mov     rdx, rbx; pvKey
0x180012262  lea     ecx, [r8-3]; dwKeyType
0x180012266  call    cs:__imp_CryptFindOIDInfo
0x18001226c  mov     rcx, rax
0x18001226f  test    rax, rax
0x180012272  jnz     loc_180012162
0x180012278  jmp     short loc_180012236
```
