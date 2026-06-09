# RegReadQWORDValue(HKEY__ *,ushort const *,unsigned __int64 &)

- ea: `0x18001274c`
- end: `0x1800128ba`
- name: `?RegReadQWORDValue@@YA_NPEAUHKEY__@@PEBGAEA_K@Z`
- size: `366`
- prototype: `char __fastcall(HKEY, const unsigned __int16 *, BYTE *lpData)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f3d0`
- `0x18000fd88`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x18001274c`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18001277c`
- `ADVAPI32!RegQueryValueExW` at `0x18001277c`

## string_xrefs

- `0x1800127cf`: `admin\wmi\events\forwarding\common\reghelp.cpp`
- `0x18001285e`: `admin\wmi\events\forwarding\common\reghelp.cpp`

## pseudocode

```c
char __fastcall RegReadQWORDValue(HKEY a1, const unsigned __int16 *a2, BYTE *lpData)
{
  unsigned int v3; // ebx
  DWORD cbData; // [rsp+30h] [rbp-40h] BYREF
  void **pExceptionObject; // [rsp+38h] [rbp-38h] BYREF
  char v7; // [rsp+40h] [rbp-30h]
  const char *v8; // [rsp+48h] [rbp-28h]
  __int64 v9; // [rsp+50h] [rbp-20h]
  __int64 v10; // [rsp+58h] [rbp-18h]
  int v11; // [rsp+60h] [rbp-10h]
  int v12; // [rsp+64h] [rbp-Ch]
  int v13; // [rsp+68h] [rbp-8h]
  DWORD Type; // [rsp+98h] [rbp+28h] BYREF

  Type = 0;
  cbData = 8;
  v3 = RegQueryValueExW(a1, a2, 0, &Type, lpData, &cbData);
  if ( v3 == 2 )
    return 0;
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids, v3);
    }
    v7 = 0;
    v8 = "admin\\wmi\\events\\forwarding\\common\\reghelp.cpp";
    v9 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v10 = 0;
    v11 = v3;
    v12 = -1;
    v13 = 54;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  if ( Type != 11 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids, 13);
    }
    v7 = 0;
    v8 = "admin\\wmi\\events\\forwarding\\common\\reghelp.cpp";
    v9 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v10 = 0;
    v11 = 13;
    v12 = -1;
    v13 = 57;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  return 1;
}

```

## disassembly

```asm
0x18001274c  mov     [rsp-8+arg_0], rbx
0x180012751  push    rbp
0x180012752  mov     rbp, rsp
0x180012755  sub     rsp, 70h
0x180012759  lea     rax, [rbp+cbData]
0x18001275d  mov     [rbp+Type], 0
0x180012764  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180012769  lea     r9, [rbp+Type]; lpType
0x18001276d  mov     [rsp+70h+lpData], r8; lpData
0x180012772  xor     r8d, r8d; lpReserved
0x180012775  mov     [rbp+cbData], 8
0x18001277c  call    cs:__imp_RegQueryValueExW
0x180012782  mov     ebx, eax
0x180012784  cmp     eax, 2
0x180012787  jnz     short loc_180012790
0x180012789  xor     al, al
0x18001278b  jmp     loc_1800128AC
0x180012790  test    ebx, ebx
0x180012792  jz      loc_18001281B
0x180012798  mov     rcx, cs:WPP_GLOBAL_Control
0x18001279f  lea     rax, WPP_GLOBAL_Control
0x1800127a6  cmp     rcx, rax
0x1800127a9  jz      short loc_1800127CF
0x1800127ab  test    byte ptr [rcx+1Ch], 1
0x1800127af  jz      short loc_1800127CF
0x1800127b1  cmp     byte ptr [rcx+19h], 2
0x1800127b5  jb      short loc_1800127CF
0x1800127b7  mov     rcx, [rcx+10h]
0x1800127bb  lea     r8, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids
0x1800127c2  mov     edx, 0Ch
0x1800127c7  mov     r9d, ebx
0x1800127ca  call    WPP_SF_D
0x1800127cf  lea     rax, aAdminWmiEvents_0; "admin\\wmi\\events\\forwarding\\common"...
0x1800127d6  mov     [rbp+var_30], 0
0x1800127da  mov     [rbp+var_28], rax
0x1800127de  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800127e5  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800127ec  mov     [rbp+var_20], 0
0x1800127f4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800127f8  mov     [rbp+pExceptionObject], rax
0x1800127fc  mov     [rbp+var_18], 0
0x180012804  mov     [rbp+var_10], ebx
0x180012807  mov     [rbp+var_C], 0FFFFFFFFh
0x18001280e  mov     [rbp+var_8], 36h ; '6'
0x180012815  call    _CxxThrowException_0
0x18001281b  cmp     [rbp+Type], 0Bh
0x18001281f  jz      loc_1800128AA
0x180012825  mov     rcx, cs:WPP_GLOBAL_Control
0x18001282c  lea     rax, WPP_GLOBAL_Control
0x180012833  mov     ebx, 0Dh
0x180012838  cmp     rcx, rax
0x18001283b  jz      short loc_18001285E
0x18001283d  test    byte ptr [rcx+1Ch], 1
0x180012841  jz      short loc_18001285E
0x180012843  cmp     byte ptr [rcx+19h], 2
0x180012847  jb      short loc_18001285E
0x180012849  mov     rcx, [rcx+10h]
0x18001284d  lea     r8, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids
0x180012854  mov     edx, ebx
0x180012856  mov     r9d, ebx
0x180012859  call    WPP_SF_D
0x18001285e  lea     rax, aAdminWmiEvents_0; "admin\\wmi\\events\\forwarding\\common"...
0x180012865  mov     [rbp+var_30], 0
0x180012869  mov     [rbp+var_28], rax
0x18001286d  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180012874  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001287b  mov     [rbp+var_20], 0
0x180012883  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180012887  mov     [rbp+pExceptionObject], rax
0x18001288b  mov     [rbp+var_18], 0
0x180012893  mov     [rbp+var_10], ebx
0x180012896  mov     [rbp+var_C], 0FFFFFFFFh
0x18001289d  mov     [rbp+var_8], 39h ; '9'
0x1800128a4  call    _CxxThrowException_0
0x1800128aa  mov     al, 1
0x1800128ac  mov     rbx, [rsp+70h+arg_0]
0x1800128b4  add     rsp, 70h
0x1800128b8  pop     rbp
0x1800128b9  retn
```
