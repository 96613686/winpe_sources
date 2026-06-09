# UtilLoadModFromSystem(ushort const *)

- ea: `0x180008ec8`
- end: `0x180008f36`
- name: `?UtilLoadModFromSystem@@YA?AV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEBG@Z`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180006bdc`
- `0x18000c268`

## callees

- `0x180005c80`
- `0x180008dfc`
- `0x180008ec8`
- `0x180009580`
- `0x1800095a8`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180008f0c`
- `KERNEL32!LoadLibraryExW` at `0x180008f0c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HMODULE *__fastcall UtilLoadModFromSystem(HMODULE *a1, __int64 a2)
{
  LPCWSTR lpLibFileName[6]; // [rsp+28h] [rbp-30h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpLibFileName);
  if ( (int)UtilGetSystemDirectory2((__int64)lpLibFileName) >= 0
    && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                          lpLibFileName,
                          a2) )
  {
    *a1 = LoadLibraryExW(lpLibFileName[0], 0, 0);
  }
  else
  {
    *a1 = 0;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpLibFileName);
  return a1;
}

```

## disassembly

```asm
0x180008ec8  mov     [rsp+arg_0], rbx
0x180008ecd  push    rdi
0x180008ece  sub     rsp, 50h
0x180008ed2  mov     rdi, rdx
0x180008ed5  mov     rbx, rcx
0x180008ed8  lea     rcx, [rsp+58h+lpLibFileName]; void *
0x180008edd  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x180008ee2  nop
0x180008ee3  lea     rcx, [rsp+58h+lpLibFileName]
0x180008ee8  call    ?UtilGetSystemDirectory2@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@G_N@Z; UtilGetSystemDirectory2(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort,bool)
0x180008eed  test    eax, eax
0x180008eef  js      short loc_180008F17
0x180008ef1  mov     rdx, rdi
0x180008ef4  lea     rcx, [rsp+58h+lpLibFileName]
0x180008ef9  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180008efe  test    al, al
0x180008f00  jz      short loc_180008F17
0x180008f02  xor     r8d, r8d; dwFlags
0x180008f05  xor     edx, edx; hFile
0x180008f07  mov     rcx, [rsp+58h+lpLibFileName]; lpLibFileName
0x180008f0c  call    cs:__imp_LoadLibraryExW
0x180008f12  mov     [rbx], rax
0x180008f15  jmp     short loc_180008F1E
0x180008f17  mov     qword ptr [rbx], 0
0x180008f1e  lea     rcx, [rsp+58h+lpLibFileName]
0x180008f23  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180008f28  mov     rax, rbx
0x180008f2b  mov     rbx, [rsp+58h+arg_0]
0x180008f30  add     rsp, 50h
0x180008f34  pop     rdi
0x180008f35  retn
```
