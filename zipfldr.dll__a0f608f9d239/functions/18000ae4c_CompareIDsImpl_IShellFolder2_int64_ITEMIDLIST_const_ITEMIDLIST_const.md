# CompareIDsImpl(IShellFolder2 *,__int64,_ITEMIDLIST const *,_ITEMIDLIST const *)

- ea: `0x18000ae4c`
- end: `0x18000b0b3`
- name: `?CompareIDsImpl@@YAJPEAUIShellFolder2@@_JPEFBU_ITEMIDLIST@@2@Z`
- size: `615`
- prototype: `int(struct IShellFolder2 *, __int64, const struct _ITEMIDLIST *, const struct _ITEMIDLIST *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000cd20`

## callees

- `0x18000acfc`
- `0x18000ae4c`
- `0x18000d5e4`
- `0x18003326c`
- `0x180036f50`
- `0x180071010`

## import_xrefs

- `PROPSYS!VariantCompare` at `0x18000afee`
- `PROPSYS!VariantCompare` at `0x18000afee`
- `SHELL32!__imp_ILCloneFirst` at `0x18000aee1`
- `SHELL32!__imp_ILCloneFirst` at `0x18000aee1`
- `SHELL32!__imp_ILFree` at `0x18000b01c`
- `SHELL32!__imp_ILFree` at `0x18000b025`
- `SHELL32!__imp_ILFree` at `0x18000b01c`
- `SHELL32!__imp_ILFree` at `0x18000b025`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x18000af6f`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x18000afdc`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x18000af6f`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x18000afdc`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b055`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b055`
- `OLEAUT32!__imp_VariantInit` at `0x18000b08f`
- `OLEAUT32!__imp_VariantInit` at `0x18000b09e`
- `OLEAUT32!__imp_VariantInit` at `0x18000b08f`
- `OLEAUT32!__imp_VariantInit` at `0x18000b09e`
- `OLEAUT32!__imp_VariantClear` at `0x18000b009`
- `OLEAUT32!__imp_VariantClear` at `0x18000b013`
- `OLEAUT32!__imp_VariantClear` at `0x18000b009`
- `OLEAUT32!__imp_VariantClear` at `0x18000b013`

## pseudocode

```c
__int64 __fastcall CompareIDsImpl(
        struct IShellFolder2 *a1,
        __int64 a2,
        const struct _ITEMIDLIST *a3,
        struct _ITEMIDLIST *a4)
{
  signed int v7; // ebx
  _WORD *v9; // rcx
  ITEMIDLIST *v10; // r14
  const struct _ITEMIDLIST *v11; // r12
  ITEMIDLIST *v12; // r15
  _WORD *v13; // rcx
  struct IShellFolder2Vtbl *lpVtbl; // rax
  const WCHAR *v15; // rdx
  int v16; // ebx
  struct IShellFolder2Vtbl *v17; // rax
  const WCHAR *v18; // rdx
  int v19; // eax
  signed int v20; // eax
  struct _ITEMID_CHILD *v21; // [rsp+30h] [rbp-49h] BYREF
  __int64 v22; // [rsp+38h] [rbp-41h]
  __int128 v23; // [rsp+40h] [rbp-39h] BYREF
  int v24; // [rsp+50h] [rbp-29h]
  VARIANT var2; // [rsp+58h] [rbp-21h] BYREF
  VARIANT var1; // [rsp+70h] [rbp-9h] BYREF

  v22 = a2;
  v7 = -2147024809;
  if ( a3 && a4 && a3->mkid.cb && a4->mkid.cb )
  {
    if ( a3 == a4 )
      return 0;
    v9 = (USHORT *)((char *)&a3->mkid.cb + a3->mkid.cb);
    if ( v9 && *v9 )
    {
      v10 = ILCloneFirst(a3);
      v7 = v10 == 0 ? 0x8007000E : 0;
      if ( !v10 )
        return (unsigned int)v7;
      v11 = v10;
    }
    else
    {
      v10 = 0;
      v11 = a3;
    }
    v12 = 0;
    v21 = 0;
    if ( a4->mkid.cb && (v13 = (USHORT *)((char *)&a4->mkid.cb + a4->mkid.cb)) != 0 && *v13 )
    {
      v20 = SHILCloneFirst((const struct _ITEMIDLIST_RELATIVE *)a4, &v21);
      v12 = (ITEMIDLIST *)v21;
      v7 = v20;
    }
    else
    {
      v21 = (struct _ITEMID_CHILD *)a4;
      v7 = 0;
    }
    if ( v7 >= 0 )
    {
      v24 = 0;
      lpVtbl = a1->lpVtbl;
      v23 = 0;
      v7 = ((__int64 (__fastcall *)(struct IShellFolder2 *, _QWORD, __int128 *))lpVtbl->MapColumnToSCID)(
             a1,
             (unsigned __int16)v22,
             &v23);
      if ( v7 >= 0 )
      {
        memset(&var1, 0, sizeof(var1));
        v16 = 0;
        if ( IsAppCompatModeEnabled((LPCWSTR)0x19, v15) )
          v16 = SHCoInitialize();
        if ( ((int (__fastcall *)(struct IShellFolder2 *, const struct _ITEMIDLIST *, __int128 *, VARIANT *))a1->lpVtbl->GetDetailsEx)(
               a1,
               v11,
               &v23,
               &var1) < 0 )
          VariantInit(&var1);
        v17 = a1->lpVtbl;
        memset(&var2, 0, sizeof(var2));
        if ( ((int (__fastcall *)(struct IShellFolder2 *, struct _ITEMID_CHILD *, __int128 *, VARIANT *))v17->GetDetailsEx)(
               a1,
               v21,
               &v23,
               &var2) < 0 )
          VariantInit(&var2);
        if ( IsAppCompatModeEnabled((LPCWSTR)0x19, v18) && !v16 )
          CoUninitialize();
        v19 = VariantCompare(&var1, &var2);
        if ( v19 )
        {
          if ( v19 < 0 )
            v7 = 0xFFFF;
          else
            v7 = v19 > 0;
        }
        else
        {
          v7 = ILCompareRelIDs(a1, a3, a4, v22);
        }
        VariantClear(&var2);
        VariantClear(&var1);
      }
      ILFree(v12);
    }
    ILFree(v10);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000ae4c  push    rbp
0x18000ae4e  push    rbx
0x18000ae4f  push    rsi
0x18000ae50  push    rdi
0x18000ae51  push    r12
0x18000ae53  push    r13
0x18000ae55  push    r14
0x18000ae57  push    r15
0x18000ae59  lea     rbp, [rsp-1Fh]
0x18000ae5e  sub     rsp, 98h
0x18000ae65  mov     rax, cs:__security_cookie
0x18000ae6c  xor     rax, rsp
0x18000ae6f  mov     [rbp+57h+var_48], rax
0x18000ae73  mov     [rbp+57h+var_98], rdx
0x18000ae77  mov     rdi, r9
0x18000ae7a  xor     edx, edx
0x18000ae7c  mov     rsi, r8
0x18000ae7f  mov     r13, rcx
0x18000ae82  mov     ebx, 80070057h
0x18000ae87  test    r8, r8
0x18000ae8a  jnz     short loc_18000AEAE
0x18000ae8c  mov     eax, ebx
0x18000ae8e  mov     rcx, [rbp+57h+var_48]
0x18000ae92  xor     rcx, rsp; StackCookie
0x18000ae95  call    __security_check_cookie
0x18000ae9a  add     rsp, 98h
0x18000aea1  pop     r15
0x18000aea3  pop     r14
0x18000aea5  pop     r13
0x18000aea7  pop     r12
0x18000aea9  pop     rdi
0x18000aeaa  pop     rsi
0x18000aeab  pop     rbx
0x18000aeac  pop     rbp
0x18000aead  retn
0x18000aeae  test    rdi, rdi
0x18000aeb1  jz      short loc_18000AE8C
0x18000aeb3  cmp     [r8], dx
0x18000aeb7  jz      short loc_18000AE8C
0x18000aeb9  cmp     [r9], dx
0x18000aebd  jz      short loc_18000AE8C
0x18000aebf  cmp     rsi, rdi
0x18000aec2  jz      loc_18000B05D
0x18000aec8  movzx   ecx, word ptr [r8]
0x18000aecc  add     rcx, rsi
0x18000aecf  jz      loc_18000B030
0x18000aed5  cmp     [rcx], dx
0x18000aed8  jz      loc_18000B030
0x18000aede  mov     rcx, rsi; pidl
0x18000aee1  call    cs:__imp_ILCloneFirst
0x18000aee7  mov     r14, rax
0x18000aeea  neg     rax
0x18000aeed  sbb     ebx, ebx
0x18000aeef  xor     edx, edx
0x18000aef1  not     ebx
0x18000aef3  and     ebx, 8007000Eh
0x18000aef9  test    r14, r14
0x18000aefc  jz      short loc_18000AE8C
0x18000aefe  mov     r12, r14
0x18000af01  mov     r15, rdx
0x18000af04  mov     [rbp+57h+var_A0], rdx
0x18000af08  cmp     [rdi], dx
0x18000af0b  jz      short loc_18000AF1E
0x18000af0d  movzx   ecx, word ptr [rdi]
0x18000af10  add     rcx, rdi
0x18000af13  jz      short loc_18000AF1E
0x18000af15  cmp     [rcx], dx
0x18000af18  jnz     loc_18000B064
0x18000af1e  mov     [rbp+57h+var_A0], rdi
0x18000af22  mov     ebx, edx
0x18000af24  test    ebx, ebx
0x18000af26  js      loc_18000B022
0x18000af2c  movzx   edx, word ptr [rbp+57h+var_98]
0x18000af30  lea     r8, [rbp+57h+var_90]
0x18000af34  xor     eax, eax
0x18000af36  xorps   xmm0, xmm0
0x18000af39  mov     [rbp+57h+var_80], eax
0x18000af3c  mov     rcx, r13
0x18000af3f  mov     rax, [r13+0]
0x18000af43  movups  [rbp+57h+var_90], xmm0
0x18000af47  mov     rax, [rax+98h]
0x18000af4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af53  mov     ebx, eax
0x18000af55  test    eax, eax
0x18000af57  js      loc_18000B019
0x18000af5d  xor     eax, eax
0x18000af5f  xorps   xmm0, xmm0
0x18000af62  movups  xmmword ptr [rbp+57h+var1], xmm0
0x18000af66  mov     qword ptr [rbp+57h+var1+10h], rax
0x18000af6a  xor     ebx, ebx
0x18000af6c  lea     ecx, [rax+19h]; pszPath
0x18000af6f  call    cs:__imp_IsAppCompatModeEnabled
0x18000af75  test    eax, eax
0x18000af77  jnz     loc_18000B07F
0x18000af7d  mov     rcx, [r13+0]
0x18000af81  lea     r9, [rbp+57h+var1]
0x18000af85  lea     r8, [rbp+57h+var_90]
0x18000af89  mov     rdx, r12
0x18000af8c  mov     rax, [rcx+88h]
0x18000af93  mov     rcx, r13
0x18000af96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af9b  test    eax, eax
0x18000af9d  js      loc_18000B08B
0x18000afa3  mov     rdx, [rbp+57h+var_A0]
0x18000afa7  lea     r9, [rbp+57h+var2]
0x18000afab  xor     eax, eax
0x18000afad  lea     r8, [rbp+57h+var_90]
0x18000afb1  mov     qword ptr [rbp+57h+var2+10h], rax
0x18000afb5  xorps   xmm0, xmm0
0x18000afb8  mov     rax, [r13+0]
0x18000afbc  mov     rcx, r13
0x18000afbf  movups  xmmword ptr [rbp+57h+var2], xmm0
0x18000afc3  mov     rax, [rax+88h]
0x18000afca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afcf  test    eax, eax
0x18000afd1  js      loc_18000B09A
0x18000afd7  mov     ecx, 19h; pszPath
0x18000afdc  call    cs:__imp_IsAppCompatModeEnabled
0x18000afe2  test    eax, eax
0x18000afe4  jnz     short loc_18000B051
0x18000afe6  lea     rdx, [rbp+57h+var2]; var2
0x18000afea  lea     rcx, [rbp+57h+var1]; var1
0x18000afee  call    cs:__imp_VariantCompare
0x18000aff4  test    eax, eax
0x18000aff6  jz      short loc_18000B03B
0x18000aff8  js      loc_18000B0A9
0x18000affe  xor     ebx, ebx
0x18000b000  test    eax, eax
0x18000b002  setnle  bl
0x18000b005  lea     rcx, [rbp+57h+var2]; pvarg
0x18000b009  call    cs:__imp_VariantClear
0x18000b00f  lea     rcx, [rbp+57h+var1]; pvarg
0x18000b013  call    cs:__imp_VariantClear
0x18000b019  mov     rcx, r15; pidl
0x18000b01c  call    cs:__imp_ILFree
0x18000b022  mov     rcx, r14; pidl
0x18000b025  call    cs:__imp_ILFree
0x18000b02b  jmp     loc_18000AE8C
0x18000b030  mov     r14, rdx
0x18000b033  mov     r12, rsi
0x18000b036  jmp     loc_18000AF01
0x18000b03b  mov     r9, [rbp+57h+var_98]
0x18000b03f  mov     r8, rdi
0x18000b042  mov     rdx, rsi
0x18000b045  mov     rcx, r13
0x18000b048  call    ILCompareRelIDs
0x18000b04d  mov     ebx, eax
0x18000b04f  jmp     short loc_18000B005
0x18000b051  test    ebx, ebx
0x18000b053  jnz     short loc_18000AFE6
0x18000b055  call    cs:__imp_CoUninitialize
0x18000b05b  jmp     short loc_18000AFE6
0x18000b05d  mov     ebx, edx
0x18000b05f  jmp     loc_18000AE8C
0x18000b064  lea     rdx, [rbp+57h+var_A0]; struct _ITEMID_CHILD **
0x18000b068  mov     rcx, rdi; struct _ITEMIDLIST_RELATIVE *
0x18000b06b  call    ?SHILCloneFirst@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU_ITEMID_CHILD@@@Z; SHILCloneFirst(_ITEMIDLIST_RELATIVE const *,_ITEMID_CHILD * *)
0x18000b070  mov     r15, [rbp+57h+var_A0]
0x18000b074  mov     ebx, eax
0x18000b076  mov     [rbp+57h+var_A0], r15
0x18000b07a  jmp     loc_18000AF24
0x18000b07f  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x18000b084  mov     ebx, eax
0x18000b086  jmp     loc_18000AF7D
0x18000b08b  lea     rcx, [rbp+57h+var1]; pvarg
0x18000b08f  call    cs:__imp_VariantInit
0x18000b095  jmp     loc_18000AFA3
0x18000b09a  lea     rcx, [rbp+57h+var2]; pvarg
0x18000b09e  call    cs:__imp_VariantInit
0x18000b0a4  jmp     loc_18000AFD7
0x18000b0a9  mov     ebx, 0FFFFh
0x18000b0ae  jmp     loc_18000B005
```
