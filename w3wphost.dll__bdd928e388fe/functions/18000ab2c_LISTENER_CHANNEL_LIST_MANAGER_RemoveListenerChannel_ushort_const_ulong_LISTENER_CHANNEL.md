# LISTENER_CHANNEL_LIST_MANAGER::RemoveListenerChannel(ushort const *,ulong,LISTENER_CHANNEL * *)

- ea: `0x18000ab2c`
- end: `0x18000abc8`
- name: `?RemoveListenerChannel@LISTENER_CHANNEL_LIST_MANAGER@@QEAAJPEBGKPEAPEAVLISTENER_CHANNEL@@@Z`
- size: `156`
- prototype: `int(LISTENER_CHANNEL_LIST_MANAGER *__hidden this, const unsigned __int16 *, unsigned int, struct LISTENER_CHANNEL **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a4b0`
- `0x18000abd0`
- `0x18000affc`

## callees

- `0x18000ab2c`
- `0x18000d010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000ab65`
- `msvcrt!_wcsicmp` at `0x18000ab65`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000ab59`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000ab59`

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
0x18000ab2c  push    rbx
0x18000ab2e  push    rbp
0x18000ab2f  push    rsi
0x18000ab30  push    rdi
0x18000ab31  push    r14
0x18000ab33  push    r15
0x18000ab35  sub     rsp, 28h
0x18000ab39  lea     r14, [rcx+8]
0x18000ab3d  mov     rsi, r9
0x18000ab40  mov     rbx, [r14]
0x18000ab43  mov     ebp, r8d
0x18000ab46  mov     r15, rdx
0x18000ab49  cmp     rbx, r14
0x18000ab4c  jz      short loc_18000ABB6
0x18000ab4e  lea     rdi, [rbx-0F8h]
0x18000ab55  lea     rcx, [rdi+10h]
0x18000ab59  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000ab5f  mov     rcx, rax; String1
0x18000ab62  mov     rdx, r15; String2
0x18000ab65  call    cs:__imp__wcsicmp
0x18000ab6b  test    eax, eax
0x18000ab6d  jnz     short loc_18000AB74
0x18000ab6f  cmp     [rdi+48h], ebp
0x18000ab72  jz      short loc_18000AB79
0x18000ab74  mov     rbx, [rbx]
0x18000ab77  jmp     short loc_18000AB49
0x18000ab79  mov     rax, [rbx]
0x18000ab7c  cmp     [rax+8], rbx
0x18000ab80  jnz     short loc_18000ABAF
0x18000ab82  mov     rcx, [rbx+8]
0x18000ab86  cmp     [rcx], rbx
0x18000ab89  jnz     short loc_18000ABAF
0x18000ab8b  mov     [rcx], rax
0x18000ab8e  mov     [rax+8], rcx
0x18000ab92  test    rsi, rsi
0x18000ab95  jz      short loc_18000AB9C
0x18000ab97  mov     [rsi], rdi
0x18000ab9a  jmp     short loc_18000ABAB
0x18000ab9c  mov     rax, [rdi]
0x18000ab9f  mov     rcx, rdi
0x18000aba2  mov     rax, [rax+8]
0x18000aba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abab  xor     eax, eax
0x18000abad  jmp     short loc_18000ABBB
0x18000abaf  mov     ecx, 3
0x18000abb4  int     29h; Win8: RtlFailFast(ecx)
0x18000abb6  mov     eax, 80070490h
0x18000abbb  add     rsp, 28h
0x18000abbf  pop     r15
0x18000abc1  pop     r14
0x18000abc3  pop     rdi
0x18000abc4  pop     rsi
0x18000abc5  pop     rbp
0x18000abc6  pop     rbx
0x18000abc7  retn
```
