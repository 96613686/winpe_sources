# ATL::AtlModuleInit(ATL::_ATL_MODULE *,ATL::_ATL_OBJMAP_ENTRY *,HINSTANCE__ *)

- ea: `0x14000a4e4`
- end: `0x14000a686`
- name: `?AtlModuleInit@ATL@@YAJPEAU_ATL_MODULE@1@PEAU_ATL_OBJMAP_ENTRY@1@PEAUHINSTANCE__@@@Z`
- size: `418`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *, struct ATL::_ATL_OBJMAP_ENTRY *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ccb8`

## callees

- `0x14000a4e4`
- `0x14000f010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x14000a52f`
- `KERNEL32!InitializeCriticalSection` at `0x14000a53a`
- `KERNEL32!InitializeCriticalSection` at `0x14000a548`
- `KERNEL32!InitializeCriticalSection` at `0x14000a52f`
- `KERNEL32!InitializeCriticalSection` at `0x14000a53a`
- `KERNEL32!InitializeCriticalSection` at `0x14000a548`
- `KERNEL32!DeleteCriticalSection` at `0x14000a5d5`
- `KERNEL32!DeleteCriticalSection` at `0x14000a5df`
- `KERNEL32!DeleteCriticalSection` at `0x14000a630`
- `KERNEL32!DeleteCriticalSection` at `0x14000a5d5`
- `KERNEL32!DeleteCriticalSection` at `0x14000a5df`
- `KERNEL32!DeleteCriticalSection` at `0x14000a630`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleInit(struct ATL::_ATL_MODULE *a1, struct ATL::_ATL_OBJMAP_ENTRY *a2, HINSTANCE a3)
{
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // rax

  if ( !a1 )
    return 2147942487LL;
  *((_QWORD *)a1 + 4) = &off_140015140;
  *((_QWORD *)a1 + 2) = a3;
  *((_QWORD *)a1 + 3) = a3;
  *((_QWORD *)a1 + 1) = a3;
  *((_DWORD *)a1 + 10) = 0;
  *((_QWORD *)a1 + 6) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 56));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 96));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 136));
  *((_QWORD *)a1 + 23) = 0;
  *((_BYTE *)a1 + 192) = 1;
  *((_DWORD *)a1 + 52) = 0;
  *((_DWORD *)a1 + 56) = 0;
  *((_QWORD *)a1 + 27) = 0;
  *((_QWORD *)a1 + 29) = 0;
  v6 = *((_QWORD *)a1 + 4);
  if ( v6 )
  {
    while ( *(_QWORD *)v6 )
    {
      LOBYTE(v5) = 1;
      (*(void (__fastcall **)(__int64))(v6 + 64))(v5);
      v7 = 56;
      v5 = 72;
      if ( *(_DWORD *)a1 != 176 )
        v7 = 72;
      v6 += v7;
    }
  }
  *((_DWORD *)a1 + 60) = 1;
  return 0;
}

```

## disassembly

```asm
0x14000a4e4  mov     [rsp+arg_8], rbx
0x14000a4e9  mov     [rsp+arg_0], rcx
0x14000a4ee  push    rdi
0x14000a4ef  sub     rsp, 20h
0x14000a4f3  mov     rbx, rcx
0x14000a4f6  test    rcx, rcx
0x14000a4f9  jnz     short loc_14000A505
0x14000a4fb  mov     eax, 80070057h
0x14000a500  jmp     loc_14000A67B
0x14000a505  lea     rax, off_140015140
0x14000a50c  mov     [rcx+20h], rax
0x14000a510  mov     [rcx+10h], r8
0x14000a514  mov     [rcx+18h], r8
0x14000a518  mov     [rcx+8], r8
0x14000a51c  mov     dword ptr [rcx+28h], 0
0x14000a523  mov     qword ptr [rcx+30h], 0
0x14000a52b  add     rcx, 38h ; '8'; lpCriticalSection
0x14000a52f  call    cs:__imp_InitializeCriticalSection
0x14000a535  nop
0x14000a536  lea     rcx, [rbx+60h]; lpCriticalSection
0x14000a53a  call    cs:__imp_InitializeCriticalSection
0x14000a540  nop
0x14000a541  lea     rcx, [rbx+88h]; lpCriticalSection
0x14000a548  call    cs:__imp_InitializeCriticalSection
0x14000a54e  nop
0x14000a54f  mov     qword ptr [rbx+0B8h], 0
0x14000a55a  mov     byte ptr [rbx+0C0h], 1
0x14000a561  mov     dword ptr [rbx+0D0h], 0
0x14000a56b  mov     dword ptr [rbx+0E0h], 0
0x14000a575  mov     qword ptr [rbx+0D8h], 0
0x14000a580  mov     qword ptr [rbx+0E8h], 0
0x14000a58b  mov     rdi, [rbx+20h]
0x14000a58f  test    rdi, rdi
0x14000a592  jz      short loc_14000A5BB
0x14000a594  jmp     short loc_14000A5B5
0x14000a596  mov     cl, 1
0x14000a598  mov     rax, [rdi+40h]
0x14000a59c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a5a1  mov     eax, 38h ; '8'
0x14000a5a6  lea     ecx, [rax+10h]
0x14000a5a9  cmp     dword ptr [rbx], 0B0h
0x14000a5af  cmovnz  eax, ecx
0x14000a5b2  add     rdi, rax
0x14000a5b5  cmp     qword ptr [rdi], 0
0x14000a5b9  jnz     short loc_14000A596
0x14000a5bb  mov     dword ptr [rbx+0F0h], 1
0x14000a5c5  xor     eax, eax
0x14000a5c7  jmp     loc_14000A67B
0x14000a5cc  mov     rbx, [rsp+28h+arg_0]
0x14000a5d1  lea     rcx, [rbx+60h]; lpCriticalSection
0x14000a5d5  call    cs:__imp_DeleteCriticalSection
0x14000a5db  lea     rcx, [rbx+38h]; lpCriticalSection
0x14000a5df  call    cs:__imp_DeleteCriticalSection
0x14000a5e5  xorps   xmm0, xmm0
0x14000a5e8  xor     eax, eax
0x14000a5ea  movups  xmmword ptr [rbx+88h], xmm0
0x14000a5f1  movups  xmmword ptr [rbx+98h], xmm0
0x14000a5f8  mov     [rbx+0A8h], rax
0x14000a5ff  xorps   xmm0, xmm0
0x14000a602  movups  xmmword ptr [rbx+60h], xmm0
0x14000a606  movups  xmmword ptr [rbx+70h], xmm0
0x14000a60a  mov     [rbx+80h], rax
0x14000a611  xorps   xmm0, xmm0
0x14000a614  movups  xmmword ptr [rbx+38h], xmm0
0x14000a618  movups  xmmword ptr [rbx+48h], xmm0
0x14000a61c  mov     [rbx+58h], rax
0x14000a620  mov     eax, 0C0000017h
0x14000a625  jmp     short loc_14000A67B
0x14000a627  mov     rbx, [rsp+28h+arg_0]
0x14000a62c  lea     rcx, [rbx+38h]; lpCriticalSection
0x14000a630  call    cs:__imp_DeleteCriticalSection
0x14000a636  xorps   xmm0, xmm0
0x14000a639  xor     eax, eax
0x14000a63b  movups  xmmword ptr [rbx+60h], xmm0
0x14000a63f  movups  xmmword ptr [rbx+70h], xmm0
0x14000a643  mov     [rbx+80h], rax
0x14000a64a  xorps   xmm0, xmm0
0x14000a64d  movups  xmmword ptr [rbx+38h], xmm0
0x14000a651  movups  xmmword ptr [rbx+48h], xmm0
0x14000a655  mov     [rbx+58h], rax
0x14000a659  mov     eax, 0C0000017h
0x14000a65e  jmp     short loc_14000A67B
0x14000a660  mov     rax, [rsp+28h+arg_0]
0x14000a665  xorps   xmm0, xmm0
0x14000a668  xor     ecx, ecx
0x14000a66a  movups  xmmword ptr [rax+38h], xmm0
0x14000a66e  movups  xmmword ptr [rax+48h], xmm0
0x14000a672  mov     [rax+58h], rcx
0x14000a676  mov     eax, 0C0000017h
0x14000a67b  mov     rbx, [rsp+28h+arg_8]
0x14000a680  add     rsp, 20h
0x14000a684  pop     rdi
0x14000a685  retn
0x14000e4c1  push    rbp
0x14000e4c3  sub     rsp, 20h
0x14000e4c7  mov     rbp, rdx
0x14000e4ca  mov     rax, [rcx]
0x14000e4cd  xor     ecx, ecx
0x14000e4cf  cmp     dword ptr [rax], 0C0000017h
0x14000e4d5  setz    cl
0x14000e4d8  mov     eax, ecx
0x14000e4da  add     rsp, 20h
0x14000e4de  pop     rbp
0x14000e4df  retn
0x14000e4e1  push    rbp
0x14000e4e3  sub     rsp, 20h
0x14000e4e7  mov     rbp, rdx
0x14000e4ea  mov     rax, [rcx]
0x14000e4ed  xor     ecx, ecx
0x14000e4ef  cmp     dword ptr [rax], 0C0000017h
0x14000e4f5  setz    cl
0x14000e4f8  mov     eax, ecx
0x14000e4fa  add     rsp, 20h
0x14000e4fe  pop     rbp
0x14000e4ff  retn
0x14000e501  push    rbp
0x14000e503  sub     rsp, 20h
0x14000e507  mov     rbp, rdx
0x14000e50a  mov     rax, [rcx]
0x14000e50d  xor     ecx, ecx
0x14000e50f  cmp     dword ptr [rax], 0C0000017h
0x14000e515  setz    cl
0x14000e518  mov     eax, ecx
0x14000e51a  add     rsp, 20h
0x14000e51e  pop     rbp
0x14000e51f  retn
```
