# PrintForwardEMF(void *,void *,_EMF_ATTRIBUTE_INFO *,int,ulong,_devicemodeW *,_PRINTPROCESSORDATA *)

- ea: `0x180003b40`
- end: `0x180003ce8`
- name: `?PrintForwardEMF@@YAHPEAX0PEAU_EMF_ATTRIBUTE_INFO@@HKPEAU_devicemodeW@@PEAU_PRINTPROCESSORDATA@@@Z`
- size: `424`
- prototype: `int(void *, void *, struct _EMF_ATTRIBUTE_INFO *, int, unsigned int, struct _devicemodeW *, struct _PRINTPROCESSORDATA *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180006b6c`

## callees

- `0x180003b40`
- `0x1800047f0`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003bcf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003bcf`

## pseudocode

```c
__int64 __fastcall PrintForwardEMF(
        void *a1,
        HDC a2,
        struct _EMF_ATTRIBUTE_INFO *a3,
        unsigned int a4,
        unsigned int a5,
        struct _devicemodeW *a6,
        struct _PRINTPROCESSORDATA *a7)
{
  struct _PRINTPROCESSORDATA *v7; // rsi
  int v8; // ebx
  unsigned int v9; // eax
  unsigned int v10; // r9d
  unsigned int v12; // edx
  int v14; // edi
  __int64 (__fastcall *v15)(void *, HDC, struct _EMF_ATTRIBUTE_INFO *, _QWORD, unsigned int, int, unsigned int *, struct _devicemodeW *); // r12
  struct _devicemodeW *v16; // r14
  unsigned int v17; // r13d
  int v18; // eax
  unsigned int v19; // r8d
  unsigned int v20; // ecx
  unsigned int v22; // [rsp+50h] [rbp-48h]
  unsigned int v23; // [rsp+54h] [rbp-44h]
  int v24; // [rsp+58h] [rbp-40h]
  unsigned int v25; // [rsp+5Ch] [rbp-3Ch]
  void *v26; // [rsp+A0h] [rbp+8h]
  unsigned int v27; // [rsp+B0h] [rbp+18h] BYREF
  unsigned int v28; // [rsp+B8h] [rbp+20h]

  v28 = a4;
  v26 = a1;
  v7 = a7;
  v8 = 1;
  v9 = a4;
  v10 = *((_DWORD *)a3 + 12);
  v12 = *((_DWORD *)a3 + 11);
  v14 = *((_DWORD *)a3 + 21);
  v27 = 0;
  v23 = v12;
  v22 = v10;
  if ( *((_DWORD *)a3 + 9) == 1
    || (v15 = (__int64 (__fastcall *)(void *, HDC, struct _EMF_ATTRIBUTE_INFO *, _QWORD, unsigned int, int, unsigned int *, struct _devicemodeW *))PrintOneSideForwardForDriverEMF,
        !*((_DWORD *)a3 + 15)) )
  {
    v15 = (__int64 (__fastcall *)(void *, HDC, struct _EMF_ATTRIBUTE_INFO *, _QWORD, unsigned int, int, unsigned int *, struct _devicemodeW *))PrintOneSideForwardEMF;
  }
  v16 = a6;
  v17 = a5;
  while ( 1 )
  {
    if ( (*((_BYTE *)v7 + 16) & 8) != 0 )
    {
      WaitForSingleObject(*((HANDLE *)v7 + 3), 0xFFFFFFFF);
      v9 = v28;
      a1 = v26;
      v12 = v23;
      v10 = v22;
    }
    if ( v14 )
    {
      v18 = v15(a1, a2, a3, v9, v17, v8, &v27, v16);
      v10 = v22;
      v8 = v18;
    }
    else
    {
      v24 = v8;
      v19 = v12;
      while ( v19 )
      {
        v20 = 0;
        if ( v19 > v10 )
        {
          v20 = v19 - v10;
          v19 = v10;
        }
        v25 = v20;
        SetDrvCopies(a2, v16, v19);
        v8 = v15(v26, a2, a3, v28, v17, v24, &v27, v16);
        if ( !v8 && !v27 )
          return v27;
        v19 = v25;
        v10 = v22;
      }
    }
    if ( !v8 )
      break;
    v9 = v28;
    a1 = v26;
    v12 = v23;
  }
  return v27;
}

```

## disassembly

```asm
0x180003b40  mov     [rsp+arg_8], rbx
0x180003b45  mov     [rsp+arg_18], r9d
0x180003b4a  mov     [rsp+arg_0], rcx
0x180003b4f  push    rbp
0x180003b50  push    rsi
0x180003b51  push    rdi
0x180003b52  push    r12
0x180003b54  push    r13
0x180003b56  push    r14
0x180003b58  push    r15
0x180003b5a  sub     rsp, 60h
0x180003b5e  mov     rsi, [rsp+98h+arg_30]
0x180003b66  mov     ebx, 1
0x180003b6b  mov     eax, r9d
0x180003b6e  mov     r9d, [r8+30h]
0x180003b72  mov     r15, rdx
0x180003b75  mov     edx, [r8+2Ch]
0x180003b79  mov     rbp, r8
0x180003b7c  mov     edi, [r8+54h]
0x180003b80  mov     [rsp+98h+arg_10], 0
0x180003b8b  mov     [rsp+98h+var_44], edx
0x180003b8f  mov     [rsp+98h+var_48], r9d
0x180003b94  cmp     [r8+24h], ebx
0x180003b98  jz      short loc_180003BA8
0x180003b9a  cmp     dword ptr [r8+3Ch], 0
0x180003b9f  lea     r12, ?PrintOneSideForwardForDriverEMF@@YAKPEAX0PEAU_EMF_ATTRIBUTE_INFO@@HKKPEAHPEAU_devicemodeW@@@Z; PrintOneSideForwardForDriverEMF(void *,void *,_EMF_ATTRIBUTE_INFO *,int,ulong,ulong,int *,_devicemodeW *)
0x180003ba6  jnz     short loc_180003BAF
0x180003ba8  lea     r12, ?PrintOneSideForwardEMF@@YAKPEAX0PEAU_EMF_ATTRIBUTE_INFO@@HKKPEAHPEAU_devicemodeW@@@Z; PrintOneSideForwardEMF(void *,void *,_EMF_ATTRIBUTE_INFO *,int,ulong,ulong,int *,_devicemodeW *)
0x180003baf  mov     r14, [rsp+98h+arg_28]
0x180003bb7  mov     r13d, [rsp+98h+arg_20]
0x180003bbf  nop
0x180003bc0  test    byte ptr [rsi+10h], 8
0x180003bc4  jz      short loc_180003BED
0x180003bc6  mov     rcx, [rsi+18h]; hHandle
0x180003bca  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180003bcf  call    cs:__imp_WaitForSingleObject
0x180003bd5  mov     eax, [rsp+98h+arg_18]
0x180003bdc  mov     rcx, [rsp+98h+arg_0]
0x180003be4  mov     edx, [rsp+98h+var_44]
0x180003be8  mov     r9d, [rsp+98h+var_48]
0x180003bed  test    edi, edi
0x180003bef  jz      short loc_180003C44
0x180003bf1  mov     [rsp+98h+var_60], r14
0x180003bf6  lea     rdx, [rsp+98h+arg_10]
0x180003bfe  mov     [rsp+98h+var_68], rdx
0x180003c03  mov     r9d, eax
0x180003c06  mov     [rsp+98h+var_70], ebx
0x180003c0a  mov     rdx, r15
0x180003c0d  mov     r8, rbp
0x180003c10  mov     [rsp+98h+var_78], r13d
0x180003c15  mov     rax, r12
0x180003c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c1d  mov     r9d, [rsp+98h+var_48]
0x180003c22  mov     ebx, eax
0x180003c24  test    ebx, ebx
0x180003c26  jz      loc_180003CC9
0x180003c2c  mov     eax, [rsp+98h+arg_18]
0x180003c33  mov     rcx, [rsp+98h+arg_0]
0x180003c3b  mov     edx, [rsp+98h+var_44]
0x180003c3f  jmp     loc_180003BC0
0x180003c44  mov     [rsp+98h+var_40], ebx
0x180003c48  mov     r8d, edx
0x180003c4b  test    r8d, r8d
0x180003c4e  jz      short loc_180003C24
0x180003c50  xor     ecx, ecx
0x180003c52  mov     eax, r8d
0x180003c55  sub     eax, r9d
0x180003c58  mov     rdx, r14; struct _devicemodeW *
0x180003c5b  cmp     r8d, r9d
0x180003c5e  cmova   ecx, eax
0x180003c61  cmova   r8d, r9d; unsigned int
0x180003c65  mov     [rsp+98h+var_3C], ecx
0x180003c69  mov     rcx, r15; hdc
0x180003c6c  call    ?SetDrvCopies@@YAHPEAXPEAU_devicemodeW@@K@Z; SetDrvCopies(void *,_devicemodeW *,ulong)
0x180003c71  mov     r9d, [rsp+98h+arg_18]
0x180003c79  lea     rax, [rsp+98h+arg_10]
0x180003c81  mov     rcx, [rsp+98h+arg_0]
0x180003c89  mov     r8, rbp
0x180003c8c  mov     [rsp+98h+var_60], r14
0x180003c91  mov     rdx, r15
0x180003c94  mov     [rsp+98h+var_68], rax
0x180003c99  mov     eax, [rsp+98h+var_40]
0x180003c9d  mov     [rsp+98h+var_70], eax
0x180003ca1  mov     rax, r12
0x180003ca4  mov     [rsp+98h+var_78], r13d
0x180003ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cae  mov     ebx, eax
0x180003cb0  test    eax, eax
0x180003cb2  jnz     short loc_180003CBD
0x180003cb4  cmp     [rsp+98h+arg_10], eax
0x180003cbb  jz      short loc_180003CC9
0x180003cbd  mov     r8d, [rsp+98h+var_3C]
0x180003cc2  mov     r9d, [rsp+98h+var_48]
0x180003cc7  jmp     short loc_180003C4B
0x180003cc9  mov     eax, [rsp+98h+arg_10]
0x180003cd0  mov     rbx, [rsp+98h+arg_8]
0x180003cd8  add     rsp, 60h
0x180003cdc  pop     r15
0x180003cde  pop     r14
0x180003ce0  pop     r13
0x180003ce2  pop     r12
0x180003ce4  pop     rdi
0x180003ce5  pop     rsi
0x180003ce6  pop     rbp
0x180003ce7  retn
```
