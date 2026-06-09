# DeviceObject::MarkObjectInUse(void)

- ea: `0x180013acc`
- end: `0x180013b38`
- name: `?MarkObjectInUse@DeviceObject@@IEAAJXZ`
- size: `108`
- prototype: `__int64 __fastcall(DeviceObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800048b4`
- `0x1800111f0`
- `0x180013720`

## callees

- `0x180013a64`
- `0x180013acc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013ae2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013ae2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013b20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013b20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013aeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013aeb`

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
0x180013acc  mov     [rsp+arg_0], rbx
0x180013ad1  mov     [rsp+arg_8], rsi
0x180013ad6  push    rdi
0x180013ad7  sub     rsp, 20h
0x180013adb  mov     rdi, rcx
0x180013ade  add     rcx, 30h ; '0'; lpCriticalSection
0x180013ae2  call    cs:__imp_EnterCriticalSection
0x180013ae8  inc     dword ptr [rdi+5Ch]
0x180013aeb  call    cs:__imp_GetCurrentThreadId
0x180013af1  mov     rcx, rdi; this
0x180013af4  mov     [rdi+58h], eax
0x180013af7  call    ?IsValid@DeviceObject@@QEBAJXZ; DeviceObject::IsValid(void)
0x180013afc  mov     esi, eax
0x180013afe  test    eax, eax
0x180013b00  js      short loc_180013B0C
0x180013b02  inc     dword ptr [rdi+1Ch]
0x180013b05  mov     dword ptr [rdi+18h], 2
0x180013b0c  add     dword ptr [rdi+5Ch], 0FFFFFFFFh
0x180013b10  mov     edx, [rdi+5Ch]
0x180013b13  jnz     short loc_180013B1C
0x180013b15  mov     dword ptr [rdi+58h], 0
0x180013b1c  lea     rcx, [rdi+30h]; lpCriticalSection
0x180013b20  call    cs:__imp_LeaveCriticalSection
0x180013b26  mov     rbx, [rsp+28h+arg_0]
0x180013b2b  mov     eax, esi
0x180013b2d  mov     rsi, [rsp+28h+arg_8]
0x180013b32  add     rsp, 20h
0x180013b36  pop     rdi
0x180013b37  retn
```
