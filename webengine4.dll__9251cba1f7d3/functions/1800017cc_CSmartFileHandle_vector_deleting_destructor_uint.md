# CSmartFileHandle::`vector deleting destructor'(uint)

- ea: `0x1800017cc`
- end: `0x180001896`
- name: `??_ECSmartFileHandle@@QEAAPEAXI@Z`
- size: `202`
- prototype: `void *__fastcall(CSmartFileHandle *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000174c`

## callees

- `0x1800017cc`
- `0x180064810`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180001810`
- `KERNEL32!CloseHandle` at `0x18000184f`
- `KERNEL32!CloseHandle` at `0x180001810`
- `KERNEL32!CloseHandle` at `0x18000184f`
- `KERNEL32!DeleteCriticalSection` at `0x180001820`
- `KERNEL32!DeleteCriticalSection` at `0x18000185f`
- `KERNEL32!DeleteCriticalSection` at `0x180001820`
- `KERNEL32!DeleteCriticalSection` at `0x18000185f`

## pseudocode

```c
CSmartFileHandle *__fastcall CSmartFileHandle::`vector deleting destructor'(CSmartFileHandle *this, char a2)
{
  _QWORD *v4; // rsi
  __int64 v5; // rbp
  char *v6; // rdi

  if ( (a2 & 2) != 0 )
  {
    v4 = (_QWORD *)((char *)this - 8);
    v5 = *((_QWORD *)this - 1);
    v6 = (char *)this + 56 * v5;
    while ( v5 )
    {
      --v5;
      v6 -= 56;
      if ( *(_QWORD *)v6 != -1 )
        CloseHandle(*(HANDLE *)v6);
      if ( *((_DWORD *)v6 + 12) )
        DeleteCriticalSection((LPCRITICAL_SECTION)(v6 + 8));
    }
    if ( (a2 & 1) != 0 )
      operator delete(v4, 56LL * *v4 + 8);
    return (CSmartFileHandle *)v4;
  }
  else
  {
    if ( *(_QWORD *)this != -1 )
      CloseHandle(*(HANDLE *)this);
    if ( *((_DWORD *)this + 12) )
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    if ( (a2 & 1) != 0 )
      operator delete(this, 0x38u);
    return this;
  }
}

```

## disassembly

```asm
0x1800017cc  mov     rax, rsp
0x1800017cf  mov     [rax+8], rbx
0x1800017d3  mov     [rax+10h], rbp
0x1800017d7  mov     [rax+18h], rsi
0x1800017db  mov     [rax+20h], rdi
0x1800017df  push    r14
0x1800017e1  sub     rsp, 20h
0x1800017e5  mov     r14d, edx
0x1800017e8  mov     rbx, rcx
0x1800017eb  test    dl, 2
0x1800017ee  jz      short loc_180001846
0x1800017f0  lea     rsi, [rcx-8]
0x1800017f4  mov     rbp, [rsi]
0x1800017f7  imul    rdi, rbp, 38h ; '8'
0x1800017fb  add     rdi, rcx
0x1800017fe  jmp     short loc_180001826
0x180001800  dec     rbp
0x180001803  lea     rdi, [rdi-38h]
0x180001807  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18000180b  jz      short loc_180001816
0x18000180d  mov     rcx, [rdi]; hObject
0x180001810  call    cs:__imp_CloseHandle
0x180001816  cmp     dword ptr [rdi+30h], 0
0x18000181a  jz      short loc_180001826
0x18000181c  lea     rcx, [rdi+8]; lpCriticalSection
0x180001820  call    cs:__imp_DeleteCriticalSection
0x180001826  test    rbp, rbp
0x180001829  jnz     short loc_180001800
0x18000182b  test    r14b, 1
0x18000182f  jz      short loc_180001841
0x180001831  imul    rdx, [rsi], 38h ; '8'
0x180001835  mov     rcx, rsi; void *
0x180001838  add     rdx, 8; unsigned __int64
0x18000183c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180001841  mov     rax, rsi
0x180001844  jmp     short loc_18000187B
0x180001846  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x18000184a  jz      short loc_180001855
0x18000184c  mov     rcx, [rcx]; hObject
0x18000184f  call    cs:__imp_CloseHandle
0x180001855  cmp     dword ptr [rbx+30h], 0
0x180001859  jz      short loc_180001865
0x18000185b  lea     rcx, [rbx+8]; lpCriticalSection
0x18000185f  call    cs:__imp_DeleteCriticalSection
0x180001865  test    r14b, 1
0x180001869  jz      short loc_180001878
0x18000186b  mov     edx, 38h ; '8'; unsigned __int64
0x180001870  mov     rcx, rbx; void *
0x180001873  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180001878  mov     rax, rbx
0x18000187b  mov     rbx, [rsp+28h+arg_0]
0x180001880  mov     rbp, [rsp+28h+arg_8]
0x180001885  mov     rsi, [rsp+28h+arg_10]
0x18000188a  mov     rdi, [rsp+28h+arg_18]
0x18000188f  add     rsp, 20h
0x180001893  pop     r14
0x180001895  retn
```
