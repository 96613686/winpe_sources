# ReadServiceConfig(HKEY__ *,HKEY__ *,NtpClientConfig *)

- ea: `0x18002b3fc`
- end: `0x18002b710`
- name: `?ReadServiceConfig@@YAJPEAUHKEY__@@0PEAUNtpClientConfig@@@Z`
- size: `788`
- prototype: `__int64 __fastcall(HKEY hkey, HKEY, struct NtpClientConfig *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18002125c`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x18002b3fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b513`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b664`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b513`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b664`

## string_xrefs

- `0x18002b571`: `MyRegQueryPolicyValueEx failed to read reg setting: %ls, error: 0x%x\n`
- `0x18002b6af`: `MyRegQueryPolicyValueEx read incorrect type for reg setting: %ls, readType:%d, expectedType:%d\n`
- `0x18002b6d0`: `ReadConfig: '%s'=0x%08X (%d)\n`

## pseudocode

```c
__int64 __fastcall ReadServiceConfig(HKEY hkey, HKEY a2, struct NtpClientConfig *a3)
{
  HKEY v3; // r10
  HKEY v4; // r11
  unsigned int v5; // edi
  unsigned int *v6; // r13
  unsigned int *v7; // r14
  __int64 v8; // rsi
  unsigned int v9; // ebx
  unsigned int *pvData; // rax
  const WCHAR *v11; // r12
  bool v12; // r15
  LSTATUS ValueW; // eax
  unsigned int v14; // ecx
  int v16; // [rsp+44h] [rbp-94h] BYREF
  int v17; // [rsp+48h] [rbp-90h] BYREF
  DWORD v18; // [rsp+4Ch] [rbp-8Ch]
  int v19; // [rsp+50h] [rbp-88h]
  unsigned int *v20; // [rsp+58h] [rbp-80h]
  unsigned int *v21; // [rsp+60h] [rbp-78h]
  unsigned int v22; // [rsp+68h] [rbp-70h]
  LPCWSTR lpValue; // [rsp+70h] [rbp-68h]
  PVOID v24; // [rsp+78h] [rbp-60h]
  _QWORD v25[11]; // [rsp+80h] [rbp-58h]
  DWORD pcbData; // [rsp+F0h] [rbp+18h] BYREF
  DWORD pdwType; // [rsp+F8h] [rbp+20h] BYREF

  v3 = a2;
  v4 = hkey;
  v5 = -2147467259;
  v16 = 0;
  v17 = 0;
  lpValue = L"MinPollInterval";
  v6 = (unsigned int *)((char *)a3 + 88);
  v24 = (char *)a3 + 88;
  v25[0] = &v16;
  v25[1] = L"MaxPollInterval";
  v7 = (unsigned int *)((char *)a3 + 92);
  v25[2] = (char *)a3 + 92;
  v25[3] = &v17;
  v8 = 0;
  v9 = 4;
  while ( 1 )
  {
    v19 = v8;
    if ( (unsigned int)v8 >= 2 )
      break;
    v18 = 4;
    pdwType = 0;
    v20 = (unsigned int *)v25[3 * v8];
    pvData = (unsigned int *)v25[3 * v8 - 1];
    v21 = pvData;
    v11 = (&lpValue)[3 * v8];
    v12 = 0;
    pcbData = 0;
    if ( v3 )
    {
      pcbData = 4;
      v12 = RegGetValueW(v3, 0, v11, 0xFFFFu, &pdwType, pvData, &pcbData) == 0;
      pvData = v21;
      v4 = hkey;
    }
    if ( !v12
      && (pcbData = 4, ValueW = RegGetValueW(v4, 0, v11, 0xFFFFu, &pdwType, pvData, &pcbData), (v5 = ValueW) != 0) )
    {
      if ( ValueW > 0 )
        v5 = (unsigned __int16)ValueW | 0x80070000;
    }
    else
    {
      v18 = pcbData;
      v5 = 0;
    }
    if ( v20 )
    {
      if ( v5 )
        *v20 = 0;
      else
        *v20 = v12 + 2;
    }
    v22 = v5;
    if ( (v5 & 0x80000000) != 0 )
    {
      if ( (unsigned __int8)FileLogAllowEntry(0) )
        FileLogAdd(L"MyRegQueryPolicyValueEx failed to read reg setting: %ls, error: 0x%x\n", v11, v5);
      return v5;
    }
    if ( pdwType != 4 )
    {
      if ( (unsigned __int8)FileLogAllowEntry(0) )
        FileLogAdd(
          L"MyRegQueryPolicyValueEx read incorrect type for reg setting: %ls, readType:%d, expectedType:%d\n",
          v11,
          pdwType,
          4);
      return v5;
    }
    if ( (unsigned __int8)FileLogAllowEntry(112) )
      FileLogAdd(L"ReadConfig: '%s'=0x%08X (%d)\n", v11, *v21, *v20);
    v8 = (unsigned int)(v8 + 1);
    v3 = a2;
    v4 = hkey;
  }
  if ( *v6 < 4 )
    *v6 = 4;
  else
    v9 = *v6;
  v14 = *((_DWORD *)g_pnpstate + 70);
  if ( *v7 > v14 )
    *v7 = v14;
  else
    v14 = *v7;
  if ( v9 > v14 )
    *v7 = v9;
  if ( (unsigned __int8)FileLogAllowEntry(112) )
    FileLogAdd(L"Poll interval settings: MinPollInterval:%d MaxPollInterval:%d\n", *v6, *v7);
  return v5;
}

```

## disassembly

```asm
0x18002b3fc  mov     [rsp+arg_8], rdx
0x18002b401  mov     [rsp+arg_0], rcx
0x18002b406  push    rbx
0x18002b407  push    rsi
0x18002b408  push    rdi
0x18002b409  push    r12
0x18002b40b  push    r13
0x18002b40d  push    r14
0x18002b40f  push    r15
0x18002b411  sub     rsp, 0A0h
0x18002b418  mov     r10, rdx
0x18002b41b  mov     r11, rcx
0x18002b41e  mov     edi, 80004005h
0x18002b423  mov     [rsp+0D8h+var_94], 0
0x18002b42b  mov     [rsp+0D8h+var_90], 0
0x18002b433  lea     rax, aMinpollinterva; "MinPollInterval"
0x18002b43a  mov     [rsp+0D8h+lpValue], rax
0x18002b43f  lea     r13, [r8+58h]
0x18002b443  mov     [rsp+0D8h+var_60], r13
0x18002b448  lea     rax, [rsp+0D8h+var_94]
0x18002b44d  mov     [rsp+0D8h+var_58], rax
0x18002b455  lea     rax, aMaxpollinterva; "MaxPollInterval"
0x18002b45c  mov     [rsp+0D8h+var_50], rax
0x18002b464  lea     r14, [r8+5Ch]
0x18002b468  mov     [rsp+0D8h+var_48], r14
0x18002b470  lea     rax, [rsp+0D8h+var_90]
0x18002b475  mov     [rsp+0D8h+var_40], rax
0x18002b47d  xor     esi, esi
0x18002b47f  lea     ebx, [rsi+4]
0x18002b482  mov     [rsp+0D8h+var_88], esi
0x18002b486  cmp     esi, 2
0x18002b489  jnb     loc_18002B582
0x18002b48f  mov     [rsp+0D8h+var_8C], ebx
0x18002b493  mov     [rsp+0D8h+arg_18], 0
0x18002b49e  lea     rcx, [rsi+rsi*2]
0x18002b4a2  mov     r9, [rsp+rcx*8+0D8h+var_58]
0x18002b4aa  mov     [rsp+0D8h+var_80], r9
0x18002b4af  mov     rax, [rsp+rcx*8+0D8h+var_60]
0x18002b4b4  mov     [rsp+0D8h+var_78], rax
0x18002b4b9  mov     r12, [rsp+rcx*8+0D8h+lpValue]
0x18002b4be  xor     r15b, r15b
0x18002b4c1  mov     [rsp+0D8h+var_98], r15b
0x18002b4c6  mov     [rsp+0D8h+arg_10], 0
0x18002b4d1  test    r10, r10
0x18002b4d4  jnz     loc_18002B630
0x18002b4da  test    r15b, r15b
0x18002b4dd  jnz     short loc_18002B529
0x18002b4df  mov     [rsp+0D8h+arg_10], ebx
0x18002b4e6  lea     rcx, [rsp+0D8h+arg_10]
0x18002b4ee  mov     [rsp+0D8h+pcbData], rcx; pcbData
0x18002b4f3  mov     [rsp+0D8h+pvData], rax; pvData
0x18002b4f8  lea     rax, [rsp+0D8h+arg_18]
0x18002b500  mov     [rsp+0D8h+pdwType], rax; pdwType
0x18002b505  mov     r9d, 0FFFFh; dwFlags
0x18002b50b  mov     r8, r12; lpValue
0x18002b50e  xor     edx, edx; lpSubKey
0x18002b510  mov     rcx, r11; hkey
0x18002b513  call    cs:__imp_RegGetValueW
0x18002b51a  nop     dword ptr [rax+rax+00h]
0x18002b51f  mov     edi, eax
0x18002b521  test    eax, eax
0x18002b523  jnz     loc_18002B61C
0x18002b529  mov     eax, [rsp+0D8h+arg_10]
0x18002b530  mov     [rsp+0D8h+var_8C], eax
0x18002b534  xor     edi, edi
0x18002b536  mov     rcx, [rsp+0D8h+var_80]
0x18002b53b  test    rcx, rcx
0x18002b53e  jz      short loc_18002B554
0x18002b540  test    edi, edi
0x18002b542  jnz     loc_18002B611
0x18002b548  neg     r15b
0x18002b54b  sbb     eax, eax
0x18002b54d  neg     eax
0x18002b54f  add     eax, 2
0x18002b552  mov     [rcx], eax
0x18002b554  mov     [rsp+0D8h+var_70], edi
0x18002b558  test    edi, edi
0x18002b55a  jns     short loc_18002B5DB
0x18002b55c  xor     ecx, ecx
0x18002b55e  call    FileLogAllowEntry
0x18002b563  test    al, al
0x18002b565  jz      loc_18002B6FA
0x18002b56b  mov     r8d, edi
0x18002b56e  mov     rdx, r12
0x18002b571  lea     rcx, aMyregquerypoli; "MyRegQueryPolicyValueEx failed to read "...
0x18002b578  call    FileLogAdd
0x18002b57d  jmp     loc_18002B6FA
0x18002b582  cmp     [r13+0], ebx
0x18002b586  jb      loc_18002B6E1
0x18002b58c  mov     ebx, [r13+0]
0x18002b590  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x18002b597  mov     ecx, [rax+118h]
0x18002b59d  cmp     [r14], ecx
0x18002b5a0  ja      loc_18002B6EA
0x18002b5a6  mov     ecx, [r14]
0x18002b5a9  cmp     ebx, ecx
0x18002b5ab  ja      loc_18002B6F2
0x18002b5b1  mov     ecx, 70h ; 'p'
0x18002b5b6  call    FileLogAllowEntry
0x18002b5bb  test    al, al
0x18002b5bd  jz      loc_18002B6FA
0x18002b5c3  mov     r8d, [r14]
0x18002b5c6  mov     edx, [r13+0]
0x18002b5ca  lea     rcx, aPollIntervalSe; "Poll interval settings: MinPollInterval"...
0x18002b5d1  call    FileLogAdd
0x18002b5d6  jmp     loc_18002B6FA
0x18002b5db  cmp     [rsp+0D8h+arg_18], ebx
0x18002b5e2  jnz     loc_18002B696
0x18002b5e8  mov     ecx, 70h ; 'p'
0x18002b5ed  call    FileLogAllowEntry
0x18002b5f2  test    al, al
0x18002b5f4  jnz     loc_18002B6BD
0x18002b5fa  inc     esi
0x18002b5fc  mov     r10, [rsp+0D8h+arg_8]
0x18002b604  mov     r11, [rsp+0D8h+arg_0]
0x18002b60c  jmp     loc_18002B482
0x18002b611  mov     dword ptr [rcx], 0
0x18002b617  jmp     loc_18002B554
0x18002b61c  jle     loc_18002B536
0x18002b622  movzx   edi, ax
0x18002b625  or      edi, 80070000h
0x18002b62b  jmp     loc_18002B536
0x18002b630  mov     [rsp+0D8h+arg_10], ebx
0x18002b637  lea     rcx, [rsp+0D8h+arg_10]
0x18002b63f  mov     [rsp+0D8h+pcbData], rcx; pcbData
0x18002b644  mov     [rsp+0D8h+pvData], rax; pvData
0x18002b649  lea     rax, [rsp+0D8h+arg_18]
0x18002b651  mov     [rsp+0D8h+pdwType], rax; pdwType
0x18002b656  mov     r9d, 0FFFFh; dwFlags
0x18002b65c  mov     r8, r12; lpValue
0x18002b65f  xor     edx, edx; lpSubKey
0x18002b661  mov     rcx, r10; hkey
0x18002b664  call    cs:__imp_RegGetValueW
0x18002b66b  nop     dword ptr [rax+rax+00h]
0x18002b670  movzx   r15d, r15b
0x18002b674  test    eax, eax
0x18002b676  mov     eax, 1
0x18002b67b  cmovz   r15d, eax
0x18002b67f  mov     [rsp+0D8h+var_98], r15b
0x18002b684  mov     rax, [rsp+0D8h+var_78]
0x18002b689  mov     r11, [rsp+0D8h+arg_0]
0x18002b691  jmp     loc_18002B4DA
0x18002b696  xor     ecx, ecx
0x18002b698  call    FileLogAllowEntry
0x18002b69d  test    al, al
0x18002b69f  jz      short loc_18002B6FA
0x18002b6a1  mov     r9d, ebx
0x18002b6a4  mov     r8d, [rsp+0D8h+arg_18]
0x18002b6ac  mov     rdx, r12
0x18002b6af  lea     rcx, aMyregquerypoli_0; "MyRegQueryPolicyValueEx read incorrect "...
0x18002b6b6  call    FileLogAdd
0x18002b6bb  jmp     short loc_18002B6FA
0x18002b6bd  mov     r9, [rsp+0D8h+var_80]
0x18002b6c2  mov     r9d, [r9]
0x18002b6c5  mov     r8, [rsp+0D8h+var_78]
0x18002b6ca  mov     r8d, [r8]
0x18002b6cd  mov     rdx, r12
0x18002b6d0  lea     rcx, aReadconfigS0x0; "ReadConfig: '%s'=0x%08X (%d)\n"
0x18002b6d7  call    FileLogAdd
0x18002b6dc  jmp     loc_18002B5FA
0x18002b6e1  mov     [r13+0], ebx
0x18002b6e5  jmp     loc_18002B590
0x18002b6ea  mov     [r14], ecx
0x18002b6ed  jmp     loc_18002B5A9
0x18002b6f2  mov     [r14], ebx
0x18002b6f5  jmp     loc_18002B5B1
0x18002b6fa  mov     eax, edi
0x18002b6fc  add     rsp, 0A0h
0x18002b703  pop     r15
0x18002b705  pop     r14
0x18002b707  pop     r13
0x18002b709  pop     r12
0x18002b70b  pop     rdi
0x18002b70c  pop     rsi
0x18002b70d  pop     rbx
0x18002b70e  retn
0x18006765c  push    rbp
0x18006765e  sub     rsp, 40h
0x180067662  mov     rbp, rdx
0x180067665  add     rsp, 40h
0x180067669  pop     rbp
0x18006766a  retn
```
