# RegReadDWORDValue(HKEY__ *,ushort const *,ulong &)

- ea: `0x180012424`
- end: `0x180012593`
- name: `?RegReadDWORDValue@@YA_NPEAUHKEY__@@PEBGAEAK@Z`
- size: `367`
- prototype: `char __fastcall(HKEY, const unsigned __int16 *, BYTE *lpData)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004288`
- `0x180007844`
- `0x180007c00`
- `0x18000e2f8`
- `0x18000f3d0`
- `0x18001483c`
- `0x180015c30`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180012424`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180012454`
- `ADVAPI32!RegQueryValueExW` at `0x180012454`

## string_xrefs

- `0x1800124a7`: `admin\wmi\events\forwarding\common\reghelp.cpp`
- `0x180012537`: `admin\wmi\events\forwarding\common\reghelp.cpp`

## pseudocode

```c
char __fastcall RegReadDWORDValue(HKEY a1, const unsigned __int16 *a2, BYTE *lpData)
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
  cbData = 4;
  v3 = RegQueryValueExW(a1, a2, 0, &Type, lpData, &cbData);
  if ( v3 == 2 )
    return 0;
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids, v3);
    }
    v7 = 0;
    v8 = "admin\\wmi\\events\\forwarding\\common\\reghelp.cpp";
    v9 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v10 = 0;
    v11 = v3;
    v12 = -1;
    v13 = 27;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  if ( Type != 4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids, 13);
    }
    v7 = 0;
    v8 = "admin\\wmi\\events\\forwarding\\common\\reghelp.cpp";
    v9 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v10 = 0;
    v11 = 13;
    v12 = -1;
    v13 = 30;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  return 1;
}

```

## disassembly

```asm
0x180012424  mov     [rsp-8+arg_0], rbx
0x180012429  push    rbp
0x18001242a  mov     rbp, rsp
0x18001242d  sub     rsp, 70h
0x180012431  lea     rax, [rbp+cbData]
0x180012435  mov     [rbp+Type], 0
0x18001243c  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180012441  lea     r9, [rbp+Type]; lpType
0x180012445  mov     [rsp+70h+lpData], r8; lpData
0x18001244a  xor     r8d, r8d; lpReserved
0x18001244d  mov     [rbp+cbData], 4
0x180012454  call    cs:__imp_RegQueryValueExW
0x18001245a  mov     ebx, eax
0x18001245c  cmp     eax, 2
0x18001245f  jnz     short loc_180012468
0x180012461  xor     al, al
0x180012463  jmp     loc_180012585
0x180012468  test    ebx, ebx
0x18001246a  jz      loc_1800124F3
0x180012470  mov     rcx, cs:WPP_GLOBAL_Control
0x180012477  lea     rax, WPP_GLOBAL_Control
0x18001247e  cmp     rcx, rax
0x180012481  jz      short loc_1800124A7
0x180012483  test    byte ptr [rcx+1Ch], 1
0x180012487  jz      short loc_1800124A7
0x180012489  cmp     byte ptr [rcx+19h], 2
0x18001248d  jb      short loc_1800124A7
0x18001248f  mov     rcx, [rcx+10h]
0x180012493  lea     r8, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids
0x18001249a  mov     edx, 0Ah
0x18001249f  mov     r9d, ebx
0x1800124a2  call    WPP_SF_D
0x1800124a7  lea     rax, aAdminWmiEvents_0; "admin\\wmi\\events\\forwarding\\common"...
0x1800124ae  mov     [rbp+var_30], 0
0x1800124b2  mov     [rbp+var_28], rax
0x1800124b6  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800124bd  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800124c4  mov     [rbp+var_20], 0
0x1800124cc  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800124d0  mov     [rbp+pExceptionObject], rax
0x1800124d4  mov     [rbp+var_18], 0
0x1800124dc  mov     [rbp+var_10], ebx
0x1800124df  mov     [rbp+var_C], 0FFFFFFFFh
0x1800124e6  mov     [rbp+var_8], 1Bh
0x1800124ed  call    _CxxThrowException_0
0x1800124f3  cmp     [rbp+Type], 4
0x1800124f7  jz      loc_180012583
0x1800124fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180012504  lea     rax, WPP_GLOBAL_Control
0x18001250b  mov     ebx, 0Dh
0x180012510  cmp     rcx, rax
0x180012513  jz      short loc_180012537
0x180012515  test    byte ptr [rcx+1Ch], 1
0x180012519  jz      short loc_180012537
0x18001251b  cmp     byte ptr [rcx+19h], 2
0x18001251f  jb      short loc_180012537
0x180012521  mov     rcx, [rcx+10h]
0x180012525  lea     edx, [rbx-2]
0x180012528  mov     r9d, ebx
0x18001252b  lea     r8, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids
0x180012532  call    WPP_SF_D
0x180012537  lea     rax, aAdminWmiEvents_0; "admin\\wmi\\events\\forwarding\\common"...
0x18001253e  mov     [rbp+var_30], 0
0x180012542  mov     [rbp+var_28], rax
0x180012546  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001254d  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180012554  mov     [rbp+var_20], 0
0x18001255c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180012560  mov     [rbp+pExceptionObject], rax
0x180012564  mov     [rbp+var_18], 0
0x18001256c  mov     [rbp+var_10], ebx
0x18001256f  mov     [rbp+var_C], 0FFFFFFFFh
0x180012576  mov     [rbp+var_8], 1Eh
0x18001257d  call    _CxxThrowException_0
0x180012583  mov     al, 1
0x180012585  mov     rbx, [rsp+70h+arg_0]
0x18001258d  add     rsp, 70h
0x180012591  pop     rbp
0x180012592  retn
```
