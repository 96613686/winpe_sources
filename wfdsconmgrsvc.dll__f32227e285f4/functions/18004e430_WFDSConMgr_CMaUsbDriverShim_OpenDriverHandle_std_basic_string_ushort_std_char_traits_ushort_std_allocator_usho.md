# WFDSConMgr::CMaUsbDriverShim::OpenDriverHandle(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void * *)

- ea: `0x18004e430`
- end: `0x18004e499`
- name: `?OpenDriverHandle@CMaUsbDriverShim@WFDSConMgr@@UEBAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAX@Z`
- size: `105`
- prototype: `DWORD __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18000665c`
- `0x18004e430`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e487`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004e473`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004e473`

## pseudocode

```c
DWORD __fastcall WFDSConMgr::CMaUsbDriverShim::OpenDriverHandle(__int64 a1, __int64 a2, _QWORD *a3)
{
  DWORD result; // eax
  const WCHAR *v5; // rax
  HANDLE FileW; // rcx

  if ( !a3 )
    return 87;
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  FileW = CreateFileW(v5, 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  result = 0;
  *a3 = FileW;
  return result;
}

```

## disassembly

```asm
0x18004e430  push    rbx
0x18004e432  sub     rsp, 40h
0x18004e436  mov     rbx, r8
0x18004e439  test    r8, r8
0x18004e43c  jnz     short loc_18004E444
0x18004e43e  lea     eax, [r8+57h]
0x18004e442  jmp     short loc_18004E493
0x18004e444  mov     rcx, rdx
0x18004e447  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004e44c  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18004e455  mov     r8d, 3; dwShareMode
0x18004e45b  mov     [rsp+48h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18004e463  mov     rcx, rax; lpFileName
0x18004e466  xor     r9d, r9d; lpSecurityAttributes
0x18004e469  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x18004e46e  mov     edx, 0C0000000h; dwDesiredAccess
0x18004e473  call    cs:__imp_CreateFileW
0x18004e479  mov     rcx, rax
0x18004e47c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004e480  jnz     short loc_18004E48E
0x18004e482  add     rsp, 40h
0x18004e486  pop     rbx
0x18004e487  jmp     cs:__imp_GetLastError
0x18004e48e  xor     eax, eax
0x18004e490  mov     [rbx], rcx
0x18004e493  add     rsp, 40h
0x18004e497  pop     rbx
0x18004e498  retn
```
