# W32TimeDeleteConfig

- ea: `0x180051020`
- end: `0x1800510bf`
- name: `W32TimeDeleteConfig`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180050e6c`
- `0x180051020`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800510a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800510a5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180051071`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180051071`

## pseudocode

```c
__int64 __fastcall W32TimeDeleteConfig(int a1)
{
  int v2; // ebx
  unsigned int i; // eax
  __int64 v4; // rcx
  const WCHAR *v5; // rdx
  LSTATUS v6; // eax
  HKEY hKey; // [rsp+38h] [rbp+10h] BYREF

  hKey = 0;
  v2 = myRegOpenKeyForProperty(a1, &hKey);
  if ( v2 >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= 6 )
        goto LABEL_12;
      v4 = 32LL * i;
      if ( a1 == *(_DWORD *)((char *)&g_rgProperties + v4) )
        break;
    }
    v5 = *(const WCHAR **)((char *)&g_rgProperties + v4 + 16);
    if ( !v5 )
    {
LABEL_12:
      v2 = -2147023728;
      goto LABEL_13;
    }
    v6 = RegDeleteValueW(hKey, v5);
    v2 = v6;
    if ( !v6 )
      goto LABEL_11;
    if ( v6 > 0 )
      v2 = (unsigned __int16)v6 | 0x80070000;
    if ( v2 >= 0 )
LABEL_11:
      v2 = 0;
  }
LABEL_13:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180051020  mov     [rsp+arg_0], rbx
0x180051025  push    rdi
0x180051026  sub     rsp, 20h
0x18005102a  lea     rdx, [rsp+28h+hKey]; HKEY *
0x18005102f  mov     [rsp+28h+hKey], 0
0x180051038  mov     edi, ecx
0x18005103a  call    ?myRegOpenKeyForProperty@@YAJKPEAPEAUHKEY__@@@Z; myRegOpenKeyForProperty(ulong,HKEY__ * *)
0x18005103f  mov     ebx, eax
0x180051041  test    eax, eax
0x180051043  js      short loc_18005109B
0x180051045  xor     eax, eax
0x180051047  lea     rdx, ?g_rgProperties@@3PAUPropertyTable@@A; PropertyTable near * g_rgProperties
0x18005104e  cmp     eax, 6
0x180051051  jnb     short loc_180051096
0x180051053  mov     ecx, eax
0x180051055  shl     rcx, 5
0x180051059  cmp     edi, [rcx+rdx]
0x18005105c  jz      short loc_180051062
0x18005105e  inc     eax
0x180051060  jmp     short loc_18005104E
0x180051062  mov     rdx, [rcx+rdx+10h]; lpValueName
0x180051067  test    rdx, rdx
0x18005106a  jz      short loc_180051096
0x18005106c  mov     rcx, [rsp+28h+hKey]; hKey
0x180051071  call    cs:__imp_RegDeleteValueW
0x180051078  nop     dword ptr [rax+rax+00h]
0x18005107d  mov     ebx, eax
0x18005107f  test    eax, eax
0x180051081  jz      short loc_180051092
0x180051083  jle     short loc_18005108E
0x180051085  movzx   ebx, ax
0x180051088  or      ebx, 80070000h
0x18005108e  test    ebx, ebx
0x180051090  js      short loc_18005109B
0x180051092  xor     ebx, ebx
0x180051094  jmp     short loc_18005109B
0x180051096  mov     ebx, 80070490h
0x18005109b  mov     rcx, [rsp+28h+hKey]; hKey
0x1800510a0  test    rcx, rcx
0x1800510a3  jz      short loc_1800510B1
0x1800510a5  call    cs:__imp_RegCloseKey
0x1800510ac  nop     dword ptr [rax+rax+00h]
0x1800510b1  mov     eax, ebx
0x1800510b3  mov     rbx, [rsp+28h+arg_0]
0x1800510b8  add     rsp, 20h
0x1800510bc  pop     rdi
0x1800510bd  retn
```
