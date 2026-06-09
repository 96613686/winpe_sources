# CPool<ProviderRequest>::GetObjectW(int)

- ea: `0x180010a9c`
- end: `0x180010b3d`
- name: `?GetObjectW@?$CPool@UProviderRequest@@@@QEAAPEAUProviderRequest@@H@Z`
- size: `161`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010e90`

## callees

- `0x18000195c`
- `0x180010a00`
- `0x180010a9c`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x180010aab`
- `KERNEL32!InterlockedPopEntrySList` at `0x180010aab`

## pseudocode

```c
PSLIST_ENTRY __fastcall CPool<ProviderRequest>::GetObjectW(__int64 a1)
{
  PSLIST_ENTRY v2; // rbx
  PSLIST_ENTRY v3; // rax
  struct _SLIST_ENTRY *v4; // rax

  v2 = 0;
  v3 = InterlockedPopEntrySList((PSLIST_HEADER)a1);
  if ( v3 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 16));
    v2 = v3 - 136;
  }
  if ( !v2 )
  {
    v4 = (struct _SLIST_ENTRY *)operator new(0x890u, (const struct std::nothrow_t *)&std::nothrow);
    v2 = v4;
    if ( !v4 )
      return 0;
    *((_QWORD *)&v4[134].Next + 1) = 0;
    v4[135].Next = 0;
    *((_QWORD *)&v4->Next + 1) = 0;
    v4[1].Next = 0;
    v4->Next = 0;
    *((_QWORD *)&v4[1].Next + 1) = 0;
    LODWORD(v4[2].Next) = 0;
    ProviderRequest::Cleanup((ProviderRequest *)v4);
  }
  _InterlockedExchange((volatile __int32 *)&v2[133].Next + 3, 2);
  v2[134].Next = (struct _SLIST_ENTRY *)a1;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 32));
  return v2;
}

```

## disassembly

```asm
0x180010a9c  mov     [rsp+arg_0], rbx
0x180010aa1  push    rdi
0x180010aa2  sub     rsp, 20h
0x180010aa6  mov     rdi, rcx
0x180010aa9  xor     ebx, ebx
0x180010aab  call    cs:__imp_InterlockedPopEntrySList
0x180010ab2  nop     dword ptr [rax+rax+00h]
0x180010ab7  test    rax, rax
0x180010aba  jz      short loc_180010AC7
0x180010abc  lock dec dword ptr [rdi+10h]
0x180010ac0  lea     rbx, [rax-880h]
0x180010ac7  test    rbx, rbx
0x180010aca  jnz     short loc_180010B14
0x180010acc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010ad3  mov     ecx, 890h; unsigned __int64
0x180010ad8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010add  mov     rbx, rax
0x180010ae0  test    rax, rax
0x180010ae3  jz      short loc_180010B39
0x180010ae5  and     qword ptr [rax+868h], 0
0x180010aed  mov     rcx, rax; this
0x180010af0  and     qword ptr [rax+870h], 0
0x180010af8  and     qword ptr [rax+8], 0
0x180010afd  and     qword ptr [rax+10h], 0
0x180010b02  and     qword ptr [rax], 0
0x180010b06  and     qword ptr [rax+18h], 0
0x180010b0b  and     dword ptr [rax+20h], 0
0x180010b0f  call    ?Cleanup@ProviderRequest@@QEAAXXZ; ProviderRequest::Cleanup(void)
0x180010b14  mov     ecx, 2
0x180010b19  xchg    ecx, [rbx+85Ch]
0x180010b1f  mov     [rbx+860h], rdi
0x180010b26  lock inc dword ptr [rdi+20h]
0x180010b2a  mov     rax, rbx
0x180010b2d  mov     rbx, [rsp+28h+arg_0]
0x180010b32  add     rsp, 20h
0x180010b36  pop     rdi
0x180010b37  retn
0x180010b39  xor     ebx, ebx
0x180010b3b  jmp     short loc_180010B2A
```
