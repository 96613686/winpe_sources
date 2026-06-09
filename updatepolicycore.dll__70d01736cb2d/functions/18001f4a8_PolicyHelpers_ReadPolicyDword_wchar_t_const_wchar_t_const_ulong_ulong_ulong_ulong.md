# PolicyHelpers::ReadPolicyDword(wchar_t const *,wchar_t const *,ulong,ulong,ulong,ulong *)

- ea: `0x18001f4a8`
- end: `0x18001f558`
- name: `?ReadPolicyDword@PolicyHelpers@@SAJPEB_W0KKKPEAK@Z`
- size: `176`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValue, unsigned int, unsigned int, unsigned int, unsigned int *pvData)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001e25c`
- `0x18001e52c`
- `0x18001e680`
- `0x18001f950`

## callees

- `0x18001f4a8`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f50e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f50e`

## pseudocode

```c
__int64 __fastcall PolicyHelpers::ReadPolicyDword(
        LPCWSTR lpSubKey,
        LPCWSTR lpValue,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *pvData)
{
  unsigned int v6; // ebx
  LSTATUS ValueW; // eax
  DWORD pcbData; // [rsp+40h] [rbp-28h] BYREF

  v6 = 0;
  pcbData = 4;
  if ( pvData )
  {
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, lpSubKey, lpValue, 0x10u, 0, pvData, &pcbData);
    if ( ValueW )
    {
      v6 = (unsigned __int16)ValueW | 0x80070000;
      if ( ValueW <= 0 )
        return (unsigned int)ValueW;
    }
    else if ( *pvData < a4 || *pvData > a5 )
    {
      *pvData = a3;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v6;
}

```

## disassembly

```asm
0x18001f4a8  mov     [rsp+arg_10], rbx
0x18001f4ad  push    rbp
0x18001f4ae  push    rsi
0x18001f4af  push    rdi
0x18001f4b0  sub     rsp, 50h
0x18001f4b4  mov     rax, cs:__security_cookie
0x18001f4bb  xor     rax, rsp
0x18001f4be  mov     [rsp+68h+var_20], rax
0x18001f4c3  mov     rdi, [rsp+68h+arg_28]
0x18001f4cb  xor     ebx, ebx
0x18001f4cd  mov     [rsp+68h+var_28], 4
0x18001f4d5  mov     ebp, r9d
0x18001f4d8  mov     esi, r8d
0x18001f4db  test    rdi, rdi
0x18001f4de  jnz     short loc_18001F4E7
0x18001f4e0  mov     ebx, 80004003h
0x18001f4e5  jmp     short loc_18001F539
0x18001f4e7  lea     rax, [rsp+68h+var_28]
0x18001f4ec  mov     r8, rdx; lpValue
0x18001f4ef  mov     [rsp+68h+pcbData], rax; pcbData
0x18001f4f4  mov     rdx, rcx; lpSubKey
0x18001f4f7  mov     [rsp+68h+pvData], rdi; pvData
0x18001f4fc  mov     r9d, 10h; dwFlags
0x18001f502  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001f509  mov     [rsp+68h+pdwType], rbx; pdwType
0x18001f50e  call    cs:__imp_RegGetValueW
0x18001f514  test    eax, eax
0x18001f516  jz      short loc_18001F528
0x18001f518  movzx   ebx, ax
0x18001f51b  or      ebx, 80070000h
0x18001f521  test    eax, eax
0x18001f523  cmovle  ebx, eax
0x18001f526  jmp     short loc_18001F539
0x18001f528  mov     eax, [rdi]
0x18001f52a  cmp     eax, ebp
0x18001f52c  jb      short loc_18001F537
0x18001f52e  cmp     eax, [rsp+68h+arg_20]
0x18001f535  jbe     short loc_18001F539
0x18001f537  mov     [rdi], esi
0x18001f539  mov     eax, ebx
0x18001f53b  mov     rcx, [rsp+68h+var_20]
0x18001f540  xor     rcx, rsp; StackCookie
0x18001f543  call    __security_check_cookie
0x18001f548  mov     rbx, [rsp+68h+arg_10]
0x18001f550  add     rsp, 50h
0x18001f554  pop     rdi
0x18001f555  pop     rsi
0x18001f556  pop     rbp
0x18001f557  retn
```
