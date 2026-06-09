# wil::unique_any_array_ptr<char *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>,unsigned __int64>::size_address_ptr<ulong>::~size_address_ptr<ulong>(void)

- ea: `0x180007064`
- end: `0x180007075`
- name: `??1?$size_address_ptr@K@?$unique_any_array_ptr@PEADU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ`
- size: `17`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18000bfe7`

## callees

- `0x180007064`

## pseudocode

```c
__int64 __fastcall wil::unique_any_array_ptr<char *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>,unsigned __int64>::size_address_ptr<unsigned long>::~size_address_ptr<unsigned long>(
        __int64 *a1)
{
  __int64 result; // rax

  if ( *((_BYTE *)a1 + 12) )
  {
    result = *a1;
    *(_QWORD *)(*a1 + 8) = *((unsigned int *)a1 + 2);
  }
  return result;
}

```

## disassembly

```asm
0x180007064  cmp     byte ptr [rcx+0Ch], 0
0x180007068  jz      short locret_180007074
0x18000706a  mov     rax, [rcx]
0x18000706d  mov     edx, [rcx+8]
0x180007070  mov     [rax+8], rdx
0x180007074  retn
```
