# MlangCharacterSource::XmlDecl(uint *)

- ea: `0x10041bc90`
- end: `0x10041be8f`
- name: `?XmlDecl@MlangCharacterSource@@UEAAPEBEPEAI@Z`
- size: `511`
- prototype: `const unsigned __int8 *__fastcall(MlangCharacterSource *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x100401780`
- `0x10041bc90`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x10041bd37`
- `KERNEL32!HeapAlloc` at `0x10041bd37`
- `KERNEL32!HeapFree` at `0x10041bcdf`
- `KERNEL32!HeapFree` at `0x10041be56`
- `KERNEL32!HeapFree` at `0x10041bcdf`
- `KERNEL32!HeapFree` at `0x10041be56`
- `ole32!CoCreateInstance` at `0x10041bd90`
- `ole32!CoCreateInstance` at `0x10041bd90`

## string_xrefs

- `0x10041bdf8`: `<?xml version="1.0"?>`

## pseudocode

```c
const unsigned __int8 *__fastcall MlangCharacterSource::XmlDecl(MlangCharacterSource *this, unsigned int *a2)
{
  void *v2; // r8
  struct IMalloc *v5; // rcx
  struct IMalloc *v6; // rcx
  LPVOID v7; // rax
  LPVOID v8; // rdi
  struct IMultiLanguage2 *v9; // rcx
  unsigned int v10; // ebp
  HRESULT v11; // eax
  bool v12; // zf
  void *v13; // r8
  struct IMalloc *v14; // rcx
  unsigned int v16; // [rsp+70h] [rbp+8h] BYREF
  int v17; // [rsp+80h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp+20h] BYREF

  v2 = (void *)*((_QWORD *)this + 32);
  if ( v2 )
  {
    v5 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v5 || (v5 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, void *))v5->lpVtbl->Free)(v5, v2);
    else
      HeapFree(g_hHeap, 0, v2);
    *((_QWORD *)this + 32) = 0;
  }
  v6 = (struct IMalloc *)*((_QWORD *)this + 1);
  v17 = 21;
  v16 = 168;
  if ( v6 || (v6 = g_pMalloc) != 0 )
    v7 = (LPVOID)((__int64 (__fastcall *)(struct IMalloc *, __int64))v6->lpVtbl->Alloc)(v6, 168);
  else
    v7 = HeapAlloc(g_hHeap, 0, 0xA8u);
  v8 = v7;
  if ( !v7 )
  {
    MXRRaiseException(-2147024882);
    JUMPOUT(0x10041BE8ELL);
  }
  *((_QWORD *)this + 32) = v7;
  v9 = s_pMultiLanguage2;
  v10 = *((_DWORD *)this + 62);
  if ( !s_pMultiLanguage2 )
  {
    ppv = 0;
    v11 = CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &IID_IMultiLanguage2, &ppv);
    v12 = v11 == 0;
    if ( v11 >= 0 )
    {
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&s_pMultiLanguage2, (signed __int64)ppv, 0) )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      v12 = 1;
    }
    if ( !v12 )
      goto LABEL_20;
    v9 = s_pMultiLanguage2;
  }
  if ( !((unsigned int (__fastcall *)(struct IMultiLanguage2 *, char *, _QWORD, const WCHAR *, int *, LPVOID, unsigned int *))v9->lpVtbl->ConvertStringFromUnicode)(
          v9,
          (char *)this + 268,
          v10,
          L"<?xml version=\"1.0\"?>",
          &v17,
          v8,
          &v16) )
  {
    *a2 = v16;
    return (const unsigned __int8 *)*((_QWORD *)this + 32);
  }
LABEL_20:
  v13 = (void *)*((_QWORD *)this + 32);
  v14 = (struct IMalloc *)*((_QWORD *)this + 1);
  if ( !v13 )
  {
LABEL_25:
    *((_QWORD *)this + 32) = 0;
    *a2 = 0;
    return (const unsigned __int8 *)*((_QWORD *)this + 32);
  }
  if ( !v14 )
  {
    v14 = g_pMalloc;
    if ( !g_pMalloc )
    {
      HeapFree(g_hHeap, 0, v13);
      goto LABEL_25;
    }
  }
  ((void (__fastcall *)(struct IMalloc *, _QWORD))v14->lpVtbl->Free)(v14, *((_QWORD *)this + 32));
  *((_QWORD *)this + 32) = 0;
  *a2 = 0;
  return (const unsigned __int8 *)*((_QWORD *)this + 32);
}

```

## disassembly

```asm
0x10041bc90  push    rbx
0x10041bc92  push    rsi
0x10041bc93  push    rdi
0x10041bc94  push    r14
0x10041bc96  sub     rsp, 48h
0x10041bc9a  mov     r8, [rcx+100h]; lpMem
0x10041bca1  xor     r14d, r14d
0x10041bca4  mov     rsi, rdx
0x10041bca7  mov     rbx, rcx
0x10041bcaa  test    r8, r8
0x10041bcad  jz      short loc_10041BCEC
0x10041bcaf  mov     rcx, [rcx+8]
0x10041bcb3  test    rcx, rcx
0x10041bcb6  jnz     short loc_10041BCC4
0x10041bcb8  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10041bcbf  test    rcx, rcx
0x10041bcc2  jz      short loc_10041BCD6
0x10041bcc4  mov     rax, [rcx]
0x10041bcc7  mov     rdx, r8
0x10041bcca  mov     rax, [rax+28h]
0x10041bcce  call    cs:__guard_dispatch_icall_fptr
0x10041bcd4  jmp     short loc_10041BCE5
0x10041bcd6  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10041bcdd  xor     edx, edx; dwFlags
0x10041bcdf  call    cs:__imp_HeapFree
0x10041bce5  mov     [rbx+100h], r14
0x10041bcec  mov     rcx, [rbx+8]
0x10041bcf0  mov     [rsp+68h+arg_10], 15h
0x10041bcfb  mov     [rsp+68h+arg_0], 0A8h
0x10041bd03  test    rcx, rcx
0x10041bd06  jz      short loc_10041BD1C
0x10041bd08  mov     rax, [rcx]
0x10041bd0b  mov     edx, 0A8h
0x10041bd10  mov     rax, [rax+18h]
0x10041bd14  call    cs:__guard_dispatch_icall_fptr
0x10041bd1a  jmp     short loc_10041BD3D
0x10041bd1c  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10041bd23  test    rcx, rcx
0x10041bd26  jnz     short loc_10041BD08
0x10041bd28  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10041bd2f  xor     edx, edx; dwFlags
0x10041bd31  mov     r8d, 0A8h; dwBytes
0x10041bd37  call    cs:__imp_HeapAlloc
0x10041bd3d  mov     rdi, rax
0x10041bd40  test    rax, rax
0x10041bd43  jz      loc_10041BE84
0x10041bd49  mov     [rbx+100h], rax
0x10041bd50  mov     rcx, cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA; IMultiLanguage2 * s_pMultiLanguage2
0x10041bd57  mov     [rsp+68h+var_28], rbp
0x10041bd5c  mov     ebp, [rbx+0F8h]
0x10041bd62  test    rcx, rcx
0x10041bd65  jnz     short loc_10041BDD2
0x10041bd67  lea     rax, [rsp+68h+arg_18]
0x10041bd6f  mov     [rsp+68h+arg_18], r14
0x10041bd77  lea     r8d, [rcx+1]; dwClsContext
0x10041bd7b  mov     [rsp+68h+ppv], rax; ppv
0x10041bd80  lea     rcx, CLSID_CMultiLanguage; rclsid
0x10041bd87  xor     edx, edx; pUnkOuter
0x10041bd89  lea     r9, IID_IMultiLanguage2; riid
0x10041bd90  call    cs:__imp_CoCreateInstance
0x10041bd96  test    eax, eax
0x10041bd98  js      short loc_10041BDC9
0x10041bd9a  mov     rcx, [rsp+68h+arg_18]
0x10041bda2  xor     eax, eax
0x10041bda4  lock cmpxchg cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA, rcx; IMultiLanguage2 * s_pMultiLanguage2
0x10041bdad  jz      short loc_10041BDC4
0x10041bdaf  mov     rcx, [rsp+68h+arg_18]
0x10041bdb7  mov     rax, [rcx]
0x10041bdba  mov     rax, [rax+10h]
0x10041bdbe  call    cs:__guard_dispatch_icall_fptr
0x10041bdc4  mov     eax, r14d
0x10041bdc7  test    eax, eax
0x10041bdc9  jnz     short loc_10041BE10
0x10041bdcb  mov     rcx, cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA; IMultiLanguage2 * s_pMultiLanguage2
0x10041bdd2  mov     rax, [rcx]
0x10041bdd5  lea     r8, [rsp+68h+arg_0]
0x10041bdda  mov     [rsp+68h+var_38], r8
0x10041bddf  lea     rdx, [rbx+10Ch]
0x10041bde6  lea     r8, [rsp+68h+arg_10]
0x10041bdee  mov     [rsp+68h+var_40], rdi
0x10041bdf3  mov     [rsp+68h+ppv], r8
0x10041bdf8  lea     r9, WideCharStr; "<?xml version=\"1.0\"?>"
0x10041bdff  mov     rax, [rax+58h]
0x10041be03  mov     r8d, ebp
0x10041be06  call    cs:__guard_dispatch_icall_fptr
0x10041be0c  test    eax, eax
0x10041be0e  jz      short loc_10041BE68
0x10041be10  mov     r8, [rbx+100h]; lpMem
0x10041be17  mov     rcx, [rbx+8]
0x10041be1b  test    r8, r8
0x10041be1e  jz      short loc_10041BE5C
0x10041be20  test    rcx, rcx
0x10041be23  jnz     short loc_10041BE31
0x10041be25  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10041be2c  test    rcx, rcx
0x10041be2f  jz      short loc_10041BE4D
0x10041be31  mov     rax, [rcx]
0x10041be34  mov     rdx, r8
0x10041be37  mov     rax, [rax+28h]
0x10041be3b  call    cs:__guard_dispatch_icall_fptr
0x10041be41  mov     [rbx+100h], r14
0x10041be48  mov     [rsi], r14d
0x10041be4b  jmp     short loc_10041BE6E
0x10041be4d  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10041be54  xor     edx, edx; dwFlags
0x10041be56  call    cs:__imp_HeapFree
0x10041be5c  mov     [rbx+100h], r14
0x10041be63  mov     [rsi], r14d
0x10041be66  jmp     short loc_10041BE6E
0x10041be68  mov     eax, [rsp+68h+arg_0]
0x10041be6c  mov     [rsi], eax
0x10041be6e  mov     rax, [rbx+100h]
0x10041be75  mov     rbp, [rsp+68h+var_28]
0x10041be7a  add     rsp, 48h
0x10041be7e  pop     r14
0x10041be80  pop     rdi
0x10041be81  pop     rsi
0x10041be82  pop     rbx
0x10041be83  retn
0x10041be84  mov     ecx, 8007000Eh; int
0x10041be89  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
