# HashFile

- ea: `0x180001fd0`
- end: `0x1800021c9`
- name: `HashFile`
- size: `505`
- prototype: `__int64 __fastcall(OLECHAR *pbData, int, HCRYPTPROV, const CHAR *, BYTE **, _DWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180001010`
- `0x1800093c0`

## callees

- `0x180001fd0`
- `0x180002ef0`
- `0x1800031f4`
- `0x180003200`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180002106`
- `KERNEL32!GetLastError` at `0x180002160`
- `KERNEL32!GetLastError` at `0x180002181`
- `KERNEL32!GetLastError` at `0x18000218b`
- `KERNEL32!GetLastError` at `0x180002198`
- `KERNEL32!GetLastError` at `0x180002106`
- `KERNEL32!GetLastError` at `0x180002160`
- `KERNEL32!GetLastError` at `0x180002181`
- `KERNEL32!GetLastError` at `0x18000218b`
- `KERNEL32!GetLastError` at `0x180002198`
- `KERNEL32!SetLastError` at `0x1800021be`
- `KERNEL32!SetLastError` at `0x1800021be`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000205b`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000205b`
- `ADVAPI32!CryptDestroyHash` at `0x180002118`
- `ADVAPI32!CryptDestroyHash` at `0x180002118`
- `ADVAPI32!CryptGetHashParam` at `0x1800020c2`
- `ADVAPI32!CryptGetHashParam` at `0x1800020fc`
- `ADVAPI32!CryptGetHashParam` at `0x1800020c2`
- `ADVAPI32!CryptGetHashParam` at `0x1800020fc`
- `ADVAPI32!CryptHashData` at `0x18000206f`
- `ADVAPI32!CryptHashData` at `0x180002093`
- `ADVAPI32!CryptHashData` at `0x18000206f`
- `ADVAPI32!CryptHashData` at `0x180002093`
- `ADVAPI32!CryptCreateHash` at `0x18000204a`
- `ADVAPI32!CryptCreateHash` at `0x18000204a`
- `CRYPT32!CertOIDToAlgId` at `0x18000201e`
- `CRYPT32!CertOIDToAlgId` at `0x18000201e`

## pseudocode

```c
__int64 __fastcall HashFile(OLECHAR *pbData, int a2, HCRYPTPROV a3, const CHAR *a4, BYTE **a5, _DWORD *a6)
{
  BYTE **v6; // r14
  _DWORD *v7; // r15
  BYTE *v11; // rdi
  unsigned int v12; // ebx
  DWORD v13; // eax
  UINT v14; // eax
  BYTE *v15; // rax
  DWORD LastError; // esi
  int v18; // eax
  BYTE v19[4]; // [rsp+30h] [rbp-58h] BYREF
  DWORD pdwDataLen; // [rsp+34h] [rbp-54h] BYREF
  HCRYPTHASH hHash[10]; // [rsp+38h] [rbp-50h] BYREF
  int pbDataa; // [rsp+98h] [rbp+10h] BYREF

  pbDataa = a2;
  v6 = a5;
  v7 = a6;
  hHash[0] = 0;
  *(_DWORD *)v19 = 0;
  *a5 = 0;
  *v7 = 0;
  v11 = 0;
  pdwDataLen = 0;
  v12 = 0;
  v13 = CertOIDToAlgId(a4);
  if ( !v13 )
  {
    LastError = -2146893816;
    goto LABEL_10;
  }
  if ( v13 == -1 )
  {
    v13 = SipOidAlgIdToAlgId(a4);
    if ( !v13 )
    {
      LastError = -2146893816;
      goto LABEL_10;
    }
  }
  if ( CryptCreateHash(a3, v13, 0, 0, hHash)
    && (v14 = SysStringByteLen(pbData), CryptHashData(hHash[0], (const BYTE *)pbData, v14, 0))
    && CryptHashData(hHash[0], (const BYTE *)&pbDataa, 4u, 0) )
  {
    pdwDataLen = 4;
    if ( !CryptGetHashParam(hHash[0], 4u, v19, &pdwDataLen, 0) )
      goto LABEL_9;
    v15 = (BYTE *)operator new(*(unsigned int *)v19);
    v11 = v15;
    if ( v15 )
    {
      if ( CryptGetHashParam(hHash[0], 2u, v15, (DWORD *)v19, 0) )
      {
        v18 = *(_DWORD *)v19;
        LastError = 0;
        *v6 = v11;
        v12 = 1;
        v11 = 0;
        *v7 = v18;
        goto LABEL_10;
      }
LABEL_9:
      LastError = GetLastError();
      goto LABEL_10;
    }
    LastError = 8;
  }
  else
  {
    LastError = GetLastError();
  }
LABEL_10:
  if ( hHash[0] )
    CryptDestroyHash(hHash[0]);
  if ( v11 )
    operator delete(v11);
  if ( !v12 )
    SetLastError(LastError);
  return v12;
}

```

## disassembly

```asm
0x180001fd0  mov     [rsp+pbData], edx
0x180001fd4  push    rbx
0x180001fd5  push    rbp
0x180001fd6  push    rsi
0x180001fd7  push    rdi
0x180001fd8  push    r12
0x180001fda  push    r13
0x180001fdc  push    r14
0x180001fde  push    r15
0x180001fe0  sub     rsp, 48h
0x180001fe4  mov     r14, [rsp+88h+arg_20]
0x180001fec  xor     r13d, r13d
0x180001fef  mov     r15, [rsp+88h+arg_28]
0x180001ff7  mov     r12, rcx
0x180001ffa  mov     rcx, r9; pszObjId
0x180001ffd  mov     [rsp+88h+hHash], r13
0x180002002  mov     rsi, r9
0x180002005  mov     dword ptr [rsp+88h+var_58], r13d
0x18000200a  mov     [r14], r13
0x18000200d  mov     rbp, r8
0x180002010  mov     [r15], r13d
0x180002013  mov     edi, r13d
0x180002016  mov     [rsp+88h+pdwDataLen], r13d
0x18000201b  mov     ebx, r13d
0x18000201e  call    cs:__imp_CertOIDToAlgId
0x180002024  test    eax, eax
0x180002026  jz      loc_180002159
0x18000202c  cmp     eax, 0FFFFFFFFh
0x18000202f  jz      loc_18000216A
0x180002035  lea     rcx, [rsp+88h+hHash]
0x18000203a  xor     r9d, r9d; dwFlags
0x18000203d  mov     [rsp+88h+phHash], rcx; phHash
0x180002042  xor     r8d, r8d; hKey
0x180002045  mov     rcx, rbp; hProv
0x180002048  mov     edx, eax; Algid
0x18000204a  call    cs:__imp_CryptCreateHash
0x180002050  test    eax, eax
0x180002052  jz      loc_180002160
0x180002058  mov     rcx, r12; bstr
0x18000205b  call    cs:__imp_SysStringByteLen
0x180002061  mov     rcx, [rsp+88h+hHash]; hHash
0x180002066  xor     r9d, r9d; dwFlags
0x180002069  mov     r8d, eax; dwDataLen
0x18000206c  mov     rdx, r12; pbData
0x18000206f  call    cs:__imp_CryptHashData
0x180002075  test    eax, eax
0x180002077  jz      loc_180002181
0x18000207d  mov     rcx, [rsp+88h+hHash]; hHash
0x180002082  lea     rdx, [rsp+88h+pbData]; pbData
0x18000208a  xor     r9d, r9d; dwFlags
0x18000208d  mov     r8d, 4; dwDataLen
0x180002093  call    cs:__imp_CryptHashData
0x180002099  test    eax, eax
0x18000209b  jz      loc_18000218B
0x1800020a1  mov     rcx, [rsp+88h+hHash]; hHash
0x1800020a6  lea     r9, [rsp+88h+pdwDataLen]; pdwDataLen
0x1800020ab  lea     r8, [rsp+88h+var_58]; pbData
0x1800020b0  mov     [rsp+88h+pdwDataLen], 4
0x1800020b8  mov     edx, 4; dwParam
0x1800020bd  mov     dword ptr [rsp+88h+phHash], r13d; dwFlags
0x1800020c2  call    cs:__imp_CryptGetHashParam
0x1800020c8  test    eax, eax
0x1800020ca  jz      loc_180002198
0x1800020d0  mov     ecx, dword ptr [rsp+88h+var_58]; Size
0x1800020d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800020d9  mov     rdi, rax
0x1800020dc  test    rax, rax
0x1800020df  jz      loc_1800021A5
0x1800020e5  mov     rcx, [rsp+88h+hHash]; hHash
0x1800020ea  lea     r9, [rsp+88h+var_58]; pdwDataLen
0x1800020ef  mov     r8, rax; pbData
0x1800020f2  mov     dword ptr [rsp+88h+phHash], r13d; dwFlags
0x1800020f7  mov     edx, 2; dwParam
0x1800020fc  call    cs:__imp_CryptGetHashParam
0x180002102  test    eax, eax
0x180002104  jnz     short loc_180002142
0x180002106  call    cs:__imp_GetLastError
0x18000210c  mov     esi, eax
0x18000210e  mov     rcx, [rsp+88h+hHash]; hHash
0x180002113  test    rcx, rcx
0x180002116  jz      short loc_18000211E
0x180002118  call    cs:__imp_CryptDestroyHash
0x18000211e  test    rdi, rdi
0x180002121  jnz     loc_1800021AF
0x180002127  test    ebx, ebx
0x180002129  jz      loc_1800021BC
0x18000212f  mov     eax, ebx
0x180002131  add     rsp, 48h
0x180002135  pop     r15
0x180002137  pop     r14
0x180002139  pop     r13
0x18000213b  pop     r12
0x18000213d  pop     rdi
0x18000213e  pop     rsi
0x18000213f  pop     rbp
0x180002140  pop     rbx
0x180002141  retn
0x180002142  mov     eax, dword ptr [rsp+88h+var_58]
0x180002146  mov     esi, r13d
0x180002149  mov     [r14], rdi
0x18000214c  mov     ebx, 1
0x180002151  mov     rdi, r13
0x180002154  mov     [r15], eax
0x180002157  jmp     short loc_18000210E
0x180002159  mov     esi, 80090008h
0x18000215e  jmp     short loc_18000210E
0x180002160  call    cs:__imp_GetLastError
0x180002166  mov     esi, eax
0x180002168  jmp     short loc_18000210E
0x18000216a  mov     rcx, rsi; pvKey
0x18000216d  call    ?SipOidAlgIdToAlgId@@YAKPEBD@Z; SipOidAlgIdToAlgId(char const *)
0x180002172  test    eax, eax
0x180002174  jnz     loc_180002035
0x18000217a  mov     esi, 80090008h
0x18000217f  jmp     short loc_18000210E
0x180002181  call    cs:__imp_GetLastError
0x180002187  mov     esi, eax
0x180002189  jmp     short loc_18000210E
0x18000218b  call    cs:__imp_GetLastError
0x180002191  mov     esi, eax
0x180002193  jmp     loc_18000210E
0x180002198  call    cs:__imp_GetLastError
0x18000219e  mov     esi, eax
0x1800021a0  jmp     loc_18000210E
0x1800021a5  mov     esi, 8
0x1800021aa  jmp     loc_18000210E
0x1800021af  mov     rcx, rdi; Block
0x1800021b2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800021b7  jmp     loc_180002127
0x1800021bc  mov     ecx, esi; dwErrCode
0x1800021be  call    cs:__imp_SetLastError
0x1800021c4  jmp     loc_18000212F
```
