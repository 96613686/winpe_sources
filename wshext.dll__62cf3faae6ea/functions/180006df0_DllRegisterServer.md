# DllRegisterServer

- ea: `0x180006df0`
- end: `0x1800071cf`
- name: `DllRegisterServer`
- size: `991`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800031f4`
- `0x180003200`
- `0x1800051a8`
- `0x180006b40`
- `0x180006d04`
- `0x180006df0`
- `0x180009cc8`
- `0x18000a55c`

## import_xrefs

- `KERNEL32!SetEnvironmentVariableA` at `0x180007095`
- `KERNEL32!SetEnvironmentVariableA` at `0x180007095`
- `ADVAPI32!RegOpenKeyExA` at `0x180006e5c`
- `ADVAPI32!RegOpenKeyExA` at `0x180006e84`
- `ADVAPI32!RegOpenKeyExA` at `0x180006eb9`
- `ADVAPI32!RegOpenKeyExA` at `0x180006e5c`
- `ADVAPI32!RegOpenKeyExA` at `0x180006e84`
- `ADVAPI32!RegOpenKeyExA` at `0x180006eb9`
- `ADVAPI32!RegSetValueExA` at `0x180007079`
- `ADVAPI32!RegSetValueExA` at `0x18000715f`
- `ADVAPI32!RegSetValueExA` at `0x180007079`
- `ADVAPI32!RegSetValueExA` at `0x18000715f`
- `ADVAPI32!RegCreateKeyExA` at `0x1800070f5`
- `ADVAPI32!RegCreateKeyExA` at `0x180007134`
- `ADVAPI32!RegCreateKeyExA` at `0x1800070f5`
- `ADVAPI32!RegCreateKeyExA` at `0x180007134`
- `ADVAPI32!RegQueryValueExA` at `0x180006ee3`
- `ADVAPI32!RegQueryValueExA` at `0x180006f2d`
- `ADVAPI32!RegQueryValueExA` at `0x180006ee3`
- `ADVAPI32!RegQueryValueExA` at `0x180006f2d`
- `ADVAPI32!RegCloseKey` at `0x1800070a9`
- `ADVAPI32!RegCloseKey` at `0x1800070b8`
- `ADVAPI32!RegCloseKey` at `0x18000716e`
- `ADVAPI32!RegCloseKey` at `0x18000717d`
- `ADVAPI32!RegCloseKey` at `0x18000718c`
- `ADVAPI32!RegCloseKey` at `0x1800070a9`
- `ADVAPI32!RegCloseKey` at `0x1800070b8`
- `ADVAPI32!RegCloseKey` at `0x18000716e`
- `ADVAPI32!RegCloseKey` at `0x18000717d`
- `ADVAPI32!RegCloseKey` at `0x18000718c`

## string_xrefs

- `0x180006e90`: `PATHEXT`
- `0x18000706d`: `PATHEXT`
- `0x18000708e`: `PATHEXT`
- `0x180007142`: `.COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  unsigned int v0; // edi
  LPBYTE v1; // r14
  BYTE *v2; // rsi
  _DWORD *v3; // r12
  struct _GUID *v4; // rdx
  int v5; // r13d
  const char * near *v6; // r15
  int ExtInPathext; // eax
  __int64 v8; // rax
  __int64 v9; // r8
  int i; // edx
  __int64 v11; // rcx
  unsigned int j; // r11d
  const char * near *v13; // rbx
  __int64 v14; // rax
  int v15; // r8d
  __int64 v16; // r9
  int k; // r10d
  __int64 v18; // rdx
  __int64 v19; // rcx
  LSTATUS v20; // eax
  unsigned int v21; // ecx
  HKEY phkResult; // [rsp+50h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-20h] BYREF
  LPBYTE v25; // [rsp+60h] [rbp-18h]
  DWORD cbData; // [rsp+C0h] [rbp+48h] BYREF
  DWORD Type; // [rsp+C8h] [rbp+50h] BYREF
  DWORD dwDisposition; // [rsp+D0h] [rbp+58h] BYREF
  HKEY v29; // [rsp+D8h] [rbp+60h] BYREF

  v0 = 0;
  Type = 0;
  v1 = 0;
  cbData = 0;
  v2 = 0;
  hKey = 0;
  v3 = 0;
  phkResult = 0;
  v29 = 0;
  SipRegisterServer();
  RegisterSignControl();
  AddEventSource();
  if ( Global::g_fWindowsNT && !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SYSTEM\\CurrentControlSet\\Control", 0, 1u, &hKey) )
  {
    if ( RegOpenKeyExA(hKey, "Session Manager", 0, 1u, &phkResult)
      || RegOpenKeyExA(phkResult, "Environment", 0, 0x2001Fu, &v29)
      || RegQueryValueExA(v29, "PATHEXT", 0, &Type, 0, &cbData) )
    {
      if ( v29 )
        RegCloseKey(v29);
      if ( phkResult )
        RegCloseKey(phkResult);
      dwDisposition = 0;
      if ( !RegCreateKeyExA(hKey, "Session Manager", 0, (LPSTR)Class, 0, 1u, 0, &phkResult, &dwDisposition)
        && !RegCreateKeyExA(phkResult, "Environment", 0, (LPSTR)Class, 0, 0x2001Fu, 0, &v29, &dwDisposition) )
      {
        RegSetValueExA(v29, "PATHEXT", 0, 1u, ".COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH", 0x31u);
      }
    }
    else if ( Type == 1 )
    {
      v25 = (LPBYTE)operator new(cbData);
      v1 = v25;
      if ( v25 )
      {
        if ( !RegQueryValueExA(v29, "PATHEXT", 0, 0, v25, &cbData) )
        {
          v3 = operator new(0x18u);
          if ( v3 )
          {
            v5 = 0;
            do
            {
              v6 = (&GSZ_PATHEXT_ADDITIONS)[v0];
              ExtInPathext = FindExtInPathext(v1, v6);
              v3[v0] = ExtInPathext == 0;
              if ( !ExtInPathext )
              {
                if ( v6 )
                {
                  v8 = -1;
                  do
                    ++v8;
                  while ( *((_BYTE *)v6 + v8) );
                }
                else
                {
                  LODWORD(v8) = 0;
                }
                v5 += v8 + 1;
              }
              ++v0;
            }
            while ( v0 < 6 );
            v2 = 0;
            if ( v5 )
            {
              v2 = (BYTE *)operator new(v5 + cbData);
              if ( v2 )
              {
                v9 = -1;
                do
                  ++v9;
                while ( v1[v9] );
                for ( i = 0; i < (int)v9; v2[v11] = v1[v11] )
                  v11 = (unsigned int)i++;
                for ( j = 0; j < 6; ++j )
                {
                  if ( v3[j] )
                  {
                    v13 = (&GSZ_PATHEXT_ADDITIONS)[j];
                    v14 = (int)v9;
                    v15 = v9 + 1;
                    v2[v14] = 59;
                    if ( v13 )
                    {
                      v16 = -1;
                      do
                        ++v16;
                      while ( *((_BYTE *)v13 + v16) );
                      for ( k = 0; k < (int)v16; v2[v19] = *((_BYTE *)v13 + v18) )
                      {
                        v18 = k;
                        v19 = k + v15;
                        ++k;
                      }
                    }
                    else
                    {
                      LODWORD(v16) = 0;
                    }
                    LODWORD(v9) = v16 + v15;
                  }
                }
                v2[(int)v9] = 0;
                v20 = RegSetValueExA(v29, "PATHEXT", 0, 1u, v2, v5 + cbData);
                v1 = v25;
                if ( !v20 )
                  SetEnvironmentVariableA("PATHEXT", (LPCSTR)v2);
              }
            }
          }
        }
      }
    }
  }
  if ( v29 )
    RegCloseKey(v29);
  if ( phkResult )
    RegCloseKey(phkResult);
  v21 = (unsigned int)hKey;
  if ( hKey )
    RegCloseKey(hKey);
  if ( v1 )
    operator delete(v1);
  if ( v2 )
    operator delete(v2);
  if ( v3 )
    operator delete(v3);
  return TaDllRegisterServer(v21, v4);
}

```

## disassembly

```asm
0x180006df0  push    rbp
0x180006df2  push    rbx
0x180006df3  push    rsi
0x180006df4  push    rdi
0x180006df5  push    r12
0x180006df7  push    r13
0x180006df9  push    r14
0x180006dfb  push    r15
0x180006dfd  mov     rbp, rsp
0x180006e00  sub     rsp, 78h
0x180006e04  xor     edi, edi
0x180006e06  mov     [rbp+Type], edi
0x180006e09  mov     r14d, edi
0x180006e0c  mov     [rbp+cbData], edi
0x180006e0f  mov     esi, edi
0x180006e11  mov     [rbp+hKey], rdi
0x180006e15  mov     r12d, edi
0x180006e18  mov     [rbp+var_28], rdi
0x180006e1c  mov     [rbp+arg_18], rdi
0x180006e20  call    ?SipRegisterServer@@YAJXZ; SipRegisterServer(void)
0x180006e25  call    ?RegisterSignControl@@YAJXZ; RegisterSignControl(void)
0x180006e2a  call    ?AddEventSource@@YAXXZ; AddEventSource(void)
0x180006e2f  cmp     cs:?g_fWindowsNT@Global@@2_NA, dil; bool Global::g_fWindowsNT
0x180006e36  jz      loc_180007165
0x180006e3c  lea     rax, [rbp+hKey]
0x180006e40  xor     r8d, r8d; ulOptions
0x180006e43  lea     ebx, [rdi+1]
0x180006e46  mov     [rsp+78h+phkResult], rax; phkResult
0x180006e4b  mov     r9d, ebx; samDesired
0x180006e4e  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control"
0x180006e55  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006e5c  call    cs:__imp_RegOpenKeyExA
0x180006e62  test    eax, eax
0x180006e64  jnz     loc_180007165
0x180006e6a  mov     rcx, [rbp+hKey]; hKey
0x180006e6e  lea     rax, [rbp+var_28]
0x180006e72  mov     r9d, ebx; samDesired
0x180006e75  mov     [rsp+78h+phkResult], rax; phkResult
0x180006e7a  xor     r8d, r8d; ulOptions
0x180006e7d  lea     rdx, aSessionManager; "Session Manager"
0x180006e84  call    cs:__imp_RegOpenKeyExA
0x180006e8a  mov     r15d, 2001Fh
0x180006e90  lea     r13, Name; "PATHEXT"
0x180006e97  test    eax, eax
0x180006e99  jnz     loc_1800070A0
0x180006e9f  mov     rcx, [rbp+var_28]; hKey
0x180006ea3  lea     rax, [rbp+arg_18]
0x180006ea7  mov     r9d, r15d; samDesired
0x180006eaa  mov     [rsp+78h+phkResult], rax; phkResult
0x180006eaf  xor     r8d, r8d; ulOptions
0x180006eb2  lea     rdx, aEnvironment; "Environment"
0x180006eb9  call    cs:__imp_RegOpenKeyExA
0x180006ebf  test    eax, eax
0x180006ec1  jnz     loc_1800070A0
0x180006ec7  mov     rcx, [rbp+arg_18]; hKey
0x180006ecb  lea     rax, [rbp+cbData]
0x180006ecf  mov     [rsp+78h+lpcbData], rax; lpcbData
0x180006ed4  lea     r9, [rbp+Type]; lpType
0x180006ed8  xor     r8d, r8d; lpReserved
0x180006edb  mov     [rsp+78h+phkResult], rdi; lpData
0x180006ee0  mov     rdx, r13; lpValueName
0x180006ee3  call    cs:__imp_RegQueryValueExA
0x180006ee9  test    eax, eax
0x180006eeb  jnz     loc_1800070A0
0x180006ef1  cmp     [rbp+Type], ebx
0x180006ef4  jnz     loc_180007165
0x180006efa  mov     ecx, [rbp+cbData]; Size
0x180006efd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006f02  mov     [rbp+var_18], rax
0x180006f06  mov     r14, rax
0x180006f09  test    rax, rax
0x180006f0c  jz      loc_180007165
0x180006f12  mov     rcx, [rbp+arg_18]; hKey
0x180006f16  lea     rax, [rbp+cbData]
0x180006f1a  mov     [rsp+78h+lpcbData], rax; lpcbData
0x180006f1f  xor     r9d, r9d; lpType
0x180006f22  xor     r8d, r8d; lpReserved
0x180006f25  mov     [rsp+78h+phkResult], r14; lpData
0x180006f2a  mov     rdx, r13; lpValueName
0x180006f2d  call    cs:__imp_RegQueryValueExA
0x180006f33  test    eax, eax
0x180006f35  jnz     loc_180007165
0x180006f3b  lea     ecx, [rdi+18h]; Size
0x180006f3e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006f43  mov     r12, rax
0x180006f46  test    rax, rax
0x180006f49  jz      loc_180007165
0x180006f4f  mov     r13d, edi
0x180006f52  lea     rsi, ?GSZ_PATHEXT_ADDITIONS@@3PAPEBDA; char const * near * GSZ_PATHEXT_ADDITIONS
0x180006f59  movsxd  rbx, edi
0x180006f5c  mov     rcx, r14
0x180006f5f  mov     r15, [rsi+rbx*8]
0x180006f63  mov     rdx, r15
0x180006f66  call    FindExtInPathext
0x180006f6b  xor     ecx, ecx
0x180006f6d  test    eax, eax
0x180006f6f  setz    cl
0x180006f72  mov     [r12+rbx*4], ecx
0x180006f76  test    eax, eax
0x180006f78  jnz     short loc_180006F97
0x180006f7a  test    r15, r15
0x180006f7d  jz      short loc_180006F8F
0x180006f7f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006f83  inc     rax
0x180006f86  cmp     byte ptr [r15+rax], 0
0x180006f8b  jnz     short loc_180006F83
0x180006f8d  jmp     short loc_180006F91
0x180006f8f  xor     eax, eax
0x180006f91  inc     r13d
0x180006f94  add     r13d, eax
0x180006f97  mov     r15d, 1
0x180006f9d  add     edi, r15d
0x180006fa0  cmp     edi, 6
0x180006fa3  jb      short loc_180006F59
0x180006fa5  xor     edi, edi
0x180006fa7  mov     esi, edi
0x180006fa9  test    r13d, r13d
0x180006fac  jz      loc_180007165
0x180006fb2  mov     ecx, [rbp+cbData]
0x180006fb5  add     ecx, r13d; Size
0x180006fb8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006fbd  mov     rsi, rax
0x180006fc0  test    rax, rax
0x180006fc3  jz      loc_180007165
0x180006fc9  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006fcd  inc     r8
0x180006fd0  cmp     [r14+r8], dil
0x180006fd4  jnz     short loc_180006FCD
0x180006fd6  mov     edx, edi
0x180006fd8  test    r8d, r8d
0x180006fdb  jle     short loc_180006FEE
0x180006fdd  mov     ecx, edx
0x180006fdf  add     edx, r15d
0x180006fe2  mov     al, [rcx+r14]
0x180006fe6  mov     [rcx+rsi], al
0x180006fe9  cmp     edx, r8d
0x180006fec  jl      short loc_180006FDD
0x180006fee  mov     r11d, edi
0x180006ff1  lea     r14, ?GSZ_PATHEXT_ADDITIONS@@3PAPEBDA; char const * near * GSZ_PATHEXT_ADDITIONS
0x180006ff8  movsxd  rcx, r11d
0x180006ffb  cmp     [r12+rcx*4], edi
0x180006fff  jz      short loc_180007049
0x180007001  mov     rbx, [r14+rcx*8]
0x180007005  movsxd  rax, r8d
0x180007008  add     r8d, r15d
0x18000700b  mov     byte ptr [rax+rsi], 3Bh ; ';'
0x18000700f  test    rbx, rbx
0x180007012  jz      short loc_180007043
0x180007014  or      r9, 0FFFFFFFFFFFFFFFFh
0x180007018  inc     r9
0x18000701b  cmp     [rbx+r9], dil
0x18000701f  jnz     short loc_180007018
0x180007021  mov     r10d, edi
0x180007024  test    r9d, r9d
0x180007027  jle     short loc_180007046
0x180007029  lea     eax, [r10+r8]
0x18000702d  movsxd  rdx, r10d
0x180007030  movsxd  rcx, eax
0x180007033  add     r10d, r15d
0x180007036  mov     al, [rdx+rbx]
0x180007039  mov     [rcx+rsi], al
0x18000703c  cmp     r10d, r9d
0x18000703f  jl      short loc_180007029
0x180007041  jmp     short loc_180007046
0x180007043  mov     r9d, edi
0x180007046  add     r8d, r9d
0x180007049  add     r11d, r15d
0x18000704c  cmp     r11d, 6
0x180007050  jb      short loc_180006FF8
0x180007052  movsxd  rax, r8d
0x180007055  mov     r9d, r15d; dwType
0x180007058  xor     r8d, r8d; Reserved
0x18000705b  mov     [rax+rsi], dil
0x18000705f  mov     edx, [rbp+cbData]
0x180007062  mov     rcx, [rbp+arg_18]; hKey
0x180007066  add     edx, r13d
0x180007069  mov     dword ptr [rsp+78h+lpcbData], edx; cbData
0x18000706d  lea     rdx, Name; "PATHEXT"
0x180007074  mov     [rsp+78h+phkResult], rsi; lpData
0x180007079  call    cs:__imp_RegSetValueExA
0x18000707f  mov     r14, [rbp+var_18]
0x180007083  test    eax, eax
0x180007085  jnz     loc_180007165
0x18000708b  mov     rdx, rsi; lpValue
0x18000708e  lea     rcx, Name; "PATHEXT"
0x180007095  call    cs:__imp_SetEnvironmentVariableA
0x18000709b  jmp     loc_180007165
0x1800070a0  mov     rcx, [rbp+arg_18]; hKey
0x1800070a4  test    rcx, rcx
0x1800070a7  jz      short loc_1800070AF
0x1800070a9  call    cs:__imp_RegCloseKey
0x1800070af  mov     rcx, [rbp+var_28]; hKey
0x1800070b3  test    rcx, rcx
0x1800070b6  jz      short loc_1800070BE
0x1800070b8  call    cs:__imp_RegCloseKey
0x1800070be  mov     rcx, [rbp+hKey]; hKey
0x1800070c2  lea     rax, [rbp+dwDisposition]
0x1800070c6  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x1800070cb  lea     r9, Class; lpClass
0x1800070d2  lea     rax, [rbp+var_28]
0x1800070d6  mov     [rbp+dwDisposition], edi
0x1800070d9  mov     [rsp+78h+var_40], rax; phkResult
0x1800070de  lea     rdx, aSessionManager; "Session Manager"
0x1800070e5  mov     [rsp+78h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800070ea  xor     r8d, r8d; Reserved
0x1800070ed  mov     dword ptr [rsp+78h+lpcbData], ebx; samDesired
0x1800070f1  mov     dword ptr [rsp+78h+phkResult], edi; dwOptions
0x1800070f5  call    cs:__imp_RegCreateKeyExA
0x1800070fb  test    eax, eax
0x1800070fd  jnz     short loc_180007165
0x1800070ff  mov     rcx, [rbp+var_28]; hKey
0x180007103  lea     rax, [rbp+dwDisposition]
0x180007107  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x18000710c  lea     r9, Class; lpClass
0x180007113  lea     rax, [rbp+arg_18]
0x180007117  xor     r8d, r8d; Reserved
0x18000711a  mov     [rsp+78h+var_40], rax; phkResult
0x18000711f  lea     rdx, aEnvironment; "Environment"
0x180007126  mov     [rsp+78h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000712b  mov     dword ptr [rsp+78h+lpcbData], r15d; samDesired
0x180007130  mov     dword ptr [rsp+78h+phkResult], edi; dwOptions
0x180007134  call    cs:__imp_RegCreateKeyExA
0x18000713a  test    eax, eax
0x18000713c  jnz     short loc_180007165
0x18000713e  mov     rcx, [rbp+arg_18]; hKey
0x180007142  lea     rax, aComExeBatCmdVb; ".COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;"...
0x180007149  mov     dword ptr [rsp+78h+lpcbData], 31h ; '1'; cbData
0x180007151  mov     r9d, ebx; dwType
0x180007154  xor     r8d, r8d; Reserved
0x180007157  mov     [rsp+78h+phkResult], rax; lpData
0x18000715c  mov     rdx, r13; lpValueName
0x18000715f  call    cs:__imp_RegSetValueExA
0x180007165  mov     rcx, [rbp+arg_18]; hKey
0x180007169  test    rcx, rcx
0x18000716c  jz      short loc_180007174
0x18000716e  call    cs:__imp_RegCloseKey
0x180007174  mov     rcx, [rbp+var_28]; hKey
0x180007178  test    rcx, rcx
0x18000717b  jz      short loc_180007183
0x18000717d  call    cs:__imp_RegCloseKey
0x180007183  mov     rcx, [rbp+hKey]; hKey
0x180007187  test    rcx, rcx
0x18000718a  jz      short loc_180007192
0x18000718c  call    cs:__imp_RegCloseKey
0x180007192  test    r14, r14
0x180007195  jz      short loc_18000719F
0x180007197  mov     rcx, r14; Block
0x18000719a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000719f  test    rsi, rsi
0x1800071a2  jz      short loc_1800071AC
0x1800071a4  mov     rcx, rsi; Block
0x1800071a7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800071ac  test    r12, r12
0x1800071af  jz      short loc_1800071B9
0x1800071b1  mov     rcx, r12; Block
0x1800071b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800071b9  call    ?TaDllRegisterServer@@YAJIPEAU_GUID@@@Z; TaDllRegisterServer(uint,_GUID *)
0x1800071be  add     rsp, 78h
0x1800071c2  pop     r15
0x1800071c4  pop     r14
0x1800071c6  pop     r13
0x1800071c8  pop     r12
0x1800071ca  pop     rdi
0x1800071cb  pop     rsi
0x1800071cc  pop     rbx
0x1800071cd  pop     rbp
0x1800071ce  retn
```
