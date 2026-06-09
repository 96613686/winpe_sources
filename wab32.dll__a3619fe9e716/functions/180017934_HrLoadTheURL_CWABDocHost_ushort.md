# HrLoadTheURL(CWABDocHost *,ushort *)

- ea: `0x180017934`
- end: `0x180017a35`
- name: `?HrLoadTheURL@@YAJPEAVCWABDocHost@@PEAG@Z`
- size: `257`
- prototype: `__int64 __fastcall(struct CWABDocHost *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017b08`

## callees

- `0x1800045e4`
- `0x180017934`
- `0x180017a3c`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x18001797d`
- `KERNEL32!LoadLibraryW` at `0x18001797d`
- `KERNEL32!FreeLibrary` at `0x1800179b3`
- `KERNEL32!FreeLibrary` at `0x180017a08`
- `KERNEL32!FreeLibrary` at `0x1800179b3`
- `KERNEL32!FreeLibrary` at `0x180017a08`
- `KERNEL32!GetProcAddress` at `0x18001799c`
- `KERNEL32!GetProcAddress` at `0x18001799c`

## string_xrefs

- `0x180017976`: `urlmon.dll`
- `0x180017992`: `CreateURLMoniker`

## pseudocode

```c
__int64 __fastcall HrLoadTheURL(struct CWABDocHost *this, unsigned __int16 *a2)
{
  HMODULE LibraryW; // rax
  HMODULE v4; // rdi
  int v5; // ebx
  int (*ProcAddress)(struct IMoniker *, const unsigned __int16 *, struct IMoniker **); // rax
  struct IMoniker *v7; // rcx
  struct IMoniker *v9; // [rsp+20h] [rbp-828h] BYREF
  unsigned __int16 v10[1024]; // [rsp+30h] [rbp-818h] BYREF

  v9 = 0;
  StringCchCopyW(v10, 0x400u, a2);
  LibraryW = LoadLibraryW(L"urlmon.dll");
  v4 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = (int (*)(struct IMoniker *, const unsigned __int16 *, struct IMoniker **))GetProcAddress(
                                                                                              LibraryW,
                                                                                              "CreateURLMoniker");
    lpfnCreateURLMoniker = ProcAddress;
    if ( ProcAddress )
    {
      v5 = ((__int64 (__fastcall *)(_QWORD, unsigned __int16 *, struct IMoniker **))ProcAddress)(0, v10, &v9);
      if ( v5 >= 0 )
        v5 = CWABDocHost::LoadFromMoniker(this, v9);
    }
    else
    {
      v5 = 0;
      FreeLibrary(v4);
    }
  }
  else
  {
    v5 = -2147219963;
  }
  v7 = v9;
  if ( v9 )
  {
    v9 = 0;
    ((void (__fastcall *)(struct IMoniker *))v7->lpVtbl->Release)(v7);
  }
  if ( v4 )
    FreeLibrary(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180017934  mov     [rsp+arg_10], rbx
0x180017939  mov     [rsp+arg_18], rsi
0x18001793e  push    rdi
0x18001793f  sub     rsp, 840h
0x180017946  mov     rax, cs:__security_cookie
0x18001794d  xor     rax, rsp
0x180017950  mov     [rsp+848h+var_18], rax
0x180017958  mov     rsi, rcx
0x18001795b  mov     [rsp+848h+var_828], 0
0x180017964  mov     r8, rdx; unsigned __int16 *
0x180017967  lea     rcx, [rsp+848h+var_818]; unsigned __int16 *
0x18001796c  mov     edx, 400h; unsigned __int64
0x180017971  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017976  lea     rcx, aUrlmonDll; "urlmon.dll"
0x18001797d  call    cs:__imp_LoadLibraryW
0x180017983  mov     rdi, rax
0x180017986  test    rax, rax
0x180017989  jnz     short loc_180017992
0x18001798b  mov     ebx, 80040605h
0x180017990  jmp     short loc_1800179E1
0x180017992  lea     rdx, aCreateurlmonik; "CreateURLMoniker"
0x180017999  mov     rcx, rdi; hModule
0x18001799c  call    cs:__imp_GetProcAddress
0x1800179a2  mov     cs:?lpfnCreateURLMoniker@@3P6AJPEAUIMoniker@@PEBGPEAPEAU1@@ZEA, rax; long (*lpfnCreateURLMoniker)(IMoniker *,ushort const *,IMoniker * *)
0x1800179a9  test    rax, rax
0x1800179ac  jnz     short loc_1800179BB
0x1800179ae  xor     ebx, ebx
0x1800179b0  mov     rcx, rdi; hLibModule
0x1800179b3  call    cs:__imp_FreeLibrary
0x1800179b9  jmp     short loc_1800179E1
0x1800179bb  lea     r8, [rsp+848h+var_828]
0x1800179c0  xor     ecx, ecx
0x1800179c2  lea     rdx, [rsp+848h+var_818]
0x1800179c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179cc  mov     ebx, eax
0x1800179ce  test    eax, eax
0x1800179d0  js      short loc_1800179E1
0x1800179d2  mov     rdx, [rsp+848h+var_828]; struct IMoniker *
0x1800179d7  mov     rcx, rsi; this
0x1800179da  call    ?LoadFromMoniker@CWABDocHost@@QEAAJPEAUIMoniker@@@Z; CWABDocHost::LoadFromMoniker(IMoniker *)
0x1800179df  mov     ebx, eax
0x1800179e1  mov     rcx, [rsp+848h+var_828]
0x1800179e6  test    rcx, rcx
0x1800179e9  jz      short loc_180017A00
0x1800179eb  mov     [rsp+848h+var_828], 0
0x1800179f4  mov     rax, [rcx]
0x1800179f7  mov     rax, [rax+10h]
0x1800179fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a00  test    rdi, rdi
0x180017a03  jz      short loc_180017A0E
0x180017a05  mov     rcx, rdi; hLibModule
0x180017a08  call    cs:__imp_FreeLibrary
0x180017a0e  mov     eax, ebx
0x180017a10  mov     rcx, [rsp+848h+var_18]
0x180017a18  xor     rcx, rsp; StackCookie
0x180017a1b  call    __security_check_cookie
0x180017a20  lea     r11, [rsp+848h+var_8]
0x180017a28  mov     rbx, [r11+20h]
0x180017a2c  mov     rsi, [r11+28h]
0x180017a30  mov     rsp, r11
0x180017a33  pop     rdi
0x180017a34  retn
```
