# PerfCache::dwGetPair(ushort const *,int,uchar * *,ulong *,uchar * *,ulong *,_LINESTRUCT *)

- ea: `0x18000f364`
- end: `0x18000f4c4`
- name: `?dwGetPair@PerfCache@@QEAAKPEBGHPEAPEAEPEAK12PEAU_LINESTRUCT@@@Z`
- size: `352`
- prototype: `unsigned int __fastcall(PerfCache *this, const unsigned __int16 *, int, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, struct _LINESTRUCT *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180011300`

## callees

- `0x18000eaa4`
- `0x18000ed70`
- `0x18000ef94`
- `0x18000f090`
- `0x18000f364`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f3fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f3fd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000f410`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000f410`

## pseudocode

```c
unsigned int __fastcall PerfCache::dwGetPair(
        PerfCache *this,
        const unsigned __int16 *a2,
        int a3,
        unsigned __int8 **a4,
        unsigned int *a5,
        unsigned __int8 **a6,
        unsigned int *a7,
        struct _LINESTRUCT *a8)
{
  unsigned int result; // eax
  int v12; // ebx
  unsigned int v13; // eax
  int v14; // r9d

  if ( (unsigned int)PerfBuff::bOK((PerfCache *)((char *)this + 8), *((HKEY *)this + 45), 0x2710u, a3) )
  {
    CIndicyList::SetUse((PerfCache *)((char *)this + 32), a3);
    *a4 = (unsigned __int8 *)*((_QWORD *)this + 3);
    *a5 = *((_DWORD *)this + 5);
    *((_QWORD *)a8 + 1) = *((_QWORD *)this + 20);
    *((_QWORD *)a8 + 2) = *((_QWORD *)this + 21);
    return 0;
  }
  PerfBuff::operator=((char *)this + 8, (char *)this + 184);
  if ( !*((_DWORD *)this + 4) )
    return -2147217402;
  v12 = *((_DWORD *)this + 38);
  v13 = GetTickCount() - v12;
  if ( v13 < 0x3E8 )
    Sleep(1000 - v13);
  result = PerfBuff::Read((PerfCache *)((char *)this + 184), *((HKEY *)this + 45), a3, v14);
  if ( !result )
  {
    CIndicyList::SetUse((PerfCache *)((char *)this + 208), a3);
    *a6 = (unsigned __int8 *)*((_QWORD *)this + 25);
    *a7 = *((_DWORD *)this + 49);
    CIndicyList::SetUse((PerfCache *)((char *)this + 32), a3);
    *a4 = (unsigned __int8 *)*((_QWORD *)this + 3);
    *a5 = *((_DWORD *)this + 5);
    *((_QWORD *)a8 + 1) = *((_QWORD *)this + 20);
    *((_QWORD *)a8 + 2) = *((_QWORD *)this + 21);
    *(_QWORD *)a8 = *((_QWORD *)this + 42);
    *((_QWORD *)a8 + 3) = *((_QWORD *)this + 43);
    *((_QWORD *)a8 + 9) = *((_QWORD *)this + 44);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000f364  push    rbx
0x18000f366  push    rbp
0x18000f367  push    rsi
0x18000f368  push    rdi
0x18000f369  push    r14
0x18000f36b  sub     rsp, 20h
0x18000f36f  mov     rdx, [rcx+168h]; HKEY
0x18000f376  mov     r14, r9
0x18000f379  mov     r9d, r8d; int
0x18000f37c  mov     esi, r8d
0x18000f37f  mov     rdi, rcx
0x18000f382  mov     r8d, 2710h; unsigned int
0x18000f388  add     rcx, 8; this
0x18000f38c  call    ?bOK@PerfBuff@@QEAAHPEAUHKEY__@@KH@Z; PerfBuff::bOK(HKEY__ *,ulong,int)
0x18000f391  test    eax, eax
0x18000f393  jz      short loc_18000F3D4
0x18000f395  lea     rcx, [rdi+20h]; this
0x18000f399  mov     edx, esi; int
0x18000f39b  call    ?SetUse@CIndicyList@@QEAAHH@Z; CIndicyList::SetUse(int)
0x18000f3a0  mov     rax, [rdi+18h]
0x18000f3a4  mov     [r14], rax
0x18000f3a7  mov     ecx, [rdi+14h]
0x18000f3aa  mov     rax, [rsp+48h+arg_20]
0x18000f3af  mov     [rax], ecx
0x18000f3b1  mov     rax, [rdi+0A0h]
0x18000f3b8  mov     rcx, [rsp+48h+arg_38]
0x18000f3c0  mov     [rcx+8], rax
0x18000f3c4  mov     rax, [rdi+0A8h]
0x18000f3cb  mov     [rcx+10h], rax
0x18000f3cf  jmp     loc_18000F4B7
0x18000f3d4  lea     rbp, [rdi+0B8h]
0x18000f3db  mov     rdx, rbp
0x18000f3de  lea     rcx, [rdi+8]
0x18000f3e2  call    ??4PerfBuff@@QEAAAEAV0@AEAV0@@Z; PerfBuff::operator=(PerfBuff &)
0x18000f3e7  cmp     dword ptr [rdi+10h], 0
0x18000f3eb  jnz     short loc_18000F3F7
0x18000f3ed  mov     eax, 80041006h
0x18000f3f2  jmp     loc_18000F4B9
0x18000f3f7  mov     ebx, [rdi+98h]
0x18000f3fd  call    cs:__imp_GetTickCount
0x18000f403  sub     eax, ebx
0x18000f405  mov     ecx, 3E8h
0x18000f40a  cmp     eax, ecx
0x18000f40c  jnb     short loc_18000F416
0x18000f40e  sub     ecx, eax; dwMilliseconds
0x18000f410  call    cs:__imp_Sleep
0x18000f416  mov     rdx, [rdi+168h]; HKEY
0x18000f41d  mov     r8d, esi; int
0x18000f420  mov     rcx, rbp; this
0x18000f423  call    ?Read@PerfBuff@@QEAAKPEAUHKEY__@@HH@Z; PerfBuff::Read(HKEY__ *,int,int)
0x18000f428  test    eax, eax
0x18000f42a  jnz     loc_18000F4B9
0x18000f430  lea     rcx, [rdi+0D0h]; this
0x18000f437  mov     edx, esi; int
0x18000f439  call    ?SetUse@CIndicyList@@QEAAHH@Z; CIndicyList::SetUse(int)
0x18000f43e  mov     rcx, [rdi+0C8h]
0x18000f445  mov     edx, esi; int
0x18000f447  mov     rax, [rsp+48h+arg_28]
0x18000f44c  mov     [rax], rcx
0x18000f44f  mov     ecx, [rdi+0C4h]
0x18000f455  mov     rax, [rsp+48h+arg_30]
0x18000f45d  mov     [rax], ecx
0x18000f45f  lea     rcx, [rdi+20h]; this
0x18000f463  call    ?SetUse@CIndicyList@@QEAAHH@Z; CIndicyList::SetUse(int)
0x18000f468  mov     rax, [rdi+18h]
0x18000f46c  mov     [r14], rax
0x18000f46f  mov     ecx, [rdi+14h]
0x18000f472  mov     rax, [rsp+48h+arg_20]
0x18000f477  mov     [rax], ecx
0x18000f479  mov     rax, [rdi+0A0h]
0x18000f480  mov     rcx, [rsp+48h+arg_38]
0x18000f488  mov     [rcx+8], rax
0x18000f48c  mov     rax, [rdi+0A8h]
0x18000f493  mov     [rcx+10h], rax
0x18000f497  mov     rax, [rdi+150h]
0x18000f49e  mov     [rcx], rax
0x18000f4a1  mov     rax, [rdi+158h]
0x18000f4a8  mov     [rcx+18h], rax
0x18000f4ac  mov     rax, [rdi+160h]
0x18000f4b3  mov     [rcx+48h], rax
0x18000f4b7  xor     eax, eax
0x18000f4b9  add     rsp, 20h
0x18000f4bd  pop     r14
0x18000f4bf  pop     rdi
0x18000f4c0  pop     rsi
0x18000f4c1  pop     rbp
0x18000f4c2  pop     rbx
0x18000f4c3  retn
```
