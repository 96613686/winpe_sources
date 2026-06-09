# WString::InternalFree(ushort * &)

- ea: `0x14000dea0`
- end: `0x14000ded8`
- name: `?InternalFree@WString@@IEBAXAEAPEAG@Z`
- size: `56`
- prototype: `void(WString *__hidden this, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d978`
- `0x14000da00`
- `0x14000dee0`
- `0x14000e078`

## callees

- `0x14000db3c`
- `0x14000dea0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000deb7`
- `OLEAUT32!__imp_SysFreeString` at `0x14000deb7`

## pseudocode

```c
void __fastcall WString::InternalFree(WString *this, unsigned __int16 **a2)
{
  if ( (*((_BYTE *)this + 12) & 4) != 0 )
  {
    if ( *a2 )
    {
      SysFreeString(*a2);
      *a2 = 0;
    }
  }
  else
  {
    WString::FreeString(a2);
  }
}

```

## disassembly

```asm
0x14000dea0  push    rbx
0x14000dea2  sub     rsp, 20h
0x14000dea6  test    byte ptr [rcx+0Ch], 4
0x14000deaa  mov     rbx, rdx
0x14000dead  jz      short loc_14000DECA
0x14000deaf  mov     rcx, [rdx]; bstrString
0x14000deb2  test    rcx, rcx
0x14000deb5  jz      short loc_14000DED2
0x14000deb7  call    cs:__imp_SysFreeString
0x14000debd  mov     qword ptr [rbx], 0
0x14000dec4  add     rsp, 20h
0x14000dec8  pop     rbx
0x14000dec9  retn
0x14000deca  mov     rcx, rbx; unsigned __int16 **
0x14000decd  call    ?FreeString@WString@@SAXAEAPEAG@Z; WString::FreeString(ushort * &)
0x14000ded2  add     rsp, 20h
0x14000ded6  pop     rbx
0x14000ded7  retn
```
