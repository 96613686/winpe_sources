# DeviceObject::UnmarkObjectInUse(void)

- ea: `0x180013e70`
- end: `0x180013ef8`
- name: `?UnmarkObjectInUse@DeviceObject@@IEAAXXZ`
- size: `136`
- prototype: `void __fastcall(DeviceObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800048b4`
- `0x1800111f0`
- `0x180013720`

## callees

- `0x180013c58`
- `0x180013e70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013e89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013e89`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013ed5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013ed5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013e92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013e92`

## pseudocode

```c
void __fastcall DeviceObject::UnmarkObjectInUse(DeviceObject *this)
{
  char v2; // si
  bool v3; // zf

  v2 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  ++*((_DWORD *)this + 23);
  *((_DWORD *)this + 22) = GetCurrentThreadId();
  v3 = (*((_DWORD *)this + 7))-- == 1;
  if ( v3 )
  {
    if ( *((_DWORD *)this + 6) == 2 )
    {
      *((_DWORD *)this + 6) = 1;
    }
    else if ( *((_DWORD *)this + 6) == 3 )
    {
      v2 = 1;
      *((_DWORD *)this + 6) = 4;
    }
  }
  v3 = (*((_DWORD *)this + 23))-- == 1;
  if ( v3 )
    *((_DWORD *)this + 22) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( v2 )
    DeviceObject::Uninstall(this);
}

```

## disassembly

```asm
0x180013e70  mov     [rsp+arg_8], rbx
0x180013e75  mov     [rsp+arg_10], rsi
0x180013e7a  push    rdi
0x180013e7b  sub     rsp, 20h
0x180013e7f  mov     rdi, rcx
0x180013e82  xor     sil, sil
0x180013e85  add     rcx, 30h ; '0'; lpCriticalSection
0x180013e89  call    cs:__imp_EnterCriticalSection
0x180013e8f  inc     dword ptr [rdi+5Ch]
0x180013e92  call    cs:__imp_GetCurrentThreadId
0x180013e98  or      ecx, 0FFFFFFFFh
0x180013e9b  mov     [rdi+58h], eax
0x180013e9e  add     [rdi+1Ch], ecx
0x180013ea1  jnz     short loc_180013EC2
0x180013ea3  cmp     dword ptr [rdi+18h], 2
0x180013ea7  jnz     short loc_180013EB2
0x180013ea9  mov     dword ptr [rdi+18h], 1
0x180013eb0  jmp     short loc_180013EC2
0x180013eb2  cmp     dword ptr [rdi+18h], 3
0x180013eb6  jnz     short loc_180013EC2
0x180013eb8  mov     sil, 1
0x180013ebb  mov     dword ptr [rdi+18h], 4
0x180013ec2  add     [rdi+5Ch], ecx
0x180013ec5  mov     eax, [rdi+5Ch]
0x180013ec8  jnz     short loc_180013ED1
0x180013eca  mov     dword ptr [rdi+58h], 0
0x180013ed1  lea     rcx, [rdi+30h]; lpCriticalSection
0x180013ed5  call    cs:__imp_LeaveCriticalSection
0x180013edb  test    sil, sil
0x180013ede  jz      short loc_180013EE8
0x180013ee0  mov     rcx, rdi; this
0x180013ee3  call    ?Uninstall@DeviceObject@@QEAAJXZ; DeviceObject::Uninstall(void)
0x180013ee8  mov     rbx, [rsp+28h+arg_8]
0x180013eed  mov     rsi, [rsp+28h+arg_10]
0x180013ef2  add     rsp, 20h
0x180013ef6  pop     rdi
0x180013ef7  retn
```
