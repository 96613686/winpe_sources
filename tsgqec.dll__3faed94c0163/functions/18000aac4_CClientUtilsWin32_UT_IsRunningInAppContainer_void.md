# CClientUtilsWin32::UT_IsRunningInAppContainer(void)

- ea: `0x18000aac4`
- end: `0x18000aaf5`
- name: `?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ`
- size: `49`
- prototype: `__int64(void)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007180`
- `0x180007430`
- `0x180007820`
- `0x180008990`
- `0x180008ea0`
- `0x180009170`
- `0x180009380`
- `0x180009960`
- `0x180009bc0`
- `0x18000a090`
- `0x18000a250`

## callees

- `0x180005a30`
- `0x18000aac4`

## pseudocode

```c
__int64 CClientUtilsWin32::UT_IsRunningInAppContainer(void)
{
  __int64 result; // rax

  if ( CClientUtilsWin32::_utRunningInAppContainer )
    return CClientUtilsWin32::_utRunningInAppContainer == 1;
  result = PAL_System_Win32_IsRunningInAppContainer();
  CClientUtilsWin32::_utRunningInAppContainer = 2 - ((_DWORD)result != 0);
  return result;
}

```

## disassembly

```asm
0x18000aac4  sub     rsp, 28h
0x18000aac8  mov     ecx, cs:?_utRunningInAppContainer@CClientUtilsWin32@@1W4UT_APPCONTAINER_CHECK_STATE@@A; UT_APPCONTAINER_CHECK_STATE CClientUtilsWin32::_utRunningInAppContainer
0x18000aace  test    ecx, ecx
0x18000aad0  jz      short loc_18000AADC
0x18000aad2  xor     eax, eax
0x18000aad4  cmp     ecx, 1
0x18000aad7  setz    al
0x18000aada  jmp     short loc_18000AAF0
0x18000aadc  call    ?PAL_System_Win32_IsRunningInAppContainer@@YAHXZ; PAL_System_Win32_IsRunningInAppContainer(void)
0x18000aae1  mov     ecx, eax
0x18000aae3  neg     ecx
0x18000aae5  sbb     edx, edx
0x18000aae7  add     edx, 2
0x18000aaea  mov     cs:?_utRunningInAppContainer@CClientUtilsWin32@@1W4UT_APPCONTAINER_CHECK_STATE@@A, edx; UT_APPCONTAINER_CHECK_STATE CClientUtilsWin32::_utRunningInAppContainer
0x18000aaf0  add     rsp, 28h
0x18000aaf4  retn
```
