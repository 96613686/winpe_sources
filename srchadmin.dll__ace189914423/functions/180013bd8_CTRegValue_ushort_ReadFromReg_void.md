# CTRegValue<ushort *>::ReadFromReg(void)

- ea: `0x180013bd8`
- end: `0x180013cd9`
- name: `?ReadFromReg@?$CTRegValue@PEAG@@QEAAJXZ`
- size: `257`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010034`
- `0x180013fb0`
- `0x180013ff0`

## callees

- `0x180013bd8`

## import_xrefs

- `SHLWAPI!SHRegGetValueW` at `0x180013c20`
- `SHLWAPI!SHRegGetValueW` at `0x180013c7f`
- `SHLWAPI!SHRegGetValueW` at `0x180013c20`
- `SHLWAPI!SHRegGetValueW` at `0x180013c7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013ca7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013ca7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013c3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013c3d`

## pseudocode

```c
__int64 __fastcall CTRegValue<unsigned short *>::ReadFromReg(__int64 a1)
{
  const WCHAR *v1; // r8
  const WCHAR *v2; // rdx
  LSTATUS ValueW; // eax
  signed int v5; // ebx
  void *pvData; // rsi
  LSTATUS v7; // eax
  SIZE_T cb; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(const WCHAR **)(a1 + 8);
  v2 = *(const WCHAR **)(a1 + 16);
  LODWORD(cb) = 0;
  ValueW = SHRegGetValueW(HKEY_LOCAL_MACHINE, v2, v1, 2, 0, 0, (DWORD *)&cb);
  v5 = ValueW;
  if ( ValueW > 0 )
    v5 = (unsigned __int16)ValueW | 0x80070000;
  if ( v5 >= 0 )
  {
    pvData = CoTaskMemAlloc((unsigned int)cb);
    if ( !pvData )
      return (unsigned int)-2147024882;
    v7 = SHRegGetValueW(HKEY_LOCAL_MACHINE, *(LPCWSTR *)(a1 + 16), *(LPCWSTR *)(a1 + 8), 2, 0, pvData, (DWORD *)&cb);
    v5 = v7;
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    if ( v5 >= 0 )
    {
      *(_QWORD *)(a1 + 32) = pvData;
      *(_DWORD *)a1 = 1;
      return (unsigned int)v5;
    }
    CoTaskMemFree(pvData);
    *(_QWORD *)(a1 + 32) = 0;
  }
  if ( v5 == -2147024894 || v5 == -2147024893 )
    return 0;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180013bd8  mov     r11, rsp
0x180013bdb  mov     [r11+10h], rbx
0x180013bdf  mov     [r11+18h], rsi
0x180013be3  push    rdi
0x180013be4  sub     rsp, 40h
0x180013be8  mov     r8, [rcx+8]; pszValue
0x180013bec  lea     rax, [r11+8]
0x180013bf0  mov     rdx, [rcx+10h]; pszSubKey
0x180013bf4  mov     rdi, rcx
0x180013bf7  mov     [r11-18h], rax
0x180013bfb  mov     r9d, 2; srrfFlags
0x180013c01  mov     qword ptr [r11-20h], 0
0x180013c09  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180013c10  mov     qword ptr [r11-28h], 0
0x180013c18  mov     dword ptr [rsp+48h+cb], 0
0x180013c20  call    cs:__imp_SHRegGetValueW
0x180013c26  mov     ebx, eax
0x180013c28  test    eax, eax
0x180013c2a  jle     short loc_180013C35
0x180013c2c  movzx   ebx, ax
0x180013c2f  or      ebx, 80070000h
0x180013c35  test    ebx, ebx
0x180013c37  js      short loc_180013CB5
0x180013c39  mov     ecx, dword ptr [rsp+48h+cb]; cb
0x180013c3d  call    cs:__imp_CoTaskMemAlloc
0x180013c43  mov     rsi, rax
0x180013c46  test    rax, rax
0x180013c49  jnz     short loc_180013C52
0x180013c4b  mov     ebx, 8007000Eh
0x180013c50  jmp     short loc_180013CC7
0x180013c52  mov     r8, [rdi+8]; pszValue
0x180013c56  lea     rax, [rsp+48h+cb]
0x180013c5b  mov     rdx, [rdi+10h]; pszSubKey
0x180013c5f  mov     r9d, 2; srrfFlags
0x180013c65  mov     [rsp+48h+pcbData], rax; pcbData
0x180013c6a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180013c71  mov     [rsp+48h+pvData], rsi; pvData
0x180013c76  mov     [rsp+48h+pdwType], 0; pdwType
0x180013c7f  call    cs:__imp_SHRegGetValueW
0x180013c85  mov     ebx, eax
0x180013c87  test    eax, eax
0x180013c89  jle     short loc_180013C94
0x180013c8b  movzx   ebx, ax
0x180013c8e  or      ebx, 80070000h
0x180013c94  test    ebx, ebx
0x180013c96  js      short loc_180013CA4
0x180013c98  mov     [rdi+20h], rsi
0x180013c9c  mov     dword ptr [rdi], 1
0x180013ca2  jmp     short loc_180013CC7
0x180013ca4  mov     rcx, rsi; pv
0x180013ca7  call    cs:__imp_CoTaskMemFree
0x180013cad  mov     qword ptr [rdi+20h], 0
0x180013cb5  cmp     ebx, 80070002h
0x180013cbb  jz      short loc_180013CC5
0x180013cbd  cmp     ebx, 80070003h
0x180013cc3  jnz     short loc_180013CC7
0x180013cc5  xor     ebx, ebx
0x180013cc7  mov     rsi, [rsp+48h+arg_10]
0x180013ccc  mov     eax, ebx
0x180013cce  mov     rbx, [rsp+48h+arg_8]
0x180013cd3  add     rsp, 40h
0x180013cd7  pop     rdi
0x180013cd8  retn
```
