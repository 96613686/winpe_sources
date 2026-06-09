# RegistryKeyEnumerator::RegistryKeyEnumerator(HKEY__ *,ushort const *)

- ea: `0x180011c60`
- end: `0x180011d66`
- name: `??0RegistryKeyEnumerator@@QEAA@PEAUHKEY__@@PEBG@Z`
- size: `262`
- prototype: `RegistryKeyEnumerator *__fastcall(RegistryKeyEnumerator *__hidden this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014310`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180011c60`
- `0x180011fd8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011cad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011cad`

## string_xrefs

- `0x180011cf9`: `admin\wmi\events\forwarding\common\reghelp.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
RegistryKeyEnumerator *__fastcall RegistryKeyEnumerator::RegistryKeyEnumerator(
        RegistryKeyEnumerator *this,
        HKEY a2,
        const unsigned __int16 *a3)
{
  unsigned int v4; // edi
  void **pExceptionObject; // [rsp+30h] [rbp-48h] BYREF
  char v7; // [rsp+38h] [rbp-40h]
  const char *v8; // [rsp+40h] [rbp-38h]
  __int64 v9; // [rsp+48h] [rbp-30h]
  __int64 v10; // [rsp+50h] [rbp-28h]
  unsigned int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]
  int v13; // [rsp+60h] [rbp-18h]

  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\EventCollector",
         0,
         0x20019u,
         (PHKEY)this);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids, v4);
    }
    v7 = 0;
    v8 = "admin\\wmi\\events\\forwarding\\common\\reghelp.cpp";
    v9 = 0;
    v10 = 0;
    v11 = v4;
    v12 = -1;
    v13 = 388;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  RegistryKeyEnumerator::QueryInfoKey(this, *(HKEY *)this);
  return this;
}

```

## disassembly

```asm
0x180011c60  mov     [rsp+arg_8], rbx
0x180011c65  mov     [rsp+arg_0], rcx
0x180011c6a  push    rdi
0x180011c6b  sub     rsp, 70h
0x180011c6f  mov     rbx, rcx
0x180011c72  mov     dword ptr [rcx+8], 0
0x180011c79  mov     qword ptr [rcx+10h], 0
0x180011c81  mov     qword ptr [rcx+18h], 0
0x180011c89  mov     qword ptr [rcx+20h], 0
0x180011c91  mov     [rsp+78h+phkResult], rcx; phkResult
0x180011c96  mov     r9d, 20019h; samDesired
0x180011c9c  xor     r8d, r8d; ulOptions
0x180011c9f  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180011ca6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011cad  call    cs:__imp_RegOpenKeyExW
0x180011cb3  mov     edi, eax
0x180011cb5  test    eax, eax
0x180011cb7  jz      loc_180011D49
0x180011cbd  lea     rax, WPP_GLOBAL_Control
0x180011cc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ccb  cmp     rcx, rax
0x180011cce  jz      short loc_180011CF4
0x180011cd0  test    byte ptr [rcx+1Ch], 1
0x180011cd4  jz      short loc_180011CF4
0x180011cd6  cmp     byte ptr [rcx+19h], 2
0x180011cda  jb      short loc_180011CF4
0x180011cdc  mov     edx, 18h
0x180011ce1  mov     r9d, edi
0x180011ce4  lea     r8, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids
0x180011ceb  mov     rcx, [rcx+10h]
0x180011cef  call    WPP_SF_D
0x180011cf4  mov     [rsp+78h+var_40], 0
0x180011cf9  lea     rax, aAdminWmiEvents_0; "admin\\wmi\\events\\forwarding\\common"...
0x180011d00  mov     [rsp+78h+var_38], rax
0x180011d05  mov     [rsp+78h+var_30], 0
0x180011d0e  mov     [rsp+78h+var_28], 0
0x180011d17  mov     [rsp+78h+var_20], edi
0x180011d1b  mov     [rsp+78h+var_1C], 0FFFFFFFFh
0x180011d23  mov     [rsp+78h+var_18], 184h
0x180011d2b  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180011d32  mov     [rsp+78h+pExceptionObject], rax
0x180011d37  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180011d3e  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180011d43  call    _CxxThrowException_0
0x180011d49  mov     rdx, [rbx]; HKEY
0x180011d4c  mov     rcx, rbx; this
0x180011d4f  call    ?QueryInfoKey@RegistryKeyEnumerator@@AEAAXPEAUHKEY__@@@Z; RegistryKeyEnumerator::QueryInfoKey(HKEY__ *)
0x180011d54  nop
0x180011d55  mov     rax, rbx
0x180011d58  mov     rbx, [rsp+78h+arg_8]
0x180011d60  add     rsp, 70h
0x180011d64  pop     rdi
0x180011d65  retn
```
