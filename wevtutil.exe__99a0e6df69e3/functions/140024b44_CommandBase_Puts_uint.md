# CommandBase::Puts(uint)

- ea: `0x140024b44`
- end: `0x140024c54`
- name: `?Puts@CommandBase@@IEAAXI@Z`
- size: `272`
- prototype: `void __fastcall(CommandBase *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400238ac`

## callees

- `0x140004ae0`
- `0x140005600`
- `0x14000d144`
- `0x14000d570`
- `0x140022cec`
- `0x140024b44`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140024b6c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140024b6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CommandBase::Puts(HANDLE *this, unsigned int a2)
{
  HMODULE ModuleHandleW; // rax
  int v5; // ebx
  _QWORD v6[2]; // [rsp+30h] [rbp-9h] BYREF
  _QWORD v7[4]; // [rsp+40h] [rbp+7h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+60h] [rbp+27h] BYREF
  int v9; // [rsp+78h] [rbp+3Fh]
  __int64 v10; // [rsp+7Ch] [rbp+43h]
  char v11; // [rsp+84h] [rbp+4Bh]

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v7);
  ModuleHandleW = GetModuleHandleW(0);
  v5 = tlx::_AppendFormatMessageImpl<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(
         v7,
         2560,
         ModuleHandleW,
         a2);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_268a439894343dd91cd92e0ef272a5e3_Traceguids,
        (unsigned int)v5);
    }
    pExceptionObject[0] = word_14003838A;
    pExceptionObject[1] = 0;
    pExceptionObject[2] = 0;
    v9 = v5;
    v10 = -1;
    v11 = 0;
    throw (EvtException *)pExceptionObject;
  }
  v6[0] = v7[0];
  v6[1] = (__int64)(v7[1] - v7[0]) >> 1;
  FilePuts(this[2], v6);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v7);
}

```

## disassembly

```asm
0x140024b44  mov     [rsp-8+arg_0], rbx
0x140024b49  mov     [rsp-8+arg_8], rdi
0x140024b4e  push    rbp
0x140024b4f  lea     rbp, [rsp-57h]
0x140024b54  sub     rsp, 90h
0x140024b5b  mov     ebx, edx
0x140024b5d  mov     rdi, rcx
0x140024b60  lea     rcx, [rbp+57h+var_50]
0x140024b64  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140024b69  nop
0x140024b6a  xor     ecx, ecx; lpModuleName
0x140024b6c  call    cs:__imp_GetModuleHandleW
0x140024b72  mov     [rsp+90h+var_68], 0
0x140024b7b  mov     [rsp+90h+var_70], 0
0x140024b83  mov     r9d, ebx
0x140024b86  mov     r8, rax
0x140024b89  mov     edx, 0A00h
0x140024b8e  lea     rcx, [rbp+57h+var_50]
0x140024b92  call    ??$_AppendFormatMessageImpl@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@IPEBXIIPEAPEAD@Z; tlx::_AppendFormatMessageImpl<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,uint,void const *,uint,uint,char * *)
0x140024b97  mov     ebx, eax
0x140024b99  test    eax, eax
0x140024b9b  jns     short loc_140024C12
0x140024b9d  lea     rax, WPP_GLOBAL_Control
0x140024ba4  mov     rcx, cs:WPP_GLOBAL_Control
0x140024bab  cmp     rcx, rax
0x140024bae  jz      short loc_140024BD7
0x140024bb0  test    dword ptr [rcx+1Ch], 400000h
0x140024bb7  jz      short loc_140024BD7
0x140024bb9  cmp     byte ptr [rcx+19h], 2
0x140024bbd  jb      short loc_140024BD7
0x140024bbf  mov     edx, 0Ah
0x140024bc4  mov     r9d, ebx
0x140024bc7  lea     r8, WPP_268a439894343dd91cd92e0ef272a5e3_Traceguids
0x140024bce  mov     rcx, [rcx+10h]
0x140024bd2  call    WPP_SF_d
0x140024bd7  lea     rax, word_14003838A
0x140024bde  mov     [rbp+57h+pExceptionObject], rax
0x140024be2  mov     [rbp+57h+var_28], 0
0x140024bea  mov     [rbp+57h+var_20], 0
0x140024bf2  mov     [rbp+57h+var_18], ebx
0x140024bf5  mov     [rbp+57h+var_14], 0FFFFFFFFFFFFFFFFh
0x140024bfd  mov     [rbp+57h+var_C], 0
0x140024c01  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140024c08  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140024c0c  call    _CxxThrowException_0
0x140024c12  mov     rax, [rbp+57h+var_50]
0x140024c16  mov     [rbp+57h+var_60], rax
0x140024c1a  mov     rcx, [rbp+57h+var_48]
0x140024c1e  sub     rcx, rax
0x140024c21  sar     rcx, 1
0x140024c24  mov     [rbp+57h+var_58], rcx
0x140024c28  lea     rdx, [rbp+57h+var_60]
0x140024c2c  mov     rcx, [rdi+10h]; hFile
0x140024c30  call    ?FilePuts@@YAJPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; FilePuts(void *,std::wstring_view)
0x140024c35  nop
0x140024c36  lea     rcx, [rbp+57h+var_50]
0x140024c3a  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140024c3f  lea     r11, [rsp+90h+var_s0]
0x140024c47  mov     rbx, [r11+10h]
0x140024c4b  mov     rdi, [r11+18h]
0x140024c4f  mov     rsp, r11
0x140024c52  pop     rbp
0x140024c53  retn
```
