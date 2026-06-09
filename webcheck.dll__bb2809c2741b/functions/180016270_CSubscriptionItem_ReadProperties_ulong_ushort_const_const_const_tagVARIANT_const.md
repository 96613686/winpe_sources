# CSubscriptionItem::ReadProperties(ulong,ushort const * const * const,tagVARIANT * const)

- ea: `0x180016270`
- end: `0x18001639a`
- name: `?ReadProperties@CSubscriptionItem@@UEAAJKQEBQEBGQEAUtagVARIANT@@@Z`
- size: `298`
- prototype: `__int64 __fastcall(CSubscriptionItem *__hidden this, unsigned int, const unsigned __int16 *const *const, struct tagVARIANT *const)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180016270`
- `0x1800163a0`
- `0x180016570`
- `0x180019948`
- `0x18001ba40`

## import_xrefs

- `SHLWAPI!StrCmpIW` at `0x18001630b`
- `SHLWAPI!StrCmpIW` at `0x18001630b`
- `ADVAPI32!RegCloseKey` at `0x180016373`
- `ADVAPI32!RegCloseKey` at `0x180016373`

## pseudocode

```c
__int64 __fastcall CSubscriptionItem::ReadProperties(
        CSubscriptionItem *this,
        unsigned int a2,
        const unsigned __int16 *const *const a3,
        struct tagVARIANT *const a4)
{
  unsigned int v8; // ebx
  __int64 i; // rdi
  const WCHAR *v10; // rcx
  unsigned __int8 *v12; // [rsp+30h] [rbp-58h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-50h] BYREF
  unsigned int v14; // [rsp+98h] [rbp+10h] BYREF

  if ( !a2 || !a3 || !a4 )
    return 2147942487LL;
  hKey = 0;
  if ( OpenItemKey((const struct _GUID *)((char *)this + 12), 0, 0x20019u, &hKey) )
  {
    v8 = 0;
    for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
    {
      if ( v8 )
        break;
      v10 = a3[i];
      v12 = 0;
      v14 = 0;
      if ( StrCmpIW(v10, L"Password") && CSubscriptionItem::ReadWithAlloc(this, hKey, a3[i], &v12, &v14) >= 0 )
      {
        v8 = SignatureBlobToVariant(v12, v14, &a4[i]);
        operator delete(v12);
      }
      else
      {
        a4[i].vt = 0;
      }
    }
    RegCloseKey(hKey);
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return v8;
}

```

## disassembly

```asm
0x180016270  push    rbx
0x180016272  push    rbp
0x180016273  push    rsi
0x180016274  push    rdi
0x180016275  push    r12
0x180016277  push    r13
0x180016279  push    r14
0x18001627b  push    r15
0x18001627d  sub     rsp, 48h
0x180016281  mov     rbp, r9
0x180016284  mov     r15, r8
0x180016287  mov     esi, edx
0x180016289  mov     r13, rcx
0x18001628c  test    edx, edx
0x18001628e  jz      loc_180016384
0x180016294  test    r8, r8
0x180016297  jz      loc_180016384
0x18001629d  test    r9, r9
0x1800162a0  jz      loc_180016384
0x1800162a6  add     rcx, 0Ch; struct _GUID *
0x1800162aa  mov     [rsp+88h+hKey], 0
0x1800162b3  lea     r9, [rsp+88h+hKey]; HKEY *
0x1800162b8  xor     edx, edx; int
0x1800162ba  mov     r8d, 20019h; unsigned int
0x1800162c0  call    ?OpenItemKey@@YAHPEBU_GUID@@HKPEAPEAUHKEY__@@@Z; OpenItemKey(_GUID const *,int,ulong,HKEY__ * *)
0x1800162c5  test    eax, eax
0x1800162c7  jz      loc_18001637B
0x1800162cd  xor     ebx, ebx
0x1800162cf  xor     edi, edi
0x1800162d1  test    esi, esi
0x1800162d3  jz      loc_18001636E
0x1800162d9  test    ebx, ebx
0x1800162db  jnz     loc_18001636E
0x1800162e1  mov     rcx, [r15+rdi*8]; psz1
0x1800162e5  lea     rax, [rdi+rdi*2]
0x1800162e9  lea     r14, ds:0[rax*8]
0x1800162f1  mov     [rsp+88h+var_58], 0
0x1800162fa  lea     rdx, ?c_szPropPassword@@3QBGB; "Password"
0x180016301  mov     [rsp+88h+arg_8], ebx
0x180016308  add     r14, rbp
0x18001630b  call    cs:__imp_StrCmpIW
0x180016311  test    eax, eax
0x180016313  jz      short loc_18001635E
0x180016315  mov     r8, [r15+rdi*8]; unsigned __int16 *
0x180016319  lea     rax, [rsp+88h+arg_8]
0x180016321  mov     rdx, [rsp+88h+hKey]; HKEY
0x180016326  lea     r9, [rsp+88h+var_58]; unsigned __int8 **
0x18001632b  mov     rcx, r13; this
0x18001632e  mov     [rsp+88h+var_68], rax; unsigned int *
0x180016333  call    ?ReadWithAlloc@CSubscriptionItem@@QEAAJPEAUHKEY__@@PEBGPEAPEAEPEAK@Z; CSubscriptionItem::ReadWithAlloc(HKEY__ *,ushort const *,uchar * *,ulong *)
0x180016338  test    eax, eax
0x18001633a  js      short loc_18001635E
0x18001633c  mov     edx, [rsp+88h+arg_8]; unsigned int
0x180016343  mov     r8, r14; struct tagVARIANT *
0x180016346  mov     rcx, [rsp+88h+var_58]; unsigned __int8 *
0x18001634b  call    ?SignatureBlobToVariant@@YAJPEAEKPEAUtagVARIANT@@@Z; SignatureBlobToVariant(uchar *,ulong,tagVARIANT *)
0x180016350  mov     rcx, [rsp+88h+var_58]; lpMem
0x180016355  mov     ebx, eax
0x180016357  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001635c  jmp     short loc_180016364
0x18001635e  xor     eax, eax
0x180016360  mov     [r14], ax
0x180016364  inc     edi
0x180016366  cmp     edi, esi
0x180016368  jb      loc_1800162D9
0x18001636e  mov     rcx, [rsp+88h+hKey]; hKey
0x180016373  call    cs:__imp_RegCloseKey
0x180016379  jmp     short loc_180016380
0x18001637b  mov     ebx, 80004005h
0x180016380  mov     eax, ebx
0x180016382  jmp     short loc_180016389
0x180016384  mov     eax, 80070057h
0x180016389  add     rsp, 48h
0x18001638d  pop     r15
0x18001638f  pop     r14
0x180016391  pop     r13
0x180016393  pop     r12
0x180016395  pop     rdi
0x180016396  pop     rsi
0x180016397  pop     rbp
0x180016398  pop     rbx
0x180016399  retn
```
