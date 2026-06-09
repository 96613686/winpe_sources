# COfflineFolder::SetNameOf(HWND__ *,_ITEMIDLIST const *,ushort const *,ulong,_ITEMIDLIST * *)

- ea: `0x18000ad80`
- end: `0x18000af3a`
- name: `?SetNameOf@COfflineFolder@@UEAAJPEAUHWND__@@PEFBU_ITEMIDLIST@@PEBGKPEAPEFAU3@@Z`
- size: `442`
- prototype: `__int64 __fastcall(COfflineFolder *__hidden this, HWND, const struct _ITEMIDLIST *, const unsigned __int16 *, unsigned int, struct _ITEMIDLIST **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x180003950`
- `0x18000ad80`
- `0x18000e500`
- `0x18001c054`
- `0x18001c384`
- `0x18001c5c0`
- `0x18001d1f4`
- `0x18002924e`
- `0x180029280`
- `0x180029310`

## import_xrefs

- `SHLWAPI!PathRemoveBlanksW` at `0x18000ae16`
- `SHLWAPI!PathRemoveBlanksW` at `0x18000ae16`
- `ole32!CoTaskMemAlloc` at `0x18000aeaf`
- `ole32!CoTaskMemAlloc` at `0x18000aeaf`

## pseudocode

```c
__int64 __fastcall COfflineFolder::SetNameOf(
        COfflineFolder *this,
        HWND a2,
        const struct _ITEMIDLIST *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        struct _ITEMIDLIST **a6)
{
  unsigned int v8; // esi
  unsigned int v9; // eax
  USHORT v10; // r14
  struct _ITEMIDLIST *v11; // rax
  struct _ITEMIDLIST *v12; // rdi
  int v14; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v15; // [rsp+24h] [rbp-DCh]
  __int64 v16; // [rsp+2Ch] [rbp-D4h]
  unsigned __int16 v17[397]; // [rsp+1296h] [rbp+1196h] BYREF
  WCHAR pszPath[264]; // [rsp+15B0h] [rbp+14B0h] BYREF

  v15 = 0;
  v16 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a3->mkid.cb <= 0xE0u || *(_WORD *)a3->mkid.abID != 29701 )
    return 2147500037LL;
  StringCchCopyW(pszPath, 0x104u, a4);
  PathRemoveBlanksW(pszPath);
  if ( pszPath[0] )
  {
    memset_0(&v14, 0, 0x1590u);
    CopyToOOEBuf(a3[2].mkid.abID, &v14);
    StringCchCopyW(v17, 0x104u, pszPath);
    v14 = 32;
    v8 = SaveBufferChange((struct OOEBuf *)&v14, 0);
    if ( a6 )
    {
      v9 = BufferSize(&v14);
      if ( v9 <= 0xFFFF
        && (v10 = v9 + 224, (unsigned __int16)(v9 + 224) >= (unsigned __int16)v9)
        && (unsigned __int64)v10 + 2 >= v10 )
      {
        v11 = (struct _ITEMIDLIST *)CoTaskMemAlloc(v10 + 2LL);
        v12 = v11;
        if ( v11 )
        {
          memset_0(v11, 0, v10 + 2LL);
          v12->mkid.cb = v10;
          *(_WORD *)v12->mkid.abID = 29701;
          *a6 = v12;
          CopyToMyPooe(&v14, v12[2].mkid.abID);
        }
        else
        {
          *a6 = 0;
        }
      }
      else
      {
        *a6 = 0;
      }
    }
  }
  else
  {
    WCMessageBox(a2, v14);
    return (unsigned int)-2147467259;
  }
  return v8;
}

```

## disassembly

```asm
0x18000ad80  mov     [rsp-8+arg_0], rbx
0x18000ad85  push    rbp
0x18000ad86  push    rsi
0x18000ad87  push    rdi
0x18000ad88  push    r12
0x18000ad8a  push    r13
0x18000ad8c  push    r14
0x18000ad8e  push    r15
0x18000ad90  lea     rbp, [rsp-16D0h]
0x18000ad98  mov     eax, 17D0h
0x18000ad9d  call    _alloca_probe
0x18000ada2  sub     rsp, rax
0x18000ada5  mov     rax, cs:__security_cookie
0x18000adac  xor     rax, rsp
0x18000adaf  mov     [rbp+1700h+var_40], rax
0x18000adb6  mov     rbx, [rbp+1700h+arg_28]
0x18000adbd  xor     r12d, r12d
0x18000adc0  mov     [rsp+1800h+var_17DC], r12
0x18000adc5  mov     rdi, r8
0x18000adc8  mov     [rsp+1800h+var_17D4], r12
0x18000adcd  mov     rsi, rdx
0x18000add0  test    rbx, rbx
0x18000add3  jz      short loc_18000ADD8
0x18000add5  mov     [rbx], r12
0x18000add8  mov     r15d, 0E0h
0x18000adde  cmp     [r8], r15w
0x18000ade2  jbe     loc_18000AF0B
0x18000ade8  mov     r13d, 7405h
0x18000adee  cmp     [r8+2], r13w
0x18000adf3  jnz     loc_18000AF0B
0x18000adf9  lea     r14d, [r15+24h]
0x18000adfd  mov     r8, r9; unsigned __int16 *
0x18000ae00  mov     edx, r14d; unsigned __int64
0x18000ae03  lea     rcx, [rbp+1700h+pszPath]; unsigned __int16 *
0x18000ae0a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ae0f  lea     rcx, [rbp+1700h+pszPath]; pszPath
0x18000ae16  call    cs:__imp_PathRemoveBlanksW
0x18000ae1c  cmp     [rbp+1700h+pszPath], r12w
0x18000ae24  jz      loc_18000AEEB
0x18000ae2a  xor     edx, edx; Val
0x18000ae2c  lea     rcx, [rsp+1800h+var_17E0]; void *
0x18000ae31  mov     r8d, 1590h; Size
0x18000ae37  call    memset_0
0x18000ae3c  lea     rcx, [rdi+8]
0x18000ae40  lea     rdx, [rsp+1800h+var_17E0]
0x18000ae45  call    CopyToOOEBuf
0x18000ae4a  lea     r8, [rbp+1700h+pszPath]; unsigned __int16 *
0x18000ae51  mov     edx, r14d; unsigned __int64
0x18000ae54  lea     rcx, [rbp+1700h+var_56A]; unsigned __int16 *
0x18000ae5b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ae60  xor     edx, edx; int
0x18000ae62  mov     [rsp+1800h+var_17E0], 20h ; ' '
0x18000ae6a  lea     rcx, [rsp+1800h+var_17E0]; struct OOEBuf *
0x18000ae6f  call    SaveBufferChange
0x18000ae74  mov     esi, eax
0x18000ae76  test    rbx, rbx
0x18000ae79  jz      loc_18000AF07
0x18000ae7f  lea     rcx, [rsp+1800h+var_17E0]
0x18000ae84  call    BufferSize
0x18000ae89  cmp     eax, 0FFFFh
0x18000ae8e  ja      short loc_18000AEA7
0x18000ae90  lea     r14d, [r15+rax]
0x18000ae94  cmp     r14w, ax
0x18000ae98  jb      short loc_18000AEA7
0x18000ae9a  movzx   eax, r14w
0x18000ae9e  lea     r15, [rax+2]
0x18000aea2  cmp     r15, rax
0x18000aea5  jnb     short loc_18000AEAC
0x18000aea7  mov     [rbx], r12
0x18000aeaa  jmp     short loc_18000AF07
0x18000aeac  mov     rcx, r15; cb
0x18000aeaf  call    cs:__imp_CoTaskMemAlloc
0x18000aeb5  mov     rdi, rax
0x18000aeb8  test    rax, rax
0x18000aebb  jz      short loc_18000AEE6
0x18000aebd  mov     r8, r15; Size
0x18000aec0  xor     edx, edx; Val
0x18000aec2  mov     rcx, rax; void *
0x18000aec5  call    memset_0
0x18000aeca  mov     [rdi], r14w
0x18000aece  lea     rdx, [rdi+8]
0x18000aed2  mov     [rdi+2], r13w
0x18000aed7  lea     rcx, [rsp+1800h+var_17E0]
0x18000aedc  mov     [rbx], rdi
0x18000aedf  call    CopyToMyPooe
0x18000aee4  jmp     short loc_18000AF07
0x18000aee6  mov     [rbx], rdi
0x18000aee9  jmp     short loc_18000AF07
0x18000aeeb  mov     edx, 2037h
0x18000aef0  mov     r9d, 10h
0x18000aef6  mov     rcx, rsi; hWnd
0x18000aef9  lea     r8d, [rdx+1]
0x18000aefd  call    WCMessageBox
0x18000af02  mov     esi, 80004005h
0x18000af07  mov     eax, esi
0x18000af09  jmp     short loc_18000AF10
0x18000af0b  mov     eax, 80004005h
0x18000af10  mov     rcx, [rbp+1700h+var_40]
0x18000af17  xor     rcx, rsp; StackCookie
0x18000af1a  call    __security_check_cookie
0x18000af1f  mov     rbx, [rsp+1800h+arg_0]
0x18000af27  add     rsp, 17D0h
0x18000af2e  pop     r15
0x18000af30  pop     r14
0x18000af32  pop     r13
0x18000af34  pop     r12
0x18000af36  pop     rdi
0x18000af37  pop     rsi
0x18000af38  pop     rbp
0x18000af39  retn
```
