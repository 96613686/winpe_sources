# DeviceObject::OnReady(long)

- ea: `0x1800152e8`
- end: `0x180015360`
- name: `?OnReady@DeviceObject@@AEAAXJ@Z`
- size: `120`
- prototype: `void __fastcall(DeviceObject *__hidden this, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180014b7c`
- `0x180014ed0`

## callees

- `0x1800152e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015300`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015300`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015354`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001530f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001530f`

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
0x1800152e8  mov     [rsp+arg_0], rbx
0x1800152ed  mov     [rsp+arg_8], rsi
0x1800152f2  push    rdi
0x1800152f3  sub     rsp, 20h
0x1800152f7  mov     rdi, rcx
0x1800152fa  mov     esi, edx
0x1800152fc  add     rcx, 30h ; '0'; lpCriticalSection
0x180015300  call    cs:__imp_EnterCriticalSection
0x180015307  nop     dword ptr [rax+rax+00h]
0x18001530c  inc     dword ptr [rdi+5Ch]
0x18001530f  call    cs:__imp_GetCurrentThreadId
0x180015316  nop     dword ptr [rax+rax+00h]
0x18001531b  xor     ecx, ecx
0x18001531d  mov     [rdi+58h], eax
0x180015320  cmp     [rdi+18h], ecx
0x180015323  jnz     short loc_18001532C
0x180015325  mov     dword ptr [rdi+18h], 1
0x18001532c  cmp     [rdi+20h], ecx
0x18001532f  jl      short loc_180015334
0x180015331  mov     [rdi+20h], esi
0x180015334  dec     dword ptr [rdi+5Ch]
0x180015337  mov     eax, [rdi+5Ch]
0x18001533a  test    eax, eax
0x18001533c  jnz     short loc_180015341
0x18001533e  mov     [rdi+58h], ecx
0x180015341  lea     rcx, [rdi+30h]
0x180015345  mov     rbx, [rsp+28h+arg_0]
0x18001534a  mov     rsi, [rsp+28h+arg_8]
0x18001534f  add     rsp, 20h
0x180015353  pop     rdi
0x180015354  jmp     cs:__imp_LeaveCriticalSection
```
