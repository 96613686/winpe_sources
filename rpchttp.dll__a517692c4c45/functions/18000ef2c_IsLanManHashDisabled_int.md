# IsLanManHashDisabled(int *)

- ea: `0x18000ef2c`
- end: `0x18000f041`
- name: `?IsLanManHashDisabled@@YAJPEAH@Z`
- size: `277`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800081e8`
- `0x18000f74c`

## callees

- `0x18000ef2c`
- `0x18001e4a4`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000ef77`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ef77`
- `ADVAPI32!RegCloseKey` at `0x18000efef`
- `ADVAPI32!RegCloseKey` at `0x18000f037`
- `ADVAPI32!RegCloseKey` at `0x18000efef`
- `ADVAPI32!RegCloseKey` at `0x18000f037`
- `ADVAPI32!RegGetValueW` at `0x18000efd8`
- `ADVAPI32!RegGetValueW` at `0x18000efd8`

## string_xrefs

- `0x18000efae`: `lmcompatibilitylevel`

## pseudocode

```c
__int64 __fastcall IsLanManHashDisabled(int *a1)
{
  LSTATUS v2; // eax
  LSTATUS ValueW; // eax
  unsigned int v5; // ebx
  DWORD pcbData; // [rsp+50h] [rbp+8h] BYREF
  unsigned int pvData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  hkey = 0;
  pcbData = 0;
  pvData = 0;
  *a1 = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Currentcontrolset\\Control\\Lsa", 0, 0x20019u, &hkey);
  if ( v2 == 2 )
    goto LABEL_7;
  if ( v2 )
  {
    CompRpcpErrorAddRecord(0xDu, v2, 0xBE0u);
    return 14;
  }
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, L"lmcompatibilitylevel", 0x18u, 0, &pvData, &pcbData);
  v5 = ValueW;
  if ( ValueW == 2 )
  {
    if ( hkey )
      RegCloseKey(hkey);
LABEL_7:
    *a1 = 1;
    return 0;
  }
  if ( ValueW || pvData < 2 )
    CompRpcpErrorAddRecord(0xDu, ValueW, 0xBE1u);
  else
    *a1 = 1;
  if ( hkey )
    RegCloseKey(hkey);
  return v5;
}

```

## disassembly

```asm
0x18000ef2c  mov     rax, rsp
0x18000ef2f  mov     [rax+20h], rbx
0x18000ef33  push    rdi
0x18000ef34  sub     rsp, 40h
0x18000ef38  mov     qword ptr [rax+18h], 0
0x18000ef40  mov     rdi, rcx
0x18000ef43  mov     dword ptr [rax+8], 0
0x18000ef4a  mov     r9d, 20019h; samDesired
0x18000ef50  mov     dword ptr [rax+10h], 0
0x18000ef57  lea     rax, [rax+18h]
0x18000ef5b  mov     dword ptr [rcx], 0
0x18000ef61  lea     rdx, aSystemCurrentc; "System\\Currentcontrolset\\Control\\Lsa"
0x18000ef68  xor     r8d, r8d; ulOptions
0x18000ef6b  mov     [rsp+48h+phkResult], rax; phkResult
0x18000ef70  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ef77  call    cs:__imp_RegOpenKeyExW
0x18000ef7d  cmp     eax, 2
0x18000ef80  jz      short loc_18000EFF5
0x18000ef82  test    eax, eax
0x18000ef84  jz      short loc_18000EF9F
0x18000ef86  mov     r8d, 0BE0h; unsigned __int16
0x18000ef8c  mov     edx, eax; unsigned int
0x18000ef8e  mov     ecx, 0Dh; unsigned int
0x18000ef93  call    ?CompRpcpErrorAddRecord@@YAXKKG@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort)
0x18000ef98  mov     eax, 0Eh
0x18000ef9d  jmp     short loc_18000EFFD
0x18000ef9f  mov     rcx, [rsp+48h+hkey]; hkey
0x18000efa4  lea     rax, [rsp+48h+arg_0]
0x18000efa9  mov     [rsp+48h+pcbData], rax; pcbData
0x18000efae  lea     r8, aLmcompatibilit; "lmcompatibilitylevel"
0x18000efb5  lea     rax, [rsp+48h+arg_8]
0x18000efba  mov     [rsp+48h+arg_0], 4
0x18000efc2  mov     [rsp+48h+pvData], rax; pvData
0x18000efc7  mov     r9d, 18h; dwFlags
0x18000efcd  xor     edx, edx; lpSubKey
0x18000efcf  mov     [rsp+48h+phkResult], 0; pdwType
0x18000efd8  call    cs:__imp_RegGetValueW
0x18000efde  mov     ebx, eax
0x18000efe0  cmp     eax, 2
0x18000efe3  jnz     short loc_18000F008
0x18000efe5  mov     rcx, [rsp+48h+hkey]; hKey
0x18000efea  test    rcx, rcx
0x18000efed  jz      short loc_18000EFF5
0x18000efef  call    cs:__imp_RegCloseKey
0x18000eff5  mov     dword ptr [rdi], 1
0x18000effb  xor     eax, eax
0x18000effd  mov     rbx, [rsp+48h+arg_18]
0x18000f002  add     rsp, 40h
0x18000f006  pop     rdi
0x18000f007  retn
0x18000f008  test    ebx, ebx
0x18000f00a  jnz     short loc_18000F01B
0x18000f00c  cmp     [rsp+48h+arg_8], 2
0x18000f011  jb      short loc_18000F01B
0x18000f013  mov     dword ptr [rdi], 1
0x18000f019  jmp     short loc_18000F02D
0x18000f01b  mov     r8d, 0BE1h; unsigned __int16
0x18000f021  mov     edx, ebx; unsigned int
0x18000f023  mov     ecx, 0Dh; unsigned int
0x18000f028  call    ?CompRpcpErrorAddRecord@@YAXKKG@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort)
0x18000f02d  mov     rcx, [rsp+48h+hkey]; hKey
0x18000f032  test    rcx, rcx
0x18000f035  jz      short loc_18000F03D
0x18000f037  call    cs:__imp_RegCloseKey
0x18000f03d  mov     eax, ebx
0x18000f03f  jmp     short loc_18000EFFD
```
