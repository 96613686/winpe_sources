# CThemeFile::GetAllSoundEvents(ushort * *)

- ea: `0x180016950`
- end: `0x180016c2b`
- name: `?GetAllSoundEvents@CThemeFile@@UEAAJPEAPEAG@Z`
- size: `731`
- prototype: `__int64 __fastcall(CThemeFile *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000a9a0`
- `0x180016950`
- `0x1800179e0`
- `0x1800199d0`
- `0x18001e1ec`
- `0x180033698`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016bbd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016bbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016a4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016a4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016b4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016b8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016b4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016b8a`

## pseudocode

```c
__int64 __fastcall CThemeFile::GetAllSoundEvents(CThemeFile *this, LPVOID *a2)
{
  __int64 result; // rax
  struct ICachedPrivateProfile *v4; // r12
  int v5; // r14d
  struct ICachedPrivateProfile *v6; // rbx
  char *p; // rdi
  int v8; // r15d
  __int64 v9; // rax
  bool v10; // zf
  int v11; // ebp
  unsigned __int16 *v12; // rax
  int v13; // ebp
  unsigned __int16 *v14; // rsi
  int v15; // edi
  unsigned __int16 *Ptr; // rcx
  __int64 v17; // rax
  __int64 v18; // r8
  int v19; // r10d
  __int64 v20; // rdx
  unsigned __int16 *v21; // r9
  unsigned __int16 *v22; // rcx
  int v23; // r8d
  int v24; // r9d
  BOOL bIgnoreCase; // [rsp+20h] [rbp-58h]
  int v26; // [rsp+28h] [rbp-50h]
  HDPA v27; // [rsp+80h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+90h] [rbp+18h] BYREF

  v27 = 0;
  result = CThemeFile::_GetCachedProfile((CThemeFile *)((char *)this - 16), 0, &v27);
  if ( (int)result >= 0 )
  {
    v4 = v27;
    pv = 0;
    v5 = (*(__int64 (__fastcall **)(HDPA, LPVOID *))(*(_QWORD *)v27 + 64LL))(v27, &pv);
    if ( v5 < 0 )
    {
LABEL_33:
      (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v4 + 16LL))(v4);
      return (unsigned int)v5;
    }
    v27 = g_pfn_DPA_Create(16);
    v6 = v27;
    if ( !v27 )
    {
      v5 = -2147024882;
LABEL_31:
      CoTaskMemFree(pv);
      if ( v6 )
        CDPA_Base<unsigned short,CTContainer_PolicyUnOwned<unsigned short>>::Destroy(&v27);
      goto LABEL_33;
    }
    v5 = 0;
    p = (char *)pv;
    v8 = 1;
    if ( *(_WORD *)pv )
    {
      while ( v5 >= 0 )
      {
        v9 = -1;
        do
          v10 = *(_WORD *)&p[2 * v9++ + 2] == 0;
        while ( !v10 );
        v11 = v9 + 1;
        if ( (unsigned __int64)((int)v9 + 1) >= 0x17
          && CompareStringOrdinal(L"AppEvents\\Schemes\\Apps", 22, (LPCWCH)p, 22, 1) == 2 )
        {
          v8 += v11;
          v5 = -2147467259;
          if ( (unsigned int)CDPA<unsigned short,CTContainer_PolicyUnOwned<unsigned short>>::SortedInsertPtr(
                               (int)&v27,
                               (int)p,
                               v23,
                               v24,
                               bIgnoreCase,
                               v26,
                               p) != -1 )
            v5 = 0;
        }
        v10 = *(_WORD *)&p[2 * v11] == 0;
        p += 2 * v11;
        if ( v10 )
        {
          if ( v5 < 0 )
            goto LABEL_30;
          goto LABEL_11;
        }
      }
      goto LABEL_30;
    }
LABEL_11:
    v12 = (unsigned __int16 *)CoTaskMemAlloc(2LL * v8);
    v5 = 0;
    *a2 = v12;
    v13 = *(_DWORD *)v6;
    v14 = v12;
    if ( !v12 )
      v5 = -2147024882;
    if ( v13 <= 0 )
    {
LABEL_28:
      if ( v5 >= 0 )
      {
        *v14 = 0;
LABEL_30:
        CDPA_Base<unsigned short,CTContainer_PolicyUnOwned<unsigned short>>::Destroy(&v27);
        v6 = v27;
        goto LABEL_31;
      }
    }
    else
    {
      v15 = 0;
      while ( v5 >= 0 )
      {
        Ptr = (unsigned __int16 *)g_pfn_DPA_GetPtr(v6, (unsigned int)v15);
        v17 = -1;
        do
          v10 = Ptr[++v17] == 0;
        while ( !v10 );
        v18 = v8;
        v19 = v17 + 1;
        if ( v8 )
        {
          if ( (unsigned __int64)v8 > 0x7FFFFFFF )
          {
            v5 = -2147024809;
            *v14 = 0;
          }
          else
          {
            v20 = 2147483646;
            v21 = v14;
            do
            {
              if ( !v20 )
                break;
              if ( !*Ptr )
                break;
              *v21++ = *Ptr++;
              --v20;
              --v18;
            }
            while ( v18 );
            v22 = v21 - 1;
            v5 = -2147024774;
            if ( v18 )
            {
              v22 = v21;
              v5 = 0;
            }
            *v22 = 0;
          }
        }
        else
        {
          v5 = -2147024809;
        }
        v8 -= v19;
        ++v15;
        v14 += v19;
        if ( v15 >= v13 )
          goto LABEL_28;
      }
    }
    CoTaskMemFree(*a2);
    *a2 = 0;
    goto LABEL_30;
  }
  return result;
}

```

## disassembly

```asm
0x180016950  mov     rax, rsp
0x180016953  push    rdi
0x180016954  push    r13
0x180016956  sub     rsp, 68h
0x18001695a  mov     r13, rdx
0x18001695d  lea     r8, [rax+8]; struct ICachedPrivateProfile **
0x180016961  xor     edi, edi
0x180016963  xor     edx, edx; bool
0x180016965  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x180016969  mov     [rax+8], rdi
0x18001696d  call    ?_GetCachedProfile@CThemeFile@@AEAAJ_NPEAPEAUICachedPrivateProfile@@@Z; CThemeFile::_GetCachedProfile(bool,ICachedPrivateProfile * *)
0x180016972  test    eax, eax
0x180016974  js      loc_180016B7E
0x18001697a  mov     [rsp+78h+var_28], r12
0x18001697f  lea     rdx, [rsp+78h+pv]
0x180016987  mov     r12, [rsp+78h+arg_0]
0x18001698f  mov     [rsp+78h+pv], rdi
0x180016997  mov     rcx, r12
0x18001699a  mov     [rsp+78h+var_30], r14
0x18001699f  mov     rax, [r12]
0x1800169a3  mov     rax, [rax+40h]
0x1800169a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169ac  mov     r14d, eax
0x1800169af  test    eax, eax
0x1800169b1  js      loc_180016B61
0x1800169b7  mov     ecx, 10h; cItemGrow
0x1800169bc  mov     [rsp+78h+arg_8], rbx
0x1800169c4  call    cs:g_pfn_DPA_Create
0x1800169ca  mov     [rsp+78h+arg_0], rax
0x1800169d2  mov     rbx, rax
0x1800169d5  test    rax, rax
0x1800169d8  jz      loc_180016B9A
0x1800169de  mov     [rsp+78h+var_38], r15
0x1800169e3  mov     r14d, edi
0x1800169e6  mov     rdi, [rsp+78h+pv]
0x1800169ee  mov     r15d, 1
0x1800169f4  mov     [rsp+78h+var_18], rbp
0x1800169f9  mov     [rsp+78h+var_20], rsi
0x1800169fe  cmp     [rdi], r14w
0x180016a02  jz      short loc_180016A44
0x180016a04  test    r14d, r14d
0x180016a07  js      loc_180016B1E
0x180016a0d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180016a14  cmp     word ptr [rdi+rax*2+2], 0
0x180016a1a  lea     rax, [rax+1]
0x180016a1e  jnz     short loc_180016A14
0x180016a20  lea     ebp, [rax+1]
0x180016a23  movsxd  rsi, ebp
0x180016a26  cmp     rsi, 17h
0x180016a2a  jnb     loc_180016BA2
0x180016a30  cmp     word ptr [rdi+rsi*2], 0
0x180016a35  lea     rdi, [rdi+rsi*2]
0x180016a39  jnz     short loc_180016A04
0x180016a3b  test    r14d, r14d
0x180016a3e  js      loc_180016B1E
0x180016a44  movsxd  rcx, r15d
0x180016a47  add     rcx, rcx; cb
0x180016a4a  call    cs:__imp_CoTaskMemAlloc
0x180016a50  xor     r14d, r14d
0x180016a53  mov     ecx, 8007000Eh
0x180016a58  test    rax, rax
0x180016a5b  mov     [r13+0], rax
0x180016a5f  mov     ebp, [rbx]
0x180016a61  mov     rsi, rax
0x180016a64  cmovz   r14d, ecx
0x180016a68  test    ebp, ebp
0x180016a6a  jle     loc_180016B14
0x180016a70  xor     edi, edi
0x180016a72  test    r14d, r14d
0x180016a75  js      loc_180016B86
0x180016a7b  mov     edx, edi; i
0x180016a7d  mov     rcx, rbx; hdpa
0x180016a80  call    cs:g_pfn_DPA_GetPtr
0x180016a86  mov     rcx, rax
0x180016a89  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180016a90  cmp     word ptr [rcx+rax*2+2], 0
0x180016a96  lea     rax, [rax+1]
0x180016a9a  jnz     short loc_180016A90
0x180016a9c  movsxd  r8, r15d
0x180016a9f  lea     r10d, [rax+1]
0x180016aa3  test    r15d, r15d
0x180016aa6  jz      loc_180016C00
0x180016aac  cmp     r8, 7FFFFFFFh
0x180016ab3  ja      loc_180016BF8
0x180016ab9  mov     edx, 7FFFFFFEh
0x180016abe  mov     r9, rsi
0x180016ac1  test    rdx, rdx
0x180016ac4  jz      short loc_180016AE3
0x180016ac6  movzx   eax, word ptr [rcx]
0x180016ac9  test    ax, ax
0x180016acc  jz      short loc_180016AE3
0x180016ace  mov     [r9], ax
0x180016ad2  add     rcx, 2
0x180016ad6  add     r9, 2
0x180016ada  dec     rdx
0x180016add  sub     r8, 1
0x180016ae1  jnz     short loc_180016AC1
0x180016ae3  test    r8, r8
0x180016ae6  lea     rcx, [r9-2]
0x180016aea  mov     r14d, 8007007Ah
0x180016af0  cmovnz  rcx, r9
0x180016af4  xor     eax, eax
0x180016af6  test    r8, r8
0x180016af9  cmovnz  r14d, eax
0x180016afd  mov     [rcx], ax
0x180016b00  movsxd  rax, r10d
0x180016b03  sub     r15d, r10d
0x180016b06  inc     edi
0x180016b08  lea     rsi, [rsi+rax*2]
0x180016b0c  cmp     edi, ebp
0x180016b0e  jl      loc_180016A72
0x180016b14  test    r14d, r14d
0x180016b17  js      short loc_180016B86
0x180016b19  xor     eax, eax
0x180016b1b  mov     [rsi], ax
0x180016b1e  lea     rcx, [rsp+78h+arg_0]
0x180016b26  call    ?Destroy@?$CDPA_Base@GV?$CTContainer_PolicyUnOwned@G@@@@QEAAHXZ; CDPA_Base<ushort,CTContainer_PolicyUnOwned<ushort>>::Destroy(void)
0x180016b2b  mov     rbx, [rsp+78h+arg_0]
0x180016b33  mov     r15, [rsp+78h+var_38]
0x180016b38  mov     rsi, [rsp+78h+var_20]
0x180016b3d  mov     rbp, [rsp+78h+var_18]
0x180016b42  mov     rcx, [rsp+78h+pv]; pv
0x180016b4a  call    cs:__imp_CoTaskMemFree
0x180016b50  test    rbx, rbx
0x180016b53  mov     rbx, [rsp+78h+arg_8]
0x180016b5b  jnz     loc_180016C19
0x180016b61  mov     rax, [r12]
0x180016b65  mov     rcx, r12
0x180016b68  mov     rax, [rax+10h]
0x180016b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b71  mov     r12, [rsp+78h+var_28]
0x180016b76  mov     eax, r14d
0x180016b79  mov     r14, [rsp+78h+var_30]
0x180016b7e  add     rsp, 68h
0x180016b82  pop     r13
0x180016b84  pop     rdi
0x180016b85  retn
0x180016b86  mov     rcx, [r13+0]; pv
0x180016b8a  call    cs:__imp_CoTaskMemFree
0x180016b90  mov     qword ptr [r13+0], 0
0x180016b98  jmp     short loc_180016B1E
0x180016b9a  mov     r14d, 8007000Eh
0x180016ba0  jmp     short loc_180016B42
0x180016ba2  mov     r9d, 16h; cchCount2
0x180016ba8  mov     [rsp+78h+bIgnoreCase], 1; int
0x180016bb0  mov     edx, r9d; cchCount1
0x180016bb3  lea     rcx, String1; "AppEvents\\Schemes\\Apps"
0x180016bba  mov     r8, rdi; lpString2
0x180016bbd  call    cs:__imp_CompareStringOrdinal
0x180016bc3  cmp     eax, 2
0x180016bc6  jnz     loc_180016A30
0x180016bcc  mov     rdx, rdi; int
0x180016bcf  mov     [rsp+78h+p], rdi; p
0x180016bd4  lea     rcx, [rsp+78h+arg_0]; int
0x180016bdc  add     r15d, ebp
0x180016bdf  call    ?SortedInsertPtr@?$CDPA@GV?$CTContainer_PolicyUnOwned@G@@@@QEAAHPEBGHP6AH00_J@Z1I0@Z; CDPA<ushort,CTContainer_PolicyUnOwned<ushort>>::SortedInsertPtr(ushort const *,int,int (*)(ushort const *,ushort const *,__int64),__int64,uint,ushort const *)
0x180016be4  xor     ecx, ecx
0x180016be6  mov     r14d, 80004005h
0x180016bec  cmp     eax, 0FFFFFFFFh
0x180016bef  cmovnz  r14d, ecx
0x180016bf3  jmp     loc_180016A30
0x180016bf8  mov     r14d, 80070057h
0x180016bfe  jmp     short loc_180016C0F
0x180016c00  mov     r14d, 80070057h
0x180016c06  test    r15d, r15d
0x180016c09  jz      loc_180016B00
0x180016c0f  xor     eax, eax
0x180016c11  mov     [rsi], ax
0x180016c14  jmp     loc_180016B00
0x180016c19  lea     rcx, [rsp+78h+arg_0]
0x180016c21  call    ?Destroy@?$CDPA_Base@GV?$CTContainer_PolicyUnOwned@G@@@@QEAAHXZ; CDPA_Base<ushort,CTContainer_PolicyUnOwned<ushort>>::Destroy(void)
0x180016c26  jmp     loc_180016B61
```
