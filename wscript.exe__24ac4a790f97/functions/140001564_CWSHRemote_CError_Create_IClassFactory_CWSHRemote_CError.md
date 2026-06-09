# CWSHRemote::CError::Create(IClassFactory *,CWSHRemote::CError * *)

- ea: `0x140001564`
- end: `0x140001695`
- name: `?Create@CError@CWSHRemote@@SAJPEAUIClassFactory@@PEAPEAV12@@Z`
- size: `305`
- prototype: `__int64 __fastcall(struct IClassFactory *, struct CWSHRemote::CError **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140002064`

## callees

- `0x140001008`
- `0x140001488`
- `0x140001564`
- `0x140018010`

## import_xrefs

- `OLEAUT32!__imp_LoadRegTypeLib` at `0x140001621`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x140001621`
- `KERNEL32!GetCurrentThreadId` at `0x1400015c6`
- `KERNEL32!GetCurrentThreadId` at `0x1400015c6`

## pseudocode

```c
__int64 __fastcall CWSHRemote::CError::Create(struct IClassFactory *a1, struct CWSHRemote::CError **a2)
{
  _DWORD *v4; // rbx
  HRESULT v5; // edi
  ITypeLib *pptlib; // [rsp+68h] [rbp+10h] BYREF

  pptlib = 0;
  *a2 = 0;
  v4 = operator new(0x78u);
  if ( !v4 )
  {
    v4 = 0;
LABEL_8:
    v5 = -2147024882;
    goto LABEL_9;
  }
  v4[2] = 1;
  *(_QWORD *)v4 = &CWSHRemote::CError::`vftable';
  *((_QWORD *)v4 + 2) = 0;
  v4[6] = 0;
  *((_QWORD *)v4 + 4) = 0;
  *((_QWORD *)v4 + 5) = 0;
  *((_QWORD *)v4 + 6) = 0;
  *((_QWORD *)v4 + 7) = 0;
  *((_QWORD *)v4 + 8) = 0;
  CCriticalSection::CCriticalSection((CCriticalSection *)(v4 + 18));
  v4[3] = GetCurrentThreadId();
  if ( !*((_BYTE *)v4 + 113) || *((_BYTE *)v4 + 112) )
    goto LABEL_8;
  *((_QWORD *)v4 + 8) = a1;
  ((void (__fastcall *)(struct IClassFactory *))a1->lpVtbl->AddRef)(a1);
  ((void (__fastcall *)(struct IClassFactory *, __int64))a1->lpVtbl->LockServer)(a1, 1);
  v5 = LoadRegTypeLib(&LIBID_WSHRemoteLibrary, 1u, 0, 0x409u, &pptlib);
  if ( v5 >= 0 )
  {
    v5 = ((__int64 (__fastcall *)(ITypeLib *, GUID *, _DWORD *))pptlib->lpVtbl->GetTypeInfoOfGuid)(
           pptlib,
           &IID_IWSHRemoteError,
           v4 + 14);
    if ( v5 >= 0 )
    {
      *a2 = (struct CWSHRemote::CError *)v4;
      v5 = 0;
      v4 = 0;
    }
  }
LABEL_9:
  if ( pptlib )
    ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
  if ( v4 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v4 + 16LL))(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140001564  push    rbx
0x140001566  push    rbp
0x140001567  push    rsi
0x140001568  push    rdi
0x140001569  sub     rsp, 38h
0x14000156d  xor     ebp, ebp
0x14000156f  mov     rdi, rcx
0x140001572  mov     rsi, rdx
0x140001575  mov     [rsp+58h+arg_8], rbp
0x14000157a  mov     [rdx], rbp
0x14000157d  lea     ecx, [rbp+78h]; Size
0x140001580  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140001585  mov     rbx, rax
0x140001588  test    rax, rax
0x14000158b  jz      loc_140001658
0x140001591  lea     rax, ??_7CError@CWSHRemote@@6B@; const CWSHRemote::CError::`vftable'
0x140001598  mov     dword ptr [rbx+8], 1
0x14000159f  lea     rcx, [rbx+48h]; this
0x1400015a3  mov     [rbx], rax
0x1400015a6  mov     [rbx+10h], rbp
0x1400015aa  mov     [rbx+18h], ebp
0x1400015ad  mov     [rbx+20h], rbp
0x1400015b1  mov     [rbx+28h], rbp
0x1400015b5  mov     [rbx+30h], rbp
0x1400015b9  mov     [rbx+38h], rbp
0x1400015bd  mov     [rbx+40h], rbp
0x1400015c1  call    ??0CCriticalSection@@QEAA@XZ; CCriticalSection::CCriticalSection(void)
0x1400015c6  call    cs:__imp_GetCurrentThreadId
0x1400015cc  mov     [rbx+0Ch], eax
0x1400015cf  cmp     [rbx+71h], bpl
0x1400015d3  jz      loc_14000165B
0x1400015d9  cmp     [rbx+70h], bpl
0x1400015dd  jnz     short loc_14000165B
0x1400015df  mov     [rbx+40h], rdi
0x1400015e3  mov     rcx, rdi
0x1400015e6  mov     rax, [rdi]
0x1400015e9  mov     rax, [rax+8]
0x1400015ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400015f2  mov     rax, [rdi]
0x1400015f5  lea     edx, [rbp+1]
0x1400015f8  mov     rcx, rdi
0x1400015fb  mov     rax, [rax+20h]
0x1400015ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001604  lea     rax, [rsp+58h+arg_8]
0x140001609  xor     r8d, r8d; wVerMinor
0x14000160c  lea     edx, [rbp+1]; wVerMajor
0x14000160f  mov     [rsp+58h+pptlib], rax; pptlib
0x140001614  mov     r9d, 409h; lcid
0x14000161a  lea     rcx, LIBID_WSHRemoteLibrary; rguid
0x140001621  call    cs:__imp_LoadRegTypeLib
0x140001627  mov     edi, eax
0x140001629  test    eax, eax
0x14000162b  js      short loc_140001660
0x14000162d  mov     rcx, [rsp+58h+arg_8]
0x140001632  lea     r8, [rbx+38h]
0x140001636  lea     rdx, IID_IWSHRemoteError
0x14000163d  mov     rax, [rcx]
0x140001640  mov     rax, [rax+30h]
0x140001644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001649  mov     edi, eax
0x14000164b  test    eax, eax
0x14000164d  js      short loc_140001660
0x14000164f  mov     [rsi], rbx
0x140001652  mov     edi, ebp
0x140001654  mov     ebx, ebp
0x140001656  jmp     short loc_140001660
0x140001658  mov     rbx, rbp
0x14000165b  mov     edi, 8007000Eh
0x140001660  mov     rcx, [rsp+58h+arg_8]
0x140001665  test    rcx, rcx
0x140001668  jz      short loc_140001676
0x14000166a  mov     rax, [rcx]
0x14000166d  mov     rax, [rax+10h]
0x140001671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001676  test    rbx, rbx
0x140001679  jz      short loc_14000168A
0x14000167b  mov     rax, [rbx]
0x14000167e  mov     rcx, rbx
0x140001681  mov     rax, [rax+10h]
0x140001685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000168a  mov     eax, edi
0x14000168c  add     rsp, 38h
0x140001690  pop     rdi
0x140001691  pop     rsi
0x140001692  pop     rbp
0x140001693  pop     rbx
0x140001694  retn
```
