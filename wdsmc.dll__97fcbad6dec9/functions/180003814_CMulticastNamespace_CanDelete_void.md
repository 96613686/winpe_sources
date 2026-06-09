# CMulticastNamespace::CanDelete(void)

- ea: `0x180003814`
- end: `0x180003860`
- name: `?CanDelete@CMulticastNamespace@@QEAAHXZ`
- size: `76`
- prototype: `__int64 __fastcall(CMulticastNamespace *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800067f0`
- `0x180006bc4`
- `0x180007a24`

## callees

- `0x180003814`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180003848`
- `KERNEL32!LeaveCriticalSection` at `0x180003848`
- `KERNEL32!EnterCriticalSection` at `0x18000382a`
- `KERNEL32!EnterCriticalSection` at `0x18000382a`

## pseudocode

```c
_BOOL8 __fastcall CMulticastNamespace::CanDelete(CMulticastNamespace *this)
{
  BOOL v2; // ebx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v2 = 0;
  if ( *((_DWORD *)this + 30) )
    v2 = *((_DWORD *)this + 111) == 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return v2;
}

```

## disassembly

```asm
0x180003814  mov     [rsp+arg_0], rbx
0x180003819  mov     [rsp+arg_8], rsi
0x18000381e  push    rdi
0x18000381f  sub     rsp, 20h
0x180003823  mov     rdi, rcx
0x180003826  add     rcx, 10h; lpCriticalSection
0x18000382a  call    cs:__imp_EnterCriticalSection
0x180003830  xor     ebx, ebx
0x180003832  cmp     [rdi+78h], ebx
0x180003835  jz      short loc_180003844
0x180003837  cmp     [rdi+1BCh], ebx
0x18000383d  jnz     short loc_180003844
0x18000383f  mov     ebx, 1
0x180003844  lea     rcx, [rdi+10h]; lpCriticalSection
0x180003848  call    cs:__imp_LeaveCriticalSection
0x18000384e  mov     rsi, [rsp+28h+arg_8]
0x180003853  mov     eax, ebx
0x180003855  mov     rbx, [rsp+28h+arg_0]
0x18000385a  add     rsp, 20h
0x18000385e  pop     rdi
0x18000385f  retn
```
