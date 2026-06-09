# CSpp::_GetNextIndex(ulong *)

- ea: `0x180019a04`
- end: `0x180019bae`
- name: `?_GetNextIndex@CSpp@@AEAAJPEAK@Z`
- size: `426`
- prototype: `__int64 __fastcall(CSpp *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001176c`

## callees

- `0x1800141ac`
- `0x180019a04`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019b7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019b7b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019b07`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019b07`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019b41`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019b41`

## pseudocode

```c
__int64 __fastcall CSpp::_GetNextIndex(CSpp *this, unsigned int *a2)
{
  int v4; // esi
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // ebx
  __int16 v8; // ax
  LSTATUS v9; // eax
  HKEY hKey; // [rsp+30h] [rbp-40h] BYREF
  int v12; // [rsp+38h] [rbp-38h] BYREF
  __int16 v13; // [rsp+3Ch] [rbp-34h]
  __int16 v14; // [rsp+3Eh] [rbp-32h]
  unsigned int Data; // [rsp+98h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp+30h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+38h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  v4 = 1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "CSpp::_GetNextIndex", 5136, 1);
  Data = 0;
  cbData = 0;
  Type = 0;
  hKey = 0;
  if ( a2 )
  {
    *a2 = 0;
    v12 = 0;
    v13 = 5146;
    v7 = CSpp::_CreateRegKey(this, HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SPP", &hKey);
    v12 = v7;
    v8 = 5148;
    if ( v7 < 0 )
      goto LABEL_6;
    v13 = 5148;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"LastIndex", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && cbData == 4 )
      v4 = Data + 1;
    Data = v4;
    v9 = RegSetValueExW(hKey, L"LastIndex", 0, 4u, (const BYTE *)&Data, 4u);
    v7 = v9;
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
    v12 = v7;
    v8 = 5168;
    if ( v7 < 0 )
    {
LABEL_6:
      v14 = v8;
    }
    else
    {
      v13 = 5168;
      *a2 = Data;
    }
    if ( hKey )
    {
      RegCloseKey(hKey);
      v7 = v12;
    }
  }
  else
  {
    v7 = -2147024809;
    v14 = 5146;
    v12 = -2147024809;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12, v5, v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180019a04  mov     [rsp-18h+arg_0], rbx
0x180019a09  push    rbp
0x180019a0a  push    rsi
0x180019a0b  push    r14
0x180019a0d  mov     rbp, rsp
0x180019a10  sub     rsp, 70h
0x180019a14  mov     r14, rdx
0x180019a17  mov     rbx, rcx
0x180019a1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019a21  lea     rax, WPP_GLOBAL_Control
0x180019a28  cmp     rcx, rax
0x180019a2b  jz      short loc_180019A4B
0x180019a2d  test    dword ptr [rcx+1Ch], 20000000h
0x180019a34  jz      short loc_180019A4B
0x180019a36  mov     rcx, [rcx+10h]
0x180019a3a  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180019a41  mov     edx, 4Fh ; 'O'
0x180019a46  call    WPP_SF_
0x180019a4b  mov     esi, 1
0x180019a50  lea     rdx, aCsppGetnextind; "CSpp::_GetNextIndex"
0x180019a57  mov     r9d, esi; unsigned __int16
0x180019a5a  lea     rcx, [rbp+var_38]; this
0x180019a5e  mov     r8d, 1410h; unsigned __int16
0x180019a64  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180019a69  mov     [rbp+Data], 0
0x180019a70  mov     eax, 141Ah
0x180019a75  mov     [rbp+cbData], 0
0x180019a7c  mov     [rbp+Type], 0
0x180019a83  mov     [rbp+hKey], 0
0x180019a8b  test    r14, r14
0x180019a8e  jz      loc_180019B86
0x180019a94  lea     r9, [rbp+hKey]; HKEY *
0x180019a98  mov     dword ptr [r14], 0
0x180019a9f  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x180019aa6  mov     [rbp+var_38], 0
0x180019aad  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180019ab4  mov     [rbp+var_34], ax
0x180019ab8  mov     rcx, rbx; this
0x180019abb  call    ?_CreateRegKey@CSpp@@AEAAJPEAUHKEY__@@PEBGPEAPEAU2@@Z; CSpp::_CreateRegKey(HKEY__ *,ushort const *,HKEY__ * *)
0x180019ac0  mov     ebx, eax
0x180019ac2  mov     [rbp+var_38], eax
0x180019ac5  test    eax, eax
0x180019ac7  mov     eax, 141Ch
0x180019acc  jns     short loc_180019AD7
0x180019ace  mov     [rbp+var_32], ax
0x180019ad2  jmp     loc_180019B70
0x180019ad7  mov     rcx, [rbp+hKey]; hKey
0x180019adb  lea     r9, [rbp+Type]; lpType
0x180019adf  mov     [rbp+var_34], ax
0x180019ae3  lea     rdx, aLastindex; "LastIndex"
0x180019aea  lea     rax, [rbp+cbData]
0x180019aee  mov     ebx, 4
0x180019af3  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180019af8  xor     r8d, r8d; lpReserved
0x180019afb  lea     rax, [rbp+Data]
0x180019aff  mov     [rbp+cbData], ebx
0x180019b02  mov     [rsp+70h+lpData], rax; lpData
0x180019b07  call    cs:__imp_RegQueryValueExW
0x180019b0d  test    eax, eax
0x180019b0f  jnz     short loc_180019B20
0x180019b11  cmp     [rbp+Type], ebx
0x180019b14  jnz     short loc_180019B20
0x180019b16  cmp     [rbp+cbData], ebx
0x180019b19  jnz     short loc_180019B20
0x180019b1b  mov     esi, [rbp+Data]
0x180019b1e  inc     esi
0x180019b20  mov     rcx, [rbp+hKey]; hKey
0x180019b24  lea     rax, [rbp+Data]
0x180019b28  mov     dword ptr [rsp+70h+lpcbData], ebx; cbData
0x180019b2c  lea     rdx, aLastindex; "LastIndex"
0x180019b33  mov     r9d, ebx; dwType
0x180019b36  mov     [rsp+70h+lpData], rax; lpData
0x180019b3b  xor     r8d, r8d; Reserved
0x180019b3e  mov     [rbp+Data], esi
0x180019b41  call    cs:__imp_RegSetValueExW
0x180019b47  mov     ebx, eax
0x180019b49  test    eax, eax
0x180019b4b  jle     short loc_180019B56
0x180019b4d  movzx   ebx, ax
0x180019b50  or      ebx, 80070000h
0x180019b56  mov     [rbp+var_38], ebx
0x180019b59  mov     eax, 1430h
0x180019b5e  test    ebx, ebx
0x180019b60  js      loc_180019ACE
0x180019b66  mov     [rbp+var_34], ax
0x180019b6a  mov     eax, [rbp+Data]
0x180019b6d  mov     [r14], eax
0x180019b70  cmp     [rbp+hKey], 0
0x180019b75  jz      short loc_180019B92
0x180019b77  mov     rcx, [rbp+hKey]; hKey
0x180019b7b  call    cs:__imp_RegCloseKey
0x180019b81  mov     ebx, [rbp+var_38]
0x180019b84  jmp     short loc_180019B92
0x180019b86  mov     ebx, 80070057h
0x180019b8b  mov     [rbp+var_32], ax
0x180019b8f  mov     [rbp+var_38], ebx
0x180019b92  lea     rcx, [rbp+var_38]; this
0x180019b96  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180019b9b  mov     eax, ebx
0x180019b9d  mov     rbx, [rsp+70h+arg_0]
0x180019ba5  add     rsp, 70h
0x180019ba9  pop     r14
0x180019bab  pop     rsi
0x180019bac  pop     rbp
0x180019bad  retn
```
