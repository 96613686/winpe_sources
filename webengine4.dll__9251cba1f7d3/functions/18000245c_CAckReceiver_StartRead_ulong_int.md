# CAckReceiver::StartRead(ulong,int)

- ea: `0x18000245c`
- end: `0x180002584`
- name: `?StartRead@CAckReceiver@@QEAAJKH@Z`
- size: `296`
- prototype: `__int64 __fastcall(CAckReceiver *__hidden this, unsigned int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180001c30`
- `0x18001dc88`

## callees

- `0x1800018c0`
- `0x18000245c`
- `0x18001e674`
- `0x18004d350`
- `0x180065b60`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1800024fe`
- `KERNEL32!ReadFile` at `0x1800024fe`
- `KERNEL32!GetLastError` at `0x180002508`
- `KERNEL32!GetLastError` at `0x180002508`
- `KERNEL32!EnterCriticalSection` at `0x180002498`
- `KERNEL32!EnterCriticalSection` at `0x180002498`
- `KERNEL32!LeaveCriticalSection` at `0x18000255d`
- `KERNEL32!LeaveCriticalSection` at `0x18000255d`

## pseudocode

```c
__int64 __fastcall CAckReceiver::StartRead(CAckReceiver *this, unsigned int a2, int a3)
{
  __int64 v3; // rsi
  __int64 v5; // rbp
  __int64 v6; // rdi
  __int64 v7; // r15
  void *v8; // r14
  __int64 v9; // r12
  unsigned int LastWin32Error; // esi
  unsigned int v11; // ebp
  DWORD LastError; // eax
  __int64 v13; // rax

  v3 = *((_QWORD *)this + 2);
  v5 = a3;
  v6 = 56LL * a3;
  v7 = a2;
  if ( *(_DWORD *)(v3 + v6 + 48) )
    EnterCriticalSection((LPCRITICAL_SECTION)(v6 + v3 + 8));
  v8 = *(void **)(v3 + v6);
  v9 = *(_QWORD *)(*((_QWORD *)this + 6) + 8 * v5);
  if ( v8 == (void *)-1LL )
  {
    LastWin32Error = -2147467259;
  }
  else
  {
    *(_DWORD *)(*((_QWORD *)this + 3) + v6 + 40) = 0;
    v11 = *(_DWORD *)(*((_QWORD *)this + 5) + 4 * v5);
    if ( v11 < (unsigned int)v7 )
    {
      LastWin32Error = -2147024362;
    }
    else
    {
      LastWin32Error = 0;
      (*(void (__fastcall **)(CAckReceiver *))(*(_QWORD *)this + 8LL))(this);
      if ( !ReadFile(
              v8,
              (LPVOID)(v9 + v7),
              v11 - v7,
              (LPDWORD)(v6 + *((_QWORD *)this + 3) + 44),
              (LPOVERLAPPED)(v6 + *((_QWORD *)this + 3))) )
      {
        LastError = GetLastError();
        if ( LastError != 997 && LastError != 234 )
        {
          (*(void (__fastcall **)(CAckReceiver *))(*(_QWORD *)this + 16LL))(this);
          CAckReceiver::Close(this);
          CProcessEntry::OnProcessDied(*((CProcessEntry **)this + 4));
          LastWin32Error = GetLastWin32Error();
        }
      }
    }
  }
  v13 = *((_QWORD *)this + 2);
  if ( *(_DWORD *)(v6 + v13 + 48) )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + v13 + 8));
  return LastWin32Error;
}

```

## disassembly

```asm
0x18000245c  mov     rax, rsp
0x18000245f  mov     [rax+8], rbx
0x180002463  mov     [rax+10h], rbp
0x180002467  mov     [rax+18h], rsi
0x18000246b  mov     [rax+20h], rdi
0x18000246f  push    r12
0x180002471  push    r14
0x180002473  push    r15
0x180002475  sub     rsp, 30h
0x180002479  mov     rsi, [rcx+10h]
0x18000247d  mov     rbx, rcx
0x180002480  movsxd  rbp, r8d
0x180002483  imul    rdi, rbp, 38h ; '8'
0x180002487  mov     r15d, edx
0x18000248a  cmp     dword ptr [rsi+rdi+30h], 0
0x18000248f  jz      short loc_18000249E
0x180002491  lea     rcx, [rsi+8]
0x180002495  add     rcx, rdi; lpCriticalSection
0x180002498  call    cs:__imp_EnterCriticalSection
0x18000249e  mov     rax, [rbx+30h]
0x1800024a2  mov     r14, [rsi+rdi]
0x1800024a6  mov     r12, [rax+rbp*8]
0x1800024aa  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800024ae  jnz     short loc_1800024BA
0x1800024b0  mov     esi, 80004005h
0x1800024b5  jmp     loc_18000254B
0x1800024ba  mov     rax, [rbx+18h]
0x1800024be  and     dword ptr [rax+rdi+28h], 0
0x1800024c3  mov     rax, [rbx+28h]
0x1800024c7  mov     ebp, [rax+rbp*4]
0x1800024ca  cmp     ebp, r15d
0x1800024cd  jb      short loc_180002546
0x1800024cf  mov     rax, [rbx]
0x1800024d2  mov     rcx, rbx
0x1800024d5  sub     ebp, r15d
0x1800024d8  xor     esi, esi
0x1800024da  mov     rax, [rax+8]
0x1800024de  call    cs:__guard_dispatch_icall_fptr
0x1800024e4  mov     r10, [rbx+18h]
0x1800024e8  lea     rdx, [r12+r15]; lpBuffer
0x1800024ec  add     r10, rdi
0x1800024ef  mov     r8d, ebp; nNumberOfBytesToRead
0x1800024f2  mov     rcx, r14; hFile
0x1800024f5  mov     [rsp+48h+lpOverlapped], r10; lpOverlapped
0x1800024fa  lea     r9, [r10+2Ch]; lpNumberOfBytesRead
0x1800024fe  call    cs:__imp_ReadFile
0x180002504  test    eax, eax
0x180002506  jnz     short loc_18000254B
0x180002508  call    cs:__imp_GetLastError
0x18000250e  cmp     eax, 3E5h
0x180002513  jz      short loc_18000254B
0x180002515  cmp     eax, 0EAh
0x18000251a  jz      short loc_18000254B
0x18000251c  mov     rax, [rbx]
0x18000251f  mov     rcx, rbx
0x180002522  mov     rax, [rax+10h]
0x180002526  call    cs:__guard_dispatch_icall_fptr
0x18000252c  mov     rcx, rbx; this
0x18000252f  call    ?Close@CAckReceiver@@QEAAXXZ; CAckReceiver::Close(void)
0x180002534  mov     rcx, [rbx+20h]; this
0x180002538  call    ?OnProcessDied@CProcessEntry@@QEAAXXZ; CProcessEntry::OnProcessDied(void)
0x18000253d  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180002542  mov     esi, eax
0x180002544  jmp     short loc_18000254B
0x180002546  mov     esi, 80070216h
0x18000254b  mov     rax, [rbx+10h]
0x18000254f  cmp     dword ptr [rdi+rax+30h], 0
0x180002554  jz      short loc_180002563
0x180002556  lea     rcx, [rax+8]
0x18000255a  add     rcx, rdi; lpCriticalSection
0x18000255d  call    cs:__imp_LeaveCriticalSection
0x180002563  mov     rbx, [rsp+48h+arg_0]
0x180002568  mov     eax, esi
0x18000256a  mov     rsi, [rsp+48h+arg_10]
0x18000256f  mov     rbp, [rsp+48h+arg_8]
0x180002574  mov     rdi, [rsp+48h+arg_18]
0x180002579  add     rsp, 30h
0x18000257d  pop     r15
0x18000257f  pop     r14
0x180002581  pop     r12
0x180002583  retn
```
