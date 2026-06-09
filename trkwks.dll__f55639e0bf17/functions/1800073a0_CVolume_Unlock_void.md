# CVolume::Unlock(void)

- ea: `0x1800073a0`
- end: `0x1800073ff`
- name: `?Unlock@CVolume@@AEAAKXZ`
- size: `95`
- prototype: `__int64 __fastcall(CVolume *this)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x18000297c`
- `0x180002b50`
- `0x180003428`
- `0x180003798`
- `0x180006a80`
- `0x18000756c`
- `0x180007c08`
- `0x180009364`
- `0x18000d0a4`
- `0x18000f22c`
- `0x18000f4bc`
- `0x18000f66c`

## callees

- `0x1800066c0`
- `0x1800073a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800073c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800073e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800073c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800073e4`

## pseudocode

```c
__int64 __fastcall CVolume::Unlock(CVolume *this)
{
  bool v1; // zf
  unsigned int v3; // edi
  int v4; // eax

  v1 = (*((_DWORD *)this + 13))-- == 1;
  v3 = *((_DWORD *)this + 13);
  if ( v1 && (v4 = *((_DWORD *)this + 4), (v4 & 0x20) != 0) )
  {
    *((_DWORD *)this + 4) = v4 & 0xFFFFFFDF;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
    PLogFileNotify::Release(this);
    return v3;
  }
  else
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
    return v3;
  }
}

```

## disassembly

```asm
0x1800073a0  mov     [rsp+arg_0], rbx
0x1800073a5  push    rdi
0x1800073a6  sub     rsp, 20h
0x1800073aa  add     dword ptr [rcx+34h], 0FFFFFFFFh
0x1800073ae  mov     rbx, rcx
0x1800073b1  mov     edi, [rcx+34h]
0x1800073b4  jnz     short loc_1800073BD
0x1800073b6  mov     eax, [rcx+10h]
0x1800073b9  test    al, 20h
0x1800073bb  jnz     short loc_1800073D7
0x1800073bd  add     rcx, 0A8h; lpCriticalSection
0x1800073c4  call    cs:__imp_LeaveCriticalSection
0x1800073ca  mov     eax, edi
0x1800073cc  mov     rbx, [rsp+28h+arg_0]
0x1800073d1  add     rsp, 20h
0x1800073d5  pop     rdi
0x1800073d6  retn
0x1800073d7  and     eax, 0FFFFFFDFh
0x1800073da  mov     [rcx+10h], eax
0x1800073dd  add     rcx, 0A8h; lpCriticalSection
0x1800073e4  call    cs:__imp_LeaveCriticalSection
0x1800073ea  mov     rcx, rbx; this
0x1800073ed  call    ?Release@PLogFileNotify@@QEAAKXZ; PLogFileNotify::Release(void)
0x1800073f2  mov     rbx, [rsp+28h+arg_0]
0x1800073f7  mov     eax, edi
0x1800073f9  add     rsp, 20h
0x1800073fd  pop     rdi
0x1800073fe  retn
```
