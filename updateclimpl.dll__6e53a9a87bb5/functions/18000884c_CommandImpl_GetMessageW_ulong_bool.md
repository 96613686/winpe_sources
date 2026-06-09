# CommandImpl::GetMessageW(ulong,bool)

- ea: `0x18000884c`
- end: `0x180008907`
- name: `?GetMessageW@CommandImpl@@CA?AV?$unique_ptr@_WU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@K_N@Z`
- size: `187`
- prototype: `_QWORD *__fastcall(_QWORD *, DWORD, unsigned __int8)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008cdc`
- `0x180015922`

## callees

- `0x180008390`
- `0x18000884c`
- `0x180010310`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800088bb`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800088bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800088df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800088df`

## pseudocode

```c
_QWORD *__fastcall CommandImpl::GetMessageW(_QWORD *a1, DWORD a2, unsigned __int8 a3)
{
  DWORD v5; // edi
  HINSTANCE ThisHandle; // rax
  void *v7; // rcx
  WCHAR Buffer[4]; // [rsp+48h] [rbp-30h] BYREF

  v5 = ((a3 + 1) << 11) | 0x300;
  *(_QWORD *)Buffer = 0;
  if ( a3 )
    ThisHandle = 0;
  else
    ThisHandle = CliUtils::GetThisHandle(1);
  if ( FormatMessageW(v5, ThisHandle, a2, 0, Buffer, 0, 0) )
  {
    *a1 = *(_QWORD *)Buffer;
  }
  else
  {
    *a1 = 0;
    v7 = *(void **)Buffer;
    *(_QWORD *)Buffer = 0;
    if ( v7 )
      LocalFree(v7);
  }
  return a1;
}

```

## disassembly

```asm
0x18000884c  push    rbx
0x18000884e  push    rsi
0x18000884f  push    rdi
0x180008850  sub     rsp, 60h
0x180008854  mov     rax, cs:__security_cookie
0x18000885b  xor     rax, rsp
0x18000885e  mov     [rsp+78h+var_28], rax
0x180008863  mov     esi, edx
0x180008865  mov     rbx, rcx
0x180008868  mov     qword ptr [rsp+78h+Buffer], rcx
0x18000886d  movzx   edi, r8b
0x180008871  inc     edi
0x180008873  shl     edi, 0Bh
0x180008876  or      edi, 300h
0x18000887c  mov     qword ptr [rsp+78h+Buffer], 0
0x180008885  test    r8b, r8b
0x180008888  jz      short loc_18000888E
0x18000888a  xor     eax, eax
0x18000888c  jmp     short loc_180008895
0x18000888e  mov     cl, 1; bool
0x180008890  call    ?GetThisHandle@CliUtils@@SAPEAUHINSTANCE__@@_N@Z; CliUtils::GetThisHandle(bool)
0x180008895  mov     [rsp+78h+Arguments], 0; Arguments
0x18000889e  mov     [rsp+78h+nSize], 0; nSize
0x1800088a6  lea     rcx, [rsp+78h+Buffer]
0x1800088ab  mov     [rsp+78h+lpBuffer], rcx; lpBuffer
0x1800088b0  xor     r9d, r9d; dwLanguageId
0x1800088b3  mov     r8d, esi; dwMessageId
0x1800088b6  mov     rdx, rax; lpSource
0x1800088b9  mov     ecx, edi; dwFlags
0x1800088bb  call    cs:__imp_FormatMessageW
0x1800088c1  test    eax, eax
0x1800088c3  jnz     short loc_1800088E7
0x1800088c5  mov     qword ptr [rbx], 0
0x1800088cc  mov     rcx, qword ptr [rsp+78h+Buffer]; hMem
0x1800088d1  mov     qword ptr [rsp+78h+Buffer], 0
0x1800088da  test    rcx, rcx
0x1800088dd  jz      short loc_1800088EF
0x1800088df  call    cs:__imp_LocalFree
0x1800088e5  jmp     short loc_1800088EF
0x1800088e7  mov     rax, qword ptr [rsp+78h+Buffer]
0x1800088ec  mov     [rbx], rax
0x1800088ef  mov     rax, rbx
0x1800088f2  mov     rcx, [rsp+78h+var_28]
0x1800088f7  xor     rcx, rsp; StackCookie
0x1800088fa  call    __security_check_cookie
0x1800088ff  add     rsp, 60h
0x180008903  pop     rdi
0x180008904  pop     rsi
0x180008905  pop     rbx
0x180008906  retn
```
