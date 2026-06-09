# CGpWmpEncoder::Initialize(IStream *,WICBitmapEncoderCacheOption)

- ea: `0x18003a540`
- end: `0x18003a649`
- name: `?Initialize@CGpWmpEncoder@@UEAAJPEAUIStream@@W4WICBitmapEncoderCacheOption@@@Z`
- size: `265`
- prototype: `__int64 __fastcall(CGpWmpEncoder *__hidden this, struct IStream *, enum WICBitmapEncoderCacheOption)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002db34`
- `0x18003a540`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a563`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a563`

## pseudocode

```c
__int64 __fastcall CGpWmpEncoder::Initialize(CGpWmpEncoder *this, struct IStream *a2, __int64 a3)
{
  char *v3; // rax
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  int v7; // edi
  __int64 v8; // rcx
  int v10; // [rsp+30h] [rbp-10h] BYREF
  char *v11; // [rsp+38h] [rbp-8h] BYREF
  __int16 v12; // [rsp+60h] [rbp+20h] BYREF
  __int16 v13; // [rsp+68h] [rbp+28h] BYREF
  int v14; // [rsp+78h] [rbp+38h] BYREF

  v3 = (char *)this - 56;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 48);
  v11 = v3;
  if ( LOBYTE(v5[1].DebugInfo) )
    EnterCriticalSection(v5);
  if ( a2 )
  {
    if ( *((_DWORD *)this - 16) == 1 )
    {
      *((_QWORD *)this + 2) = a2;
      ((void (__fastcall *)(struct IStream *, struct IStream *, __int64))a2->lpVtbl->AddRef)(a2, a2, a3);
      v8 = *((_QWORD *)this + 2);
      v10 = 0;
      v12 = 18761;
      v14 = 0;
      v13 = 444;
      v7 = (*(__int64 (__fastcall **)(__int64, __int16 *, __int64, int *))(*(_QWORD *)v8 + 32LL))(v8, &v12, 2, &v14);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(_QWORD, __int16 *, __int64, int *))(**((_QWORD **)this + 2) + 32LL))(
               *((_QWORD *)this + 2),
               &v13,
               2,
               &v14);
        if ( v7 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(_QWORD, int *, __int64, int *))(**((_QWORD **)this + 2) + 32LL))(
                 *((_QWORD *)this + 2),
                 &v10,
                 4,
                 &v14);
          if ( v7 >= 0 )
          {
            *((_DWORD *)this + 12) = 4;
            *((_DWORD *)this - 16) = 2;
          }
        }
      }
    }
    else
    {
      v7 = -2003292412;
    }
  }
  else
  {
    v7 = -2147024809;
  }
  CGuard<CMTALock>::~CGuard<CMTALock>(&v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003a540  push    rbp
0x18003a542  push    rbx
0x18003a543  push    rdi
0x18003a544  mov     rbp, rsp
0x18003a547  sub     rsp, 40h
0x18003a54b  lea     rax, [rcx-38h]
0x18003a54f  mov     rbx, rcx
0x18003a552  lea     rcx, [rax+8]; lpCriticalSection
0x18003a556  mov     [rbp+var_8], rax
0x18003a55a  cmp     byte ptr [rcx+28h], 0
0x18003a55e  mov     rdi, rdx
0x18003a561  jz      short loc_18003A569
0x18003a563  call    cs:__imp_EnterCriticalSection
0x18003a569  test    rdi, rdi
0x18003a56c  jnz     short loc_18003A578
0x18003a56e  mov     edi, 80070057h
0x18003a573  jmp     loc_18003A636
0x18003a578  cmp     dword ptr [rbx-40h], 1
0x18003a57c  jnz     loc_18003A631
0x18003a582  mov     [rbx+10h], rdi
0x18003a586  mov     rcx, rdi
0x18003a589  mov     rax, [rdi]
0x18003a58c  mov     rax, [rax+8]
0x18003a590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a595  mov     rcx, [rbx+10h]
0x18003a599  lea     r9, [rbp+arg_18]
0x18003a59d  mov     eax, 4949h
0x18003a5a2  mov     [rbp+var_10], 0
0x18003a5a9  mov     [rbp+arg_0], ax
0x18003a5ad  lea     rdx, [rbp+arg_0]
0x18003a5b1  mov     eax, 1BCh
0x18003a5b6  mov     [rbp+arg_18], 0
0x18003a5bd  mov     [rbp+arg_8], ax
0x18003a5c1  mov     r8d, 2
0x18003a5c7  mov     rax, [rcx]
0x18003a5ca  mov     rax, [rax+20h]
0x18003a5ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a5d3  mov     edi, eax
0x18003a5d5  test    eax, eax
0x18003a5d7  js      short loc_18003A636
0x18003a5d9  mov     rcx, [rbx+10h]
0x18003a5dd  lea     r9, [rbp+arg_18]
0x18003a5e1  mov     r8d, 2
0x18003a5e7  lea     rdx, [rbp+arg_8]
0x18003a5eb  mov     rax, [rcx]
0x18003a5ee  mov     rax, [rax+20h]
0x18003a5f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a5f7  mov     edi, eax
0x18003a5f9  test    eax, eax
0x18003a5fb  js      short loc_18003A636
0x18003a5fd  mov     rcx, [rbx+10h]
0x18003a601  lea     r9, [rbp+arg_18]
0x18003a605  mov     r8d, 4
0x18003a60b  lea     rdx, [rbp+var_10]
0x18003a60f  mov     rax, [rcx]
0x18003a612  mov     rax, [rax+20h]
0x18003a616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a61b  mov     edi, eax
0x18003a61d  test    eax, eax
0x18003a61f  js      short loc_18003A636
0x18003a621  mov     dword ptr [rbx+30h], 4
0x18003a628  mov     dword ptr [rbx-40h], 2
0x18003a62f  jmp     short loc_18003A636
0x18003a631  mov     edi, 88982F04h
0x18003a636  lea     rcx, [rbp+var_8]
0x18003a63a  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18003a63f  mov     eax, edi
0x18003a641  add     rsp, 40h
0x18003a645  pop     rdi
0x18003a646  pop     rbx
0x18003a647  pop     rbp
0x18003a648  retn
```
