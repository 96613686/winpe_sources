# DirectUI::NativeHWNDHost::CreateHostWindow(ulong,ushort const *,ushort const *,ulong,int,int,int,int,HWND__ *,HMENU__ *,HINSTANCE__ *,void *)

- ea: `0x180003b70`
- end: `0x180003b76`
- name: `?CreateHostWindow@NativeHWNDHost@DirectUI@@UEAAPEAUHWND__@@KPEBG0KHHHHPEAU3@PEAUHMENU__@@PEAUHINSTANCE__@@PEAX@Z_0`
- size: `6`
- prototype: `HWND __fastcall(DirectUI::NativeHWNDHost *this, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned int, int, int, int, int, HWND, HMENU, HINSTANCE, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `DUI70!?CreateHostWindow@NativeHWNDHost@DirectUI@@UEAAPEAUHWND__@@KPEBG0KHHHHPEAU3@PEAUHMENU__@@PEAUHINSTANCE__@@PEAX@Z` at `0x180003b70`

## pseudocode

```c
// attributes: thunk
HWND __fastcall DirectUI::NativeHWNDHost::CreateHostWindow(
        DirectUI::NativeHWNDHost *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        HWND a10,
        HMENU a11,
        HINSTANCE a12,
        void *a13)
{
  return __imp_?CreateHostWindow@NativeHWNDHost@DirectUI@@UEAAPEAUHWND__@@KPEBG0KHHHHPEAU3@PEAUHMENU__@@PEAUHINSTANCE__@@PEAX@Z(
           this,
           a2,
           a3,
           a4,
           a5,
           a6,
           a7,
           a8,
           a9,
           a10,
           a11,
           a12,
           a13);
}

```

## disassembly

```asm
0x180003b70  jmp     cs:__imp_?CreateHostWindow@NativeHWNDHost@DirectUI@@UEAAPEAUHWND__@@KPEBG0KHHHHPEAU3@PEAUHMENU__@@PEAUHINSTANCE__@@PEAX@Z
```
