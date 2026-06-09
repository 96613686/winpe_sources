# WPP_RECORDER_SF_qqL

- ea: `0x14000b8cc`
- end: `0x14000b9c8`
- name: `WPP_RECORDER_SF_qqL`
- size: `252`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140003d08`
- `0x140004078`
- `0x140005fc4`
- `0x14000b670`

## callees

- `0x14000b8cc`
- `0x140014d50`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000b949`
- `WppRecorder!WppAutoLogTrace` at `0x14000b949`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qqL(__int64 a1, _DWORD a2, _DWORD a3, unsigned __int16 a4, __int64 a5, ...)
{
  int v8; // [rsp+20h] [rbp-68h]
  __int64 v9; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  __int64 v11; // [rsp+C0h] [rbp+38h] BYREF
  va_list va1; // [rsp+C0h] [rbp+38h]
  va_list va2; // [rsp+C8h] [rbp+40h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v9 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v11 = va_arg(va2, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    pfnWppTraceMessage(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
      a4,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      8,
      va2,
      4,
      0);
  LOWORD(v8) = a4;
  return WppAutoLogTrace(a1, 4, 3, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids, v8, (__int64 *)va);
}

```

## disassembly

```asm
0x14000b8cc  push    rbx
0x14000b8ce  push    rbp
0x14000b8cf  push    rsi
0x14000b8d0  push    rdi
0x14000b8d1  sub     rsp, 68h
0x14000b8d5  mov     rdi, rcx
0x14000b8d8  movzx   ebx, r9w
0x14000b8dc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b8e3  mov     ebp, 8
0x14000b8e8  mov     eax, [rcx+2Ch]
0x14000b8eb  lea     esi, [rbp-4]
0x14000b8ee  test    sil, al
0x14000b8f1  jnz     short loc_14000B95F
0x14000b8f3  mov     [rsp+88h+var_30], 0
0x14000b8fc  lea     rax, [rsp+88h+arg_38]
0x14000b904  mov     [rsp+88h+var_38], rsi
0x14000b909  lea     r9, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x14000b910  mov     [rsp+88h+var_40], rax
0x14000b915  mov     r8d, 3
0x14000b91b  mov     [rsp+88h+var_48], rbp
0x14000b920  lea     rax, [rsp+88h+arg_30]
0x14000b928  mov     [rsp+88h+var_50], rax
0x14000b92d  mov     edx, esi
0x14000b92f  lea     rax, [rsp+88h+arg_28]
0x14000b937  mov     [rsp+88h+var_58], rbp
0x14000b93c  mov     [rsp+88h+var_60], rax
0x14000b941  mov     rcx, rdi
0x14000b944  mov     word ptr [rsp+88h+var_68], bx
0x14000b949  call    cs:__imp_WppAutoLogTrace
0x14000b950  nop     dword ptr [rax+rax+00h]
0x14000b955  add     rsp, 68h
0x14000b959  pop     rdi
0x14000b95a  pop     rsi
0x14000b95b  pop     rbp
0x14000b95c  pop     rbx
0x14000b95d  retn
0x14000b95f  cmp     [rcx+29h], sil
0x14000b963  jb      short loc_14000B8F3
0x14000b965  mov     rax, cs:pfnWppTraceMessage
0x14000b96c  lea     rdx, [rsp+88h+arg_38]
0x14000b974  mov     rcx, [rcx+18h]
0x14000b978  lea     r8, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x14000b97f  mov     [rsp+88h+var_38], 0
0x14000b988  mov     r9d, ebx
0x14000b98b  mov     [rsp+88h+var_40], rsi
0x14000b990  mov     [rsp+88h+var_48], rdx
0x14000b995  lea     rdx, [rsp+88h+arg_30]
0x14000b99d  mov     [rsp+88h+var_50], rbp
0x14000b9a2  mov     [rsp+88h+var_58], rdx
0x14000b9a7  lea     rdx, [rsp+88h+arg_28]
0x14000b9af  mov     [rsp+88h+var_60], rbp
0x14000b9b4  mov     [rsp+88h+var_68], rdx
0x14000b9b9  mov     edx, 2Bh ; '+'
0x14000b9be  call    _guard_dispatch_icall
0x14000b9c3  jmp     loc_14000B8F3
```
