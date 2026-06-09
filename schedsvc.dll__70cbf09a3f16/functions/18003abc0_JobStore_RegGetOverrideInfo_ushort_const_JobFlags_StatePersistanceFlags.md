# JobStore::RegGetOverrideInfo(ushort const *,JobFlags::StatePersistanceFlags *)

- ea: `0x18003abc0`
- end: `0x18003ad71`
- name: `?RegGetOverrideInfo@JobStore@@QEBAXPEBGPEAW4StatePersistanceFlags@JobFlags@@@Z`
- size: `433`
- prototype: `void __fastcall(HKEY *this, const unsigned __int16 *, enum JobFlags::StatePersistanceFlags *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180045df0`
- `0x18006c840`

## callees

- `0x18003abc0`
- `0x1800504b4`
- `0x180053e54`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003ac95`
- `OLEAUT32!__imp_SysAllocString` at `0x18003ac95`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ac60`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ac8c`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ac60`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ac8c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ac30`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ac30`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003aced`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003aced`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ac71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ac71`

## pseudocode

```c
void __fastcall JobStore::RegGetOverrideInfo(
        HKEY *this,
        const unsigned __int16 *a2,
        enum JobFlags::StatePersistanceFlags *a3)
{
  BSTR v6; // rbx
  __int64 v7; // rax
  LSTATUS v8; // eax
  char v9; // r8
  LSTATUS v10; // eax
  HKEY hKey[7]; // [rsp+30h] [rbp-38h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+8h] BYREF
  DWORD Type; // [rsp+80h] [rbp+18h] BYREF
  int Data; // [rsp+88h] [rbp+20h] BYREF

  Type = 0;
  cbData = 0;
  Data = 0;
  hKey[0] = 0;
  v6 = 0;
  *(_DWORD *)a3 = 0;
  if ( this[4] )
  {
    if ( a2 )
    {
      SysFreeString(0);
      v6 = SysAllocString(a2);
      hKey[1] = (HKEY)v6;
      if ( !v6 )
        ATL::PrivateAtlThrow(0x8007000E);
    }
    LODWORD(v7) = 0;
    if ( *v6 )
    {
      do
      {
        if ( v6[(unsigned int)v7] == 92 )
          v6[(unsigned int)v7] = 47;
        v7 = (unsigned int)(v7 + 1);
      }
      while ( v6[v7] );
    }
    v8 = RegOpenKeyExW(this[4], v6, 0, 0xF003Fu, hKey);
    v9 = v8;
    if ( !v8 )
    {
      cbData = 4;
      v10 = RegQueryValueExW(hKey[0], L"StateFlags", 0, &Type, (LPBYTE)&Data, &cbData);
      v9 = v10;
      if ( !v10 && Type == 4 && cbData == 4 && (Data | 3) == 3 )
        *(_DWORD *)a3 = Data;
    }
  }
  else
  {
    v9 = 50;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      88,
      (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
      (_DWORD)a2,
      (__int64)a2,
      v9);
  }
  SysFreeString(v6);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
}

```

## disassembly

```asm
0x18003abc0  mov     rax, rsp
0x18003abc3  push    rbx
0x18003abc4  push    rbp
0x18003abc5  push    rsi
0x18003abc6  push    rdi
0x18003abc7  push    r14
0x18003abc9  sub     rsp, 40h
0x18003abcd  mov     r14, r8
0x18003abd0  mov     rsi, rdx
0x18003abd3  mov     rdi, rcx
0x18003abd6  xor     ebp, ebp
0x18003abd8  mov     [rax+18h], ebp
0x18003abdb  mov     [rax+8], ebp
0x18003abde  mov     [rax+20h], ebp
0x18003abe1  mov     [rax-38h], rbp
0x18003abe5  mov     ebx, ebp
0x18003abe7  mov     [r8], ebp
0x18003abea  cmp     [rcx+20h], rbp
0x18003abee  jz      loc_18003AD34
0x18003abf4  test    rdx, rdx
0x18003abf7  jnz     loc_18003AC8A
0x18003abfd  mov     eax, ebp
0x18003abff  cmp     [rbx], ax
0x18003ac02  jz      short loc_18003AC16
0x18003ac04  mov     ecx, eax
0x18003ac06  cmp     word ptr [rbx+rcx*2], 5Ch ; '\'
0x18003ac0b  jz      short loc_18003AC82
0x18003ac0d  inc     eax
0x18003ac0f  cmp     word ptr [rbx+rax*2], 0
0x18003ac14  jnz     short loc_18003AC04
0x18003ac16  lea     rax, [rsp+68h+hKey]
0x18003ac1b  mov     [rsp+68h+phkResult], rax; phkResult
0x18003ac20  mov     r9d, 0F003Fh; samDesired
0x18003ac26  xor     r8d, r8d; ulOptions
0x18003ac29  mov     rdx, rbx; lpSubKey
0x18003ac2c  mov     rcx, [rdi+20h]; hKey
0x18003ac30  call    cs:__imp_RegOpenKeyExW
0x18003ac36  mov     r8d, eax
0x18003ac39  test    eax, eax
0x18003ac3b  jz      short loc_18003ACB7
0x18003ac3d  lea     rax, WPP_GLOBAL_Control
0x18003ac44  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ac4b  cmp     rcx, rax
0x18003ac4e  jz      short loc_18003AC5D
0x18003ac50  test    dword ptr [rcx+1Ch], 40000h
0x18003ac57  jnz     loc_18003AD3F
0x18003ac5d  mov     rcx, rbx; bstrString
0x18003ac60  call    cs:__imp_SysFreeString
0x18003ac66  nop
0x18003ac67  mov     rcx, [rsp+68h+hKey]; hKey
0x18003ac6c  test    rcx, rcx
0x18003ac6f  jz      short loc_18003AC77
0x18003ac71  call    cs:__imp_RegCloseKey
0x18003ac77  add     rsp, 40h
0x18003ac7b  pop     r14
0x18003ac7d  pop     rdi
0x18003ac7e  pop     rsi
0x18003ac7f  pop     rbp
0x18003ac80  pop     rbx
0x18003ac81  retn
0x18003ac82  mov     word ptr [rbx+rcx*2], 2Fh ; '/'
0x18003ac88  jmp     short loc_18003AC0D
0x18003ac8a  xor     ecx, ecx; bstrString
0x18003ac8c  call    cs:__imp_SysFreeString
0x18003ac92  mov     rcx, rsi; psz
0x18003ac95  call    cs:__imp_SysAllocString
0x18003ac9b  mov     rbx, rax
0x18003ac9e  mov     [rsp+68h+var_30], rax
0x18003aca3  test    rax, rax
0x18003aca6  jnz     loc_18003ABFD
0x18003acac  mov     ecx, 8007000Eh; unsigned int
0x18003acb1  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18003acb7  mov     [rsp+68h+cbData], 4
0x18003acbf  lea     rax, [rsp+68h+cbData]
0x18003acc4  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18003acc9  lea     rax, [rsp+68h+Data]
0x18003acd1  mov     [rsp+68h+phkResult], rax; lpData
0x18003acd6  lea     r9, [rsp+68h+Type]; lpType
0x18003acde  xor     r8d, r8d; lpReserved
0x18003ace1  lea     rdx, aStateflags; "StateFlags"
0x18003ace8  mov     rcx, [rsp+68h+hKey]; hKey
0x18003aced  call    cs:__imp_RegQueryValueExW
0x18003acf3  mov     r8d, eax
0x18003acf6  test    eax, eax
0x18003acf8  jnz     loc_18003AC3D
0x18003acfe  cmp     [rsp+68h+Type], 4
0x18003ad06  jnz     loc_18003AC3D
0x18003ad0c  cmp     [rsp+68h+cbData], 4
0x18003ad11  jnz     loc_18003AC3D
0x18003ad17  mov     ecx, [rsp+68h+Data]
0x18003ad1e  mov     eax, ecx
0x18003ad20  or      eax, 3
0x18003ad23  cmp     eax, 3
0x18003ad26  jnz     loc_18003AC3D
0x18003ad2c  mov     [r14], ecx
0x18003ad2f  jmp     loc_18003AC3D
0x18003ad34  mov     r8d, 32h ; '2'
0x18003ad3a  jmp     loc_18003AC3D
0x18003ad3f  cmp     byte ptr [rcx+19h], 2
0x18003ad43  jb      loc_18003AC5D
0x18003ad49  mov     edx, 58h ; 'X'
0x18003ad4e  mov     dword ptr [rsp+68h+lpcbData], r8d
0x18003ad53  mov     [rsp+68h+phkResult], rsi
0x18003ad58  mov     r9, rsi
0x18003ad5b  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x18003ad62  mov     rcx, [rcx+10h]
0x18003ad66  call    WPP_SF_SSD
0x18003ad6b  jmp     loc_18003AC5D
```
