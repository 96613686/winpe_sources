# HMEHelpers::CleanupWMPDeviceSettings(__MIDL___MIDL_itf_playerps_0000_0005_0004 *)

- ea: `0x1800166a0`
- end: `0x180016722`
- name: `?CleanupWMPDeviceSettings@HMEHelpers@@YAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z`
- size: `130`
- prototype: `__int64 __fastcall(HMEHelpers *__hidden this, struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180003ed0`
- `0x1800040a8`
- `0x180004ce8`
- `0x180004ff0`
- `0x18000638c`
- `0x180006bfc`
- `0x180006d34`
- `0x18000b380`
- `0x1800125c0`
- `0x180016d00`

## callees

- `0x1800166a0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180016702`
- `ole32!CoTaskMemFree` at `0x180016702`
- `OLEAUT32!__imp_SysFreeString` at `0x1800166cf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800166dd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800166eb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800166cf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800166dd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800166eb`

## pseudocode

```c
__int64 __fastcall HMEHelpers::CleanupWMPDeviceSettings(
        HMEHelpers *this,
        struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *a2)
{
  unsigned int v3; // ebp
  LPVOID *v4; // rdi
  int v5; // r14d
  __int64 v6; // rbx

  if ( this )
  {
    v3 = 0;
    v4 = (LPVOID *)((char *)this + 32);
    v5 = 0;
    if ( *((int *)this + 6) > 0 )
    {
      do
      {
        v6 = 32LL * v5;
        SysFreeString(*(BSTR *)((char *)*v4 + v6));
        SysFreeString(*(BSTR *)((char *)*v4 + v6 + 8));
        SysFreeString(*(BSTR *)((char *)*v4 + v6 + 16));
        ++v5;
      }
      while ( v5 < *((_DWORD *)this + 6) );
      if ( *((int *)this + 6) > 0 )
        CoTaskMemFree(*v4);
    }
    *v4 = 0;
    *((_DWORD *)this + 6) = 0;
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v3;
}

```

## disassembly

```asm
0x1800166a0  push    rbx
0x1800166a2  push    rbp
0x1800166a3  push    rsi
0x1800166a4  push    rdi
0x1800166a5  push    r14
0x1800166a7  sub     rsp, 20h
0x1800166ab  mov     rsi, rcx
0x1800166ae  test    rcx, rcx
0x1800166b1  jz      short loc_180016710
0x1800166b3  xor     ebp, ebp
0x1800166b5  lea     rdi, [rcx+20h]
0x1800166b9  xor     r14d, r14d
0x1800166bc  cmp     [rcx+18h], ebp
0x1800166bf  jle     short loc_180016708
0x1800166c1  mov     rcx, [rdi]
0x1800166c4  movsxd  rbx, r14d
0x1800166c7  shl     rbx, 5
0x1800166cb  mov     rcx, [rcx+rbx]; bstrString
0x1800166cf  call    cs:__imp_SysFreeString
0x1800166d5  mov     rcx, [rdi]
0x1800166d8  mov     rcx, [rcx+rbx+8]; bstrString
0x1800166dd  call    cs:__imp_SysFreeString
0x1800166e3  mov     rcx, [rdi]
0x1800166e6  mov     rcx, [rcx+rbx+10h]; bstrString
0x1800166eb  call    cs:__imp_SysFreeString
0x1800166f1  inc     r14d
0x1800166f4  cmp     r14d, [rsi+18h]
0x1800166f8  jl      short loc_1800166C1
0x1800166fa  cmp     [rsi+18h], ebp
0x1800166fd  jle     short loc_180016708
0x1800166ff  mov     rcx, [rdi]; pv
0x180016702  call    cs:__imp_CoTaskMemFree
0x180016708  mov     [rdi], rbp
0x18001670b  mov     [rsi+18h], ebp
0x18001670e  jmp     short loc_180016715
0x180016710  mov     ebp, 80004003h
0x180016715  mov     eax, ebp
0x180016717  add     rsp, 20h
0x18001671b  pop     r14
0x18001671d  pop     rdi
0x18001671e  pop     rsi
0x18001671f  pop     rbp
0x180016720  pop     rbx
0x180016721  retn
```
