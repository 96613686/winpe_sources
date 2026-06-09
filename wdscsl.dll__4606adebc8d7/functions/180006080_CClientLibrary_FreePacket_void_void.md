# CClientLibrary::FreePacket(void *,void *)

- ea: `0x180006080`
- end: `0x1800060ec`
- name: `?FreePacket@CClientLibrary@@QEAAKPEAX0@Z`
- size: `108`
- prototype: `unsigned int __fastcall(CClientLibrary *__hidden this, void *, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180005558`
- `0x18000be50`
- `0x18000c594`
- `0x18000c5dc`

## callees

- `0x180006080`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CClientLibrary::FreePacket(CClientLibrary *this, void *a2, _QWORD *a3)
{
  unsigned int v3; // ebx
  __int64 v5; // rcx

  v3 = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 10, 0) )
  {
    if ( a3 )
    {
      if ( a2 )
      {
        if ( *((_DWORD *)this + 12) )
          return (*((unsigned int (__fastcall **)(void *, _QWORD))this + 9))(a2, 0);
        else
          return 6;
      }
      else
      {
        v5 = *(a3 - 2);
        if ( v5 )
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD *, CClientLibrary *))(*(_QWORD *)v5 + 8LL))(v5, 0, a3, this);
      }
    }
    else
    {
      return 87;
    }
  }
  else
  {
    return 5023;
  }
  return v3;
}

```

## disassembly

```asm
0x180006080  push    rbx
0x180006082  sub     rsp, 20h
0x180006086  xor     ebx, ebx
0x180006088  mov     r10, rdx
0x18000608b  mov     eax, ebx
0x18000608d  mov     r9, rcx
0x180006090  lock xadd [rcx+28h], eax
0x180006095  test    eax, eax
0x180006097  jnz     short loc_1800060A0
0x180006099  mov     ebx, 139Fh
0x18000609e  jmp     short loc_1800060E3
0x1800060a0  test    r8, r8
0x1800060a3  jnz     short loc_1800060AB
0x1800060a5  lea     ebx, [r8+57h]
0x1800060a9  jmp     short loc_1800060E3
0x1800060ab  test    r10, r10
0x1800060ae  jz      short loc_1800060CE
0x1800060b0  cmp     [rcx+30h], ebx
0x1800060b3  jnz     short loc_1800060BC
0x1800060b5  mov     ebx, 6
0x1800060ba  jmp     short loc_1800060E3
0x1800060bc  mov     rax, [r9+48h]
0x1800060c0  xor     edx, edx
0x1800060c2  mov     rcx, r10
0x1800060c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060ca  mov     ebx, eax
0x1800060cc  jmp     short loc_1800060E3
0x1800060ce  mov     rcx, [r8-10h]
0x1800060d2  test    rcx, rcx
0x1800060d5  jz      short loc_1800060E3
0x1800060d7  mov     rax, [rcx]
0x1800060da  mov     rax, [rax+8]
0x1800060de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060e3  mov     eax, ebx
0x1800060e5  add     rsp, 20h
0x1800060e9  pop     rbx
0x1800060ea  retn
```
