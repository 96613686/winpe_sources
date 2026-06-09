# BlockShutDown(void)

- ea: `0x140005794`
- end: `0x140005855`
- name: `?BlockShutDown@@YAJXZ`
- size: `193`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400075b0`
- `0x14000afc0`

## callees

- `0x140005794`
- `0x14000e280`
- `0x140013490`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140005842`
- `KERNEL32!LocalFree` at `0x140005842`
- `KERNEL32!CreateThread` at `0x1400057b7`
- `KERNEL32!CreateThread` at `0x1400057b7`
- `KERNEL32!GetLastError` at `0x1400057c9`
- `KERNEL32!GetLastError` at `0x1400057c9`

## string_xrefs

- `0x1400057e0`: `Failed to create work thread`

## pseudocode

```c
__int64 BlockShutDown(void)
{
  signed int v0; // ebx
  signed int LastError; // eax
  HLOCAL v2; // rdi
  HLOCAL hMem; // [rsp+40h] [rbp+8h] BYREF

  v0 = 0;
  qword_140020140 = (__int64)CreateThread(0, 0, (LPTHREAD_START_ROUTINE)BlockShutDownThread, 0, 0, 0);
  if ( !qword_140020140 )
  {
    LastError = GetLastError();
    v0 = LastError;
    if ( LastError > 0 )
      v0 = (unsigned __int16)LastError | 0x80070000;
    if ( v0 >= 0 )
      v0 = -2147467259;
    WusaLogDebugEventA(L"BlockShutDown", 293, "Failed to create work thread");
    hMem = 0;
    WusaGetErrorMessage(v0, (unsigned __int16 **)&hMem);
    v2 = hMem;
    WusaLogDebugEventA(L"BlockShutDown", 297, "Exit with error code 0X%x (%ls)", v0, (const wchar_t *)hMem);
    if ( v2 )
      LocalFree(v2);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x140005794  mov     [rsp+arg_8], rbx
0x140005799  push    rdi
0x14000579a  sub     rsp, 30h
0x14000579e  xor     ebx, ebx
0x1400057a0  lea     r8, ?BlockShutDownThread@@YAKPEAX@Z; lpStartAddress
0x1400057a7  mov     [rsp+38h+lpThreadId], rbx; lpThreadId
0x1400057ac  xor     r9d, r9d; lpParameter
0x1400057af  xor     edx, edx; dwStackSize
0x1400057b1  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x1400057b5  xor     ecx, ecx; lpThreadAttributes
0x1400057b7  call    cs:__imp_CreateThread
0x1400057bd  mov     cs:qword_140020140, rax
0x1400057c4  test    rax, rax
0x1400057c7  jnz     short loc_140005848
0x1400057c9  call    cs:__imp_GetLastError
0x1400057cf  mov     ebx, eax
0x1400057d1  test    eax, eax
0x1400057d3  jle     short loc_1400057DE
0x1400057d5  movzx   ebx, ax
0x1400057d8  or      ebx, 80070000h
0x1400057de  test    ebx, ebx
0x1400057e0  lea     r8, aFailedToCreate_12; "Failed to create work thread"
0x1400057e7  mov     eax, 80004005h
0x1400057ec  lea     rcx, aBlockshutdown; "BlockShutDown"
0x1400057f3  mov     edx, 125h
0x1400057f8  cmovns  ebx, eax
0x1400057fb  call    WusaLogDebugEventA
0x140005800  lea     rdx, [rsp+38h+hMem]; unsigned __int16 **
0x140005805  mov     [rsp+38h+hMem], 0
0x14000580e  mov     ecx, ebx; dwMessageId
0x140005810  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x140005815  mov     rdi, [rsp+38h+hMem]
0x14000581a  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x140005821  mov     r9d, ebx
0x140005824  mov     qword ptr [rsp+38h+dwCreationFlags], rdi
0x140005829  mov     edx, 129h
0x14000582e  lea     rcx, aBlockshutdown; "BlockShutDown"
0x140005835  call    WusaLogDebugEventA
0x14000583a  test    rdi, rdi
0x14000583d  jz      short loc_140005848
0x14000583f  mov     rcx, rdi; hMem
0x140005842  call    cs:__imp_LocalFree
0x140005848  mov     eax, ebx
0x14000584a  mov     rbx, [rsp+38h+arg_8]
0x14000584f  add     rsp, 30h
0x140005853  pop     rdi
0x140005854  retn
```
