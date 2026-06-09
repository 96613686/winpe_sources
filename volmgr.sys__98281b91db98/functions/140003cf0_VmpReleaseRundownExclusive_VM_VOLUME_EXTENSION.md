# VmpReleaseRundownExclusive(VM_VOLUME_EXTENSION *)

- ea: `0x140003cf0`
- end: `0x140003e61`
- name: `?VmpReleaseRundownExclusive@@YAXPEAVVM_VOLUME_EXTENSION@@@Z`
- size: `369`
- prototype: `void __fastcall(struct VM_VOLUME_EXTENSION *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003c50`

## callees

- `0x140003cf0`
- `0x140005090`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003dd0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003dd0`
- `ntoskrnl!KeReleaseMutex` at `0x140003de2`
- `ntoskrnl!KeReleaseMutex` at `0x140003de2`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140003d25`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140003d25`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003d3d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003d3d`

## pseudocode

```c
void __fastcall VmpReleaseRundownExclusive(struct VM_VOLUME_EXTENSION *a1)
{
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v2; // rcx
  char **v3; // rdx
  char *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rdi
  _QWORD *v9; // rax
  __int64 v10; // rcx
  _QWORD *v11; // rsi
  _QWORD *v12; // rdx
  unsigned __int8 *v13; // rax
  __int64 v14; // [rsp+20h] [rbp-38h] BYREF
  char **v15; // [rsp+28h] [rbp-30h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  v2 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)a1 + 14);
  v15 = (char **)&v14;
  v14 = (__int64)&v14;
  ExReInitializeRundownProtectionCacheAware(v2);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a1 + 17, &LockHandle);
  if ( *(__int64 **)(v14 + 8) != &v14 )
    goto LABEL_12;
  v3 = v15;
  if ( *v15 != (char *)&v14 )
    goto LABEL_12;
  v4 = (char *)a1 + 120;
  if ( *(struct VM_VOLUME_EXTENSION **)(*((_QWORD *)a1 + 15) + 8LL) != (struct VM_VOLUME_EXTENSION *)((char *)a1 + 120) )
    goto LABEL_12;
  if ( **((char ***)a1 + 16) != v4 )
    goto LABEL_12;
  *v15 = v4;
  v15 = (char **)*((_QWORD *)a1 + 16);
  *v15 = (char *)&v14;
  *((_QWORD *)a1 + 16) = v3;
  v5 = *(_QWORD *)v4;
  if ( *(char **)(*(_QWORD *)v4 + 8LL) != v4 || *v3 != v4 )
    goto LABEL_12;
  *v3 = (char *)v5;
  *(_QWORD *)(v5 + 8) = v3;
  *((_QWORD *)a1 + 16) = (char *)a1 + 120;
  *(_QWORD *)v4 = v4;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  KeReleaseMutex((PRKMUTEX)a1 + 1, 0);
  v6 = *((_QWORD *)a1 + 1);
  v7 = *(_QWORD *)a1;
  v8 = *(_QWORD *)(v6 + 32);
  v9 = (_QWORD *)v14;
  if ( (__int64 *)v14 != &v14 )
  {
    while ( 1 )
    {
      v10 = *v9;
      if ( *(_QWORD **)(*v9 + 8LL) != v9 )
        break;
      v11 = (_QWORD *)v9[1];
      if ( (_QWORD *)*v11 != v9 )
        break;
      v12 = v9 - 21;
      v13 = (unsigned __int8 *)v9[2];
      *v11 = v10;
      *(_QWORD *)(v10 + 8) = v11;
      (*(void (__fastcall **)(__int64, _QWORD *))(v8 + 8LL * *v13 + 112))(v7, v12);
      v9 = (_QWORD *)*v11;
      if ( (__int64 *)*v11 == &v14 )
        return;
    }
LABEL_12:
    __fastfail(3u);
  }
}

```

## disassembly

```asm
0x140003cf0  mov     r11, rsp
0x140003cf3  mov     [r11+8], rbx
0x140003cf7  mov     [r11+10h], rsi
0x140003cfb  push    rdi
0x140003cfc  sub     rsp, 50h
0x140003d00  xor     eax, eax
0x140003d02  xorps   xmm0, xmm0
0x140003d05  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x140003d0a  mov     [r11-18h], rax
0x140003d0e  mov     rbx, rcx
0x140003d11  mov     rcx, [rcx+70h]; RunRefCacheAware
0x140003d15  lea     rax, [r11-38h]
0x140003d19  mov     [r11-30h], rax
0x140003d1d  lea     rax, [r11-38h]
0x140003d21  mov     [r11-38h], rax
0x140003d25  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x140003d2c  nop     dword ptr [rax+rax+00h]
0x140003d31  lea     rcx, [rbx+88h]; SpinLock
0x140003d38  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x140003d3d  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140003d44  nop     dword ptr [rax+rax+00h]
0x140003d49  mov     rax, [rsp+58h+var_38]
0x140003d4e  lea     rcx, [rsp+58h+var_38]
0x140003d53  cmp     [rax+8], rcx
0x140003d57  jnz     loc_140003E5A
0x140003d5d  mov     rdx, [rsp+58h+var_30]
0x140003d62  lea     rax, [rsp+58h+var_38]
0x140003d67  cmp     [rdx], rax
0x140003d6a  jnz     loc_140003E5A
0x140003d70  mov     rcx, [rbx+78h]
0x140003d74  lea     rax, [rbx+78h]
0x140003d78  cmp     [rcx+8], rax
0x140003d7c  jnz     loc_140003E5A
0x140003d82  mov     rcx, [rax+8]
0x140003d86  cmp     [rcx], rax
0x140003d89  jnz     loc_140003E5A
0x140003d8f  mov     [rdx], rax
0x140003d92  lea     r8, [rsp+58h+var_38]
0x140003d97  mov     rcx, [rax+8]
0x140003d9b  mov     [rsp+58h+var_30], rcx
0x140003da0  mov     [rcx], r8
0x140003da3  mov     [rax+8], rdx
0x140003da7  mov     rcx, [rax]
0x140003daa  cmp     [rcx+8], rax
0x140003dae  jnz     loc_140003E5A
0x140003db4  cmp     [rdx], rax
0x140003db7  jnz     loc_140003E5A
0x140003dbd  mov     [rdx], rcx
0x140003dc0  mov     [rcx+8], rdx
0x140003dc4  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x140003dc9  mov     [rax+8], rax
0x140003dcd  mov     [rax], rax
0x140003dd0  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140003dd7  nop     dword ptr [rax+rax+00h]
0x140003ddc  lea     rcx, [rbx+38h]; Mutex
0x140003de0  xor     edx, edx; Wait
0x140003de2  call    cs:__imp_KeReleaseMutex
0x140003de9  nop     dword ptr [rax+rax+00h]
0x140003dee  mov     rax, [rbx+8]
0x140003df2  lea     rcx, [rsp+58h+var_38]
0x140003df7  mov     rbx, [rbx]
0x140003dfa  mov     rdi, [rax+20h]
0x140003dfe  mov     rax, [rsp+58h+var_38]
0x140003e03  cmp     rax, rcx
0x140003e06  jz      short loc_140003E49
0x140003e08  mov     rcx, [rax]
0x140003e0b  cmp     [rcx+8], rax
0x140003e0f  jnz     short loc_140003E5A
0x140003e11  mov     rsi, [rax+8]
0x140003e15  cmp     [rsi], rax
0x140003e18  jnz     short loc_140003E5A
0x140003e1a  lea     rdx, [rax-0A8h]
0x140003e21  mov     rax, [rax+10h]
0x140003e25  mov     [rsi], rcx
0x140003e28  mov     [rcx+8], rsi
0x140003e2c  mov     rcx, rbx
0x140003e2f  movzx   eax, byte ptr [rax]
0x140003e32  mov     rax, [rdi+rax*8+70h]
0x140003e37  call    _guard_dispatch_icall
0x140003e3c  mov     rax, [rsi]
0x140003e3f  lea     rcx, [rsp+58h+var_38]
0x140003e44  cmp     rax, rcx
0x140003e47  jnz     short loc_140003E08
0x140003e49  mov     rbx, [rsp+58h+arg_0]
0x140003e4e  mov     rsi, [rsp+58h+arg_8]
0x140003e53  add     rsp, 50h
0x140003e57  pop     rdi
0x140003e58  retn
0x140003e5a  mov     ecx, 3
0x140003e5f  int     29h; Win8: RtlFailFast(ecx)
```
