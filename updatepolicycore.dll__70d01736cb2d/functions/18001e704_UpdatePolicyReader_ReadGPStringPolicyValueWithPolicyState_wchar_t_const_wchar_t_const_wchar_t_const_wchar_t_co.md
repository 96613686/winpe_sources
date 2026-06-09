# UpdatePolicyReader::ReadGPStringPolicyValueWithPolicyState(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,tagUpdatePolicyValue_V1 *)

- ea: `0x18001e704`
- end: `0x18001e7de`
- name: `?ReadGPStringPolicyValueWithPolicyState@UpdatePolicyReader@@CAJPEB_W000PEAUtagUpdatePolicyValue_V1@@@Z`
- size: `218`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, struct tagUpdatePolicyValue_V1 *)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18001bf44`
- `0x18001c88c`
- `0x18001c9bc`
- `0x18001cbac`

## callees

- `0x18001e480`
- `0x18001e704`
- `0x18001f328`
- `0x18003002c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001e793`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e793`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::ReadGPStringPolicyValueWithPolicyState(
        const wchar_t *a1,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        struct tagUpdatePolicyValue_V1 *a5)
{
  _DWORD *v7; // rbx
  int v8; // esi
  int v9; // eax
  OLECHAR *v10; // rbx
  __int64 v11; // rax
  BSTR v12; // rax
  int v14; // [rsp+20h] [rbp-28h] BYREF
  OLECHAR *psz; // [rsp+28h] [rbp-20h] BYREF

  v14 = 0;
  v7 = (_DWORD *)((char *)a5 + 4);
  psz = 0;
  v8 = UpdatePolicyReader::ReadGPPolicyStateHelper(a1, a2, (struct tagUpdatePolicyValue_V1 *)((char *)a5 + 4), &v14);
  if ( v8 >= 0 )
  {
    if ( !v14 )
      *v7 = 0;
    if ( *v7 == 1 )
    {
      v9 = PolicyHelpers::ReadPolicyString(a3, a4, &psz);
      v10 = psz;
      v8 = v9;
      if ( v9 >= 0 )
      {
        if ( !psz )
          goto LABEL_11;
        v11 = -1;
        do
          ++v11;
        while ( psz[v11] );
        if ( v11 )
        {
LABEL_11:
          v12 = SysAllocString(psz);
          if ( v12 )
          {
            *((_QWORD *)a5 + 3) = v12;
            *((_WORD *)a5 + 8) = 8;
            *((_DWORD *)a5 + 2) = 1;
          }
          else
          {
            v8 = -2147024882;
          }
        }
        else
        {
          *((_DWORD *)a5 + 1) = 0;
        }
      }
      if ( v10 )
        operator delete(v10);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001e704  mov     rax, rsp
0x18001e707  mov     [rax+8], rbx
0x18001e70b  mov     [rax+10h], rbp
0x18001e70f  mov     [rax+18h], rsi
0x18001e713  push    rdi
0x18001e714  push    r14
0x18001e716  push    r15
0x18001e718  sub     rsp, 30h
0x18001e71c  mov     rdi, [rsp+48h+arg_20]
0x18001e721  mov     rbp, r9
0x18001e724  mov     r14, r8
0x18001e727  lea     r9, [rax-28h]; int *
0x18001e72b  xor     r15d, r15d
0x18001e72e  mov     [rax-28h], r15d
0x18001e732  lea     rbx, [rdi+4]
0x18001e736  mov     [rax-20h], r15
0x18001e73a  mov     r8, rbx; enum tagUpdatePolicyStatus *
0x18001e73d  call    ?ReadGPPolicyStateHelper@UpdatePolicyReader@@CAJPEB_W0PEAW4tagUpdatePolicyStatus@@PEAH@Z; UpdatePolicyReader::ReadGPPolicyStateHelper(wchar_t const *,wchar_t const *,tagUpdatePolicyStatus *,int *)
0x18001e742  mov     esi, eax
0x18001e744  test    eax, eax
0x18001e746  js      short loc_18001E7C3
0x18001e748  cmp     [rsp+48h+var_28], r15d
0x18001e74d  jnz     short loc_18001E752
0x18001e74f  mov     [rbx], r15d
0x18001e752  cmp     dword ptr [rbx], 1
0x18001e755  jnz     short loc_18001E7C3
0x18001e757  lea     r8, [rsp+48h+psz]; wchar_t **
0x18001e75c  mov     rdx, rbp; lpValue
0x18001e75f  mov     rcx, r14; lpSubKey
0x18001e762  call    ?ReadPolicyString@PolicyHelpers@@SAJPEB_W0PEAPEA_W@Z; PolicyHelpers::ReadPolicyString(wchar_t const *,wchar_t const *,wchar_t * *)
0x18001e767  mov     rbx, [rsp+48h+psz]
0x18001e76c  mov     esi, eax
0x18001e76e  test    eax, eax
0x18001e770  js      short loc_18001E7B6
0x18001e772  test    rbx, rbx
0x18001e775  jz      short loc_18001E790
0x18001e777  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e77b  inc     rax
0x18001e77e  cmp     [rbx+rax*2], r15w
0x18001e783  jnz     short loc_18001E77B
0x18001e785  test    rax, rax
0x18001e788  jnz     short loc_18001E790
0x18001e78a  mov     [rdi+4], r15d
0x18001e78e  jmp     short loc_18001E7B6
0x18001e790  mov     rcx, rbx; psz
0x18001e793  call    cs:__imp_SysAllocString
0x18001e799  test    rax, rax
0x18001e79c  jnz     short loc_18001E7A5
0x18001e79e  mov     esi, 8007000Eh
0x18001e7a3  jmp     short loc_18001E7B6
0x18001e7a5  mov     [rdi+18h], rax
0x18001e7a9  mov     word ptr [rdi+10h], 8
0x18001e7af  mov     dword ptr [rdi+8], 1
0x18001e7b6  test    rbx, rbx
0x18001e7b9  jz      short loc_18001E7C3
0x18001e7bb  mov     rcx, rbx; Block
0x18001e7be  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e7c3  mov     rbx, [rsp+48h+arg_0]
0x18001e7c8  mov     eax, esi
0x18001e7ca  mov     rsi, [rsp+48h+arg_10]
0x18001e7cf  mov     rbp, [rsp+48h+arg_8]
0x18001e7d4  add     rsp, 30h
0x18001e7d8  pop     r15
0x18001e7da  pop     r14
0x18001e7dc  pop     rdi
0x18001e7dd  retn
```
