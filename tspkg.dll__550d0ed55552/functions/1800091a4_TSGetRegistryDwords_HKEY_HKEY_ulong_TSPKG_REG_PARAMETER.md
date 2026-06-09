# TSGetRegistryDwords(HKEY__ *,HKEY__ *,ulong,_TSPKG_REG_PARAMETER *)

- ea: `0x1800091a4`
- end: `0x180009311`
- name: `?TSGetRegistryDwords@@YAJPEAUHKEY__@@0KPEAU_TSPKG_REG_PARAMETER@@@Z`
- size: `365`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY, unsigned int, struct _TSPKG_REG_PARAMETER *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000a2bc`

## callees

- `0x1800091a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000920c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000920c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009279`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800092b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009279`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800092b5`

## pseudocode

```c
__int64 __fastcall TSGetRegistryDwords(unsigned __int64 hKey, HKEY a2, __int64 a3, struct _TSPKG_REG_PARAMETER *a4)
{
  unsigned __int64 v6; // rsi
  __int64 v7; // rbx
  __int64 v8; // r15
  HKEY v9; // r14
  LSTATUS v10; // eax
  int v11; // eax
  BYTE Data[4]; // [rsp+60h] [rbp-18h] BYREF
  DWORD Type; // [rsp+64h] [rbp-14h] BYREF
  DWORD v15[4]; // [rsp+68h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+D0h] [rbp+58h] BYREF

  v15[0] = -1;
  v6 = hKey;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  if ( !RegQueryInfoKeyW((HKEY)hKey, 0, 0, 0, 0, 0, 0, v15, 0, 0, 0, 0) )
    v6 &= -(__int64)(v15[0] != 0);
  v7 = 128;
  v8 = 4;
  do
  {
    --v8;
    Type = 0;
    v7 -= 32;
    *(_DWORD *)Data = 0;
    v9 = (HKEY)v6;
    cbData = 4;
    if ( *(_DWORD *)((char *)a4 + v7 + 24) && a2 )
    {
      v9 = a2;
LABEL_8:
      v10 = RegQueryValueExW(v9, *(LPCWSTR *)((char *)a4 + v7), 0, &Type, Data, &cbData);
      if ( v10 != 2 )
        goto LABEL_12;
      goto LABEL_9;
    }
    if ( v6 )
      goto LABEL_8;
LABEL_9:
    if ( v9 != a2 || (cbData = 4, !v6) )
    {
LABEL_18:
      v11 = *(_DWORD *)((char *)a4 + v7 + 16);
      goto LABEL_19;
    }
    v10 = RegQueryValueExW((HKEY)v6, *(LPCWSTR *)((char *)a4 + v7), 0, &Type, Data, &cbData);
LABEL_12:
    if ( v10 || Type != 4 || cbData != 4 )
      goto LABEL_18;
    if ( *(_DWORD *)((char *)a4 + v7 + 20) )
    {
      **(_DWORD **)((char *)a4 + v7 + 8) = *(_DWORD *)Data == 0;
      continue;
    }
    v11 = *(_DWORD *)Data;
LABEL_19:
    **(_DWORD **)((char *)a4 + v7 + 8) = v11;
  }
  while ( v8 );
  return 0;
}

```

## disassembly

```asm
0x1800091a4  mov     r11, rsp
0x1800091a7  mov     [r11+18h], r8d
0x1800091ab  push    rbp
0x1800091ac  push    rbx
0x1800091ad  push    rsi
0x1800091ae  push    rdi
0x1800091af  push    r12
0x1800091b1  push    r13
0x1800091b3  push    r14
0x1800091b5  push    r15
0x1800091b7  mov     rbp, rsp
0x1800091ba  sub     rsp, 78h
0x1800091be  xor     r13d, r13d
0x1800091c1  mov     [rbp+var_10], 0FFFFFFFFh
0x1800091c8  mov     [r11-60h], r13
0x1800091cc  lea     rax, [rbp+var_10]
0x1800091d0  mov     [r11-68h], r13
0x1800091d4  mov     rdi, r9
0x1800091d7  mov     [r11-70h], r13
0x1800091db  mov     r12, rdx
0x1800091de  mov     [r11-78h], r13
0x1800091e2  xor     r9d, r9d; lpReserved
0x1800091e5  mov     [r11-80h], rax
0x1800091e9  xor     r8d, r8d; lpcchClass
0x1800091ec  mov     [rsp+78h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x1800091f1  xor     edx, edx; lpClass
0x1800091f3  mov     [rsp+78h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x1800091f8  mov     rsi, rcx
0x1800091fb  mov     [rsp+78h+lpcSubKeys], r13; lpcSubKeys
0x180009200  mov     [rbp+Type], r13d
0x180009204  mov     dword ptr [rbp+Data], r13d
0x180009208  mov     [rbp+cbData], r13d
0x18000920c  call    cs:__imp_RegQueryInfoKeyW
0x180009212  test    eax, eax
0x180009214  jnz     short loc_180009221
0x180009216  mov     eax, [rbp+var_10]
0x180009219  neg     eax
0x18000921b  sbb     rcx, rcx
0x18000921e  and     rsi, rcx
0x180009221  mov     ebx, 80h
0x180009226  lea     r15d, [rbx-7Ch]
0x18000922a  dec     r15
0x18000922d  mov     [rbp+Type], r13d
0x180009231  lea     rbx, [rbx-20h]
0x180009235  mov     dword ptr [rbp+Data], r13d
0x180009239  mov     r14, rsi
0x18000923c  mov     [rbp+cbData], 4
0x180009243  cmp     [rbx+rdi+18h], r13d
0x180009248  jz      short loc_180009254
0x18000924a  test    r12, r12
0x18000924d  jz      short loc_180009254
0x18000924f  mov     r14, r12
0x180009252  jmp     short loc_180009259
0x180009254  test    rsi, rsi
0x180009257  jz      short loc_180009284
0x180009259  mov     rdx, [rbx+rdi]; lpValueName
0x18000925d  lea     rax, [rbp+cbData]
0x180009261  mov     [rsp+78h+lpcbMaxSubKeyLen], rax; lpcbData
0x180009266  lea     r9, [rbp+Type]; lpType
0x18000926a  lea     rax, [rbp+Data]
0x18000926e  xor     r8d, r8d; lpReserved
0x180009271  mov     rcx, r14; hKey
0x180009274  mov     [rsp+78h+lpcSubKeys], rax; lpData
0x180009279  call    cs:__imp_RegQueryValueExW
0x18000927f  cmp     eax, 2
0x180009282  jnz     short loc_1800092BB
0x180009284  cmp     r14, r12
0x180009287  jnz     short loc_1800092EA
0x180009289  mov     [rbp+cbData], 4
0x180009290  test    rsi, rsi
0x180009293  jz      short loc_1800092EA
0x180009295  mov     rdx, [rbx+rdi]; lpValueName
0x180009299  lea     rax, [rbp+cbData]
0x18000929d  mov     [rsp+78h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800092a2  lea     r9, [rbp+Type]; lpType
0x1800092a6  lea     rax, [rbp+Data]
0x1800092aa  xor     r8d, r8d; lpReserved
0x1800092ad  mov     rcx, rsi; hKey
0x1800092b0  mov     [rsp+78h+lpcSubKeys], rax; lpData
0x1800092b5  call    cs:__imp_RegQueryValueExW
0x1800092bb  test    eax, eax
0x1800092bd  jnz     short loc_1800092EA
0x1800092bf  cmp     [rbp+Type], 4
0x1800092c3  jnz     short loc_1800092EA
0x1800092c5  cmp     [rbp+cbData], 4
0x1800092c9  jnz     short loc_1800092EA
0x1800092cb  cmp     [rbx+rdi+14h], r13d
0x1800092d0  jz      short loc_1800092E5
0x1800092d2  cmp     dword ptr [rbp+Data], r13d
0x1800092d6  mov     ecx, r13d
0x1800092d9  mov     rax, [rbx+rdi+8]
0x1800092de  setz    cl
0x1800092e1  mov     [rax], ecx
0x1800092e3  jmp     short loc_1800092F5
0x1800092e5  mov     eax, dword ptr [rbp+Data]
0x1800092e8  jmp     short loc_1800092EE
0x1800092ea  mov     eax, [rbx+rdi+10h]
0x1800092ee  mov     rcx, [rbx+rdi+8]
0x1800092f3  mov     [rcx], eax
0x1800092f5  test    r15, r15
0x1800092f8  jnz     loc_18000922A
0x1800092fe  xor     eax, eax
0x180009300  add     rsp, 78h
0x180009304  pop     r15
0x180009306  pop     r14
0x180009308  pop     r13
0x18000930a  pop     r12
0x18000930c  pop     rdi
0x18000930d  pop     rsi
0x18000930e  pop     rbx
0x18000930f  pop     rbp
0x180009310  retn
```
