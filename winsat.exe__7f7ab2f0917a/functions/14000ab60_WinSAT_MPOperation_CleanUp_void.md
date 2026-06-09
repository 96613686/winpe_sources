# WinSAT::MPOperation::CleanUp(void)

- ea: `0x14000ab60`
- end: `0x14000acee`
- name: `?CleanUp@MPOperation@WinSAT@@UEAAKXZ`
- size: `398`
- prototype: `__int64 __fastcall(WinSAT::MPOperation *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007918`

## callees

- `0x14000ab60`
- `0x14011a010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000ac13`
- `KERNEL32!CloseHandle` at `0x14000acbc`
- `KERNEL32!CloseHandle` at `0x14000ac13`
- `KERNEL32!CloseHandle` at `0x14000acbc`
- `KERNEL32!GetCurrentThread` at `0x14000abbb`
- `KERNEL32!GetCurrentThread` at `0x14000abbb`
- `KERNEL32!SetThreadPriority` at `0x14000abc6`
- `KERNEL32!SetThreadPriority` at `0x14000abc6`
- `KERNEL32!GetCurrentProcess` at `0x14000abaa`
- `KERNEL32!GetCurrentProcess` at `0x14000abaa`
- `KERNEL32!SetPriorityClass` at `0x14000abb5`
- `KERNEL32!SetPriorityClass` at `0x14000abb5`
- `KERNEL32!SetLastError` at `0x14000ab82`
- `KERNEL32!SetLastError` at `0x14000ab82`

## pseudocode

```c
__int64 __fastcall WinSAT::MPOperation::CleanUp(WinSAT::MPOperation *this)
{
  DWORD v3; // ebx
  HANDLE CurrentProcess; // rax
  HANDLE CurrentThread; // rax
  unsigned int i; // ebx
  void (__fastcall ***v7)(_QWORD, __int64); // rcx
  void *v8; // rcx
  char *v9; // rcx
  __int64 v10; // rax

  if ( (*(unsigned int (__fastcall **)(WinSAT::MPOperation *))(*(_QWORD *)this + 8LL))(this) == 6 )
  {
    *((_DWORD *)this + 14) = 3;
    if ( !*((_BYTE *)this + 8376) )
    {
      v3 = *((_DWORD *)this + 2100);
      CurrentProcess = GetCurrentProcess();
      SetPriorityClass(CurrentProcess, v3);
      CurrentThread = GetCurrentThread();
      SetThreadPriority(CurrentThread, 0);
    }
    for ( i = 0; i < *((_DWORD *)this + 2075); ++i )
    {
      v7 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + i + 13);
      if ( v7 )
      {
        (**v7)(v7, 1);
        *((_QWORD *)this + i + 13) = 0;
      }
    }
    v8 = (void *)*((_QWORD *)this + 1048);
    *((_DWORD *)this + 2075) = 0;
    if ( v8 )
      CloseHandle(v8);
    v9 = (char *)*((_QWORD *)this + 1049);
    *((_QWORD *)this + 1048) = 0;
    *((_WORD *)this + 4148) = 0;
    *((_BYTE *)this + 8298) = 0;
    *((_DWORD *)this + 2075) = 0;
    *((_DWORD *)this + 2076) = 0;
    *((_DWORD *)this + 2077) = 0;
    *((_DWORD *)this + 2078) = 0;
    *((_DWORD *)this + 2079) = 0;
    *((_DWORD *)this + 2080) = 0;
    *((_DWORD *)this + 2081) = 0;
    *((_WORD *)this + 4168) = 256;
    *((_QWORD *)this + 1043) = 0;
    *((_QWORD *)this + 1044) = 0;
    *((_BYTE *)this + 8360) = 0;
    *((_DWORD *)this + 2091) = 0x4000;
    *((_DWORD *)this + 2092) = 100;
    *((_DWORD *)this + 2093) = 2500;
    *((_WORD *)this + 4188) = 256;
    *((_BYTE *)this + 8378) = 0;
    *((_QWORD *)this + 1048) = 0;
    if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v9);
      *((_QWORD *)this + 1049) = 0;
    }
    v10 = *(_QWORD *)this;
    *((_DWORD *)this + 2100) = -1;
    return (*(__int64 (__fastcall **)(WinSAT::MPOperation *))(v10 + 128))(this);
  }
  else
  {
    SetLastError(1u);
    return 1;
  }
}

```

## disassembly

```asm
0x14000ab60  push    rbx
0x14000ab62  push    rbp
0x14000ab63  push    rsi
0x14000ab64  push    rdi
0x14000ab65  sub     rsp, 28h
0x14000ab69  mov     rax, [rcx]
0x14000ab6c  mov     rdi, rcx
0x14000ab6f  mov     rax, [rax+8]
0x14000ab73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ab78  cmp     eax, 6
0x14000ab7b  jz      short loc_14000AB92
0x14000ab7d  mov     ecx, 1; dwErrCode
0x14000ab82  call    cs:__imp_SetLastError
0x14000ab88  mov     eax, 1
0x14000ab8d  jmp     loc_14000ACE5
0x14000ab92  xor     ebp, ebp
0x14000ab94  mov     dword ptr [rdi+38h], 3
0x14000ab9b  cmp     [rdi+20B8h], bpl
0x14000aba2  jnz     short loc_14000ABCC
0x14000aba4  mov     ebx, [rdi+20D0h]
0x14000abaa  call    cs:__imp_GetCurrentProcess
0x14000abb0  mov     rcx, rax; hProcess
0x14000abb3  mov     edx, ebx; dwPriorityClass
0x14000abb5  call    cs:__imp_SetPriorityClass
0x14000abbb  call    cs:__imp_GetCurrentThread
0x14000abc1  mov     rcx, rax; hThread
0x14000abc4  xor     edx, edx; nPriority
0x14000abc6  call    cs:__imp_SetThreadPriority
0x14000abcc  mov     ebx, ebp
0x14000abce  cmp     [rdi+206Ch], ebp
0x14000abd4  jbe     short loc_14000AC01
0x14000abd6  mov     esi, ebx
0x14000abd8  mov     rcx, [rdi+rsi*8+68h]
0x14000abdd  test    rcx, rcx
0x14000abe0  jz      short loc_14000ABF7
0x14000abe2  mov     rax, [rcx]
0x14000abe5  mov     edx, 1
0x14000abea  mov     rax, [rax]
0x14000abed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000abf2  mov     [rdi+rsi*8+68h], rbp
0x14000abf7  inc     ebx
0x14000abf9  cmp     ebx, [rdi+206Ch]
0x14000abff  jb      short loc_14000ABD6
0x14000ac01  mov     rcx, [rdi+20C0h]; hObject
0x14000ac08  mov     [rdi+206Ch], ebp
0x14000ac0e  test    rcx, rcx
0x14000ac11  jz      short loc_14000AC19
0x14000ac13  call    cs:__imp_CloseHandle
0x14000ac19  mov     rcx, [rdi+20C8h]; hObject
0x14000ac20  mov     [rdi+20C0h], rbp
0x14000ac27  mov     [rdi+2068h], bp
0x14000ac2e  mov     [rdi+206Ah], bpl
0x14000ac35  mov     [rdi+206Ch], ebp
0x14000ac3b  lea     rax, [rcx-1]
0x14000ac3f  mov     [rdi+2070h], ebp
0x14000ac45  mov     [rdi+2074h], ebp
0x14000ac4b  mov     [rdi+2078h], ebp
0x14000ac51  mov     [rdi+207Ch], ebp
0x14000ac57  mov     [rdi+2080h], ebp
0x14000ac5d  mov     [rdi+2084h], ebp
0x14000ac63  mov     word ptr [rdi+2090h], 100h
0x14000ac6c  mov     [rdi+2098h], rbp
0x14000ac73  mov     [rdi+20A0h], rbp
0x14000ac7a  mov     [rdi+20A8h], bpl
0x14000ac81  mov     dword ptr [rdi+20ACh], 4000h
0x14000ac8b  mov     dword ptr [rdi+20B0h], 64h ; 'd'
0x14000ac95  mov     dword ptr [rdi+20B4h], 9C4h
0x14000ac9f  mov     word ptr [rdi+20B8h], 100h
0x14000aca8  mov     [rdi+20BAh], bpl
0x14000acaf  mov     [rdi+20C0h], rbp
0x14000acb6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000acba  ja      short loc_14000ACC9
0x14000acbc  call    cs:__imp_CloseHandle
0x14000acc2  mov     [rdi+20C8h], rbp
0x14000acc9  mov     rax, [rdi]
0x14000accc  mov     rcx, rdi
0x14000accf  mov     dword ptr [rdi+20D0h], 0FFFFFFFFh
0x14000acd9  mov     rax, [rax+80h]
0x14000ace0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ace5  add     rsp, 28h
0x14000ace9  pop     rdi
0x14000acea  pop     rsi
0x14000aceb  pop     rbp
0x14000acec  pop     rbx
0x14000aced  retn
```
