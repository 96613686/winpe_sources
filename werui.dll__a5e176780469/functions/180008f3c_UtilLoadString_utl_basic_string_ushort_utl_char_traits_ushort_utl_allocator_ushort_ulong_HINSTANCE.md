# UtilLoadString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ulong,HINSTANCE__ *)

- ea: `0x180008f3c`
- end: `0x180008fb2`
- name: `?UtilLoadString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@KPEAUHINSTANCE__@@@Z`
- size: `118`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `20`
- callee_count: `2`
- tags: ``

## callers

- `0x180005fec`
- `0x180006440`
- `0x18000765c`
- `0x180007e50`
- `0x1800080d8`
- `0x1800083c0`
- `0x1800084b8`
- `0x180008528`
- `0x180008668`
- `0x18000899c`
- `0x180009b74`
- `0x18000a238`
- `0x18000cbc8`
- `0x18000d4c0`
- `0x18000d6b8`
- `0x18000e18c`
- `0x18000e440`
- `0x18000e6a4`
- `0x18000ea8c`
- `0x18000fc94`

## callees

- `0x180008f3c`
- `0x1800096d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008f6b`
- `KERNEL32!GetLastError` at `0x180008f6b`
- `USER32!LoadStringW` at `0x180008f61`
- `USER32!LoadStringW` at `0x180008f61`

## pseudocode

```c
__int64 __fastcall UtilLoadString(__int64 a1, UINT a2)
{
  signed int LastError; // eax
  unsigned int v4; // edx
  _WORD *v5; // rcx
  __int64 Buffer; // [rsp+40h] [rbp+18h] BYREF

  Buffer = 0;
  if ( LoadStringW(&_ImageBase, a2, (LPWSTR)&Buffer, 0) )
  {
    return (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                              a1,
                              Buffer) == 0
         ? 0x8007000E
         : 0;
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v5 = *(_WORD **)a1;
    *(_QWORD *)(a1 + 8) = *(_QWORD *)a1;
    *v5 = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180008f3c  mov     [rsp+Buffer], r8
0x180008f41  push    rbx
0x180008f42  sub     rsp, 20h
0x180008f46  mov     rbx, rcx
0x180008f49  mov     [rsp+28h+Buffer], 0
0x180008f52  lea     rcx, __ImageBase; hInstance
0x180008f59  xor     r9d, r9d; cchBufferMax
0x180008f5c  lea     r8, [rsp+28h+Buffer]; lpBuffer
0x180008f61  call    cs:__imp_LoadStringW
0x180008f67  test    eax, eax
0x180008f69  jnz     short loc_180008F8E
0x180008f6b  call    cs:__imp_GetLastError
0x180008f71  mov     edx, eax
0x180008f73  test    eax, eax
0x180008f75  jle     short loc_180008F80
0x180008f77  movzx   edx, ax
0x180008f7a  or      edx, 80070000h
0x180008f80  mov     rcx, [rbx]
0x180008f83  xor     eax, eax
0x180008f85  mov     [rbx+8], rcx
0x180008f89  mov     [rcx], ax
0x180008f8c  jmp     short loc_180008FAA
0x180008f8e  mov     rdx, [rsp+28h+Buffer]
0x180008f93  mov     rcx, rbx
0x180008f96  mov     r8d, eax
0x180008f99  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180008f9e  neg     al
0x180008fa0  sbb     edx, edx
0x180008fa2  not     edx
0x180008fa4  and     edx, 8007000Eh
0x180008faa  mov     eax, edx
0x180008fac  add     rsp, 20h
0x180008fb0  pop     rbx
0x180008fb1  retn
```
