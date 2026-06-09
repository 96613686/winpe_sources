# SVSThreadPool::SVSThreadPool(ulong)

- ea: `0x180051018`
- end: `0x180051133`
- name: `??0SVSThreadPool@@QEAA@K@Z`
- size: `283`
- prototype: `SVSThreadPool *__fastcall(SVSThreadPool *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014580`

## callees

- `0x18001aea8`
- `0x180051018`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180051030`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180051030`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800510d7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800510f1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800510d7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800510f1`

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
0x180051018  mov     [rsp+arg_0], rbx
0x18005101d  mov     [rsp+arg_8], rsi
0x180051022  push    rdi
0x180051023  sub     rsp, 20h
0x180051027  mov     rbx, rcx
0x18005102a  mov     edi, edx
0x18005102c  add     rcx, 18h; lpCriticalSection
0x180051030  call    cs:__imp_InitializeCriticalSection
0x180051037  nop     dword ptr [rax+rax+00h]
0x18005103c  mov     rdx, cs:g_pvAllocData
0x180051043  lea     rax, ??_7?$SVSTHeap@_J@@6B@; const SVSTHeap<__int64>::`vftable'
0x18005104a  xor     esi, esi
0x18005104c  mov     [rbx], rax
0x18005104f  mov     [rbx+8], esi
0x180051052  lea     ecx, [rsi+10h]
0x180051055  call    svsutil_Alloc
0x18005105a  test    rax, rax
0x18005105d  jz      short loc_180051068
0x18005105f  mov     [rax+8], rsi
0x180051063  mov     [rax], rsi
0x180051066  jmp     short loc_18005106B
0x180051068  mov     rax, rsi
0x18005106b  mov     rdx, cs:g_pvAllocData
0x180051072  mov     ecx, 28h ; '('
0x180051077  mov     [rbx+10h], rax
0x18005107b  lea     rax, ??_7?$SVSTHeap@_J@@6B@; const SVSTHeap<__int64>::`vftable'
0x180051082  mov     [rbx], rax
0x180051085  mov     [rbx+5Ch], edi
0x180051088  mov     [rbx+48h], rsi
0x18005108c  mov     [rbx+50h], rsi
0x180051090  mov     [rbx+64h], rsi
0x180051094  mov     [rbx+60h], esi
0x180051097  mov     [rbx+6Ch], esi
0x18005109a  call    svsutil_Alloc
0x18005109f  test    rax, rax
0x1800510a2  jnz     short loc_1800510A9
0x1800510a4  mov     rax, rsi
0x1800510a7  jmp     short loc_1800510C9
0x1800510a9  mov     [rax], rsi
0x1800510ac  mov     [rax+8], rsi
0x1800510b0  mov     [rax+10h], rsi
0x1800510b4  mov     dword ptr [rax+18h], 18h
0x1800510bb  mov     dword ptr [rax+1Ch], 14h
0x1800510c2  mov     dword ptr [rax+20h], 1E8h
0x1800510c9  xor     r9d, r9d; lpName
0x1800510cc  mov     [rbx+40h], rax
0x1800510d0  xor     r8d, r8d; bInitialState
0x1800510d3  xor     edx, edx; bManualReset
0x1800510d5  xor     ecx, ecx; lpEventAttributes
0x1800510d7  call    cs:__imp_CreateEventW
0x1800510de  nop     dword ptr [rax+rax+00h]
0x1800510e3  xor     r9d, r9d; lpName
0x1800510e6  xor     r8d, r8d; bInitialState
0x1800510e9  xor     edx, edx; bManualReset
0x1800510eb  mov     [rbx+48h], rax
0x1800510ef  xor     ecx, ecx; lpEventAttributes
0x1800510f1  call    cs:__imp_CreateEventW
0x1800510f8  nop     dword ptr [rax+rax+00h]
0x1800510fd  mov     [rbx+50h], rax
0x180051101  cmp     [rbx+40h], rsi
0x180051105  jz      short loc_18005111F
0x180051107  cmp     [rbx+10h], rsi
0x18005110b  jz      short loc_18005111F
0x18005110d  cmp     [rbx+48h], rsi
0x180051111  jz      short loc_18005111F
0x180051113  test    rax, rax
0x180051116  jz      short loc_18005111F
0x180051118  mov     dword ptr [rbx+58h], 1
0x18005111f  mov     rsi, [rsp+28h+arg_8]
0x180051124  mov     rax, rbx
0x180051127  mov     rbx, [rsp+28h+arg_0]
0x18005112c  add     rsp, 20h
0x180051130  pop     rdi
0x180051131  retn
```
