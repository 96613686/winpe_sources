# wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>(void)

- ea: `0x140004d6c`
- end: `0x140004dd4`
- name: `??1?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ`
- size: `104`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400075b0`
- `0x14000db50`

## callees

- `0x140004d6c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140004d8f`
- `KERNEL32!GetLastError` at `0x140004d8f`
- `KERNEL32!SetLastError` at `0x140004da2`
- `KERNEL32!SetLastError` at `0x140004da2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004d9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004db4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004d9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004db4`

## pseudocode

```c
void __fastcall wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>(
        __int64 a1)
{
  void **v1; // r14
  void **v3; // rbp
  void *v4; // rbx
  DWORD LastError; // edi

  v1 = *(void ***)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = &v1[*(_QWORD *)(a1 + 8)];
    while ( v1 != v3 )
    {
      v4 = *v1;
      LastError = GetLastError();
      CoTaskMemFree(v4);
      SetLastError(LastError);
      ++v1;
    }
    CoTaskMemFree(*(LPVOID *)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x140004d6c  push    rbx
0x140004d6e  push    rbp
0x140004d6f  push    rsi
0x140004d70  push    rdi
0x140004d71  push    r14
0x140004d73  sub     rsp, 20h
0x140004d77  mov     r14, [rcx]
0x140004d7a  mov     rsi, rcx
0x140004d7d  test    r14, r14
0x140004d80  jz      short loc_140004DC9
0x140004d82  mov     rax, [rcx+8]
0x140004d86  lea     rbp, [r14+rax*8]
0x140004d8a  jmp     short loc_140004DAC
0x140004d8c  mov     rbx, [r14]
0x140004d8f  call    cs:__imp_GetLastError
0x140004d95  mov     rcx, rbx; pv
0x140004d98  mov     edi, eax
0x140004d9a  call    cs:__imp_CoTaskMemFree
0x140004da0  mov     ecx, edi; dwErrCode
0x140004da2  call    cs:__imp_SetLastError
0x140004da8  add     r14, 8
0x140004dac  cmp     r14, rbp
0x140004daf  jnz     short loc_140004D8C
0x140004db1  mov     rcx, [rsi]; pv
0x140004db4  call    cs:__imp_CoTaskMemFree
0x140004dba  mov     qword ptr [rsi], 0
0x140004dc1  mov     qword ptr [rsi+8], 0
0x140004dc9  add     rsp, 20h
0x140004dcd  pop     r14
0x140004dcf  pop     rdi
0x140004dd0  pop     rsi
0x140004dd1  pop     rbp
0x140004dd2  pop     rbx
0x140004dd3  retn
```
