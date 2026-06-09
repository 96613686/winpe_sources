# GetReaderInfo(ulong,ushort const *,CBuffer *,CBuffer *)

- ea: `0x18000d640`
- end: `0x18000daaa`
- name: `?GetReaderInfo@@YAHKPEBGPEAVCBuffer@@1@Z`
- size: `1130`
- prototype: `int(unsigned int, const unsigned __int16 *, struct CBuffer *, struct CBuffer *)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180009c10`
- `0x18000cae0`
- `0x180011b70`
- `0x180012000`
- `0x180024254`

## callees

- `0x180002220`
- `0x18000d640`
- `0x18001b9b8`
- `0x18001ba04`
- `0x18002ef20`
- `0x18002ef38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d701`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d771`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d7d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d8f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d701`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d771`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d7d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d8f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d886`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d886`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d73f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d7a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d73f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d7a9`

## string_xrefs

- `0x18000d6a9`: `SOFTWARE\Microsoft\Cryptography\Calais\Readers`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetReaderInfo(unsigned int a1, const unsigned __int16 *a2, struct CBuffer *a3, const void **a4)
{
  HKEY v7; // rcx
  unsigned int v8; // esi
  const WCHAR *v9; // r15
  unsigned int i; // edi
  HKEY v11; // r14
  HKEY v12; // r14
  LSTATUS v13; // eax
  unsigned __int64 v14; // rdx
  int v15; // edi
  BYTE *v16; // rax
  LSTATUS v17; // eax
  int v18; // esi
  void *v19; // rdi
  void *v20; // rcx
  void *v22; // rax
  void *v23; // rdi
  unsigned __int64 v24; // rdx
  int v25; // esi
  void *v26; // r14
  void *v27; // rcx
  LSTATUS v28; // [rsp+30h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+34h] [rbp-B4h] BYREF
  LSTATUS pExceptionObject; // [rsp+38h] [rbp-B0h] BYREF
  ulong v31; // [rsp+3Ch] [rbp-ACh] BYREF
  ulong v32; // [rsp+40h] [rbp-A8h] BYREF
  ulong v33; // [rsp+44h] [rbp-A4h] BYREF
  ulong v34; // [rsp+48h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-98h] BYREF
  int v36; // [rsp+58h] [rbp-90h]
  const int *v37; // [rsp+60h] [rbp-88h]
  void *v38; // [rsp+68h] [rbp-80h]
  __int64 v39; // [rsp+70h] [rbp-78h]
  int v40; // [rsp+78h] [rbp-70h]
  HKEY phkResult; // [rsp+80h] [rbp-68h] BYREF
  int v42; // [rsp+88h] [rbp-60h]
  const int *v43; // [rsp+90h] [rbp-58h]
  void *v44; // [rsp+98h] [rbp-50h]
  __int64 v45; // [rsp+A0h] [rbp-48h]
  LSTATUS v46; // [rsp+A8h] [rbp-40h]
  LPCWSTR lpSubKey[2]; // [rsp+B0h] [rbp-38h]
  struct CBuffer *cbData; // [rsp+100h] [rbp+18h] BYREF
  struct CBuffer *v49; // [rsp+108h] [rbp+20h]

  v49 = (struct CBuffer *)a4;
  cbData = a3;
  v37 = &CBuffer::`vftable';
  v38 = 0;
  v39 = 0;
  hKey = 0;
  v40 = 1010;
  v43 = &CBuffer::`vftable';
  v44 = 0;
  v45 = 0;
  v7 = 0;
  phkResult = 0;
  v46 = 1010;
  lpSubKey[0] = L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\Readers";
  lpSubKey[1] = 0;
  v8 = 0;
  try
  {
    while ( 1 )
    {
      if ( v8 >= 2 )
      {
LABEL_52:
        v34 = 2;
        throw &v34;
      }
      v9 = lpSubKey[v8];
      if ( v9 )
        break;
LABEL_50:
      ++v8;
    }
    for ( i = 0; ; ++i )
    {
      if ( i >= 2 )
      {
        if ( a1 != 2 )
          goto LABEL_52;
        goto LABEL_50;
      }
      if ( dword_180038360[4 * i] >= a1 )
      {
        v11 = *(HKEY *)&dword_180038360[4 * i + 2];
        if ( v7 )
        {
          RegCloseKey(v7);
          phkResult = 0;
        }
        v46 = 1010;
        LODWORD(v45) = 0;
        v46 = RegOpenKeyExW(v11, v9, 0, 0x20019u, &phkResult);
        v42 = 2;
        if ( !v46 )
        {
          v12 = phkResult;
          if ( hKey )
          {
            RegCloseKey(hKey);
            hKey = 0;
          }
          v40 = 1010;
          LODWORD(v39) = 0;
          v13 = RegOpenKeyExW(v12, a2, 0, 0x20019u, &hKey);
          v40 = v13;
          v36 = 2;
          if ( !v13 )
          {
            if ( phkResult )
            {
              RegCloseKey(phkResult);
              phkResult = 0;
              v13 = v40;
            }
            v46 = 1010;
            LODWORD(v45) = 0;
            v43 = &CBuffer::`vftable';
            if ( v44 )
            {
              operator delete(v44, v14);
              v13 = v40;
            }
            goto LABEL_64;
          }
        }
        v7 = phkResult;
      }
    }
  }
  catch ( unsigned long )
  {
    CRegistry::~CRegistry((CRegistry *)&hKey);
    return 0;
  }
LABEL_64:
  if ( a4 )
  {
    try
    {
      LODWORD(cbData) = 0;
      Type = 0;
      if ( v13 )
      {
        v28 = v13;
        throw (ulong *)&v28;
      }
      v15 = 0;
      while ( 1 )
      {
        while ( 1 )
        {
          if ( v15 )
            goto LABEL_69;
          LODWORD(cbData) = *((_DWORD *)a4 + 5);
          v16 = (BYTE *)((_DWORD)cbData ? a4[1] : &WideCharStr);
          v17 = RegQueryValueExW(hKey, L"Device", 0, &Type, v16, (LPDWORD)&cbData);
          if ( !v17 )
            break;
          if ( v17 != 234 )
          {
            pExceptionObject = v17;
            throw (ulong *)&pExceptionObject;
          }
          v25 = (int)cbData;
          if ( *((_DWORD *)a4 + 5) < (unsigned int)cbData )
          {
            v26 = operator new[]((unsigned int)cbData);
            if ( !v26 )
            {
              v31 = 14;
              throw &v31;
            }
            v27 = (void *)a4[1];
            if ( v27 )
              operator delete(v27, v14);
            a4[1] = v26;
            *((_DWORD *)a4 + 5) = v25;
          }
          *((_DWORD *)a4 + 4) = 0;
        }
        v18 = (int)cbData;
        if ( *((_DWORD *)a4 + 4) )
        {
          if ( *((_DWORD *)a4 + 5) >= (unsigned int)cbData )
            goto LABEL_32;
          v22 = operator new[]((unsigned int)cbData);
          v23 = v22;
          if ( !v22 )
          {
            v32 = 14;
            throw &v32;
          }
          memcpy_0(v22, a4[1], *((unsigned int *)a4 + 4));
          operator delete((void *)a4[1], v24);
          a4[1] = v23;
          *((_DWORD *)a4 + 5) = v18;
          v15 = 1;
          *((_DWORD *)a4 + 4) = v18;
        }
        else
        {
          if ( *((_DWORD *)a4 + 5) < (unsigned int)cbData )
          {
            v19 = operator new[]((unsigned int)cbData);
            if ( !v19 )
            {
              v33 = 14;
              throw &v33;
            }
            v20 = (void *)a4[1];
            if ( v20 )
              operator delete(v20, v14);
            a4[1] = v19;
            *((_DWORD *)a4 + 5) = v18;
          }
          *((_DWORD *)a4 + 4) = 0;
LABEL_32:
          v15 = 1;
          *((_DWORD *)a4 + 4) = v18;
        }
      }
    }
    catch ( unsigned long )
    {
      *((_DWORD *)v49 + 4) = 0;
      throw;
    }
LABEL_69:
    ;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v40 = 1010;
  LODWORD(v39) = 0;
  v37 = &CBuffer::`vftable';
  if ( v38 )
    operator delete(v38, v14);
  return 1;
}

```

## disassembly

```asm
0x18000d640  mov     r11, rsp
0x18000d643  mov     [r11+8], rbx
0x18000d647  mov     [r11+10h], rsi
0x18000d64b  mov     [r11+20h], r9
0x18000d64f  mov     [r11+18h], r8
0x18000d653  push    rdi
0x18000d654  push    r12
0x18000d656  push    r13
0x18000d658  push    r14
0x18000d65a  push    r15
0x18000d65c  sub     rsp, 0C0h
0x18000d663  mov     rbx, r9
0x18000d666  mov     r13, rdx
0x18000d669  mov     r12d, ecx
0x18000d66c  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000d673  mov     [rsp+0E8h+var_88], rax
0x18000d678  xor     edx, edx
0x18000d67a  mov     [r11-80h], rdx
0x18000d67e  mov     [r11-78h], rdx
0x18000d682  mov     [rsp+0E8h+hKey], rdx
0x18000d687  mov     [rsp+0E8h+var_70], 3F2h
0x18000d68f  mov     [r11-58h], rax
0x18000d693  mov     [r11-50h], rdx
0x18000d697  mov     [r11-48h], rdx
0x18000d69b  mov     ecx, edx; hKey
0x18000d69d  mov     [r11-68h], rdx
0x18000d6a1  mov     dword ptr [r11-40h], 3F2h
0x18000d6a9  lea     rax, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x18000d6b0  mov     [r11-38h], rax
0x18000d6b4  mov     [r11-30h], rdx
0x18000d6b8  mov     esi, edx
0x18000d6ba  lea     r8, dword_180038360
0x18000d6c1  cmp     esi, 2
0x18000d6c4  jnb     loc_18000DA06
0x18000d6ca  mov     eax, esi
0x18000d6cc  mov     r15, [rsp+rax*8+0E8h+lpSubKey]
0x18000d6d4  test    r15, r15
0x18000d6d7  jz      loc_18000D9E1
0x18000d6dd  mov     edi, edx
0x18000d6df  cmp     edi, 2
0x18000d6e2  jnb     loc_18000D9DB
0x18000d6e8  mov     eax, edi
0x18000d6ea  add     rax, rax
0x18000d6ed  cmp     [r8+rax*8], r12d
0x18000d6f1  jb      loc_18000DA92
0x18000d6f7  mov     r14, [r8+rax*8+8]
0x18000d6fc  test    rcx, rcx
0x18000d6ff  jz      short loc_18000D711
0x18000d701  call    cs:__imp_RegCloseKey
0x18000d707  xor     edx, edx
0x18000d709  mov     [rsp+0E8h+var_68], rdx
0x18000d711  mov     [rsp+0E8h+var_40], 3F2h
0x18000d71c  mov     dword ptr [rsp+0E8h+var_48], edx
0x18000d723  lea     rax, [rsp+0E8h+var_68]
0x18000d72b  mov     [rsp+0E8h+phkResult], rax; phkResult
0x18000d730  mov     r9d, 20019h; samDesired
0x18000d736  xor     r8d, r8d; ulOptions
0x18000d739  mov     rdx, r15; lpSubKey
0x18000d73c  mov     rcx, r14; hKey
0x18000d73f  call    cs:__imp_RegOpenKeyExW
0x18000d745  mov     [rsp+0E8h+var_40], eax
0x18000d74c  mov     [rsp+0E8h+var_60], 2
0x18000d757  test    eax, eax
0x18000d759  jnz     loc_18000DA81
0x18000d75f  mov     r14, [rsp+0E8h+var_68]
0x18000d767  mov     rcx, [rsp+0E8h+hKey]; hKey
0x18000d76c  test    rcx, rcx
0x18000d76f  jz      short loc_18000D780
0x18000d771  call    cs:__imp_RegCloseKey
0x18000d777  mov     [rsp+0E8h+hKey], 0
0x18000d780  mov     [rsp+0E8h+var_70], 3F2h
0x18000d788  mov     dword ptr [rsp+0E8h+var_78], 0
0x18000d790  lea     rax, [rsp+0E8h+hKey]
0x18000d795  mov     [rsp+0E8h+phkResult], rax; phkResult
0x18000d79a  mov     r9d, 20019h; samDesired
0x18000d7a0  xor     r8d, r8d; ulOptions
0x18000d7a3  mov     rdx, r13; lpSubKey
0x18000d7a6  mov     rcx, r14; hKey
0x18000d7a9  call    cs:__imp_RegOpenKeyExW
0x18000d7af  mov     [rsp+0E8h+var_70], eax
0x18000d7b3  mov     [rsp+0E8h+var_90], 2
0x18000d7bb  test    eax, eax
0x18000d7bd  jnz     loc_18000DA81
0x18000d7c3  mov     rcx, [rsp+0E8h+var_68]; hKey
0x18000d7cb  test    rcx, rcx
0x18000d7ce  jz      loc_18000D9FE
0x18000d7d4  call    cs:__imp_RegCloseKey
0x18000d7da  xor     r15d, r15d
0x18000d7dd  mov     [rsp+0E8h+var_68], r15
0x18000d7e5  mov     eax, [rsp+0E8h+var_70]
0x18000d7e9  mov     [rsp+0E8h+var_40], 3F2h
0x18000d7f4  mov     dword ptr [rsp+0E8h+var_48], r15d
0x18000d7fc  lea     rdi, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000d803  mov     [rsp+0E8h+var_58], rdi
0x18000d80b  mov     rcx, [rsp+0E8h+var_50]; void *
0x18000d813  test    rcx, rcx
0x18000d816  jz      short loc_18000D821
0x18000d818  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d81d  mov     eax, [rsp+0E8h+var_70]
0x18000d821  test    rbx, rbx
0x18000d824  jz      loc_18000D8E9
0x18000d82a  mov     dword ptr [rsp+0E8h+cbData], r15d
0x18000d832  mov     [rsp+0E8h+Type], r15d
0x18000d837  test    eax, eax
0x18000d839  jnz     loc_18000DA20
0x18000d83f  mov     edi, r15d
0x18000d842  test    edi, edi
0x18000d844  jnz     loc_18000D8E2
0x18000d84a  mov     eax, [rbx+14h]
0x18000d84d  mov     dword ptr [rsp+0E8h+cbData], eax
0x18000d854  test    eax, eax
0x18000d856  jz      loc_18000D9CF
0x18000d85c  mov     rax, [rbx+8]
0x18000d860  lea     rcx, [rsp+0E8h+cbData]
0x18000d868  mov     [rsp+0E8h+lpcbData], rcx; lpcbData
0x18000d86d  mov     [rsp+0E8h+phkResult], rax; lpData
0x18000d872  lea     r9, [rsp+0E8h+Type]; lpType
0x18000d877  xor     r8d, r8d; lpReserved
0x18000d87a  lea     rdx, ValueName; "Device"
0x18000d881  mov     rcx, [rsp+0E8h+hKey]; hKey
0x18000d886  call    cs:__imp_RegQueryValueExW
0x18000d88c  test    eax, eax
0x18000d88e  jnz     loc_18000D988
0x18000d894  mov     esi, dword ptr [rsp+0E8h+cbData]
0x18000d89b  cmp     [rbx+10h], eax
0x18000d89e  ja      loc_18000D942
0x18000d8a4  cmp     [rbx+14h], esi
0x18000d8a7  jnb     short loc_18000D8D1
0x18000d8a9  mov     ecx, esi; unsigned __int64
0x18000d8ab  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000d8b0  mov     rdi, rax
0x18000d8b3  test    rax, rax
0x18000d8b6  jz      loc_18000DA67
0x18000d8bc  mov     rcx, [rbx+8]; void *
0x18000d8c0  test    rcx, rcx
0x18000d8c3  jz      short loc_18000D8CA
0x18000d8c5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d8ca  mov     [rbx+8], rdi
0x18000d8ce  mov     [rbx+14h], esi
0x18000d8d1  mov     [rbx+10h], r15d
0x18000d8d5  mov     edi, 1
0x18000d8da  mov     [rbx+10h], esi
0x18000d8dd  jmp     loc_18000D842
0x18000d8e2  lea     rdi, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000d8e9  mov     rcx, [rsp+0E8h+hKey]; hKey
0x18000d8ee  test    rcx, rcx
0x18000d8f1  jz      short loc_18000D8FE
0x18000d8f3  call    cs:__imp_RegCloseKey
0x18000d8f9  mov     [rsp+0E8h+hKey], r15
0x18000d8fe  mov     [rsp+0E8h+var_70], 3F2h
0x18000d906  mov     dword ptr [rsp+0E8h+var_78], r15d
0x18000d90b  mov     [rsp+0E8h+var_88], rdi
0x18000d910  mov     rcx, [rsp+0E8h+var_80]; void *
0x18000d915  test    rcx, rcx
0x18000d918  jz      short loc_18000D920
0x18000d91a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d91f  nop
0x18000d920  mov     eax, 1
0x18000d925  lea     r11, [rsp+0E8h+var_28]
0x18000d92d  mov     rbx, [r11+30h]
0x18000d931  mov     rsi, [r11+38h]
0x18000d935  mov     rsp, r11
0x18000d938  pop     r15
0x18000d93a  pop     r14
0x18000d93c  pop     r13
0x18000d93e  pop     r12
0x18000d940  pop     rdi
0x18000d941  retn
0x18000d942  cmp     [rbx+14h], esi
0x18000d945  jnb     short loc_18000D8D5
0x18000d947  mov     rcx, rsi; unsigned __int64
0x18000d94a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000d94f  mov     rdi, rax
0x18000d952  test    rax, rax
0x18000d955  jz      loc_18000DA4E
0x18000d95b  mov     r8d, [rbx+10h]; Size
0x18000d95f  mov     rdx, [rbx+8]; Src
0x18000d963  mov     rcx, rax; void *
0x18000d966  call    memcpy_0
0x18000d96b  mov     rcx, [rbx+8]; void *
0x18000d96f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d974  mov     [rbx+8], rdi
0x18000d978  mov     [rbx+14h], esi
0x18000d97b  mov     edi, 1
0x18000d980  mov     [rbx+10h], esi
0x18000d983  jmp     loc_18000D842
0x18000d988  cmp     eax, 0EAh
0x18000d98d  jnz     short loc_18000D9E8
0x18000d98f  mov     esi, dword ptr [rsp+0E8h+cbData]
0x18000d996  cmp     [rbx+14h], esi
0x18000d999  jnb     short loc_18000D9C3
0x18000d99b  mov     ecx, esi; unsigned __int64
0x18000d99d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000d9a2  mov     r14, rax
0x18000d9a5  test    rax, rax
0x18000d9a8  jz      loc_18000DA35
0x18000d9ae  mov     rcx, [rbx+8]; void *
0x18000d9b2  test    rcx, rcx
0x18000d9b5  jz      short loc_18000D9BC
0x18000d9b7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d9bc  mov     [rbx+8], r14
0x18000d9c0  mov     [rbx+14h], esi
0x18000d9c3  mov     esi, r15d
0x18000d9c6  mov     [rbx+10h], r15d
0x18000d9ca  jmp     loc_18000D842
0x18000d9cf  lea     rax, WideCharStr
0x18000d9d6  jmp     loc_18000D860
0x18000d9db  cmp     r12d, 2
0x18000d9df  jnz     short loc_18000DA06
0x18000d9e1  inc     esi
0x18000d9e3  jmp     loc_18000D6C1
0x18000d9e8  mov     [rsp+0E8h+pExceptionObject], eax
0x18000d9ec  lea     rdx, _TI1K; pThrowInfo
0x18000d9f3  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18000d9f8  call    _CxxThrowException_0
0x18000d9fe  xor     r15d, r15d
0x18000da01  jmp     loc_18000D7E9
0x18000da06  mov     [rsp+0E8h+var_A0], 2
0x18000da0e  lea     rdx, _TI1K; pThrowInfo
0x18000da15  lea     rcx, [rsp+0E8h+var_A0]; pExceptionObject
0x18000da1a  call    _CxxThrowException_0
0x18000da20  mov     [rsp+0E8h+var_B8], eax
0x18000da24  lea     rdx, _TI1K; pThrowInfo
0x18000da2b  lea     rcx, [rsp+0E8h+var_B8]; pExceptionObject
0x18000da30  call    _CxxThrowException_0
0x18000da35  mov     [rsp+0E8h+var_AC], 0Eh
0x18000da3d  lea     rdx, _TI1K; pThrowInfo
0x18000da44  lea     rcx, [rsp+0E8h+var_AC]; pExceptionObject
0x18000da49  call    _CxxThrowException_0
0x18000da4e  mov     [rsp+0E8h+var_A8], 0Eh
0x18000da56  lea     rdx, _TI1K; pThrowInfo
0x18000da5d  lea     rcx, [rsp+0E8h+var_A8]; pExceptionObject
0x18000da62  call    _CxxThrowException_0
0x18000da67  mov     [rsp+0E8h+var_A4], 0Eh
0x18000da6f  lea     rdx, _TI1K; pThrowInfo
0x18000da76  lea     rcx, [rsp+0E8h+var_A4]; pExceptionObject
0x18000da7b  call    _CxxThrowException_0
0x18000da81  mov     rcx, [rsp+0E8h+var_68]
0x18000da89  xor     edx, edx
0x18000da8b  lea     r8, dword_180038360
0x18000da92  inc     edi
0x18000da94  jmp     loc_18000D6DF
0x18000da99  lea     rcx, [rsp+0E8h+hKey]; this
0x18000da9e  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18000daa3  xor     eax, eax
0x18000daa5  jmp     loc_18000D925
```
