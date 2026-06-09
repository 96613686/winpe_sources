# LOG_WRITER::LOG_WRITER(void)

- ea: `0x180002094`
- end: `0x1800021bc`
- name: `??0LOG_WRITER@@QEAA@XZ`
- size: `296`
- prototype: `LOG_WRITER *__fastcall(LOG_WRITER *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007670`
- `0x180008174`

## callees

- `0x180002094`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180002189`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180002189`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180002181`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180002181`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800020c1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800020cc`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800020c1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800020cc`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800020dd`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800020dd`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800020f8`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002113`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800020f8`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002113`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000212e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000212e`

## pseudocode

```c
LOG_WRITER *__fastcall LOG_WRITER::LOG_WRITER(LOG_WRITER *this)
{
  struct _SYSTEMTIME *v2; // rcx
  __int64 v3; // rax

  *(_QWORD *)this = &LOG_WRITER::`vftable';
  *((_QWORD *)this + 1) = 0;
  STRU::STRU((LOG_WRITER *)((char *)this + 16));
  STRU::STRU((LOG_WRITER *)((char *)this + 72));
  STRA::STRA((LOG_WRITER *)((char *)this + 128));
  STRA::STRA((LOG_WRITER *)((char *)this + 184), (char *)this + 240, 0x100u);
  STRA::STRA((LOG_WRITER *)((char *)this + 496), (char *)this + 552, 1u);
  STRU::STRU((LOG_WRITER *)((char *)this + 560), (unsigned __int16 *)this + 308, 2u);
  *(_QWORD *)((char *)this + 620) = 0;
  *((_QWORD *)this + 79) = -1;
  *((_QWORD *)this + 80) = 0;
  *((_QWORD *)this + 83) = 0;
  *((_QWORD *)this + 84) = 1;
  v2 = (struct _SYSTEMTIME *)((char *)this + 648);
  v3 = *((_QWORD *)this + 1);
  if ( v3 && *(_DWORD *)(v3 + 4) == 1 )
    GetLocalTime(v2);
  else
    GetSystemTime(v2);
  **((_WORD **)this + 13) = 0;
  *((_DWORD *)this + 30) = 0;
  **((_BYTE **)this + 20) = 0;
  *((_DWORD *)this + 44) = 0;
  return this;
}

```

## disassembly

```asm
0x180002094  mov     [rsp+arg_8], rbx
0x180002099  mov     [rsp+arg_10], rsi
0x18000209e  mov     [rsp+arg_0], rcx
0x1800020a3  push    rdi
0x1800020a4  sub     rsp, 20h
0x1800020a8  mov     rbx, rcx
0x1800020ab  lea     rax, ??_7LOG_WRITER@@6B@; const LOG_WRITER::`vftable'
0x1800020b2  mov     [rcx], rax
0x1800020b5  mov     qword ptr [rcx+8], 0
0x1800020bd  add     rcx, 10h
0x1800020c1  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800020c7  nop
0x1800020c8  lea     rcx, [rbx+48h]
0x1800020cc  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800020d2  nop
0x1800020d3  lea     rsi, [rbx+80h]
0x1800020da  mov     rcx, rsi
0x1800020dd  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x1800020e3  nop
0x1800020e4  lea     rdx, [rbx+0F0h]
0x1800020eb  lea     rcx, [rbx+0B8h]
0x1800020f2  mov     r8d, 100h
0x1800020f8  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800020fe  nop
0x1800020ff  lea     rdx, [rbx+228h]
0x180002106  lea     rcx, [rbx+1F0h]
0x18000210d  mov     r8d, 1
0x180002113  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180002119  nop
0x18000211a  lea     rdx, [rbx+268h]
0x180002121  lea     rcx, [rbx+230h]
0x180002128  mov     r8d, 2
0x18000212e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002134  mov     qword ptr [rbx+26Ch], 0
0x18000213f  mov     qword ptr [rbx+278h], 0FFFFFFFFFFFFFFFFh
0x18000214a  mov     qword ptr [rbx+280h], 0
0x180002155  mov     qword ptr [rbx+298h], 0
0x180002160  mov     qword ptr [rbx+2A0h], 1
0x18000216b  lea     rcx, [rbx+288h]; lpSystemTime
0x180002172  mov     rax, [rbx+8]
0x180002176  test    rax, rax
0x180002179  jz      short loc_180002189
0x18000217b  cmp     dword ptr [rax+4], 1
0x18000217f  jnz     short loc_180002189
0x180002181  call    cs:__imp_GetLocalTime
0x180002187  jmp     short loc_18000218F
0x180002189  call    cs:__imp_GetSystemTime
0x18000218f  mov     rcx, [rbx+68h]
0x180002193  xor     eax, eax
0x180002195  mov     [rcx], ax
0x180002198  mov     [rbx+78h], eax
0x18000219b  mov     rax, [rsi+20h]
0x18000219f  mov     byte ptr [rax], 0
0x1800021a2  mov     dword ptr [rsi+30h], 0
0x1800021a9  mov     rax, rbx
0x1800021ac  mov     rbx, [rsp+28h+arg_8]
0x1800021b1  mov     rsi, [rsp+28h+arg_10]
0x1800021b6  add     rsp, 20h
0x1800021ba  pop     rdi
0x1800021bb  retn
```
