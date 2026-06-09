# DavReadRegistryBypassServerNames

- ea: `0x18002539c`
- end: `0x180025506`
- name: `DavReadRegistryBypassServerNames`
- size: `362`
- prototype: `__int64 __fastcall(HKEY hkey)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002550c`

## callees

- `0x18000b7dc`
- `0x18002539c`

## import_xrefs

- `msvcrt!tolower` at `0x1800254ce`
- `msvcrt!tolower` at `0x1800254ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025438`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025438`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800253e1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002548c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800253e1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002548c`
- `KERNEL32!LocalFree` at `0x18002549b`
- `KERNEL32!LocalFree` at `0x18002549b`
- `KERNEL32!LocalAlloc` at `0x18002540d`
- `KERNEL32!LocalAlloc` at `0x18002540d`

## pseudocode

```c
__int64 __fastcall DavReadRegistryBypassServerNames(HKEY hkey)
{
  LSTATUS ValueW; // eax
  unsigned int v3; // ebp
  _WORD *pvData; // rdi
  __int64 v5; // rbx
  DWORD LastError; // eax
  __int64 v7; // rsi
  __int64 v8; // rbx
  __int16 v9; // ax
  DWORD pcbData; // [rsp+68h] [rbp+10h] BYREF
  DWORD pdwType; // [rsp+70h] [rbp+18h] BYREF

  pdwType = 0;
  pcbData = 0;
  ValueW = RegGetValueW(hkey, 0, L"AuthForwardServerList", 0x20u, &pdwType, 0, &pcbData);
  v3 = ValueW;
  if ( ValueW == 234 || (pvData = 0, !ValueW) )
  {
    pcbData += 4;
    pvData = LocalAlloc(0x40u, pcbData);
    if ( !pvData )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        LastError = GetLastError();
        WPP_SF_d(v5, 56, WPP_3c901703a5983ce609c0997329a96280_Traceguids, LastError);
      }
      v3 = 14;
      pBypassServerNames = 0;
      return v3;
    }
    v3 = RegGetValueW(hkey, 0, L"AuthForwardServerList", 0x20u, &pdwType, pvData, &pcbData);
    if ( v3 )
    {
      LocalFree(pvData);
      pBypassServerNames = 0;
      return v3;
    }
  }
  pBypassServerNames = pvData;
  if ( pvData )
  {
    LODWORD(v7) = 0;
    if ( *pvData )
    {
      do
      {
        if ( pvData[(unsigned int)v7] )
        {
          do
          {
            v8 = (unsigned int)v7;
            v9 = tolower((unsigned __int16)pvData[(unsigned int)v7]);
            pvData = pBypassServerNames;
            v7 = (unsigned int)(v7 + 1);
            *((_WORD *)pBypassServerNames + v8) = v9;
          }
          while ( pvData[v7] );
        }
        v7 = (unsigned int)(v7 + 1);
      }
      while ( pvData[v7] );
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18002539c  mov     r11, rsp
0x18002539f  mov     [r11+8], rbx
0x1800253a3  mov     [r11+20h], rbp
0x1800253a7  push    rsi
0x1800253a8  push    rdi
0x1800253a9  push    r14
0x1800253ab  sub     rsp, 40h
0x1800253af  xor     r14d, r14d
0x1800253b2  lea     rax, [r11+10h]
0x1800253b6  mov     [r11-28h], rax
0x1800253ba  lea     r8, Value; "AuthForwardServerList"
0x1800253c1  lea     rax, [r11+18h]
0x1800253c5  mov     [r11-30h], r14
0x1800253c9  xor     edx, edx; lpSubKey
0x1800253cb  mov     [r11+18h], r14d
0x1800253cf  lea     esi, [r14+20h]
0x1800253d3  mov     [r11+10h], r14d
0x1800253d7  mov     r9d, esi; dwFlags
0x1800253da  mov     [r11-38h], rax
0x1800253de  mov     rbx, rcx
0x1800253e1  call    cs:__imp_RegGetValueW
0x1800253e7  mov     ebp, eax
0x1800253e9  cmp     eax, 0EAh
0x1800253ee  jz      short loc_1800253FB
0x1800253f0  mov     edi, r14d
0x1800253f3  test    eax, eax
0x1800253f5  jnz     loc_1800254AA
0x1800253fb  mov     eax, [rsp+58h+arg_8]
0x1800253ff  mov     ecx, 40h ; '@'; uFlags
0x180025404  add     eax, 4
0x180025407  mov     edx, eax; uBytes
0x180025409  mov     [rsp+58h+arg_8], eax
0x18002540d  call    cs:__imp_LocalAlloc
0x180025413  mov     rdi, rax
0x180025416  test    rax, rax
0x180025419  jnz     short loc_180025464
0x18002541b  mov     rbx, cs:WPP_GLOBAL_Control
0x180025422  lea     rax, WPP_GLOBAL_Control
0x180025429  cmp     rbx, rax
0x18002542c  jz      short loc_180025453
0x18002542e  test    byte ptr [rbx+1Ch], 1
0x180025432  jz      short loc_180025453
0x180025434  mov     rbx, [rbx+10h]
0x180025438  call    cs:__imp_GetLastError
0x18002543e  lea     edx, [rdi+38h]
0x180025441  mov     rcx, rbx
0x180025444  mov     r9d, eax
0x180025447  lea     r8, WPP_3c901703a5983ce609c0997329a96280_Traceguids
0x18002544e  call    WPP_SF_d
0x180025453  mov     ebp, 0Eh
0x180025458  mov     cs:pBypassServerNames, rdi
0x18002545f  jmp     loc_1800254F1
0x180025464  lea     rax, [rsp+58h+arg_8]
0x180025469  mov     r9d, esi; dwFlags
0x18002546c  mov     [rsp+58h+pcbData], rax; pcbData
0x180025471  lea     r8, Value; "AuthForwardServerList"
0x180025478  lea     rax, [rsp+58h+arg_10]
0x18002547d  mov     [rsp+58h+pvData], rdi; pvData
0x180025482  xor     edx, edx; lpSubKey
0x180025484  mov     [rsp+58h+pdwType], rax; pdwType
0x180025489  mov     rcx, rbx; hkey
0x18002548c  call    cs:__imp_RegGetValueW
0x180025492  mov     ebp, eax
0x180025494  test    eax, eax
0x180025496  jz      short loc_1800254AA
0x180025498  mov     rcx, rdi; hMem
0x18002549b  call    cs:__imp_LocalFree
0x1800254a1  mov     cs:pBypassServerNames, r14
0x1800254a8  jmp     short loc_1800254F1
0x1800254aa  mov     cs:pBypassServerNames, rdi
0x1800254b1  test    rdi, rdi
0x1800254b4  jz      short loc_1800254F1
0x1800254b6  mov     esi, r14d
0x1800254b9  cmp     [rdi], r14w
0x1800254bd  jz      short loc_1800254F1
0x1800254bf  mov     eax, esi
0x1800254c1  cmp     [rdi+rax*2], r14w
0x1800254c6  jz      short loc_1800254E8
0x1800254c8  mov     ebx, esi
0x1800254ca  movzx   ecx, word ptr [rdi+rbx*2]; C
0x1800254ce  call    cs:__imp_tolower
0x1800254d4  mov     rdi, cs:pBypassServerNames
0x1800254db  inc     esi
0x1800254dd  mov     [rdi+rbx*2], ax
0x1800254e1  cmp     [rdi+rsi*2], r14w
0x1800254e6  jnz     short loc_1800254C8
0x1800254e8  inc     esi
0x1800254ea  cmp     [rdi+rsi*2], r14w
0x1800254ef  jnz     short loc_1800254BF
0x1800254f1  mov     rbx, [rsp+58h+arg_0]
0x1800254f6  mov     eax, ebp
0x1800254f8  mov     rbp, [rsp+58h+arg_18]
0x1800254fd  add     rsp, 40h
0x180025501  pop     r14
0x180025503  pop     rdi
0x180025504  pop     rsi
0x180025505  retn
```
