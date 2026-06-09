# DeviceObject::IsValid(void)

- ea: `0x180013a64`
- end: `0x180013ac4`
- name: `?IsValid@DeviceObject@@QEBAJXZ`
- size: `96`
- prototype: `__int64 __fastcall(DeviceObject *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800132cc`
- `0x180013acc`

## callees

- `0x180013a64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013a78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013a78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013ab1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013ab1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013a81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013a81`

## pseudocode

```c
__int64 __fastcall DeviceObject::IsValid(DeviceObject *this)
{
  char *v1; // rbx
  unsigned int v3; // edi

  v1 = (char *)this + 48;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  ++*((_DWORD *)v1 + 11);
  *((_DWORD *)v1 + 10) = GetCurrentThreadId();
  if ( (unsigned int)(*((_DWORD *)this + 6) - 1) <= 1 )
    v3 = *((_DWORD *)this + 8);
  else
    v3 = -2147024875;
  if ( (*((_DWORD *)v1 + 11))-- == 1 )
    *((_DWORD *)v1 + 10) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v1);
  return v3;
}

```

## disassembly

```asm
0x180013a64  mov     [rsp+arg_0], rbx
0x180013a69  push    rdi
0x180013a6a  sub     rsp, 20h
0x180013a6e  lea     rbx, [rcx+30h]
0x180013a72  mov     rdi, rcx
0x180013a75  mov     rcx, rbx; lpCriticalSection
0x180013a78  call    cs:__imp_EnterCriticalSection
0x180013a7e  inc     dword ptr [rbx+2Ch]
0x180013a81  call    cs:__imp_GetCurrentThreadId
0x180013a87  mov     [rbx+28h], eax
0x180013a8a  mov     eax, [rdi+18h]
0x180013a8d  dec     eax
0x180013a8f  cmp     eax, 1
0x180013a92  jbe     short loc_180013A9B
0x180013a94  mov     edi, 80070015h
0x180013a99  jmp     short loc_180013A9E
0x180013a9b  mov     edi, [rdi+20h]
0x180013a9e  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x180013aa2  mov     edx, [rbx+2Ch]
0x180013aa5  jnz     short loc_180013AAE
0x180013aa7  mov     dword ptr [rbx+28h], 0
0x180013aae  mov     rcx, rbx; lpCriticalSection
0x180013ab1  call    cs:__imp_LeaveCriticalSection
0x180013ab7  mov     rbx, [rsp+28h+arg_0]
0x180013abc  mov     eax, edi
0x180013abe  add     rsp, 20h
0x180013ac2  pop     rdi
0x180013ac3  retn
```
