# VmbusPipeServerConnectPipeInternal(void *,_OVERLAPPED *,bool *)

- ea: `0x1800076d0`
- end: `0x18000776c`
- name: `?VmbusPipeServerConnectPipeInternal@@YAJPEAXPEAU_OVERLAPPED@@PEA_N@Z`
- size: `156`
- prototype: `__int64 __fastcall(void *, struct _OVERLAPPED *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800077d0`

## callees

- `0x1800024e0`
- `0x180005d94`
- `0x1800076d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007723`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180007719`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180007719`

## string_xrefs

- `0x18000773e`: `onecore\vm\dv\vmbus\pipes\dll\server.cpp`

## pseudocode

```c
int __fastcall VmbusPipeServerConnectPipeInternal(void *a1, struct _OVERLAPPED *a2, bool *a3)
{
  DWORD LastError; // eax
  unsigned int v6; // [rsp+20h] [rbp-38h]
  DWORD v7; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v7 = 0;
  if ( DeviceIoControl(a1, 0x22C01Cu, 0, 0, 0, 0, &v7, a2) )
  {
    *a3 = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 535 )
    {
      *a3 = 1;
    }
    else if ( LastError )
    {
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x14F,
               (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\server.cpp",
               (const char *)LastError,
               v6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800076d0  mov     r11, rsp
0x1800076d3  push    rbx
0x1800076d4  sub     rsp, 50h
0x1800076d8  mov     rax, cs:__security_cookie
0x1800076df  xor     rax, rsp
0x1800076e2  mov     [rsp+58h+var_10], rax
0x1800076e7  mov     [r11-20h], rdx
0x1800076eb  lea     rax, [r11-18h]
0x1800076ef  mov     [r11-28h], rax
0x1800076f3  mov     rbx, r8
0x1800076f6  mov     [rsp+58h+nOutBufferSize], 0; nOutBufferSize
0x1800076fe  xor     r9d, r9d; nInBufferSize
0x180007701  xor     r8d, r8d; lpInBuffer
0x180007704  mov     qword ptr [r11-38h], 0
0x18000770c  mov     edx, 22C01Ch; dwIoControlCode
0x180007711  mov     [rsp+58h+var_18], 0
0x180007719  call    cs:__imp_DeviceIoControl
0x18000771f  test    eax, eax
0x180007721  jnz     short loc_180007754
0x180007723  call    cs:__imp_GetLastError
0x180007729  cmp     eax, 217h
0x18000772e  jnz     short loc_180007735
0x180007730  mov     byte ptr [rbx], 1
0x180007733  jmp     short loc_180007757
0x180007735  test    eax, eax
0x180007737  jz      short loc_180007757
0x180007739  mov     rcx, [rsp+58h]; this
0x18000773e  lea     r8, aOnecoreVmDvVmb_0; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\ser"...
0x180007745  mov     r9d, eax; char *
0x180007748  mov     edx, 14Fh; void *
0x18000774d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180007752  jmp     short loc_180007759
0x180007754  mov     byte ptr [rbx], 0
0x180007757  xor     eax, eax
0x180007759  mov     rcx, [rsp+58h+var_10]
0x18000775e  xor     rcx, rsp; StackCookie
0x180007761  call    __security_check_cookie
0x180007766  add     rsp, 50h
0x18000776a  pop     rbx
0x18000776b  retn
```
