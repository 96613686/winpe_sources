# RegistryKeyEnumerator::CloseRegKey(void)

- ea: `0x180011d98`
- end: `0x180011e5f`
- name: `?CloseRegKey@RegistryKeyEnumerator@@AEAAXXZ`
- size: `199`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012c6c`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180011d98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011db1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011db1`

## string_xrefs

- `0x180011df8`: `admin\wmi\events\forwarding\common\reghelp.cpp`

## pseudocode

```c
void __fastcall RegistryKeyEnumerator::CloseRegKey(HKEY *this)
{
  HKEY v2; // rcx
  unsigned int v3; // edi
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  char v5; // [rsp+28h] [rbp-40h]
  const char *v6; // [rsp+30h] [rbp-38h]
  __int64 v7; // [rsp+38h] [rbp-30h]
  __int64 v8; // [rsp+40h] [rbp-28h]
  unsigned int v9; // [rsp+48h] [rbp-20h]
  int v10; // [rsp+4Ch] [rbp-1Ch]
  int v11; // [rsp+50h] [rbp-18h]

  v2 = *this;
  if ( v2 )
  {
    v3 = RegCloseKey(v2);
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids, v3);
      }
      v5 = 0;
      v6 = "admin\\wmi\\events\\forwarding\\common\\reghelp.cpp";
      v7 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v8 = 0;
      v9 = v3;
      v10 = -1;
      v11 = 405;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    *this = 0;
  }
}

```

## disassembly

```asm
0x180011d98  mov     [rsp+arg_0], rbx
0x180011d9d  push    rdi
0x180011d9e  sub     rsp, 60h
0x180011da2  mov     rbx, rcx
0x180011da5  mov     rcx, [rcx]; hKey
0x180011da8  test    rcx, rcx
0x180011dab  jz      loc_180011E54
0x180011db1  call    cs:__imp_RegCloseKey
0x180011db7  mov     edi, eax
0x180011db9  test    eax, eax
0x180011dbb  jz      loc_180011E4D
0x180011dc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180011dc8  lea     rax, WPP_GLOBAL_Control
0x180011dcf  cmp     rcx, rax
0x180011dd2  jz      short loc_180011DF8
0x180011dd4  test    byte ptr [rcx+1Ch], 1
0x180011dd8  jz      short loc_180011DF8
0x180011dda  cmp     byte ptr [rcx+19h], 2
0x180011dde  jb      short loc_180011DF8
0x180011de0  mov     rcx, [rcx+10h]
0x180011de4  lea     r8, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids
0x180011deb  mov     edx, 19h
0x180011df0  mov     r9d, edi
0x180011df3  call    WPP_SF_D
0x180011df8  lea     rax, aAdminWmiEvents_0; "admin\\wmi\\events\\forwarding\\common"...
0x180011dff  mov     [rsp+68h+var_40], 0
0x180011e04  mov     [rsp+68h+var_38], rax
0x180011e09  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180011e10  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180011e17  mov     [rsp+68h+var_30], 0
0x180011e20  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180011e25  mov     [rsp+68h+pExceptionObject], rax
0x180011e2a  mov     [rsp+68h+var_28], 0
0x180011e33  mov     [rsp+68h+var_20], edi
0x180011e37  mov     [rsp+68h+var_1C], 0FFFFFFFFh
0x180011e3f  mov     [rsp+68h+var_18], 195h
0x180011e47  call    _CxxThrowException_0
0x180011e4d  mov     qword ptr [rbx], 0
0x180011e54  mov     rbx, [rsp+68h+arg_0]
0x180011e59  add     rsp, 60h
0x180011e5d  pop     rdi
0x180011e5e  retn
```
