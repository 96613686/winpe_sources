# RegReadByteArrayValue(HKEY__ *,ushort const *,ulong &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x1800121fc`
- end: `0x18001241d`
- name: `?RegReadByteArrayValue@@YA_NPEAUHKEY__@@PEBGAEAKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `545`
- prototype: `char __fastcall(HKEY hKey, LPCWSTR lpValueName, LPDWORD lpType, LPBYTE *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001259c`
- `0x1800128c0`

## callees

- `0x18000195c`
- `0x180001976`
- `0x1800032dc`
- `0x180011270`
- `0x1800121fc`
- `0x18001fe50`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180012253`
- `ADVAPI32!RegQueryValueExW` at `0x1800122c1`
- `ADVAPI32!RegQueryValueExW` at `0x180012253`
- `ADVAPI32!RegQueryValueExW` at `0x1800122c1`

## string_xrefs

- `0x180012308`: `admin\wmi\events\forwarding\common\reghelp.cpp`
- `0x1800123a7`: `admin\wmi\events\forwarding\common\reghelp.cpp`

## pseudocode

```c
char __fastcall RegReadByteArrayValue(HKEY hKey, LPCWSTR lpValueName, LPDWORD lpType, LPBYTE *a4)
{
  unsigned int v8; // eax
  unsigned int v9; // edi
  unsigned int v10; // eax
  unsigned int v11; // edi
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  void **pExceptionObject; // [rsp+38h] [rbp-C8h] BYREF
  char v15; // [rsp+40h] [rbp-C0h]
  const char *v16; // [rsp+48h] [rbp-B8h]
  __int64 v17; // [rsp+50h] [rbp-B0h]
  __int64 v18; // [rsp+58h] [rbp-A8h]
  unsigned int v19; // [rsp+60h] [rbp-A0h]
  int v20; // [rsp+64h] [rbp-9Ch]
  int v21; // [rsp+68h] [rbp-98h]
  BYTE Data[528]; // [rsp+70h] [rbp-90h] BYREF

  cbData = 520;
  v8 = RegQueryValueExW(hKey, lpValueName, 0, lpType, Data, &cbData);
  v9 = v8;
  if ( v8 == 2 )
    return 0;
  if ( v8 )
  {
    if ( v8 != 234 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids, v8);
      }
      v15 = 0;
      v16 = "admin\\wmi\\events\\forwarding\\common\\reghelp.cpp";
      v17 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v18 = 0;
      v19 = v9;
      v20 = -1;
      v21 = 157;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    std::vector<unsigned char>::resize(a4, cbData);
    v10 = RegQueryValueExW(hKey, lpValueName, 0, lpType, *a4, &cbData);
    v11 = v10;
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids, v10);
      }
      v15 = 0;
      v16 = "admin\\wmi\\events\\forwarding\\common\\reghelp.cpp";
      v17 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v18 = 0;
      v19 = v11;
      v20 = -1;
      v21 = 152;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    std::vector<unsigned char>::resize(a4, cbData);
  }
  else
  {
    std::vector<unsigned char>::resize(a4, cbData);
    memcpy_0(*a4, Data, cbData);
  }
  return 1;
}

```

## disassembly

```asm
0x1800121fc  push    rbp
0x1800121fe  push    rbx
0x1800121ff  push    rsi
0x180012200  push    rdi
0x180012201  push    r14
0x180012203  push    r15
0x180012205  lea     rbp, [rsp-198h]
0x18001220d  sub     rsp, 298h
0x180012214  mov     rax, cs:__security_cookie
0x18001221b  xor     rax, rsp
0x18001221e  mov     [rbp+1C0h+var_40], rax
0x180012225  lea     rax, [rsp+2C0h+cbData]
0x18001222a  mov     [rsp+2C0h+cbData], 208h
0x180012232  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x180012237  mov     rbx, r9
0x18001223a  lea     rax, [rsp+2C0h+Data]
0x18001223f  mov     r15, r8
0x180012242  mov     r9, r8; lpType
0x180012245  mov     [rsp+2C0h+lpData], rax; lpData
0x18001224a  xor     r8d, r8d; lpReserved
0x18001224d  mov     r14, rdx
0x180012250  mov     rsi, rcx
0x180012253  call    cs:__imp_RegQueryValueExW
0x180012259  mov     edi, eax
0x18001225b  cmp     eax, 2
0x18001225e  jz      loc_1800123FC
0x180012264  test    eax, eax
0x180012266  jnz     short loc_18001228B
0x180012268  mov     edx, [rsp+2C0h+cbData]
0x18001226c  mov     rcx, rbx
0x18001226f  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x180012274  mov     r8d, [rsp+2C0h+cbData]; Size
0x180012279  lea     rdx, [rsp+2C0h+Data]; Src
0x18001227e  mov     rcx, [rbx]; void *
0x180012281  call    memcpy_0
0x180012286  jmp     loc_180012369
0x18001228b  cmp     edi, 0EAh
0x180012291  jnz     loc_180012370
0x180012297  mov     edx, [rsp+2C0h+cbData]
0x18001229b  mov     rcx, rbx
0x18001229e  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800122a3  lea     rax, [rsp+2C0h+cbData]
0x1800122a8  mov     r9, r15; lpType
0x1800122ab  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x1800122b0  xor     r8d, r8d; lpReserved
0x1800122b3  mov     rax, [rbx]
0x1800122b6  mov     rdx, r14; lpValueName
0x1800122b9  mov     rcx, rsi; hKey
0x1800122bc  mov     [rsp+2C0h+lpData], rax; lpData
0x1800122c1  call    cs:__imp_RegQueryValueExW
0x1800122c7  mov     edi, eax
0x1800122c9  test    eax, eax
0x1800122cb  jz      loc_18001235D
0x1800122d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800122d8  lea     rdx, WPP_GLOBAL_Control
0x1800122df  cmp     rcx, rdx
0x1800122e2  jz      short loc_180012308
0x1800122e4  test    byte ptr [rcx+1Ch], 1
0x1800122e8  jz      short loc_180012308
0x1800122ea  cmp     byte ptr [rcx+19h], 2
0x1800122ee  jb      short loc_180012308
0x1800122f0  mov     rcx, [rcx+10h]
0x1800122f4  lea     r8, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids
0x1800122fb  mov     edx, 10h
0x180012300  mov     r9d, eax
0x180012303  call    WPP_SF_D
0x180012308  lea     rax, aAdminWmiEvents_0; "admin\\wmi\\events\\forwarding\\common"...
0x18001230f  mov     [rsp+2C0h+var_280], 0
0x180012314  mov     [rsp+2C0h+var_278], rax
0x180012319  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180012320  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180012327  mov     [rsp+2C0h+var_270], 0
0x180012330  lea     rcx, [rsp+2C0h+pExceptionObject]; pExceptionObject
0x180012335  mov     [rsp+2C0h+pExceptionObject], rax
0x18001233a  mov     [rsp+2C0h+var_268], 0
0x180012343  mov     [rsp+2C0h+var_260], edi
0x180012347  mov     [rsp+2C0h+var_25C], 0FFFFFFFFh
0x18001234f  mov     [rsp+2C0h+var_258], 98h
0x180012357  call    _CxxThrowException_0
0x18001235d  mov     edx, [rsp+2C0h+cbData]
0x180012361  mov     rcx, rbx
0x180012364  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x180012369  mov     al, 1
0x18001236b  jmp     loc_1800123FE
0x180012370  mov     rcx, cs:WPP_GLOBAL_Control
0x180012377  lea     rdx, WPP_GLOBAL_Control
0x18001237e  cmp     rcx, rdx
0x180012381  jz      short loc_1800123A7
0x180012383  test    byte ptr [rcx+1Ch], 1
0x180012387  jz      short loc_1800123A7
0x180012389  cmp     byte ptr [rcx+19h], 2
0x18001238d  jb      short loc_1800123A7
0x18001238f  mov     rcx, [rcx+10h]
0x180012393  lea     r8, WPP_dd61285705663051d0ad8ad3622c245b_Traceguids
0x18001239a  mov     edx, 11h
0x18001239f  mov     r9d, edi
0x1800123a2  call    WPP_SF_D
0x1800123a7  lea     rax, aAdminWmiEvents_0; "admin\\wmi\\events\\forwarding\\common"...
0x1800123ae  mov     [rsp+2C0h+var_280], 0
0x1800123b3  mov     [rsp+2C0h+var_278], rax
0x1800123b8  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800123bf  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800123c6  mov     [rsp+2C0h+var_270], 0
0x1800123cf  lea     rcx, [rsp+2C0h+pExceptionObject]; pExceptionObject
0x1800123d4  mov     [rsp+2C0h+pExceptionObject], rax
0x1800123d9  mov     [rsp+2C0h+var_268], 0
0x1800123e2  mov     [rsp+2C0h+var_260], edi
0x1800123e6  mov     [rsp+2C0h+var_25C], 0FFFFFFFFh
0x1800123ee  mov     [rsp+2C0h+var_258], 9Dh
0x1800123f6  call    _CxxThrowException_0
0x1800123fc  xor     al, al
0x1800123fe  mov     rcx, [rbp+1C0h+var_40]
0x180012405  xor     rcx, rsp; StackCookie
0x180012408  call    __security_check_cookie
0x18001240d  add     rsp, 298h
0x180012414  pop     r15
0x180012416  pop     r14
0x180012418  pop     rdi
0x180012419  pop     rsi
0x18001241a  pop     rbx
0x18001241b  pop     rbp
0x18001241c  retn
```
