# DataObj_GetCharArray(IDataObject *,ushort,ushort * *,unsigned __int64 *)

- ea: `0x1800249a8`
- end: `0x180024b53`
- name: `?DataObj_GetCharArray@@YAJPEAUIDataObject@@GPEAPEAGPEA_K@Z`
- size: `427`
- prototype: `__int64 __fastcall(struct IDataObject *, __int16, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e874`
- `0x18000f340`

## callees

- `0x18000581b`
- `0x18001f3a4`
- `0x1800249a8`
- `0x180048934`
- `0x180048954`
- `0x18007e4b0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024ad6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024afa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024ad6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024afa`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180024b04`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180024b2f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180024b04`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180024b2f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x180024a68`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x180024a68`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180024a2b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180024a2b`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x180024b3a`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x180024b3a`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall DataObj_GetCharArray(
        struct IDataObject *a1,
        __int16 a2,
        unsigned __int16 **a3,
        unsigned __int64 *a4)
{
  int LastError; // ebx
  HBITMAP hBitmap; // rbx
  const char *v8; // r9
  const void *v9; // r14
  void *v10; // rdi
  SIZE_T v11; // r15
  unsigned __int64 v12; // rsi
  unsigned int v13; // edx
  void *v14; // rcx
  int v15; // eax
  unsigned __int16 *v16; // rbx
  STGMEDIUM hMem; // [rsp+30h] [rbp-48h] BYREF
  __int16 v19; // [rsp+48h] [rbp-30h] BYREF
  int v20; // [rsp+4Ah] [rbp-2Eh]
  __int16 v21; // [rsp+4Eh] [rbp-2Ah]
  __int64 v22; // [rsp+50h] [rbp-28h]
  int v23; // [rsp+58h] [rbp-20h]
  int v24; // [rsp+5Ch] [rbp-1Ch]
  __int64 v25; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  LPVOID pv; // [rsp+C0h] [rbp+48h] BYREF

  *a3 = 0;
  *a4 = 0;
  memset(&hMem, 0, sizeof(hMem));
  v19 = a2;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 1;
  v24 = -1;
  v25 = 1;
  LastError = ((__int64 (__fastcall *)(struct IDataObject *, __int16 *, STGMEDIUM *))a1->lpVtbl->GetData)(
                a1,
                &v19,
                &hMem);
  if ( LastError >= 0 )
  {
    hBitmap = hMem.hBitmap;
    if ( hMem.hBitmap )
    {
      v9 = GlobalLock(hMem.hBitmap);
      v10 = (void *)((unsigned __int64)hBitmap & -(__int64)(v9 != 0));
      if ( v10 )
      {
        v11 = GlobalSize(hMem.hBitmap);
        v12 = v11 >> 1;
        if ( v11 >> 1 >= 2 && !wcsncmp_0((const wchar_t *)v9 + v12 - 2, &String2, 2u) )
        {
          pv = 0;
          v15 = CTCoAllocPolicy::Alloc(v14, v13, v11, &pv);
          LastError = v15;
          if ( v15 >= 0 )
          {
            v16 = (unsigned __int16 *)pv;
            memcpy_0(pv, v9, v11);
            *a3 = v16;
            *a4 = v12;
            CoTaskMemFree(0);
            GlobalUnlock(v10);
            LastError = 0;
            goto LABEL_13;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1E3,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\dobjutil_storage.h",
            (const char *)(unsigned int)v15,
            (int)v10);
          CoTaskMemFree(pv);
        }
        else
        {
          LastError = -2147024809;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1E0,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\dobjutil_storage.h",
            (const char *)0x80070057LL,
            (int)v10);
        }
        GlobalUnlock(v10);
        goto LABEL_13;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1DB,
                    (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\dobjutil_storage.h",
                    v8);
    }
    else
    {
      LastError = -2147221404;
    }
  }
LABEL_13:
  ReleaseStgMedium(&hMem);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800249a8  push    rbp
0x1800249aa  push    rbx
0x1800249ab  push    rsi
0x1800249ac  push    rdi
0x1800249ad  push    r12
0x1800249af  push    r13
0x1800249b1  push    r14
0x1800249b3  push    r15
0x1800249b5  mov     rbp, rsp
0x1800249b8  sub     rsp, 78h
0x1800249bc  mov     r12, r9
0x1800249bf  mov     r13, r8
0x1800249c2  xor     edi, edi
0x1800249c4  mov     [r8], rdi
0x1800249c7  mov     [r9], rdi
0x1800249ca  xorps   xmm0, xmm0
0x1800249cd  xor     eax, eax
0x1800249cf  movups  xmmword ptr [rbp+hMem], xmm0
0x1800249d3  mov     [rbp+var_38], rax
0x1800249d7  mov     [rbp+var_30], dx
0x1800249db  mov     [rbp+var_2E], eax
0x1800249de  mov     [rbp+var_2A], ax
0x1800249e2  mov     [rbp+var_28], rdi
0x1800249e6  lea     eax, [rdi+1]
0x1800249e9  mov     [rbp+var_20], eax
0x1800249ec  mov     [rbp+var_1C], 0FFFFFFFFh
0x1800249f3  mov     [rbp+var_18], rax
0x1800249f7  mov     rax, [rcx]
0x1800249fa  lea     r8, [rbp+hMem]
0x1800249fe  lea     rdx, [rbp+var_30]
0x180024a02  mov     rax, [rax+18h]
0x180024a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a0b  mov     ebx, eax
0x180024a0d  test    eax, eax
0x180024a0f  js      loc_180024B36
0x180024a15  mov     rbx, [rbp+hMem+8]
0x180024a19  test    rbx, rbx
0x180024a1c  jnz     short loc_180024A28
0x180024a1e  mov     ebx, 80040064h
0x180024a23  jmp     loc_180024B36
0x180024a28  mov     rcx, rbx; hMem
0x180024a2b  call    cs:__imp_GlobalLock
0x180024a31  mov     r14, rax
0x180024a34  mov     [rbp+var_50], rax
0x180024a38  neg     rax
0x180024a3b  sbb     rdi, rdi
0x180024a3e  and     rdi, rbx
0x180024a41  mov     [rbp+var_58], rdi
0x180024a45  jnz     short loc_180024A64
0x180024a47  mov     rcx, [rbp+40h]; this
0x180024a4b  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180024a52  mov     edx, 1DBh; void *
0x180024a57  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180024a5c  nop
0x180024a5d  mov     ebx, eax
0x180024a5f  jmp     loc_180024B36
0x180024a64  mov     rcx, [rbp+hMem+8]; hMem
0x180024a68  call    cs:__imp_GlobalSize
0x180024a6e  mov     r15, rax
0x180024a71  mov     rsi, rax
0x180024a74  shr     rsi, 1
0x180024a77  cmp     rsi, 2
0x180024a7b  jb      loc_180024B0E
0x180024a81  lea     rcx, [rsi-2]
0x180024a85  lea     rcx, [r14+rcx*2]; String1
0x180024a89  mov     r8d, 2; MaxCount
0x180024a8f  lea     rdx, String2; String2
0x180024a96  call    wcsncmp_0
0x180024a9b  test    eax, eax
0x180024a9d  jnz     short loc_180024B0E
0x180024a9f  mov     [rbp+pv], 0
0x180024aa7  lea     r9, [rbp+pv]; void **
0x180024aab  mov     r8, r15; unsigned __int64
0x180024aae  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180024ab3  mov     ebx, eax
0x180024ab5  test    eax, eax
0x180024ab7  jns     short loc_180024ADE
0x180024ab9  mov     rcx, [rbp+40h]; this
0x180024abd  mov     r9d, eax; char *
0x180024ac0  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180024ac7  mov     edx, 1E3h; void *
0x180024acc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024ad1  nop
0x180024ad2  mov     rcx, [rbp+pv]; pv
0x180024ad6  call    cs:__imp_CoTaskMemFree
0x180024adc  jmp     short loc_180024B2C
0x180024ade  mov     r8, r15; Size
0x180024ae1  mov     rdx, r14; Src
0x180024ae4  mov     rbx, [rbp+pv]
0x180024ae8  mov     rcx, rbx; void *
0x180024aeb  call    memcpy_0
0x180024af0  mov     [r13+0], rbx
0x180024af4  mov     [r12], rsi
0x180024af8  xor     ecx, ecx; pv
0x180024afa  call    cs:__imp_CoTaskMemFree
0x180024b00  nop
0x180024b01  mov     rcx, rdi; hMem
0x180024b04  call    cs:__imp_GlobalUnlock
0x180024b0a  xor     ebx, ebx
0x180024b0c  jmp     short loc_180024B36
0x180024b0e  mov     rcx, [rbp+40h]; this
0x180024b12  mov     ebx, 80070057h
0x180024b17  mov     r9d, ebx; char *
0x180024b1a  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180024b21  mov     edx, 1E0h; void *
0x180024b26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024b2b  nop
0x180024b2c  mov     rcx, rdi; hMem
0x180024b2f  call    cs:__imp_GlobalUnlock
0x180024b35  nop
0x180024b36  lea     rcx, [rbp+hMem]; LPSTGMEDIUM
0x180024b3a  call    cs:__imp_ReleaseStgMedium
0x180024b40  mov     eax, ebx
0x180024b42  add     rsp, 78h
0x180024b46  pop     r15
0x180024b48  pop     r14
0x180024b4a  pop     r13
0x180024b4c  pop     r12
0x180024b4e  pop     rdi
0x180024b4f  pop     rsi
0x180024b50  pop     rbx
0x180024b51  pop     rbp
0x180024b52  retn
```
