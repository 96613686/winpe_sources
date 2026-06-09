# OutpProcessRingResult

- ea: `0x140004790`
- end: `0x140004853`
- name: `OutpProcessRingResult`
- size: `195`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1400037e0`
- `0x140003f40`
- `0x140004cc0`
- `0x140005300`
- `0x140005750`

## callees

- `0x140004790`
- `0x14000a204`
- `0x140011ed0`

## pseudocode

```c
__int64 __fastcall OutpProcessRingResult(__int64 *a1, __int64 a2)
{
  __int64 v4; // rdi

  if ( (int)a2 < 0 )
  {
    if ( (_DWORD)a2 == -2147483643 )
    {
      if ( *((_DWORD *)a1 + 66) != 5 )
      {
        *((_DWORD *)a1 + 66) = 2;
        if ( (*(_BYTE *)(a1[11] + 64) & 1) == 0 )
          OutpEnqueuePollingTimer(a1);
      }
      return 2147483653LL;
    }
    else
    {
      if ( (_DWORD)a2 != -1073741811 )
      {
        *((_DWORD *)a1 + 66) = 6;
        *((_DWORD *)a1 + 267) = a2;
      }
      return (unsigned int)a2;
    }
  }
  else
  {
    ++*((_DWORD *)a1 + 114);
    if ( (_DWORD)a2 == 532 )
    {
      v4 = *a1;
      LOBYTE(a2) = *(_BYTE *)(*a1 + 2345) == 0;
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(*a1 + 2512))(*(_QWORD *)(*a1 + 2368), a2) )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v4 + 1684));
        ++a1[59];
      }
      else
      {
        ++a1[60];
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x140004790  push    rbx
0x140004792  sub     rsp, 20h
0x140004796  mov     rbx, rcx
0x140004799  test    edx, edx
0x14000479b  js      short loc_1400047FD
0x14000479d  inc     dword ptr [rcx+1C8h]
0x1400047a3  cmp     edx, 214h
0x1400047a9  jz      short loc_1400047B4
0x1400047ab  xor     eax, eax
0x1400047ad  add     rsp, 20h
0x1400047b1  pop     rbx
0x1400047b2  retn
0x1400047b4  mov     [rsp+28h+arg_0], rdi
0x1400047b9  mov     rdi, [rcx]
0x1400047bc  movzx   eax, byte ptr [rdi+929h]
0x1400047c3  mov     rcx, [rdi+940h]
0x1400047ca  test    al, al
0x1400047cc  mov     rax, [rdi+9D0h]
0x1400047d3  setz    dl
0x1400047d6  call    _guard_dispatch_icall
0x1400047db  test    al, al
0x1400047dd  jz      short loc_1400047F4
0x1400047df  lock inc dword ptr [rdi+694h]
0x1400047e6  inc     qword ptr [rbx+1D8h]
0x1400047ed  mov     rdi, [rsp+28h+arg_0]
0x1400047f2  jmp     short loc_1400047AB
0x1400047f4  inc     qword ptr [rbx+1E0h]
0x1400047fb  jmp     short loc_1400047ED
0x1400047fd  cmp     edx, 80000005h
0x140004803  jnz     short loc_140004834
0x140004805  cmp     dword ptr [rcx+108h], 5
0x14000480c  jz      short loc_14000482A
0x14000480e  mov     dword ptr [rcx+108h], 2
0x140004818  mov     rcx, [rcx+58h]
0x14000481c  test    byte ptr [rcx+40h], 1
0x140004820  jnz     short loc_14000482A
0x140004822  mov     rcx, rbx
0x140004825  call    OutpEnqueuePollingTimer
0x14000482a  mov     eax, 80000005h
0x14000482f  jmp     loc_1400047AD
0x140004834  cmp     edx, 0C000000Dh
0x14000483a  jz      short loc_14000484C
0x14000483c  mov     dword ptr [rcx+108h], 6
0x140004846  mov     [rcx+42Ch], edx
0x14000484c  mov     eax, edx
0x14000484e  jmp     loc_1400047AD
```
