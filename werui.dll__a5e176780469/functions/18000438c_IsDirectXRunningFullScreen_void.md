# IsDirectXRunningFullScreen(void)

- ea: `0x18000438c`
- end: `0x180004428`
- name: `?IsDirectXRunningFullScreen@@YAHXZ`
- size: `156`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180006ee0`

## callees

- `0x1800035dc`
- `0x180003fc4`
- `0x18000438c`
- `0x180018010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x18000439b`
- `KERNEL32!LoadLibraryW` at `0x18000439b`
- `KERNEL32!GetProcAddress` at `0x1800043e3`
- `KERNEL32!GetProcAddress` at `0x1800043e3`

## string_xrefs

- `0x180004394`: `gdi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 IsDirectXRunningFullScreen(void)
{
  unsigned int v0; // ebx
  HMODULE LibraryW; // rax
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  unsigned __int8 (*ProcAddress)(void); // rax
  HMODULE v6; // [rsp+30h] [rbp+8h] BYREF

  v0 = 0;
  LibraryW = LoadLibraryW(L"gdi32.dll");
  v6 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = (unsigned __int8 (*)(void))GetProcAddress(LibraryW, "D3DKMTCheckExclusiveOwnership");
    if ( ProcAddress )
    {
      v0 = ProcAddress();
      goto LABEL_11;
    }
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v3 = 16;
      goto LABEL_5;
    }
  }
  else
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v3 = 15;
LABEL_5:
      WPP_SF_(v2[2], v3, WPP_da26f2d1156739261f61a97d8df66789_Traceguids);
    }
  }
LABEL_11:
  tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(&v6);
  return v0;
}

```

## disassembly

```asm
0x18000438c  push    rbx
0x18000438e  sub     rsp, 20h
0x180004392  xor     ebx, ebx
0x180004394  lea     rcx, LibFileName; "gdi32.dll"
0x18000439b  call    cs:__imp_LoadLibraryW
0x1800043a1  mov     [rsp+28h+arg_0], rax
0x1800043a6  test    rax, rax
0x1800043a9  jnz     short loc_1800043D9
0x1800043ab  lea     rax, WPP_GLOBAL_Control
0x1800043b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043b9  cmp     rcx, rax
0x1800043bc  jz      short loc_180004416
0x1800043be  test    byte ptr [rcx+1Ch], 1
0x1800043c2  jz      short loc_180004416
0x1800043c4  lea     edx, [rbx+0Fh]
0x1800043c7  lea     r8, WPP_da26f2d1156739261f61a97d8df66789_Traceguids
0x1800043ce  mov     rcx, [rcx+10h]
0x1800043d2  call    WPP_SF_
0x1800043d7  jmp     short loc_180004416
0x1800043d9  lea     rdx, ProcName; "D3DKMTCheckExclusiveOwnership"
0x1800043e0  mov     rcx, rax; hModule
0x1800043e3  call    cs:__imp_GetProcAddress
0x1800043e9  test    rax, rax
0x1800043ec  jnz     short loc_18000440E
0x1800043ee  lea     rax, WPP_GLOBAL_Control
0x1800043f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043fc  cmp     rcx, rax
0x1800043ff  jz      short loc_180004416
0x180004401  test    byte ptr [rcx+1Ch], 1
0x180004405  jz      short loc_180004416
0x180004407  mov     edx, 10h
0x18000440c  jmp     short loc_1800043C7
0x18000440e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004413  movzx   ebx, al
0x180004416  lea     rcx, [rsp+28h+arg_0]
0x18000441b  call    ??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)
0x180004420  mov     eax, ebx
0x180004422  add     rsp, 20h
0x180004426  pop     rbx
0x180004427  retn
```
