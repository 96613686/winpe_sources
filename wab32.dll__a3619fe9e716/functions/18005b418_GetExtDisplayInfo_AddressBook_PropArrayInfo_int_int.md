# GetExtDisplayInfo(AddressBook *,_PropArrayInfo *,int,int)

- ea: `0x18005b418`
- end: `0x18005b758`
- name: `?GetExtDisplayInfo@@YAJPEAVAddressBook@@PEAU_PropArrayInfo@@HH@Z`
- size: `832`
- prototype: `__int64 __fastcall(struct AddressBook *, struct _PropArrayInfo *, int, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004f3b4`
- `0x18004f8c4`
- `0x180053818`

## callees

- `0x180002818`
- `0x18005b3c8`
- `0x18005b418`
- `0x18005b760`
- `0x180093010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18005b576`
- `KERNEL32!LocalAlloc` at `0x18005b576`
- `ole32!CoCreateInstance` at `0x18005b6a4`
- `ole32!CoCreateInstance` at `0x18005b6a4`
- `ntdll!WinSqmIncrementDWORD` at `0x18005b4f7`
- `ntdll!WinSqmIncrementDWORD` at `0x18005b54a`
- `ntdll!WinSqmIncrementDWORD` at `0x18005b4f7`
- `ntdll!WinSqmIncrementDWORD` at `0x18005b54a`

## pseudocode

```c
__int64 __fastcall GetExtDisplayInfo(struct AddressBook *a1, struct _PropArrayInfo *a2, int a3, int a4)
{
  int v4; // ebx
  struct _GUID *v8; // rbx
  int ExtDLLInfo; // r12d
  int v10; // eax
  __int64 v11; // rbx
  __int64 v12; // rdi
  unsigned int v13; // r15d
  IID *v14; // rdi
  unsigned int v15; // r12d
  _QWORD *v16; // rax
  _QWORD *v17; // rdx
  unsigned int v18; // ebx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rax
  unsigned int i; // r15d
  unsigned __int8 *Data4; // r14
  IID *v25; // rbx
  HRESULT Instance; // eax
  __int64 v27; // rdx
  unsigned int v29; // [rsp+30h] [rbp-20h] BYREF
  __int128 v30; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v31; // [rsp+90h] [rbp+40h] BYREF
  int v32; // [rsp+A8h] [rbp+58h]

  v32 = a4;
  v4 = a4;
  if ( !*((_QWORD *)a1 + 133) )
  {
    v8 = (struct _GUID *)((char *)a1 + 1076);
    v30 = 0u;
    v29 = 0;
    v31 = 0;
    ExtDLLInfo = HrGetExtDLLInfo((struct _ExtDisplayDLLInfo **)&v30 + 1, &v29, 1, (struct _GUID *)((char *)a1 + 1076));
    v10 = HrGetExtDLLInfo((struct _ExtDisplayDLLInfo **)&v30, &v31, 0, v8);
    v11 = *((_QWORD *)&v30 + 1);
    v12 = v30;
    if ( v30 == 0 )
      return (unsigned int)-2147467259;
    v13 = v31 + v29;
    if ( !(v31 + v29) || ExtDLLInfo < 0 && v10 < 0 )
      return (unsigned int)-2147467259;
    if ( *((_QWORD *)&v30 + 1) )
    {
      if ( v29 > 1 || v29 == 1 && **((_OWORD **)&v30 + 1) != *(_OWORD *)&CLSID_DsPropertyPages )
        WinSqmIncrementDWORD(0, 7245, 1);
      for ( *((_QWORD *)a1 + 133) = v11; *(_QWORD *)(v11 + 40); v11 = *(_QWORD *)(v11 + 40) )
        ;
      *(_QWORD *)(v11 + 40) = v12;
    }
    else
    {
      if ( v31 > 1
        || v31 == 1
        && (*(_QWORD *)v30 != *(_QWORD *)&CLSID_DsPropertyPages.Data1
         || *(_QWORD *)(v30 + 8) != *(_QWORD *)CLSID_DsPropertyPages.Data4) )
      {
        WinSqmIncrementDWORD(0, 7246, 1);
      }
      *((_QWORD *)a1 + 133) = v12;
    }
    v4 = v32;
    *((_DWORD *)a1 + 268) = v13;
  }
  v14 = (IID *)*((_QWORD *)a1 + 133);
  v15 = *((_DWORD *)a1 + 268);
  v16 = LocalAlloc(0x40u, 0x40u);
  *((_QWORD *)a2 + 26) = v16;
  v17 = v16;
  if ( v16 )
  {
    v19 = *((_QWORD *)a2 + 12);
    v20 = v19 + 16;
    if ( !v19 )
      v20 = 648;
    v17[1] = *(_QWORD *)v20;
    *(_QWORD *)(*((_QWORD *)a2 + 26) + 16LL) = *((_QWORD *)a2 + 12);
    *(_QWORD *)(*((_QWORD *)a2 + 26) + 24LL) = *((_QWORD *)a2 + 3);
    *(_DWORD *)(*((_QWORD *)a2 + 26) + 32LL) = a3;
    *(_DWORD *)(*((_QWORD *)a2 + 26) + 36LL) = 0;
    v21 = *((_QWORD *)a2 + 28);
    if ( v21 )
    {
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)(v21 + 2 * v22) );
      if ( v22 )
      {
        *(_DWORD *)(*((_QWORD *)a2 + 26) + 40LL) |= 1u;
        *(_QWORD *)(*((_QWORD *)a2 + 26) + 56LL) = *((_QWORD *)a2 + 28);
        *(_DWORD *)(*((_QWORD *)a2 + 26) + 40LL) |= 0x80000000;
        if ( *((_DWORD *)a2 + 58) )
          *(_DWORD *)(*((_QWORD *)a2 + 26) + 40LL) |= 4u;
      }
    }
    for ( i = 0; i < v15; ++i )
    {
      if ( v14 )
      {
        if ( v14[1].Data1 == v4 )
        {
          Data4 = v14[1].Data4;
          v25 = v14 + 2;
          if ( !*(_QWORD *)v14[1].Data4 || !*(_QWORD *)&v25->Data1 )
          {
            Instance = CoCreateInstance(v14, 0, 3u, &IID_IShellPropSheetExt, (LPVOID *)v14[1].Data4);
            if ( *(_QWORD *)Data4 )
            {
              if ( Instance >= 0 )
              {
                v25 = v14 + 2;
                if ( (***(int (__fastcall ****)(_QWORD, GUID *, __int64))Data4)(
                       *(_QWORD *)Data4,
                       &IID_IWABExtInit,
                       (__int64)&v14[2]) < 0
                  || !*(_QWORD *)&v25->Data1 )
                {
                  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(v14[1].Data4);
                }
              }
            }
          }
          if ( *(_QWORD *)Data4 )
          {
            if ( *(_QWORD *)&v25->Data1 )
            {
              v27 = *((_QWORD *)a2 + 26);
              *(IID *)((char *)a2 + 264) = *v14;
              if ( (*(int (__fastcall **)(_QWORD, __int64))(**(_QWORD **)&v25->Data1 + 24LL))(
                     *(_QWORD *)&v25->Data1,
                     v27) >= 0 )
                (*(void (__fastcall **)(_QWORD, __int64 (__fastcall *)(struct _PSP *, __int64), struct _PropArrayInfo *))(**(_QWORD **)Data4 + 24LL))(
                  *(_QWORD *)Data4,
                  AddPropSheetPageProc,
                  a2);
            }
          }
          v4 = v32;
        }
        v14 = *(IID **)v14[2].Data4;
      }
    }
    return 0;
  }
  else
  {
    v18 = -2147024882;
    if ( v14 )
      FreePropExtList(v14);
  }
  return v18;
}

```

## disassembly

```asm
0x18005b418  mov     [rsp-38h+arg_8], rbx
0x18005b41d  mov     [rsp-38h+arg_18], r9d
0x18005b422  push    rbp
0x18005b423  push    rsi
0x18005b424  push    rdi
0x18005b425  push    r12
0x18005b427  push    r13
0x18005b429  push    r14
0x18005b42b  push    r15
0x18005b42d  mov     rbp, rsp
0x18005b430  sub     rsp, 50h
0x18005b434  xor     r15d, r15d
0x18005b437  mov     ebx, r9d
0x18005b43a  mov     r13d, r8d
0x18005b43d  mov     rsi, rdx
0x18005b440  mov     r14, rcx
0x18005b443  cmp     [rcx+428h], r15
0x18005b44a  jnz     loc_18005B561
0x18005b450  lea     rbx, [rcx+434h]
0x18005b457  mov     qword ptr [rbp+var_18+8], r15
0x18005b45b  mov     r9, rbx; struct _GUID *
0x18005b45e  mov     qword ptr [rbp+var_18], r15
0x18005b462  lea     r8d, [r15+1]; int
0x18005b466  mov     [rbp+var_20], r15d
0x18005b46a  lea     rdx, [rbp+var_20]; unsigned int *
0x18005b46e  mov     [rbp+arg_0], r15d
0x18005b472  lea     rcx, [rbp+var_18+8]; struct _ExtDisplayDLLInfo **
0x18005b476  call    ?HrGetExtDLLInfo@@YAJPEAPEAU_ExtDisplayDLLInfo@@PEAKHPEAU_GUID@@@Z; HrGetExtDLLInfo(_ExtDisplayDLLInfo * *,ulong *,int,_GUID *)
0x18005b47b  mov     r9, rbx; struct _GUID *
0x18005b47e  lea     rdx, [rbp+arg_0]; unsigned int *
0x18005b482  xor     r8d, r8d; int
0x18005b485  lea     rcx, [rbp+var_18]; struct _ExtDisplayDLLInfo **
0x18005b489  mov     r12d, eax
0x18005b48c  call    ?HrGetExtDLLInfo@@YAJPEAPEAU_ExtDisplayDLLInfo@@PEAKHPEAU_GUID@@@Z; HrGetExtDLLInfo(_ExtDisplayDLLInfo * *,ulong *,int,_GUID *)
0x18005b491  mov     rbx, qword ptr [rbp+var_18+8]
0x18005b495  mov     rdi, qword ptr [rbp+var_18]
0x18005b499  test    rbx, rbx
0x18005b49c  jnz     short loc_18005B4A7
0x18005b49e  test    rdi, rdi
0x18005b4a1  jz      loc_18005B5A6
0x18005b4a7  mov     ecx, [rbp+arg_0]
0x18005b4aa  mov     edx, [rbp+var_20]
0x18005b4ad  lea     r15d, [rcx+rdx]
0x18005b4b1  test    r15d, r15d
0x18005b4b4  jz      loc_18005B5A6
0x18005b4ba  test    r12d, r12d
0x18005b4bd  jns     short loc_18005B4C7
0x18005b4bf  test    eax, eax
0x18005b4c1  js      loc_18005B5A6
0x18005b4c7  test    rbx, rbx
0x18005b4ca  jz      short loc_18005B51F
0x18005b4cc  cmp     edx, 1
0x18005b4cf  ja      short loc_18005B4EC
0x18005b4d1  jnz     short loc_18005B4FD
0x18005b4d3  mov     rax, [rbx]
0x18005b4d6  cmp     rax, qword ptr cs:CLSID_DsPropertyPages.Data1
0x18005b4dd  jnz     short loc_18005B4EC
0x18005b4df  mov     rax, [rbx+8]
0x18005b4e3  cmp     rax, qword ptr cs:CLSID_DsPropertyPages.Data4
0x18005b4ea  jz      short loc_18005B4FD
0x18005b4ec  xor     ecx, ecx
0x18005b4ee  mov     edx, 1C4Dh
0x18005b4f3  lea     r8d, [rcx+1]
0x18005b4f7  call    cs:__imp_WinSqmIncrementDWORD
0x18005b4fd  mov     [r14+428h], rbx
0x18005b504  cmp     qword ptr [rbx+28h], 0
0x18005b509  jz      short loc_18005B519
0x18005b50b  mov     rax, [rbx+28h]
0x18005b50f  mov     rbx, rax
0x18005b512  cmp     qword ptr [rax+28h], 0
0x18005b517  jnz     short loc_18005B50B
0x18005b519  mov     [rbx+28h], rdi
0x18005b51d  jmp     short loc_18005B557
0x18005b51f  cmp     ecx, 1
0x18005b522  ja      short loc_18005B53F
0x18005b524  jnz     short loc_18005B550
0x18005b526  mov     rax, [rdi]
0x18005b529  cmp     rax, qword ptr cs:CLSID_DsPropertyPages.Data1
0x18005b530  jnz     short loc_18005B53F
0x18005b532  mov     rax, [rdi+8]
0x18005b536  cmp     rax, qword ptr cs:CLSID_DsPropertyPages.Data4
0x18005b53d  jz      short loc_18005B550
0x18005b53f  xor     ecx, ecx
0x18005b541  mov     edx, 1C4Eh
0x18005b546  lea     r8d, [rcx+1]
0x18005b54a  call    cs:__imp_WinSqmIncrementDWORD
0x18005b550  mov     [r14+428h], rdi
0x18005b557  mov     ebx, [rbp+arg_18]
0x18005b55a  mov     [r14+430h], r15d
0x18005b561  mov     rdi, [r14+428h]
0x18005b568  mov     ecx, 40h ; '@'; uFlags
0x18005b56d  mov     r12d, [r14+430h]
0x18005b574  mov     edx, ecx; uBytes
0x18005b576  call    cs:__imp_LocalAlloc
0x18005b57c  mov     [rsi+0D0h], rax
0x18005b583  mov     rdx, rax
0x18005b586  test    rax, rax
0x18005b589  jnz     short loc_18005B5B0
0x18005b58b  mov     ebx, 8007000Eh
0x18005b590  test    rdi, rdi
0x18005b593  jz      loc_18005B73E
0x18005b599  mov     rcx, rdi; hMem
0x18005b59c  call    ?FreePropExtList@@YAXPEAU_ExtDisplayDLLInfo@@@Z; FreePropExtList(_ExtDisplayDLLInfo *)
0x18005b5a1  jmp     loc_18005B73E
0x18005b5a6  mov     ebx, 80004005h
0x18005b5ab  jmp     loc_18005B73E
0x18005b5b0  mov     rax, [rsi+60h]
0x18005b5b4  mov     r8d, 288h
0x18005b5ba  test    rax, rax
0x18005b5bd  lea     rcx, [rax+10h]
0x18005b5c1  cmovz   rcx, r8
0x18005b5c5  mov     rax, [rcx]
0x18005b5c8  mov     [rdx+8], rax
0x18005b5cc  mov     rcx, [rsi+0D0h]
0x18005b5d3  mov     rax, [rsi+60h]
0x18005b5d7  mov     [rcx+10h], rax
0x18005b5db  mov     rcx, [rsi+0D0h]
0x18005b5e2  mov     rax, [rsi+18h]
0x18005b5e6  mov     [rcx+18h], rax
0x18005b5ea  mov     rax, [rsi+0D0h]
0x18005b5f1  mov     [rax+20h], r13d
0x18005b5f5  xor     r13d, r13d
0x18005b5f8  mov     rax, [rsi+0D0h]
0x18005b5ff  mov     [rax+24h], r13d
0x18005b603  mov     rcx, [rsi+0E0h]
0x18005b60a  test    rcx, rcx
0x18005b60d  jz      short loc_18005B65F
0x18005b60f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005b613  inc     rax
0x18005b616  cmp     [rcx+rax*2], r13w
0x18005b61b  jnz     short loc_18005B613
0x18005b61d  test    rax, rax
0x18005b620  jz      short loc_18005B65F
0x18005b622  mov     rax, [rsi+0D0h]
0x18005b629  or      dword ptr [rax+28h], 1
0x18005b62d  mov     rax, [rsi+0E0h]
0x18005b634  mov     rcx, [rsi+0D0h]
0x18005b63b  mov     [rcx+38h], rax
0x18005b63f  mov     rax, [rsi+0D0h]
0x18005b646  bts     dword ptr [rax+28h], 1Fh
0x18005b64b  cmp     [rsi+0E8h], r13d
0x18005b652  jz      short loc_18005B65F
0x18005b654  mov     rax, [rsi+0D0h]
0x18005b65b  or      dword ptr [rax+28h], 4
0x18005b65f  mov     r15d, r13d
0x18005b662  test    r12d, r12d
0x18005b665  jz      loc_18005B73B
0x18005b66b  test    rdi, rdi
0x18005b66e  jz      loc_18005B72F
0x18005b674  cmp     [rdi+10h], ebx
0x18005b677  jnz     loc_18005B72B
0x18005b67d  lea     r14, [rdi+18h]
0x18005b681  lea     rbx, [rdi+20h]
0x18005b685  cmp     [r14], r13
0x18005b688  jz      short loc_18005B68F
0x18005b68a  cmp     [rbx], r13
0x18005b68d  jnz     short loc_18005B6E0
0x18005b68f  xor     edx, edx; pUnkOuter
0x18005b691  mov     [rsp+50h+ppv], r14; ppv
0x18005b696  lea     r9, IID_IShellPropSheetExt; riid
0x18005b69d  mov     rcx, rdi; rclsid
0x18005b6a0  lea     r8d, [rdx+3]; dwClsContext
0x18005b6a4  call    cs:__imp_CoCreateInstance
0x18005b6aa  mov     rcx, [r14]
0x18005b6ad  test    rcx, rcx
0x18005b6b0  jz      short loc_18005B6E0
0x18005b6b2  test    eax, eax
0x18005b6b4  js      short loc_18005B6E0
0x18005b6b6  mov     rax, [rcx]
0x18005b6b9  lea     rbx, [rdi+20h]
0x18005b6bd  mov     r8, rbx
0x18005b6c0  lea     rdx, IID_IWABExtInit
0x18005b6c7  mov     rax, [rax]
0x18005b6ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b6cf  test    eax, eax
0x18005b6d1  js      short loc_18005B6D8
0x18005b6d3  cmp     [rbx], r13
0x18005b6d6  jnz     short loc_18005B6E0
0x18005b6d8  mov     rcx, r14
0x18005b6db  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18005b6e0  cmp     [r14], r13
0x18005b6e3  jz      short loc_18005B728
0x18005b6e5  cmp     [rbx], r13
0x18005b6e8  jz      short loc_18005B728
0x18005b6ea  movups  xmm0, xmmword ptr [rdi]
0x18005b6ed  mov     rdx, [rsi+0D0h]
0x18005b6f4  movdqu  xmmword ptr [rsi+108h], xmm0
0x18005b6fc  mov     rcx, [rbx]
0x18005b6ff  mov     rax, [rcx]
0x18005b702  mov     rax, [rax+18h]
0x18005b706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b70b  test    eax, eax
0x18005b70d  js      short loc_18005B728
0x18005b70f  mov     rcx, [r14]
0x18005b712  lea     rdx, ?AddPropSheetPageProc@@YAHPEAU_PSP@@_J@Z; AddPropSheetPageProc(_PSP *,__int64)
0x18005b719  mov     r8, rsi
0x18005b71c  mov     rax, [rcx]
0x18005b71f  mov     rax, [rax+18h]
0x18005b723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b728  mov     ebx, [rbp+arg_18]
0x18005b72b  mov     rdi, [rdi+28h]
0x18005b72f  inc     r15d
0x18005b732  cmp     r15d, r12d
0x18005b735  jb      loc_18005B66B
0x18005b73b  mov     ebx, r13d
0x18005b73e  mov     eax, ebx
0x18005b740  mov     rbx, [rsp+50h+arg_8]
0x18005b748  add     rsp, 50h
0x18005b74c  pop     r15
0x18005b74e  pop     r14
0x18005b750  pop     r13
0x18005b752  pop     r12
0x18005b754  pop     rdi
0x18005b755  pop     rsi
0x18005b756  pop     rbp
0x18005b757  retn
```
