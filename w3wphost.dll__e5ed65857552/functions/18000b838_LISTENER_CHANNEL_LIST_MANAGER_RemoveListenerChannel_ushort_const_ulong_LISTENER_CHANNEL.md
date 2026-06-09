# LISTENER_CHANNEL_LIST_MANAGER::RemoveListenerChannel(ushort const *,ulong,LISTENER_CHANNEL * *)

- ea: `0x18000b838`
- end: `0x18000b8e1`
- name: `?RemoveListenerChannel@LISTENER_CHANNEL_LIST_MANAGER@@QEAAJPEBGKPEAPEAVLISTENER_CHANNEL@@@Z`
- size: `169`
- prototype: `int(LISTENER_CHANNEL_LIST_MANAGER *__hidden this, const unsigned __int16 *, unsigned int, struct LISTENER_CHANNEL **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b1a0`
- `0x18000b8e8`
- `0x18000bdc4`

## callees

- `0x18000b838`
- `0x18000e010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000b877`
- `msvcrt!_wcsicmp` at `0x18000b877`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b865`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b865`

## pseudocode

```c
__int64 __fastcall LISTENER_CHANNEL_LIST_MANAGER::RemoveListenerChannel(
        LISTENER_CHANNEL_LIST_MANAGER *this,
        const unsigned __int16 *a2,
        int a3,
        struct LISTENER_CHANNEL **a4)
{
  char *v4; // r14
  char *i; // rbx
  struct LISTENER_CHANNEL *v9; // rdi
  const wchar_t *Str; // rax
  char *v11; // rax
  char **v12; // rcx

  v4 = (char *)this + 8;
  for ( i = (char *)*((_QWORD *)this + 1); ; i = *(char **)i )
  {
    if ( i == v4 )
      return 2147943568LL;
    v9 = (struct LISTENER_CHANNEL *)(i - 248);
    Str = STRU::QueryStr((STRU *)(i - 232));
    if ( !_wcsicmp(Str, a2) && *((_DWORD *)v9 + 18) == a3 )
      break;
  }
  v11 = *(char **)i;
  if ( *(char **)(*(_QWORD *)i + 8LL) != i || (v12 = (char **)*((_QWORD *)i + 1), *v12 != i) )
    __fastfail(3u);
  *v12 = v11;
  *((_QWORD *)v11 + 1) = v12;
  if ( a4 )
    *a4 = v9;
  else
    (*(void (__fastcall **)(_QWORD *))(*(_QWORD *)v9 + 8LL))((_QWORD *)i - 31);
  return 0;
}

```

## disassembly

```asm
0x18000b838  push    rbx
0x18000b83a  push    rbp
0x18000b83b  push    rsi
0x18000b83c  push    rdi
0x18000b83d  push    r14
0x18000b83f  push    r15
0x18000b841  sub     rsp, 28h
0x18000b845  lea     r14, [rcx+8]
0x18000b849  mov     rsi, r9
0x18000b84c  mov     rbx, [r14]
0x18000b84f  mov     ebp, r8d
0x18000b852  mov     r15, rdx
0x18000b855  cmp     rbx, r14
0x18000b858  jz      short loc_18000B8CE
0x18000b85a  lea     rdi, [rbx-0F8h]
0x18000b861  lea     rcx, [rdi+10h]
0x18000b865  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000b86c  nop     dword ptr [rax+rax+00h]
0x18000b871  mov     rcx, rax; String1
0x18000b874  mov     rdx, r15; String2
0x18000b877  call    cs:__imp__wcsicmp
0x18000b87e  nop     dword ptr [rax+rax+00h]
0x18000b883  test    eax, eax
0x18000b885  jnz     short loc_18000B88C
0x18000b887  cmp     [rdi+48h], ebp
0x18000b88a  jz      short loc_18000B891
0x18000b88c  mov     rbx, [rbx]
0x18000b88f  jmp     short loc_18000B855
0x18000b891  mov     rax, [rbx]
0x18000b894  cmp     [rax+8], rbx
0x18000b898  jnz     short loc_18000B8C7
0x18000b89a  mov     rcx, [rbx+8]
0x18000b89e  cmp     [rcx], rbx
0x18000b8a1  jnz     short loc_18000B8C7
0x18000b8a3  mov     [rcx], rax
0x18000b8a6  mov     [rax+8], rcx
0x18000b8aa  test    rsi, rsi
0x18000b8ad  jz      short loc_18000B8B4
0x18000b8af  mov     [rsi], rdi
0x18000b8b2  jmp     short loc_18000B8C3
0x18000b8b4  mov     rax, [rdi]
0x18000b8b7  mov     rcx, rdi
0x18000b8ba  mov     rax, [rax+8]
0x18000b8be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8c3  xor     eax, eax
0x18000b8c5  jmp     short loc_18000B8D3
0x18000b8c7  mov     ecx, 3
0x18000b8cc  int     29h; Win8: RtlFailFast(ecx)
0x18000b8ce  mov     eax, 80070490h
0x18000b8d3  add     rsp, 28h
0x18000b8d7  pop     r15
0x18000b8d9  pop     r14
0x18000b8db  pop     rdi
0x18000b8dc  pop     rsi
0x18000b8dd  pop     rbp
0x18000b8de  pop     rbx
0x18000b8df  retn
```
