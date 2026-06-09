# CCleanupBase::Initialize(HKEY__ *,ushort const *,ushort * *,ushort * *,ulong *)

- ea: `0x180002930`
- end: `0x180002a70`
- name: `?Initialize@CCleanupBase@@UEAAJPEAUHKEY__@@PEBGPEAPEAG2PEAK@Z`
- size: `320`
- prototype: `signed int __fastcall(LONG_PTR lParam, HKEY, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180002930`
- `0x180002a78`

## import_xrefs

- `ntdll!WinSqmIsOptedIn` at `0x180002a44`
- `ntdll!WinSqmIsOptedIn` at `0x180002a44`
- `KERNEL32!GetLastError` at `0x1800029a5`
- `KERNEL32!GetLastError` at `0x1800029a5`
- `KERNEL32!CreateEventW` at `0x180002993`
- `KERNEL32!CreateEventW` at `0x180002993`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x1800029c9`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x1800029c9`
- `KERNEL32!EnumUILanguagesW` at `0x1800029fd`
- `KERNEL32!EnumUILanguagesW` at `0x1800029fd`
- `DismApi!DismInitialize` at `0x180002a0f`
- `DismApi!DismInitialize` at `0x180002a0f`
- `DismApi!DismOpenSession` at `0x180002a38`
- `DismApi!DismOpenSession` at `0x180002a38`

## pseudocode

```c
signed int __fastcall CCleanupBase::Initialize(
        LONG_PTR lParam,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        unsigned int *a6)
{
  HANDLE EventW; // rax
  signed int result; // eax
  int v10; // ebx

  if ( !a4 || !a5 || !a6 || !a3 )
    return -2147024809;
  *a4 = 0;
  *a5 = 0;
  *a6 = *(_DWORD *)(lParam + 532);
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(lParam + 616) = EventW;
  if ( EventW && GetSystemWindowsDirectoryW((LPWSTR)(lParam + 8), 0x104u) )
  {
    if ( *(_WORD *)(lParam + 8) != *a3 || !(unsigned int)IsProcessElevated() )
      return 1;
    if ( !*(_DWORD *)(lParam + 584) || EnumUILanguagesW(CCleanupBase::EnumUILanguagesProc, 8u, lParam) )
    {
      v10 = DismInitialize(2, 0, 0);
      if ( v10 >= 0 )
      {
        *(_DWORD *)(lParam + 588) = 1;
        v10 = DismOpenSession(L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}", 0, 0, lParam + 624);
        if ( v10 >= 0 )
          *(_DWORD *)(lParam + 576) = WinSqmIsOptedIn();
      }
      return v10;
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180002930  mov     [rsp+arg_0], rbx
0x180002935  mov     [rsp+arg_8], rsi
0x18000293a  push    rdi
0x18000293b  sub     rsp, 20h
0x18000293f  mov     rsi, r8
0x180002942  mov     rdi, rcx
0x180002945  test    r9, r9
0x180002948  jz      loc_180002A5B
0x18000294e  mov     rax, [rsp+28h+arg_20]
0x180002953  test    rax, rax
0x180002956  jz      loc_180002A5B
0x18000295c  mov     rcx, [rsp+28h+arg_28]
0x180002961  test    rcx, rcx
0x180002964  jz      loc_180002A5B
0x18000296a  test    r8, r8
0x18000296d  jz      loc_180002A5B
0x180002973  mov     qword ptr [r9], 0
0x18000297a  xor     r8d, r8d; bInitialState
0x18000297d  mov     qword ptr [rax], 0
0x180002984  xor     r9d, r9d; lpName
0x180002987  mov     eax, [rdi+214h]
0x18000298d  xor     edx, edx; bManualReset
0x18000298f  mov     [rcx], eax
0x180002991  xor     ecx, ecx; lpEventAttributes
0x180002993  call    cs:__imp_CreateEventW
0x180002999  mov     [rdi+268h], rax
0x1800029a0  test    rax, rax
0x1800029a3  jnz     short loc_1800029C0
0x1800029a5  call    cs:__imp_GetLastError
0x1800029ab  test    eax, eax
0x1800029ad  jle     loc_180002A60
0x1800029b3  movzx   eax, ax
0x1800029b6  or      eax, 80070000h
0x1800029bb  jmp     loc_180002A60
0x1800029c0  mov     edx, 104h; uSize
0x1800029c5  lea     rcx, [rdi+8]; lpBuffer
0x1800029c9  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800029cf  test    eax, eax
0x1800029d1  jz      short loc_1800029A5
0x1800029d3  movzx   eax, word ptr [rsi]
0x1800029d6  cmp     [rdi+8], ax
0x1800029da  jnz     short loc_180002A52
0x1800029dc  call    ?IsProcessElevated@@YAHXZ; IsProcessElevated(void)
0x1800029e1  test    eax, eax
0x1800029e3  jz      short loc_180002A52
0x1800029e5  cmp     dword ptr [rdi+248h], 0
0x1800029ec  jz      short loc_180002A07
0x1800029ee  mov     r8, rdi; lParam
0x1800029f1  lea     rcx, ?EnumUILanguagesProc@CCleanupBase@@KAHPEAG_J@Z; lpUILanguageEnumProc
0x1800029f8  mov     edx, 8; dwFlags
0x1800029fd  call    cs:__imp_EnumUILanguagesW
0x180002a03  test    eax, eax
0x180002a05  jz      short loc_1800029A5
0x180002a07  xor     edx, edx
0x180002a09  xor     r8d, r8d
0x180002a0c  lea     ecx, [rdx+2]
0x180002a0f  call    cs:__imp_DismInitialize
0x180002a15  mov     ebx, eax
0x180002a17  test    eax, eax
0x180002a19  js      short loc_180002A57
0x180002a1b  lea     r9, [rdi+270h]
0x180002a22  mov     dword ptr [rdi+24Ch], 1
0x180002a2c  xor     r8d, r8d
0x180002a2f  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x180002a36  xor     edx, edx
0x180002a38  call    cs:__imp_DismOpenSession
0x180002a3e  mov     ebx, eax
0x180002a40  test    eax, eax
0x180002a42  js      short loc_180002A57
0x180002a44  call    cs:__imp_WinSqmIsOptedIn
0x180002a4a  mov     [rdi+240h], eax
0x180002a50  jmp     short loc_180002A57
0x180002a52  mov     ebx, 1
0x180002a57  mov     eax, ebx
0x180002a59  jmp     short loc_180002A60
0x180002a5b  mov     eax, 80070057h
0x180002a60  mov     rbx, [rsp+28h+arg_0]
0x180002a65  mov     rsi, [rsp+28h+arg_8]
0x180002a6a  add     rsp, 20h
0x180002a6e  pop     rdi
0x180002a6f  retn
```
