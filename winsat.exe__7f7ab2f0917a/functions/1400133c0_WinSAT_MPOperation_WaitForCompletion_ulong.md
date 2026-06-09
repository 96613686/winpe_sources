# WinSAT::MPOperation::WaitForCompletion(ulong)

- ea: `0x1400133c0`
- end: `0x14001344e`
- name: `?WaitForCompletion@MPOperation@WinSAT@@UEAAKK@Z`
- size: `142`
- prototype: `unsigned int(WinSAT::MPOperation *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400133c0`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x140013430`
- `KERNEL32!GetCurrentThread` at `0x140013430`
- `KERNEL32!WaitForSingleObject` at `0x1400133f9`
- `KERNEL32!WaitForSingleObject` at `0x1400133f9`
- `KERNEL32!SetThreadPriority` at `0x14001343b`
- `KERNEL32!SetThreadPriority` at `0x14001343b`
- `KERNEL32!GetCurrentProcess` at `0x14001341f`
- `KERNEL32!GetCurrentProcess` at `0x14001341f`
- `KERNEL32!SetPriorityClass` at `0x14001342a`
- `KERNEL32!SetPriorityClass` at `0x14001342a`
- `KERNEL32!SetLastError` at `0x1400133e5`
- `KERNEL32!SetLastError` at `0x1400133e5`

## pseudocode

```c
__int64 __fastcall WinSAT::MPOperation::WaitForCompletion(HANDLE *this, DWORD a2)
{
  DWORD v5; // edi
  DWORD v6; // ebx
  HANDLE CurrentProcess; // rax
  HANDLE CurrentThread; // rax

  if ( (*((unsigned int (__fastcall **)(HANDLE *))*this + 1))(this) == 4 )
  {
    v5 = WaitForSingleObject(this[1048], a2);
    if ( v5 )
      *((_BYTE *)this + 8296) = 1;
    if ( !*((_BYTE *)this + 8376) && !v5 )
    {
      v6 = *((_DWORD *)this + 2100);
      CurrentProcess = GetCurrentProcess();
      SetPriorityClass(CurrentProcess, v6);
      CurrentThread = GetCurrentThread();
      SetThreadPriority(CurrentThread, 0);
    }
    return v5;
  }
  else
  {
    SetLastError(1u);
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x1400133c0  mov     [rsp+arg_0], rbx
0x1400133c5  push    rdi
0x1400133c6  sub     rsp, 20h
0x1400133ca  mov     rax, [rcx]
0x1400133cd  mov     edi, edx
0x1400133cf  mov     rbx, rcx
0x1400133d2  mov     rax, [rax+8]
0x1400133d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400133db  cmp     eax, 4
0x1400133de  jz      short loc_1400133F0
0x1400133e0  mov     ecx, 1; dwErrCode
0x1400133e5  call    cs:__imp_SetLastError
0x1400133eb  or      eax, 0FFFFFFFFh
0x1400133ee  jmp     short loc_140013443
0x1400133f0  mov     rcx, [rbx+20C0h]; hHandle
0x1400133f7  mov     edx, edi; dwMilliseconds
0x1400133f9  call    cs:__imp_WaitForSingleObject
0x1400133ff  mov     edi, eax
0x140013401  test    eax, eax
0x140013403  jz      short loc_14001340C
0x140013405  mov     byte ptr [rbx+2068h], 1
0x14001340c  cmp     byte ptr [rbx+20B8h], 0
0x140013413  jnz     short loc_140013441
0x140013415  test    edi, edi
0x140013417  jnz     short loc_140013441
0x140013419  mov     ebx, [rbx+20D0h]
0x14001341f  call    cs:__imp_GetCurrentProcess
0x140013425  mov     rcx, rax; hProcess
0x140013428  mov     edx, ebx; dwPriorityClass
0x14001342a  call    cs:__imp_SetPriorityClass
0x140013430  call    cs:__imp_GetCurrentThread
0x140013436  mov     rcx, rax; hThread
0x140013439  xor     edx, edx; nPriority
0x14001343b  call    cs:__imp_SetThreadPriority
0x140013441  mov     eax, edi
0x140013443  mov     rbx, [rsp+28h+arg_0]
0x140013448  add     rsp, 20h
0x14001344c  pop     rdi
0x14001344d  retn
```
