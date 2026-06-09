# ex_oomCheck(void *,OOM_EXCEPTIONS)

- ea: `0x1004310c0`
- end: `0x10043114a`
- name: `?ex_oomCheck@@YAXPEAXW4OOM_EXCEPTIONS@@@Z`
- size: `138`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `35`
- callee_count: `1`
- tags: ``

## callers

- `0x100430f30`
- `0x1004675e0`
- `0x100467820`
- `0x100468130`
- `0x1004686c0`
- `0x1004cd2e0`
- `0x1004cd6b0`
- `0x1004cd9d0`
- `0x1004cde10`
- `0x1004ce1e0`
- `0x1004ce4f0`
- `0x1004ce9b0`
- `0x1004cf0b0`
- `0x1004cf500`
- `0x1004cf960`
- `0x1004cfff0`
- `0x1004d0470`
- `0x1004d0910`
- `0x1004d0fb0`
- `0x1004d1400`
- `0x1004d18a0`
- `0x1004d1f00`
- `0x1004d2590`
- `0x1004d2a10`
- `0x1004d2e70`
- `0x1004d3630`
- `0x1004d3de0`
- `0x1004d4590`
- `0x1004d4cf0`
- `0x1004d5480`
- `0x1004d5c10`
- `0x1004d6d80`
- `0x1004d7090`
- `0x1004d7680`
- `0x1004d7de0`

## callees

- `0x1004310c0`

## import_xrefs

- `sqldk!SystemThread_TlsIndex` at `0x1004310d7`
- `sqldk!SystemThread_TlsOffset` at `0x1004310e8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100431103`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100431103`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100431139`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100431139`

## pseudocode

```c
void __fastcall ex_oomCheck(__int64 a1, unsigned __int8 a2)
{
  int v2; // edi
  __int64 v3; // rbx
  __int64 v4; // rax

  if ( !a1 )
  {
    v2 = a2;
    v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v4 = *(_QWORD *)(v3 + 256);
    if ( !v4 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v4 = *(_QWORD *)(v3 + 256);
    }
    ex_raise(7, 1, 17, v2, *(_QWORD *)(*(_QWORD *)(v4 + 536) + 3336LL) + 320LL);
  }
}

```

## disassembly

```asm
0x1004310c0  test    rcx, rcx
0x1004310c3  jnz     locret_100431149
0x1004310c9  push    rdi
0x1004310ca  sub     rsp, 30h
0x1004310ce  mov     r8, gs:58h
0x1004310d7  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004310de  mov     [rsp+38h+arg_0], rbx
0x1004310e3  movzx   edi, dl
0x1004310e6  mov     ecx, [rax]
0x1004310e8  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004310ef  mov     ebx, [rax]
0x1004310f1  add     rbx, [r8+rcx*8]
0x1004310f5  mov     rax, [rbx+100h]
0x1004310fc  test    rax, rax
0x1004310ff  jnz     short loc_100431110
0x100431101  xor     ecx, ecx
0x100431103  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100431109  mov     rax, [rbx+100h]
0x100431110  mov     rax, [rax+218h]
0x100431117  mov     edx, 1
0x10043111c  mov     r9d, edi
0x10043111f  mov     rcx, [rax+0D08h]
0x100431126  lea     r8d, [rdx+10h]
0x10043112a  add     rcx, 140h
0x100431131  mov     [rsp+38h+var_18], rcx
0x100431136  lea     ecx, [rdx+6]
0x100431139  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10043113f  mov     rbx, [rsp+38h+arg_0]
0x100431144  add     rsp, 30h
0x100431148  pop     rdi
0x100431149  retn
```
