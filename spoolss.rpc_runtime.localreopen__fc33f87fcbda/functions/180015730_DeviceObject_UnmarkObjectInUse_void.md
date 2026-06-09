# DeviceObject::UnmarkObjectInUse(void)

- ea: `0x180015730`
- end: `0x1800157cb`
- name: `?UnmarkObjectInUse@DeviceObject@@IEAAXXZ`
- size: `155`
- prototype: `void __fastcall(DeviceObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180004bf4`
- `0x18001285c`
- `0x180014ed0`

## callees

- `0x1800154bc`
- `0x180015730`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015749`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015749`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800157a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800157a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015758`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015758`

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
0x180015730  mov     [rsp+arg_8], rbx
0x180015735  mov     [rsp+arg_10], rsi
0x18001573a  push    rdi
0x18001573b  sub     rsp, 20h
0x18001573f  mov     rdi, rcx
0x180015742  xor     sil, sil
0x180015745  add     rcx, 30h ; '0'; lpCriticalSection
0x180015749  call    cs:__imp_EnterCriticalSection
0x180015750  nop     dword ptr [rax+rax+00h]
0x180015755  inc     dword ptr [rdi+5Ch]
0x180015758  call    cs:__imp_GetCurrentThreadId
0x18001575f  nop     dword ptr [rax+rax+00h]
0x180015764  or      ecx, 0FFFFFFFFh
0x180015767  mov     [rdi+58h], eax
0x18001576a  add     [rdi+1Ch], ecx
0x18001576d  jnz     short loc_18001578E
0x18001576f  cmp     dword ptr [rdi+18h], 2
0x180015773  jnz     short loc_18001577E
0x180015775  mov     dword ptr [rdi+18h], 1
0x18001577c  jmp     short loc_18001578E
0x18001577e  cmp     dword ptr [rdi+18h], 3
0x180015782  jnz     short loc_18001578E
0x180015784  mov     sil, 1
0x180015787  mov     dword ptr [rdi+18h], 4
0x18001578e  add     [rdi+5Ch], ecx
0x180015791  mov     eax, [rdi+5Ch]
0x180015794  jnz     short loc_18001579D
0x180015796  mov     dword ptr [rdi+58h], 0
0x18001579d  lea     rcx, [rdi+30h]; lpCriticalSection
0x1800157a1  call    cs:__imp_LeaveCriticalSection
0x1800157a8  nop     dword ptr [rax+rax+00h]
0x1800157ad  test    sil, sil
0x1800157b0  jz      short loc_1800157BA
0x1800157b2  mov     rcx, rdi; this
0x1800157b5  call    ?Uninstall@DeviceObject@@QEAAJXZ; DeviceObject::Uninstall(void)
0x1800157ba  mov     rbx, [rsp+28h+arg_8]
0x1800157bf  mov     rsi, [rsp+28h+arg_10]
0x1800157c4  add     rsp, 20h
0x1800157c8  pop     rdi
0x1800157c9  retn
```
