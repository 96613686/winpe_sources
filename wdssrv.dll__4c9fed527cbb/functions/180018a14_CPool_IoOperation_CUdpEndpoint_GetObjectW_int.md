# CPool<IoOperation<CUdpEndpoint>>::GetObjectW(int)

- ea: `0x180018a14`
- end: `0x180018aff`
- name: `?GetObjectW@?$CPool@U?$IoOperation@VCUdpEndpoint@@@@@@QEAAPEAU?$IoOperation@VCUdpEndpoint@@@@H@Z`
- size: `235`
- prototype: `PSLIST_ENTRY __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180019498`
- `0x180019c3c`
- `0x180019d14`

## callees

- `0x18000195c`
- `0x180018a14`
- `0x18001c12a`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x180018a23`
- `KERNEL32!InterlockedPopEntrySList` at `0x180018a23`

## pseudocode

```c
PSLIST_ENTRY __fastcall CPool<IoOperation<CUdpEndpoint>>::GetObjectW(__int64 a1)
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
0x180018a14  mov     [rsp+arg_0], rbx
0x180018a19  push    rdi
0x180018a1a  sub     rsp, 20h
0x180018a1e  mov     rdi, rcx
0x180018a21  xor     ebx, ebx
0x180018a23  call    cs:__imp_InterlockedPopEntrySList
0x180018a2a  nop     dword ptr [rax+rax+00h]
0x180018a2f  test    rax, rax
0x180018a32  jz      short loc_180018A3F
0x180018a34  lock dec dword ptr [rdi+10h]
0x180018a38  lea     rbx, [rax-500h]
0x180018a3f  test    rbx, rbx
0x180018a42  jnz     loc_180018AD6
0x180018a48  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018a4f  mov     ecx, 510h; unsigned __int64
0x180018a54  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180018a59  mov     rbx, rax
0x180018a5c  test    rax, rax
0x180018a5f  jz      loc_180018AFB
0x180018a65  xorps   xmm0, xmm0
0x180018a68  lea     rcx, [rax+40h]; void *
0x180018a6c  movups  xmmword ptr [rax], xmm0
0x180018a6f  xor     edx, edx; Val
0x180018a71  mov     r8d, 80h; Size
0x180018a77  movups  xmmword ptr [rax+10h], xmm0
0x180018a7b  and     qword ptr [rax+20h], 0
0x180018a80  and     dword ptr [rax+28h], 0
0x180018a84  and     qword ptr [rax+30h], 0
0x180018a89  and     dword ptr [rax+38h], 0
0x180018a8d  call    memset_0
0x180018a92  and     dword ptr [rbx+0C0h], 0
0x180018a99  lea     rcx, [rbx+0C4h]; void *
0x180018aa0  xor     edx, edx; Val
0x180018aa2  mov     r8d, 41Ch; Size
0x180018aa8  call    memset_0
0x180018aad  and     dword ptr [rbx+4E0h], 0
0x180018ab4  xorps   xmm0, xmm0
0x180018ab7  and     qword ptr [rbx+4E8h], 0
0x180018abf  and     qword ptr [rbx+4F0h], 0
0x180018ac7  and     qword ptr [rbx+4F8h], 0
0x180018acf  movups  xmmword ptr [rbx+500h], xmm0
0x180018ad6  mov     ecx, 2
0x180018adb  xchg    ecx, [rbx+4E0h]
0x180018ae1  mov     [rbx+4E8h], rdi
0x180018ae8  lock inc dword ptr [rdi+20h]
0x180018aec  mov     rax, rbx
0x180018aef  mov     rbx, [rsp+28h+arg_0]
0x180018af4  add     rsp, 20h
0x180018af8  pop     rdi
0x180018af9  retn
0x180018afb  xor     ebx, ebx
0x180018afd  jmp     short loc_180018AEC
```
