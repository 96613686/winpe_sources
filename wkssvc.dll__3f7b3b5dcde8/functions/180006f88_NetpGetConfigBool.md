# NetpGetConfigBool

- ea: `0x180006f88`
- end: `0x1800070f7`
- name: `NetpGetConfigBool`
- size: `367`
- prototype: `__int64 __fastcall(HKEY *, const WCHAR *, int, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180007100`

## callees

- `0x180006f88`
- `0x180007604`
- `0x180007620`
- `0x180007710`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180007052`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180007066`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000707a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180007093`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180007052`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180007066`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000707a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180007093`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007018`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007018`
- `netutils!NetApiBufferFree` at `0x1800070c5`
- `netutils!NetApiBufferFree` at `0x1800070c5`

## pseudocode

```c
__int64 __fastcall NetpGetConfigBool(HKEY *a1, const WCHAR *a2, int a3, int *a4)
{
  HKEY v8; // rcx
  __int64 result; // rax
  BYTE *lpData; // rbx
  LSTATUS v11; // eax
  unsigned int v12; // edi
  int v13; // edi
  __int64 v14; // rax
  unsigned int v15; // esi
  DWORD cbData; // [rsp+70h] [rbp+18h] BYREF
  DWORD Type; // [rsp+78h] [rbp+20h] BYREF

  if ( !a4 )
    return 87;
  *a4 = a3;
  if ( !a1 )
    return 87;
  v8 = *a1;
  Type = 0;
  cbData = 0;
  result = NetpGetWinRegConfigMaxSizes(v8, a2, &cbData);
  if ( !(_DWORD)result && cbData )
  {
    lpData = (BYTE *)NetpMemoryAllocate(cbData);
    if ( !lpData )
      return 8;
    v11 = RegQueryValueExW(*a1, a2, 0, &Type, lpData, &cbData);
    v12 = v11;
    if ( v11 == 2 )
    {
      v12 = 0;
LABEL_10:
      NetpMemoryFree(lpData);
      return v12;
    }
    if ( v11 )
      goto LABEL_10;
    v13 = 1;
    if ( Type == 1 )
    {
      if ( (unsigned int)_o__wcsicmp(lpData, L"TRUE") && (unsigned int)_o__wcsicmp(lpData, L"YES") )
      {
        if ( (unsigned int)_o__wcsicmp(lpData, L"FALSE") && (unsigned int)_o__wcsicmp(lpData, L"NO") )
        {
          v13 = a3;
          v14 = -1;
          do
            ++v14;
          while ( *(_WORD *)&lpData[2 * v14] );
          v15 = (_DWORD)v14 != 0 ? 0xD : 0;
          goto LABEL_23;
        }
        v13 = 0;
      }
LABEL_22:
      v15 = 0;
LABEL_23:
      NetApiBufferFree(lpData);
      result = v15;
      *a4 = v13;
      return result;
    }
    if ( Type == 4 )
    {
      v13 = *(_DWORD *)lpData;
      goto LABEL_22;
    }
    NetpMemoryFree(lpData);
    return 13;
  }
  return result;
}

```

## disassembly

```asm
0x180006f88  mov     rax, rsp
0x180006f8b  mov     [rax+8], rbx
0x180006f8f  push    rbp
0x180006f90  push    rsi
0x180006f91  push    rdi
0x180006f92  push    r14
0x180006f94  push    r15
0x180006f96  sub     rsp, 30h
0x180006f9a  xor     r15d, r15d
0x180006f9d  mov     r14, r9
0x180006fa0  mov     esi, r8d
0x180006fa3  mov     rbp, rdx
0x180006fa6  mov     rdi, rcx
0x180006fa9  test    r9, r9
0x180006fac  jz      loc_1800070E1
0x180006fb2  mov     [r9], r8d
0x180006fb5  test    rcx, rcx
0x180006fb8  jz      loc_1800070E1
0x180006fbe  mov     rcx, [rcx]
0x180006fc1  lea     r8, [rax+18h]
0x180006fc5  mov     [rax+20h], r15d
0x180006fc9  mov     [rax+18h], r15d
0x180006fcd  call    NetpGetWinRegConfigMaxSizes
0x180006fd2  test    eax, eax
0x180006fd4  jnz     loc_1800070E6
0x180006fda  mov     ecx, [rsp+58h+cbData]
0x180006fde  test    ecx, ecx
0x180006fe0  jz      loc_1800070E6
0x180006fe6  call    NetpMemoryAllocate
0x180006feb  mov     rbx, rax
0x180006fee  test    rax, rax
0x180006ff1  jnz     short loc_180006FFB
0x180006ff3  lea     eax, [rbx+8]
0x180006ff6  jmp     loc_1800070E6
0x180006ffb  mov     rcx, [rdi]; hKey
0x180006ffe  lea     rax, [rsp+58h+cbData]
0x180007003  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180007008  lea     r9, [rsp+58h+Type]; lpType
0x18000700d  xor     r8d, r8d; lpReserved
0x180007010  mov     [rsp+58h+lpData], rbx; lpData
0x180007015  mov     rdx, rbp; lpValueName
0x180007018  call    cs:__imp_RegQueryValueExW
0x18000701e  mov     edi, eax
0x180007020  cmp     eax, 2
0x180007023  jnz     short loc_18000702A
0x180007025  mov     edi, r15d
0x180007028  jmp     short loc_18000702E
0x18000702a  test    eax, eax
0x18000702c  jz      short loc_18000703D
0x18000702e  mov     rcx, rbx
0x180007031  call    NetpMemoryFree
0x180007036  mov     eax, edi
0x180007038  jmp     loc_1800070E6
0x18000703d  mov     edi, 1
0x180007042  cmp     [rsp+58h+Type], edi
0x180007046  jnz     short loc_1800070B6
0x180007048  lea     rdx, aTrue_0; "TRUE"
0x18000704f  mov     rcx, rbx
0x180007052  call    cs:__imp__o__wcsicmp
0x180007058  test    eax, eax
0x18000705a  jz      short loc_1800070BF
0x18000705c  lea     rdx, aYes; "YES"
0x180007063  mov     rcx, rbx
0x180007066  call    cs:__imp__o__wcsicmp
0x18000706c  test    eax, eax
0x18000706e  jz      short loc_1800070BF
0x180007070  lea     rdx, aFalse_0; "FALSE"
0x180007077  mov     rcx, rbx
0x18000707a  call    cs:__imp__o__wcsicmp
0x180007080  test    eax, eax
0x180007082  jnz     short loc_180007089
0x180007084  mov     edi, r15d
0x180007087  jmp     short loc_1800070BF
0x180007089  lea     rdx, aNo; "NO"
0x180007090  mov     rcx, rbx
0x180007093  call    cs:__imp__o__wcsicmp
0x180007099  test    eax, eax
0x18000709b  jz      short loc_180007084
0x18000709d  mov     edi, esi
0x18000709f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800070a3  inc     rax
0x1800070a6  cmp     [rbx+rax*2], r15w
0x1800070ab  jnz     short loc_1800070A3
0x1800070ad  neg     eax
0x1800070af  sbb     esi, esi
0x1800070b1  and     esi, 0Dh
0x1800070b4  jmp     short loc_1800070C2
0x1800070b6  cmp     [rsp+58h+Type], 4
0x1800070bb  jnz     short loc_1800070D2
0x1800070bd  mov     edi, [rbx]
0x1800070bf  mov     esi, r15d
0x1800070c2  mov     rcx, rbx; Buffer
0x1800070c5  call    cs:__imp_NetApiBufferFree
0x1800070cb  mov     eax, esi
0x1800070cd  mov     [r14], edi
0x1800070d0  jmp     short loc_1800070E6
0x1800070d2  mov     rcx, rbx
0x1800070d5  call    NetpMemoryFree
0x1800070da  mov     eax, 0Dh
0x1800070df  jmp     short loc_1800070E6
0x1800070e1  mov     eax, 57h ; 'W'
0x1800070e6  mov     rbx, [rsp+58h+arg_0]
0x1800070eb  add     rsp, 30h
0x1800070ef  pop     r15
0x1800070f1  pop     r14
0x1800070f3  pop     rdi
0x1800070f4  pop     rsi
0x1800070f5  pop     rbp
0x1800070f6  retn
```
