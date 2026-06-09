# ThreadGlobals::ThreadGlobals(void)

- ea: `0x18003581c`
- end: `0x1800358cc`
- name: `??0ThreadGlobals@@AEAA@XZ`
- size: `176`
- prototype: `ThreadGlobals *__fastcall(ThreadGlobals *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800357a0`

## callees

- `0x180022ce0`
- `0x1800238f4`
- `0x18003581c`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x1800358b7`
- `KERNEL32!TlsSetValue` at `0x1800358b7`
- `KERNEL32!GetCurrentThreadId` at `0x180035855`
- `KERNEL32!GetCurrentThreadId` at `0x180035855`

## pseudocode

```c
ThreadGlobals *__fastcall ThreadGlobals::ThreadGlobals(ThreadGlobals *this)
{
  __int64 v2; // rax

  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 6) = 0;
  if ( (unsigned int)MUTX::Enter((MUTX *)&ThreadGlobals::g_mutx) )
  {
    *(_DWORD *)this = GetCurrentThreadId();
    *((_QWORD *)this + 2) = ThreadGlobals::g_ptgFirst;
    *((_QWORD *)this + 1) = &ThreadGlobals::g_ptgFirst;
    ThreadGlobals::g_ptgFirst = this;
    v2 = *((_QWORD *)this + 2);
    if ( v2 )
      *(_QWORD *)(v2 + 8) = (char *)this + 16;
    MUTX::Leave((MUTX *)&ThreadGlobals::g_mutx);
    *((_DWORD *)this + 18) = 0;
    *((_QWORD *)this + 7) = -1;
    *((_QWORD *)this + 8) = -1;
    *((_DWORD *)this + 36) = 0;
    TlsSetValue(g_luTls, this);
  }
  return this;
}

```

## disassembly

```asm
0x18003581c  push    rbx
0x18003581e  sub     rsp, 20h
0x180035822  mov     rbx, rcx
0x180035825  mov     qword ptr [rcx+18h], 0
0x18003582d  mov     qword ptr [rcx+28h], 0
0x180035835  mov     qword ptr [rcx+20h], 0
0x18003583d  mov     qword ptr [rcx+30h], 0
0x180035845  lea     rcx, ?g_mutx@ThreadGlobals@@0VMUTX@@A; this
0x18003584c  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x180035851  test    eax, eax
0x180035853  jz      short loc_1800358BD
0x180035855  call    cs:__imp_GetCurrentThreadId
0x18003585b  mov     [rbx], eax
0x18003585d  lea     rdx, [rbx+10h]
0x180035861  mov     rax, cs:?g_ptgFirst@ThreadGlobals@@0PEAV1@EA; ThreadGlobals * ThreadGlobals::g_ptgFirst
0x180035868  mov     [rdx], rax
0x18003586b  lea     rax, ?g_ptgFirst@ThreadGlobals@@0PEAV1@EA; ThreadGlobals * ThreadGlobals::g_ptgFirst
0x180035872  mov     [rbx+8], rax
0x180035876  mov     cs:?g_ptgFirst@ThreadGlobals@@0PEAV1@EA, rbx; ThreadGlobals * ThreadGlobals::g_ptgFirst
0x18003587d  mov     rax, [rdx]
0x180035880  test    rax, rax
0x180035883  jnz     short loc_1800358C6
0x180035885  lea     rcx, ?g_mutx@ThreadGlobals@@0VMUTX@@A; this
0x18003588c  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x180035891  or      rax, 0FFFFFFFFFFFFFFFFh
0x180035895  mov     dword ptr [rbx+48h], 0
0x18003589c  mov     [rbx+38h], rax
0x1800358a0  mov     rdx, rbx; lpTlsValue
0x1800358a3  mov     [rbx+40h], rax
0x1800358a7  mov     dword ptr [rbx+90h], 0
0x1800358b1  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x1800358b7  call    cs:__imp_TlsSetValue
0x1800358bd  mov     rax, rbx
0x1800358c0  add     rsp, 20h
0x1800358c4  pop     rbx
0x1800358c5  retn
0x1800358c6  mov     [rax+8], rdx
0x1800358ca  jmp     short loc_180035885
```
