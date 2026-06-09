# IsDiamondFile(char *)

- ea: `0x1800025b8`
- end: `0x18000268f`
- name: `?IsDiamondFile@@YAHPEAD@Z`
- size: `215`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180002b00`

## callees

- `0x1800025b8`
- `0x1800026f0`
- `0x1800031b0`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800025f2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002603`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002638`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002649`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800025f2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002603`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002638`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002649`
- `KERNEL32!_lclose` at `0x18000266b`
- `KERNEL32!_lclose` at `0x18000266b`

## pseudocode

```c
__int64 __fastcall IsDiamondFile(char *a1)
{
  __int64 v2; // rdi
  int (*v3)(void *, __int64, struct FDICABINETINFO *); // rbx
  __int64 v4; // rcx
  unsigned int v5; // ebx
  __int128 v7; // [rsp+20h] [rbp-28h] BYREF
  __int64 v8; // [rsp+30h] [rbp-18h]

  v8 = 0;
  v7 = 0;
  if ( itlsDiamondContext == -1 )
    return 0;
  if ( !TlsGetValue(itlsDiamondContext) )
    return 0;
  if ( !*((_QWORD *)TlsGetValue(itlsDiamondContext) + 1) )
    return 0;
  v2 = SpdFdiOpen(a1, 0);
  if ( v2 == -1 )
    return 0;
  v3 = pFDIIsCabinet;
  if ( itlsDiamondContext == -1 || !TlsGetValue(itlsDiamondContext) )
    v4 = 0;
  else
    v4 = *((_QWORD *)TlsGetValue(itlsDiamondContext) + 1);
  v5 = ((__int64 (__fastcall *)(__int64, __int64, __int128 *))v3)(v4, v2, &v7);
  _lclose(v2);
  return v5;
}

```

## disassembly

```asm
0x1800025b8  mov     [rsp+arg_8], rbx
0x1800025bd  push    rdi
0x1800025be  sub     rsp, 40h
0x1800025c2  mov     rax, cs:__security_cookie
0x1800025c9  xor     rax, rsp
0x1800025cc  mov     [rsp+48h+var_10], rax
0x1800025d1  xor     eax, eax
0x1800025d3  mov     rbx, rcx
0x1800025d6  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x1800025dc  xorps   xmm0, xmm0
0x1800025df  mov     [rsp+48h+var_18], rax
0x1800025e4  movups  [rsp+48h+var_28], xmm0
0x1800025e9  cmp     ecx, 0FFFFFFFFh
0x1800025ec  jz      loc_180002675
0x1800025f2  call    cs:__imp_TlsGetValue
0x1800025f8  test    rax, rax
0x1800025fb  jz      short loc_180002675
0x1800025fd  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x180002603  call    cs:__imp_TlsGetValue
0x180002609  cmp     qword ptr [rax+8], 0
0x18000260e  jz      short loc_180002675
0x180002610  xor     r8d, r8d; int
0x180002613  xor     edx, edx; int
0x180002615  mov     rcx, rbx; char *
0x180002618  call    ?SpdFdiOpen@@YA_JPEADHH@Z; SpdFdiOpen(char *,int,int)
0x18000261d  mov     rdi, rax
0x180002620  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002624  jz      short loc_180002675
0x180002626  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x18000262c  mov     rbx, cs:?pFDIIsCabinet@@3P6AHPEAX_JPEAUFDICABINETINFO@@@ZEA; int (*pFDIIsCabinet)(void *,__int64,FDICABINETINFO *)
0x180002633  cmp     ecx, 0FFFFFFFFh
0x180002636  jz      short loc_180002655
0x180002638  call    cs:__imp_TlsGetValue
0x18000263e  test    rax, rax
0x180002641  jz      short loc_180002655
0x180002643  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x180002649  call    cs:__imp_TlsGetValue
0x18000264f  mov     rcx, [rax+8]
0x180002653  jmp     short loc_180002657
0x180002655  xor     ecx, ecx
0x180002657  lea     r8, [rsp+48h+var_28]
0x18000265c  mov     rdx, rdi
0x18000265f  mov     rax, rbx
0x180002662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002667  mov     ecx, edi; hFile
0x180002669  mov     ebx, eax
0x18000266b  call    cs:__imp__lclose
0x180002671  mov     eax, ebx
0x180002673  jmp     short loc_180002677
0x180002675  xor     eax, eax
0x180002677  mov     rcx, [rsp+48h+var_10]
0x18000267c  xor     rcx, rsp; StackCookie
0x18000267f  call    __security_check_cookie
0x180002684  mov     rbx, [rsp+48h+arg_8]
0x180002689  add     rsp, 40h
0x18000268d  pop     rdi
0x18000268e  retn
```
