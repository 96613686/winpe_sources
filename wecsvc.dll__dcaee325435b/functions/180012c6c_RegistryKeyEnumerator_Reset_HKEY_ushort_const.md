# RegistryKeyEnumerator::Reset(HKEY__ *,ushort const *)

- ea: `0x180012c6c`
- end: `0x180012d5c`
- name: `?Reset@RegistryKeyEnumerator@@QEAAXPEAUHKEY__@@PEBG@Z`
- size: `240`
- prototype: `void __fastcall(HKEY *this, HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014310`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180011d98`
- `0x180011fd8`
- `0x180012c6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012ca4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012ca4`

## string_xrefs

- `0x180012ceb`: `admin\wmi\events\forwarding\common\reghelp.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RegistryKeyEnumerator::Reset(HKEY *this, HKEY hKey, LPCWSTR lpSubKey)
{
  unsigned int v6; // ebx
  void **pExceptionObject; // [rsp+30h] [rbp-48h] BYREF
  char v8; // [rsp+38h] [rbp-40h]
  const char *v9; // [rsp+40h] [rbp-38h]
  __int64 v10; // [rsp+48h] [rbp-30h]
  __int64 v11; // [rsp+50h] [rbp-28h]
  unsigned int v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+5Ch] [rbp-1Ch]
  int v14; // [rsp+60h] [rbp-18h]

  RegistryKeyEnumerator::CloseRegKey(this);
  *((_DWORD *)this + 2) = 0;
  v6 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, this);
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids, v6);
    }
    v8 = 0;
    v9 = "admin\\wmi\\events\\forwarding\\common\\reghelp.cpp";
    v10 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v11 = 0;
    v12 = v6;
    v13 = -1;
    v14 = 454;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  RegistryKeyEnumerator::QueryInfoKey((DWORD *)this, *this);
}

```

## disassembly

```asm
0x180012c6c  mov     [rsp+arg_0], rbx
0x180012c71  mov     [rsp+arg_8], rsi
0x180012c76  push    rdi
0x180012c77  sub     rsp, 70h
0x180012c7b  mov     rbx, r8
0x180012c7e  mov     rdi, rdx
0x180012c81  mov     rsi, rcx
0x180012c84  call    ?CloseRegKey@RegistryKeyEnumerator@@AEAAXXZ; RegistryKeyEnumerator::CloseRegKey(void)
0x180012c89  mov     r9d, 20019h; samDesired
0x180012c8f  mov     dword ptr [rsi+8], 0
0x180012c96  xor     r8d, r8d; ulOptions
0x180012c99  mov     [rsp+78h+phkResult], rsi; phkResult
0x180012c9e  mov     rdx, rbx; lpSubKey
0x180012ca1  mov     rcx, rdi; hKey
0x180012ca4  call    cs:__imp_RegOpenKeyExW
0x180012caa  mov     ebx, eax
0x180012cac  test    eax, eax
0x180012cae  jz      loc_180012D40
0x180012cb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180012cbb  lea     rax, WPP_GLOBAL_Control
0x180012cc2  cmp     rcx, rax
0x180012cc5  jz      short loc_180012CEB
0x180012cc7  test    byte ptr [rcx+1Ch], 1
0x180012ccb  jz      short loc_180012CEB
0x180012ccd  cmp     byte ptr [rcx+19h], 2
0x180012cd1  jb      short loc_180012CEB
0x180012cd3  mov     rcx, [rcx+10h]
0x180012cd7  lea     r8, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids
0x180012cde  mov     edx, 1Ah
0x180012ce3  mov     r9d, ebx
0x180012ce6  call    WPP_SF_D
0x180012ceb  lea     rax, aAdminWmiEvents_0; "admin\\wmi\\events\\forwarding\\common"...
0x180012cf2  mov     [rsp+78h+var_40], 0
0x180012cf7  mov     [rsp+78h+var_38], rax
0x180012cfc  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180012d03  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180012d0a  mov     [rsp+78h+var_30], 0
0x180012d13  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180012d18  mov     [rsp+78h+pExceptionObject], rax
0x180012d1d  mov     [rsp+78h+var_28], 0
0x180012d26  mov     [rsp+78h+var_20], ebx
0x180012d2a  mov     [rsp+78h+var_1C], 0FFFFFFFFh
0x180012d32  mov     [rsp+78h+var_18], 1C6h
0x180012d3a  call    _CxxThrowException_0
0x180012d40  mov     rdx, [rsi]; HKEY
0x180012d43  mov     rcx, rsi; this
0x180012d46  lea     r11, [rsp+78h+var_8]
0x180012d4b  mov     rbx, [r11+10h]
0x180012d4f  mov     rsi, [r11+18h]
0x180012d53  mov     rsp, r11
0x180012d56  pop     rdi
0x180012d57  jmp     ?QueryInfoKey@RegistryKeyEnumerator@@AEAAXPEAUHKEY__@@@Z; RegistryKeyEnumerator::QueryInfoKey(HKEY__ *)
```
