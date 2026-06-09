# ShowHelp

- ea: `0x18007b8e8`
- end: `0x18007b988`
- name: `ShowHelp`
- size: `160`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18003dc10`
- `0x18004c570`
- `0x180056560`
- `0x180059420`
- `0x18005abf0`
- `0x18007b378`

## callees

- `0x180005d08`
- `0x18007b8e8`

## import_xrefs

- `KERNEL32!CreateThread` at `0x18007b924`
- `KERNEL32!CreateThread` at `0x18007b924`
- `KERNEL32!CloseHandle` at `0x18007b975`
- `KERNEL32!CloseHandle` at `0x18007b975`
- `ole32!CoWaitForMultipleHandles` at `0x18007b968`
- `ole32!CoWaitForMultipleHandles` at `0x18007b968`
- `OLEAUT32!__imp_SysAllocString` at `0x18007b8f7`
- `OLEAUT32!__imp_SysAllocString` at `0x18007b8f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b93e`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b93e`

## pseudocode

```c
__int64 __fastcall ShowHelp(const OLECHAR *a1)
{
  unsigned int LastError; // ebx
  BSTR v2; // rax
  OLECHAR *v3; // rdi
  DWORD dwindex; // [rsp+48h] [rbp+10h] BYREF
  HANDLE pHandles; // [rsp+50h] [rbp+18h] BYREF

  LastError = -2147024882;
  v2 = SysAllocString(a1);
  v3 = v2;
  if ( v2 )
  {
    pHandles = CreateThread(0, 0, HelpWndProc, v2, 0, 0);
    if ( pHandles )
    {
      dwindex = 0;
      LastError = CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
      CloseHandle(pHandles);
    }
    else
    {
      LastError = HrGetLastError();
      SysFreeString(v3);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18007b8e8  mov     [rsp+arg_0], rbx
0x18007b8ed  push    rdi
0x18007b8ee  sub     rsp, 30h
0x18007b8f2  mov     ebx, 8007000Eh
0x18007b8f7  call    cs:__imp_SysAllocString
0x18007b8fd  mov     rdi, rax
0x18007b900  test    rax, rax
0x18007b903  jz      short loc_18007B97B
0x18007b905  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18007b90e  lea     r8, _HelpWndProc; lpStartAddress
0x18007b915  mov     r9, rax; lpParameter
0x18007b918  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18007b920  xor     edx, edx; dwStackSize
0x18007b922  xor     ecx, ecx; lpThreadAttributes
0x18007b924  call    cs:__imp_CreateThread
0x18007b92a  mov     [rsp+38h+pHandles], rax
0x18007b92f  test    rax, rax
0x18007b932  jnz     short loc_18007B946
0x18007b934  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18007b939  mov     rcx, rdi; bstrString
0x18007b93c  mov     ebx, eax
0x18007b93e  call    cs:__imp_SysFreeString
0x18007b944  jmp     short loc_18007B97B
0x18007b946  lea     rax, [rsp+38h+dwindex]
0x18007b94b  mov     [rsp+38h+dwindex], 0
0x18007b953  lea     r9, [rsp+38h+pHandles]; pHandles
0x18007b958  mov     qword ptr [rsp+38h+dwCreationFlags], rax; lpdwindex
0x18007b95d  mov     r8d, 1; cHandles
0x18007b963  or      edx, 0FFFFFFFFh; dwTimeout
0x18007b966  xor     ecx, ecx; dwFlags
0x18007b968  call    cs:__imp_CoWaitForMultipleHandles
0x18007b96e  mov     rcx, [rsp+38h+pHandles]; hObject
0x18007b973  mov     ebx, eax
0x18007b975  call    cs:__imp_CloseHandle
0x18007b97b  mov     eax, ebx
0x18007b97d  mov     rbx, [rsp+38h+arg_0]
0x18007b982  add     rsp, 30h
0x18007b986  pop     rdi
0x18007b987  retn
```
