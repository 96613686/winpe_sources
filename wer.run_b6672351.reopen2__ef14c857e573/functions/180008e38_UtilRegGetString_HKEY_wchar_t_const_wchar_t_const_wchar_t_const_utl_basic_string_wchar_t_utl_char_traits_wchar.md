# UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)

- ea: `0x180008e38`
- end: `0x18000906b`
- name: `?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z`
- size: `563`
- prototype: `__int64 __usercall@<rax>(HKEY hkey@<rcx>, LPCWSTR lpSubKey@<rdx>, LPCWSTR lpValue@<r8>, __int64, char, char)`
- caller_count: `15`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a3ac`
- `0x180013838`
- `0x18001c38c`
- `0x180022e44`
- `0x180032278`
- `0x180037164`
- `0x1800394d4`
- `0x18004083c`
- `0x180045758`
- `0x1800494a8`
- `0x18004cd60`
- `0x18009407c`
- `0x1800952e4`
- `0x18009cda0`
- `0x1800aa540`

## callees

- `0x180008e38`
- `0x18000add4`
- `0x18000ae48`
- `0x18000cf50`
- `0x18000da00`
- `0x18000db80`
- `0x18001cb20`
- `0x1800201f0`
- `0x180025560`
- `0x1800459c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000902e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000902e`
- `ntdll!wcsnlen` at `0x180008fcd`
- `ntdll!wcsnlen` at `0x180008fcd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008f50`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008fad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008f50`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008fad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009043`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009043`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008ee8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008ee8`

## pseudocode

```c
__int64 __fastcall UtilRegGetString(
        HKEY hkey,
        LPCWSTR lpSubKey,
        LPCWSTR lpValue,
        void *a4,
        __int64 a5,
        char a6,
        unsigned __int8 a7)
{
  __int64 v11; // rsi
  unsigned int v13; // ebx
  int v14; // ebx
  HKEY *phkResult; // rax
  LSTATUS ValueW; // eax
  bool v17; // cc
  size_t v18; // rax
  _WORD *v19; // rcx
  HKEY hKey; // [rsp+40h] [rbp-30h] BYREF
  PVOID lpMem[2]; // [rsp+48h] [rbp-28h] BYREF
  char v22; // [rsp+58h] [rbp-18h] BYREF
  DWORD pcbData; // [rsp+A0h] [rbp+30h] BYREF

  pcbData = 0;
  hKey = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpMem);
  v11 = a5;
  if ( !a5 )
  {
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpMem);
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    return 2147942487LL;
  }
  if ( a4
    && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(lpMem, a4) )
  {
    goto LABEL_5;
  }
  v14 = a7;
  if ( lpSubKey || a7 )
  {
    phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    ValueW = RegOpenKeyExW(hkey, lpSubKey, 0, (v14 << 8) | 1, phkResult);
    v13 = ValueW;
    if ( ValueW )
      goto LABEL_9;
    hkey = hKey;
  }
  pcbData = 0;
  ValueW = RegGetValueW(hkey, 0, lpValue, 2u, 0, 0, &pcbData);
  v13 = ValueW;
  if ( ValueW )
  {
LABEL_9:
    if ( !a4 )
    {
      v17 = ValueW <= 0;
      goto LABEL_11;
    }
    goto LABEL_18;
  }
  lpMem[1] = lpMem[0];
  *(_WORD *)lpMem[0] = 0;
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                          lpMem,
                          ((unsigned __int64)pcbData >> 1) + 1) )
  {
    ValueW = RegGetValueW(hkey, 0, lpValue, 2u, 0, lpMem[0], &pcbData);
    v13 = ValueW;
    v17 = ValueW <= 0;
    if ( ValueW )
    {
LABEL_11:
      if ( !v17 )
        v13 = (unsigned __int16)ValueW | 0x80070000;
      goto LABEL_22;
    }
    v18 = wcsnlen((const wchar_t *)lpMem[0], (unsigned __int64)pcbData >> 1);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::erase(lpMem, v18);
LABEL_18:
    v13 = 0;
    if ( a6 )
      v13 = UtilExpandEnvironmentStrings((LPCWSTR)lpMem[0]);
    else
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(v11, lpMem);
    if ( !v13 )
      goto LABEL_23;
    goto LABEL_22;
  }
LABEL_5:
  v13 = -2147024882;
LABEL_22:
  v19 = *(_WORD **)v11;
  *(_QWORD *)(v11 + 8) = *(_QWORD *)v11;
  *v19 = 0;
LABEL_23:
  if ( lpMem[0] != &v22 )
    HeapFree(g_hWerheap, 0, lpMem[0]);
  if ( hKey )
    RegCloseKey(hKey);
  return v13;
}

```

## disassembly

```asm
0x180008e38  mov     [rsp-28h+arg_8], rbx
0x180008e3d  mov     [rsp-28h+arg_10], rsi
0x180008e42  push    rbp
0x180008e43  push    rdi
0x180008e44  push    r12
0x180008e46  push    r14
0x180008e48  push    r15
0x180008e4a  mov     rbp, rsp
0x180008e4d  sub     rsp, 70h
0x180008e51  mov     r14, rcx
0x180008e54  mov     [rbp+arg_0], 0
0x180008e5b  lea     rcx, [rbp+lpMem]; void *
0x180008e5f  mov     [rbp+hKey], 0
0x180008e67  mov     rdi, r9
0x180008e6a  mov     r12, r8
0x180008e6d  mov     r15, rdx
0x180008e70  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180008e75  mov     rsi, [rbp+arg_20]
0x180008e79  test    rsi, rsi
0x180008e7c  jnz     short loc_180008E9A
0x180008e7e  lea     rcx, [rbp+lpMem]; void *
0x180008e82  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180008e87  lea     rcx, [rbp+hKey]
0x180008e8b  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180008e90  mov     eax, 80070057h
0x180008e95  jmp     loc_180009051
0x180008e9a  test    rdi, rdi
0x180008e9d  jz      short loc_180008EB9
0x180008e9f  mov     rdx, rdi
0x180008ea2  lea     rcx, [rbp+lpMem]
0x180008ea6  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180008eab  test    al, al
0x180008ead  jnz     short loc_180008EB9
0x180008eaf  mov     ebx, 8007000Eh
0x180008eb4  jmp     loc_18000900C
0x180008eb9  movzx   ebx, [rbp+arg_30]
0x180008ebd  test    r15, r15
0x180008ec0  jnz     short loc_180008EC6
0x180008ec2  test    bl, bl
0x180008ec4  jz      short loc_180008F1D
0x180008ec6  lea     rcx, [rbp+hKey]
0x180008eca  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180008ecf  mov     r9d, ebx
0x180008ed2  mov     [rsp+70h+phkResult], rax; phkResult
0x180008ed7  shl     r9d, 8
0x180008edb  xor     r8d, r8d; ulOptions
0x180008ede  or      r9d, 1; samDesired
0x180008ee2  mov     rdx, r15; lpSubKey
0x180008ee5  mov     rcx, r14; hKey
0x180008ee8  call    cs:__imp_RegOpenKeyExW
0x180008eef  nop     dword ptr [rax+rax+00h]
0x180008ef4  mov     ebx, eax
0x180008ef6  test    eax, eax
0x180008ef8  jz      short loc_180008F19
0x180008efa  test    rdi, rdi
0x180008efd  jnz     loc_180008FE5
0x180008f03  test    eax, eax
0x180008f05  jle     loc_18000900C
0x180008f0b  movzx   ebx, ax
0x180008f0e  or      ebx, 80070000h
0x180008f14  jmp     loc_18000900C
0x180008f19  mov     r14, [rbp+hKey]
0x180008f1d  lea     rax, [rbp+arg_0]
0x180008f21  mov     [rbp+arg_0], 0
0x180008f28  mov     [rsp+70h+pcbData], rax; pcbData
0x180008f2d  mov     r15d, 2
0x180008f33  mov     [rsp+70h+pvData], 0; pvData
0x180008f3c  mov     r9d, r15d; dwFlags
0x180008f3f  mov     r8, r12; lpValue
0x180008f42  mov     [rsp+70h+phkResult], 0; pdwType
0x180008f4b  xor     edx, edx; lpSubKey
0x180008f4d  mov     rcx, r14; hkey
0x180008f50  call    cs:__imp_RegGetValueW
0x180008f57  nop     dword ptr [rax+rax+00h]
0x180008f5c  mov     ebx, eax
0x180008f5e  test    eax, eax
0x180008f60  jnz     short loc_180008EFA
0x180008f62  mov     rcx, [rbp+lpMem]
0x180008f66  mov     [rbp+var_20], rcx
0x180008f6a  mov     [rcx], ax
0x180008f6d  lea     rcx, [rbp+lpMem]
0x180008f71  mov     edx, [rbp+arg_0]
0x180008f74  shr     rdx, 1
0x180008f77  inc     rdx
0x180008f7a  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x180008f7f  test    al, al
0x180008f81  jz      loc_180008EAF
0x180008f87  lea     rax, [rbp+arg_0]
0x180008f8b  mov     r9d, r15d; dwFlags
0x180008f8e  mov     [rsp+70h+pcbData], rax; pcbData
0x180008f93  mov     r8, r12; lpValue
0x180008f96  mov     rax, [rbp+lpMem]
0x180008f9a  xor     edx, edx; lpSubKey
0x180008f9c  mov     [rsp+70h+pvData], rax; pvData
0x180008fa1  mov     rcx, r14; hkey
0x180008fa4  mov     [rsp+70h+phkResult], 0; pdwType
0x180008fad  call    cs:__imp_RegGetValueW
0x180008fb4  nop     dword ptr [rax+rax+00h]
0x180008fb9  mov     ebx, eax
0x180008fbb  test    eax, eax
0x180008fbd  jnz     loc_180008F05
0x180008fc3  mov     edx, [rbp+arg_0]
0x180008fc6  mov     rcx, [rbp+lpMem]; Source
0x180008fca  shr     rdx, 1; MaxCount
0x180008fcd  call    cs:__imp_wcsnlen
0x180008fd4  nop     dword ptr [rax+rax+00h]
0x180008fd9  mov     rdx, rax
0x180008fdc  lea     rcx, [rbp+lpMem]
0x180008fe0  call    ?erase@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV12@_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::erase(unsigned __int64)
0x180008fe5  xor     ebx, ebx
0x180008fe7  cmp     [rbp+arg_28], bl
0x180008fea  jz      short loc_180008FFC
0x180008fec  mov     rcx, [rbp+lpMem]; lpSrc
0x180008ff0  mov     rdx, rsi
0x180008ff3  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180008ff8  mov     ebx, eax
0x180008ffa  jmp     short loc_180009008
0x180008ffc  lea     rdx, [rbp+lpMem]
0x180009000  mov     rcx, rsi
0x180009003  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x180009008  test    ebx, ebx
0x18000900a  jz      short loc_180009018
0x18000900c  mov     rcx, [rsi]
0x18000900f  xor     eax, eax
0x180009011  mov     [rsi+8], rcx
0x180009015  mov     [rcx], ax
0x180009018  mov     r8, [rbp+lpMem]; lpMem
0x18000901c  lea     rax, [rbp+var_18]
0x180009020  cmp     r8, rax
0x180009023  jz      short loc_18000903A
0x180009025  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18000902c  xor     edx, edx; dwFlags
0x18000902e  call    cs:__imp_HeapFree
0x180009035  nop     dword ptr [rax+rax+00h]
0x18000903a  mov     rcx, [rbp+hKey]; hKey
0x18000903e  test    rcx, rcx
0x180009041  jz      short loc_18000904F
0x180009043  call    cs:__imp_RegCloseKey
0x18000904a  nop     dword ptr [rax+rax+00h]
0x18000904f  mov     eax, ebx
0x180009051  lea     r11, [rsp+70h+var_s0]
0x180009056  mov     rbx, [r11+38h]
0x18000905a  mov     rsi, [r11+40h]
0x18000905e  mov     rsp, r11
0x180009061  pop     r15
0x180009063  pop     r14
0x180009065  pop     r12
0x180009067  pop     rdi
0x180009068  pop     rbp
0x180009069  retn
```
