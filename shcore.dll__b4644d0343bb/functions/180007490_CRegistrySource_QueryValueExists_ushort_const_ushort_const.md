# CRegistrySource::QueryValueExists(ushort const *,ushort const *)

- ea: `0x180007490`
- end: `0x1800075e9`
- name: `?QueryValueExists@CRegistrySource@@UEAAJPEBG0@Z`
- size: `345`
- prototype: `int(CRegistrySource *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180007120`
- `0x180007490`
- `0x1800079a0`
- `0x180008018`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007576`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007576`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800074e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800074e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007545`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007545`

## pseudocode

```c
__int64 __fastcall CRegistrySource::QueryValueExists(
        CRegistrySource *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  HKEY v3; // rdi
  unsigned int v5; // eax
  LSTATUS ValueW; // ebx
  LSTATUS v7; // eax
  HKEY cbData; // [rsp+60h] [rbp+20h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF

  v3 = (HKEY)*((_QWORD *)this + 6);
  if ( !v3 )
  {
    LOWORD(ValueW) = 87;
    return (unsigned __int16)ValueW | 0x80070000;
  }
  if ( a2 && *a2 )
  {
    cbData = 0;
    ValueW = RegOpenKeyExW(v3, a2, 0, 1u, &cbData);
    if ( !ValueW )
    {
      ValueW = SHRegQueryValueW(cbData, a3, 0, 0);
      RegCloseKey(cbData);
    }
  }
  else
  {
    Type = 0;
    LODWORD(cbData) = 0;
    v5 = RegQueryValueExW(v3, a3, 0, &Type, 0, (LPDWORD)&cbData);
    ValueW = v5;
    if ( !v5 || v5 == 234 )
    {
      if ( Type == 1 )
      {
        if ( (int)cbData + 2 < (unsigned int)cbData )
          ValueW = 534;
      }
      else
      {
        if ( Type == 2 )
        {
          v7 = NullTerminateRegExpandSzStringW(v3, (__int64)&cbData, 0, v5);
        }
        else
        {
          if ( Type != 7 )
            goto LABEL_14;
          v7 = NullTerminateRegMultiSzStringW(0, &cbData, 0, v5);
        }
        ValueW = v7;
      }
    }
  }
LABEL_14:
  if ( ValueW > 0 )
    return (unsigned __int16)ValueW | 0x80070000;
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x180007490  mov     [rsp-18h+arg_8], rbx
0x180007495  mov     [rsp-18h+arg_10], rsi
0x18000749a  push    rbp
0x18000749b  push    rdi
0x18000749c  push    r14
0x18000749e  mov     rbp, rsp
0x1800074a1  sub     rsp, 40h
0x1800074a5  mov     rdi, [rcx+30h]
0x1800074a9  xor     r14d, r14d
0x1800074ac  mov     rsi, r8
0x1800074af  test    rdi, rdi
0x1800074b2  jz      loc_1800075E2
0x1800074b8  test    rdx, rdx
0x1800074bb  jnz     short loc_180007526
0x1800074bd  lea     rax, [rbp+cbData]
0x1800074c1  mov     [rbp+Type], r14d
0x1800074c5  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800074ca  lea     r9, [rbp+Type]; lpType
0x1800074ce  xor     r8d, r8d; lpReserved
0x1800074d1  mov     [rsp+40h+lpData], r14; lpData
0x1800074d6  mov     rdx, rsi; lpValueName
0x1800074d9  mov     dword ptr [rbp+cbData], r14d
0x1800074dd  mov     rcx, rdi; hKey
0x1800074e0  call    cs:__imp_RegQueryValueExW
0x1800074e6  mov     ebx, eax
0x1800074e8  mov     ecx, 0EAh
0x1800074ed  test    eax, eax
0x1800074ef  jz      short loc_1800074F9
0x1800074f1  cmp     eax, ecx
0x1800074f3  jnz     loc_1800075A4
0x1800074f9  mov     eax, [rbp+Type]
0x1800074fc  sub     eax, 1
0x1800074ff  jz      loc_1800075C6
0x180007505  sub     eax, 1
0x180007508  jz      short loc_18000757E
0x18000750a  cmp     eax, 5
0x18000750d  jnz     loc_1800075A4
0x180007513  mov     r9d, ebx
0x180007516  lea     rdx, [rbp+cbData]
0x18000751a  xor     r8d, r8d
0x18000751d  xor     ecx, ecx
0x18000751f  call    NullTerminateRegMultiSzStringW
0x180007524  jmp     short loc_1800075A2
0x180007526  cmp     [rdx], r14w
0x18000752a  jz      short loc_1800074BD
0x18000752c  lea     rax, [rbp+cbData]
0x180007530  mov     [rbp+cbData], r14
0x180007534  mov     r9d, 1; samDesired
0x18000753a  mov     [rsp+40h+lpData], rax; phkResult
0x18000753f  xor     r8d, r8d; ulOptions
0x180007542  mov     rcx, rdi; hKey
0x180007545  call    cs:__imp_RegOpenKeyExW
0x18000754b  mov     ebx, eax
0x18000754d  test    eax, eax
0x18000754f  jnz     short loc_1800075A4
0x180007551  mov     rcx, [rbp+cbData]; hKey
0x180007555  xor     r9d, r9d
0x180007558  mov     [rsp+40h+lpcbData], r14; __int64
0x18000755d  mov     r8d, 0FFFFh
0x180007563  mov     rdx, rsi; lpValueName
0x180007566  mov     [rsp+40h+lpData], r14; LPBYTE
0x18000756b  call    _SHRegQueryValueW
0x180007570  mov     rcx, [rbp+cbData]; hKey
0x180007574  mov     ebx, eax
0x180007576  call    cs:__imp_RegCloseKey
0x18000757c  jmp     short loc_1800075A4
0x18000757e  mov     [rsp+40h+var_10], ebx; int
0x180007582  lea     rax, [rbp+cbData]
0x180007586  mov     dword ptr [rsp+40h+lpcbData], r14d; int
0x18000758b  lea     r8, [rbp+Type]
0x18000758f  xor     r9d, r9d
0x180007592  mov     [rsp+40h+lpData], rax; __int64
0x180007597  mov     rdx, rsi
0x18000759a  mov     rcx, rdi; hKey
0x18000759d  call    NullTerminateRegExpandSzStringW
0x1800075a2  mov     ebx, eax
0x1800075a4  test    ebx, ebx
0x1800075a6  jle     short loc_1800075B1
0x1800075a8  movzx   ebx, bx
0x1800075ab  or      ebx, 80070000h
0x1800075b1  mov     rsi, [rsp+40h+arg_10]
0x1800075b6  mov     eax, ebx
0x1800075b8  mov     rbx, [rsp+40h+arg_8]
0x1800075bd  add     rsp, 40h
0x1800075c1  pop     r14
0x1800075c3  pop     rdi
0x1800075c4  pop     rbp
0x1800075c5  retn
0x1800075c6  test    ebx, ebx
0x1800075c8  jnz     short loc_1800075DC
0x1800075ca  mov     ecx, dword ptr [rbp+cbData]
0x1800075cd  mov     edx, 216h
0x1800075d2  lea     eax, [rcx+2]
0x1800075d5  cmp     eax, ecx
0x1800075d7  cmovb   ebx, edx
0x1800075da  jmp     short loc_1800075A4
0x1800075dc  cmp     ebx, ecx
0x1800075de  jz      short loc_1800075CA
0x1800075e0  jmp     short loc_1800075A4
0x1800075e2  mov     ebx, 57h ; 'W'
0x1800075e7  jmp     short loc_1800075A8
```
