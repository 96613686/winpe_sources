# CreateTheCancelEvent(void * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001ca88`
- end: `0x18001cb14`
- name: `?CreateTheCancelEvent@@YAJAEAPEAXAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z`
- size: `140`
- prototype: `signed int __fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012af0`
- `0x180020ad0`

## callees

- `0x18001ca88`
- `0x18001cbe0`
- `0x18001cc2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001cae5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001cae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001caf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001caf3`

## pseudocode

```c
signed int __fastcall CreateTheCancelEvent(_QWORD *a1, __int64 a2)
{
  signed int result; // eax
  HANDLE v5; // rax
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+20h] [rbp-28h] BYREF

  if ( (unsigned int)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::UuidCreate(a2) )
    return -2147024888;
  *(_QWORD *)&EventAttributes.nLength = 24;
  *(_QWORD *)&EventAttributes.bInheritHandle = 1;
  EventAttributes.lpSecurityDescriptor = 0;
  result = SetAdminRights(&EventAttributes);
  if ( result >= 0 )
  {
    v5 = CreateEventW(&EventAttributes, 0, 0, *(LPCWSTR *)(*(_QWORD *)a2 + 24LL));
    *a1 = v5;
    if ( v5 )
    {
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001ca88  mov     [rsp+arg_0], rbx
0x18001ca8d  push    rdi
0x18001ca8e  sub     rsp, 40h
0x18001ca92  mov     rdi, rcx
0x18001ca95  mov     rbx, rdx
0x18001ca98  mov     rcx, rdx
0x18001ca9b  call    ?UuidCreate@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAJXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::UuidCreate(void)
0x18001caa0  test    eax, eax
0x18001caa2  jz      short loc_18001CAAB
0x18001caa4  mov     eax, 80070008h
0x18001caa9  jmp     short loc_18001CB09
0x18001caab  lea     rcx, [rsp+48h+EventAttributes]
0x18001cab0  mov     qword ptr [rsp+48h+EventAttributes.nLength], 18h
0x18001cab9  mov     qword ptr [rsp+48h+EventAttributes.bInheritHandle], 1
0x18001cac2  mov     [rsp+48h+EventAttributes.lpSecurityDescriptor], 0
0x18001cacb  call    SetAdminRights
0x18001cad0  test    eax, eax
0x18001cad2  js      short loc_18001CB09
0x18001cad4  mov     r9, [rbx]
0x18001cad7  lea     rcx, [rsp+48h+EventAttributes]; lpEventAttributes
0x18001cadc  xor     r8d, r8d; bInitialState
0x18001cadf  xor     edx, edx; bManualReset
0x18001cae1  mov     r9, [r9+18h]; lpName
0x18001cae5  call    cs:__imp_CreateEventW
0x18001caeb  mov     [rdi], rax
0x18001caee  test    rax, rax
0x18001caf1  jnz     short loc_18001CB07
0x18001caf3  call    cs:__imp_GetLastError
0x18001caf9  test    eax, eax
0x18001cafb  jle     short loc_18001CB09
0x18001cafd  movzx   eax, ax
0x18001cb00  or      eax, 80070000h
0x18001cb05  jmp     short loc_18001CB09
0x18001cb07  xor     eax, eax
0x18001cb09  mov     rbx, [rsp+48h+arg_0]
0x18001cb0e  add     rsp, 40h
0x18001cb12  pop     rdi
0x18001cb13  retn
```
