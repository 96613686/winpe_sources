# SIPObject_::CalcHashLength(ulong *,unsigned __int64,ulong)

- ea: `0x18003ecb8`
- end: `0x18003ed50`
- name: `?CalcHashLength@SIPObject_@@KAHPEAK_KK@Z`
- size: `152`
- prototype: `__int64 __fastcall(DWORD *pdwDataLen, HCRYPTPROV hProv, ALG_ID Algid)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c290`
- `0x18002159c`

## callees

- `0x18003ecb8`

## import_xrefs

- `CRYPTSP!CryptGetHashParam` at `0x18003ed28`
- `CRYPTSP!CryptGetHashParam` at `0x18003ed28`
- `CRYPTSP!CryptDestroyHash` at `0x18003ed37`
- `CRYPTSP!CryptDestroyHash` at `0x18003ed37`
- `CRYPTSP!CryptHashData` at `0x18003ed08`
- `CRYPTSP!CryptHashData` at `0x18003ed08`
- `CRYPTSP!CryptCreateHash` at `0x18003ece8`
- `CRYPTSP!CryptCreateHash` at `0x18003ece8`

## pseudocode

```c
__int64 __fastcall SIPObject_::CalcHashLength(DWORD *pdwDataLen, HCRYPTPROV hProv, ALG_ID Algid)
{
  unsigned int v4; // ebx
  HCRYPTHASH hHash; // [rsp+58h] [rbp+20h] BYREF

  hHash = 0;
  if ( !CryptCreateHash(hProv, Algid, 0, 0, &hHash) )
    return 0;
  v4 = 1;
  if ( !CryptHashData(hHash, "X", 1u, 0) || !CryptGetHashParam(hHash, 2u, 0, pdwDataLen, 0) || !CryptDestroyHash(hHash) )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x18003ecb8  mov     r11, rsp
0x18003ecbb  mov     [r11+8], rbx
0x18003ecbf  push    rdi
0x18003ecc0  sub     rsp, 30h
0x18003ecc4  mov     rdi, rcx
0x18003ecc7  mov     qword ptr [r11+20h], 0
0x18003eccf  lea     rcx, [r11+20h]
0x18003ecd3  mov     eax, r8d
0x18003ecd6  mov     r10, rdx
0x18003ecd9  mov     [r11-18h], rcx
0x18003ecdd  mov     rcx, r10; hProv
0x18003ece0  xor     r9d, r9d; dwFlags
0x18003ece3  xor     r8d, r8d; hKey
0x18003ece6  mov     edx, eax; Algid
0x18003ece8  call    cs:__imp_CryptCreateHash
0x18003ecee  test    eax, eax
0x18003ecf0  jz      short loc_18003ED41
0x18003ecf2  mov     rcx, [rsp+38h+hHash]; hHash
0x18003ecf7  lea     rdx, pbData; "X"
0x18003ecfe  xor     r9d, r9d; dwFlags
0x18003ed01  lea     ebx, [r9+1]
0x18003ed05  mov     r8d, ebx; dwDataLen
0x18003ed08  call    cs:__imp_CryptHashData
0x18003ed0e  test    eax, eax
0x18003ed10  jz      short loc_18003ED41
0x18003ed12  mov     rcx, [rsp+38h+hHash]; hHash
0x18003ed17  lea     edx, [rbx+1]; dwParam
0x18003ed1a  mov     r9, rdi; pdwDataLen
0x18003ed1d  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18003ed25  xor     r8d, r8d; pbData
0x18003ed28  call    cs:__imp_CryptGetHashParam
0x18003ed2e  test    eax, eax
0x18003ed30  jz      short loc_18003ED41
0x18003ed32  mov     rcx, [rsp+38h+hHash]; hHash
0x18003ed37  call    cs:__imp_CryptDestroyHash
0x18003ed3d  test    eax, eax
0x18003ed3f  jnz     short loc_18003ED43
0x18003ed41  xor     ebx, ebx
0x18003ed43  mov     eax, ebx
0x18003ed45  mov     rbx, [rsp+38h+arg_0]
0x18003ed4a  add     rsp, 30h
0x18003ed4e  pop     rdi
0x18003ed4f  retn
```
