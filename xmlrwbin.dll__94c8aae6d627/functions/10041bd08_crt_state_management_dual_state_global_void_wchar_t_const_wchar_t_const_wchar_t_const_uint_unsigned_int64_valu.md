# __crt_state_management::dual_state_global<void (*)(wchar_t const *,wchar_t const *,wchar_t const *,uint,unsigned __int64)>::value(__crt_cached_ptd_host &)

- ea: `0x10041bd08`
- end: `0x10041bd54`
- name: `?value@?$dual_state_global@P6AXPEB_W00I_K@Z@__crt_state_management@@QEAAAEAP6AXPEB_W00I_K@ZAEAV__crt_cached_ptd_host@@@Z`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x10041bf74`

## callees

- `0x10041bd08`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10041bd24`
- `KERNEL32!GetLastError` at `0x10041bd24`
- `KERNEL32!SetLastError` at `0x10041bd34`
- `KERNEL32!SetLastError` at `0x10041bd34`

## pseudocode

```c
__int64 __fastcall __crt_state_management::dual_state_global<void (*)(wchar_t const *,wchar_t const *,wchar_t const *,unsigned int,unsigned __int64)>::value(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbx
  DWORD LastError; // eax

  v2 = 0;
  if ( *(_BYTE *)(a2 + 16) )
  {
    v2 = *(_QWORD *)(a2 + 8);
  }
  else
  {
    LastError = GetLastError();
    *(_QWORD *)(a2 + 8) = 0;
    *(_BYTE *)(a2 + 16) = 1;
    SetLastError(LastError);
  }
  return a1 + 8 * v2;
}

```

## disassembly

```asm
0x10041bd08  mov     [rsp+arg_0], rbx
0x10041bd0d  mov     [rsp+arg_8], rsi
0x10041bd12  push    rdi
0x10041bd13  sub     rsp, 20h
0x10041bd17  xor     ebx, ebx
0x10041bd19  mov     rdi, rdx
0x10041bd1c  mov     rsi, rcx
0x10041bd1f  cmp     [rdx+10h], bl
0x10041bd22  jnz     short loc_10041BD3C
0x10041bd24  call    cs:__imp_GetLastError
0x10041bd2a  mov     ecx, eax; dwErrCode
0x10041bd2c  mov     [rdi+8], rbx
0x10041bd30  mov     byte ptr [rdi+10h], 1
0x10041bd34  call    cs:__imp_SetLastError
0x10041bd3a  jmp     short loc_10041BD40
0x10041bd3c  mov     rbx, [rdx+8]
0x10041bd40  lea     rax, [rsi+rbx*8]
0x10041bd44  mov     rbx, [rsp+28h+arg_0]
0x10041bd49  mov     rsi, [rsp+28h+arg_8]
0x10041bd4e  add     rsp, 20h
0x10041bd52  pop     rdi
0x10041bd53  retn
```
