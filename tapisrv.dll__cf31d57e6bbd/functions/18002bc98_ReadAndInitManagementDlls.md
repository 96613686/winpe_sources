# ReadAndInitManagementDlls

- ea: `0x18002bc98`
- end: `0x18002c182`
- name: `ReadAndInitManagementDlls`
- size: `1258`
- prototype: `void()`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002b8f0`
- `0x18002d6d0`

## callees

- `0x18001c854`
- `0x18002b688`
- `0x18002bc98`
- `0x18002c8d4`
- `0x18003dc84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bd62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bd96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c15e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bd62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bd96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c15e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bcfc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bcfc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bd30`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bd8c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bd30`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bd8c`
- `KERNEL32!lstrcmpiW` at `0x18002bf14`
- `KERNEL32!lstrcmpiW` at `0x18002bf14`
- `KERNEL32!HeapAlloc` at `0x18002bd50`
- `KERNEL32!HeapAlloc` at `0x18002bdab`
- `KERNEL32!HeapAlloc` at `0x18002bdd5`
- `KERNEL32!HeapAlloc` at `0x18002be65`
- `KERNEL32!HeapAlloc` at `0x18002beb8`
- `KERNEL32!HeapAlloc` at `0x18002bd50`
- `KERNEL32!HeapAlloc` at `0x18002bdab`
- `KERNEL32!HeapAlloc` at `0x18002bdd5`
- `KERNEL32!HeapAlloc` at `0x18002be65`
- `KERNEL32!HeapAlloc` at `0x18002beb8`
- `KERNEL32!CreateThread` at `0x18002c088`
- `KERNEL32!CreateThread` at `0x18002c147`
- `KERNEL32!CreateThread` at `0x18002c088`
- `KERNEL32!CreateThread` at `0x18002c147`
- `KERNEL32!CloseHandle` at `0x18002c091`
- `KERNEL32!CloseHandle` at `0x18002c150`
- `KERNEL32!CloseHandle` at `0x18002c091`
- `KERNEL32!CloseHandle` at `0x18002c150`
- `KERNEL32!LeaveCriticalSection` at `0x18002c061`
- `KERNEL32!LeaveCriticalSection` at `0x18002c125`
- `KERNEL32!LeaveCriticalSection` at `0x18002c16b`
- `KERNEL32!LeaveCriticalSection` at `0x18002c061`
- `KERNEL32!LeaveCriticalSection` at `0x18002c125`
- `KERNEL32!LeaveCriticalSection` at `0x18002c16b`
- `KERNEL32!lstrlenW` at `0x18002be48`
- `KERNEL32!lstrlenW` at `0x18002be48`
- `KERNEL32!EnterCriticalSection` at `0x18002bcd6`
- `KERNEL32!EnterCriticalSection` at `0x18002c04a`
- `KERNEL32!EnterCriticalSection` at `0x18002c111`
- `KERNEL32!EnterCriticalSection` at `0x18002bcd6`
- `KERNEL32!EnterCriticalSection` at `0x18002c04a`
- `KERNEL32!EnterCriticalSection` at `0x18002c111`

## string_xrefs

- `0x18002bd29`: `ManagementDlls`
- `0x18002bd80`: `ManagementDlls`
- `0x18002c0ed`: `No management DLLs present on this server`
- `0x18002be31`: `Management DLL %d is %ls`

## pseudocode

```c
void ReadAndInitManagementDlls()
{
  LSTATUS v0; // eax
  LSTATUS v1; // edi
  DWORD v2; // esi
  BYTE *v3; // rax
  BYTE *v4; // r14
  _DWORD *v5; // rax
  _QWORD *v6; // rdi
  BYTE *v7; // rcx
  HANDLE v8; // rcx
  _QWORD *v9; // rax
  _QWORD *v10; // rsi
  int v11; // r12d
  const wchar_t *v12; // r15
  const wchar_t *v13; // rbx
  wchar_t v14; // ax
  int v15; // eax
  size_t v16; // r13
  wchar_t *v17; // rax
  int v18; // r11d
  _QWORD *v19; // rax
  __int64 i; // rbx
  __int64 j; // rsi
  _QWORD *v22; // rbx
  _QWORD *v23; // rsi
  __int64 v24; // rax
  void *v25; // rbx
  HANDLE v26; // rax
  __int64 v27; // rsi
  LPVOID *v28; // rbx
  void *v29; // rbx
  HANDLE v30; // rax
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+48h] BYREF
  DWORD Type; // [rsp+98h] [rbp+50h] BYREF
  int v34; // [rsp+A0h] [rbp+58h]
  DWORD ThreadId; // [rsp+A8h] [rbp+60h] BYREF

  cbData = 0;
  Type = 0;
  ThreadId = 0;
  hKey = 0;
  if ( (dword_180051900 & 2) != 0 )
  {
    EnterCriticalSection(&gManagementDllsCritSec);
    v0 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony\\Server",
           0,
           0xF003Fu,
           &hKey);
    cbData = 0;
    v1 = v0;
    if ( v0 || (RegQueryValueExW(hKey, L"ManagementDlls", 0, &Type, 0, &cbData), !cbData) )
    {
      TRACELogPrint(65538, "No management DLLs present on this server");
      v29 = lpParameter;
      if ( lpParameter )
      {
        EnterCriticalSection(&gDllListCritSec);
        lpParameter = 0;
        LeaveCriticalSection(&gDllListCritSec);
        v30 = CreateThread(0, 0, FreeOldDllListProc, v29, 0, &ThreadId);
        CloseHandle(v30);
      }
      if ( v1 )
        goto LABEL_51;
    }
    else
    {
      v2 = v1 + 8;
      v3 = (BYTE *)HeapAlloc(ghTapisrvHeap, v1 + 8, cbData);
      v4 = v3;
      if ( v3 )
      {
        RegQueryValueExW(hKey, L"ManagementDlls", 0, &Type, v3, &cbData);
        RegCloseKey(hKey);
        v5 = HeapAlloc(ghTapisrvHeap, v2, 0x10u);
        v6 = v5;
        if ( v5 )
        {
          v8 = ghTapisrvHeap;
          *v5 = 0;
          v9 = HeapAlloc(v8, v2, 0x100u);
          v6[1] = v9;
          v10 = v9;
          if ( v9 )
          {
            v11 = 0;
            v34 = 0;
            v12 = (const wchar_t *)v4;
            v13 = (const wchar_t *)v4;
            while ( 1 )
            {
              v14 = *v13;
              if ( !*v13 )
                goto LABEL_16;
              do
              {
                if ( v14 == 34 )
                  break;
                v14 = *++v13;
              }
              while ( *v13 );
              if ( *v13 )
                *v13 = 0;
              else
LABEL_16:
                v34 = 1;
              TRACELogPrint(262146, "Management DLL %d is %ls", v11, v12);
              v15 = lstrlenW(v12) + 1;
              v16 = 2LL * v15;
              v17 = (wchar_t *)HeapAlloc(ghTapisrvHeap, 8u, (unsigned int)(2 * v15));
              v10[29] = v17;
              if ( !v17 )
                break;
              StringCbCopyW(v17, v16, v12);
              v18 = gdwDllIDs;
              *((_DWORD *)v10 + 2) = gdwDllIDs;
              gdwDllIDs = v18 + 1;
              if ( v34 )
              {
                if ( lpParameter )
                {
                  for ( i = *((_QWORD *)lpParameter + 1); i; i = *(_QWORD *)(i + 248) )
                  {
                    for ( j = v6[1]; ; j = *(_QWORD *)(j + 248) )
                    {
                      if ( !j )
                        goto LABEL_28;
                      if ( !lstrcmpiW(*(LPCWSTR *)(j + 232), *(LPCWSTR *)(i + 232)) )
                        break;
                    }
                    *(_OWORD *)(j + 16) = *(_OWORD *)(i + 16);
                    *(_OWORD *)(j + 32) = *(_OWORD *)(i + 32);
                    *(_OWORD *)(j + 48) = *(_OWORD *)(i + 48);
                    *(_OWORD *)(j + 64) = *(_OWORD *)(i + 64);
                    *(_OWORD *)(j + 80) = *(_OWORD *)(i + 80);
                    *(_OWORD *)(j + 96) = *(_OWORD *)(i + 96);
                    *(_OWORD *)(j + 112) = *(_OWORD *)(i + 112);
                    *(_OWORD *)(j + 128) = *(_OWORD *)(i + 128);
                    *(_OWORD *)(j + 144) = *(_OWORD *)(i + 144);
                    *(_OWORD *)(j + 160) = *(_OWORD *)(i + 160);
                    *(_OWORD *)(j + 176) = *(_OWORD *)(i + 176);
                    *(_OWORD *)(j + 192) = *(_OWORD *)(i + 192);
                    *(_OWORD *)(j + 208) = *(_OWORD *)(i + 208);
                    *(_QWORD *)(j + 224) = *(_QWORD *)(i + 224);
                    *(_QWORD *)j = *(_QWORD *)i;
                    *(_DWORD *)(j + 8) = *(_DWORD *)(i + 8);
                    *(_QWORD *)i = 0;
LABEL_28:
                    ;
                  }
                }
                v22 = (_QWORD *)v6[1];
                v23 = 0;
                while ( 1 )
                {
LABEL_36:
                  if ( !v22 )
                  {
                    if ( !v6[1] )
                    {
                      ServerFree(v6);
                      v6 = 0;
                    }
                    v25 = lpParameter;
                    EnterCriticalSection(&gDllListCritSec);
                    lpParameter = v6;
                    v6 = 0;
                    LeaveCriticalSection(&gDllListCritSec);
                    if ( v25 )
                    {
                      v26 = CreateThread(0, 0, FreeOldDllListProc, v25, 0, &ThreadId);
                      CloseHandle(v26);
                    }
                    goto LABEL_41;
                  }
                  if ( *v22 || (unsigned int)LoadNewDll((__int64)v22) )
                    goto LABEL_35;
                  v24 = v22[31];
                  if ( v23 )
                    break;
                  v6[1] = v24;
                  ServerFree(v22);
                  v22 = (_QWORD *)v6[1];
                }
                v23[31] = v24;
                ServerFree(v22);
                v22 = v23;
LABEL_35:
                v23 = v22;
                v22 = (_QWORD *)v22[31];
                goto LABEL_36;
              }
              v19 = HeapAlloc(ghTapisrvHeap, 8u, 0x100u);
              v10[31] = v19;
              if ( !v19 )
                break;
              ++v13;
              v10 = v19;
              v12 = v13;
              ++v11;
            }
LABEL_41:
            ServerFree(v4);
            if ( v6 )
            {
              v27 = v6[1];
              while ( v27 )
              {
                v28 = (LPVOID *)v27;
                v27 = *(_QWORD *)(v27 + 248);
                ServerFree(v28[29]);
                ServerFree(v28);
              }
              ServerFree(v6);
            }
            goto LABEL_51;
          }
          ServerFree(v4);
          v7 = (BYTE *)v6;
        }
        else
        {
          v7 = v4;
        }
        ServerFree(v7);
LABEL_51:
        LeaveCriticalSection(&gManagementDllsCritSec);
        return;
      }
    }
    RegCloseKey(hKey);
    goto LABEL_51;
  }
}

```

## disassembly

```asm
0x18002bc98  push    rbp
0x18002bc9a  push    rbx
0x18002bc9b  push    rsi
0x18002bc9c  push    rdi
0x18002bc9d  push    r12
0x18002bc9f  push    r13
0x18002bca1  push    r14
0x18002bca3  push    r15
0x18002bca5  mov     rbp, rsp
0x18002bca8  sub     rsp, 48h
0x18002bcac  xor     r13d, r13d
0x18002bcaf  test    byte ptr cs:dword_180051900, 2
0x18002bcb6  mov     [rbp+cbData], r13d
0x18002bcba  mov     [rbp+Type], r13d
0x18002bcbe  mov     [rbp+ThreadId], r13d
0x18002bcc2  mov     [rbp+hKey], r13
0x18002bcc6  jz      loc_18002C171
0x18002bccc  lea     rbx, gManagementDllsCritSec
0x18002bcd3  mov     rcx, rbx; lpCriticalSection
0x18002bcd6  call    cs:__imp_EnterCriticalSection
0x18002bcdc  lea     rax, [rbp+hKey]
0x18002bce0  mov     r9d, 0F003Fh; samDesired
0x18002bce6  xor     r8d, r8d; ulOptions
0x18002bce9  mov     [rsp+48h+phkResult], rax; phkResult
0x18002bcee  lea     rdx, gszRegKeyServer; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002bcf5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002bcfc  call    cs:__imp_RegOpenKeyExW
0x18002bd02  mov     [rbp+cbData], r13d
0x18002bd06  mov     edi, eax
0x18002bd08  test    eax, eax
0x18002bd0a  jnz     loc_18002C0ED
0x18002bd10  mov     rcx, [rbp+hKey]; hKey
0x18002bd14  lea     rax, [rbp+cbData]
0x18002bd18  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18002bd1d  lea     r9, [rbp+Type]; lpType
0x18002bd21  xor     r8d, r8d; lpReserved
0x18002bd24  mov     [rsp+48h+phkResult], r13; lpData
0x18002bd29  lea     rdx, gszManagementDlls; "ManagementDlls"
0x18002bd30  call    cs:__imp_RegQueryValueExW
0x18002bd36  mov     eax, [rbp+cbData]
0x18002bd39  test    eax, eax
0x18002bd3b  jz      loc_18002C0ED
0x18002bd41  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002bd48  lea     esi, [rdi+8]
0x18002bd4b  mov     edx, esi; dwFlags
0x18002bd4d  mov     r8d, eax; dwBytes
0x18002bd50  call    cs:__imp_HeapAlloc
0x18002bd56  mov     rcx, [rbp+hKey]; hKey
0x18002bd5a  mov     r14, rax
0x18002bd5d  test    rax, rax
0x18002bd60  jnz     short loc_18002BD70
0x18002bd62  call    cs:__imp_RegCloseKey
0x18002bd68  mov     rcx, rbx
0x18002bd6b  jmp     loc_18002C16B
0x18002bd70  lea     rax, [rbp+cbData]
0x18002bd74  xor     r8d, r8d; lpReserved
0x18002bd77  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18002bd7c  lea     r9, [rbp+Type]; lpType
0x18002bd80  lea     rdx, gszManagementDlls; "ManagementDlls"
0x18002bd87  mov     [rsp+48h+phkResult], r14; lpData
0x18002bd8c  call    cs:__imp_RegQueryValueExW
0x18002bd92  mov     rcx, [rbp+hKey]; hKey
0x18002bd96  call    cs:__imp_RegCloseKey
0x18002bd9c  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002bda3  mov     r8d, 10h; dwBytes
0x18002bda9  mov     edx, esi; dwFlags
0x18002bdab  call    cs:__imp_HeapAlloc
0x18002bdb1  mov     rdi, rax
0x18002bdb4  test    rax, rax
0x18002bdb7  jnz     short loc_18002BDC3
0x18002bdb9  mov     rcx, r14; lpMem
0x18002bdbc  call    ServerFree
0x18002bdc1  jmp     short loc_18002BD68
0x18002bdc3  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002bdca  mov     r8d, 100h; dwBytes
0x18002bdd0  mov     edx, esi; dwFlags
0x18002bdd2  mov     [rax], r13d
0x18002bdd5  call    cs:__imp_HeapAlloc
0x18002bddb  mov     [rdi+8], rax
0x18002bddf  mov     rsi, rax
0x18002bde2  test    rax, rax
0x18002bde5  jnz     short loc_18002BDF4
0x18002bde7  mov     rcx, r14; lpMem
0x18002bdea  call    ServerFree
0x18002bdef  mov     rcx, rdi
0x18002bdf2  jmp     short loc_18002BDBC
0x18002bdf4  mov     r12d, r13d
0x18002bdf7  mov     [rbp+arg_10], r13d
0x18002bdfb  mov     r15, r14
0x18002bdfe  mov     rbx, r14
0x18002be01  movzx   eax, word ptr [rbx]
0x18002be04  test    ax, ax
0x18002be07  jz      short loc_18002BE27
0x18002be09  cmp     ax, 22h ; '"'
0x18002be0d  jz      short loc_18002BE1B
0x18002be0f  add     rbx, 2
0x18002be13  movzx   eax, word ptr [rbx]
0x18002be16  test    ax, ax
0x18002be19  jnz     short loc_18002BE09
0x18002be1b  cmp     [rbx], r13w
0x18002be1f  jz      short loc_18002BE27
0x18002be21  mov     [rbx], r13w
0x18002be25  jmp     short loc_18002BE2E
0x18002be27  mov     [rbp+arg_10], 1
0x18002be2e  mov     r9, r15
0x18002be31  lea     rdx, aManagementDllD; "Management DLL %d is %ls"
0x18002be38  mov     r8d, r12d
0x18002be3b  mov     ecx, 40002h
0x18002be40  call    TRACELogPrint
0x18002be45  mov     rcx, r15; lpString
0x18002be48  call    cs:__imp_lstrlenW
0x18002be4e  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002be55  mov     edx, 8; dwFlags
0x18002be5a  inc     eax
0x18002be5c  movsxd  r13, eax
0x18002be5f  add     r13, r13
0x18002be62  mov     r8d, r13d; dwBytes
0x18002be65  call    cs:__imp_HeapAlloc
0x18002be6b  mov     [rsi+0E8h], rax
0x18002be72  test    rax, rax
0x18002be75  jz      loc_18002C097
0x18002be7b  mov     r8, r15; pszSrc
0x18002be7e  mov     rdx, r13; cbDest
0x18002be81  mov     rcx, rax; pszDest
0x18002be84  call    StringCbCopyW
0x18002be89  mov     r11d, cs:gdwDllIDs
0x18002be90  xor     r13d, r13d
0x18002be93  mov     [rsi+8], r11d
0x18002be97  inc     r11d
0x18002be9a  mov     cs:gdwDllIDs, r11d
0x18002bea1  cmp     [rbp+arg_10], r13d
0x18002bea5  jnz     short loc_18002BEE0
0x18002bea7  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002beae  lea     edx, [r13+8]; dwFlags
0x18002beb2  mov     r8d, 100h; dwBytes
0x18002beb8  call    cs:__imp_HeapAlloc
0x18002bebe  mov     [rsi+0F8h], rax
0x18002bec5  test    rax, rax
0x18002bec8  jz      loc_18002C097
0x18002bece  add     rbx, 2
0x18002bed2  mov     rsi, rax
0x18002bed5  mov     r15, rbx
0x18002bed8  inc     r12d
0x18002bedb  jmp     loc_18002BE01
0x18002bee0  mov     rbx, cs:lpParameter
0x18002bee7  test    rbx, rbx
0x18002beea  jz      loc_18002BFE0
0x18002bef0  mov     rbx, [rbx+8]
0x18002bef4  jmp     loc_18002BFD7
0x18002bef9  mov     rsi, [rdi+8]
0x18002befd  test    rsi, rsi
0x18002bf00  jz      loc_18002BFD0
0x18002bf06  mov     rdx, [rbx+0E8h]; lpString2
0x18002bf0d  mov     rcx, [rsi+0E8h]; lpString1
0x18002bf14  call    cs:__imp_lstrcmpiW
0x18002bf1a  test    eax, eax
0x18002bf1c  jz      short loc_18002BF27
0x18002bf1e  mov     rsi, [rsi+0F8h]
0x18002bf25  jmp     short loc_18002BEFD
0x18002bf27  movups  xmm0, xmmword ptr [rbx+10h]
0x18002bf2b  movups  xmmword ptr [rsi+10h], xmm0
0x18002bf2f  movups  xmm1, xmmword ptr [rbx+20h]
0x18002bf33  movups  xmmword ptr [rsi+20h], xmm1
0x18002bf37  movups  xmm0, xmmword ptr [rbx+30h]
0x18002bf3b  movups  xmmword ptr [rsi+30h], xmm0
0x18002bf3f  movups  xmm1, xmmword ptr [rbx+40h]
0x18002bf43  movups  xmmword ptr [rsi+40h], xmm1
0x18002bf47  movups  xmm0, xmmword ptr [rbx+50h]
0x18002bf4b  movups  xmmword ptr [rsi+50h], xmm0
0x18002bf4f  movups  xmm1, xmmword ptr [rbx+60h]
0x18002bf53  movups  xmmword ptr [rsi+60h], xmm1
0x18002bf57  movups  xmm0, xmmword ptr [rbx+70h]
0x18002bf5b  movups  xmmword ptr [rsi+70h], xmm0
0x18002bf5f  movups  xmm1, xmmword ptr [rbx+80h]
0x18002bf66  movups  xmmword ptr [rsi+80h], xmm1
0x18002bf6d  movups  xmm0, xmmword ptr [rbx+90h]
0x18002bf74  movups  xmmword ptr [rsi+90h], xmm0
0x18002bf7b  movups  xmm1, xmmword ptr [rbx+0A0h]
0x18002bf82  movups  xmmword ptr [rsi+0A0h], xmm1
0x18002bf89  movups  xmm0, xmmword ptr [rbx+0B0h]
0x18002bf90  movups  xmmword ptr [rsi+0B0h], xmm0
0x18002bf97  movups  xmm1, xmmword ptr [rbx+0C0h]
0x18002bf9e  movups  xmmword ptr [rsi+0C0h], xmm1
0x18002bfa5  movups  xmm0, xmmword ptr [rbx+0D0h]
0x18002bfac  movups  xmmword ptr [rsi+0D0h], xmm0
0x18002bfb3  mov     rax, [rbx+0E0h]
0x18002bfba  mov     [rsi+0E0h], rax
0x18002bfc1  mov     rax, [rbx]
0x18002bfc4  mov     [rsi], rax
0x18002bfc7  mov     eax, [rbx+8]
0x18002bfca  mov     [rsi+8], eax
0x18002bfcd  mov     [rbx], r13
0x18002bfd0  mov     rbx, [rbx+0F8h]
0x18002bfd7  test    rbx, rbx
0x18002bfda  jnz     loc_18002BEF9
0x18002bfe0  mov     rbx, [rdi+8]
0x18002bfe4  mov     rsi, r13
0x18002bfe7  jmp     short loc_18002C026
0x18002bfe9  cmp     [rbx], r13
0x18002bfec  jnz     short loc_18002C01C
0x18002bfee  mov     rcx, rbx
0x18002bff1  call    LoadNewDll
0x18002bff6  test    eax, eax
0x18002bff8  jnz     short loc_18002C01C
0x18002bffa  mov     rax, [rbx+0F8h]
0x18002c001  mov     rcx, rbx; lpMem
0x18002c004  test    rsi, rsi
0x18002c007  jz      loc_18002C0AE
0x18002c00d  mov     [rsi+0F8h], rax
0x18002c014  call    ServerFree
0x18002c019  mov     rbx, rsi
0x18002c01c  mov     rsi, rbx
0x18002c01f  mov     rbx, [rbx+0F8h]
0x18002c026  test    rbx, rbx
0x18002c029  jnz     short loc_18002BFE9
0x18002c02b  cmp     [rdi+8], r13
0x18002c02f  jnz     short loc_18002C03C
0x18002c031  mov     rcx, rdi; lpMem
0x18002c034  call    ServerFree
0x18002c039  mov     rdi, r13
0x18002c03c  mov     rbx, cs:lpParameter
0x18002c043  lea     rcx, gDllListCritSec; lpCriticalSection
0x18002c04a  call    cs:__imp_EnterCriticalSection
0x18002c050  mov     cs:lpParameter, rdi
0x18002c057  lea     rcx, gDllListCritSec; lpCriticalSection
0x18002c05e  mov     rdi, r13
0x18002c061  call    cs:__imp_LeaveCriticalSection
0x18002c067  test    rbx, rbx
0x18002c06a  jz      short loc_18002C097
0x18002c06c  lea     rax, [rbp+ThreadId]
0x18002c070  mov     r9, rbx; lpParameter
0x18002c073  mov     [rsp+48h+lpcbData], rax; lpThreadId
0x18002c078  lea     r8, FreeOldDllListProc; lpStartAddress
0x18002c07f  xor     edx, edx; dwStackSize
0x18002c081  mov     dword ptr [rsp+48h+phkResult], r13d; dwCreationFlags
0x18002c086  xor     ecx, ecx; lpThreadAttributes
0x18002c088  call    cs:__imp_CreateThread
0x18002c08e  mov     rcx, rax; hObject
0x18002c091  call    cs:__imp_CloseHandle
0x18002c097  mov     rcx, r14; lpMem
0x18002c09a  call    ServerFree
0x18002c09f  test    rdi, rdi
0x18002c0a2  jz      loc_18002C164
0x18002c0a8  mov     rsi, [rdi+8]
0x18002c0ac  jmp     short loc_18002C0DE
0x18002c0ae  mov     [rdi+8], rax
0x18002c0b2  call    ServerFree
0x18002c0b7  mov     rbx, [rdi+8]
0x18002c0bb  jmp     loc_18002C026
0x18002c0c0  mov     rbx, rsi
0x18002c0c3  mov     rsi, [rsi+0F8h]
0x18002c0ca  mov     rcx, [rbx+0E8h]; lpMem
0x18002c0d1  call    ServerFree
0x18002c0d6  mov     rcx, rbx; lpMem
0x18002c0d9  call    ServerFree
0x18002c0de  test    rsi, rsi
0x18002c0e1  jnz     short loc_18002C0C0
0x18002c0e3  mov     rcx, rdi; lpMem
0x18002c0e6  call    ServerFree
0x18002c0eb  jmp     short loc_18002C164
0x18002c0ed  lea     rdx, aNoManagementDl; "No management DLLs present on this serv"...
0x18002c0f4  mov     ecx, 10002h
0x18002c0f9  call    TRACELogPrint
0x18002c0fe  mov     rbx, cs:lpParameter
0x18002c105  test    rbx, rbx
0x18002c108  jz      short loc_18002C156
0x18002c10a  lea     rcx, gDllListCritSec; lpCriticalSection
0x18002c111  call    cs:__imp_EnterCriticalSection
0x18002c117  lea     rcx, gDllListCritSec; lpCriticalSection
0x18002c11e  mov     cs:lpParameter, r13
0x18002c125  call    cs:__imp_LeaveCriticalSection
0x18002c12b  lea     rax, [rbp+ThreadId]
0x18002c12f  mov     r9, rbx; lpParameter
0x18002c132  mov     [rsp+48h+lpcbData], rax; lpThreadId
0x18002c137  lea     r8, FreeOldDllListProc; lpStartAddress
0x18002c13e  xor     edx, edx; dwStackSize
0x18002c140  mov     dword ptr [rsp+48h+phkResult], r13d; dwCreationFlags
0x18002c145  xor     ecx, ecx; lpThreadAttributes
0x18002c147  call    cs:__imp_CreateThread
0x18002c14d  mov     rcx, rax; hObject
0x18002c150  call    cs:__imp_CloseHandle
0x18002c156  test    edi, edi
0x18002c158  jnz     short loc_18002C164
0x18002c15a  mov     rcx, [rbp+hKey]; hKey
0x18002c15e  call    cs:__imp_RegCloseKey
0x18002c164  lea     rcx, gManagementDllsCritSec; lpCriticalSection
0x18002c16b  call    cs:__imp_LeaveCriticalSection
0x18002c171  add     rsp, 48h
0x18002c175  pop     r15
0x18002c177  pop     r14
0x18002c179  pop     r13
0x18002c17b  pop     r12
0x18002c17d  pop     rdi
0x18002c17e  pop     rsi
0x18002c17f  pop     rbx
0x18002c180  pop     rbp
0x18002c181  retn
```
