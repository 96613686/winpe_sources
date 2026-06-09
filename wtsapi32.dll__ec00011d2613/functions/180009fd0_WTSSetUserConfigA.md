# WTSSetUserConfigA

- ea: `0x180009fd0`
- end: `0x18000a181`
- name: `WTSSetUserConfigA`
- size: `433`
- prototype: `BOOL __stdcall(LPSTR pServerName, LPSTR pUserName, WTS_CONFIG_CLASS WTSConfigClass, LPSTR pBuffer, DWORD DataLength)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180004b80`
- `0x180008acc`
- `0x180009ae8`
- `0x180009fd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a0dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a0dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a16a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a16a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a0b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a0bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a0d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a0b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a0bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a0d3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a106`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a106`

## pseudocode

```c
BOOL __stdcall WTSSetUserConfigA(
        LPSTR pServerName,
        LPSTR pUserName,
        WTS_CONFIG_CLASS WTSConfigClass,
        LPSTR pBuffer,
        DWORD DataLength)
{
  LPWSTR v5; // rsi
  WCHAR *v6; // rdi
  DWORD v7; // r15d
  DWORD LastError; // r14d
  int v10; // ebx
  WCHAR *v12; // rax
  int v13; // eax
  int v14; // [rsp+30h] [rbp-20h]
  LPWSTR pServerNamea; // [rsp+38h] [rbp-18h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-10h] BYREF
  WCHAR *v17; // [rsp+48h] [rbp-8h] BYREF
  DWORD v20; // [rsp+A8h] [rbp+58h] BYREF

  v5 = 0;
  v14 = 1;
  v6 = 0;
  hMem = 0;
  v7 = 0;
  pServerNamea = 0;
  v17 = 0;
  v20 = 0;
  if ( !pBuffer || !DataLength )
    goto LABEL_13;
  LastError = 0;
  v10 = CopyStringA((__int64)pUserName, &hMem, 0);
  if ( !v10 )
    goto LABEL_14;
  v10 = CopyStringA((__int64)pServerName, &pServerNamea, 0);
  if ( !v10 )
    goto LABEL_30;
  if ( (unsigned int)WTSConfigClass < WTSUserConfigfInheritInitialProgram
    || WTSConfigClass == WTSUserConfigModemCallbackPhoneNumber
    || WTSConfigClass == WTSUserConfigTerminalServerProfilePath
    || WTSConfigClass == WTSUserConfigTerminalServerHomeDir
    || WTSConfigClass == WTSUserConfigTerminalServerHomeDirDrive )
  {
    v13 = CopyStringA((__int64)pBuffer, &v17, &v20);
    v6 = v17;
    v7 = v20;
  }
  else
  {
    if ( WTSConfigClass != WTSUserConfigUser )
    {
      v7 = 4;
      if ( DataLength < 4 )
      {
        v5 = pServerNamea;
LABEL_13:
        LastError = 87;
        v10 = 0;
        goto LABEL_14;
      }
      v6 = (WCHAR *)pBuffer;
      v14 = 0;
      goto LABEL_29;
    }
    v12 = (WCHAR *)LocalAlloc(0x40u, 0x864u);
    v6 = v12;
    if ( !v12 )
    {
      v10 = 0;
      LastError = 14;
      goto LABEL_28;
    }
    v13 = ConvertUserInfoFromAnsiToUnicode(pBuffer, v12);
    v7 = 2148;
  }
  v10 = v13;
LABEL_28:
  if ( v10 )
  {
LABEL_29:
    v5 = pServerNamea;
    v10 = WTSSetUserConfigW(pServerNamea, (LPWSTR)hMem, WTSConfigClass, v6, v7);
    LastError = GetLastError();
    goto LABEL_14;
  }
LABEL_30:
  v5 = pServerNamea;
LABEL_14:
  if ( hMem )
    LocalFree(hMem);
  if ( v5 )
    LocalFree(v5);
  if ( v14 && v6 )
    LocalFree(v6);
  SetLastError(LastError);
  return v10;
}

```

## disassembly

```asm
0x180009fd0  mov     [rsp-38h+WTSConfigClass], r8d
0x180009fd5  mov     [rsp-38h+arg_0], rcx
0x180009fda  push    rbp
0x180009fdb  push    rbx
0x180009fdc  push    rsi
0x180009fdd  push    rdi
0x180009fde  push    r12
0x180009fe0  push    r14
0x180009fe2  push    r15
0x180009fe4  mov     rbp, rsp
0x180009fe7  sub     rsp, 50h
0x180009feb  xor     esi, esi
0x180009fed  mov     [rbp+var_20], 1
0x180009ff4  xor     edi, edi
0x180009ff6  mov     [rbp+hMem], 0
0x180009ffe  xor     r15d, r15d
0x18000a001  mov     [rbp+pServerName], rsi
0x18000a005  mov     [rbp+var_8], rdi
0x18000a009  mov     r12, r9
0x18000a00c  mov     [rbp+arg_18], r15d
0x18000a010  mov     rax, rdx
0x18000a013  test    r9, r9
0x18000a016  jz      loc_18000A0A0
0x18000a01c  cmp     [rbp+DataLength], esi
0x18000a01f  jz      short loc_18000A0A0
0x18000a021  xor     r8d, r8d
0x18000a024  lea     rdx, [rbp+hMem]
0x18000a028  mov     rcx, rax
0x18000a02b  xor     r14d, r14d
0x18000a02e  call    _CopyStringA
0x18000a033  mov     ebx, eax
0x18000a035  test    eax, eax
0x18000a037  jz      short loc_18000A0A8
0x18000a039  mov     rcx, [rbp+arg_0]
0x18000a03d  lea     rdx, [rbp+pServerName]
0x18000a041  xor     r8d, r8d
0x18000a044  call    _CopyStringA
0x18000a049  mov     ebx, eax
0x18000a04b  test    eax, eax
0x18000a04d  jz      loc_18000A178
0x18000a053  mov     esi, [rbp+WTSConfigClass]
0x18000a056  mov     ecx, esi
0x18000a058  test    esi, esi
0x18000a05a  jz      loc_18000A12F
0x18000a060  sub     ecx, 1
0x18000a063  jz      loc_18000A12F
0x18000a069  sub     ecx, 0Ch
0x18000a06c  jz      loc_18000A12F
0x18000a072  sub     ecx, 2
0x18000a075  jz      loc_18000A12F
0x18000a07b  sub     ecx, 1
0x18000a07e  jz      loc_18000A12F
0x18000a084  sub     ecx, 1
0x18000a087  jz      loc_18000A12F
0x18000a08d  cmp     ecx, 2
0x18000a090  jz      short loc_18000A0FC
0x18000a092  lea     r15d, [rdi+4]
0x18000a096  cmp     [rbp+DataLength], r15d
0x18000a09a  jnb     short loc_18000A0F3
0x18000a09c  mov     rsi, [rbp+pServerName]
0x18000a0a0  mov     r14d, 57h ; 'W'
0x18000a0a6  xor     ebx, ebx
0x18000a0a8  mov     rcx, [rbp+hMem]; hMem
0x18000a0ac  test    rcx, rcx
0x18000a0af  jz      short loc_18000A0B7
0x18000a0b1  call    cs:__imp_LocalFree
0x18000a0b7  test    rsi, rsi
0x18000a0ba  jz      short loc_18000A0C5
0x18000a0bc  mov     rcx, rsi; hMem
0x18000a0bf  call    cs:__imp_LocalFree
0x18000a0c5  cmp     [rbp+var_20], 0
0x18000a0c9  jz      short loc_18000A0D9
0x18000a0cb  test    rdi, rdi
0x18000a0ce  jz      short loc_18000A0D9
0x18000a0d0  mov     rcx, rdi; hMem
0x18000a0d3  call    cs:__imp_LocalFree
0x18000a0d9  mov     ecx, r14d; dwErrCode
0x18000a0dc  call    cs:__imp_SetLastError
0x18000a0e2  mov     eax, ebx
0x18000a0e4  add     rsp, 50h
0x18000a0e8  pop     r15
0x18000a0ea  pop     r14
0x18000a0ec  pop     r12
0x18000a0ee  pop     rdi
0x18000a0ef  pop     rsi
0x18000a0f0  pop     rbx
0x18000a0f1  pop     rbp
0x18000a0f2  retn
0x18000a0f3  mov     rdi, r12
0x18000a0f6  mov     [rbp+var_20], r14d
0x18000a0fa  jmp     short loc_18000A14D
0x18000a0fc  mov     edx, 864h; uBytes
0x18000a101  mov     ecx, 40h ; '@'; uFlags
0x18000a106  call    cs:__imp_LocalAlloc
0x18000a10c  mov     rdi, rax
0x18000a10f  test    rax, rax
0x18000a112  jz      short loc_18000A127
0x18000a114  mov     rdx, rax
0x18000a117  mov     rcx, r12
0x18000a11a  call    ConvertUserInfoFromAnsiToUnicode
0x18000a11f  mov     r15d, 864h
0x18000a125  jmp     short loc_18000A147
0x18000a127  xor     ebx, ebx
0x18000a129  lea     r14d, [rbx+0Eh]
0x18000a12d  jmp     short loc_18000A149
0x18000a12f  lea     r8, [rbp+arg_18]
0x18000a133  mov     rcx, r12
0x18000a136  lea     rdx, [rbp+var_8]
0x18000a13a  call    _CopyStringA
0x18000a13f  mov     rdi, [rbp+var_8]
0x18000a143  mov     r15d, [rbp+arg_18]
0x18000a147  mov     ebx, eax
0x18000a149  test    ebx, ebx
0x18000a14b  jz      short loc_18000A178
0x18000a14d  mov     rdx, [rbp+hMem]; pUserName
0x18000a151  mov     r8d, esi; WTSConfigClass
0x18000a154  mov     rsi, [rbp+pServerName]
0x18000a158  mov     r9, rdi; pBuffer
0x18000a15b  mov     rcx, rsi; pServerName
0x18000a15e  mov     [rsp+50h+var_30], r15d; DataLength
0x18000a163  call    WTSSetUserConfigW
0x18000a168  mov     ebx, eax
0x18000a16a  call    cs:__imp_GetLastError
0x18000a170  mov     r14d, eax
0x18000a173  jmp     loc_18000A0A8
0x18000a178  mov     rsi, [rbp+pServerName]
0x18000a17c  jmp     loc_18000A0A8
```
