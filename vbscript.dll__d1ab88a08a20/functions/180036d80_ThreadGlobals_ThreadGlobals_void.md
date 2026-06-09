# ThreadGlobals::ThreadGlobals(void)

- ea: `0x180036d80`
- end: `0x180036e3d`
- name: `??0ThreadGlobals@@AEAA@XZ`
- size: `189`
- prototype: `ThreadGlobals *__fastcall(ThreadGlobals *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180036cfc`

## callees

- `0x18001cb34`
- `0x18001eef0`
- `0x180036d80`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x180036e21`
- `KERNEL32!TlsSetValue` at `0x180036e21`
- `KERNEL32!GetCurrentThreadId` at `0x180036db9`
- `KERNEL32!GetCurrentThreadId` at `0x180036db9`

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
0x180036d80  push    rbx
0x180036d82  sub     rsp, 20h
0x180036d86  mov     rbx, rcx
0x180036d89  mov     qword ptr [rcx+18h], 0
0x180036d91  mov     qword ptr [rcx+28h], 0
0x180036d99  mov     qword ptr [rcx+20h], 0
0x180036da1  mov     qword ptr [rcx+30h], 0
0x180036da9  lea     rcx, ?g_mutx@ThreadGlobals@@0VMUTX@@A; this
0x180036db0  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x180036db5  test    eax, eax
0x180036db7  jz      short loc_180036E2D
0x180036db9  call    cs:__imp_GetCurrentThreadId
0x180036dc0  nop     dword ptr [rax+rax+00h]
0x180036dc5  mov     [rbx], eax
0x180036dc7  lea     rdx, [rbx+10h]
0x180036dcb  mov     rax, cs:?g_ptgFirst@ThreadGlobals@@0PEAV1@EA; ThreadGlobals * ThreadGlobals::g_ptgFirst
0x180036dd2  mov     [rdx], rax
0x180036dd5  lea     rax, ?g_ptgFirst@ThreadGlobals@@0PEAV1@EA; ThreadGlobals * ThreadGlobals::g_ptgFirst
0x180036ddc  mov     [rbx+8], rax
0x180036de0  mov     cs:?g_ptgFirst@ThreadGlobals@@0PEAV1@EA, rbx; ThreadGlobals * ThreadGlobals::g_ptgFirst
0x180036de7  mov     rax, [rdx]
0x180036dea  test    rax, rax
0x180036ded  jnz     short loc_180036E37
0x180036def  lea     rcx, ?g_mutx@ThreadGlobals@@0VMUTX@@A; this
0x180036df6  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x180036dfb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180036dff  mov     dword ptr [rbx+48h], 0
0x180036e06  mov     [rbx+38h], rax
0x180036e0a  mov     rdx, rbx; lpTlsValue
0x180036e0d  mov     [rbx+40h], rax
0x180036e11  mov     dword ptr [rbx+90h], 0
0x180036e1b  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180036e21  call    cs:__imp_TlsSetValue
0x180036e28  nop     dword ptr [rax+rax+00h]
0x180036e2d  mov     rax, rbx
0x180036e30  add     rsp, 20h
0x180036e34  pop     rbx
0x180036e35  retn
0x180036e37  mov     [rax+8], rdx
0x180036e3b  jmp     short loc_180036DEF
```
