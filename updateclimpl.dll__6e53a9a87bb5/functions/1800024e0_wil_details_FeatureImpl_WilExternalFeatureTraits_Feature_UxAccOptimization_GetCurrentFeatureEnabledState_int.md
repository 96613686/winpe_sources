# wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800024e0`
- end: `0x1800026f1`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilExternalFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `529`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800026f8`

## callees

- `0x1800024e0`
- `0x1800148e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002686`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002695`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800026a8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002686`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002695`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800026a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800025f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002643`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002658`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800025f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002643`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002658`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800025c9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000261f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800025c9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000261f`

## string_xrefs

- `0x1800025c2`: `kernelbase.dll`
- `0x180002618`: `windowsudk.shellcommon.dll`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilExternalFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v3)(__int64, __int64); // rax
  int v4; // eax
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // eax
  int v8; // edx
  unsigned int v9; // eax
  bool v10; // si
  int v11; // r12d
  char v12; // r13
  HMODULE Library; // rax
  HMODULE v14; // rdi
  bool v15; // bl
  FARPROC v16; // rax
  bool v17; // zf
  HMODULE v18; // rax
  HMODULE v19; // rbx
  bool v20; // r15
  FARPROC ProcAddress; // rax
  bool v23; // [rsp+20h] [rbp-58h]

  v3 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( !g_wil_details_internalGetFeatureEnabledState )
  {
    v3 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState;
    if ( !g_wil_details_apiGetFeatureEnabledState )
    {
      *a2 = 0;
      v6 = 0;
      goto LABEL_8;
    }
  }
  v4 = v3(48433719, 64);
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( (v4 & 0xFFFFFF3F) == 0 )
  {
LABEL_8:
    v7 = 0;
    v8 = v6;
    goto LABEL_9;
  }
  v7 = 0;
  if ( v5 == 2 )
    v7 = 64;
  v8 = v6 | v7;
LABEL_9:
  *(_DWORD *)a2 = v8;
  v9 = v6 | v7;
  v10 = 0;
  v11 = 1;
  if ( (v9 & 0x400) != 0 && v9 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    if ( (v9 & 0x40) == 0 )
      goto LABEL_30;
  }
  Library = LoadLibraryExA("kernelbase.dll", 0, 0x800u);
  v14 = Library;
  v15 = Library != 0;
  v23 = Library != 0;
  if ( !Library || (v16 = GetProcAddress(Library, "AreExternalFeatureDependenciesEnabled")) == 0 )
  {
    v18 = LoadLibraryExA("windowsudk.shellcommon.dll", 0, 0x800u);
    v19 = v18;
    v20 = v18 != 0;
    if ( v18 )
    {
      ProcAddress = GetProcAddress(v18, "AreExternalFeatureDependenciesEnabled");
      if ( ProcAddress || (ProcAddress = GetProcAddress(v19, "GetExternalFeatureState")) != 0 )
      {
        v10 = ((unsigned int (__fastcall *)(__int64))ProcAddress)(48433719) == 2;
        if ( v20 )
          FreeLibrary(v19);
        goto LABEL_24;
      }
      if ( v20 )
        FreeLibrary(v19);
    }
    v10 = 0;
LABEL_24:
    v17 = !v23;
    goto LABEL_25;
  }
  v10 = ((unsigned int (__fastcall *)(__int64))v16)(48433719) == 2;
  v17 = !v15;
LABEL_25:
  if ( !v17 )
    FreeLibrary(v14);
  if ( v12 && !v10 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_30:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v10 )
    v11 = 0;
  *(_DWORD *)a2 = v11 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x1800024e0  mov     [rsp+arg_0], rbx
0x1800024e5  push    rbp
0x1800024e6  push    rsi
0x1800024e7  push    rdi
0x1800024e8  push    r12
0x1800024ea  push    r13
0x1800024ec  push    r14
0x1800024ee  push    r15
0x1800024f0  sub     rsp, 40h
0x1800024f4  mov     r14, rdx
0x1800024f7  mov     ecx, 2E30A37h
0x1800024fc  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180002503  test    rax, rax
0x180002506  jnz     short loc_180002514
0x180002508  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000250f  test    rax, rax
0x180002512  jz      short loc_180002562
0x180002514  mov     ebp, 40h ; '@'
0x180002519  mov     edx, ebp
0x18000251b  call    _guard_dispatch_icall
0x180002520  mov     edx, eax
0x180002522  mov     qword ptr [r14], 0
0x180002529  mov     r8d, eax
0x18000252c  and     r8d, 0FFFFFF3Fh
0x180002533  mov     ecx, r8d
0x180002536  and     ecx, 3
0x180002539  shl     ecx, 2
0x18000253c  and     eax, ebp
0x18000253e  or      ecx, eax
0x180002540  shl     ecx, 2
0x180002543  and     edx, 80h
0x180002549  or      ecx, edx
0x18000254b  shl     ecx, 3
0x18000254e  test    r8d, r8d
0x180002551  jz      short loc_180002589
0x180002553  xor     eax, eax
0x180002555  cmp     r8d, 2
0x180002559  cmovz   eax, ebp
0x18000255c  mov     edx, eax
0x18000255e  or      edx, ecx
0x180002560  jmp     short loc_18000258D
0x180002562  mov     qword ptr [rdx], 0
0x180002569  xor     ecx, ecx
0x18000256b  and     ecx, 3
0x18000256e  shl     ecx, 2
0x180002571  xor     eax, eax
0x180002573  lea     ebp, [rax+40h]
0x180002576  and     eax, ebp
0x180002578  or      ecx, eax
0x18000257a  shl     ecx, 2
0x18000257d  xor     eax, eax
0x18000257f  and     eax, 80h
0x180002584  or      ecx, eax
0x180002586  shl     ecx, 3
0x180002589  xor     eax, eax
0x18000258b  mov     edx, ecx
0x18000258d  mov     [r14], edx
0x180002590  or      eax, ecx
0x180002592  xor     sil, sil
0x180002595  mov     r12d, 1
0x18000259b  mov     r15d, 800h
0x1800025a1  bt      eax, 0Ah
0x1800025a5  jnb     short loc_1800025B1
0x1800025a7  cmp     eax, r15d
0x1800025aa  jb      short loc_1800025B1
0x1800025ac  mov     r13b, r12b
0x1800025af  jmp     short loc_1800025BD
0x1800025b1  xor     r13b, r13b
0x1800025b4  test    bpl, al
0x1800025b7  jz      loc_1800026BD
0x1800025bd  mov     r8d, r15d; dwFlags
0x1800025c0  xor     edx, edx; hFile
0x1800025c2  lea     rcx, LibFileName; "kernelbase.dll"
0x1800025c9  call    cs:__imp_LoadLibraryExA
0x1800025cf  mov     rdi, rax
0x1800025d2  mov     [rsp+78h+var_50], rax
0x1800025d7  test    rax, rax
0x1800025da  setnz   bl
0x1800025dd  mov     [rsp+78h+var_58], bl
0x1800025e1  test    rax, rax
0x1800025e4  jz      short loc_180002613
0x1800025e6  lea     rdx, ProcName; "AreExternalFeatureDependenciesEnabled"
0x1800025ed  mov     rcx, rax; hModule
0x1800025f0  call    cs:__imp_GetProcAddress
0x1800025f6  test    rax, rax
0x1800025f9  jz      short loc_180002613
0x1800025fb  mov     ecx, 2E30A37h
0x180002600  call    _guard_dispatch_icall
0x180002605  cmp     eax, 2
0x180002608  setz    sil
0x18000260c  test    bl, bl
0x18000260e  jmp     loc_1800026A3
0x180002613  mov     r8d, r15d; dwFlags
0x180002616  xor     edx, edx; hFile
0x180002618  lea     rcx, aWindowsudkShel; "windowsudk.shellcommon.dll"
0x18000261f  call    cs:__imp_LoadLibraryExA
0x180002625  mov     rbx, rax
0x180002628  mov     [rsp+78h+var_48], rax
0x18000262d  test    rax, rax
0x180002630  setnz   r15b
0x180002634  test    rax, rax
0x180002637  jz      short loc_18000268E
0x180002639  lea     rdx, ProcName; "AreExternalFeatureDependenciesEnabled"
0x180002640  mov     rcx, rax; hModule
0x180002643  call    cs:__imp_GetProcAddress
0x180002649  test    rax, rax
0x18000264c  jnz     short loc_18000266D
0x18000264e  lea     rdx, aGetexternalfea; "GetExternalFeatureState"
0x180002655  mov     rcx, rbx; hModule
0x180002658  call    cs:__imp_GetProcAddress
0x18000265e  test    rax, rax
0x180002661  jnz     short loc_18000266D
0x180002663  test    r15b, r15b
0x180002666  jz      short loc_18000269B
0x180002668  mov     rcx, rbx
0x18000266b  jmp     short loc_180002695
0x18000266d  mov     ecx, 2E30A37h
0x180002672  call    _guard_dispatch_icall
0x180002677  cmp     eax, 2
0x18000267a  setz    sil
0x18000267e  test    r15b, r15b
0x180002681  jz      short loc_18000269E
0x180002683  mov     rcx, rbx; hLibModule
0x180002686  call    cs:__imp_FreeLibrary
0x18000268c  jmp     short loc_18000269E
0x18000268e  test    r15b, r15b
0x180002691  jz      short loc_18000269B
0x180002693  xor     ecx, ecx; hLibModule
0x180002695  call    cs:__imp_FreeLibrary
0x18000269b  xor     sil, sil
0x18000269e  cmp     [rsp+78h+var_58], 0
0x1800026a3  jz      short loc_1800026AE
0x1800026a5  mov     rcx, rdi; hLibModule
0x1800026a8  call    cs:__imp_FreeLibrary
0x1800026ae  test    r13b, r13b
0x1800026b1  jz      short loc_1800026BD
0x1800026b3  test    sil, sil
0x1800026b6  jnz     short loc_1800026BD
0x1800026b8  btr     dword ptr [r14], 0Ah
0x1800026bd  mov     eax, [r14]
0x1800026c0  test    bpl, al
0x1800026c3  jz      short loc_1800026CA
0x1800026c5  test    sil, sil
0x1800026c8  jnz     short loc_1800026CD
0x1800026ca  xor     r12d, r12d
0x1800026cd  and     eax, 0FFFFFFFEh
0x1800026d0  or      eax, r12d
0x1800026d3  mov     [r14], eax
0x1800026d6  mov     rax, r14
0x1800026d9  mov     rbx, [rsp+78h+arg_0]
0x1800026e1  add     rsp, 40h
0x1800026e5  pop     r15
0x1800026e7  pop     r14
0x1800026e9  pop     r13
0x1800026eb  pop     r12
0x1800026ed  pop     rdi
0x1800026ee  pop     rsi
0x1800026ef  pop     rbp
0x1800026f0  retn
```
