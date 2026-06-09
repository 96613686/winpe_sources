# EnumWindowStationProc(ushort *,__int64)

- ea: `0x18001e690`
- end: `0x18001e70f`
- name: `?EnumWindowStationProc@@YAHPEAG_J@Z`
- size: `127`
- prototype: `__int64 __fastcall(const WCHAR *, LPARAM)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001e690`

## import_xrefs

- `USER32!OpenWindowStationW` at `0x18001e6a8`
- `USER32!OpenWindowStationW` at `0x18001e6a8`
- `USER32!GetProcessWindowStation` at `0x18001e6b6`
- `USER32!GetProcessWindowStation` at `0x18001e6b6`
- `USER32!SetProcessWindowStation` at `0x18001e6e5`
- `USER32!SetProcessWindowStation` at `0x18001e6f2`
- `USER32!SetProcessWindowStation` at `0x18001e6e5`
- `USER32!SetProcessWindowStation` at `0x18001e6f2`
- `USER32!EnumDesktopsW` at `0x18001e707`
- `USER32!EnumDesktopsW` at `0x18001e707`
- `USER32!CloseWindowStation` at `0x18001e6c7`
- `USER32!CloseWindowStation` at `0x18001e6c7`

## pseudocode

```c
__int64 __fastcall EnumWindowStationProc(const WCHAR *a1, LPARAM a2)
{
  HWINSTA v3; // rbx
  HWINSTA ProcessWindowStation; // rdi

  v3 = OpenWindowStationW(a1, 0, 1u);
  if ( v3 )
  {
    ProcessWindowStation = GetProcessWindowStation();
    if ( ProcessWindowStation )
    {
      if ( SetProcessWindowStation(v3) )
        EnumDesktopsW(v3, (DESKTOPENUMPROCW)EnumDesktopProc, a2);
      SetProcessWindowStation(ProcessWindowStation);
    }
    CloseWindowStation(v3);
  }
  return 1;
}

```

## disassembly

```asm
0x18001e690  mov     [rsp+arg_0], rbx
0x18001e695  mov     [rsp+arg_8], rsi
0x18001e69a  push    rdi
0x18001e69b  sub     rsp, 20h
0x18001e69f  mov     rsi, rdx
0x18001e6a2  xor     edx, edx; fInherit
0x18001e6a4  lea     r8d, [rdx+1]; dwDesiredAccess
0x18001e6a8  call    cs:__imp_OpenWindowStationW
0x18001e6ae  mov     rbx, rax
0x18001e6b1  test    rax, rax
0x18001e6b4  jz      short loc_18001E6CD
0x18001e6b6  call    cs:__imp_GetProcessWindowStation
0x18001e6bc  mov     rdi, rax
0x18001e6bf  test    rax, rax
0x18001e6c2  jnz     short loc_18001E6E2
0x18001e6c4  mov     rcx, rbx; hWinSta
0x18001e6c7  call    cs:__imp_CloseWindowStation
0x18001e6cd  mov     rbx, [rsp+28h+arg_0]
0x18001e6d2  mov     eax, 1
0x18001e6d7  mov     rsi, [rsp+28h+arg_8]
0x18001e6dc  add     rsp, 20h
0x18001e6e0  pop     rdi
0x18001e6e1  retn
0x18001e6e2  mov     rcx, rbx; hWinSta
0x18001e6e5  call    cs:__imp_SetProcessWindowStation
0x18001e6eb  test    eax, eax
0x18001e6ed  jnz     short loc_18001E6FA
0x18001e6ef  mov     rcx, rdi; hWinSta
0x18001e6f2  call    cs:__imp_SetProcessWindowStation
0x18001e6f8  jmp     short loc_18001E6C4
0x18001e6fa  mov     r8, rsi; lParam
0x18001e6fd  lea     rdx, ?EnumDesktopProc@@YAHPEAG_J@Z; lpEnumFunc
0x18001e704  mov     rcx, rbx; hwinsta
0x18001e707  call    cs:__imp_EnumDesktopsW
0x18001e70d  jmp     short loc_18001E6EF
```
