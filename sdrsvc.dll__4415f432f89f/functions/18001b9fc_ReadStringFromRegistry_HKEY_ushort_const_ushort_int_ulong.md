# _ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int,ulong)

- ea: `0x18001b9fc`
- end: `0x18001bc14`
- name: `?_ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGHK@Z`
- size: `536`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, BYTE **, int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b438`
- `0x18001b4c0`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001b9fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001baa0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001bb6f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001baa0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001bb6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bb29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bb29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bbde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bbde`

## string_xrefs

- `0x18001ba27`: `_ReadStringFromRegistry`

## pseudocode

```c
__int64 __fastcall _ReadStringFromRegistry(HKEY hKey, LPCWSTR lpValueName, BYTE **a3, int a4, unsigned int a5)
{
  __int16 v9; // ax
  signed int v10; // ebx
  LSTATUS v11; // eax
  __int16 v12; // ax
  unsigned int v13; // ebx
  BYTE *lpData; // rdi
  int v15; // eax
  bool v16; // sf
  int v17; // ebx
  DWORD lpcbData; // [rsp+30h] [rbp-40h] BYREF
  int v20; // [rsp+38h] [rbp-38h] BYREF
  __int16 v21; // [rsp+3Ch] [rbp-34h]
  __int16 v22; // [rsp+3Eh] [rbp-32h]
  int v23; // [rsp+40h] [rbp-30h]
  DWORD cbData; // [rsp+A8h] [rbp+38h] BYREF
  DWORD Type; // [rsp+B0h] [rbp+40h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v20, "_ReadStringFromRegistry", 140, 2);
  Type = 0;
  cbData = 0;
  lpcbData = 0;
  if ( a3 )
    *a3 = 0;
  v9 = 149;
  if ( !lpValueName || (v21 = 149, v9 = 150, !a3) )
  {
    v10 = -2147024809;
LABEL_5:
    v20 = v10;
    v22 = v9;
    goto LABEL_32;
  }
  v21 = 150;
  v20 = 0;
  v11 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
  v10 = v11;
  if ( a4 && v11 == 2 )
  {
    v10 = 1;
    v12 = 155;
    v20 = 1;
LABEL_31:
    v21 = v12;
    goto LABEL_32;
  }
  if ( v11 > 0 )
    v10 = (unsigned __int16)v11 | 0x80070000;
  v20 = v10;
  if ( v10 < 0 )
  {
    v22 = 158;
    v23 = 1;
    goto LABEL_32;
  }
  v13 = a5;
  v21 = 158;
  v9 = 163;
  if ( Type != a5 )
  {
    v10 = -2147023267;
    goto LABEL_5;
  }
  v21 = 163;
  v9 = 170;
  if ( (cbData & 1) != 0 )
  {
    v10 = -2130706378;
    goto LABEL_5;
  }
  v20 = 0;
  v21 = 170;
  lpData = (BYTE *)CoTaskMemAlloc(cbData);
  v9 = 173;
  if ( !lpData )
  {
    v10 = -2147024882;
    goto LABEL_5;
  }
  v21 = 173;
  lpcbData = cbData;
  v20 = 0;
  v15 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, &lpcbData);
  if ( v15 > 0 )
    v15 = (unsigned __int16)v15 | 0x80070000;
  v20 = v15;
  v16 = v15 < 0;
  v12 = 176;
  if ( !v16 )
  {
    v21 = 176;
    v12 = 181;
    if ( Type == v13 )
    {
      v21 = 181;
      v12 = 188;
      if ( lpcbData == cbData )
      {
        v21 = 188;
        v10 = 0;
        v20 = 0;
        v12 = 190;
        if ( !*(_WORD *)&lpData[2 * ((unsigned __int64)cbData >> 1) - 2] )
        {
          *a3 = lpData;
          goto LABEL_31;
        }
      }
      v17 = -2130706378;
    }
    else
    {
      v17 = -2147023267;
    }
    v20 = v17;
  }
  v22 = v12;
  CoTaskMemFree(lpData);
  v10 = v20;
LABEL_32:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v20);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001b9fc  mov     [rsp-28h+arg_0], rbx
0x18001ba01  mov     [rsp-28h+arg_18], rsi
0x18001ba06  push    rbp
0x18001ba07  push    rdi
0x18001ba08  push    r12
0x18001ba0a  push    r14
0x18001ba0c  push    r15
0x18001ba0e  mov     rbp, rsp
0x18001ba11  sub     rsp, 70h
0x18001ba15  mov     edi, r9d
0x18001ba18  mov     rsi, r8
0x18001ba1b  mov     r14, rdx
0x18001ba1e  mov     r15, rcx
0x18001ba21  mov     r9d, 2; unsigned __int16
0x18001ba27  lea     rdx, aReadstringfrom_0; "_ReadStringFromRegistry"
0x18001ba2e  mov     r8d, 8Ch; unsigned __int16
0x18001ba34  lea     rcx, [rbp+var_38]; this
0x18001ba38  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001ba3d  xor     r12d, r12d
0x18001ba40  mov     [rbp+Type], r12d
0x18001ba44  mov     [rbp+cbData], r12d
0x18001ba48  mov     [rbp+var_40], r12d
0x18001ba4c  test    rsi, rsi
0x18001ba4f  jz      short loc_18001BA54
0x18001ba51  mov     [rsi], r12
0x18001ba54  mov     eax, 95h
0x18001ba59  test    r14, r14
0x18001ba5c  jnz     short loc_18001BA6F
0x18001ba5e  mov     ebx, 80070057h
0x18001ba63  mov     [rbp+var_38], ebx
0x18001ba66  mov     [rbp+var_32], ax
0x18001ba6a  jmp     loc_18001BBF0
0x18001ba6f  mov     [rbp+var_34], ax
0x18001ba73  mov     eax, 96h
0x18001ba78  test    rsi, rsi
0x18001ba7b  jz      short loc_18001BA5E
0x18001ba7d  mov     [rbp+var_34], ax
0x18001ba81  lea     r9, [rbp+Type]; lpType
0x18001ba85  lea     rax, [rbp+cbData]
0x18001ba89  mov     [rbp+var_38], r12d
0x18001ba8d  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18001ba92  xor     r8d, r8d; lpReserved
0x18001ba95  mov     rdx, r14; lpValueName
0x18001ba98  mov     [rsp+70h+lpData], r12; lpData
0x18001ba9d  mov     rcx, r15; hKey
0x18001baa0  call    cs:__imp_RegQueryValueExW
0x18001baa6  mov     ebx, eax
0x18001baa8  test    edi, edi
0x18001baaa  jz      short loc_18001BAC1
0x18001baac  cmp     eax, 2
0x18001baaf  jnz     short loc_18001BAC1
0x18001bab1  lea     ebx, [rax-1]
0x18001bab4  mov     eax, 9Bh
0x18001bab9  mov     [rbp+var_38], ebx
0x18001babc  jmp     loc_18001BBEC
0x18001bac1  test    eax, eax
0x18001bac3  jle     short loc_18001BACE
0x18001bac5  movzx   ebx, ax
0x18001bac8  or      ebx, 80070000h
0x18001bace  mov     [rbp+var_38], ebx
0x18001bad1  mov     eax, 9Eh
0x18001bad6  test    ebx, ebx
0x18001bad8  jns     short loc_18001BAEA
0x18001bada  mov     [rbp+var_32], ax
0x18001bade  mov     [rbp+var_30], 1
0x18001bae5  jmp     loc_18001BBF0
0x18001baea  mov     ebx, [rbp+arg_20]
0x18001baed  mov     [rbp+var_34], ax
0x18001baf1  mov     eax, 0A3h
0x18001baf6  cmp     [rbp+Type], ebx
0x18001baf9  jz      short loc_18001BB05
0x18001bafb  mov     ebx, 8007065Dh
0x18001bb00  jmp     loc_18001BA63
0x18001bb05  test    byte ptr [rbp+cbData], 1
0x18001bb09  mov     [rbp+var_34], ax
0x18001bb0d  mov     eax, 0AAh
0x18001bb12  jz      short loc_18001BB1E
0x18001bb14  mov     ebx, 81000036h
0x18001bb19  jmp     loc_18001BA63
0x18001bb1e  mov     ecx, [rbp+cbData]; cb
0x18001bb21  mov     [rbp+var_38], r12d
0x18001bb25  mov     [rbp+var_34], ax
0x18001bb29  call    cs:__imp_CoTaskMemAlloc
0x18001bb2f  mov     rdi, rax
0x18001bb32  test    rax, rax
0x18001bb35  mov     eax, 0ADh
0x18001bb3a  jnz     short loc_18001BB46
0x18001bb3c  mov     ebx, 8007000Eh
0x18001bb41  jmp     loc_18001BA63
0x18001bb46  mov     [rbp+var_34], ax
0x18001bb4a  lea     r9, [rbp+Type]; lpType
0x18001bb4e  mov     eax, [rbp+cbData]
0x18001bb51  xor     r8d, r8d; lpReserved
0x18001bb54  mov     [rbp+var_40], eax
0x18001bb57  mov     rdx, r14; lpValueName
0x18001bb5a  lea     rax, [rbp+var_40]
0x18001bb5e  mov     [rbp+var_38], r12d
0x18001bb62  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18001bb67  mov     rcx, r15; hKey
0x18001bb6a  mov     [rsp+70h+lpData], rdi; lpData
0x18001bb6f  call    cs:__imp_RegQueryValueExW
0x18001bb75  test    eax, eax
0x18001bb77  jle     short loc_18001BB81
0x18001bb79  movzx   eax, ax
0x18001bb7c  or      eax, 80070000h
0x18001bb81  mov     [rbp+var_38], eax
0x18001bb84  test    eax, eax
0x18001bb86  mov     eax, 0B0h
0x18001bb8b  js      short loc_18001BBD7
0x18001bb8d  mov     [rbp+var_34], ax
0x18001bb91  mov     eax, 0B5h
0x18001bb96  cmp     [rbp+Type], ebx
0x18001bb99  jz      short loc_18001BBA2
0x18001bb9b  mov     ebx, 8007065Dh
0x18001bba0  jmp     short loc_18001BBD4
0x18001bba2  mov     ecx, [rbp+cbData]
0x18001bba5  mov     [rbp+var_34], ax
0x18001bba9  mov     eax, 0BCh
0x18001bbae  cmp     [rbp+var_40], ecx
0x18001bbb1  jnz     short loc_18001BBCF
0x18001bbb3  mov     [rbp+var_34], ax
0x18001bbb7  mov     ebx, r12d
0x18001bbba  mov     eax, ecx
0x18001bbbc  mov     [rbp+var_38], ebx
0x18001bbbf  shr     rax, 1
0x18001bbc2  cmp     [rdi+rax*2-2], r12w
0x18001bbc8  mov     eax, 0BEh
0x18001bbcd  jz      short loc_18001BBE9
0x18001bbcf  mov     ebx, 81000036h
0x18001bbd4  mov     [rbp+var_38], ebx
0x18001bbd7  mov     rcx, rdi; pv
0x18001bbda  mov     [rbp+var_32], ax
0x18001bbde  call    cs:__imp_CoTaskMemFree
0x18001bbe4  mov     ebx, [rbp+var_38]
0x18001bbe7  jmp     short loc_18001BBF0
0x18001bbe9  mov     [rsi], rdi
0x18001bbec  mov     [rbp+var_34], ax
0x18001bbf0  lea     rcx, [rbp+var_38]; this
0x18001bbf4  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001bbf9  lea     r11, [rsp+70h+var_s0]
0x18001bbfe  mov     eax, ebx
0x18001bc00  mov     rbx, [r11+30h]
0x18001bc04  mov     rsi, [r11+48h]
0x18001bc08  mov     rsp, r11
0x18001bc0b  pop     r15
0x18001bc0d  pop     r14
0x18001bc0f  pop     r12
0x18001bc11  pop     rdi
0x18001bc12  pop     rbp
0x18001bc13  retn
```
