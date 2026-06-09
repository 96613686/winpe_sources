# PxeProviderRegister

- ea: `0x180008c90`
- end: `0x180008d19`
- name: `PxeProviderRegister`
- size: `137`
- prototype: `DWORD __stdcall(LPCWSTR pszProviderName, LPCWSTR pszModulePath, PXE_REG_INDEX Index, BOOL bIsCritical, PHKEY phProviderKey)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800050e4`
- `0x180005e44`
- `0x1800075dc`
- `0x180008c90`

## pseudocode

```c
DWORD __stdcall PxeProviderRegister(
        LPCWSTR pszProviderName,
        LPCWSTR pszModulePath,
        PXE_REG_INDEX Index,
        BOOL bIsCritical,
        PHKEY phProviderKey)
{
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  DWORD result; // eax
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8

  v9 = CPxeProviderHandler::Initialize((CPxeProviderHandler *)&off_18001C020, (void *)pszModulePath, 1);
  result = ElValidateWin32_3(v9, v10, v11, 76);
  if ( !result )
  {
    v13 = CPxeProviderHandler::Register(
            (CPxeProviderHandler *)&off_18001C020,
            pszProviderName,
            pszModulePath,
            Index,
            bIsCritical,
            phProviderKey);
    return ElValidateWin32_3(v13, v14, v15, 84);
  }
  return result;
}

```

## disassembly

```asm
0x180008c90  mov     [rsp+arg_0], rbx
0x180008c95  mov     [rsp+arg_8], rbp
0x180008c9a  mov     [rsp+arg_10], rsi
0x180008c9f  push    rdi
0x180008ca0  sub     rsp, 30h
0x180008ca4  mov     edi, r8d
0x180008ca7  mov     rbp, rcx
0x180008caa  mov     r8d, 1; int
0x180008cb0  lea     rcx, off_18001C020; this
0x180008cb7  mov     ebx, r9d
0x180008cba  mov     rsi, rdx
0x180008cbd  call    ?Initialize@CPxeProviderHandler@@QEAAKPEAXH@Z; CPxeProviderHandler::Initialize(void *,int)
0x180008cc2  mov     ecx, eax
0x180008cc4  mov     r9d, 4Ch ; 'L'
0x180008cca  call    ElValidateWin32_3
0x180008ccf  test    eax, eax
0x180008cd1  jnz     short loc_180008D03
0x180008cd3  mov     rax, [rsp+38h+phProviderKey]
0x180008cd8  lea     rcx, off_18001C020; this
0x180008cdf  mov     [rsp+38h+var_10], rax; HKEY *
0x180008ce4  mov     r9d, edi; unsigned int
0x180008ce7  mov     r8, rsi; unsigned __int16 *
0x180008cea  mov     [rsp+38h+var_18], ebx; int
0x180008cee  mov     rdx, rbp; unsigned __int16 *
0x180008cf1  call    ?Register@CPxeProviderHandler@@QEAAKPEBG0KHPEAPEAUHKEY__@@@Z; CPxeProviderHandler::Register(ushort const *,ushort const *,ulong,int,HKEY__ * *)
0x180008cf6  mov     ecx, eax
0x180008cf8  mov     r9d, 54h ; 'T'
0x180008cfe  call    ElValidateWin32_3
0x180008d03  mov     rbx, [rsp+38h+arg_0]
0x180008d08  mov     rbp, [rsp+38h+arg_8]
0x180008d0d  mov     rsi, [rsp+38h+arg_10]
0x180008d12  add     rsp, 30h
0x180008d16  pop     rdi
0x180008d17  retn
```
