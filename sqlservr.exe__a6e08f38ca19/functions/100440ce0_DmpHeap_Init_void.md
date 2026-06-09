# DmpHeap::Init(void)

- ea: `0x100440ce0`
- end: `0x100440d60`
- name: `?Init@DmpHeap@@QEAAJXZ`
- size: `128`
- prototype: `__int64 __fastcall(DmpHeap *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x100441930`

## callees

- `0x100440ce0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100440d10`
- `KERNEL32!GetLastError` at `0x100440d10`
- `KERNEL32!HeapCreate` at `0x100440d02`
- `KERNEL32!HeapCreate` at `0x100440d02`
- `api-ms-win-crt-runtime-l1-1-0!_resetstkoflw` at `0x100440d37`
- `api-ms-win-crt-runtime-l1-1-0!_resetstkoflw` at `0x100440d37`

## pseudocode

```c
__int64 __fastcall DmpHeap::Init(DmpHeap *this)
{
  HANDLE v2; // rax
  signed int LastError; // eax
  __int64 result; // rax
  int v5; // [rsp+20h] [rbp-28h]

  v5 = 0;
  if ( !*(_QWORD *)this )
  {
    v2 = HeapCreate(0, 0x10000u, 0);
    *(_QWORD *)this = v2;
    if ( !v2 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v5 = LastError;
    }
  }
  result = (unsigned int)v5;
  if ( v5 >= 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x100440ce0  push    rbx
0x100440ce2  sub     rsp, 40h
0x100440ce6  mov     rbx, rcx
0x100440ce9  xor     eax, eax
0x100440ceb  mov     [rsp+48h+var_28], eax
0x100440cef  mov     [rsp+48h+arg_8], eax
0x100440cf3  cmp     [rcx], rax
0x100440cf6  jnz     short loc_100440D26
0x100440cf8  xor     r8d, r8d; dwMaximumSize
0x100440cfb  mov     edx, 10000h; dwInitialSize
0x100440d00  xor     ecx, ecx; flOptions
0x100440d02  call    cs:__imp_HeapCreate
0x100440d08  mov     [rbx], rax
0x100440d0b  test    rax, rax
0x100440d0e  jnz     short loc_100440D26
0x100440d10  call    cs:__imp_GetLastError
0x100440d16  test    eax, eax
0x100440d18  jle     short loc_100440D22
0x100440d1a  movzx   eax, ax
0x100440d1d  or      eax, 80070000h
0x100440d22  mov     [rsp+48h+var_28], eax
0x100440d26  jmp     short loc_100440D4D
0x100440d28  mov     [rsp+48h+arg_8], eax
0x100440d2c  mov     eax, [rsp+48h+arg_8]
0x100440d30  cmp     eax, 0C00000FDh
0x100440d35  jnz     short loc_100440D3D
0x100440d37  call    cs:__imp__resetstkoflw
0x100440d3d  mov     eax, [rsp+48h+arg_8]
0x100440d41  test    eax, eax
0x100440d43  js      short loc_100440D4D
0x100440d45  mov     [rsp+48h+arg_8], 80004005h
0x100440d4d  mov     ecx, [rsp+48h+arg_8]
0x100440d51  mov     eax, [rsp+48h+var_28]
0x100440d55  test    eax, eax
0x100440d57  cmovns  eax, ecx
0x100440d5a  add     rsp, 40h
0x100440d5e  pop     rbx
0x100440d5f  retn
0x100456430  push    rbp
0x100456432  sub     rsp, 20h
0x100456436  mov     rbp, rdx
0x100456439  mov     [rbp+28h], rcx
0x10045643d  mov     [rbp+30h], rcx
0x100456441  mov     eax, 1
0x100456446  add     rsp, 20h
0x10045644a  pop     rbp
0x10045644b  retn
```
