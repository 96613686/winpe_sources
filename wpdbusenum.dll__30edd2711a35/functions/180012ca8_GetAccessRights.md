# GetAccessRights

- ea: `0x180012ca8`
- end: `0x180012ddc`
- name: `GetAccessRights`
- size: `308`
- prototype: `LSTATUS __fastcall(HKEY hKey, _DWORD *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180005670`
- `0x180005f60`

## callees

- `0x180012ca8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012d5f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012d5f`

## string_xrefs

- `0x180012d2f`: `Deny_Read`
- `0x180012d22`: `Deny_Write`

## pseudocode

```c
LSTATUS __fastcall GetAccessRights(HKEY hKey, _DWORD *a2, int a3)
{
  unsigned int v3; // esi
  LSTATUS result; // eax
  unsigned int v8; // ebx
  const WCHAR *v9; // rdx
  BYTE *lpData; // rax
  int v11; // edx
  DWORD cbData; // [rsp+30h] [rbp-18h] BYREF
  DWORD Type[5]; // [rsp+34h] [rbp-14h] BYREF
  int v14; // [rsp+80h] [rbp+38h] BYREF
  int v15; // [rsp+88h] [rbp+40h] BYREF
  int v16; // [rsp+90h] [rbp+48h] BYREF
  int Data; // [rsp+98h] [rbp+50h] BYREF

  v3 = 1;
  *a2 = 0;
  if ( a3 != 1 )
    v3 = 4;
  if ( hKey )
  {
    result = 0;
    v16 = 0;
    v8 = 0;
    v14 = 0;
    v15 = 0;
    Data = 0;
    while ( 1 )
    {
      if ( v8 >= v3 )
        return result;
      Type[0] = 4;
      cbData = 4;
      if ( v8 )
      {
        switch ( v8 )
        {
          case 1u:
            v9 = L"Deny_Read";
            lpData = (BYTE *)&v15;
            break;
          case 2u:
            v9 = L"Deny_Write";
            lpData = (BYTE *)&v14;
            break;
          case 3u:
            v9 = L"Deny_Execute";
            lpData = (BYTE *)&Data;
            break;
          default:
            result = 87;
            goto LABEL_31;
        }
      }
      else
      {
        v9 = L"Deny_All";
        lpData = (BYTE *)&v16;
      }
      result = RegQueryValueExW(hKey, v9, 0, Type, lpData, &cbData);
      if ( result )
      {
        if ( a3 == 1 )
          goto LABEL_31;
        result = 0;
LABEL_17:
        if ( v16 )
          goto LABEL_27;
        if ( ++v8 == v3 )
        {
          v11 = v14;
          if ( v14 )
            *a2 |= 2u;
          if ( v15 )
          {
            *a2 |= 4u;
            if ( v11 )
              *a2 |= 1u;
          }
        }
      }
      else
      {
        if ( a3 != 1 )
          goto LABEL_17;
        if ( !v16 )
        {
          result = 3;
          goto LABEL_31;
        }
LABEL_27:
        *a2 = 7;
        ++v8;
      }
    }
  }
  result = 6;
LABEL_31:
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x180012ca8  push    rbp
0x180012caa  push    rbx
0x180012cab  push    rsi
0x180012cac  push    rdi
0x180012cad  push    r14
0x180012caf  push    r15
0x180012cb1  mov     rbp, rsp
0x180012cb4  sub     rsp, 48h
0x180012cb8  mov     esi, 1
0x180012cbd  mov     dword ptr [rdx], 0
0x180012cc3  mov     r15, rcx
0x180012cc6  cmp     r8d, esi
0x180012cc9  mov     r14d, r8d
0x180012ccc  mov     rdi, rdx
0x180012ccf  lea     ecx, [rsi+3]
0x180012cd2  cmovnz  esi, ecx
0x180012cd5  test    r15, r15
0x180012cd8  jz      loc_180012DC4
0x180012cde  xor     eax, eax
0x180012ce0  mov     [rbp+arg_10], eax
0x180012ce3  xor     ebx, ebx
0x180012ce5  mov     [rbp+arg_0], eax
0x180012ce8  mov     [rbp+arg_8], eax
0x180012ceb  mov     [rbp+Data], eax
0x180012cee  cmp     ebx, esi
0x180012cf0  jnb     loc_180012DCF
0x180012cf6  mov     [rbp+Type], ecx
0x180012cf9  mov     eax, ebx
0x180012cfb  mov     [rbp+cbData], ecx
0x180012cfe  test    ebx, ebx
0x180012d00  jz      short loc_180012D3C
0x180012d02  sub     eax, 1
0x180012d05  jz      short loc_180012D2F
0x180012d07  sub     eax, 1
0x180012d0a  jz      short loc_180012D22
0x180012d0c  cmp     eax, 1
0x180012d0f  jnz     loc_180012DBD
0x180012d15  lea     rdx, aDenyExecute; "Deny_Execute"
0x180012d1c  lea     rax, [rbp+Data]
0x180012d20  jmp     short loc_180012D47
0x180012d22  lea     rdx, aDenyWrite; "Deny_Write"
0x180012d29  lea     rax, [rbp+arg_0]
0x180012d2d  jmp     short loc_180012D47
0x180012d2f  lea     rdx, aDenyRead; "Deny_Read"
0x180012d36  lea     rax, [rbp+arg_8]
0x180012d3a  jmp     short loc_180012D47
0x180012d3c  lea     rdx, aDenyAll; "Deny_All"
0x180012d43  lea     rax, [rbp+arg_10]
0x180012d47  lea     rcx, [rbp+cbData]
0x180012d4b  xor     r8d, r8d; lpReserved
0x180012d4e  mov     [rsp+48h+lpcbData], rcx; lpcbData
0x180012d53  lea     r9, [rbp+Type]; lpType
0x180012d57  mov     rcx, r15; hKey
0x180012d5a  mov     [rsp+48h+lpData], rax; lpData
0x180012d5f  call    cs:__imp_RegQueryValueExW
0x180012d65  test    eax, eax
0x180012d67  jz      short loc_180012D99
0x180012d69  cmp     r14d, 1
0x180012d6d  jz      short loc_180012DC9
0x180012d6f  xor     eax, eax
0x180012d71  cmp     [rbp+arg_10], 0
0x180012d75  jnz     short loc_180012DAB
0x180012d77  inc     ebx
0x180012d79  cmp     ebx, esi
0x180012d7b  jnz     short loc_180012DB3
0x180012d7d  mov     edx, [rbp+arg_0]
0x180012d80  test    edx, edx
0x180012d82  jz      short loc_180012D87
0x180012d84  or      dword ptr [rdi], 2
0x180012d87  cmp     [rbp+arg_8], 0
0x180012d8b  jz      short loc_180012DB3
0x180012d8d  or      dword ptr [rdi], 4
0x180012d90  test    edx, edx
0x180012d92  jz      short loc_180012DB3
0x180012d94  or      dword ptr [rdi], 1
0x180012d97  jmp     short loc_180012DB3
0x180012d99  cmp     r14d, 1
0x180012d9d  jnz     short loc_180012D71
0x180012d9f  cmp     [rbp+arg_10], 0
0x180012da3  jnz     short loc_180012DAB
0x180012da5  lea     eax, [r14+2]
0x180012da9  jmp     short loc_180012DC9
0x180012dab  mov     dword ptr [rdi], 7
0x180012db1  inc     ebx
0x180012db3  mov     ecx, 4
0x180012db8  jmp     loc_180012CEE
0x180012dbd  mov     eax, 57h ; 'W'
0x180012dc2  jmp     short loc_180012DC9
0x180012dc4  mov     eax, 6
0x180012dc9  mov     dword ptr [rdi], 0
0x180012dcf  add     rsp, 48h
0x180012dd3  pop     r15
0x180012dd5  pop     r14
0x180012dd7  pop     rdi
0x180012dd8  pop     rsi
0x180012dd9  pop     rbx
0x180012dda  pop     rbp
0x180012ddb  retn
```
