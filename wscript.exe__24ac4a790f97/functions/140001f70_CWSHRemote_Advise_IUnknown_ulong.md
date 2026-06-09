# CWSHRemote::Advise(IUnknown *,ulong *)

- ea: `0x140001f70`
- end: `0x14000205e`
- name: `?Advise@CWSHRemote@@UEAAJPEAUIUnknown@@PEAK@Z`
- size: `238`
- prototype: `__int64 __fastcall(CWSHRemote *__hidden this, struct IUnknown *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x140001f70`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140001f9f`
- `KERNEL32!GetCurrentThreadId` at `0x140001f9f`

## pseudocode

```c
__int64 __fastcall CWSHRemote::Advise(CWSHRemote *this, struct IUnknown *a2, unsigned int *a3)
{
  int v6; // ebx
  struct IUnknownVtbl *lpVtbl; // rax
  unsigned int v8; // ebx
  int v9; // eax
  int v10; // ebx
  __int64 v12; // rcx
  __int64 v13; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = *((_DWORD *)this + 4);
  if ( GetCurrentThreadId() != v6 )
    return 2147549183LL;
  lpVtbl = a2->lpVtbl;
  v13 = 0;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(a2, &IID_IDispatch, &v13) >= 0 )
  {
    v9 = *((_DWORD *)this + 136);
    if ( v9 >= 50 )
    {
LABEL_9:
      *a3 = 0;
      v8 = -2147220991;
    }
    else
    {
      while ( 1 )
      {
        v10 = v9 + 1;
        if ( !*((_QWORD *)this + v9 + 18) )
          break;
        ++v9;
        if ( v10 >= 50 )
          goto LABEL_9;
      }
      v12 = v13;
      *((_QWORD *)this + v9 + 18) = v13;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
      *((_DWORD *)this + 136) = v10;
      *a3 = v10;
      v8 = 0;
    }
  }
  else
  {
    v8 = -2147220990;
  }
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return v8;
}

```

## disassembly

```asm
0x140001f70  push    rbx
0x140001f72  push    rsi
0x140001f73  push    rdi
0x140001f74  push    r14
0x140001f76  sub     rsp, 28h
0x140001f7a  mov     rdi, r8
0x140001f7d  mov     r14, rdx
0x140001f80  mov     rsi, rcx
0x140001f83  test    rdx, rdx
0x140001f86  jz      loc_14000204F
0x140001f8c  test    r8, r8
0x140001f8f  jz      loc_14000204F
0x140001f95  mov     dword ptr [r8], 0
0x140001f9c  mov     ebx, [rcx+10h]
0x140001f9f  call    cs:__imp_GetCurrentThreadId
0x140001fa5  cmp     eax, ebx
0x140001fa7  jnz     loc_140002048
0x140001fad  mov     rax, [r14]
0x140001fb0  lea     r8, [rsp+48h+arg_8]
0x140001fb5  lea     rdx, IID_IDispatch
0x140001fbc  mov     [rsp+48h+arg_8], 0
0x140001fc5  mov     rcx, r14
0x140001fc8  mov     rax, [rax]
0x140001fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001fd0  test    eax, eax
0x140001fd2  jns     short loc_140001FDB
0x140001fd4  mov     ebx, 80040202h
0x140001fd9  jmp     short loc_140002009
0x140001fdb  mov     eax, [rsi+220h]
0x140001fe1  cmp     eax, 32h ; '2'
0x140001fe4  jge     short loc_140001FFE
0x140001fe6  movsxd  rdx, eax
0x140001fe9  lea     ebx, [rax+1]
0x140001fec  cmp     qword ptr [rsi+rdx*8+90h], 0
0x140001ff5  jz      short loc_140002023
0x140001ff7  mov     eax, ebx
0x140001ff9  cmp     ebx, 32h ; '2'
0x140001ffc  jl      short loc_140001FE6
0x140001ffe  mov     dword ptr [rdi], 0
0x140002004  mov     ebx, 80040201h
0x140002009  mov     rcx, [rsp+48h+arg_8]
0x14000200e  test    rcx, rcx
0x140002011  jz      short loc_14000201F
0x140002013  mov     rdx, [rcx]
0x140002016  mov     rax, [rdx+10h]
0x14000201a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000201f  mov     eax, ebx
0x140002021  jmp     short loc_140002054
0x140002023  mov     rcx, [rsp+48h+arg_8]
0x140002028  mov     [rsi+rdx*8+90h], rcx
0x140002030  mov     rax, [rcx]
0x140002033  mov     rax, [rax+8]
0x140002037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000203c  mov     [rsi+220h], ebx
0x140002042  mov     [rdi], ebx
0x140002044  xor     ebx, ebx
0x140002046  jmp     short loc_140002009
0x140002048  mov     eax, 8000FFFFh
0x14000204d  jmp     short loc_140002054
0x14000204f  mov     eax, 80004003h
0x140002054  add     rsp, 28h
0x140002058  pop     r14
0x14000205a  pop     rdi
0x14000205b  pop     rsi
0x14000205c  pop     rbx
0x14000205d  retn
```
