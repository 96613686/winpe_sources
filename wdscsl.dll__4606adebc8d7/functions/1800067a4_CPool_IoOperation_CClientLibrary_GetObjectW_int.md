# CPool<IoOperation<CClientLibrary>>::GetObjectW(int)

- ea: `0x1800067a4`
- end: `0x18000688f`
- name: `?GetObjectW@?$CPool@U?$IoOperation@VCClientLibrary@@@@@@QEAAPEAU?$IoOperation@VCClientLibrary@@@@H@Z`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008174`

## callees

- `0x1800017d8`
- `0x1800067a4`
- `0x18000d6d2`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x1800067b3`
- `KERNEL32!InterlockedPopEntrySList` at `0x1800067b3`

## pseudocode

```c
PSLIST_ENTRY __fastcall CPool<IoOperation<CClientLibrary>>::GetObjectW(__int64 a1)
{
  PSLIST_ENTRY v2; // rbx
  PSLIST_ENTRY v3; // rax
  struct _SLIST_ENTRY *v4; // rax

  v2 = 0;
  v3 = InterlockedPopEntrySList((PSLIST_HEADER)a1);
  if ( v3 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 16));
    v2 = v3 - 80;
  }
  if ( !v2 )
  {
    v4 = (struct _SLIST_ENTRY *)operator new(0x510u, (const struct std::nothrow_t *)&std::nothrow);
    v2 = v4;
    if ( !v4 )
      return 0;
    *v4 = 0;
    v4[1] = 0;
    v4[2].Next = 0;
    *((_DWORD *)&v4[2].Next + 2) = 0;
    v4[3].Next = 0;
    *((_DWORD *)&v4[3].Next + 2) = 0;
    memset_0(&v4[4], 0, 0x80u);
    LODWORD(v2[12].Next) = 0;
    memset_0((char *)&v2[12].Next + 4, 0, 0x41Cu);
    LODWORD(v2[78].Next) = 0;
    *((_QWORD *)&v2[78].Next + 1) = 0;
    v2[79].Next = 0;
    *((_QWORD *)&v2[79].Next + 1) = 0;
    v2[80] = 0;
  }
  _InterlockedExchange((volatile __int32 *)&v2[78], 2);
  *((_QWORD *)&v2[78].Next + 1) = a1;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 32));
  return v2;
}

```

## disassembly

```asm
0x1800067a4  mov     [rsp+arg_0], rbx
0x1800067a9  push    rdi
0x1800067aa  sub     rsp, 20h
0x1800067ae  mov     rdi, rcx
0x1800067b1  xor     ebx, ebx
0x1800067b3  call    cs:__imp_InterlockedPopEntrySList
0x1800067ba  nop     dword ptr [rax+rax+00h]
0x1800067bf  test    rax, rax
0x1800067c2  jz      short loc_1800067CF
0x1800067c4  lock dec dword ptr [rdi+10h]
0x1800067c8  lea     rbx, [rax-500h]
0x1800067cf  test    rbx, rbx
0x1800067d2  jnz     loc_180006866
0x1800067d8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800067df  mov     ecx, 510h; unsigned __int64
0x1800067e4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800067e9  mov     rbx, rax
0x1800067ec  test    rax, rax
0x1800067ef  jz      loc_18000688B
0x1800067f5  xorps   xmm0, xmm0
0x1800067f8  lea     rcx, [rax+40h]; void *
0x1800067fc  movups  xmmword ptr [rax], xmm0
0x1800067ff  xor     edx, edx; Val
0x180006801  mov     r8d, 80h; Size
0x180006807  movups  xmmword ptr [rax+10h], xmm0
0x18000680b  and     qword ptr [rax+20h], 0
0x180006810  and     dword ptr [rax+28h], 0
0x180006814  and     qword ptr [rax+30h], 0
0x180006819  and     dword ptr [rax+38h], 0
0x18000681d  call    memset_0
0x180006822  and     dword ptr [rbx+0C0h], 0
0x180006829  lea     rcx, [rbx+0C4h]; void *
0x180006830  xor     edx, edx; Val
0x180006832  mov     r8d, 41Ch; Size
0x180006838  call    memset_0
0x18000683d  and     dword ptr [rbx+4E0h], 0
0x180006844  xorps   xmm0, xmm0
0x180006847  and     qword ptr [rbx+4E8h], 0
0x18000684f  and     qword ptr [rbx+4F0h], 0
0x180006857  and     qword ptr [rbx+4F8h], 0
0x18000685f  movups  xmmword ptr [rbx+500h], xmm0
0x180006866  mov     ecx, 2
0x18000686b  xchg    ecx, [rbx+4E0h]
0x180006871  mov     [rbx+4E8h], rdi
0x180006878  lock inc dword ptr [rdi+20h]
0x18000687c  mov     rax, rbx
0x18000687f  mov     rbx, [rsp+28h+arg_0]
0x180006884  add     rsp, 20h
0x180006888  pop     rdi
0x180006889  retn
0x18000688b  xor     ebx, ebx
0x18000688d  jmp     short loc_18000687C
```
