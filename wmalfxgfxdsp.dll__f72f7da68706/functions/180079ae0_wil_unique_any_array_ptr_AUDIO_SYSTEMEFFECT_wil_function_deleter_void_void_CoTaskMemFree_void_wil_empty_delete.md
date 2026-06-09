# wil::unique_any_array_ptr<AUDIO_SYSTEMEFFECT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::release(void)

- ea: `0x180079ae0`
- end: `0x180079af3`
- name: `?release@?$unique_any_array_ptr@UAUDIO_SYSTEMEFFECT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAPEAUAUDIO_SYSTEMEFFECT@@XZ`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x1800775a0`

## pseudocode

```c
__int64 __fastcall wil::unique_any_array_ptr<AUDIO_SYSTEMEFFECT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::release(
        __int64 *a1)
{
  __int64 result; // rax

  result = *a1;
  *a1 = 0;
  a1[1] = 0;
  return result;
}

```

## disassembly

```asm
0x180079ae0  mov     rax, [rcx]
0x180079ae3  mov     qword ptr [rcx], 0
0x180079aea  mov     qword ptr [rcx+8], 0
0x180079af2  retn
```
