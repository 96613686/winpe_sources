# RegWriteQWORDValue(HKEY__ *,ushort const *,unsigned __int64)

- ea: `0x180012ac0`
- end: `0x180012b8d`
- name: `?RegWriteQWORDValue@@YAXPEAUHKEY__@@PEBG_K@Z`
- size: `205`
- prototype: `void __fastcall(HKEY, const unsigned __int16 *, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f8bc`
- `0x18000fd88`
- `0x1800103b8`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180012ac0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012aec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012aec`

## string_xrefs

- `0x180012b33`: `admin\wmi\events\forwarding\common\reghelp.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RegWriteQWORDValue(HKEY a1, const unsigned __int16 *a2, __int64 a3)
{
  unsigned int v3; // ebx
  void **pExceptionObject; // [rsp+30h] [rbp-40h] BYREF
  char v5; // [rsp+38h] [rbp-38h]
  const char *v6; // [rsp+40h] [rbp-30h]
  __int64 v7; // [rsp+48h] [rbp-28h]
  __int64 v8; // [rsp+50h] [rbp-20h]
  unsigned int v9; // [rsp+58h] [rbp-18h]
  int v10; // [rsp+5Ch] [rbp-14h]
  int v11; // [rsp+60h] [rbp-10h]
  __int64 Data; // [rsp+90h] [rbp+20h] BYREF

  Data = a3;
  v3 = RegSetValueExW(a1, a2, 0, 0xBu, (const BYTE *)&Data, 8u);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids, v3);
    }
    v5 = 0;
    v6 = "admin\\wmi\\events\\forwarding\\common\\reghelp.cpp";
    v7 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v8 = 0;
    v9 = v3;
    v10 = -1;
    v11 = 195;
    throw (wmi::GenericException *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x180012ac0  mov     [rsp-8+arg_0], rbx
0x180012ac5  mov     [rsp-8+Data], r8
0x180012aca  push    rbp
0x180012acb  mov     rbp, rsp
0x180012ace  sub     rsp, 70h
0x180012ad2  lea     rax, [rbp+Data]
0x180012ad6  mov     [rsp+70h+cbData], 8; cbData
0x180012ade  mov     r9d, 0Bh; dwType
0x180012ae4  mov     [rsp+70h+lpData], rax; lpData
0x180012ae9  xor     r8d, r8d; Reserved
0x180012aec  call    cs:__imp_RegSetValueExW
0x180012af2  mov     ebx, eax
0x180012af4  test    eax, eax
0x180012af6  jz      loc_180012B7F
0x180012afc  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b03  lea     rax, WPP_GLOBAL_Control
0x180012b0a  cmp     rcx, rax
0x180012b0d  jz      short loc_180012B33
0x180012b0f  test    byte ptr [rcx+1Ch], 1
0x180012b13  jz      short loc_180012B33
0x180012b15  cmp     byte ptr [rcx+19h], 2
0x180012b19  jb      short loc_180012B33
0x180012b1b  mov     rcx, [rcx+10h]
0x180012b1f  lea     r8, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids
0x180012b26  mov     edx, 13h
0x180012b2b  mov     r9d, ebx
0x180012b2e  call    WPP_SF_D
0x180012b33  lea     rax, aAdminWmiEvents_0; "admin\\wmi\\events\\forwarding\\common"...
0x180012b3a  mov     [rbp+var_38], 0
0x180012b3e  mov     [rbp+var_30], rax
0x180012b42  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180012b49  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180012b50  mov     [rbp+var_28], 0
0x180012b58  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180012b5c  mov     [rbp+pExceptionObject], rax
0x180012b60  mov     [rbp+var_20], 0
0x180012b68  mov     [rbp+var_18], ebx
0x180012b6b  mov     [rbp+var_14], 0FFFFFFFFh
0x180012b72  mov     [rbp+var_10], 0C3h
0x180012b79  call    _CxxThrowException_0
0x180012b7f  mov     rbx, [rsp+70h+arg_0]
0x180012b87  add     rsp, 70h
0x180012b8b  pop     rbp
0x180012b8c  retn
```
