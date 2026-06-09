# HashStreamMD5(IStream *,_GUID *)

- ea: `0x18008f9fc`
- end: `0x18008fbca`
- name: `?HashStreamMD5@@YAJPEAUIStream@@PEAU_GUID@@@Z`
- size: `462`
- prototype: `__int64 __fastcall(struct IStream *, struct _GUID *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18007c810`
- `0x18007d7b0`
- `0x18007e590`

## callees

- `0x180005d08`
- `0x18008f9fc`
- `0x180091eaa`
- `0x180091ef0`
- `0x180091f80`
- `0x180093010`

## import_xrefs

- `ADVAPI32!CryptAcquireContextW` at `0x18008faa1`
- `ADVAPI32!CryptAcquireContextW` at `0x18008faa1`
- `ADVAPI32!CryptCreateHash` at `0x18008fad1`
- `ADVAPI32!CryptCreateHash` at `0x18008fad1`
- `ADVAPI32!CryptHashData` at `0x18008fb17`
- `ADVAPI32!CryptHashData` at `0x18008fb17`
- `ADVAPI32!CryptGetHashParam` at `0x18008fb4a`
- `ADVAPI32!CryptGetHashParam` at `0x18008fb4a`
- `ADVAPI32!CryptDestroyHash` at `0x18008fb85`
- `ADVAPI32!CryptDestroyHash` at `0x18008fb85`
- `ADVAPI32!CryptReleaseContext` at `0x18008fba0`
- `ADVAPI32!CryptReleaseContext` at `0x18008fba0`

## pseudocode

```c
__int64 __fastcall HashStreamMD5(struct IStream *a1, BYTE *a2)
{
  __int64 v4; // rax
  int LastError; // ebx
  DWORD dwDataLen; // [rsp+30h] [rbp-D0h] BYREF
  HCRYPTHASH phHash; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v9; // [rsp+40h] [rbp-C0h]
  HCRYPTPROV phProv; // [rsp+48h] [rbp-B8h] BYREF
  BYTE pbData[4096]; // [rsp+50h] [rbp-B0h] BYREF

  phProv = 0;
  phHash = 0;
  memset_0(pbData, 0, sizeof(pbData));
  v4 = *(_QWORD *)a1;
  v9 = 0;
  dwDataLen = 0;
  LastError = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, _QWORD, _QWORD))(v4 + 40))(a1, 0, 0, 0);
  if ( LastError >= 0 )
  {
    if ( CryptAcquireContextW(&phProv, 0, 0, 1u, 0xF0000000) && CryptCreateHash(phProv, 0x8003u, 0, 0, &phHash) )
    {
      while ( 1 )
      {
        LastError = (*(__int64 (__fastcall **)(struct IStream *, BYTE *, __int64, DWORD *))(*(_QWORD *)a1 + 24LL))(
                      a1,
                      pbData,
                      4096,
                      &dwDataLen);
        if ( LastError < 0 )
          break;
        if ( dwDataLen )
        {
          if ( !CryptHashData(phHash, pbData, dwDataLen, 0) )
            goto LABEL_3;
          if ( dwDataLen )
            continue;
        }
        dwDataLen = 16;
        if ( !CryptGetHashParam(phHash, 2u, a2, &dwDataLen, 0) )
          goto LABEL_3;
        LastError = (*(__int64 (__fastcall **)(struct IStream *, __int64, _QWORD, _QWORD))(*(_QWORD *)a1 + 40LL))(
                      a1,
                      v9,
                      0,
                      0);
        if ( LastError >= 0 )
          LastError = 0;
        break;
      }
    }
    else
    {
LABEL_3:
      LastError = HrGetLastError();
    }
  }
  if ( phHash )
  {
    CryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18008f9fc  mov     [rsp-8+arg_10], rbx
0x18008fa01  push    rbp
0x18008fa02  push    rsi
0x18008fa03  push    rdi
0x18008fa04  lea     rbp, [rsp-0F60h]
0x18008fa0c  mov     eax, 1060h
0x18008fa11  call    _alloca_probe
0x18008fa16  sub     rsp, rax
0x18008fa19  mov     rax, cs:__security_cookie
0x18008fa20  xor     rax, rsp
0x18008fa23  mov     [rbp+0F70h+var_20], rax
0x18008fa2a  mov     rsi, rdx
0x18008fa2d  mov     [rsp+1070h+phProv], 0
0x18008fa36  mov     rdi, rcx
0x18008fa39  mov     [rsp+1070h+phHash], 0
0x18008fa42  xor     edx, edx; Val
0x18008fa44  lea     rcx, [rsp+1070h+pbData]; void *
0x18008fa49  mov     r8d, 1000h; Size
0x18008fa4f  call    memset_0
0x18008fa54  mov     rax, [rdi]
0x18008fa57  xor     r9d, r9d
0x18008fa5a  mov     [rsp+1070h+var_1030], 0
0x18008fa63  xor     r8d, r8d
0x18008fa66  mov     rdx, [rsp+1070h+var_1030]
0x18008fa6b  mov     rcx, rdi
0x18008fa6e  mov     [rsp+1070h+dwDataLen], 0
0x18008fa76  mov     rax, [rax+28h]
0x18008fa7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fa7f  mov     ebx, eax
0x18008fa81  test    eax, eax
0x18008fa83  js      loc_18008FB7B
0x18008fa89  mov     r9d, 1; dwProvType
0x18008fa8f  mov     [rsp+1070h+dwFlags], 0F0000000h; dwFlags
0x18008fa97  xor     r8d, r8d; szProvider
0x18008fa9a  lea     rcx, [rsp+1070h+phProv]; phProv
0x18008fa9f  xor     edx, edx; szContainer
0x18008faa1  call    cs:__imp_CryptAcquireContextW
0x18008faa7  test    eax, eax
0x18008faa9  jnz     short loc_18008FAB7
0x18008faab  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18008fab0  mov     ebx, eax
0x18008fab2  jmp     loc_18008FB7B
0x18008fab7  mov     rcx, [rsp+1070h+phProv]; hProv
0x18008fabc  lea     rax, [rsp+1070h+phHash]
0x18008fac1  xor     r9d, r9d; dwFlags
0x18008fac4  mov     qword ptr [rsp+1070h+dwFlags], rax; phHash
0x18008fac9  xor     r8d, r8d; hKey
0x18008facc  mov     edx, 8003h; Algid
0x18008fad1  call    cs:__imp_CryptCreateHash
0x18008fad7  test    eax, eax
0x18008fad9  jz      short loc_18008FAAB
0x18008fadb  mov     rax, [rdi]
0x18008fade  lea     r9, [rsp+1070h+dwDataLen]
0x18008fae3  mov     r8d, 1000h
0x18008fae9  lea     rdx, [rsp+1070h+pbData]
0x18008faee  mov     rcx, rdi
0x18008faf1  mov     rax, [rax+18h]
0x18008faf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fafa  mov     ebx, eax
0x18008fafc  test    eax, eax
0x18008fafe  js      short loc_18008FB7B
0x18008fb00  mov     r8d, [rsp+1070h+dwDataLen]; dwDataLen
0x18008fb05  test    r8d, r8d
0x18008fb08  jz      short loc_18008FB28
0x18008fb0a  mov     rcx, [rsp+1070h+phHash]; hHash
0x18008fb0f  lea     rdx, [rsp+1070h+pbData]; pbData
0x18008fb14  xor     r9d, r9d; dwFlags
0x18008fb17  call    cs:__imp_CryptHashData
0x18008fb1d  test    eax, eax
0x18008fb1f  jz      short loc_18008FAAB
0x18008fb21  cmp     [rsp+1070h+dwDataLen], 0
0x18008fb26  jnz     short loc_18008FADB
0x18008fb28  mov     rcx, [rsp+1070h+phHash]; hHash
0x18008fb2d  lea     r9, [rsp+1070h+dwDataLen]; pdwDataLen
0x18008fb32  mov     r8, rsi; pbData
0x18008fb35  mov     [rsp+1070h+dwDataLen], 10h
0x18008fb3d  mov     edx, 2; dwParam
0x18008fb42  mov     [rsp+1070h+dwFlags], 0; dwFlags
0x18008fb4a  call    cs:__imp_CryptGetHashParam
0x18008fb50  test    eax, eax
0x18008fb52  jz      loc_18008FAAB
0x18008fb58  mov     rax, [rdi]
0x18008fb5b  xor     r9d, r9d
0x18008fb5e  mov     rdx, [rsp+1070h+var_1030]
0x18008fb63  xor     r8d, r8d
0x18008fb66  mov     rcx, rdi
0x18008fb69  mov     rax, [rax+28h]
0x18008fb6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fb72  mov     ebx, eax
0x18008fb74  xor     eax, eax
0x18008fb76  test    ebx, ebx
0x18008fb78  cmovns  ebx, eax
0x18008fb7b  mov     rcx, [rsp+1070h+phHash]; hHash
0x18008fb80  test    rcx, rcx
0x18008fb83  jz      short loc_18008FB94
0x18008fb85  call    cs:__imp_CryptDestroyHash
0x18008fb8b  mov     [rsp+1070h+phHash], 0
0x18008fb94  mov     rcx, [rsp+1070h+phProv]; hProv
0x18008fb99  test    rcx, rcx
0x18008fb9c  jz      short loc_18008FBA6
0x18008fb9e  xor     edx, edx; dwFlags
0x18008fba0  call    cs:__imp_CryptReleaseContext
0x18008fba6  mov     eax, ebx
0x18008fba8  mov     rcx, [rbp+0F70h+var_20]
0x18008fbaf  xor     rcx, rsp; StackCookie
0x18008fbb2  call    __security_check_cookie
0x18008fbb7  mov     rbx, [rsp+1070h+arg_10]
0x18008fbbf  add     rsp, 1060h
0x18008fbc6  pop     rdi
0x18008fbc7  pop     rsi
0x18008fbc8  pop     rbp
0x18008fbc9  retn
```
