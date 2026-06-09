# SVSThreadPool::SVSThreadPool(ulong)

- ea: `0x18004db8c`
- end: `0x18004dc94`
- name: `??0SVSThreadPool@@QEAA@K@Z`
- size: `264`
- prototype: `SVSThreadPool *__fastcall(SVSThreadPool *this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001f41c`

## callees

- `0x180006168`
- `0x18004db8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004dba4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004dba4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004dc45`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004dc59`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004dc45`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004dc59`

## pseudocode

```c
SVSThreadPool *__fastcall SVSThreadPool::SVSThreadPool(SVSThreadPool *this, int a2)
{
  __int64 v4; // rdx
  _QWORD *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rax
  HANDLE EventW; // rax

  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v4 = g_pvAllocData;
  *(_QWORD *)this = &SVSTHeap<__int64>::`vftable';
  *((_DWORD *)this + 2) = 0;
  v5 = (_QWORD *)svsutil_Alloc(16, v4);
  if ( v5 )
  {
    v5[1] = 0;
    *v5 = 0;
  }
  else
  {
    v5 = 0;
  }
  v6 = g_pvAllocData;
  *((_QWORD *)this + 2) = v5;
  *(_QWORD *)this = &SVSTHeap<__int64>::`vftable';
  *((_DWORD *)this + 23) = a2;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *(_QWORD *)((char *)this + 100) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_DWORD *)this + 27) = 0;
  v7 = svsutil_Alloc(40, v6);
  if ( v7 )
  {
    *(_QWORD *)v7 = 0;
    *(_QWORD *)(v7 + 8) = 0;
    *(_QWORD *)(v7 + 16) = 0;
    *(_DWORD *)(v7 + 24) = 24;
    *(_DWORD *)(v7 + 28) = 20;
    *(_DWORD *)(v7 + 32) = 488;
  }
  else
  {
    v7 = 0;
  }
  *((_QWORD *)this + 8) = v7;
  *((_QWORD *)this + 9) = CreateEventW(0, 0, 0, 0);
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 10) = EventW;
  if ( *((_QWORD *)this + 8) && *((_QWORD *)this + 2) && *((_QWORD *)this + 9) && EventW )
    *((_DWORD *)this + 22) = 1;
  return this;
}

```

## disassembly

```asm
0x18004db8c  mov     [rsp+arg_0], rbx
0x18004db91  mov     [rsp+arg_8], rsi
0x18004db96  push    rdi
0x18004db97  sub     rsp, 20h
0x18004db9b  mov     rbx, rcx
0x18004db9e  mov     edi, edx
0x18004dba0  add     rcx, 18h; lpCriticalSection
0x18004dba4  call    cs:__imp_InitializeCriticalSection
0x18004dbaa  mov     rdx, cs:g_pvAllocData
0x18004dbb1  lea     rax, ??_7?$SVSTHeap@_J@@6B@; const SVSTHeap<__int64>::`vftable'
0x18004dbb8  xor     esi, esi
0x18004dbba  mov     [rbx], rax
0x18004dbbd  mov     [rbx+8], esi
0x18004dbc0  lea     ecx, [rsi+10h]
0x18004dbc3  call    svsutil_Alloc
0x18004dbc8  test    rax, rax
0x18004dbcb  jz      short loc_18004DBD6
0x18004dbcd  mov     [rax+8], rsi
0x18004dbd1  mov     [rax], rsi
0x18004dbd4  jmp     short loc_18004DBD9
0x18004dbd6  mov     rax, rsi
0x18004dbd9  mov     rdx, cs:g_pvAllocData
0x18004dbe0  mov     ecx, 28h ; '('
0x18004dbe5  mov     [rbx+10h], rax
0x18004dbe9  lea     rax, ??_7?$SVSTHeap@_J@@6B@; const SVSTHeap<__int64>::`vftable'
0x18004dbf0  mov     [rbx], rax
0x18004dbf3  mov     [rbx+5Ch], edi
0x18004dbf6  mov     [rbx+48h], rsi
0x18004dbfa  mov     [rbx+50h], rsi
0x18004dbfe  mov     [rbx+64h], rsi
0x18004dc02  mov     [rbx+60h], esi
0x18004dc05  mov     [rbx+6Ch], esi
0x18004dc08  call    svsutil_Alloc
0x18004dc0d  test    rax, rax
0x18004dc10  jnz     short loc_18004DC17
0x18004dc12  mov     rax, rsi
0x18004dc15  jmp     short loc_18004DC37
0x18004dc17  mov     [rax], rsi
0x18004dc1a  mov     [rax+8], rsi
0x18004dc1e  mov     [rax+10h], rsi
0x18004dc22  mov     dword ptr [rax+18h], 18h
0x18004dc29  mov     dword ptr [rax+1Ch], 14h
0x18004dc30  mov     dword ptr [rax+20h], 1E8h
0x18004dc37  xor     r9d, r9d; lpName
0x18004dc3a  mov     [rbx+40h], rax
0x18004dc3e  xor     r8d, r8d; bInitialState
0x18004dc41  xor     edx, edx; bManualReset
0x18004dc43  xor     ecx, ecx; lpEventAttributes
0x18004dc45  call    cs:__imp_CreateEventW
0x18004dc4b  xor     r9d, r9d; lpName
0x18004dc4e  xor     r8d, r8d; bInitialState
0x18004dc51  xor     edx, edx; bManualReset
0x18004dc53  mov     [rbx+48h], rax
0x18004dc57  xor     ecx, ecx; lpEventAttributes
0x18004dc59  call    cs:__imp_CreateEventW
0x18004dc5f  mov     [rbx+50h], rax
0x18004dc63  cmp     [rbx+40h], rsi
0x18004dc67  jz      short loc_18004DC81
0x18004dc69  cmp     [rbx+10h], rsi
0x18004dc6d  jz      short loc_18004DC81
0x18004dc6f  cmp     [rbx+48h], rsi
0x18004dc73  jz      short loc_18004DC81
0x18004dc75  test    rax, rax
0x18004dc78  jz      short loc_18004DC81
0x18004dc7a  mov     dword ptr [rbx+58h], 1
0x18004dc81  mov     rsi, [rsp+28h+arg_8]
0x18004dc86  mov     rax, rbx
0x18004dc89  mov     rbx, [rsp+28h+arg_0]
0x18004dc8e  add     rsp, 20h
0x18004dc92  pop     rdi
0x18004dc93  retn
```
