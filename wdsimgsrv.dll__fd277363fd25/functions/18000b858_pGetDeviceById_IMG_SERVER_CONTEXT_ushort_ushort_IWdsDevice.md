# pGetDeviceById(_IMG_SERVER_CONTEXT *,ushort *,ushort *,IWdsDevice * *)

- ea: `0x18000b858`
- end: `0x18000b9b3`
- name: `?pGetDeviceById@@YAJPEAU_IMG_SERVER_CONTEXT@@PEAG1PEAPEAUIWdsDevice@@@Z`
- size: `347`
- prototype: `__int64 __fastcall(struct _IMG_SERVER_CONTEXT *, unsigned __int16 *, unsigned __int16 *, struct IWdsDevice **)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002e64`
- `0x180006548`
- `0x18000b668`

## callees

- `0x1800080d0`
- `0x18000b034`
- `0x18000b2f0`
- `0x18000b858`
- `0x18000cbd4`
- `0x18000ccf8`
- `0x180017010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000b96f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000b98e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000b96f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000b98e`
- `WdsCommonLib!?WdsConvertWdsStringArrayToSafeArray@@YAKPEAV?$CDynArray@PEAGVCDeallocateString@@@@PEAPEAUtagSAFEARRAY@@@Z` at `0x18000b8b4`
- `WdsCommonLib!?WdsConvertWdsStringArrayToSafeArray@@YAKPEAV?$CDynArray@PEAGVCDeallocateString@@@@PEAPEAUtagSAFEARRAY@@@Z` at `0x18000b8b4`
- `WdsCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x18000b93f`
- `WdsCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x18000b93f`

## pseudocode

```c
__int64 __fastcall pGetDeviceById(
        struct _IMG_SERVER_CONTEXT *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IWdsDevice **a4)
{
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // r8d
  __int64 v12; // rdx
  __int64 v13; // r8
  char *v14; // rcx
  __int64 v15; // rdi
  __int64 v16; // rsi
  __int64 v18; // [rsp+20h] [rbp-40h] BYREF
  __int64 v19; // [rsp+28h] [rbp-38h] BYREF
  CMRSWLock *v20; // [rsp+30h] [rbp-30h] BYREF
  int v21; // [rsp+38h] [rbp-28h]
  char *v22; // [rsp+40h] [rbp-20h] BYREF
  int v23; // [rsp+48h] [rbp-18h]
  unsigned int v24; // [rsp+4Ch] [rbp-14h]

  v22 = 0;
  v23 = 0;
  v24 = 0;
  v19 = 0;
  v18 = 0;
  v6 = (unsigned int)BuildDeviceIdQuery((__int64)a1, a2, a3, (__int64)&v22);
  if ( (int)ElValidateHr_1(v6, v7, v8, 860) >= 0 )
  {
    LODWORD(v6) = WdsConvertWdsStringArrayToSafeArray(&v22, &v18);
    if ( (unsigned int)ElValidateWin32_1((unsigned int)v6, v9, v10, 870) )
    {
      if ( (int)v6 > 0 )
        LODWORD(v6) = (unsigned __int16)v6 | 0x80070000;
    }
    else
    {
      v6 = v18;
      CSafeArray::Destroy((CSafeArray *)&v19);
      v18 = 0;
      v19 = v6;
      CAutoReaderLock::CAutoReaderLock((CAutoReaderLock *)&v20, (struct CMRSWLock *)g_Lock, v11);
      LODWORD(v6) = (*(__int64 (__fastcall **)(_QWORD, __int64, struct IWdsDevice **))(**((_QWORD **)a1 + 7) + 72LL))(
                      *((_QWORD *)a1 + 7),
                      v6,
                      a4);
      ElValidateHr_1((unsigned int)v6, v12, v13, 888);
      if ( v21 == 1 )
        CMRSWLock::ReaderRelease(v20);
    }
  }
  CSafeArray::Destroy((CSafeArray *)&v19);
  v14 = v22;
  if ( v24 )
  {
    v15 = 0;
    v16 = v24;
    do
    {
      if ( *(_QWORD *)&v14[v15] )
      {
        operator delete[](*(void **)&v14[v15]);
        v14 = v22;
      }
      v15 += 8;
      --v16;
    }
    while ( v16 );
  }
  if ( v14 )
    operator delete[](v14);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000b858  mov     [rsp-8+arg_0], rbx
0x18000b85d  mov     [rsp-8+arg_8], rsi
0x18000b862  mov     [rsp-8+arg_10], rdi
0x18000b867  push    rbp
0x18000b868  mov     rbp, rsp
0x18000b86b  sub     rsp, 60h
0x18000b86f  and     [rbp+var_20], 0
0x18000b874  mov     rsi, r9
0x18000b877  and     [rbp+var_18], 0
0x18000b87b  lea     r9, [rbp+var_20]
0x18000b87f  and     [rbp+var_14], 0
0x18000b883  mov     rdi, rcx
0x18000b886  and     [rbp+var_38], 0
0x18000b88b  and     [rbp+var_40], 0
0x18000b890  call    ?BuildDeviceIdQuery@@YAJPEAU_IMG_SERVER_CONTEXT@@PEBG1PEAV?$CDynArray@PEAGVCDeallocateString@@@@@Z; BuildDeviceIdQuery(_IMG_SERVER_CONTEXT *,ushort const *,ushort const *,CDynArray<ushort *,CDeallocateString> *)
0x18000b895  mov     r9d, 35Ch
0x18000b89b  mov     ecx, eax
0x18000b89d  mov     ebx, eax
0x18000b89f  call    ElValidateHr_1
0x18000b8a4  test    eax, eax
0x18000b8a6  js      loc_18000B94B
0x18000b8ac  lea     rdx, [rbp+var_40]
0x18000b8b0  lea     rcx, [rbp+var_20]
0x18000b8b4  call    cs:__imp_?WdsConvertWdsStringArrayToSafeArray@@YAKPEAV?$CDynArray@PEAGVCDeallocateString@@@@PEAPEAUtagSAFEARRAY@@@Z; WdsConvertWdsStringArrayToSafeArray(CDynArray<ushort *,CDeallocateString> *,tagSAFEARRAY * *)
0x18000b8bb  nop     dword ptr [rax+rax+00h]
0x18000b8c0  mov     ecx, eax
0x18000b8c2  mov     r9d, 366h
0x18000b8c8  mov     ebx, eax
0x18000b8ca  call    ElValidateWin32_1
0x18000b8cf  test    eax, eax
0x18000b8d1  jz      short loc_18000B8E2
0x18000b8d3  test    ebx, ebx
0x18000b8d5  jle     short loc_18000B94B
0x18000b8d7  movzx   ebx, bx
0x18000b8da  or      ebx, 80070000h
0x18000b8e0  jmp     short loc_18000B94B
0x18000b8e2  mov     rbx, [rbp+var_40]
0x18000b8e6  lea     rcx, [rbp+var_38]; this
0x18000b8ea  call    ?Destroy@CSafeArray@@QEAAXXZ; CSafeArray::Destroy(void)
0x18000b8ef  and     [rbp+var_40], 0
0x18000b8f4  lea     rdx, ?g_Lock@@3VCMRSWLock@@A; struct CMRSWLock *
0x18000b8fb  lea     rcx, [rbp+var_30]; this
0x18000b8ff  mov     [rbp+var_38], rbx
0x18000b903  call    ??0CAutoReaderLock@@QEAA@PEAVCMRSWLock@@H@Z; CAutoReaderLock::CAutoReaderLock(CMRSWLock *,int)
0x18000b908  mov     rcx, [rdi+38h]
0x18000b90c  mov     r8, rsi
0x18000b90f  mov     rdx, rbx
0x18000b912  mov     rax, [rcx]
0x18000b915  mov     rax, [rax+48h]
0x18000b919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b91e  mov     r9d, 378h
0x18000b924  mov     ecx, eax
0x18000b926  mov     ebx, eax
0x18000b928  call    ElValidateHr_1
0x18000b92d  test    eax, eax
0x18000b92f  mov     eax, [rbp+var_28]
0x18000b932  test    eax, eax
0x18000b934  jz      short loc_18000B94B
0x18000b936  cmp     eax, 1
0x18000b939  jnz     short loc_18000B94B
0x18000b93b  mov     rcx, [rbp+var_30]
0x18000b93f  call    cs:__imp_?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x18000b946  nop     dword ptr [rax+rax+00h]
0x18000b94b  lea     rcx, [rbp+var_38]; this
0x18000b94f  call    ?Destroy@CSafeArray@@QEAAXXZ; CSafeArray::Destroy(void)
0x18000b954  mov     eax, [rbp+var_14]
0x18000b957  mov     rcx, [rbp+var_20]
0x18000b95b  test    eax, eax
0x18000b95d  jz      short loc_18000B989
0x18000b95f  xor     edi, edi
0x18000b961  mov     esi, eax
0x18000b963  mov     rax, [rdi+rcx]
0x18000b967  test    rax, rax
0x18000b96a  jz      short loc_18000B97F
0x18000b96c  mov     rcx, rax
0x18000b96f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000b976  nop     dword ptr [rax+rax+00h]
0x18000b97b  mov     rcx, [rbp+var_20]
0x18000b97f  add     rdi, 8
0x18000b983  sub     rsi, 1
0x18000b987  jnz     short loc_18000B963
0x18000b989  test    rcx, rcx
0x18000b98c  jz      short loc_18000B99A
0x18000b98e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000b995  nop     dword ptr [rax+rax+00h]
0x18000b99a  lea     r11, [rsp+60h+var_s0]
0x18000b99f  mov     eax, ebx
0x18000b9a1  mov     rbx, [r11+10h]
0x18000b9a5  mov     rsi, [r11+18h]
0x18000b9a9  mov     rdi, [r11+20h]
0x18000b9ad  mov     rsp, r11
0x18000b9b0  pop     rbp
0x18000b9b1  retn
```
