# LoadIconFromModule(ushort *,ulong,int,int,HICON__ * *)

- ea: `0x18000553c`
- end: `0x1800055eb`
- name: `?LoadIconFromModule@@YAJPEAGKHHPEAPEAUHICON__@@@Z`
- size: `175`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, int, int, HICON *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000449c`
- `0x180005bbc`
- `0x180010bec`

## callees

- `0x18000553c`
- `0x1800075c0`
- `0x180016574`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800055d6`
- `KERNEL32!FreeLibrary` at `0x1800055d6`
- `KERNEL32!GetLastError` at `0x18000558f`
- `KERNEL32!GetLastError` at `0x18000558f`
- `KERNEL32!LoadLibraryW` at `0x180005579`
- `KERNEL32!LoadLibraryW` at `0x180005579`
- `KERNEL32!SetErrorMode` at `0x18000556a`
- `KERNEL32!SetErrorMode` at `0x180005584`
- `KERNEL32!SetErrorMode` at `0x18000556a`
- `KERNEL32!SetErrorMode` at `0x180005584`

## string_xrefs

- `0x180005570`: `wmploc.dll`

## pseudocode

```c
__int64 __fastcall LoadIconFromModule(unsigned __int16 *a1, unsigned __int16 a2, int a3, int a4, HICON *a5)
{
  HICON *phico; // rdi
  int IconWithScaleDown; // ebx
  UINT v8; // ebx
  HMODULE LibraryW; // rsi
  signed int LastError; // eax
  int v12; // [rsp+60h] [rbp+18h] BYREF
  int cy; // [rsp+68h] [rbp+20h] BYREF

  cy = a4;
  v12 = a3;
  phico = a5;
  if ( a5 )
  {
    v8 = SetErrorMode(0x8003u);
    LibraryW = LoadLibraryW(L"wmploc.dll");
    SetErrorMode(v8);
    if ( LibraryW )
      goto LABEL_7;
    LastError = GetLastError();
    IconWithScaleDown = LastError;
    if ( LastError > 0 )
      IconWithScaleDown = (unsigned __int16)LastError | 0x80070000;
    if ( IconWithScaleDown >= 0 )
    {
LABEL_7:
      GetLogicalToPhysicalDPI(&v12, &cy);
      IconWithScaleDown = LoadIconWithScaleDown(LibraryW, (PCWSTR)a2, v12, cy, phico);
      FreeLibrary(LibraryW);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)IconWithScaleDown;
}

```

## disassembly

```asm
0x18000553c  mov     [rsp+arg_0], rbx
0x180005541  mov     [rsp+cy], r9d
0x180005546  mov     [rsp+arg_10], r8d
0x18000554b  push    rbp
0x18000554c  push    rsi
0x18000554d  push    rdi
0x18000554e  sub     rsp, 30h
0x180005552  mov     rdi, [rsp+48h+arg_20]
0x180005557  mov     ebp, edx
0x180005559  test    rdi, rdi
0x18000555c  jnz     short loc_180005565
0x18000555e  mov     ebx, 80004003h
0x180005563  jmp     short loc_1800055DC
0x180005565  mov     ecx, 8003h; uMode
0x18000556a  call    cs:__imp_SetErrorMode
0x180005570  lea     rcx, LibFileName; "wmploc.dll"
0x180005577  mov     ebx, eax
0x180005579  call    cs:__imp_LoadLibraryW
0x18000557f  mov     ecx, ebx; uMode
0x180005581  mov     rsi, rax
0x180005584  call    cs:__imp_SetErrorMode
0x18000558a  test    rsi, rsi
0x18000558d  jnz     short loc_1800055A8
0x18000558f  call    cs:__imp_GetLastError
0x180005595  mov     ebx, eax
0x180005597  test    eax, eax
0x180005599  jle     short loc_1800055A4
0x18000559b  movzx   ebx, ax
0x18000559e  or      ebx, 80070000h
0x1800055a4  test    ebx, ebx
0x1800055a6  js      short loc_1800055DC
0x1800055a8  lea     rdx, [rsp+48h+cy]; int *
0x1800055ad  lea     rcx, [rsp+48h+arg_10]; int *
0x1800055b2  call    ?GetLogicalToPhysicalDPI@@YAXPEAH0@Z; GetLogicalToPhysicalDPI(int *,int *)
0x1800055b7  mov     r9d, [rsp+48h+cy]; cy
0x1800055bc  mov     rcx, rsi; hinst
0x1800055bf  mov     r8d, [rsp+48h+arg_10]; cx
0x1800055c4  movzx   edx, bp; pszName
0x1800055c7  mov     [rsp+48h+phico], rdi; phico
0x1800055cc  call    LoadIconWithScaleDown
0x1800055d1  mov     rcx, rsi; hLibModule
0x1800055d4  mov     ebx, eax
0x1800055d6  call    cs:__imp_FreeLibrary
0x1800055dc  mov     eax, ebx
0x1800055de  mov     rbx, [rsp+48h+arg_0]
0x1800055e3  add     rsp, 30h
0x1800055e7  pop     rdi
0x1800055e8  pop     rsi
0x1800055e9  pop     rbp
0x1800055ea  retn
```
