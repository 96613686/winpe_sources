# WofPreFsctlGetDeleteReparsePoint

- ea: `0x140036330`
- end: `0x1400364e7`
- name: `WofPreFsctlGetDeleteReparsePoint`
- size: `439`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x1400346f0`

## callees

- `0x140036330`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400363d5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140036474`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400363d5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140036474`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400363c9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140036468`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400363c9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140036468`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140036389`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140036389`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003639c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003639c`
- `FLTMGR!FltGetStreamContext` at `0x140036365`
- `FLTMGR!FltGetStreamContext` at `0x140036365`
- `FLTMGR!FltGetStreamHandleContext` at `0x140036437`
- `FLTMGR!FltGetStreamHandleContext` at `0x140036437`
- `FLTMGR!FltReleaseContext` at `0x1400363e6`
- `FLTMGR!FltReleaseContext` at `0x140036455`
- `FLTMGR!FltReleaseContext` at `0x140036485`
- `FLTMGR!FltReleaseContext` at `0x1400364aa`
- `FLTMGR!FltReleaseContext` at `0x1400364d4`
- `FLTMGR!FltReleaseContext` at `0x1400363e6`
- `FLTMGR!FltReleaseContext` at `0x140036455`
- `FLTMGR!FltReleaseContext` at `0x140036485`
- `FLTMGR!FltReleaseContext` at `0x1400364aa`
- `FLTMGR!FltReleaseContext` at `0x1400364d4`

## pseudocode

```c
__int64 __fastcall WofPreFsctlGetDeleteReparsePoint(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  _DWORD *v7; // rsi
  int v8; // eax
  bool v9; // bl
  struct _FILE_OBJECT *v10; // rdx
  struct _FLT_INSTANCE *v11; // rcx
  PFLT_CONTEXT v12; // [rsp+20h] [rbp-38h] BYREF
  PFLT_CONTEXT Context; // [rsp+70h] [rbp+18h] BYREF

  Context = 0;
  if ( !a4 && !byte_140018454
    || FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context) < 0 )
  {
    return 1;
  }
  v7 = Context;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v7 + 32LL));
  v8 = v7[2] & 0xF000000;
  if ( v8 == 0x1000000 )
  {
    v9 = 0;
  }
  else if ( v8 == 0x2000000 )
  {
    v9 = *(_QWORD *)(a2 + 40) == *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v7 + 16LL) + 56LL);
  }
  else
  {
    if ( *(_QWORD *)(a2 + 40) )
    {
      v10 = *(struct _FILE_OBJECT **)(a2 + 32);
      v11 = *(struct _FLT_INSTANCE **)(a2 + 24);
      v12 = 0;
      if ( FltGetStreamHandleContext(v11, v10, &v12) != -1073741275 )
      {
        if ( (*(_DWORD *)v12 & 1) != 0 )
        {
          FltReleaseContext(v12);
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v7 + 32LL));
          KeLeaveCriticalRegion();
          FltReleaseContext(Context);
          return 1;
        }
        if ( (*(_DWORD *)v12 & 2) != 0 && v7[3] < 4u )
        {
          FltReleaseContext(v12);
          v9 = 0;
          goto LABEL_7;
        }
        FltReleaseContext(v12);
      }
    }
    v9 = 1;
  }
LABEL_7:
  if ( (v7[2] & 0x20) != 0 )
    v9 = 1;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v7 + 32LL));
  KeLeaveCriticalRegion();
  FltReleaseContext(Context);
  if ( v9 )
    return 1;
  *(_DWORD *)(a1 + 24) = -1073741195;
  return 4;
}

```

## disassembly

```asm
0x140036330  mov     [rsp+Context], r8
0x140036335  push    rbx
0x140036336  push    rbp
0x140036337  push    rsi
0x140036338  push    rdi
0x140036339  sub     rsp, 38h
0x14003633d  xor     ebp, ebp
0x14003633f  mov     rbx, rdx
0x140036342  mov     [rsp+58h+Context], rbp
0x140036347  mov     rdi, rcx
0x14003634a  test    r9b, r9b
0x14003634d  jnz     short loc_140036358
0x14003634f  cmp     cs:byte_140018454, bpl
0x140036356  jz      short loc_140036375
0x140036358  mov     rdx, [rdx+20h]; FileObject
0x14003635c  lea     r8, [rsp+58h+Context]; Context
0x140036361  mov     rcx, [rbx+18h]; Instance
0x140036365  call    cs:__imp_FltGetStreamContext
0x14003636c  nop     dword ptr [rax+rax+00h]
0x140036371  test    eax, eax
0x140036373  jns     short loc_140036384
0x140036375  mov     eax, 1
0x14003637a  add     rsp, 38h
0x14003637e  pop     rdi
0x14003637f  pop     rsi
0x140036380  pop     rbp
0x140036381  pop     rbx
0x140036382  retn
0x140036384  mov     rsi, [rsp+58h+Context]
0x140036389  call    cs:__imp_KeEnterCriticalRegion
0x140036390  nop     dword ptr [rax+rax+00h]
0x140036395  mov     rcx, [rsi]
0x140036398  add     rcx, 20h ; ' '; FastMutex
0x14003639c  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400363a3  nop     dword ptr [rax+rax+00h]
0x1400363a8  mov     eax, [rsi+8]
0x1400363ab  and     eax, 0F000000h
0x1400363b0  cmp     eax, 1000000h
0x1400363b5  jnz     short loc_140036410
0x1400363b7  xor     bl, bl
0x1400363b9  mov     eax, [rsi+8]
0x1400363bc  test    al, 20h
0x1400363be  jz      short loc_1400363C2
0x1400363c0  mov     bl, 1
0x1400363c2  mov     rcx, [rsi]
0x1400363c5  add     rcx, 20h ; ' '; FastMutex
0x1400363c9  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400363d0  nop     dword ptr [rax+rax+00h]
0x1400363d5  call    cs:__imp_KeLeaveCriticalRegion
0x1400363dc  nop     dword ptr [rax+rax+00h]
0x1400363e1  mov     rcx, [rsp+58h+Context]; Context
0x1400363e6  call    cs:__imp_FltReleaseContext
0x1400363ed  nop     dword ptr [rax+rax+00h]
0x1400363f2  test    bl, bl
0x1400363f4  jnz     loc_140036375
0x1400363fa  mov     dword ptr [rdi+18h], 0C0000275h
0x140036401  mov     eax, 4
0x140036406  add     rsp, 38h
0x14003640a  pop     rdi
0x14003640b  pop     rsi
0x14003640c  pop     rbp
0x14003640d  pop     rbx
0x14003640e  retn
0x140036410  cmp     eax, 2000000h
0x140036415  jz      loc_1400364BD
0x14003641b  cmp     [rbx+28h], rbp
0x14003641f  jz      loc_1400364B6
0x140036425  mov     rdx, [rbx+20h]; FileObject
0x140036429  lea     r8, [rsp+58h+var_38]; Context
0x14003642e  mov     rcx, [rbx+18h]; Instance
0x140036432  mov     [rsp+58h+var_38], rbp
0x140036437  call    cs:__imp_FltGetStreamHandleContext
0x14003643e  nop     dword ptr [rax+rax+00h]
0x140036443  cmp     eax, 0C0000225h
0x140036448  jz      short loc_1400364B6
0x14003644a  mov     rcx, [rsp+58h+var_38]; Context
0x14003644f  mov     eax, [rcx]
0x140036451  test    al, 1
0x140036453  jz      short loc_1400364A0
0x140036455  call    cs:__imp_FltReleaseContext
0x14003645c  nop     dword ptr [rax+rax+00h]
0x140036461  mov     rcx, [rsi]
0x140036464  add     rcx, 20h ; ' '; FastMutex
0x140036468  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14003646f  nop     dword ptr [rax+rax+00h]
0x140036474  call    cs:__imp_KeLeaveCriticalRegion
0x14003647b  nop     dword ptr [rax+rax+00h]
0x140036480  mov     rcx, [rsp+58h+Context]; Context
0x140036485  call    cs:__imp_FltReleaseContext
0x14003648c  nop     dword ptr [rax+rax+00h]
0x140036491  mov     eax, 1
0x140036496  add     rsp, 38h
0x14003649a  pop     rdi
0x14003649b  pop     rsi
0x14003649c  pop     rbp
0x14003649d  pop     rbx
0x14003649e  retn
0x1400364a0  test    al, 2
0x1400364a2  jz      short loc_1400364AA
0x1400364a4  cmp     dword ptr [rsi+0Ch], 4
0x1400364a8  jb      short loc_1400364D4
0x1400364aa  call    cs:__imp_FltReleaseContext
0x1400364b1  nop     dword ptr [rax+rax+00h]
0x1400364b6  mov     bl, 1
0x1400364b8  jmp     loc_1400363B9
0x1400364bd  mov     rax, [rsi]
0x1400364c0  mov     rcx, [rax+10h]
0x1400364c4  mov     rax, [rcx+38h]
0x1400364c8  cmp     [rbx+28h], rax
0x1400364cc  setz    bl
0x1400364cf  jmp     loc_1400363B9
0x1400364d4  call    cs:__imp_FltReleaseContext
0x1400364db  nop     dword ptr [rax+rax+00h]
0x1400364e0  xor     bl, bl
0x1400364e2  jmp     loc_1400363B9
```
