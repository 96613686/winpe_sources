# W32TimeSetConfig

- ea: `0x1800511d0`
- end: `0x180051288`
- name: `W32TimeSetConfig`
- size: `184`
- prototype: `__int64 __fastcall(unsigned int, DWORD, const BYTE *, DWORD)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180050e6c`
- `0x1800511d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005126e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005126e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005123a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005123a`

## pseudocode

```c
__int64 __fastcall W32TimeSetConfig(unsigned int a1, DWORD a2, const BYTE *a3, DWORD a4)
{
  signed int v8; // ebx
  unsigned int i; // eax
  __int64 v10; // rcx
  const WCHAR *v11; // rdx
  LSTATUS v12; // eax
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF

  hKey = 0;
  v8 = myRegOpenKeyForProperty(a1, &hKey);
  if ( v8 >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= 6 )
        goto LABEL_12;
      v10 = 32LL * i;
      if ( a1 == *(_DWORD *)((char *)&g_rgProperties + v10) )
        break;
    }
    v11 = *(const WCHAR **)((char *)&g_rgProperties + v10 + 16);
    if ( !v11 )
    {
LABEL_12:
      v8 = -2147023728;
      goto LABEL_13;
    }
    v12 = RegSetValueExW(hKey, v11, 0, a2, a3, a4);
    v8 = v12;
    if ( !v12 )
      goto LABEL_11;
    if ( v12 > 0 )
      v8 = (unsigned __int16)v12 | 0x80070000;
    if ( v8 >= 0 )
LABEL_11:
      v8 = 0;
  }
LABEL_13:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800511d0  push    rbx
0x1800511d2  push    rbp
0x1800511d3  push    rsi
0x1800511d4  push    rdi
0x1800511d5  push    r14
0x1800511d7  sub     rsp, 40h
0x1800511db  mov     r14d, edx
0x1800511de  mov     [rsp+68h+hKey], 0
0x1800511e7  lea     rdx, [rsp+68h+hKey]; HKEY *
0x1800511ec  mov     esi, r9d
0x1800511ef  mov     rbp, r8
0x1800511f2  mov     edi, ecx
0x1800511f4  call    ?myRegOpenKeyForProperty@@YAJKPEAPEAUHKEY__@@@Z; myRegOpenKeyForProperty(ulong,HKEY__ * *)
0x1800511f9  mov     ebx, eax
0x1800511fb  test    eax, eax
0x1800511fd  js      short loc_180051264
0x1800511ff  xor     eax, eax
0x180051201  lea     rdx, ?g_rgProperties@@3PAUPropertyTable@@A; PropertyTable near * g_rgProperties
0x180051208  cmp     eax, 6
0x18005120b  jnb     short loc_18005125F
0x18005120d  mov     ecx, eax
0x18005120f  shl     rcx, 5
0x180051213  cmp     edi, [rcx+rdx]
0x180051216  jz      short loc_18005121C
0x180051218  inc     eax
0x18005121a  jmp     short loc_180051208
0x18005121c  mov     rdx, [rcx+rdx+10h]; lpValueName
0x180051221  test    rdx, rdx
0x180051224  jz      short loc_18005125F
0x180051226  mov     rcx, [rsp+68h+hKey]; hKey
0x18005122b  mov     r9d, r14d; dwType
0x18005122e  mov     [rsp+68h+cbData], esi; cbData
0x180051232  xor     r8d, r8d; Reserved
0x180051235  mov     [rsp+68h+lpData], rbp; lpData
0x18005123a  call    cs:__imp_RegSetValueExW
0x180051241  nop     dword ptr [rax+rax+00h]
0x180051246  mov     ebx, eax
0x180051248  test    eax, eax
0x18005124a  jz      short loc_18005125B
0x18005124c  jle     short loc_180051257
0x18005124e  movzx   ebx, ax
0x180051251  or      ebx, 80070000h
0x180051257  test    ebx, ebx
0x180051259  js      short loc_180051264
0x18005125b  xor     ebx, ebx
0x18005125d  jmp     short loc_180051264
0x18005125f  mov     ebx, 80070490h
0x180051264  mov     rcx, [rsp+68h+hKey]; hKey
0x180051269  test    rcx, rcx
0x18005126c  jz      short loc_18005127A
0x18005126e  call    cs:__imp_RegCloseKey
0x180051275  nop     dword ptr [rax+rax+00h]
0x18005127a  mov     eax, ebx
0x18005127c  add     rsp, 40h
0x180051280  pop     r14
0x180051282  pop     rdi
0x180051283  pop     rsi
0x180051284  pop     rbp
0x180051285  pop     rbx
0x180051286  retn
```
