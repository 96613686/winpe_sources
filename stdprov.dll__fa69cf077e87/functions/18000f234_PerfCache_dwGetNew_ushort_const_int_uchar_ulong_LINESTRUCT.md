# PerfCache::dwGetNew(ushort const *,int,uchar * *,ulong *,_LINESTRUCT *)

- ea: `0x18000f234`
- end: `0x18000f35e`
- name: `?dwGetNew@PerfCache@@QEAAKPEBGHPEAPEAEPEAKPEAU_LINESTRUCT@@@Z`
- size: `298`
- prototype: `unsigned int __fastcall(PerfCache *this, const unsigned __int16 *, int, unsigned __int8 **, unsigned int *, struct _LINESTRUCT *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180010dc8`

## callees

- `0x18000eaa4`
- `0x18000ed70`
- `0x18000ef94`
- `0x18000f090`
- `0x18000f104`
- `0x18000f234`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f2c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f2c1`

## pseudocode

```c
unsigned int __fastcall PerfCache::dwGetNew(
        PerfCache *this,
        const unsigned __int16 *a2,
        int a3,
        unsigned __int8 **a4,
        unsigned int *a5,
        struct _LINESTRUCT *a6)
{
  unsigned int result; // eax
  HKEY v10; // rdx
  int v11; // r9d
  int v12; // ebx

  result = PerfCache::dwGetHandle((PCNZWCH *)this, a2);
  v10 = (HKEY)*((_QWORD *)this + 45);
  if ( v10 && !result )
  {
    if ( (unsigned int)PerfBuff::bOK((PerfCache *)((char *)this + 184), v10, 0x7D0u, a3) )
      goto LABEL_10;
    if ( (unsigned int)PerfBuff::bOK((PerfCache *)((char *)this + 184), *((HKEY *)this + 45), 0x2710u, a3) )
    {
      if ( !(unsigned int)PerfBuff::bOK((PerfCache *)((char *)this + 8), *((HKEY *)this + 45), 0x2710u, a3)
        || (v12 = *((_DWORD *)this + 82), GetTickCount() - v12 >= 0x3E8) )
      {
        PerfBuff::operator=((char *)this + 8, (char *)this + 184);
        if ( !*((_DWORD *)this + 4) )
          return -2147217402;
      }
    }
    result = PerfBuff::Read((PerfCache *)((char *)this + 184), *((HKEY *)this + 45), a3, v11);
    if ( !result )
    {
LABEL_10:
      CIndicyList::SetUse((PerfCache *)((char *)this + 208), a3);
      *a4 = (unsigned __int8 *)*((_QWORD *)this + 25);
      *a5 = *((_DWORD *)this + 49);
      *(_QWORD *)a6 = *((_QWORD *)this + 42);
      *((_QWORD *)a6 + 3) = *((_QWORD *)this + 43);
      *((_QWORD *)a6 + 9) = *((_QWORD *)this + 44);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f234  push    rbx
0x18000f236  push    rbp
0x18000f237  push    rsi
0x18000f238  push    rdi
0x18000f239  push    r14
0x18000f23b  push    r15
0x18000f23d  sub     rsp, 28h
0x18000f241  mov     r15, r9
0x18000f244  mov     ebp, r8d
0x18000f247  mov     rdi, rcx
0x18000f24a  call    ?dwGetHandle@PerfCache@@AEAAKPEBG@Z; PerfCache::dwGetHandle(ushort const *)
0x18000f24f  mov     rdx, [rdi+168h]; HKEY
0x18000f256  test    rdx, rdx
0x18000f259  jz      loc_18000F351
0x18000f25f  test    eax, eax
0x18000f261  jnz     loc_18000F351
0x18000f267  lea     rsi, [rdi+0B8h]
0x18000f26e  mov     r9d, ebp; int
0x18000f271  mov     rcx, rsi; this
0x18000f274  mov     r8d, 7D0h; unsigned int
0x18000f27a  call    ?bOK@PerfBuff@@QEAAHPEAUHKEY__@@KH@Z; PerfBuff::bOK(HKEY__ *,ulong,int)
0x18000f27f  test    eax, eax
0x18000f281  jnz     short loc_18000F2FF
0x18000f283  mov     rdx, [rdi+168h]; HKEY
0x18000f28a  mov     ebx, 2710h
0x18000f28f  mov     r8d, ebx; unsigned int
0x18000f292  mov     r9d, ebp; int
0x18000f295  mov     rcx, rsi; this
0x18000f298  call    ?bOK@PerfBuff@@QEAAHPEAUHKEY__@@KH@Z; PerfBuff::bOK(HKEY__ *,ulong,int)
0x18000f29d  test    eax, eax
0x18000f29f  jz      short loc_18000F2E9
0x18000f2a1  mov     rdx, [rdi+168h]; HKEY
0x18000f2a8  lea     rcx, [rdi+8]; this
0x18000f2ac  mov     r9d, ebp; int
0x18000f2af  mov     r8d, ebx; unsigned int
0x18000f2b2  call    ?bOK@PerfBuff@@QEAAHPEAUHKEY__@@KH@Z; PerfBuff::bOK(HKEY__ *,ulong,int)
0x18000f2b7  test    eax, eax
0x18000f2b9  jz      short loc_18000F2D0
0x18000f2bb  mov     ebx, [rdi+148h]
0x18000f2c1  call    cs:__imp_GetTickCount
0x18000f2c7  sub     eax, ebx
0x18000f2c9  cmp     eax, 3E8h
0x18000f2ce  jb      short loc_18000F2E9
0x18000f2d0  mov     rdx, rsi
0x18000f2d3  lea     rcx, [rdi+8]
0x18000f2d7  call    ??4PerfBuff@@QEAAAEAV0@AEAV0@@Z; PerfBuff::operator=(PerfBuff &)
0x18000f2dc  cmp     dword ptr [rdi+10h], 0
0x18000f2e0  jnz     short loc_18000F2E9
0x18000f2e2  mov     eax, 80041006h
0x18000f2e7  jmp     short loc_18000F351
0x18000f2e9  mov     rdx, [rdi+168h]; HKEY
0x18000f2f0  mov     r8d, ebp; int
0x18000f2f3  mov     rcx, rsi; this
0x18000f2f6  call    ?Read@PerfBuff@@QEAAKPEAUHKEY__@@HH@Z; PerfBuff::Read(HKEY__ *,int,int)
0x18000f2fb  test    eax, eax
0x18000f2fd  jnz     short loc_18000F351
0x18000f2ff  lea     rcx, [rdi+0D0h]; this
0x18000f306  mov     edx, ebp; int
0x18000f308  call    ?SetUse@CIndicyList@@QEAAHH@Z; CIndicyList::SetUse(int)
0x18000f30d  mov     rax, [rdi+0C8h]
0x18000f314  mov     [r15], rax
0x18000f317  mov     ecx, [rdi+0C4h]
0x18000f31d  mov     rax, [rsp+58h+arg_20]
0x18000f325  mov     [rax], ecx
0x18000f327  mov     rax, [rdi+150h]
0x18000f32e  mov     rcx, [rsp+58h+arg_28]
0x18000f336  mov     [rcx], rax
0x18000f339  mov     rax, [rdi+158h]
0x18000f340  mov     [rcx+18h], rax
0x18000f344  mov     rax, [rdi+160h]
0x18000f34b  mov     [rcx+48h], rax
0x18000f34f  xor     eax, eax
0x18000f351  add     rsp, 28h
0x18000f355  pop     r15
0x18000f357  pop     r14
0x18000f359  pop     rdi
0x18000f35a  pop     rsi
0x18000f35b  pop     rbp
0x18000f35c  pop     rbx
0x18000f35d  retn
```
