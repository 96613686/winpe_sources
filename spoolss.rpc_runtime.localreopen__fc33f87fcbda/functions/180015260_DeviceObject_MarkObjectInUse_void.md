# DeviceObject::MarkObjectInUse(void)

- ea: `0x180015260`
- end: `0x1800152df`
- name: `?MarkObjectInUse@DeviceObject@@IEAAJXZ`
- size: `127`
- prototype: `__int64 __fastcall(DeviceObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004bf4`
- `0x18001285c`
- `0x180014ed0`

## callees

- `0x1800151e4`
- `0x180015260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015276`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015276`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800152c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800152c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015285`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015285`

## pseudocode

```c
__int64 __fastcall DeviceObject::MarkObjectInUse(DeviceObject *this)
{
  int IsValid; // esi

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  ++*((_DWORD *)this + 23);
  *((_DWORD *)this + 22) = GetCurrentThreadId();
  IsValid = DeviceObject::IsValid(this);
  if ( IsValid >= 0 )
  {
    ++*((_DWORD *)this + 7);
    *((_DWORD *)this + 6) = 2;
  }
  if ( (*((_DWORD *)this + 23))-- == 1 )
    *((_DWORD *)this + 22) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  return (unsigned int)IsValid;
}

```

## disassembly

```asm
0x180015260  mov     [rsp+arg_0], rbx
0x180015265  mov     [rsp+arg_8], rsi
0x18001526a  push    rdi
0x18001526b  sub     rsp, 20h
0x18001526f  mov     rdi, rcx
0x180015272  add     rcx, 30h ; '0'; lpCriticalSection
0x180015276  call    cs:__imp_EnterCriticalSection
0x18001527d  nop     dword ptr [rax+rax+00h]
0x180015282  inc     dword ptr [rdi+5Ch]
0x180015285  call    cs:__imp_GetCurrentThreadId
0x18001528c  nop     dword ptr [rax+rax+00h]
0x180015291  mov     rcx, rdi; this
0x180015294  mov     [rdi+58h], eax
0x180015297  call    ?IsValid@DeviceObject@@QEBAJXZ; DeviceObject::IsValid(void)
0x18001529c  mov     esi, eax
0x18001529e  test    eax, eax
0x1800152a0  js      short loc_1800152AC
0x1800152a2  inc     dword ptr [rdi+1Ch]
0x1800152a5  mov     dword ptr [rdi+18h], 2
0x1800152ac  add     dword ptr [rdi+5Ch], 0FFFFFFFFh
0x1800152b0  mov     edx, [rdi+5Ch]
0x1800152b3  jnz     short loc_1800152BC
0x1800152b5  mov     dword ptr [rdi+58h], 0
0x1800152bc  lea     rcx, [rdi+30h]; lpCriticalSection
0x1800152c0  call    cs:__imp_LeaveCriticalSection
0x1800152c7  nop     dword ptr [rax+rax+00h]
0x1800152cc  mov     rbx, [rsp+28h+arg_0]
0x1800152d1  mov     eax, esi
0x1800152d3  mov     rsi, [rsp+28h+arg_8]
0x1800152d8  add     rsp, 20h
0x1800152dc  pop     rdi
0x1800152dd  retn
```
