# DeviceObject::OnReady(long)

- ea: `0x180013b40`
- end: `0x180013ba7`
- name: `?OnReady@DeviceObject@@AEAAXJ@Z`
- size: `103`
- prototype: `void __fastcall(DeviceObject *__hidden this, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800133ec`
- `0x180013720`

## callees

- `0x180013b40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013b58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013b58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013ba0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013b61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013b61`

## pseudocode

```c
void __fastcall DeviceObject::OnReady(DeviceObject *this, int a2)
{
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  ++*((_DWORD *)this + 23);
  *((_DWORD *)this + 22) = GetCurrentThreadId();
  if ( !*((_DWORD *)this + 6) )
    *((_DWORD *)this + 6) = 1;
  if ( *((int *)this + 8) >= 0 )
    *((_DWORD *)this + 8) = a2;
  if ( !--*((_DWORD *)this + 23) )
    *((_DWORD *)this + 22) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
}

```

## disassembly

```asm
0x180013b40  mov     [rsp+arg_0], rbx
0x180013b45  mov     [rsp+arg_8], rsi
0x180013b4a  push    rdi
0x180013b4b  sub     rsp, 20h
0x180013b4f  mov     rdi, rcx
0x180013b52  mov     esi, edx
0x180013b54  add     rcx, 30h ; '0'; lpCriticalSection
0x180013b58  call    cs:__imp_EnterCriticalSection
0x180013b5e  inc     dword ptr [rdi+5Ch]
0x180013b61  call    cs:__imp_GetCurrentThreadId
0x180013b67  xor     ecx, ecx
0x180013b69  mov     [rdi+58h], eax
0x180013b6c  cmp     [rdi+18h], ecx
0x180013b6f  jnz     short loc_180013B78
0x180013b71  mov     dword ptr [rdi+18h], 1
0x180013b78  cmp     [rdi+20h], ecx
0x180013b7b  jl      short loc_180013B80
0x180013b7d  mov     [rdi+20h], esi
0x180013b80  dec     dword ptr [rdi+5Ch]
0x180013b83  mov     eax, [rdi+5Ch]
0x180013b86  test    eax, eax
0x180013b88  jnz     short loc_180013B8D
0x180013b8a  mov     [rdi+58h], ecx
0x180013b8d  lea     rcx, [rdi+30h]
0x180013b91  mov     rbx, [rsp+28h+arg_0]
0x180013b96  mov     rsi, [rsp+28h+arg_8]
0x180013b9b  add     rsp, 20h
0x180013b9f  pop     rdi
0x180013ba0  jmp     cs:__imp_LeaveCriticalSection
```
