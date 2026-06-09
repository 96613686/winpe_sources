# _stub_GdiCombineTransform

- ea: `0x140036d80`
- end: `0x140036e27`
- name: `_stub_GdiCombineTransform`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400098e0`
- `0x140017b74`
- `0x140036d80`

## import_xrefs

- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140036dc9`
- `ntoskrnl!PsIsWin32KFilterEnabled` at `0x140036dc9`

## string_xrefs

- `0x140036daf`: `NtGdiCombineTransform`

## pseudocode

```c
__int64 stub_GdiCombineTransform()
{
  __int64 result; // rax

  if ( !(unsigned __int8)IsWin32KSyscallFiltered() )
    return NtGdiCombineTransform();
  NtUserWin32kSysCallFilterStub();
  if ( !(unsigned __int8)PsIsWin32KFilterEnabled() )
    return NtGdiCombineTransform();
  result = (unsigned int)*((char *)&W32pServiceTableFilter[27] + 4 * (unsigned int)W32pServiceLimitFilter + 5);
  if ( (int)result > 0 )
    return 3221225500LL;
  return result;
}

```

## disassembly

```asm
0x140036d80  sub     rsp, 48h
0x140036d84  mov     [rsp+48h+var_28], rcx
0x140036d89  mov     [rsp+48h+var_20], rdx
0x140036d8e  mov     [rsp+48h+var_18], r8
0x140036d93  mov     [rsp+48h+var_10], r9
0x140036d98  mov     rcx, 0DDh
0x140036d9f  call    cs:__imp_IsWin32KSyscallFiltered
0x140036da6  nop     dword ptr [rax+rax+00h]
0x140036dab  test    al, al
0x140036dad  jz      short loc_140036E03
0x140036daf  lea     rcx, aNtgdicombinetr; "NtGdiCombineTransform"
0x140036db6  mov     rdx, 0DDh
0x140036dbd  call    cs:__imp_NtUserWin32kSysCallFilterStub
0x140036dc4  nop     dword ptr [rax+rax+00h]
0x140036dc9  call    cs:__imp_PsIsWin32KFilterEnabled
0x140036dd0  nop     dword ptr [rax+rax+00h]
0x140036dd5  test    al, al
0x140036dd7  jz      short loc_140036E03
0x140036dd9  lea     rcx, W32pServiceTableFilter
0x140036de0  mov     edx, cs:W32pServiceLimitFilter
0x140036de6  mov     rax, 0DDh
0x140036ded  lea     rcx, [rcx+rdx*4]
0x140036df1  movsx   eax, byte ptr [rcx+rax]
0x140036df5  or      eax, eax
0x140036df7  jle     short loc_140036DFE
0x140036df9  mov     eax, 0C000001Ch
0x140036dfe  add     rsp, 48h
0x140036e02  retn
0x140036e03  mov     rax, cs:__imp_NtGdiCombineTransform
0x140036e0a  mov     rcx, [rsp+48h+var_28]
0x140036e0f  mov     rdx, [rsp+48h+var_20]
0x140036e14  mov     r8, [rsp+48h+var_18]
0x140036e19  mov     r9, [rsp+48h+var_10]
0x140036e1e  add     rsp, 48h
0x140036e22  jmp     rax
```
