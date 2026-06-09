# CUnbufferedWriter::~CUnbufferedWriter(void)

- ea: `0x18000c914`
- end: `0x18000c9f2`
- name: `??1CUnbufferedWriter@@QEAA@XZ`
- size: `222`
- prototype: `void __fastcall(CUnbufferedWriter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180007f74`

## callees

- `0x180001194`
- `0x18000c914`
- `0x18000d2b4`

## import_xrefs

- `KERNEL32!VirtualFree` at `0x18000c99c`
- `KERNEL32!VirtualFree` at `0x18000c99c`
- `KERNEL32!CloseHandle` at `0x18000c934`
- `KERNEL32!CloseHandle` at `0x18000c94c`
- `KERNEL32!CloseHandle` at `0x18000c963`
- `KERNEL32!CloseHandle` at `0x18000c934`
- `KERNEL32!CloseHandle` at `0x18000c94c`
- `KERNEL32!CloseHandle` at `0x18000c963`

## pseudocode

```c
void __fastcall CUnbufferedWriter::~CUnbufferedWriter(HANDLE *this)
{
  HANDLE v2; // rcx
  HANDLE v3; // rcx
  HANDLE v4; // rcx
  __int64 i; // rdi
  void *v6; // rcx
  HANDLE v7; // rcx
  HANDLE v8; // rcx

  CUnbufferedWriter::WaitForOutstandingOperations(this);
  v2 = this[9];
  if ( v2 )
  {
    CloseHandle(v2);
    this[9] = 0;
  }
  v3 = this[3];
  if ( v3 != (HANDLE)-1LL )
  {
    CloseHandle(v3);
    this[3] = (HANDLE)-1LL;
  }
  v4 = this[4];
  if ( v4 )
  {
    CloseHandle(v4);
    this[4] = 0;
  }
  if ( this[10] )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 11); i = (unsigned int)(i + 1) )
    {
      v6 = (void *)*((_QWORD *)this[10] + 6 * i + 4);
      if ( v6 )
      {
        VirtualFree(v6, 0, 0x8000u);
        *((_QWORD *)this[10] + 6 * i + 4) = 0;
      }
    }
    v7 = this[10];
    if ( v7 )
    {
      operator delete(v7);
      this[10] = 0;
    }
  }
  v8 = this[2];
  if ( v8 )
  {
    operator delete(v8);
    this[2] = 0;
  }
}

```

## disassembly

```asm
0x18000c914  mov     [rsp+arg_0], rbx
0x18000c919  mov     [rsp+arg_8], rsi
0x18000c91e  push    rdi
0x18000c91f  sub     rsp, 20h
0x18000c923  mov     rbx, rcx
0x18000c926  call    ?WaitForOutstandingOperations@CUnbufferedWriter@@QEAAJXZ; CUnbufferedWriter::WaitForOutstandingOperations(void)
0x18000c92b  mov     rcx, [rbx+48h]; hObject
0x18000c92f  test    rcx, rcx
0x18000c932  jz      short loc_18000C942
0x18000c934  call    cs:__imp_CloseHandle
0x18000c93a  mov     qword ptr [rbx+48h], 0
0x18000c942  mov     rcx, [rbx+18h]; hObject
0x18000c946  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c94a  jz      short loc_18000C95A
0x18000c94c  call    cs:__imp_CloseHandle
0x18000c952  mov     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x18000c95a  mov     rcx, [rbx+20h]; hObject
0x18000c95e  test    rcx, rcx
0x18000c961  jz      short loc_18000C971
0x18000c963  call    cs:__imp_CloseHandle
0x18000c969  mov     qword ptr [rbx+20h], 0
0x18000c971  cmp     qword ptr [rbx+50h], 0
0x18000c976  jz      short loc_18000C9CC
0x18000c978  xor     edi, edi
0x18000c97a  cmp     [rbx+2Ch], edi
0x18000c97d  jbe     short loc_18000C9B6
0x18000c97f  mov     rax, [rbx+50h]
0x18000c983  lea     rsi, [rdi+rdi*2]
0x18000c987  add     rsi, rsi
0x18000c98a  mov     rcx, [rax+rsi*8+20h]; lpAddress
0x18000c98f  test    rcx, rcx
0x18000c992  jz      short loc_18000C9AF
0x18000c994  xor     edx, edx; dwSize
0x18000c996  mov     r8d, 8000h; dwFreeType
0x18000c99c  call    cs:__imp_VirtualFree
0x18000c9a2  mov     rax, [rbx+50h]
0x18000c9a6  mov     qword ptr [rax+rsi*8+20h], 0
0x18000c9af  inc     edi
0x18000c9b1  cmp     edi, [rbx+2Ch]
0x18000c9b4  jb      short loc_18000C97F
0x18000c9b6  mov     rcx, [rbx+50h]; void *
0x18000c9ba  test    rcx, rcx
0x18000c9bd  jz      short loc_18000C9CC
0x18000c9bf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c9c4  mov     qword ptr [rbx+50h], 0
0x18000c9cc  mov     rcx, [rbx+10h]; void *
0x18000c9d0  test    rcx, rcx
0x18000c9d3  jz      short loc_18000C9E2
0x18000c9d5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c9da  mov     qword ptr [rbx+10h], 0
0x18000c9e2  mov     rbx, [rsp+28h+arg_0]
0x18000c9e7  mov     rsi, [rsp+28h+arg_8]
0x18000c9ec  add     rsp, 20h
0x18000c9f0  pop     rdi
0x18000c9f1  retn
```
