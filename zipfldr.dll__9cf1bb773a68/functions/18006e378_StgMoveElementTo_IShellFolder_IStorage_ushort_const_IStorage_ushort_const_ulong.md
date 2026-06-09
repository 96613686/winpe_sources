# StgMoveElementTo(IShellFolder *,IStorage *,ushort const *,IStorage *,ushort const *,ulong)

- ea: `0x18006e378`
- end: `0x18006e65e`
- name: `?StgMoveElementTo@@YAJPEAUIShellFolder@@PEAUIStorage@@PEBG12K@Z`
- size: `742`
- prototype: `int(struct IShellFolder *, struct IStorage *, const unsigned __int16 *, struct IStorage *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006dea0`

## callees

- `0x180036f50`
- `0x180037958`
- `0x18006e0a8`
- `0x18006e378`
- `0x180071010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x18006e636`
- `SHELL32!__imp_ILFree` at `0x18006e636`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e5dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e5dd`

## pseudocode

```c
__int64 __fastcall StgMoveElementTo(
        struct IShellFolder *a1,
        struct IStorage *a2,
        struct IBindCtx *a3,
        struct IStorage *a4,
        const unsigned __int16 *a5,
        unsigned int a6)
{
  int v11; // ebx
  struct IShellFolderVtbl *lpVtbl; // rax
  struct IStorageVtbl *v13; // rax
  __int64 v14; // rcx
  struct IShellFolderVtbl *v15; // rax
  struct IStorageVtbl *v16; // rax
  unsigned int *v17; // [rsp+20h] [rbp-A9h]
  unsigned int *v18; // [rsp+30h] [rbp-99h]
  LPITEMIDLIST pidl; // [rsp+40h] [rbp-89h] BYREF
  __int64 v20; // [rsp+48h] [rbp-81h] BYREF
  __int64 v21; // [rsp+50h] [rbp-79h] BYREF
  __int64 v22; // [rsp+58h] [rbp-71h] BYREF
  __int64 v23; // [rsp+60h] [rbp-69h] BYREF
  LPVOID pv[10]; // [rsp+70h] [rbp-59h] BYREF

  if ( a6 >= 2 )
    return 2147942487LL;
  pidl = 0;
  v11 = ParseDisplayNameChild(a1, (HWND)a2, a3, (const unsigned __int16 *)a3, v17, (struct _ITEMID_CHILD **)&pidl, v18);
  if ( v11 >= 0 )
  {
    lpVtbl = a1->lpVtbl;
    v23 = 0;
    if ( ((int (__fastcall *)(struct IShellFolder *, LPITEMIDLIST, _QWORD, GUID *, __int64 *))lpVtbl->BindToObject)(
           a1,
           pidl,
           0,
           &GUID_0000000c_0000_0000_c000_000000000046,
           &v23) < 0 )
    {
      v15 = a1->lpVtbl;
      v22 = 0;
      v11 = ((__int64 (__fastcall *)(struct IShellFolder *, LPITEMIDLIST, _QWORD, GUID *, __int64 *))v15->BindToObject)(
              a1,
              pidl,
              0,
              &GUID_0000000b_0000_0000_c000_000000000046,
              &v22);
      if ( v11 < 0 )
      {
LABEL_25:
        ILFree(pidl);
        return (unsigned int)v11;
      }
      v16 = a4->lpVtbl;
      v20 = 0;
      v11 = ((__int64 (__fastcall *)(struct IStorage *, const unsigned __int16 *, __int64, _QWORD, _DWORD, __int64 *))v16->CreateStorage)(
              a4,
              a5,
              4114,
              0,
              0,
              &v20);
      if ( v11 >= 0 )
      {
        v21 = 0;
        if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v22 + 88LL))(
               v22,
               0,
               0,
               0,
               &v21) )
        {
          goto LABEL_21;
        }
        memset_0(pv, 0, sizeof(pv));
        do
        {
          if ( (*(unsigned int (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v21 + 24LL))(v21, 1, pv) )
            break;
          v11 = (*(__int64 (__fastcall **)(__int64, LPVOID, __int64, LPVOID, unsigned int))(*(_QWORD *)v22 + 64LL))(
                  v22,
                  pv[0],
                  v20,
                  pv[0],
                  a6);
          if ( v11 >= 0 )
            v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20 + 72LL))(v20, 0);
          CoTaskMemFree(pv[0]);
        }
        while ( v11 >= 0 );
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        if ( v11 >= 0 )
LABEL_21:
          v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20 + 72LL))(v20, 0);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      }
      v14 = v22;
    }
    else
    {
      v13 = a4->lpVtbl;
      v20 = 0;
      v11 = ((__int64 (__fastcall *)(struct IStorage *, const unsigned __int16 *, __int64, _QWORD, _DWORD, __int64 *))v13->CreateStream)(
              a4,
              a5,
              4113,
              0,
              0,
              &v20);
      if ( v11 >= 0 )
      {
        v21 = -1;
        v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v23 + 56LL))(
                v23,
                v20,
                -1,
                0,
                0);
        if ( v11 >= 0 )
        {
          v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20 + 64LL))(v20, 0);
          if ( v11 >= 0 && !a6 )
            v11 = ((__int64 (__fastcall *)(struct IStorage *, struct IBindCtx *))a2->lpVtbl->DestroyElement)(a2, a3);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      }
      v14 = v23;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    goto LABEL_25;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18006e378  push    rbp
0x18006e37a  push    rbx
0x18006e37b  push    rsi
0x18006e37c  push    rdi
0x18006e37d  push    r12
0x18006e37f  push    r13
0x18006e381  push    r14
0x18006e383  push    r15
0x18006e385  lea     rbp, [rsp-0Fh]
0x18006e38a  sub     rsp, 0D8h
0x18006e391  mov     rax, cs:__security_cookie
0x18006e398  xor     rax, rsp
0x18006e39b  mov     [rbp+47h+var_50], rax
0x18006e39f  mov     r12d, [rbp+47h+arg_28]
0x18006e3a3  mov     rsi, r9
0x18006e3a6  mov     r13, [rbp+47h+arg_20]
0x18006e3aa  mov     r14, r8
0x18006e3ad  mov     r15, rdx
0x18006e3b0  mov     rdi, rcx
0x18006e3b3  cmp     r12d, 2
0x18006e3b7  jb      short loc_18006E3C3
0x18006e3b9  mov     eax, 80070057h
0x18006e3be  jmp     loc_18006E63E
0x18006e3c3  lea     rax, [rsp+110h+pidl]
0x18006e3c8  mov     [rsp+110h+pidl], 0
0x18006e3d1  mov     r9, r14; unsigned __int16 *
0x18006e3d4  mov     [rsp+110h+var_E8], rax; struct _ITEMID_CHILD **
0x18006e3d9  call    ?ParseDisplayNameChild@@YAJPEAUIShellFolder@@PEAUHWND__@@PEAUIBindCtx@@PEBGPEAKPEAPEAU_ITEMID_CHILD@@4@Z; ParseDisplayNameChild(IShellFolder *,HWND__ *,IBindCtx *,ushort const *,ulong *,_ITEMID_CHILD * *,ulong *)
0x18006e3de  mov     ebx, eax
0x18006e3e0  test    eax, eax
0x18006e3e2  js      loc_18006E63C
0x18006e3e8  mov     rax, [rdi]
0x18006e3eb  lea     rcx, [rbp+47h+var_B0]
0x18006e3ef  mov     rdx, [rsp+110h+pidl]
0x18006e3f4  lea     r9, _GUID_0000000c_0000_0000_c000_000000000046
0x18006e3fb  mov     [rsp+110h+var_F0], rcx
0x18006e400  xor     r8d, r8d
0x18006e403  mov     rcx, rdi
0x18006e406  mov     [rbp+47h+var_B0], 0
0x18006e40e  mov     rax, [rax+28h]
0x18006e412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e417  test    eax, eax
0x18006e419  js      loc_18006E4D1
0x18006e41f  mov     rax, [rsi]
0x18006e422  lea     rcx, [rsp+110h+var_C8]
0x18006e427  mov     [rsp+110h+var_E8], rcx
0x18006e42c  xor     edi, edi
0x18006e42e  xor     r9d, r9d
0x18006e431  mov     [rsp+110h+var_C8], rdi
0x18006e436  mov     r8d, 1011h
0x18006e43c  mov     dword ptr [rsp+110h+var_F0], edi
0x18006e440  mov     rax, [rax+18h]
0x18006e444  mov     rdx, r13
0x18006e447  mov     rcx, rsi
0x18006e44a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e44f  mov     ebx, eax
0x18006e451  test    eax, eax
0x18006e453  js      short loc_18006E4C8
0x18006e455  mov     rcx, [rbp+47h+var_B0]
0x18006e459  or      eax, 0FFFFFFFFh
0x18006e45c  mov     rdx, [rsp+110h+var_C8]
0x18006e461  xor     r9d, r9d
0x18006e464  mov     dword ptr [rbp+47h+var_C0], eax
0x18006e467  mov     dword ptr [rbp+47h+var_C0+4], eax
0x18006e46a  mov     rax, [rcx]
0x18006e46d  mov     r8, [rbp+47h+var_C0]
0x18006e471  mov     [rsp+110h+var_F0], rdi
0x18006e476  mov     rax, [rax+38h]
0x18006e47a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e47f  mov     ebx, eax
0x18006e481  test    eax, eax
0x18006e483  js      short loc_18006E4B7
0x18006e485  mov     rcx, [rsp+110h+var_C8]
0x18006e48a  xor     edx, edx
0x18006e48c  mov     rax, [rcx]
0x18006e48f  mov     rax, [rax+40h]
0x18006e493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e498  mov     ebx, eax
0x18006e49a  test    eax, eax
0x18006e49c  js      short loc_18006E4B7
0x18006e49e  test    r12d, r12d
0x18006e4a1  jnz     short loc_18006E4B7
0x18006e4a3  mov     rax, [r15]
0x18006e4a6  mov     rdx, r14
0x18006e4a9  mov     rcx, r15
0x18006e4ac  mov     rax, [rax+60h]
0x18006e4b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e4b5  mov     ebx, eax
0x18006e4b7  mov     rcx, [rsp+110h+var_C8]
0x18006e4bc  mov     rax, [rcx]
0x18006e4bf  mov     rax, [rax+10h]
0x18006e4c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e4c8  mov     rcx, [rbp+47h+var_B0]
0x18006e4cc  jmp     loc_18006E625
0x18006e4d1  mov     rax, [rdi]
0x18006e4d4  lea     rcx, [rbp+47h+var_B8]
0x18006e4d8  mov     rdx, [rsp+110h+pidl]
0x18006e4dd  lea     r9, _GUID_0000000b_0000_0000_c000_000000000046
0x18006e4e4  mov     [rsp+110h+var_F0], rcx
0x18006e4e9  xor     r14d, r14d
0x18006e4ec  xor     r8d, r8d
0x18006e4ef  mov     [rbp+47h+var_B8], r14
0x18006e4f3  mov     rax, [rax+28h]
0x18006e4f7  mov     rcx, rdi
0x18006e4fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e4ff  mov     ebx, eax
0x18006e501  test    eax, eax
0x18006e503  js      loc_18006E631
0x18006e509  mov     rax, [rsi]
0x18006e50c  lea     rcx, [rsp+110h+var_C8]
0x18006e511  mov     [rsp+110h+var_E8], rcx
0x18006e516  xor     r9d, r9d
0x18006e519  mov     r8d, 1012h
0x18006e51f  mov     [rsp+110h+var_C8], r14
0x18006e524  mov     rdx, r13
0x18006e527  mov     dword ptr [rsp+110h+var_F0], r14d
0x18006e52c  mov     rax, [rax+28h]
0x18006e530  mov     rcx, rsi
0x18006e533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e538  mov     ebx, eax
0x18006e53a  test    eax, eax
0x18006e53c  js      loc_18006E621
0x18006e542  mov     rcx, [rbp+47h+var_B8]
0x18006e546  lea     rdx, [rbp+47h+var_C0]
0x18006e54a  mov     [rbp+47h+var_C0], r14
0x18006e54e  xor     r9d, r9d
0x18006e551  mov     [rsp+110h+var_F0], rdx
0x18006e556  xor     r8d, r8d
0x18006e559  xor     edx, edx
0x18006e55b  mov     rax, [rcx]
0x18006e55e  mov     rax, [rax+58h]
0x18006e562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e567  test    eax, eax
0x18006e569  jnz     loc_18006E5FB
0x18006e56f  xor     edx, edx; Val
0x18006e571  lea     r8d, [r14+50h]; Size
0x18006e575  lea     rcx, [rbp+47h+pv]; void *
0x18006e579  call    memset_0
0x18006e57e  mov     rcx, [rbp+47h+var_C0]
0x18006e582  lea     r8, [rbp+47h+pv]
0x18006e586  xor     r9d, r9d
0x18006e589  mov     rax, [rcx]
0x18006e58c  lea     edx, [r9+1]
0x18006e590  mov     rax, [rax+18h]
0x18006e594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e599  test    eax, eax
0x18006e59b  jnz     short loc_18006E5E7
0x18006e59d  mov     rcx, [rbp+47h+var_B8]
0x18006e5a1  mov     rdx, [rbp+47h+pv]
0x18006e5a5  mov     r8, [rsp+110h+var_C8]
0x18006e5aa  mov     r9, rdx
0x18006e5ad  mov     dword ptr [rsp+110h+var_F0], r12d
0x18006e5b2  mov     rax, [rcx]
0x18006e5b5  mov     rax, [rax+40h]
0x18006e5b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e5be  mov     ebx, eax
0x18006e5c0  test    eax, eax
0x18006e5c2  js      short loc_18006E5D9
0x18006e5c4  mov     rcx, [rsp+110h+var_C8]
0x18006e5c9  xor     edx, edx
0x18006e5cb  mov     rax, [rcx]
0x18006e5ce  mov     rax, [rax+48h]
0x18006e5d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e5d7  mov     ebx, eax
0x18006e5d9  mov     rcx, [rbp+47h+pv]; pv
0x18006e5dd  call    cs:__imp_CoTaskMemFree
0x18006e5e3  test    ebx, ebx
0x18006e5e5  jns     short loc_18006E57E
0x18006e5e7  mov     rcx, [rbp+47h+var_C0]
0x18006e5eb  mov     rax, [rcx]
0x18006e5ee  mov     rax, [rax+10h]
0x18006e5f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e5f7  test    ebx, ebx
0x18006e5f9  js      short loc_18006E610
0x18006e5fb  mov     rcx, [rsp+110h+var_C8]
0x18006e600  xor     edx, edx
0x18006e602  mov     rax, [rcx]
0x18006e605  mov     rax, [rax+48h]
0x18006e609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e60e  mov     ebx, eax
0x18006e610  mov     rcx, [rsp+110h+var_C8]
0x18006e615  mov     rax, [rcx]
0x18006e618  mov     rax, [rax+10h]
0x18006e61c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e621  mov     rcx, [rbp+47h+var_B8]
0x18006e625  mov     rax, [rcx]
0x18006e628  mov     rax, [rax+10h]
0x18006e62c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e631  mov     rcx, [rsp+110h+pidl]; pidl
0x18006e636  call    cs:__imp_ILFree
0x18006e63c  mov     eax, ebx
0x18006e63e  mov     rcx, [rbp+47h+var_50]
0x18006e642  xor     rcx, rsp; StackCookie
0x18006e645  call    __security_check_cookie
0x18006e64a  add     rsp, 0D8h
0x18006e651  pop     r15
0x18006e653  pop     r14
0x18006e655  pop     r13
0x18006e657  pop     r12
0x18006e659  pop     rdi
0x18006e65a  pop     rsi
0x18006e65b  pop     rbx
0x18006e65c  pop     rbp
0x18006e65d  retn
```
