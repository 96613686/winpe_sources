# CStorage::DeleteType(unsigned __int64)

- ea: `0x180011ef4`
- end: `0x18001203e`
- name: `?DeleteType@CStorage@@QEAAH_K@Z`
- size: `330`
- prototype: `__int64 __fastcall(CStorage *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011578`

## callees

- `0x18000ffa4`
- `0x180011ef4`
- `0x1800274d2`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001202b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180028933`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001202b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180028933`

## pseudocode

```c
__int64 __fastcall CStorage::DeleteType(CStorage *this, __int64 a2)
{
  unsigned int v3; // edi
  __int64 v5; // rsi
  __int64 i; // rbx
  unsigned int v7; // edx
  _QWORD *v8; // rcx
  __int64 v9; // [rsp+68h] [rbp+10h] BYREF

  v9 = a2;
  (*(void (__fastcall **)(struct IKernel32Interface *, _QWORD, __int64))(*(_QWORD *)g_Kernel32 + 416LL))(
    g_Kernel32,
    *(_QWORD *)this,
    0xFFFFFFFFLL);
  v9 = 0;
  v3 = 0;
  if ( *((_DWORD *)this + 11) )
    return 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *))(**((_QWORD **)this + 8) + 16LL))(
         *((_QWORD *)this + 8),
         0,
         256,
         &v9);
  if ( v5 )
  {
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      v7 = *(_DWORD *)(v5 + 20);
      if ( (unsigned int)i >= v7 )
        break;
      v8 = (_QWORD *)(v5 + 8 * ((unsigned int)i + 4 * i + 3));
      if ( *v8 == 0x4D53424C4B425244LL )
      {
        if ( !v8[2] )
        {
          if ( (unsigned int)i < v7 - 1 )
            memmove_0(v8, (const void *)(v5 + 8 * (5LL * (unsigned int)(i + 1) + 3)), 40LL * (v7 - (unsigned int)i));
          v7 = --*(_DWORD *)(v5 + 20);
          v3 = 1;
        }
        break;
      }
    }
    if ( v3 )
    {
      *(_DWORD *)(v5 + 8) = 1;
      v3 = CStorage::CheckAndRestoreIntegrity(this);
    }
    else
    {
      v3 = (unsigned int)i >= v7;
    }
  }
  if ( v9 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 24LL))(*((_QWORD *)this + 8));
  ReleaseMutex(*(HANDLE *)this);
  return v3;
}

```

## disassembly

```asm
0x180011ef4  mov     rax, rsp
0x180011ef7  mov     [rax+18h], rbx
0x180011efb  mov     [rax+20h], rsi
0x180011eff  mov     [rax+10h], rdx
0x180011f03  mov     [rax+8], rcx
0x180011f07  push    rdi
0x180011f08  push    r12
0x180011f0a  push    r14
0x180011f0c  sub     rsp, 40h
0x180011f10  mov     r14, rcx
0x180011f13  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180011f1a  mov     rax, [rcx]
0x180011f1d  or      r8d, 0FFFFFFFFh
0x180011f21  mov     rdx, [r14]
0x180011f24  mov     rax, [rax+1A0h]
0x180011f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f30  mov     [rsp+58h+arg_8], 0
0x180011f39  xor     edi, edi
0x180011f3b  cmp     [r14+2Ch], edi
0x180011f3f  jz      short loc_180011F58
0x180011f41  xor     eax, eax
0x180011f43  mov     rbx, [rsp+58h+arg_10]
0x180011f48  mov     rsi, [rsp+58h+arg_18]
0x180011f4d  add     rsp, 40h
0x180011f51  pop     r14
0x180011f53  pop     r12
0x180011f55  pop     rdi
0x180011f56  retn
0x180011f58  mov     rcx, [r14+40h]
0x180011f5c  mov     rax, [rcx]
0x180011f5f  lea     r9, [rsp+58h+arg_8]
0x180011f64  xor     edx, edx
0x180011f66  mov     r8d, 100h
0x180011f6c  mov     rax, [rax+10h]
0x180011f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f75  mov     rsi, rax
0x180011f78  test    rax, rax
0x180011f7b  jz      loc_18001200E
0x180011f81  mov     [rsp+58h+var_28], 0
0x180011f89  xor     ebx, ebx
0x180011f8b  lea     r12d, [rbx+1]
0x180011f8f  mov     r8, 4D53424C4B425244h
0x180011f99  mov     [rsp+58h+var_28], ebx
0x180011f9d  mov     edx, [rsi+14h]
0x180011fa0  cmp     ebx, edx
0x180011fa2  jnb     short loc_180011FEF
0x180011fa4  mov     eax, ebx
0x180011fa6  lea     rcx, ds:3[rbx*4]
0x180011fae  add     rcx, rax
0x180011fb1  lea     rcx, [rsi+rcx*8]; void *
0x180011fb5  cmp     r8, [rcx]
0x180011fb8  jnz     short loc_180012003
0x180011fba  cmp     qword ptr [rcx+10h], 0
0x180011fbf  jnz     short loc_180011FEF
0x180011fc1  lea     eax, [rdx-1]
0x180011fc4  cmp     ebx, eax
0x180011fc6  jnb     short loc_180011FE6
0x180011fc8  sub     edx, ebx
0x180011fca  lea     r8, [rdx+rdx*4]
0x180011fce  shl     r8, 3; Size
0x180011fd2  lea     eax, [rbx+1]
0x180011fd5  lea     rax, [rax+rax*4]
0x180011fd9  add     rax, 3
0x180011fdd  lea     rdx, [rsi+rax*8]; Src
0x180011fe1  call    memmove_0
0x180011fe6  dec     dword ptr [rsi+14h]
0x180011fe9  mov     edx, [rsi+14h]
0x180011fec  mov     edi, r12d
0x180011fef  test    edi, edi
0x180011ff1  jz      short loc_180012008
0x180011ff3  mov     [rsi+8], r12d
0x180011ff7  mov     rcx, r14; this
0x180011ffa  call    ?CheckAndRestoreIntegrity@CStorage@@IEAAHXZ; CStorage::CheckAndRestoreIntegrity(void)
0x180011fff  mov     edi, eax
0x180012001  jmp     short loc_18001200E
0x180012003  add     ebx, r12d
0x180012006  jmp     short loc_180011F99
0x180012008  cmp     ebx, edx
0x18001200a  cmovnb  edi, r12d
0x18001200e  mov     rdx, [rsp+58h+arg_8]
0x180012013  test    rdx, rdx
0x180012016  jz      short loc_180012028
0x180012018  mov     rcx, [r14+40h]
0x18001201c  mov     rax, [rcx]
0x18001201f  mov     rax, [rax+18h]
0x180012023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012028  mov     rcx, [r14]; hMutex
0x18001202b  call    cs:__imp_ReleaseMutex
0x180012032  nop     dword ptr [rax+rax+00h]
0x180012037  mov     eax, edi
0x180012039  jmp     loc_180011F43
0x180028905  push    rbp
0x180028907  sub     rsp, 30h
0x18002890b  mov     rbp, rdx
0x18002890e  mov     rdx, [rbp+68h]
0x180028912  test    rdx, rdx
0x180028915  jz      short loc_18002892C
0x180028917  mov     rax, [rbp+60h]
0x18002891b  mov     rcx, [rax+40h]
0x18002891f  mov     r8, [rcx]
0x180028922  mov     rax, [r8+18h]
0x180028926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002892b  nop
0x18002892c  mov     rcx, [rbp+60h]
0x180028930  mov     rcx, [rcx]; hMutex
0x180028933  call    cs:__imp_ReleaseMutex
0x18002893a  nop     dword ptr [rax+rax+00h]
0x18002893f  nop
0x180028940  add     rsp, 30h
0x180028944  pop     rbp
0x180028945  retn
```
