# SxRegReadString(HKEY__ *,ushort const *,CBsString *)

- ea: `0x18001e7e0`
- end: `0x18001e9d0`
- name: `?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z`
- size: `496`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, struct CBsString *this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x18001e41c`
- `0x18001e54c`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001e7e0`
- `0x18001f6e4`
- `0x18001f7f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e89f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e92b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e89f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e92b`

## string_xrefs

- `0x18001e7fc`: `SxRegReadString`

## pseudocode

```c
__int64 __fastcall SxRegReadString(HKEY hKey, LPCWSTR lpValueName, const void **this)
{
  __int16 v6; // ax
  int v7; // ebx
  int v9; // [rsp+30h] [rbp-40h] BYREF
  __int16 v10; // [rsp+34h] [rbp-3Ch]
  __int16 v11; // [rsp+36h] [rbp-3Ah]
  int v12; // [rsp+38h] [rbp-38h]
  DWORD cbData; // [rsp+B0h] [rbp+40h] BYREF
  DWORD Type; // [rsp+B8h] [rbp+48h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "SxRegReadString", 156, 2);
  Type = 1;
  v6 = 163;
  cbData = 0;
  if ( !this || (v10 = 163, v6 = 164, !hKey) )
  {
    v7 = -2147024809;
LABEL_16:
    v9 = v7;
    goto LABEL_17;
  }
  v9 = 0;
  v10 = 164;
  v7 = CBsString::ExtendBuffer(this, 0x20u);
  v9 = v7;
  v6 = 169;
  if ( v7 < 0 )
  {
LABEL_17:
    v11 = v6;
    goto LABEL_18;
  }
  v10 = 169;
  cbData = 2 * *((_DWORD *)this + 3) - 2;
  v7 = RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)*this, &cbData);
  CBsString::BoundUpdateLength((CBsString *)this, *((unsigned int *)this + 3));
  if ( !v7 )
  {
LABEL_8:
    v6 = 201;
    if ( Type - 1 <= 1 )
    {
      v10 = 201;
      v6 = 213;
      if ( (cbData & 1) == 0 )
      {
        v9 = 0;
        v10 = 213;
        CBsString::BoundUpdateLength((CBsString *)this, cbData >> 1);
        v7 = v9;
        goto LABEL_18;
      }
    }
    v7 = -2147418113;
    goto LABEL_16;
  }
  while ( v7 == 234 )
  {
    v9 = 0;
    v10 = 191;
    v7 = CBsString::ExtendBuffer(this, ((unsigned __int64)cbData + 3) >> 1);
    v9 = v7;
    v6 = 198;
    if ( v7 < 0 )
      goto LABEL_17;
    v10 = 198;
    cbData = 2 * *((_DWORD *)this + 3) - 2;
    v7 = RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)*this, &cbData);
    CBsString::BoundUpdateLength((CBsString *)this, *((unsigned int *)this + 3));
    if ( !v7 )
      goto LABEL_8;
  }
  if ( v7 > 0 )
    v7 = (unsigned __int16)v7 | 0x80070000;
  v9 = v7;
  v11 = 191;
  v12 = 1;
LABEL_18:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001e7e0  mov     [rsp-28h+arg_0], rbx
0x18001e7e5  push    rbp
0x18001e7e6  push    rsi
0x18001e7e7  push    rdi
0x18001e7e8  push    r13
0x18001e7ea  push    r14
0x18001e7ec  mov     rbp, rsp
0x18001e7ef  sub     rsp, 70h
0x18001e7f3  mov     rdi, r8
0x18001e7f6  mov     r14, rdx
0x18001e7f9  mov     rsi, rcx
0x18001e7fc  lea     rdx, aSxregreadstrin; "SxRegReadString"
0x18001e803  mov     r8d, 9Ch; unsigned __int16
0x18001e809  lea     rcx, [rbp+var_40]; this
0x18001e80d  mov     r9d, 2; unsigned __int16
0x18001e813  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001e818  mov     [rbp+Type], 1
0x18001e81f  mov     eax, 0A3h
0x18001e824  mov     [rbp+cbData], 0
0x18001e82b  test    rdi, rdi
0x18001e82e  jz      loc_18001E9A5
0x18001e834  mov     [rbp+var_3C], ax
0x18001e838  mov     eax, 0A4h
0x18001e83d  test    rsi, rsi
0x18001e840  jz      loc_18001E9A5
0x18001e846  mov     edx, 20h ; ' '; unsigned int
0x18001e84b  mov     [rbp+var_40], 0
0x18001e852  mov     rcx, rdi; this
0x18001e855  mov     [rbp+var_3C], ax
0x18001e859  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x18001e85e  mov     ebx, eax
0x18001e860  mov     [rbp+var_40], eax
0x18001e863  test    eax, eax
0x18001e865  mov     eax, 0A9h
0x18001e86a  js      loc_18001E9AD
0x18001e870  mov     [rbp+var_3C], ax
0x18001e874  lea     r9, [rbp+Type]; lpType
0x18001e878  mov     eax, [rdi+0Ch]
0x18001e87b  xor     r8d, r8d; lpReserved
0x18001e87e  mov     rdx, r14; lpValueName
0x18001e881  mov     rcx, rsi; hKey
0x18001e884  lea     eax, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18001e88b  mov     [rbp+cbData], eax
0x18001e88e  lea     rax, [rbp+cbData]
0x18001e892  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18001e897  mov     rax, [rdi]
0x18001e89a  mov     [rsp+70h+lpData], rax; lpData
0x18001e89f  call    cs:__imp_RegQueryValueExW
0x18001e8a5  mov     edx, [rdi+0Ch]; unsigned int
0x18001e8a8  mov     rcx, rdi; this
0x18001e8ab  mov     ebx, eax
0x18001e8ad  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x18001e8b2  test    ebx, ebx
0x18001e8b4  jz      loc_18001E946
0x18001e8ba  mov     r13d, 0BFh
0x18001e8c0  cmp     ebx, 0EAh
0x18001e8c6  jnz     loc_18001E95C
0x18001e8cc  mov     edx, [rbp+cbData]
0x18001e8cf  mov     rcx, rdi; this
0x18001e8d2  add     rdx, 3
0x18001e8d6  mov     [rbp+var_40], 0
0x18001e8dd  shr     rdx, 1; unsigned int
0x18001e8e0  mov     [rbp+var_3C], r13w
0x18001e8e5  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x18001e8ea  mov     ebx, eax
0x18001e8ec  mov     [rbp+var_40], eax
0x18001e8ef  test    eax, eax
0x18001e8f1  mov     eax, 0C6h
0x18001e8f6  js      loc_18001E9AD
0x18001e8fc  mov     [rbp+var_3C], ax
0x18001e900  lea     r9, [rbp+Type]; lpType
0x18001e904  mov     eax, [rdi+0Ch]
0x18001e907  xor     r8d, r8d; lpReserved
0x18001e90a  mov     rdx, r14; lpValueName
0x18001e90d  mov     rcx, rsi; hKey
0x18001e910  lea     eax, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18001e917  mov     [rbp+cbData], eax
0x18001e91a  lea     rax, [rbp+cbData]
0x18001e91e  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18001e923  mov     rax, [rdi]
0x18001e926  mov     [rsp+70h+lpData], rax; lpData
0x18001e92b  call    cs:__imp_RegQueryValueExW
0x18001e931  mov     edx, [rdi+0Ch]; unsigned int
0x18001e934  mov     rcx, rdi; this
0x18001e937  mov     ebx, eax
0x18001e939  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x18001e93e  test    ebx, ebx
0x18001e940  jnz     loc_18001E8C0
0x18001e946  mov     eax, [rbp+Type]
0x18001e949  dec     eax
0x18001e94b  cmp     eax, 1
0x18001e94e  mov     eax, 0C9h
0x18001e953  jbe     short loc_18001E97A
0x18001e955  mov     ebx, 8000FFFFh
0x18001e95a  jmp     short loc_18001E9AA
0x18001e95c  test    ebx, ebx
0x18001e95e  jle     short loc_18001E969
0x18001e960  movzx   ebx, bx
0x18001e963  or      ebx, 80070000h
0x18001e969  mov     [rbp+var_40], ebx
0x18001e96c  mov     [rbp+var_3A], r13w
0x18001e971  mov     [rbp+var_38], 1
0x18001e978  jmp     short loc_18001E9B1
0x18001e97a  mov     edx, [rbp+cbData]
0x18001e97d  mov     [rbp+var_3C], ax
0x18001e981  mov     eax, 0D5h
0x18001e986  test    dl, 1
0x18001e989  jnz     short loc_18001E955
0x18001e98b  shr     edx, 1; unsigned int
0x18001e98d  mov     rcx, rdi; this
0x18001e990  mov     [rbp+var_40], 0
0x18001e997  mov     [rbp+var_3C], ax
0x18001e99b  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x18001e9a0  mov     ebx, [rbp+var_40]
0x18001e9a3  jmp     short loc_18001E9B1
0x18001e9a5  mov     ebx, 80070057h
0x18001e9aa  mov     [rbp+var_40], ebx
0x18001e9ad  mov     [rbp+var_3A], ax
0x18001e9b1  lea     rcx, [rbp+var_40]; this
0x18001e9b5  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001e9ba  mov     eax, ebx
0x18001e9bc  mov     rbx, [rsp+70h+arg_0]
0x18001e9c4  add     rsp, 70h
0x18001e9c8  pop     r14
0x18001e9ca  pop     r13
0x18001e9cc  pop     rdi
0x18001e9cd  pop     rsi
0x18001e9ce  pop     rbp
0x18001e9cf  retn
```
