# SqosPreReadWrite

- ea: `0x1400142c0`
- end: `0x14001440e`
- name: `SqosPreReadWrite`
- size: `334`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140001380`
- `0x140003790`
- `0x14000603c`
- `0x1400142c0`

## import_xrefs

- `FLTMGR!FltGetStreamHandleContext` at `0x1400142f8`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400142f8`
- `FLTMGR!FltReleaseContext` at `0x140014375`
- `FLTMGR!FltReleaseContext` at `0x14001438b`
- `FLTMGR!FltReleaseContext` at `0x140014375`
- `FLTMGR!FltReleaseContext` at `0x14001438b`
- `FLTMGR!FltGetInstanceContext` at `0x140014356`
- `FLTMGR!FltGetInstanceContext` at `0x140014356`

## pseudocode

```c
__int64 __fastcall SqosPreReadWrite(_QWORD *a1, __int64 a2, _QWORD *a3)
{
  int v3; // eax
  NTSTATUS StreamHandleContext; // eax
  _QWORD *Job; // rax
  _QWORD *v9; // rdi
  unsigned int started; // ebx
  PFLT_CONTEXT Context; // [rsp+50h] [rbp+8h] BYREF
  PFLT_CONTEXT v13; // [rsp+68h] [rbp+20h] BYREF

  v3 = *(_DWORD *)a1;
  v13 = 0;
  Context = 0;
  if ( (v3 & 1) == 0 )
    return 1;
  StreamHandleContext = FltGetStreamHandleContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context);
  if ( StreamHandleContext == -1073741275 )
  {
    if ( FltGetInstanceContext(*(PFLT_INSTANCE *)(a2 + 24), &v13) < 0
      || *((_DWORD *)v13 + 47) != 2
      || !*((_DWORD *)v13 + 231)
      || (int)SqospCreateStreamHandleContext((__int64)a1, a2, *((_QWORD *)v13 + 22), byte_14000D2AB, 0, &Context) < 0 )
    {
      goto LABEL_10;
    }
  }
  else if ( StreamHandleContext < 0 )
  {
    goto LABEL_10;
  }
  if ( !*((_BYTE *)Context + 32) )
  {
    if ( *(_DWORD *)(*((_QWORD *)Context + 1) + 924LL) )
    {
      Job = SqospCreateJob((__int64)Context, a1);
      v9 = Job;
      if ( Job )
      {
        started = SqospStartJob(Job);
        if ( started )
          *a3 = 0;
        else
          *a3 = v9;
        goto LABEL_11;
      }
    }
  }
LABEL_10:
  started = 1;
LABEL_11:
  if ( v13 )
    FltReleaseContext(v13);
  if ( Context )
    FltReleaseContext(Context);
  return started;
}

```

## disassembly

```asm
0x1400142c0  mov     [rsp+arg_8], rbx
0x1400142c5  push    rbp
0x1400142c6  push    rsi
0x1400142c7  push    rdi
0x1400142c8  sub     rsp, 30h
0x1400142cc  mov     eax, [rcx]
0x1400142ce  xor     ebp, ebp
0x1400142d0  mov     [rsp+48h+arg_18], rbp
0x1400142d5  mov     rsi, r8
0x1400142d8  mov     [rsp+48h+Context], rbp
0x1400142dd  mov     rdi, rdx
0x1400142e0  mov     rbx, rcx
0x1400142e3  test    al, 1
0x1400142e5  jz      loc_1400143A7
0x1400142eb  mov     rdx, [rdx+20h]; FileObject
0x1400142ef  lea     r8, [rsp+48h+Context]; Context
0x1400142f4  mov     rcx, [rdi+18h]; Instance
0x1400142f8  call    cs:__imp_FltGetStreamHandleContext
0x1400142ff  nop     dword ptr [rax+rax+00h]
0x140014304  cmp     eax, 0C0000225h
0x140014309  jz      short loc_14001434D
0x14001430b  test    eax, eax
0x14001430d  js      short loc_140014366
0x14001430f  mov     rcx, [rsp+48h+Context]
0x140014314  cmp     [rcx+20h], bpl
0x140014318  jnz     short loc_140014366
0x14001431a  mov     rax, [rcx+8]
0x14001431e  cmp     [rax+39Ch], ebp
0x140014324  jz      short loc_140014366
0x140014326  mov     rdx, rbx
0x140014329  call    SqospCreateJob
0x14001432e  mov     rdi, rax
0x140014331  test    rax, rax
0x140014334  jz      short loc_140014366
0x140014336  mov     rcx, rax
0x140014339  call    SqospStartJob
0x14001433e  mov     ebx, eax
0x140014340  test    eax, eax
0x140014342  jnz     loc_140014406
0x140014348  mov     [rsi], rdi
0x14001434b  jmp     short loc_14001436B
0x14001434d  mov     rcx, [rdi+18h]; Instance
0x140014351  lea     rdx, [rsp+48h+arg_18]; Context
0x140014356  call    cs:__imp_FltGetInstanceContext
0x14001435d  nop     dword ptr [rax+rax+00h]
0x140014362  test    eax, eax
0x140014364  jns     short loc_1400143BA
0x140014366  mov     ebx, 1
0x14001436b  mov     rcx, [rsp+48h+arg_18]; Context
0x140014370  test    rcx, rcx
0x140014373  jz      short loc_140014381
0x140014375  call    cs:__imp_FltReleaseContext
0x14001437c  nop     dword ptr [rax+rax+00h]
0x140014381  mov     rcx, [rsp+48h+Context]; Context
0x140014386  test    rcx, rcx
0x140014389  jz      short loc_140014397
0x14001438b  call    cs:__imp_FltReleaseContext
0x140014392  nop     dword ptr [rax+rax+00h]
0x140014397  mov     eax, ebx
0x140014399  mov     rbx, [rsp+48h+arg_8]
0x14001439e  add     rsp, 30h
0x1400143a2  pop     rdi
0x1400143a3  pop     rsi
0x1400143a4  pop     rbp
0x1400143a5  retn
0x1400143a7  mov     rbx, [rsp+48h+arg_8]
0x1400143ac  mov     eax, 1
0x1400143b1  add     rsp, 30h
0x1400143b5  pop     rdi
0x1400143b6  pop     rsi
0x1400143b7  pop     rbp
0x1400143b8  retn
0x1400143ba  mov     rcx, [rsp+48h+arg_18]
0x1400143bf  cmp     dword ptr [rcx+0BCh], 2
0x1400143c6  jnz     short loc_140014366
0x1400143c8  cmp     [rcx+39Ch], ebp
0x1400143ce  jz      short loc_140014366
0x1400143d0  mov     r8, [rcx+0B0h]
0x1400143d7  lea     rax, [rsp+48h+Context]
0x1400143dc  movzx   r9d, cs:byte_14000D2AB
0x1400143e4  mov     rdx, rdi
0x1400143e7  mov     [rsp+48h+var_20], rax
0x1400143ec  mov     rcx, rbx
0x1400143ef  mov     [rsp+48h+var_28], bpl
0x1400143f4  call    SqospCreateStreamHandleContext
0x1400143f9  test    eax, eax
0x1400143fb  jns     loc_14001430F
0x140014401  jmp     loc_140014366
0x140014406  mov     [rsi], rbp
0x140014409  jmp     loc_14001436B
```
