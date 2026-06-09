# _fcloseall

- ea: `0x100421b84`
- end: `0x100421c36`
- name: `_fcloseall`
- size: `178`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x10041f100`

## callees

- `0x10041bba0`
- `0x10041bc00`
- `0x10041c24c`
- `0x100421b84`
- `0x100422458`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x100421bf7`
- `KERNEL32!DeleteCriticalSection` at `0x100421bf7`

## pseudocode

```c
int __cdecl fcloseall()
{
  int i; // ebx
  __int64 v1; // rcx
  int v3; // [rsp+20h] [rbp-18h]

  v3 = 0;
  _acrt_lock(8);
  for ( i = 3; i != nstream; ++i )
  {
    v1 = *((_QWORD *)_piob + i);
    if ( v1 )
    {
      if ( (*(_DWORD *)(v1 + 20) & 0x2000) != 0 && fclose(*((FILE **)_piob + i)) != -1 )
        ++v3;
      DeleteCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)_piob + i) + 48LL));
      free_base(*((void **)_piob + i));
      *((_QWORD *)_piob + i) = 0;
    }
  }
  _acrt_unlock(8);
  return v3;
}

```

## disassembly

```asm
0x100421b84  mov     [rsp+arg_8], rbx
0x100421b89  push    rdi
0x100421b8a  sub     rsp, 30h
0x100421b8e  and     [rsp+38h+var_18], 0
0x100421b93  mov     ecx, 8
0x100421b98  call    __acrt_lock
0x100421b9d  nop
0x100421b9e  mov     ebx, 3
0x100421ba3  mov     [rsp+38h+var_14], ebx
0x100421ba7  cmp     ebx, cs:_nstream
0x100421bad  jz      short loc_100421C1D
0x100421baf  movsxd  rdi, ebx
0x100421bb2  mov     rax, cs:__piob
0x100421bb9  mov     rcx, [rax+rdi*8]
0x100421bbd  test    rcx, rcx
0x100421bc0  jnz     short loc_100421BC4
0x100421bc2  jmp     short loc_100421C19
0x100421bc4  mov     eax, [rcx+14h]
0x100421bc7  nop
0x100421bc8  shr     eax, 0Dh
0x100421bcb  and     al, 1
0x100421bcd  jz      short loc_100421BE8
0x100421bcf  mov     rcx, cs:__piob
0x100421bd6  mov     rcx, [rcx+rdi*8]; Stream
0x100421bda  call    fclose
0x100421bdf  cmp     eax, 0FFFFFFFFh
0x100421be2  jz      short loc_100421BE8
0x100421be4  inc     [rsp+38h+var_18]
0x100421be8  mov     rax, cs:__piob
0x100421bef  mov     rcx, [rax+rdi*8]
0x100421bf3  add     rcx, 30h ; '0'; lpCriticalSection
0x100421bf7  call    cs:__imp_DeleteCriticalSection
0x100421bfd  mov     rcx, cs:__piob
0x100421c04  mov     rcx, [rcx+rdi*8]; Block
0x100421c08  call    _free_base
0x100421c0d  mov     rax, cs:__piob
0x100421c14  and     qword ptr [rax+rdi*8], 0
0x100421c19  inc     ebx
0x100421c1b  jmp     short loc_100421BA3
0x100421c1d  mov     ecx, 8
0x100421c22  call    __acrt_unlock
0x100421c27  mov     eax, [rsp+38h+var_18]
0x100421c2b  mov     rbx, [rsp+38h+arg_8]
0x100421c30  add     rsp, 30h
0x100421c34  pop     rdi
0x100421c35  retn
0x1004254e3  push    rbp
0x1004254e5  sub     rsp, 20h
0x1004254e9  mov     rbp, rdx
0x1004254ec  mov     ecx, 8
0x1004254f1  add     rsp, 20h
0x1004254f5  pop     rbp
0x1004254f6  jmp     __acrt_unlock
```
