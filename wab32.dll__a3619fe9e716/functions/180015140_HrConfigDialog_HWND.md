# HrConfigDialog(HWND__ *)

- ea: `0x180015140`
- end: `0x18001525c`
- name: `?HrConfigDialog@@YAJPEAUHWND__@@@Z`
- size: `284`
- prototype: `__int64 __fastcall(HWND)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180015e4c`

## callees

- `0x180015140`
- `0x180093010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x18001515e`
- `KERNEL32!LoadLibraryW` at `0x18001515e`
- `KERNEL32!FreeLibrary` at `0x180015247`
- `KERNEL32!FreeLibrary` at `0x180015247`
- `KERNEL32!GetProcAddress` at `0x180015185`
- `KERNEL32!GetProcAddress` at `0x1800151c4`
- `KERNEL32!GetProcAddress` at `0x18001522e`
- `KERNEL32!GetProcAddress` at `0x180015185`
- `KERNEL32!GetProcAddress` at `0x1800151c4`
- `KERNEL32!GetProcAddress` at `0x18001522e`

## string_xrefs

- `0x180015157`: `tapi32.dll`

## pseudocode

```c
__int64 __fastcall HrConfigDialog(HWND a1)
{
  HMODULE LibraryW; // rax
  HMODULE v3; // rdi
  unsigned int v5; // ebx
  FARPROC ProcAddress; // rax
  unsigned int (__fastcall *v7)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // rsi
  FARPROC v8; // rax
  FARPROC v9; // rax
  unsigned int v10; // [rsp+58h] [rbp+10h] BYREF
  int v11; // [rsp+60h] [rbp+18h] BYREF

  v10 = 0;
  LibraryW = LoadLibraryW(L"tapi32.dll");
  v3 = LibraryW;
  if ( !LibraryW )
    return 2147500037LL;
  v5 = -2147467259;
  ProcAddress = GetProcAddress(LibraryW, "lineTranslateDialog");
  v7 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress;
  if ( ProcAddress )
  {
    if ( ((unsigned int (__fastcall *)(_QWORD, _QWORD, __int64, HWND, _QWORD))ProcAddress)(0, 0, 65540, a1, 0) )
    {
      v8 = GetProcAddress(v3, "lineInitialize");
      if ( !v8 )
        goto LABEL_11;
      v11 = 0;
      if ( ((unsigned int (__fastcall *)(unsigned int *, HINSTANCE, __int64 (__fastcall *)(), _QWORD, int *))v8)(
             &v10,
             hinstMapiX,
             wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
             0,
             &v11)
        || v7(v10, 0, 65540, a1, 0) )
      {
        goto LABEL_11;
      }
      v9 = GetProcAddress(v3, "lineShutdown");
      if ( v9 )
        ((void (__fastcall *)(_QWORD))v9)(v10);
    }
    v5 = 0;
  }
LABEL_11:
  FreeLibrary(v3);
  return v5;
}

```

## disassembly

```asm
0x180015140  mov     [rsp+arg_0], rbx
0x180015145  push    rbp
0x180015146  push    rsi
0x180015147  push    rdi
0x180015148  sub     rsp, 30h
0x18001514c  mov     rbp, rcx
0x18001514f  mov     [rsp+48h+arg_8], 0
0x180015157  lea     rcx, aTapi32Dll; "tapi32.dll"
0x18001515e  call    cs:__imp_LoadLibraryW
0x180015164  mov     rdi, rax
0x180015167  test    rax, rax
0x18001516a  jnz     short loc_180015176
0x18001516c  mov     eax, 80004005h
0x180015171  jmp     loc_18001524F
0x180015176  lea     rdx, ProcName; "lineTranslateDialog"
0x18001517d  mov     rcx, rdi; hModule
0x180015180  mov     ebx, 80004005h
0x180015185  call    cs:__imp_GetProcAddress
0x18001518b  mov     rsi, rax
0x18001518e  test    rax, rax
0x180015191  jz      loc_180015244
0x180015197  mov     r9, rbp
0x18001519a  mov     [rsp+48h+var_28], 0
0x1800151a3  xor     edx, edx
0x1800151a5  xor     ecx, ecx
0x1800151a7  mov     r8d, 10004h
0x1800151ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151b2  test    eax, eax
0x1800151b4  jz      loc_180015242
0x1800151ba  lea     rdx, aLineinitialize; "lineInitialize"
0x1800151c1  mov     rcx, rdi; hModule
0x1800151c4  call    cs:__imp_GetProcAddress
0x1800151ca  test    rax, rax
0x1800151cd  jz      short loc_180015244
0x1800151cf  mov     rdx, cs:hinstMapiX
0x1800151d6  lea     rcx, [rsp+48h+arg_10]
0x1800151db  mov     [rsp+48h+var_28], rcx
0x1800151e0  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x1800151e7  lea     rcx, [rsp+48h+arg_8]
0x1800151ec  mov     [rsp+48h+arg_10], 0
0x1800151f4  xor     r9d, r9d
0x1800151f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151fc  test    eax, eax
0x1800151fe  jnz     short loc_180015244
0x180015200  mov     ecx, [rsp+48h+arg_8]
0x180015204  mov     r9, rbp
0x180015207  xor     edx, edx
0x180015209  mov     [rsp+48h+var_28], 0
0x180015212  mov     r8d, 10004h
0x180015218  mov     rax, rsi
0x18001521b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015220  test    eax, eax
0x180015222  jnz     short loc_180015244
0x180015224  lea     rdx, aLineshutdown; "lineShutdown"
0x18001522b  mov     rcx, rdi; hModule
0x18001522e  call    cs:__imp_GetProcAddress
0x180015234  test    rax, rax
0x180015237  jz      short loc_180015242
0x180015239  mov     ecx, [rsp+48h+arg_8]
0x18001523d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015242  xor     ebx, ebx
0x180015244  mov     rcx, rdi; hLibModule
0x180015247  call    cs:__imp_FreeLibrary
0x18001524d  mov     eax, ebx
0x18001524f  mov     rbx, [rsp+48h+arg_0]
0x180015254  add     rsp, 30h
0x180015258  pop     rdi
0x180015259  pop     rsi
0x18001525a  pop     rbp
0x18001525b  retn
```
