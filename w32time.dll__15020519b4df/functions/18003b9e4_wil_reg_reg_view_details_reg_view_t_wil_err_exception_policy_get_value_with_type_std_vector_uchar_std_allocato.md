# wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::get_value_with_type<std::vector<uchar,std::allocator<uchar>>,wil::err_exception_policy>(ushort const *,ushort const *,std::vector<uchar,std::allocator<uchar>> &,ulong)

- ea: `0x18003b9e4`
- end: `0x18003baf4`
- name: `??$get_value_with_type@V?$vector@EV?$allocator@E@std@@@std@@Uerr_exception_policy@wil@@@?$reg_view_t@Uerr_exception_policy@wil@@@reg_view_details@reg@wil@@AEBAXPEBG0AEAV?$vector@EV?$allocator@E@std@@@std@@K@Z`
- size: `272`
- prototype: `__int64 __fastcall(HKEY *, __int64, const WCHAR *, _DWORD *, DWORD pcbData)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180056b6c`

## callees

- `0x18003b9e4`
- `0x18003c810`
- `0x1800568e0`
- `0x180056bbc`
- `0x180056ce0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ba57`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ba57`

## string_xrefs

- `0x18003ba47`: `System\CurrentControlSet\Services\W32Time\TimeProviders\NtpClient\Nts`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::get_value_with_type<std::vector<unsigned char>,wil::err_exception_policy>(
        HKEY *a1,
        __int64 a2,
        const WCHAR *a3,
        _DWORD *a4,
        DWORD pcbData)
{
  int v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  DWORD v11; // edx
  DWORD value_flags_from_value_type; // edi
  HKEY v13; // rcx
  int ValueW; // eax
  void *v15; // rdx
  unsigned int v16; // r8d
  __int64 v17; // rdx
  __int64 result; // rax
  void *v19; // rdx
  unsigned int v20; // r8d
  int v21; // eax
  void *v22; // rdx
  unsigned int v23; // r8d
  int pdwType; // [rsp+20h] [rbp-48h]
  int pdwTypea; // [rsp+20h] [rbp-48h]
  PVOID pvData; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v8 = wil::reg::reg_view_details::reg_value_type_info::prepare_buffer(a4);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, v9, v10, (const char *)(unsigned int)v8, pdwType);
  value_flags_from_value_type = wil::reg::reg_view_details::get_value_flags_from_value_type(
                                  (wil::reg::reg_view_details *)7,
                                  a4[2] - *a4);
  while ( 1 )
  {
    pvData = *(PVOID *)a4;
    v13 = *a1;
    pcbData = v11;
    ValueW = RegGetValueW(
               v13,
               L"System\\CurrentControlSet\\Services\\W32Time\\TimeProviders\\NtpClient\\Nts",
               a3,
               value_flags_from_value_type,
               0,
               pvData,
               &pcbData);
    if ( ValueW > 0 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    if ( ValueW == -2147024662 )
    {
      v17 = pcbData;
      goto LABEL_14;
    }
    if ( ValueW < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, v15, v16, (const char *)(unsigned int)ValueW, pdwTypea);
    v17 = pcbData;
    if ( *(_QWORD *)a4 || !pcbData )
      break;
LABEL_14:
    v21 = wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(a4, v17);
    if ( v21 < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, v22, v23, (const char *)(unsigned int)v21, pdwTypea);
    v11 = pcbData;
  }
  result = (unsigned int)(a4[2] - *a4);
  if ( (_DWORD)result != pcbData )
  {
    result = wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(a4, pcbData);
    if ( (int)result < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, v19, v20, (const char *)(unsigned int)result, pdwTypea);
  }
  return result;
}

```

## disassembly

```asm
0x18003b9e4  push    rbx
0x18003b9e6  push    rsi
0x18003b9e7  push    rdi
0x18003b9e8  push    r14
0x18003b9ea  sub     rsp, 48h
0x18003b9ee  mov     r14, rcx
0x18003b9f1  mov     rbx, r9
0x18003b9f4  mov     rcx, r9
0x18003b9f7  mov     rsi, r8
0x18003b9fa  call    ?prepare_buffer@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; wil::reg::reg_view_details::reg_value_type_info::prepare_buffer(std::vector<uchar> &)
0x18003b9ff  test    eax, eax
0x18003ba01  jns     short loc_18003BA11
0x18003ba03  mov     rcx, [rsp+68h]; this
0x18003ba08  mov     r9d, eax; char *
0x18003ba0b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003ba11  mov     edx, [rbx+8]
0x18003ba14  mov     ecx, 7; this
0x18003ba19  sub     edx, [rbx]; unsigned int
0x18003ba1b  call    ?get_value_flags_from_value_type@reg_view_details@reg@wil@@YAKK@Z; wil::reg::reg_view_details::get_value_flags_from_value_type(ulong)
0x18003ba20  mov     edi, eax
0x18003ba22  mov     rcx, [rbx]
0x18003ba25  lea     rax, [rsp+68h+arg_20]
0x18003ba2d  mov     [rsp+68h+pcbData], rax; pcbData
0x18003ba32  mov     r9d, edi; dwFlags
0x18003ba35  mov     [rsp+68h+pvData], rcx; pvData
0x18003ba3a  mov     r8, rsi; lpValue
0x18003ba3d  mov     rcx, [r14]; hkey
0x18003ba40  mov     [rsp+68h+arg_20], edx
0x18003ba47  lea     rdx, aSystemCurrentc_10; "System\\CurrentControlSet\\Services\\W3"...
0x18003ba4e  mov     [rsp+68h+pdwType], 0; int
0x18003ba57  call    cs:__imp_RegGetValueW
0x18003ba5e  nop     dword ptr [rax+rax+00h]
0x18003ba63  test    eax, eax
0x18003ba65  jle     short loc_18003BA6F
0x18003ba67  movzx   eax, ax
0x18003ba6a  or      eax, 80070000h
0x18003ba6f  cmp     eax, 800700EAh
0x18003ba74  jz      short loc_18003BAAE
0x18003ba76  test    eax, eax
0x18003ba78  js      short loc_18003BACD
0x18003ba7a  cmp     qword ptr [rbx], 0
0x18003ba7e  mov     edx, [rsp+68h+arg_20]
0x18003ba85  jnz     short loc_18003BA8B
0x18003ba87  test    edx, edx
0x18003ba89  jnz     short loc_18003BAB5
0x18003ba8b  mov     eax, [rbx+8]
0x18003ba8e  sub     eax, [rbx]
0x18003ba90  cmp     eax, edx
0x18003ba92  jz      short loc_18003BAE9
0x18003ba94  mov     rcx, rbx
0x18003ba97  call    ?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$vector@EV?$allocator@E@std@@@std@@K@Z; wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(std::vector<uchar> &,ulong)
0x18003ba9c  test    eax, eax
0x18003ba9e  jns     short loc_18003BAE9
0x18003baa0  mov     rcx, [rsp+68h]; this
0x18003baa5  mov     r9d, eax; char *
0x18003baa8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003baae  mov     edx, [rsp+68h+arg_20]
0x18003bab5  mov     rcx, rbx
0x18003bab8  call    ?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$vector@EV?$allocator@E@std@@@std@@K@Z; wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(std::vector<uchar> &,ulong)
0x18003babd  test    eax, eax
0x18003babf  js      short loc_18003BADB
0x18003bac1  mov     edx, [rsp+68h+arg_20]
0x18003bac8  jmp     loc_18003BA22
0x18003bacd  mov     rcx, [rsp+68h]; this
0x18003bad2  mov     r9d, eax; char *
0x18003bad5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003badb  mov     rcx, [rsp+68h]; this
0x18003bae0  mov     r9d, eax; char *
0x18003bae3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003bae9  add     rsp, 48h
0x18003baed  pop     r14
0x18003baef  pop     rdi
0x18003baf0  pop     rsi
0x18003baf1  pop     rbx
0x18003baf2  retn
```
