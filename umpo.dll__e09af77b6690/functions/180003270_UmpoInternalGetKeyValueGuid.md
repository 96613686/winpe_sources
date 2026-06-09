# UmpoInternalGetKeyValueGuid

- ea: `0x180003270`
- end: `0x18000335e`
- name: `UmpoInternalGetKeyValueGuid`
- size: `238`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, UUID *Uuid)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800027d4`
- `0x180002d8c`
- `0x1800034c0`
- `0x180007790`

## callees

- `0x180003270`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800032bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003308`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800032bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003308`
- `RPCRT4!UuidFromStringW` at `0x180003322`
- `RPCRT4!UuidFromStringW` at `0x180003322`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003337`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003337`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800032dd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800032dd`

## pseudocode

```c
__int64 __fastcall UmpoInternalGetKeyValueGuid(HKEY hKey, LPCWSTR lpValueName, UUID *Uuid)
{
  unsigned int v6; // ebx
  DWORD v7; // eax
  DWORD v8; // esi
  BYTE *lpData; // rdi
  DWORD cbData; // [rsp+70h] [rbp+18h] BYREF
  DWORD Type; // [rsp+78h] [rbp+20h] BYREF

  if ( Uuid )
  {
    cbData = 0;
    Type = 0;
    v6 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
    if ( !v6 )
    {
      v7 = cbData;
      if ( cbData )
      {
        v8 = cbData + 2;
        cbData += 2;
        lpData = (BYTE *)LocalAlloc(0x40u, v7 + 2);
        if ( lpData )
        {
          v6 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, &cbData);
          if ( !v6 )
          {
            *(_WORD *)&lpData[2 * (v8 >> 1) - 2] = 0;
            v6 = UuidFromStringW((RPC_WSTR)lpData, Uuid);
            if ( v6 )
              v6 = 13;
          }
          LocalFree(lpData);
        }
        else
        {
          return 14;
        }
      }
    }
  }
  else
  {
    return 87;
  }
  return v6;
}

```

## disassembly

```asm
0x180003270  mov     r11, rsp
0x180003273  mov     [r11+8], rbx
0x180003277  push    rbp
0x180003278  push    rsi
0x180003279  push    rdi
0x18000327a  push    r14
0x18000327c  push    r15
0x18000327e  sub     rsp, 30h
0x180003282  mov     r15, r8
0x180003285  mov     rbp, rdx
0x180003288  mov     r14, rcx
0x18000328b  test    r8, r8
0x18000328e  jz      loc_180003350
0x180003294  lea     rax, [r11+18h]
0x180003298  mov     [rsp+58h+cbData], 0
0x1800032a0  mov     [r11-30h], rax
0x1800032a4  lea     r9, [r11+20h]; lpType
0x1800032a8  xor     r8d, r8d; lpReserved
0x1800032ab  mov     qword ptr [r11-38h], 0
0x1800032b3  mov     [rsp+58h+Type], 0
0x1800032bb  call    cs:__imp_RegQueryValueExW
0x1800032c1  mov     ebx, eax
0x1800032c3  test    eax, eax
0x1800032c5  jnz     short loc_18000333D
0x1800032c7  mov     eax, [rsp+58h+cbData]
0x1800032cb  test    eax, eax
0x1800032cd  jz      short loc_18000333D
0x1800032cf  add     eax, 2
0x1800032d2  lea     ecx, [rbx+40h]; uFlags
0x1800032d5  mov     edx, eax; uBytes
0x1800032d7  mov     esi, eax
0x1800032d9  mov     [rsp+58h+cbData], eax
0x1800032dd  call    cs:__imp_LocalAlloc
0x1800032e3  mov     rdi, rax
0x1800032e6  test    rax, rax
0x1800032e9  jz      short loc_180003357
0x1800032eb  lea     rax, [rsp+58h+cbData]
0x1800032f0  xor     r8d, r8d; lpReserved
0x1800032f3  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800032f8  lea     r9, [rsp+58h+Type]; lpType
0x1800032fd  mov     rdx, rbp; lpValueName
0x180003300  mov     [rsp+58h+lpData], rdi; lpData
0x180003305  mov     rcx, r14; hKey
0x180003308  call    cs:__imp_RegQueryValueExW
0x18000330e  mov     ebx, eax
0x180003310  test    eax, eax
0x180003312  jnz     short loc_180003334
0x180003314  shr     esi, 1
0x180003316  mov     rdx, r15; Uuid
0x180003319  dec     esi
0x18000331b  mov     rcx, rdi; StringUuid
0x18000331e  mov     [rdi+rsi*2], ax
0x180003322  call    cs:__imp_UuidFromStringW
0x180003328  mov     ebx, eax
0x18000332a  mov     eax, 0Dh
0x18000332f  test    ebx, ebx
0x180003331  cmovnz  ebx, eax
0x180003334  mov     rcx, rdi; hMem
0x180003337  call    cs:__imp_LocalFree
0x18000333d  mov     eax, ebx
0x18000333f  mov     rbx, [rsp+58h+arg_0]
0x180003344  add     rsp, 30h
0x180003348  pop     r15
0x18000334a  pop     r14
0x18000334c  pop     rdi
0x18000334d  pop     rsi
0x18000334e  pop     rbp
0x18000334f  retn
0x180003350  mov     ebx, 57h ; 'W'
0x180003355  jmp     short loc_18000333D
0x180003357  mov     ebx, 0Eh
0x18000335c  jmp     short loc_18000333D
```
