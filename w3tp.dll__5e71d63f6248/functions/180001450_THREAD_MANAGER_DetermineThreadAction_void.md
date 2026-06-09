# THREAD_MANAGER::DetermineThreadAction(void)

- ea: `0x180001450`
- end: `0x1800014fc`
- name: `?DetermineThreadAction@THREAD_MANAGER@@AEAAXXZ`
- size: `172`
- prototype: `void __fastcall(THREAD_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180001f40`

## callees

- `0x180001450`
- `0x180001510`
- `0x180001b40`
- `0x180001f8c`
- `0x180002bc0`
- `0x1800035c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800014f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001460`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001460`

## pseudocode

```c
void __fastcall THREAD_MANAGER::DetermineThreadAction(THREAD_MANAGER *this)
{
  unsigned int v2; // r9d
  struct THREAD_MANAGER::THREAD_PARAM **v3; // rdi
  int v4; // r8d
  struct THREAD_MANAGER::THREAD_PARAM *v5; // rcx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( *((_DWORD *)this + 12) )
  {
    v3 = (struct THREAD_MANAGER::THREAD_PARAM **)((char *)this + 64);
  }
  else
  {
    v4 = *(_DWORD *)(*((_QWORD *)this + 14) + 68LL);
    if ( v4 == -1
      || !(unsigned int)TooMuchProcessorUsage(
                          *(union _LARGE_INTEGER *)((char *)this + 128),
                          *(union _LARGE_INTEGER *)((char *)this + 120),
                          v4,
                          v2) )
    {
      v3 = (struct THREAD_MANAGER::THREAD_PARAM **)((char *)this + 64);
      if ( (unsigned int)TooMuchContextSwitchingLoad(
                           *((_DWORD *)this + 18),
                           *(_DWORD *)(*((_QWORD *)this + 8) + 32LL),
                           *(_DWORD *)(*((_QWORD *)this + 14) + 76LL)) )
      {
        THREAD_MANAGER::DoThreadParking((struct _OVERLAPPED *)this);
      }
      else if ( (unsigned int)THREAD_MANAGER::DoThreadCreation(this, *v3) )
      {
        goto LABEL_12;
      }
    }
    else
    {
      v3 = (struct THREAD_MANAGER::THREAD_PARAM **)((char *)this + 64);
    }
  }
  v5 = *v3;
  if ( *v3 )
  {
    *(_DWORD *)v5 = 2017546324;
    operator delete(v5);
  }
  *((_DWORD *)this + 13) = 0;
LABEL_12:
  *v3 = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x180001450  push    rbx
0x180001452  push    rbp
0x180001453  push    rsi
0x180001454  push    rdi
0x180001455  sub     rsp, 28h
0x180001459  mov     rbx, rcx
0x18000145c  add     rcx, 8; lpCriticalSection
0x180001460  call    cs:__imp_EnterCriticalSection
0x180001466  xor     ebp, ebp
0x180001468  cmp     [rbx+30h], ebp
0x18000146b  jz      short loc_180001473
0x18000146d  lea     rdi, [rbx+40h]
0x180001471  jmp     short loc_1800014D0
0x180001473  mov     rax, [rbx+70h]
0x180001477  mov     r8d, [rax+44h]; int
0x18000147b  cmp     r8d, 0FFFFFFFFh
0x18000147f  jz      short loc_18000149B
0x180001481  mov     rdx, [rbx+78h]; union _LARGE_INTEGER
0x180001485  mov     rcx, [rbx+80h]; union _LARGE_INTEGER
0x18000148c  call    ?TooMuchProcessorUsage@@YAHT_LARGE_INTEGER@@0JK@Z; TooMuchProcessorUsage(_LARGE_INTEGER,_LARGE_INTEGER,long,ulong)
0x180001491  test    eax, eax
0x180001493  jz      short loc_18000149B
0x180001495  lea     rdi, [rbx+40h]
0x180001499  jmp     short loc_1800014D0
0x18000149b  mov     rdx, [rbx+40h]
0x18000149f  lea     rdi, [rbx+40h]
0x1800014a3  mov     r8, [rbx+70h]
0x1800014a7  mov     ecx, [rbx+48h]; unsigned int
0x1800014aa  mov     edx, [rdx+20h]; unsigned int
0x1800014ad  mov     r8d, [r8+4Ch]; unsigned int
0x1800014b1  call    ?TooMuchContextSwitchingLoad@@YAHKKKK@Z; TooMuchContextSwitchingLoad(ulong,ulong,ulong,ulong)
0x1800014b6  mov     rcx, rbx; this
0x1800014b9  test    eax, eax
0x1800014bb  jz      short loc_1800014C4
0x1800014bd  call    ?DoThreadParking@THREAD_MANAGER@@AEAAXXZ; THREAD_MANAGER::DoThreadParking(void)
0x1800014c2  jmp     short loc_1800014D0
0x1800014c4  mov     rdx, [rdi]; lpParameter
0x1800014c7  call    ?DoThreadCreation@THREAD_MANAGER@@AEAAHPEAUTHREAD_PARAM@1@@Z; THREAD_MANAGER::DoThreadCreation(THREAD_MANAGER::THREAD_PARAM *)
0x1800014cc  test    eax, eax
0x1800014ce  jnz     short loc_1800014E6
0x1800014d0  mov     rcx, [rdi]; Block
0x1800014d3  test    rcx, rcx
0x1800014d6  jz      short loc_1800014E3
0x1800014d8  mov     dword ptr [rcx], 78415054h
0x1800014de  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800014e3  mov     [rbx+34h], ebp
0x1800014e6  lea     rcx, [rbx+8]
0x1800014ea  mov     [rdi], rbp
0x1800014ed  add     rsp, 28h
0x1800014f1  pop     rdi
0x1800014f2  pop     rsi
0x1800014f3  pop     rbp
0x1800014f4  pop     rbx
0x1800014f5  jmp     cs:__imp_LeaveCriticalSection
```
