# CreateRoleSpecificRegValues(RoleType,int,int)

- ea: `0x1800498b8`
- end: `0x180049b48`
- name: `?CreateRoleSpecificRegValues@@YAJW4RoleType@@HH@Z`
- size: `656`
- prototype: `__int64 __fastcall(int, int, int)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004a5e4`
- `0x18004ade0`
- `0x18004afd0`
- `0x18004b2f0`
- `0x18004b4b0`

## callees

- `0x18003bafc`
- `0x1800498b8`
- `0x18004a474`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049b12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049b12`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049932`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049a53`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049932`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049a53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800499b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049af2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800499b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049af2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049997`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049ad3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049997`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049ad3`

## pseudocode

```c
__int64 __fastcall CreateRoleSpecificRegValues(int a1, int a2, int a3)
{
  __int64 v3; // r15
  int v4; // r12d
  unsigned int v6; // ebx
  unsigned int v7; // esi
  wchar_t **v8; // r13
  wchar_t **v9; // rdi
  const WCHAR *v10; // rdx
  int v11; // eax
  bool v12; // sf
  wchar_t *v13; // rax
  int v14; // eax
  LSTATUS v15; // eax
  signed int v16; // edi
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // esi
  wchar_t **i; // r12
  wchar_t **v21; // rdi
  const BYTE *v22; // r14
  int v23; // eax
  bool v24; // sf
  wchar_t *v25; // rax
  int v26; // eax
  __int64 v27; // rax
  LSTATUS v28; // eax
  signed int v29; // edi
  HLOCAL hMem[2]; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+80h] [rbp+40h] BYREF
  int v33; // [rsp+88h] [rbp+48h]
  HKEY hKey; // [rsp+98h] [rbp+58h] BYREF

  v33 = a2;
  v3 = 4LL * a1;
  v4 = a2;
  v6 = 0;
  v7 = 0;
  v8 = (&off_18006E970)[v3];
  if ( LODWORD((&off_18006E970)[v3 + 1]) )
  {
    do
    {
      hKey = 0;
      v9 = &v8[4 * v7];
      v10 = *v9;
      Data = *((_DWORD *)v9 + 4);
      v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 2u, &hKey);
      v12 = v11 < 0;
      if ( v11 > 0 )
      {
        v11 = (unsigned __int16)v11 | 0x80070000;
        v12 = v11 < 0;
      }
      if ( v12 )
      {
        if ( v6 )
          v11 = v6;
        v6 = v11;
      }
      else
      {
        v13 = v9[3];
        if ( v13 )
        {
          v14 = ((__int64 (__fastcall *)(int *, wchar_t **))v13)(&Data, v9);
          if ( v14 < 0 && !v6 )
            v6 = v14;
        }
        v15 = RegSetValueExW(hKey, v9[1], 0, 4u, (const BYTE *)&Data, 4u);
        v16 = v15;
        if ( v15 > 0 )
          v16 = (unsigned __int16)v15 | 0x80070000;
        RegCloseKey(hKey);
        if ( v16 < 0 && !v6 )
          v6 = v16;
      }
      ++v7;
    }
    while ( v7 < LODWORD((&off_18006E970)[v3 + 1]) );
    v4 = v33;
  }
  if ( a3 )
  {
    v17 = OverrideServerSpecificDwordValues();
    if ( !v6 )
      v6 = v17;
    v18 = OverrideServerSpecificSZValues();
    if ( !v6 )
      v6 = v18;
  }
  if ( !v4 )
  {
    v19 = 0;
    for ( i = (&off_18006E970)[v3 + 2]; v19 < LODWORD((&off_18006E970)[v3 + 3]); ++v19 )
    {
      hKey = 0;
      hMem[0] = 0;
      v21 = &i[4 * v19];
      v22 = (const BYTE *)v21[2];
      v23 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, *v21, 0, 2u, &hKey);
      v24 = v23 < 0;
      if ( v23 > 0 )
      {
        v23 = (unsigned __int16)v23 | 0x80070000;
        v24 = v23 < 0;
      }
      if ( v24 )
      {
        if ( v6 )
          v23 = v6;
        v6 = v23;
      }
      else
      {
        v25 = v21[3];
        if ( v25 )
        {
          v26 = ((__int64 (__fastcall *)(HLOCAL *, wchar_t **))v25)(hMem, v21);
          if ( v26 >= 0 )
          {
            v22 = (const BYTE *)hMem[0];
          }
          else if ( !v6 )
          {
            v6 = v26;
          }
        }
        v27 = -1;
        do
          ++v27;
        while ( *(_WORD *)&v22[2 * v27] );
        v28 = RegSetValueExW(hKey, v21[1], 0, 1u, v22, 2 * v27 + 2);
        v29 = v28;
        if ( v28 > 0 )
          v29 = (unsigned __int16)v28 | 0x80070000;
        RegCloseKey(hKey);
        if ( v29 < 0 && !v6 )
          v6 = v29;
      }
      if ( hMem[0] )
        LocalFree(hMem[0]);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800498b8  mov     [rsp-38h+arg_10], rbx
0x1800498bd  mov     [rsp-38h+arg_8], edx
0x1800498c1  push    rbp
0x1800498c2  push    rsi
0x1800498c3  push    rdi
0x1800498c4  push    r12
0x1800498c6  push    r13
0x1800498c8  push    r14
0x1800498ca  push    r15
0x1800498cc  mov     rbp, rsp
0x1800498cf  sub     rsp, 40h
0x1800498d3  lea     rdi, off_18006E970
0x1800498da  movsxd  r15, ecx
0x1800498dd  shl     r15, 5
0x1800498e1  mov     r12d, edx
0x1800498e4  xor     edx, edx
0x1800498e6  mov     r14d, r8d
0x1800498e9  mov     ebx, edx
0x1800498eb  mov     esi, edx
0x1800498ed  mov     r13, [r15+rdi]
0x1800498f1  cmp     [r15+rdi+8], edx
0x1800498f6  jbe     loc_1800499E5
0x1800498fc  lea     r12, off_18006E970
0x180049903  mov     [rbp+hKey], rdx
0x180049907  mov     r9d, 2; samDesired
0x18004990d  mov     edi, esi
0x18004990f  xor     r8d, r8d; ulOptions
0x180049912  shl     rdi, 5
0x180049916  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004991d  add     rdi, r13
0x180049920  mov     eax, [rdi+10h]
0x180049923  mov     rdx, [rdi]; lpSubKey
0x180049926  mov     [rbp+Data], eax
0x180049929  lea     rax, [rbp+hKey]
0x18004992d  mov     [rsp+40h+phkResult], rax; phkResult
0x180049932  call    cs:__imp_RegOpenKeyExW
0x180049939  nop     dword ptr [rax+rax+00h]
0x18004993e  xor     edx, edx
0x180049940  test    eax, eax
0x180049942  jle     short loc_18004994E
0x180049944  movzx   eax, ax
0x180049947  or      eax, 80070000h
0x18004994c  test    eax, eax
0x18004994e  jns     short loc_180049959
0x180049950  test    ebx, ebx
0x180049952  cmovnz  eax, ebx
0x180049955  mov     ebx, eax
0x180049957  jmp     short loc_1800499CD
0x180049959  mov     rax, [rdi+18h]
0x18004995d  test    rax, rax
0x180049960  jz      short loc_180049977
0x180049962  mov     rdx, rdi
0x180049965  lea     rcx, [rbp+Data]
0x180049969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004996e  test    eax, eax
0x180049970  jns     short loc_180049977
0x180049972  test    ebx, ebx
0x180049974  cmovz   ebx, eax
0x180049977  mov     rdx, [rdi+8]; lpValueName
0x18004997b  lea     rax, [rbp+Data]
0x18004997f  mov     ecx, 4
0x180049984  xor     r8d, r8d; Reserved
0x180049987  mov     [rsp+40h+cbData], ecx; cbData
0x18004998b  mov     r9d, ecx; dwType
0x18004998e  mov     rcx, [rbp+hKey]; hKey
0x180049992  mov     [rsp+40h+phkResult], rax; lpData
0x180049997  call    cs:__imp_RegSetValueExW
0x18004999e  nop     dword ptr [rax+rax+00h]
0x1800499a3  mov     edi, eax
0x1800499a5  test    eax, eax
0x1800499a7  jle     short loc_1800499B2
0x1800499a9  movzx   edi, ax
0x1800499ac  or      edi, 80070000h
0x1800499b2  mov     rcx, [rbp+hKey]; hKey
0x1800499b6  call    cs:__imp_RegCloseKey
0x1800499bd  nop     dword ptr [rax+rax+00h]
0x1800499c2  xor     edx, edx
0x1800499c4  test    edi, edi
0x1800499c6  jns     short loc_1800499CD
0x1800499c8  test    ebx, ebx
0x1800499ca  cmovz   ebx, edi
0x1800499cd  inc     esi
0x1800499cf  cmp     esi, [r15+r12+8]
0x1800499d4  jb      loc_180049903
0x1800499da  mov     r12d, [rbp+arg_8]
0x1800499de  lea     rdi, off_18006E970
0x1800499e5  test    r14d, r14d
0x1800499e8  jz      short loc_180049A00
0x1800499ea  call    ?OverrideServerSpecificDwordValues@@YAJXZ; OverrideServerSpecificDwordValues(void)
0x1800499ef  test    ebx, ebx
0x1800499f1  cmovz   ebx, eax
0x1800499f4  call    ?OverrideServerSpecificSZValues@@YAJXZ; OverrideServerSpecificSZValues(void)
0x1800499f9  xor     edx, edx
0x1800499fb  test    ebx, ebx
0x1800499fd  cmovz   ebx, eax
0x180049a00  test    r12d, r12d
0x180049a03  jnz     loc_180049B2D
0x180049a09  mov     esi, edx
0x180049a0b  mov     r12, [r15+rdi+10h]
0x180049a10  cmp     [r15+rdi+18h], edx
0x180049a15  jbe     loc_180049B2D
0x180049a1b  lea     r13, off_18006E970
0x180049a22  mov     [rbp+hKey], rdx
0x180049a26  lea     rax, [rbp+hKey]
0x180049a2a  mov     [rbp+hMem], rdx
0x180049a2e  mov     r9d, 2; samDesired
0x180049a34  mov     edi, esi
0x180049a36  xor     r8d, r8d; ulOptions
0x180049a39  shl     rdi, 5
0x180049a3d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180049a44  add     rdi, r12
0x180049a47  mov     [rsp+40h+phkResult], rax; phkResult
0x180049a4c  mov     rdx, [rdi]; lpSubKey
0x180049a4f  mov     r14, [rdi+10h]
0x180049a53  call    cs:__imp_RegOpenKeyExW
0x180049a5a  nop     dword ptr [rax+rax+00h]
0x180049a5f  xor     edx, edx
0x180049a61  test    eax, eax
0x180049a63  jle     short loc_180049A6F
0x180049a65  movzx   eax, ax
0x180049a68  or      eax, 80070000h
0x180049a6d  test    eax, eax
0x180049a6f  jns     short loc_180049A7D
0x180049a71  test    ebx, ebx
0x180049a73  cmovnz  eax, ebx
0x180049a76  mov     ebx, eax
0x180049a78  jmp     loc_180049B09
0x180049a7d  mov     rax, [rdi+18h]
0x180049a81  test    rax, rax
0x180049a84  jz      short loc_180049AA4
0x180049a86  mov     rdx, rdi
0x180049a89  lea     rcx, [rbp+hMem]
0x180049a8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a92  xor     edx, edx
0x180049a94  test    eax, eax
0x180049a96  jns     short loc_180049AA0
0x180049a98  test    ebx, ebx
0x180049a9a  jnz     short loc_180049AA4
0x180049a9c  mov     ebx, eax
0x180049a9e  jmp     short loc_180049AA4
0x180049aa0  mov     r14, [rbp+hMem]
0x180049aa4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180049aa8  inc     rax
0x180049aab  cmp     [r14+rax*2], dx
0x180049ab0  jnz     short loc_180049AA8
0x180049ab2  mov     rdx, [rdi+8]; lpValueName
0x180049ab6  lea     eax, ds:2[rax*2]
0x180049abd  mov     rcx, [rbp+hKey]; hKey
0x180049ac1  mov     r9d, 1; dwType
0x180049ac7  mov     [rsp+40h+cbData], eax; cbData
0x180049acb  xor     r8d, r8d; Reserved
0x180049ace  mov     [rsp+40h+phkResult], r14; lpData
0x180049ad3  call    cs:__imp_RegSetValueExW
0x180049ada  nop     dword ptr [rax+rax+00h]
0x180049adf  mov     edi, eax
0x180049ae1  test    eax, eax
0x180049ae3  jle     short loc_180049AEE
0x180049ae5  movzx   edi, ax
0x180049ae8  or      edi, 80070000h
0x180049aee  mov     rcx, [rbp+hKey]; hKey
0x180049af2  call    cs:__imp_RegCloseKey
0x180049af9  nop     dword ptr [rax+rax+00h]
0x180049afe  xor     edx, edx
0x180049b00  test    edi, edi
0x180049b02  jns     short loc_180049B09
0x180049b04  test    ebx, ebx
0x180049b06  cmovz   ebx, edi
0x180049b09  mov     rcx, [rbp+hMem]; hMem
0x180049b0d  test    rcx, rcx
0x180049b10  jz      short loc_180049B20
0x180049b12  call    cs:__imp_LocalFree
0x180049b19  nop     dword ptr [rax+rax+00h]
0x180049b1e  xor     edx, edx
0x180049b20  inc     esi
0x180049b22  cmp     esi, [r15+r13+18h]
0x180049b27  jb      loc_180049A22
0x180049b2d  mov     eax, ebx
0x180049b2f  mov     rbx, [rsp+40h+arg_10]
0x180049b37  add     rsp, 40h
0x180049b3b  pop     r15
0x180049b3d  pop     r14
0x180049b3f  pop     r13
0x180049b41  pop     r12
0x180049b43  pop     rdi
0x180049b44  pop     rsi
0x180049b45  pop     rbp
0x180049b46  retn
```
