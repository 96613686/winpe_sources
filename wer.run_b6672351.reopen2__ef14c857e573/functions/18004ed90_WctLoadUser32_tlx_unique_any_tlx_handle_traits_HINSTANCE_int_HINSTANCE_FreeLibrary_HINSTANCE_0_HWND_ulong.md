# WctLoadUser32(tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> *,HWND__ * (**)(ulong))

- ea: `0x18004ed90`
- end: `0x18004eede`
- name: `?WctLoadUser32@@YAKPEAV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEAP6APEAUHWND__@@K@Z@Z`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180060970`

## callees

- `0x180004c64`
- `0x180020680`
- `0x180039210`
- `0x180039760`
- `0x18004ed90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004ee4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004ee4f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004ede9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004ede9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18004ee28`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18004ee28`

## string_xrefs

- `0x18004ee21`: `user32.dll`

## pseudocode

```c
__int64 __fastcall WctLoadUser32(HMODULE *a1, FARPROC *a2)
{
  wchar_t *v4; // rcx
  HMODULE v5; // rcx
  HMODULE LibraryW; // rax
  unsigned int v7; // ebx
  FARPROC ProcAddress; // rsi
  HMODULE v10; // [rsp+50h] [rbp+8h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    v5 = *a1;
    *a1 = 0;
    if ( v5 )
      FreeLibrary(v5);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    *a2 = 0;
    v4 = WPP_GLOBAL_Control;
  }
  if ( a1 && a2 )
  {
    LibraryW = LoadLibraryW(L"user32.dll");
    v10 = LibraryW;
    if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "GetSendMessageReceiver")) != 0 )
    {
      tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::operator=(
        a1,
        &v10);
      v7 = 0;
      *a2 = ProcAddress;
    }
    else
    {
      v7 = 50;
    }
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, v7);
    tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(&v10);
  }
  else
  {
    v7 = 87;
    if ( v4 != (wchar_t *)&WPP_GLOBAL_Control && (v4[14] & 4) != 0 )
      WPP_SF_d(*((_QWORD *)v4 + 2), 72, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, 87);
  }
  return v7;
}

```

## disassembly

```asm
0x18004ed90  push    rbx
0x18004ed92  push    rsi
0x18004ed93  push    rdi
0x18004ed94  push    r14
0x18004ed96  sub     rsp, 28h
0x18004ed9a  mov     rdi, rdx
0x18004ed9d  mov     rbx, rcx
0x18004eda0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004eda7  lea     r14, WPP_GLOBAL_Control
0x18004edae  cmp     rcx, r14
0x18004edb1  jz      short loc_18004EDD5
0x18004edb3  test    byte ptr [rcx+1Ch], 4
0x18004edb7  jz      short loc_18004EDD5
0x18004edb9  mov     rcx, [rcx+10h]
0x18004edbd  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18004edc4  mov     edx, 47h ; 'G'
0x18004edc9  call    WPP_SF_
0x18004edce  mov     rcx, cs:WPP_GLOBAL_Control
0x18004edd5  test    rbx, rbx
0x18004edd8  jz      short loc_18004EDFC
0x18004edda  mov     rcx, [rbx]; hLibModule
0x18004eddd  mov     qword ptr [rbx], 0
0x18004ede4  test    rcx, rcx
0x18004ede7  jz      short loc_18004EDF5
0x18004ede9  call    cs:__imp_FreeLibrary
0x18004edf0  nop     dword ptr [rax+rax+00h]
0x18004edf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004edfc  test    rdi, rdi
0x18004edff  jz      short loc_18004EE0F
0x18004ee01  mov     qword ptr [rdi], 0
0x18004ee08  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ee0f  test    rbx, rbx
0x18004ee12  jz      loc_18004EEAB
0x18004ee18  test    rdi, rdi
0x18004ee1b  jz      loc_18004EEAB
0x18004ee21  lea     rcx, aUser32Dll; "user32.dll"
0x18004ee28  call    cs:__imp_LoadLibraryW
0x18004ee2f  nop     dword ptr [rax+rax+00h]
0x18004ee34  mov     [rsp+48h+arg_0], rax
0x18004ee39  test    rax, rax
0x18004ee3c  jnz     short loc_18004EE45
0x18004ee3e  mov     ebx, 32h ; '2'
0x18004ee43  jmp     short loc_18004EE75
0x18004ee45  lea     rdx, aGetsendmessage; "GetSendMessageReceiver"
0x18004ee4c  mov     rcx, rax; hModule
0x18004ee4f  call    cs:__imp_GetProcAddress
0x18004ee56  nop     dword ptr [rax+rax+00h]
0x18004ee5b  mov     rsi, rax
0x18004ee5e  test    rax, rax
0x18004ee61  jz      short loc_18004EE3E
0x18004ee63  lea     rdx, [rsp+48h+arg_0]
0x18004ee68  mov     rcx, rbx
0x18004ee6b  call    ??4?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::operator=(tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> &&)
0x18004ee70  xor     ebx, ebx
0x18004ee72  mov     [rdi], rsi
0x18004ee75  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ee7c  cmp     rcx, r14
0x18004ee7f  jz      short loc_18004EE9F
0x18004ee81  test    byte ptr [rcx+1Ch], 4
0x18004ee85  jz      short loc_18004EE9F
0x18004ee87  mov     rcx, [rcx+10h]
0x18004ee8b  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18004ee92  mov     edx, 49h ; 'I'
0x18004ee97  mov     r9d, ebx
0x18004ee9a  call    WPP_SF_d
0x18004ee9f  lea     rcx, [rsp+48h+arg_0]
0x18004eea4  call    ??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)
0x18004eea9  jmp     short loc_18004EED1
0x18004eeab  mov     ebx, 57h ; 'W'
0x18004eeb0  cmp     rcx, r14
0x18004eeb3  jz      short loc_18004EED1
0x18004eeb5  test    byte ptr [rcx+1Ch], 4
0x18004eeb9  jz      short loc_18004EED1
0x18004eebb  mov     rcx, [rcx+10h]
0x18004eebf  lea     edx, [rbx-0Fh]
0x18004eec2  mov     r9d, ebx
0x18004eec5  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18004eecc  call    WPP_SF_d
0x18004eed1  mov     eax, ebx
0x18004eed3  add     rsp, 28h
0x18004eed7  pop     r14
0x18004eed9  pop     rdi
0x18004eeda  pop     rsi
0x18004eedb  pop     rbx
0x18004eedc  retn
```
