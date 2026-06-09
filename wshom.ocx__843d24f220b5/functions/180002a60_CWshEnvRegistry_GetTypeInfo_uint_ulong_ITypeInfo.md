# CWshEnvRegistry::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x180002a60`
- end: `0x180002bf1`
- name: `?GetTypeInfo@CWshEnvRegistry@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `401`
- prototype: `int(CWshEnvRegistry *__hidden this, unsigned int, unsigned int, struct ITypeInfo **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180006dc0`

## callees

- `0x180002a60`
- `0x180011010`

## import_xrefs

- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180002af4`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180002af4`
- `KERNEL32!LeaveCriticalSection` at `0x180002abb`
- `KERNEL32!LeaveCriticalSection` at `0x180002bb9`
- `KERNEL32!LeaveCriticalSection` at `0x180002abb`
- `KERNEL32!LeaveCriticalSection` at `0x180002bb9`
- `KERNEL32!EnterCriticalSection` at `0x180002a91`
- `KERNEL32!EnterCriticalSection` at `0x180002a91`

## pseudocode

```c
__int64 __fastcall CWshEnvRegistry::GetTypeInfo(CWshEnvRegistry *this, int a2, LCID a3, struct ITypeInfo **a4)
{
  __int64 v7; // rbx
  __int64 v9; // rcx
  HRESULT v10; // ebp
  __int64 v11; // rdx
  __int64 v12; // rax
  ITypeLib *v13; // rcx
  void (*Release)(void); // rax
  __int64 *v15; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v16; // [rsp+68h] [rbp+10h] BYREF
  ITypeLib *pptlib; // [rsp+78h] [rbp+20h] BYREF

  *a4 = 0;
  if ( !a2 )
  {
    v7 = *((_QWORD *)this + 7);
    EnterCriticalSection(&CDispatch::s_oCS);
    if ( *(_QWORD *)(v7 + 56) )
    {
LABEL_3:
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v7 + 56) + 8LL))(*(_QWORD *)(v7 + 56));
      *a4 = *(struct ITypeInfo **)(v7 + 56);
      LeaveCriticalSection(&CDispatch::s_oCS);
      return 0;
    }
    v9 = *((_QWORD *)this + 7);
    pptlib = 0;
    v10 = LoadRegTypeLib(*(const GUID *const *)(v9 + 32), *(_WORD *)(v9 + 48), 0, a3, &pptlib);
    if ( v10 < 0 )
      goto LABEL_11;
    v11 = *((_QWORD *)this + 7);
    v15 = 0;
    v10 = ((__int64 (__fastcall *)(ITypeLib *, _QWORD, __int64 **))pptlib->lpVtbl->GetTypeInfoOfGuid)(
            pptlib,
            *(_QWORD *)(v11 + 40),
            &v15);
    if ( v10 >= 0 )
    {
      v16 = 0;
      v10 = (*(__int64 (__fastcall **)(__int64 *, __int64, unsigned int *))(*v15 + 64))(v15, 0xFFFFFFFFLL, &v16);
      v12 = *v15;
      if ( v10 < 0 )
      {
        (*(void (**)(void))(v12 + 16))();
        Release = (void (*)(void))pptlib->lpVtbl->Release;
        goto LABEL_10;
      }
      v10 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64))(v12 + 112))(v15, v16, *((_QWORD *)this + 7) + 56LL);
      (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
      if ( v10 >= 0 )
      {
        v13 = pptlib;
        *((_BYTE *)this + 64) = 1;
        ((void (__fastcall *)(ITypeLib *))v13->lpVtbl->Release)(v13);
        goto LABEL_3;
      }
    }
    Release = (void (*)(void))pptlib->lpVtbl->Release;
LABEL_10:
    Release();
LABEL_11:
    LeaveCriticalSection(&CDispatch::s_oCS);
    return (unsigned int)v10;
  }
  return 2147614731LL;
}

```

## disassembly

```asm
0x180002a60  push    rbp
0x180002a62  push    rsi
0x180002a63  push    rdi
0x180002a64  push    r14
0x180002a66  sub     rsp, 38h
0x180002a6a  xor     r14d, r14d
0x180002a6d  mov     rdi, r9
0x180002a70  mov     [r9], r14
0x180002a73  mov     ebp, r8d
0x180002a76  mov     rsi, rcx
0x180002a79  test    edx, edx
0x180002a7b  jnz     loc_180002BD0
0x180002a81  mov     [rsp+58h+var_28], rbx
0x180002a86  mov     rbx, [rcx+38h]
0x180002a8a  lea     rcx, ?s_oCS@CDispatch@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002a91  call    cs:__imp_EnterCriticalSection
0x180002a97  cmp     [rbx+38h], r14
0x180002a9b  jz      short loc_180002AD3
0x180002a9d  mov     rcx, [rbx+38h]
0x180002aa1  mov     rax, [rcx]
0x180002aa4  mov     rax, [rax+8]
0x180002aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aad  mov     rax, [rbx+38h]
0x180002ab1  lea     rcx, ?s_oCS@CDispatch@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002ab8  mov     [rdi], rax
0x180002abb  call    cs:__imp_LeaveCriticalSection
0x180002ac1  mov     rbx, [rsp+58h+var_28]
0x180002ac6  mov     eax, r14d
0x180002ac9  add     rsp, 38h
0x180002acd  pop     r14
0x180002acf  pop     rdi
0x180002ad0  pop     rsi
0x180002ad1  pop     rbp
0x180002ad2  retn
0x180002ad3  mov     rcx, [rsi+38h]
0x180002ad7  lea     rax, [rsp+58h+arg_18]
0x180002adc  mov     [rsp+58h+arg_18], r14
0x180002ae1  xor     r8d, r8d; wVerMinor
0x180002ae4  mov     r9d, ebp; lcid
0x180002ae7  mov     [rsp+58h+pptlib], rax; pptlib
0x180002aec  movzx   edx, word ptr [rcx+30h]; wVerMajor
0x180002af0  mov     rcx, [rcx+20h]; rguid
0x180002af4  call    cs:__imp_LoadRegTypeLib
0x180002afa  mov     ebp, eax
0x180002afc  test    eax, eax
0x180002afe  js      loc_180002BB2
0x180002b04  mov     rcx, [rsp+58h+arg_18]
0x180002b09  lea     r8, [rsp+58h+arg_0]
0x180002b0e  mov     rdx, [rsi+38h]
0x180002b12  mov     [rsp+58h+arg_0], r14
0x180002b17  mov     rax, [rcx]
0x180002b1a  mov     rdx, [rdx+28h]
0x180002b1e  mov     rax, [rax+30h]
0x180002b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b27  mov     ebp, eax
0x180002b29  test    eax, eax
0x180002b2b  js      short loc_180002BA1
0x180002b2d  mov     rcx, [rsp+58h+arg_0]
0x180002b32  lea     r8, [rsp+58h+arg_8]
0x180002b37  mov     [rsp+58h+arg_8], r14d
0x180002b3c  mov     edx, 0FFFFFFFFh
0x180002b41  mov     rax, [rcx]
0x180002b44  mov     rax, [rax+40h]
0x180002b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b4d  mov     rcx, [rsp+58h+arg_0]
0x180002b52  mov     ebp, eax
0x180002b54  test    eax, eax
0x180002b56  mov     rax, [rcx]
0x180002b59  js      short loc_180002BDA
0x180002b5b  mov     r8, [rsi+38h]
0x180002b5f  mov     edx, [rsp+58h+arg_8]
0x180002b63  add     r8, 38h ; '8'
0x180002b67  mov     rax, [rax+70h]
0x180002b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b70  mov     rcx, [rsp+58h+arg_0]
0x180002b75  mov     ebp, eax
0x180002b77  mov     rax, [rcx]
0x180002b7a  mov     rax, [rax+10h]
0x180002b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b83  test    ebp, ebp
0x180002b85  js      short loc_180002BA1
0x180002b87  mov     rcx, [rsp+58h+arg_18]
0x180002b8c  mov     byte ptr [rsi+40h], 1
0x180002b90  mov     rax, [rcx]
0x180002b93  mov     rax, [rax+10h]
0x180002b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b9c  jmp     loc_180002A9D
0x180002ba1  mov     rcx, [rsp+58h+arg_18]
0x180002ba6  mov     rdx, [rcx]
0x180002ba9  mov     rax, [rdx+10h]
0x180002bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bb2  lea     rcx, ?s_oCS@CDispatch@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002bb9  call    cs:__imp_LeaveCriticalSection
0x180002bbf  mov     rbx, [rsp+58h+var_28]
0x180002bc4  mov     eax, ebp
0x180002bc6  add     rsp, 38h
0x180002bca  pop     r14
0x180002bcc  pop     rdi
0x180002bcd  pop     rsi
0x180002bce  pop     rbp
0x180002bcf  retn
0x180002bd0  mov     eax, 8002000Bh
0x180002bd5  jmp     loc_180002AC9
0x180002bda  mov     rax, [rax+10h]
0x180002bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002be3  mov     rcx, [rsp+58h+arg_18]
0x180002be8  mov     rax, [rcx]
0x180002beb  mov     rax, [rax+10h]
0x180002bef  jmp     short loc_180002BAD
```
