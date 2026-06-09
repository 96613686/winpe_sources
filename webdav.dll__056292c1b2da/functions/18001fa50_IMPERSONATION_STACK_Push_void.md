# IMPERSONATION_STACK::Push(void *)

- ea: `0x18001fa50`
- end: `0x18001fae9`
- name: `?Push@IMPERSONATION_STACK@@QEAAJPEAX@Z`
- size: `153`
- prototype: `int(IMPERSONATION_STACK *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f588`
- `0x18001f76c`

## callees

- `0x1800011d4`
- `0x18001fa50`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001faaf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001faaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fab9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fab9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001fad2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001fad2`

## pseudocode

```c
int __fastcall IMPERSONATION_STACK::Push(IMPERSONATION_STACK *this, void *a2)
{
  int result; // eax
  __int64 v5; // rax
  _QWORD *v6; // rax

  if ( !a2 )
    return -2147024809;
  v5 = *((_QWORD *)this + 1);
  if ( v5 && *(void **)(v5 + 8) == a2 )
  {
    ++*(_DWORD *)(v5 + 16);
    return 0;
  }
  v6 = operator new(0x18u);
  if ( !v6 )
    return -2147024888;
  v6[1] = a2;
  *((_DWORD *)v6 + 4) = 1;
  *v6 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = v6;
  if ( RevertToSelf() && SetThreadToken(0, a2) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18001fa50  mov     [rsp+arg_0], rbx
0x18001fa55  push    rdi
0x18001fa56  sub     rsp, 20h
0x18001fa5a  mov     rbx, rdx
0x18001fa5d  mov     rdi, rcx
0x18001fa60  test    rdx, rdx
0x18001fa63  jnz     short loc_18001FA6C
0x18001fa65  mov     eax, 80070057h
0x18001fa6a  jmp     short loc_18001FADE
0x18001fa6c  mov     rax, [rcx+8]
0x18001fa70  test    rax, rax
0x18001fa73  jz      short loc_18001FA80
0x18001fa75  cmp     [rax+8], rbx
0x18001fa79  jnz     short loc_18001FA80
0x18001fa7b  inc     dword ptr [rax+10h]
0x18001fa7e  jmp     short loc_18001FADC
0x18001fa80  mov     ecx, 18h; Size
0x18001fa85  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fa8a  mov     rcx, rax
0x18001fa8d  test    rax, rax
0x18001fa90  jnz     short loc_18001FA99
0x18001fa92  mov     eax, 80070008h
0x18001fa97  jmp     short loc_18001FADE
0x18001fa99  mov     [rax+8], rbx
0x18001fa9d  mov     dword ptr [rax+10h], 1
0x18001faa4  mov     rax, [rdi+8]
0x18001faa8  mov     [rcx], rax
0x18001faab  mov     [rdi+8], rcx
0x18001faaf  call    cs:__imp_RevertToSelf
0x18001fab5  test    eax, eax
0x18001fab7  jnz     short loc_18001FACD
0x18001fab9  call    cs:__imp_GetLastError
0x18001fabf  test    eax, eax
0x18001fac1  jle     short loc_18001FADE
0x18001fac3  movzx   eax, ax
0x18001fac6  or      eax, 80070000h
0x18001facb  jmp     short loc_18001FADE
0x18001facd  mov     rdx, rbx; Token
0x18001fad0  xor     ecx, ecx; Thread
0x18001fad2  call    cs:__imp_SetThreadToken
0x18001fad8  test    eax, eax
0x18001fada  jz      short loc_18001FAB9
0x18001fadc  xor     eax, eax
0x18001fade  mov     rbx, [rsp+28h+arg_0]
0x18001fae3  add     rsp, 20h
0x18001fae7  pop     rdi
0x18001fae8  retn
```
