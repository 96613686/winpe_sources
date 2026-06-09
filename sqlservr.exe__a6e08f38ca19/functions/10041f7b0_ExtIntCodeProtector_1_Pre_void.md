# ExtIntCodeProtector<1>::Pre(void)

- ea: `0x10041f7b0`
- end: `0x10041f856`
- name: `?Pre@?$ExtIntCodeProtector@$00@@QEAAJXZ`
- size: `166`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x10041ed30`
- `0x10041ee70`

## callees

- `0x10041f7b0`

## import_xrefs

- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041f7ea`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041f832`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041f7ea`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041f832`
- `sqldk!SystemThread_TlsOffset` at `0x10041f7cf`
- `sqldk!SystemThread_TlsOffset` at `0x10041f817`
- `sqldk!SystemThread_TlsIndex` at `0x10041f7c6`
- `sqldk!SystemThread_TlsIndex` at `0x10041f80e`

## pseudocode

```c
__int64 __fastcall ExtIntCodeProtector<1>::Pre(int *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rax

  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v3 = *(_QWORD *)(v2 + 256);
  if ( !v3 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v3 = *(_QWORD *)(v2 + 256);
  }
  *a1 = (*(_DWORD *)(v3 + 616) >> 9) & 1;
  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v5 = *(_QWORD *)(v4 + 256);
  if ( !v5 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v5 = *(_QWORD *)(v4 + 256);
  }
  *(_DWORD *)(v5 + 616) |= 0x200u;
  return 0;
}

```

## disassembly

```asm
0x10041f7b0  mov     [rsp+arg_0], rbx
0x10041f7b5  push    rdi
0x10041f7b6  sub     rsp, 20h
0x10041f7ba  mov     r8, gs:58h
0x10041f7c3  mov     rdi, rcx
0x10041f7c6  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041f7cd  mov     edx, [rax]
0x10041f7cf  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041f7d6  mov     ebx, [rax]
0x10041f7d8  add     rbx, [r8+rdx*8]
0x10041f7dc  mov     rax, [rbx+100h]
0x10041f7e3  test    rax, rax
0x10041f7e6  jnz     short loc_10041F7F7
0x10041f7e8  xor     ecx, ecx
0x10041f7ea  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041f7f0  mov     rax, [rbx+100h]
0x10041f7f7  mov     eax, [rax+268h]
0x10041f7fd  shr     eax, 9
0x10041f800  and     eax, 1
0x10041f803  mov     [rdi], eax
0x10041f805  mov     rdx, gs:58h
0x10041f80e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041f815  mov     ecx, [rax]
0x10041f817  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041f81e  mov     ebx, [rax]
0x10041f820  add     rbx, [rdx+rcx*8]
0x10041f824  mov     rax, [rbx+100h]
0x10041f82b  test    rax, rax
0x10041f82e  jnz     short loc_10041F83F
0x10041f830  xor     ecx, ecx
0x10041f832  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041f838  mov     rax, [rbx+100h]
0x10041f83f  or      dword ptr [rax+268h], 200h
0x10041f849  mov     rbx, [rsp+28h+arg_0]
0x10041f84e  xor     eax, eax
0x10041f850  add     rsp, 20h
0x10041f854  pop     rdi
0x10041f855  retn
```
