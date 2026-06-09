# PMH_PING_CALLBACK::Release(void)

- ea: `0x180003700`
- end: `0x180003772`
- name: `?Release@PMH_PING_CALLBACK@@UEAAKXZ`
- size: `114`
- prototype: `unsigned int __fastcall(PMH_PING_CALLBACK *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180003700`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003750`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003750`

## pseudocode

```c
__int64 __fastcall PMH_PING_CALLBACK::Release(PMH_PING_CALLBACK *this)
{
  unsigned __int32 v2; // edi
  __int64 v3; // rcx

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 3);
  if ( !v2 && this )
  {
    *(_QWORD *)this = &PMH_PING_CALLBACK::`vftable';
    v3 = *((_QWORD *)this + 2);
    if ( v3 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
      *((_QWORD *)this + 2) = 0;
    }
    if ( *((_DWORD *)this + 6) == 1 )
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    *((_DWORD *)this + 2) = 1129072720;
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x180003700  mov     [rsp+arg_0], rbx
0x180003705  push    rdi
0x180003706  sub     rsp, 20h
0x18000370a  mov     rbx, rcx
0x18000370d  or      edi, 0FFFFFFFFh
0x180003710  lock xadd [rcx+0Ch], edi
0x180003715  sub     edi, 1
0x180003718  jnz     short loc_180003765
0x18000371a  test    rcx, rcx
0x18000371d  jz      short loc_180003765
0x18000371f  lea     rax, ??_7PMH_PING_CALLBACK@@6B@; const PMH_PING_CALLBACK::`vftable'
0x180003726  mov     [rcx], rax
0x180003729  mov     rcx, [rcx+10h]
0x18000372d  test    rcx, rcx
0x180003730  jz      short loc_180003746
0x180003732  mov     rax, [rcx]
0x180003735  mov     rax, [rax+8]
0x180003739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000373e  mov     qword ptr [rbx+10h], 0
0x180003746  cmp     dword ptr [rbx+18h], 1
0x18000374a  jnz     short loc_180003756
0x18000374c  lea     rcx, [rbx+20h]; lpCriticalSection
0x180003750  call    cs:__imp_DeleteCriticalSection
0x180003756  mov     rcx, rbx; Block
0x180003759  mov     dword ptr [rbx+8], 434C4850h
0x180003760  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003765  mov     rbx, [rsp+28h+arg_0]
0x18000376a  mov     eax, edi
0x18000376c  add     rsp, 20h
0x180003770  pop     rdi
0x180003771  retn
```
