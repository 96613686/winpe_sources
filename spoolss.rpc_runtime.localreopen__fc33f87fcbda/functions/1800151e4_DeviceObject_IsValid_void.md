# DeviceObject::IsValid(void)

- ea: `0x1800151e4`
- end: `0x180015257`
- name: `?IsValid@DeviceObject@@QEBAJXZ`
- size: `115`
- prototype: `__int64 __fastcall(DeviceObject *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180014a50`
- `0x180015260`

## callees

- `0x1800151e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800151f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800151f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001523d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001523d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015207`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015207`

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
0x1800151e4  mov     [rsp+arg_0], rbx
0x1800151e9  push    rdi
0x1800151ea  sub     rsp, 20h
0x1800151ee  lea     rbx, [rcx+30h]
0x1800151f2  mov     rdi, rcx
0x1800151f5  mov     rcx, rbx; lpCriticalSection
0x1800151f8  call    cs:__imp_EnterCriticalSection
0x1800151ff  nop     dword ptr [rax+rax+00h]
0x180015204  inc     dword ptr [rbx+2Ch]
0x180015207  call    cs:__imp_GetCurrentThreadId
0x18001520e  nop     dword ptr [rax+rax+00h]
0x180015213  mov     [rbx+28h], eax
0x180015216  mov     eax, [rdi+18h]
0x180015219  dec     eax
0x18001521b  cmp     eax, 1
0x18001521e  jbe     short loc_180015227
0x180015220  mov     edi, 80070015h
0x180015225  jmp     short loc_18001522A
0x180015227  mov     edi, [rdi+20h]
0x18001522a  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x18001522e  mov     edx, [rbx+2Ch]
0x180015231  jnz     short loc_18001523A
0x180015233  mov     dword ptr [rbx+28h], 0
0x18001523a  mov     rcx, rbx; lpCriticalSection
0x18001523d  call    cs:__imp_LeaveCriticalSection
0x180015244  nop     dword ptr [rax+rax+00h]
0x180015249  mov     rbx, [rsp+28h+arg_0]
0x18001524e  mov     eax, edi
0x180015250  add     rsp, 20h
0x180015254  pop     rdi
0x180015255  retn
```
