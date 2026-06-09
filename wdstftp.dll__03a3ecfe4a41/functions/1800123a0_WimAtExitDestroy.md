# WimAtExitDestroy

- ea: `0x1800123a0`
- end: `0x180012460`
- name: `WimAtExitDestroy`
- size: `192`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800123a0`
- `0x180060e70`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180012428`
- `KERNEL32!HeapFree` at `0x180012428`
- `KERNEL32!EnterCriticalSection` at `0x1800123be`
- `KERNEL32!EnterCriticalSection` at `0x1800123be`
- `KERNEL32!LeaveCriticalSection` at `0x1800123e0`
- `KERNEL32!LeaveCriticalSection` at `0x1800123e0`
- `KERNEL32!DeleteCriticalSection` at `0x180012454`
- `KERNEL32!GetProcessHeap` at `0x180012414`
- `KERNEL32!GetProcessHeap` at `0x180012414`

## pseudocode

```c
void __fastcall WimAtExitDestroy()
{
  _QWORD *v0; // rbx
  void (__fastcall *v1)(_QWORD); // rax
  _QWORD *v2; // rdi
  HANDLE ProcessHeap; // rax

  if ( dword_1800778F4 )
  {
    EnterCriticalSection(&stru_180077AA0);
    v0 = lpMem;
    lpMem = 0;
    LeaveCriticalSection(&stru_180077AA0);
    if ( v0 )
    {
      do
      {
        v1 = (void (__fastcall *)(_QWORD))v0[1];
        v2 = (_QWORD *)v0[3];
        if ( v1 )
          v1(v0[2]);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v0, 0xFFFFFFFF) == 1 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v0);
        }
        v0 = v2;
      }
      while ( v2 );
    }
  }
  dword_1800778F4 = 0;
  DeleteCriticalSection(&stru_180077AA0);
}

```

## disassembly

```asm
0x1800123a0  mov     [rsp+arg_0], rbx
0x1800123a5  push    rdi
0x1800123a6  sub     rsp, 20h
0x1800123aa  cmp     cs:dword_1800778F4, 0
0x1800123b1  jz      loc_18001243C
0x1800123b7  lea     rcx, stru_180077AA0; lpCriticalSection
0x1800123be  call    cs:__imp_EnterCriticalSection
0x1800123c5  nop     dword ptr [rax+rax+00h]
0x1800123ca  mov     rbx, cs:lpMem
0x1800123d1  lea     rcx, stru_180077AA0; lpCriticalSection
0x1800123d8  and     cs:lpMem, 0
0x1800123e0  call    cs:__imp_LeaveCriticalSection
0x1800123e7  nop     dword ptr [rax+rax+00h]
0x1800123ec  test    rbx, rbx
0x1800123ef  jz      short loc_18001243C
0x1800123f1  mov     rax, [rbx+8]
0x1800123f5  mov     rdi, [rbx+18h]
0x1800123f9  test    rax, rax
0x1800123fc  jz      short loc_180012408
0x1800123fe  mov     rcx, [rbx+10h]
0x180012402  call    cs:__guard_dispatch_icall_fptr
0x180012408  or      eax, 0FFFFFFFFh
0x18001240b  lock xadd [rbx], eax
0x18001240f  cmp     eax, 1
0x180012412  jnz     short loc_180012434
0x180012414  call    cs:__imp_GetProcessHeap
0x18001241b  nop     dword ptr [rax+rax+00h]
0x180012420  mov     r8, rbx; lpMem
0x180012423  xor     edx, edx; dwFlags
0x180012425  mov     rcx, rax; hHeap
0x180012428  call    cs:__imp_HeapFree
0x18001242f  nop     dword ptr [rax+rax+00h]
0x180012434  mov     rbx, rdi
0x180012437  test    rdi, rdi
0x18001243a  jnz     short loc_1800123F1
0x18001243c  and     cs:dword_1800778F4, 0
0x180012443  lea     rcx, stru_180077AA0
0x18001244a  mov     rbx, [rsp+28h+arg_0]
0x18001244f  add     rsp, 20h
0x180012453  pop     rdi
0x180012454  jmp     cs:__imp_DeleteCriticalSection
```
