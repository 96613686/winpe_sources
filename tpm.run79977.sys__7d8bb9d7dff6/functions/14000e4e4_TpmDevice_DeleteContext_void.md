# TpmDevice::DeleteContext(void *)

- ea: `0x14000e4e4`
- end: `0x14000e562`
- name: `?DeleteContext@TpmDevice@@QEAAXPEAX@Z`
- size: `126`
- prototype: `void(TpmDevice *__hidden this, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14000e3ac`
- `0x140021a60`

## callees

- `0x14000e4e4`
- `0x14000e568`
- `0x1400454a0`
- `0x1400454cc`
- `0x1400454f0`

## pseudocode

```c
void __fastcall TpmDevice::DeleteContext(TpmDevice *this, struct TpmContext *a2)
{
  GuardedMutex *v2; // rsi
  struct TpmContext **v5; // r9
  void **v6; // rax

  v2 = (TpmDevice *)((char *)this + 1176);
  GuardedMutex::Acquire((TpmDevice *)((char *)this + 1176));
  TpmScheduler::Cancel((TpmDevice *)((char *)this + 888), a2, 1);
  v5 = (struct TpmContext **)*((_QWORD *)a2 + 2);
  if ( v5[1] != (struct TpmContext *)((char *)a2 + 16) || (v6 = (void **)*((_QWORD *)a2 + 3), *v6 != (char *)a2 + 16) )
    __fastfail(3u);
  *v6 = v5;
  v5[1] = (struct TpmContext *)v6;
  TpmFree(a2);
  --*((_DWORD *)this + 3);
  GuardedMutex::Release(v2);
}

```

## disassembly

```asm
0x14000e4e4  mov     [rsp+arg_0], rbx
0x14000e4e9  mov     [rsp+arg_8], rsi
0x14000e4ee  push    rdi
0x14000e4ef  sub     rsp, 20h
0x14000e4f3  lea     rsi, [rcx+498h]
0x14000e4fa  mov     rbx, rcx
0x14000e4fd  mov     rcx, rsi; this
0x14000e500  mov     rdi, rdx
0x14000e503  call    ?Acquire@GuardedMutex@@QEAAXXZ; GuardedMutex::Acquire(void)
0x14000e508  lea     rcx, [rbx+378h]; this
0x14000e50f  mov     r8b, 1; bool
0x14000e512  mov     rdx, rdi; struct TpmContext *
0x14000e515  call    ?Cancel@TpmScheduler@@QEAAXPEAVTpmContext@@_N@Z; TpmScheduler::Cancel(TpmContext *,bool)
0x14000e51a  lea     r8, [rdi+10h]
0x14000e51e  mov     r9, [r8]
0x14000e521  cmp     [r9+8], r8
0x14000e525  jnz     short loc_14000E55B
0x14000e527  mov     rax, [r8+8]
0x14000e52b  cmp     [rax], r8
0x14000e52e  jnz     short loc_14000E55B
0x14000e530  mov     [rax], r9
0x14000e533  mov     rcx, rdi; void *
0x14000e536  mov     [r9+8], rax
0x14000e53a  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14000e53f  dec     dword ptr [rbx+0Ch]
0x14000e542  mov     rcx, rsi; this
0x14000e545  call    ?Release@GuardedMutex@@QEAAXXZ; GuardedMutex::Release(void)
0x14000e54a  mov     rbx, [rsp+28h+arg_0]
0x14000e54f  mov     rsi, [rsp+28h+arg_8]
0x14000e554  add     rsp, 20h
0x14000e558  pop     rdi
0x14000e559  retn
0x14000e55b  mov     ecx, 3
0x14000e560  int     29h; Win8: RtlFailFast(ecx)
```
