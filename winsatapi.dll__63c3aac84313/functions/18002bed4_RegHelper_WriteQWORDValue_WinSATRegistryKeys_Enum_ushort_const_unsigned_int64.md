# RegHelper::WriteQWORDValue(WinSATRegistryKeys::Enum,ushort const *,unsigned __int64)

- ea: `0x18002bed4`
- end: `0x18002bf6f`
- name: `?WriteQWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBG_K@Z`
- size: `155`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020428`
- `0x180021294`
- `0x1800213d0`

## callees

- `0x18000e234`
- `0x1800173a4`
- `0x18002bed4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002bf4b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002bf4b`

## pseudocode

```c
__int64 __fastcall RegHelper::WriteQWORDValue(__int64 a1, const WCHAR *a2, __int64 a3)
{
  unsigned int v5; // ebx
  HKEY hKey[5]; // [rsp+30h] [rbp-28h] BYREF
  __int64 Data; // [rsp+78h] [rbp+20h] BYREF

  memset(hKey, 0, 24);
  v5 = ATL::CRegKey::Open(hKey, HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSATAPI", 2u);
  if ( !v5 )
  {
    Data = a3;
    v5 = RegSetValueExW(hKey[0], a2, 0, 0xBu, (const BYTE *)&Data, 8u);
  }
  ATL::CRegKey::Close(hKey);
  return v5;
}

```

## disassembly

```asm
0x18002bed4  mov     rax, rsp
0x18002bed7  mov     [rax+8], rbx
0x18002bedb  mov     [rax+10h], rsi
0x18002bedf  push    rdi
0x18002bee0  sub     rsp, 50h
0x18002bee4  mov     rdi, r8
0x18002bee7  mov     qword ptr [rax-28h], 0
0x18002beef  mov     rsi, rdx
0x18002bef2  mov     qword ptr [rax-20h], 0
0x18002befa  lea     r8, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002bf01  mov     qword ptr [rax-18h], 0
0x18002bf09  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18002bf10  lea     rcx, [rax-28h]; this
0x18002bf14  mov     r9d, 2; unsigned int
0x18002bf1a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002bf1f  mov     ebx, eax
0x18002bf21  test    eax, eax
0x18002bf23  jnz     short loc_18002BF53
0x18002bf25  mov     rcx, [rsp+58h+hKey]; hKey
0x18002bf2a  lea     rax, [rsp+58h+Data]
0x18002bf2f  mov     [rsp+58h+cbData], 8; cbData
0x18002bf37  lea     r9d, [rbx+0Bh]; dwType
0x18002bf3b  xor     r8d, r8d; Reserved
0x18002bf3e  mov     [rsp+58h+lpData], rax; lpData
0x18002bf43  mov     rdx, rsi; lpValueName
0x18002bf46  mov     [rsp+58h+Data], rdi
0x18002bf4b  call    cs:__imp_RegSetValueExW
0x18002bf51  mov     ebx, eax
0x18002bf53  lea     rcx, [rsp+58h+hKey]; this
0x18002bf58  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002bf5d  mov     rsi, [rsp+58h+arg_8]
0x18002bf62  mov     eax, ebx
0x18002bf64  mov     rbx, [rsp+58h+arg_0]
0x18002bf69  add     rsp, 50h
0x18002bf6d  pop     rdi
0x18002bf6e  retn
```
