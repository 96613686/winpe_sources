# CContactRichPreview::RegisterWindowClass(HINSTANCE__ *)

- ea: `0x180038bd4`
- end: `0x180038c99`
- name: `?RegisterWindowClass@CContactRichPreview@@SAHPEAUHINSTANCE__@@@Z`
- size: `197`
- prototype: `__int64 __fastcall(HINSTANCE)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180018060`

## callees

- `0x180038bd4`
- `0x180079e3c`
- `0x180091eaa`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x180038c58`
- `KERNEL32!LoadLibraryW` at `0x180038c58`
- `USER32!LoadCursorW` at `0x180038c1c`
- `USER32!LoadCursorW` at `0x180038c1c`
- `USER32!GetSysColorBrush` at `0x180038c2c`
- `USER32!GetSysColorBrush` at `0x180038c2c`
- `USER32!RegisterClassExW` at `0x180038c48`
- `USER32!RegisterClassExW` at `0x180038c48`

## string_xrefs

- `0x180038c4e`: `msftedit.dll`

## pseudocode

```c
_BOOL8 __fastcall CContactRichPreview::RegisterWindowClass(HINSTANCE a1)
{
  ATOM v2; // bx
  WNDCLASSEXW v4; // [rsp+20h] [rbp-58h] BYREF

  hInstance = a1;
  memset_0(&v4, 0, sizeof(v4));
  v4.cbSize = 80;
  v4.lpfnWndProc = (WNDPROC)CContactRichPreview::_StaticWndProc;
  v4.style = 0x4000;
  v4.hInstance = a1;
  v4.hCursor = LoadCursorW(0, (LPCWSTR)0x7F00);
  v4.hbrBackground = GetSysColorBrush(5);
  v4.lpszClassName = L"Contact Rich Preview Window";
  v2 = RegisterClassExW(&v4);
  hLibModule = LoadLibraryW(L"msftedit.dll");
  if ( (unsigned int)IsBiDiLocalizedSystem() )
    off_1800A9870 = L"\\par\\rtlpar\n";
  return v2 && hLibModule;
}

```

## disassembly

```asm
0x180038bd4  push    rbx
0x180038bd6  sub     rsp, 70h
0x180038bda  xor     edx, edx; Val
0x180038bdc  mov     cs:hInstance, rcx
0x180038be3  mov     rbx, rcx
0x180038be6  lea     rcx, [rsp+78h+var_58]; void *
0x180038beb  lea     r8d, [rdx+50h]; Size
0x180038bef  call    memset_0
0x180038bf4  lea     rax, ?_StaticWndProc@CContactRichPreview@@CA_JPEAUHWND__@@I_K_J@Z; CContactRichPreview::_StaticWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180038bfb  mov     [rsp+78h+var_58.cbSize], 50h ; 'P'
0x180038c03  mov     edx, 7F00h; lpCursorName
0x180038c08  mov     [rsp+78h+var_58.lpfnWndProc], rax
0x180038c0d  xor     ecx, ecx; hInstance
0x180038c0f  mov     [rsp+78h+var_58.style], 4000h
0x180038c17  mov     [rsp+78h+var_58.hInstance], rbx
0x180038c1c  call    cs:__imp_LoadCursorW
0x180038c22  mov     ecx, 5; nIndex
0x180038c27  mov     [rsp+78h+var_58.hCursor], rax
0x180038c2c  call    cs:__imp_GetSysColorBrush
0x180038c32  mov     [rsp+78h+var_58.hbrBackground], rax
0x180038c37  lea     rcx, [rsp+78h+var_58]; WNDCLASSEXW *
0x180038c3c  lea     rax, aContactRichPre; "Contact Rich Preview Window"
0x180038c43  mov     [rsp+78h+var_58.lpszClassName], rax
0x180038c48  call    cs:__imp_RegisterClassExW
0x180038c4e  lea     rcx, aMsfteditDll; "msftedit.dll"
0x180038c55  movzx   ebx, ax
0x180038c58  call    cs:__imp_LoadLibraryW
0x180038c5e  mov     cs:hLibModule, rax
0x180038c65  call    IsBiDiLocalizedSystem
0x180038c6a  test    eax, eax
0x180038c6c  jz      short loc_180038C7C
0x180038c6e  lea     rax, aParRtlpar; "\\par\\rtlpar\n"
0x180038c75  mov     cs:off_1800A9870, rax; "\\par\n"
0x180038c7c  xor     ecx, ecx
0x180038c7e  cmp     cx, bx
0x180038c81  jz      short loc_180038C91
0x180038c83  cmp     cs:hLibModule, rcx
0x180038c8a  jz      short loc_180038C91
0x180038c8c  lea     eax, [rcx+1]
0x180038c8f  jmp     short loc_180038C93
0x180038c91  xor     eax, eax
0x180038c93  add     rsp, 70h
0x180038c97  pop     rbx
0x180038c98  retn
```
