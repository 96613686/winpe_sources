# LoadLibraryUsingFullPath(ushort const *,int,HINSTANCE__ * *)

- ea: `0x18004a740`
- end: `0x18004a859`
- name: `?LoadLibraryUsingFullPath@@YAJPEBGHPEAPEAUHINSTANCE__@@@Z`
- size: `281`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, HINSTANCE *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x1800146d4`
- `0x18001c358`
- `0x18001c660`

## callees

- `0x180007824`
- `0x18004a740`
- `0x18004d030`
- `0x18004d350`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18004a7d1`
- `KERNEL32!lstrlenW` at `0x18004a7d1`
- `KERNEL32!LoadLibraryW` at `0x18004a817`
- `KERNEL32!LoadLibraryW` at `0x18004a817`
- `KERNEL32!GetSystemDirectoryW` at `0x18004a790`
- `KERNEL32!GetSystemDirectoryW` at `0x18004a790`

## pseudocode

```c
__int64 __fastcall LoadLibraryUsingFullPath(const unsigned __int16 *a1, int a2, HINSTANCE *a3)
{
  unsigned int v5; // ebx
  HMODULE LibraryW; // rax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-238h] BYREF

  Buffer[0] = 0;
  *a3 = 0;
  if ( a2 )
  {
    if ( a2 != 1 )
      return (unsigned int)-2147024736;
    v5 = StringCchCatW(Buffer, 0x105u, &Names::s_wszInstallDirectory);
    if ( v5 )
      return v5;
  }
  else
  {
    Buffer[260] = 0;
    if ( !GetSystemDirectoryW(Buffer, 0x104u) )
      return (unsigned int)GetLastWin32Error();
  }
  if ( !Buffer[0] )
    return (unsigned int)-2147024736;
  if ( Buffer[lstrlenW(Buffer) - 1] == 92 || (v5 = StringCchCatW(Buffer, 0x105u, L"\\")) == 0 )
  {
    v5 = StringCchCatW(Buffer, 0x105u, a1);
    if ( !v5 )
    {
      LibraryW = LoadLibraryW(Buffer);
      *a3 = LibraryW;
      if ( !LibraryW )
        return (unsigned int)GetLastWin32Error();
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18004a740  mov     r11, rsp
0x18004a743  mov     [r11+8], rbx
0x18004a747  mov     [r11+10h], rbp
0x18004a74b  push    rsi
0x18004a74c  push    rdi
0x18004a74d  push    r14
0x18004a74f  sub     rsp, 240h
0x18004a756  mov     rax, cs:__security_cookie
0x18004a75d  xor     rax, rsp
0x18004a760  mov     [rsp+258h+var_28], rax
0x18004a768  xor     ebp, ebp
0x18004a76a  mov     rdi, r8
0x18004a76d  mov     [rsp+258h+Buffer], bp
0x18004a772  mov     rsi, rcx
0x18004a775  mov     [r8], rbp
0x18004a778  mov     r14d, 105h
0x18004a77e  test    edx, edx
0x18004a780  jnz     short loc_18004A7A6
0x18004a782  lea     edx, [r14-1]; uSize
0x18004a786  mov     [r11-30h], bp
0x18004a78b  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x18004a790  call    cs:__imp_GetSystemDirectoryW
0x18004a796  test    eax, eax
0x18004a798  jnz     short loc_18004A7C5
0x18004a79a  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18004a79f  mov     ebx, eax
0x18004a7a1  jmp     loc_18004A82F
0x18004a7a6  cmp     edx, 1
0x18004a7a9  jnz     short loc_18004A82A
0x18004a7ab  lea     r8, ?s_wszInstallDirectory@Names@@0PAGA; unsigned __int16 *
0x18004a7b2  mov     rdx, r14; unsigned __int64
0x18004a7b5  lea     rcx, [rsp+258h+Buffer]; unsigned __int16 *
0x18004a7ba  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004a7bf  mov     ebx, eax
0x18004a7c1  test    eax, eax
0x18004a7c3  jnz     short loc_18004A82F
0x18004a7c5  cmp     [rsp+258h+Buffer], bp
0x18004a7ca  jz      short loc_18004A82A
0x18004a7cc  lea     rcx, [rsp+258h+Buffer]; lpString
0x18004a7d1  call    cs:__imp_lstrlenW
0x18004a7d7  movsxd  rcx, eax
0x18004a7da  cmp     [rsp+rcx*2+258h+var_23A], 5Ch ; '\'
0x18004a7e0  jz      short loc_18004A7FC
0x18004a7e2  lea     r8, SubBlock; "\\"
0x18004a7e9  mov     rdx, r14; unsigned __int64
0x18004a7ec  lea     rcx, [rsp+258h+Buffer]; unsigned __int16 *
0x18004a7f1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004a7f6  mov     ebx, eax
0x18004a7f8  test    eax, eax
0x18004a7fa  jnz     short loc_18004A82F
0x18004a7fc  mov     r8, rsi; unsigned __int16 *
0x18004a7ff  lea     rcx, [rsp+258h+Buffer]; unsigned __int16 *
0x18004a804  mov     rdx, r14; unsigned __int64
0x18004a807  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004a80c  mov     ebx, eax
0x18004a80e  test    eax, eax
0x18004a810  jnz     short loc_18004A82F
0x18004a812  lea     rcx, [rsp+258h+Buffer]; lpLibFileName
0x18004a817  call    cs:__imp_LoadLibraryW
0x18004a81d  mov     [rdi], rax
0x18004a820  test    rax, rax
0x18004a823  jnz     short loc_18004A82F
0x18004a825  jmp     loc_18004A79A
0x18004a82a  mov     ebx, 800700A0h
0x18004a82f  mov     eax, ebx
0x18004a831  mov     rcx, [rsp+258h+var_28]
0x18004a839  xor     rcx, rsp; StackCookie
0x18004a83c  call    __security_check_cookie
0x18004a841  lea     r11, [rsp+258h+var_18]
0x18004a849  mov     rbx, [r11+20h]
0x18004a84d  mov     rbp, [r11+28h]
0x18004a851  mov     rsp, r11
0x18004a854  pop     r14
0x18004a856  pop     rdi
0x18004a857  pop     rsi
0x18004a858  retn
```
