# WaitForHandle

- ea: `0x180003f58`
- end: `0x180004002`
- name: `WaitForHandle`
- size: `170`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800038c0`
- `0x18000d4f4`

## callees

- `0x180003f58`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003fe5`
- `KERNEL32!GetLastError` at `0x180003fe5`
- `USER32!PeekMessageA` at `0x180003fba`
- `USER32!PeekMessageA` at `0x180003fba`
- `USER32!TranslateMessage` at `0x180003fc9`
- `USER32!TranslateMessage` at `0x180003fc9`
- `USER32!MsgWaitForMultipleObjects` at `0x180003f93`
- `USER32!MsgWaitForMultipleObjects` at `0x180003f93`
- `USER32!DispatchMessageA` at `0x180003fd4`
- `USER32!DispatchMessageA` at `0x180003fd4`

## pseudocode

```c
signed int __fastcall WaitForHandle(void *a1, DWORD a2, DWORD *a3)
{
  DWORD v5; // eax
  signed int result; // eax
  tagMSG Msg; // [rsp+30h] [rbp-38h] BYREF
  HANDLE pHandles; // [rsp+70h] [rbp+8h] BYREF

  pHandles = a1;
  memset(&Msg, 0, sizeof(Msg));
  while ( 1 )
  {
    v5 = MsgWaitForMultipleObjects(1u, &pHandles, 0, a2, 0x1CFFu);
    *a3 = v5;
    if ( v5 == -1 )
      break;
    if ( v5 != 1 )
      return 0;
    while ( PeekMessageA(&Msg, 0, 0, 0, 1u) )
    {
      TranslateMessage(&Msg);
      DispatchMessageA(&Msg);
      if ( Msg.message == 16 )
        return 0;
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180003f58  mov     rax, rsp
0x180003f5b  mov     [rax+10h], rbx
0x180003f5f  mov     [rax+8], rcx
0x180003f63  push    rdi
0x180003f64  sub     rsp, 60h
0x180003f68  xorps   xmm0, xmm0
0x180003f6b  mov     rbx, r8
0x180003f6e  movups  xmmword ptr [rax-38h], xmm0
0x180003f72  mov     edi, edx
0x180003f74  movups  xmmword ptr [rax-28h], xmm0
0x180003f78  movups  xmmword ptr [rax-18h], xmm0
0x180003f7c  xor     r8d, r8d; fWaitAll
0x180003f7f  mov     [rsp+68h+dwWakeMask], 1CFFh; dwWakeMask
0x180003f87  mov     r9d, edi; dwMilliseconds
0x180003f8a  lea     rdx, [rsp+68h+pHandles]; pHandles
0x180003f8f  lea     ecx, [r8+1]; nCount
0x180003f93  call    cs:__imp_MsgWaitForMultipleObjects
0x180003f99  mov     [rbx], eax
0x180003f9b  cmp     eax, 0FFFFFFFFh
0x180003f9e  jz      short loc_180003FE5
0x180003fa0  cmp     eax, 1
0x180003fa3  jnz     short loc_180003FE1
0x180003fa5  xor     r9d, r9d; wMsgFilterMax
0x180003fa8  mov     [rsp+68h+dwWakeMask], 1; wRemoveMsg
0x180003fb0  xor     r8d, r8d; wMsgFilterMin
0x180003fb3  lea     rcx, [rsp+68h+Msg]; lpMsg
0x180003fb8  xor     edx, edx; hWnd
0x180003fba  call    cs:__imp_PeekMessageA
0x180003fc0  test    eax, eax
0x180003fc2  jz      short loc_180003F7C
0x180003fc4  lea     rcx, [rsp+68h+Msg]; lpMsg
0x180003fc9  call    cs:__imp_TranslateMessage
0x180003fcf  lea     rcx, [rsp+68h+Msg]; lpMsg
0x180003fd4  call    cs:__imp_DispatchMessageA
0x180003fda  cmp     [rsp+68h+Msg.message], 10h
0x180003fdf  jnz     short loc_180003FA5
0x180003fe1  xor     eax, eax
0x180003fe3  jmp     short loc_180003FF7
0x180003fe5  call    cs:__imp_GetLastError
0x180003feb  test    eax, eax
0x180003fed  jle     short loc_180003FF7
0x180003fef  movzx   eax, ax
0x180003ff2  or      eax, 80070000h
0x180003ff7  mov     rbx, [rsp+68h+arg_8]
0x180003ffc  add     rsp, 60h
0x180004000  pop     rdi
0x180004001  retn
```
