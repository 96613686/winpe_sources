# THREAD_POOL::CreateThreadPool(THREAD_POOL * *,THREAD_POOL_CONFIG *)

- ea: `0x1800037c0`
- end: `0x180003872`
- name: `?CreateThreadPool@THREAD_POOL@@SAHPEAPEAV1@PEAUTHREAD_POOL_CONFIG@@@Z`
- size: `178`
- prototype: `static int(struct THREAD_POOL **, struct THREAD_POOL_CONFIG *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180003d80`

## callees

- `0x1800017a0`
- `0x180001f4c`
- `0x180003768`
- `0x1800037c0`
- `0x180003be0`

## pseudocode

```c
__int64 __fastcall THREAD_POOL::CreateThreadPool(struct THREAD_POOL **a1, struct THREAD_POOL_CONFIG *a2)
{
  THREAD_POOL *v4; // rax
  THREAD_POOL *v5; // rbx
  THREAD_POOL_DATA *v6; // rax
  unsigned int v7; // edx
  void (*v8)(void *); // rdx
  unsigned int v9; // edi

  *a1 = 0;
  v4 = (THREAD_POOL *)operator new(8u);
  v5 = v4;
  if ( !v4 )
    return 0;
  *(_QWORD *)v4 = 0;
  v6 = (THREAD_POOL_DATA *)operator new(0x88u);
  if ( !v6 )
  {
    THREAD_POOL::`scalar deleting destructor'(v5, v7);
    return 0;
  }
  *(_DWORD *)v6 = 1094996052;
  *((_QWORD *)v6 + 1) = 0;
  *((_QWORD *)v6 + 2) = 0;
  *((_QWORD *)v6 + 3) = 0;
  *((_QWORD *)v6 + 4) = 0;
  *((_QWORD *)v6 + 5) = v5;
  *(_QWORD *)v5 = v6;
  v9 = THREAD_POOL_DATA::InitializeThreadPool(v6, a2);
  if ( v9 )
  {
    *a1 = v5;
    return 1;
  }
  else
  {
    THREAD_POOL::TerminateThreadPool((void **)v5, v8);
  }
  return v9;
}

```

## disassembly

```asm
0x1800037c0  mov     [rsp+arg_0], rbx
0x1800037c5  mov     [rsp+arg_8], rsi
0x1800037ca  push    rdi
0x1800037cb  sub     rsp, 20h
0x1800037cf  mov     rsi, rcx
0x1800037d2  mov     qword ptr [rcx], 0
0x1800037d9  mov     ecx, 8; Size
0x1800037de  mov     rdi, rdx
0x1800037e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800037e6  mov     rbx, rax
0x1800037e9  test    rax, rax
0x1800037ec  jz      short loc_18000385E
0x1800037ee  mov     ecx, 88h; Size
0x1800037f3  mov     qword ptr [rax], 0
0x1800037fa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800037ff  test    rax, rax
0x180003802  jz      short loc_180003856
0x180003804  mov     dword ptr [rax], 41445054h
0x18000380a  mov     rdx, rdi; struct THREAD_POOL_CONFIG *
0x18000380d  mov     qword ptr [rax+8], 0
0x180003815  mov     rcx, rax; this
0x180003818  mov     qword ptr [rax+10h], 0
0x180003820  mov     qword ptr [rax+18h], 0
0x180003828  mov     qword ptr [rax+20h], 0
0x180003830  mov     [rax+28h], rbx
0x180003834  mov     [rbx], rax
0x180003837  call    ?InitializeThreadPool@THREAD_POOL_DATA@@QEAAHPEAUTHREAD_POOL_CONFIG@@@Z; THREAD_POOL_DATA::InitializeThreadPool(THREAD_POOL_CONFIG *)
0x18000383c  mov     edi, eax
0x18000383e  test    eax, eax
0x180003840  jz      short loc_18000384C
0x180003842  mov     [rsi], rbx
0x180003845  mov     edi, 1
0x18000384a  jmp     short loc_180003860
0x18000384c  mov     rcx, rbx; this
0x18000384f  call    ?TerminateThreadPool@THREAD_POOL@@QEAAXXZ; THREAD_POOL::TerminateThreadPool(void)
0x180003854  jmp     short loc_180003860
0x180003856  mov     rcx, rbx; this
0x180003859  call    ??_GTHREAD_POOL@@AEAAPEAXI@Z; THREAD_POOL::`scalar deleting destructor'(uint)
0x18000385e  xor     edi, edi
0x180003860  mov     rbx, [rsp+28h+arg_0]
0x180003865  mov     eax, edi
0x180003867  mov     rsi, [rsp+28h+arg_8]
0x18000386c  add     rsp, 20h
0x180003870  pop     rdi
0x180003871  retn
```
