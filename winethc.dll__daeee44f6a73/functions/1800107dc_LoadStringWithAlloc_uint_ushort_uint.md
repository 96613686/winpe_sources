# LoadStringWithAlloc(uint,ushort * *,uint)

- ea: `0x1800107dc`
- end: `0x180010878`
- name: `?LoadStringWithAlloc@@YAJIPEAPEAGI@Z`
- size: `156`
- prototype: `__int64 __fastcall(UINT uID, unsigned __int16 **, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005b30`
- `0x180008ec0`
- `0x18000a22c`
- `0x180010324`

## callees

- `0x1800107dc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180010834`
- `KERNEL32!GetLastError` at `0x180010834`
- `USER32!LoadStringW` at `0x180010824`
- `USER32!LoadStringW` at `0x180010824`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800107f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800107f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010852`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010852`

## pseudocode

```c
__int64 __fastcall LoadStringWithAlloc(UINT uID, LPVOID *a2)
{
  unsigned __int16 *v4; // rax
  unsigned int v6; // ebx
  signed int LastError; // eax

  v4 = (unsigned __int16 *)CoTaskMemAlloc(0x800u);
  *a2 = v4;
  if ( !v4 )
    return 2147942414LL;
  v6 = 0;
  if ( !LoadStringW(hInstance, uID, v4, 1024) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    CoTaskMemFree(*a2);
    *a2 = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x1800107dc  mov     [rsp+arg_0], rbx
0x1800107e1  mov     [rsp+arg_8], rsi
0x1800107e6  push    rdi
0x1800107e7  sub     rsp, 20h
0x1800107eb  mov     esi, ecx
0x1800107ed  mov     rdi, rdx
0x1800107f0  mov     ecx, 800h; cb
0x1800107f5  call    cs:__imp_CoTaskMemAlloc
0x1800107fc  nop     dword ptr [rax+rax+00h]
0x180010801  mov     [rdi], rax
0x180010804  test    rax, rax
0x180010807  jnz     short loc_180010810
0x180010809  mov     eax, 8007000Eh
0x18001080e  jmp     short loc_180010867
0x180010810  mov     rcx, cs:hInstance; hInstance
0x180010817  mov     r9d, 400h; cchBufferMax
0x18001081d  mov     r8, rax; lpBuffer
0x180010820  mov     edx, esi; uID
0x180010822  xor     ebx, ebx
0x180010824  call    cs:__imp_LoadStringW
0x18001082b  nop     dword ptr [rax+rax+00h]
0x180010830  test    eax, eax
0x180010832  jnz     short loc_180010865
0x180010834  call    cs:__imp_GetLastError
0x18001083b  nop     dword ptr [rax+rax+00h]
0x180010840  mov     ebx, eax
0x180010842  test    eax, eax
0x180010844  jle     short loc_18001084F
0x180010846  movzx   ebx, ax
0x180010849  or      ebx, 80070000h
0x18001084f  mov     rcx, [rdi]; pv
0x180010852  call    cs:__imp_CoTaskMemFree
0x180010859  nop     dword ptr [rax+rax+00h]
0x18001085e  mov     qword ptr [rdi], 0
0x180010865  mov     eax, ebx
0x180010867  mov     rbx, [rsp+28h+arg_0]
0x18001086c  mov     rsi, [rsp+28h+arg_8]
0x180010871  add     rsp, 20h
0x180010875  pop     rdi
0x180010876  retn
```
