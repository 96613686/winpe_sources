# COleControlHost::_PersistInit(void)

- ea: `0x18001f29c`
- end: `0x18001f3d3`
- name: `?_PersistInit@COleControlHost@@IEAAJXZ`
- size: `311`
- prototype: `__int64 __fastcall(COleControlHost *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001eef8`

## callees

- `0x18001f29c`
- `0x18001f3dc`
- `0x180029010`

## import_xrefs

- `ole32!CreateILockBytesOnHGlobal` at `0x18001f350`
- `ole32!CreateILockBytesOnHGlobal` at `0x18001f350`
- `ole32!StgCreateDocfileOnILockBytes` at `0x18001f374`
- `ole32!StgCreateDocfileOnILockBytes` at `0x18001f374`

## pseudocode

```c
__int64 __fastcall COleControlHost::_PersistInit(COleControlHost *this)
{
  HRESULT v3; // ebx
  void (*v4)(void); // rax
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v6; // [rsp+20h] [rbp-10h] BYREF
  __int64 v7; // [rsp+48h] [rbp+18h] BYREF
  IStorage *ppstgOpen; // [rsp+50h] [rbp+20h] BYREF
  LPLOCKBYTES pplkbyt; // [rsp+58h] [rbp+28h] BYREF

  v7 = 0;
  if ( COleControlHost::_SendNotify(this, 0x1302u, 0) == -1 )
    return 1;
  if ( (***((int (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 14))(
         *((_QWORD *)this + 14),
         &IID_IPersistStreamInit,
         &v7) >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 64LL))(v7);
    v4 = *(void (**)(void))(*(_QWORD *)v7 + 16LL);
LABEL_11:
    v4();
    return (unsigned int)v3;
  }
  v5 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 14);
  v6 = 0;
  v3 = (**v5)(v5, &IID_IPersistStorage, &v6);
  if ( v3 >= 0 )
  {
    pplkbyt = 0;
    v3 = CreateILockBytesOnHGlobal(0, 1, &pplkbyt);
    if ( v3 >= 0 )
    {
      ppstgOpen = 0;
      v3 = StgCreateDocfileOnILockBytes(pplkbyt, 0x1012u, 0, &ppstgOpen);
      if ( v3 >= 0 )
      {
        v3 = (*(__int64 (__fastcall **)(__int64, IStorage *))(*(_QWORD *)v6 + 40LL))(v6, ppstgOpen);
        ((void (__fastcall *)(IStorage *))ppstgOpen->lpVtbl->Release)(ppstgOpen);
      }
      ((void (__fastcall *)(LPLOCKBYTES))pplkbyt->lpVtbl->Release)(pplkbyt);
    }
    v4 = *(void (**)(void))(*(_QWORD *)v6 + 16LL);
    goto LABEL_11;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001f29c  mov     [rsp-8+arg_0], rbx
0x18001f2a1  push    rbp
0x18001f2a2  mov     rbp, rsp
0x18001f2a5  sub     rsp, 30h
0x18001f2a9  xor     r8d, r8d; struct tagNMHDR *
0x18001f2ac  mov     [rbp+arg_8], 0
0x18001f2b4  mov     edx, 1302h; unsigned int
0x18001f2b9  mov     rbx, rcx
0x18001f2bc  call    ?_SendNotify@COleControlHost@@IEAA_JIPEAUtagNMHDR@@@Z; COleControlHost::_SendNotify(uint,tagNMHDR *)
0x18001f2c1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001f2c5  jnz     short loc_18001F2D1
0x18001f2c7  mov     eax, 1
0x18001f2cc  jmp     loc_18001F3C8
0x18001f2d1  mov     rcx, [rbx+70h]
0x18001f2d5  lea     r8, [rbp+arg_8]
0x18001f2d9  lea     rdx, IID_IPersistStreamInit
0x18001f2e0  mov     rax, [rcx]
0x18001f2e3  mov     rax, [rax]
0x18001f2e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2eb  test    eax, eax
0x18001f2ed  js      short loc_18001F311
0x18001f2ef  mov     rcx, [rbp+arg_8]
0x18001f2f3  mov     rax, [rcx]
0x18001f2f6  mov     rax, [rax+40h]
0x18001f2fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2ff  mov     rcx, [rbp+arg_8]
0x18001f303  mov     ebx, eax
0x18001f305  mov     rdx, [rcx]
0x18001f308  mov     rax, [rdx+10h]
0x18001f30c  jmp     loc_18001F3C1
0x18001f311  mov     rcx, [rbx+70h]
0x18001f315  lea     r8, [rbp+var_10]
0x18001f319  mov     [rbp+var_10], 0
0x18001f321  lea     rdx, IID_IPersistStorage
0x18001f328  mov     rax, [rcx]
0x18001f32b  mov     rax, [rax]
0x18001f32e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f333  mov     ebx, eax
0x18001f335  test    eax, eax
0x18001f337  js      loc_18001F3C6
0x18001f33d  lea     r8, [rbp+pplkbyt]; pplkbyt
0x18001f341  mov     [rbp+pplkbyt], 0
0x18001f349  mov     edx, 1; fDeleteOnRelease
0x18001f34e  xor     ecx, ecx; hGlobal
0x18001f350  call    cs:__imp_CreateILockBytesOnHGlobal
0x18001f356  mov     ebx, eax
0x18001f358  test    eax, eax
0x18001f35a  js      short loc_18001F3B6
0x18001f35c  mov     rcx, [rbp+pplkbyt]; plkbyt
0x18001f360  lea     r9, [rbp+ppstgOpen]; ppstgOpen
0x18001f364  xor     r8d, r8d; reserved
0x18001f367  mov     [rbp+ppstgOpen], 0
0x18001f36f  mov     edx, 1012h; grfMode
0x18001f374  call    cs:__imp_StgCreateDocfileOnILockBytes
0x18001f37a  mov     ebx, eax
0x18001f37c  test    eax, eax
0x18001f37e  js      short loc_18001F3A6
0x18001f380  mov     rcx, [rbp+var_10]
0x18001f384  mov     rdx, [rbp+ppstgOpen]
0x18001f388  mov     rax, [rcx]
0x18001f38b  mov     rax, [rax+28h]
0x18001f38f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f394  mov     rcx, [rbp+ppstgOpen]
0x18001f398  mov     ebx, eax
0x18001f39a  mov     rax, [rcx]
0x18001f39d  mov     rax, [rax+10h]
0x18001f3a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3a6  mov     rcx, [rbp+pplkbyt]
0x18001f3aa  mov     rax, [rcx]
0x18001f3ad  mov     rax, [rax+10h]
0x18001f3b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3b6  mov     rcx, [rbp+var_10]
0x18001f3ba  mov     rax, [rcx]
0x18001f3bd  mov     rax, [rax+10h]
0x18001f3c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3c6  mov     eax, ebx
0x18001f3c8  mov     rbx, [rsp+30h+arg_0]
0x18001f3cd  add     rsp, 30h
0x18001f3d1  pop     rbp
0x18001f3d2  retn
```
