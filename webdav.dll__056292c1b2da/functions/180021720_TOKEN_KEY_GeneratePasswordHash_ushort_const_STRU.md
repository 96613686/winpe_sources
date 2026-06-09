# TOKEN_KEY::GeneratePasswordHash(ushort const *,STRU *)

- ea: `0x180021720`
- end: `0x1800219cc`
- name: `?GeneratePasswordHash@TOKEN_KEY@@QEAAJPEBGPEAVSTRU@@@Z`
- size: `684`
- prototype: `int(TOKEN_KEY *__hidden this, const unsigned __int16 *, struct STRU *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800213d8`

## callees

- `0x180021720`
- `0x180022520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800217b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021888`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800218cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800217b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021888`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800218cf`
- `iisutil!PuDbgPrint` at `0x180021802`
- `iisutil!PuDbgPrint` at `0x180021802`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002198b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180021999`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002198b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180021999`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180021972`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180021972`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002189e`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002189e`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800218fe`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800218fe`
- `ADVAPI32!CryptCreateHash` at `0x1800217ab`
- `ADVAPI32!CryptCreateHash` at `0x1800217ab`
- `ADVAPI32!CryptGetHashParam` at `0x18002187e`
- `ADVAPI32!CryptGetHashParam` at `0x1800218c5`
- `ADVAPI32!CryptGetHashParam` at `0x18002187e`
- `ADVAPI32!CryptGetHashParam` at `0x1800218c5`
- `ADVAPI32!CryptDestroyHash` at `0x180021981`
- `ADVAPI32!CryptDestroyHash` at `0x180021981`
- `ADVAPI32!CryptHashData` at `0x180021828`
- `ADVAPI32!CryptHashData` at `0x180021828`

## string_xrefs

- `0x1800217f6`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x1800217d7`: `CryptCreateHash() failed : hr = 0x%x\n`
- `0x1800217eb`: `TOKEN_KEY::GeneratePasswordHash`

## pseudocode

```c
__int64 __fastcall TOKEN_KEY::GeneratePasswordHash(TOKEN_KEY *this, const BYTE *a2, struct STRU *a3)
{
  signed int LastError; // eax
  signed int v6; // ebx
  const char *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r8
  signed int v10; // eax
  signed int v11; // eax
  unsigned int v12; // esi
  BYTE *v13; // r15
  __int64 v14; // r14
  unsigned int v15; // r10d
  unsigned int i; // r11d
  unsigned int v17; // eax
  __int16 v18; // cx
  __int64 v19; // rax
  __int64 v20; // r10
  unsigned int v21; // r8d
  __int64 pdwDataLen; // [rsp+30h] [rbp-39h] BYREF
  HCRYPTHASH hHash; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v25[32]; // [rsp+40h] [rbp-29h] BYREF
  BYTE *pbData; // [rsp+60h] [rbp-9h]
  int v27; // [rsp+68h] [rbp-1h]
  __int16 v28; // [rsp+6Ch] [rbp+3h]
  _OWORD v29[2]; // [rsp+70h] [rbp+7h] BYREF

  v28 = 256;
  hHash = 0;
  LODWORD(pdwDataLen) = 0;
  pbData = (BYTE *)v29;
  v27 = 32;
  memset(v29, 0, sizeof(v29));
  if ( !a2 || !a3 )
  {
    BUFFER::~BUFFER((BUFFER *)v25);
    return 2147942487LL;
  }
  if ( !CryptCreateHash(TOKEN_KEY::sm_hCryptProv, 0x800Cu, 0, 0, &hHash) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_28;
    v7 = "CryptCreateHash() failed : hr = 0x%x\n";
    v8 = 774;
    goto LABEL_8;
  }
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)&a2[2 * v9] );
  if ( CryptHashData(hHash, a2, 2 * v9, 0) )
  {
    LODWORD(pdwDataLen) = 32;
    if ( !CryptGetHashParam(hHash, 2u, pbData, (DWORD *)&pdwDataLen, 0) )
    {
      v11 = GetLastError();
      v6 = v11;
      if ( v11 != 234 )
        goto LABEL_22;
      if ( !BUFFER::Resize((BUFFER *)v25, pdwDataLen) )
      {
        v6 = -2147024882;
        goto LABEL_28;
      }
      if ( !CryptGetHashParam(hHash, 2u, pbData, (DWORD *)&pdwDataLen, 0) )
      {
        v11 = GetLastError();
        v6 = v11;
LABEL_22:
        if ( v11 > 0 )
          v6 = (unsigned __int16)v11 | 0x80070000;
        goto LABEL_28;
      }
    }
    v12 = pdwDataLen;
    v13 = pbData;
    v6 = STRU::Resize(a3, 4 * pdwDataLen + 2);
    if ( v6 >= 0 )
    {
      v14 = *((_QWORD *)a3 + 4);
      v15 = 0;
      for ( i = 0; i < v12; v15 = v20 + 1 )
      {
        v17 = v13[i] >> 4;
        v18 = v17 + 87 + (v17 < 0xA ? 0xFFD9 : 0);
        v19 = v15;
        v20 = v15 + 1;
        *(_WORD *)(v14 + 2 * v19) = v18;
        v21 = v13[i++] & 0xF;
        *(_WORD *)(v14 + 2 * v20) = v21 + (v21 < 0xA ? 48 : 87);
      }
      STRU::SetLen(a3, v15);
    }
    goto LABEL_28;
  }
  v10 = GetLastError();
  v6 = v10;
  if ( v10 > 0 )
    v6 = (unsigned __int16)v10 | 0x80070000;
  if ( (g_dwDebugFlags & 3) == 0 )
    goto LABEL_28;
  v7 = "CryptHashData() failed : hr = 0x%x\n";
  v8 = 788;
LABEL_8:
  PuDbgPrint(
    g_pDebug,
    "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
    v8,
    "TOKEN_KEY::GeneratePasswordHash",
    v7,
    v6,
    pdwDataLen);
LABEL_28:
  if ( hHash )
    CryptDestroyHash(hHash);
  BUFFER::~BUFFER((BUFFER *)v25);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180021720  mov     [rsp-8+arg_0], rbx
0x180021725  mov     [rsp-8+arg_18], rsi
0x18002172a  push    rbp
0x18002172b  push    rdi
0x18002172c  push    r12
0x18002172e  push    r14
0x180021730  push    r15
0x180021732  lea     rbp, [rsp-37h]
0x180021737  sub     rsp, 0A0h
0x18002173e  mov     rax, cs:__security_cookie
0x180021745  xor     rax, rsp
0x180021748  mov     [rbp+57h+var_30], rax
0x18002174c  xor     r12d, r12d
0x18002174f  mov     [rbp+57h+var_54], 100h
0x180021755  mov     [rbp+57h+hHash], r12
0x180021759  xorps   xmm0, xmm0
0x18002175c  mov     dword ptr [rbp+57h+pdwDataLen], r12d
0x180021760  lea     rax, [rbp+57h+var_50]
0x180021764  mov     [rbp+57h+pbData], rax
0x180021768  mov     rdi, r8
0x18002176b  lea     esi, [r12+20h]
0x180021770  mov     rbx, rdx
0x180021773  mov     [rbp+57h+var_58], esi
0x180021776  movups  [rbp+57h+var_50], xmm0
0x18002177a  movups  [rbp+57h+var_40], xmm0
0x18002177e  test    rdx, rdx
0x180021781  jz      loc_180021995
0x180021787  test    r8, r8
0x18002178a  jz      loc_180021995
0x180021790  mov     rcx, cs:?sm_hCryptProv@TOKEN_KEY@@0_KA; hProv
0x180021797  lea     rax, [rbp+57h+hHash]
0x18002179b  xor     r9d, r9d; dwFlags
0x18002179e  mov     [rsp+0C0h+phHash], rax; phHash
0x1800217a3  xor     r8d, r8d; hKey
0x1800217a6  mov     edx, 800Ch; Algid
0x1800217ab  call    cs:__imp_CryptCreateHash
0x1800217b1  test    eax, eax
0x1800217b3  jnz     short loc_18002180D
0x1800217b5  call    cs:__imp_GetLastError
0x1800217bb  mov     ebx, eax
0x1800217bd  test    eax, eax
0x1800217bf  jle     short loc_1800217CA
0x1800217c1  movzx   ebx, ax
0x1800217c4  or      ebx, 80070000h
0x1800217ca  test    byte ptr cs:g_dwDebugFlags, 3
0x1800217d1  jz      loc_180021978
0x1800217d7  lea     rax, aCryptcreatehas; "CryptCreateHash() failed : hr = 0x%x\n"
0x1800217de  mov     r8d, 306h
0x1800217e4  mov     rcx, cs:g_pDebug
0x1800217eb  lea     r9, aTokenKeyGenera; "TOKEN_KEY::GeneratePasswordHash"
0x1800217f2  mov     [rsp+0C0h+var_98], ebx
0x1800217f6  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800217fd  mov     [rsp+0C0h+phHash], rax
0x180021802  call    cs:__imp_PuDbgPrint
0x180021808  jmp     loc_180021978
0x18002180d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180021811  inc     r8
0x180021814  cmp     [rbx+r8*2], r12w
0x180021819  jnz     short loc_180021811
0x18002181b  mov     rcx, [rbp+57h+hHash]; hHash
0x18002181f  add     r8d, r8d; dwDataLen
0x180021822  xor     r9d, r9d; dwFlags
0x180021825  mov     rdx, rbx; pbData
0x180021828  call    cs:__imp_CryptHashData
0x18002182e  test    eax, eax
0x180021830  jnz     short loc_180021863
0x180021832  call    cs:__imp_GetLastError
0x180021838  mov     ebx, eax
0x18002183a  test    eax, eax
0x18002183c  jle     short loc_180021847
0x18002183e  movzx   ebx, ax
0x180021841  or      ebx, 80070000h
0x180021847  test    byte ptr cs:g_dwDebugFlags, 3
0x18002184e  jz      loc_180021978
0x180021854  lea     rax, aCrypthashdataF; "CryptHashData() failed : hr = 0x%x\n"
0x18002185b  mov     r8d, 314h
0x180021861  jmp     short loc_1800217E4
0x180021863  mov     r8, [rbp+57h+pbData]; pbData
0x180021867  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x18002186b  mov     rcx, [rbp+57h+hHash]; hHash
0x18002186f  mov     dword ptr [rbp+57h+pdwDataLen], esi
0x180021872  mov     esi, 2
0x180021877  mov     edx, esi; dwParam
0x180021879  mov     dword ptr [rsp+0C0h+phHash], r12d; dwFlags
0x18002187e  call    cs:__imp_CryptGetHashParam
0x180021884  test    eax, eax
0x180021886  jnz     short loc_1800218ED
0x180021888  call    cs:__imp_GetLastError
0x18002188e  mov     ebx, eax
0x180021890  cmp     eax, 0EAh
0x180021895  jnz     short loc_1800218D7
0x180021897  mov     edx, dword ptr [rbp+57h+pdwDataLen]
0x18002189a  lea     rcx, [rbp+57h+var_80]
0x18002189e  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800218a4  test    al, al
0x1800218a6  jnz     short loc_1800218B2
0x1800218a8  mov     ebx, 8007000Eh
0x1800218ad  jmp     loc_180021978
0x1800218b2  mov     r8, [rbp+57h+pbData]; pbData
0x1800218b6  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x1800218ba  mov     rcx, [rbp+57h+hHash]; hHash
0x1800218be  mov     edx, esi; dwParam
0x1800218c0  mov     dword ptr [rsp+0C0h+phHash], r12d; dwFlags
0x1800218c5  call    cs:__imp_CryptGetHashParam
0x1800218cb  test    eax, eax
0x1800218cd  jnz     short loc_1800218ED
0x1800218cf  call    cs:__imp_GetLastError
0x1800218d5  mov     ebx, eax
0x1800218d7  test    eax, eax
0x1800218d9  jle     loc_180021978
0x1800218df  movzx   ebx, ax
0x1800218e2  or      ebx, 80070000h
0x1800218e8  jmp     loc_180021978
0x1800218ed  mov     esi, dword ptr [rbp+57h+pdwDataLen]
0x1800218f0  mov     rcx, rdi
0x1800218f3  mov     r15, [rbp+57h+pbData]
0x1800218f7  lea     edx, ds:2[rsi*4]
0x1800218fe  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180021904  mov     ebx, eax
0x180021906  test    eax, eax
0x180021908  js      short loc_180021978
0x18002190a  mov     r14, [rdi+20h]
0x18002190e  mov     r10d, r12d
0x180021911  mov     r11d, r12d
0x180021914  test    esi, esi
0x180021916  jz      short loc_18002196C
0x180021918  mov     edx, r11d
0x18002191b  movzx   eax, byte ptr [rdx+r15]
0x180021920  shr     eax, 4
0x180021923  cmp     eax, 0Ah
0x180021926  sbb     cx, cx
0x180021929  add     ax, 57h ; 'W'
0x18002192d  and     cx, 0FFD9h
0x180021932  add     cx, ax
0x180021935  mov     eax, r10d
0x180021938  inc     r10d
0x18002193b  mov     [r14+rax*2], cx
0x180021940  movzx   r8d, byte ptr [rdx+r15]
0x180021945  and     r8d, 0Fh
0x180021949  cmp     r8d, 0Ah
0x18002194d  sbb     ax, ax
0x180021950  inc     r11d
0x180021953  and     ax, 0FFD9h
0x180021957  add     ax, 57h ; 'W'
0x18002195b  add     ax, r8w
0x18002195f  mov     [r14+r10*2], ax
0x180021964  inc     r10d
0x180021967  cmp     r11d, esi
0x18002196a  jb      short loc_180021918
0x18002196c  mov     edx, r10d
0x18002196f  mov     rcx, rdi
0x180021972  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180021978  mov     rcx, [rbp+57h+hHash]; hHash
0x18002197c  test    rcx, rcx
0x18002197f  jz      short loc_180021987
0x180021981  call    cs:__imp_CryptDestroyHash
0x180021987  lea     rcx, [rbp+57h+var_80]
0x18002198b  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180021991  mov     eax, ebx
0x180021993  jmp     short loc_1800219A4
0x180021995  lea     rcx, [rbp+57h+var_80]
0x180021999  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002199f  mov     eax, 80070057h
0x1800219a4  mov     rcx, [rbp+57h+var_30]
0x1800219a8  xor     rcx, rsp; StackCookie
0x1800219ab  call    __security_check_cookie
0x1800219b0  lea     r11, [rsp+0C0h+var_20]
0x1800219b8  mov     rbx, [r11+30h]
0x1800219bc  mov     rsi, [r11+48h]
0x1800219c0  mov     rsp, r11
0x1800219c3  pop     r15
0x1800219c5  pop     r14
0x1800219c7  pop     r12
0x1800219c9  pop     rdi
0x1800219ca  pop     rbp
0x1800219cb  retn
```
