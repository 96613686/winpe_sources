# HyperVStorage::GetVariantValue(ushort const *,tagVARIANT &)

- ea: `0x1401c8ca0`
- end: `0x1401c8f5c`
- name: `?GetVariantValue@HyperVStorage@@QEBAJPEBGAEAUtagVARIANT@@@Z`
- size: `700`
- prototype: `int(HyperVStorage *__hidden this, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1401ea480`

## callees

- `0x140036db4`
- `0x140039d68`
- `0x14003a600`
- `0x1400b9bc4`
- `0x1400f560c`
- `0x140132960`
- `0x14013361c`
- `0x1401c8ca0`
- `0x1401d54d4`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1401c8cf1`
- `OLEAUT32!__imp_VariantInit` at `0x1401c8cf1`
- `OLEAUT32!__imp_VariantClear` at `0x1401c8f27`
- `OLEAUT32!__imp_VariantClear` at `0x1401c8f27`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401c8e16`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401c8e16`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401c8f14`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401c8f14`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1401c8e46`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1401c8e46`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1401c8de4`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1401c8de4`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall HyperVStorage::GetVariantValue(
        HyperVStorage *this,
        const unsigned __int16 *a2,
        struct tagVARIANT *a3)
{
  HyperVStorageKeyTableEntry *v7; // r13
  unsigned int v8; // edi
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rsi
  HyperVStorageKeyTableEntry *v10; // rcx
  ULONG ValueSizeInBytes; // eax
  SAFEARRAY *Vector; // rcx
  HyperVStorageKeyTableEntry *v13; // rcx
  UINT FileObjectDataSizeInBytes; // eax
  BSTR v15; // rax
  __int64 v16; // r9
  int v17; // edi
  __int16 v18; // ax
  int v19; // [rsp+40h] [rbp-68h] BYREF
  __int64 v20; // [rsp+48h] [rbp-60h] BYREF
  HyperVStorage *v21; // [rsp+50h] [rbp-58h]
  struct tagVARIANT *v22; // [rsp+58h] [rbp-50h]
  struct tagVARIANT *v23; // [rsp+60h] [rbp-48h]
  void *ppvData; // [rsp+68h] [rbp-40h] BYREF
  int v25; // [rsp+70h] [rbp-38h] BYREF

  v21 = this;
  v23 = a3;
  v22 = a3;
  if ( !a2 )
    HvsThrowHResultError(-2147024809);
  VariantInit(a3);
  v20 = 0;
  if ( !(unsigned int)HyperVStorage::GetOrCreateNode(this, a2, 0, &v20, 0) )
    return 2147942402LL;
  v25 = 0;
  ppvData = 0;
  v7 = *(HyperVStorageKeyTableEntry **)(v20 + 40);
  LODWORD(v20) = **(unsigned __int8 **)v7;
  switch ( (_DWORD)v20 )
  {
    case 3:
      a3->vt = 20;
      break;
    case 4:
      a3->vt = 21;
      break;
    case 5:
      a3->vt = 5;
      break;
    default:
      switch ( (_DWORD)v20 )
      {
        case 6:
          if ( (unsigned int)HyperVStorageKeyTableEntry::PointsToFileObject(v7) )
            FileObjectDataSizeInBytes = HyperVStorageKeyTableEntry::GetFileObjectDataSizeInBytes(v13);
          else
            FileObjectDataSizeInBytes = HyperVStorageKeyTableEntry::GetValueSizeInBytes(v13);
          v8 = FileObjectDataSizeInBytes;
          v19 = FileObjectDataSizeInBytes;
          v15 = SysAllocStringByteLen(0, FileObjectDataSizeInBytes);
          p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a3->llVal;
          a3->llVal = (LONGLONG)v15;
          ppvData = v15;
          memset_0(v15, 0, v8 + 2LL);
          a3->vt = 8;
          break;
        case 7:
          if ( (unsigned int)HyperVStorageKeyTableEntry::PointsToFileObject(v7) )
            ValueSizeInBytes = HyperVStorageKeyTableEntry::GetFileObjectDataSizeInBytes(v10);
          else
            ValueSizeInBytes = HyperVStorageKeyTableEntry::GetValueSizeInBytes(v10);
          v8 = ValueSizeInBytes;
          v19 = ValueSizeInBytes;
          Vector = SafeArrayCreateVector(0x11u, 0, ValueSizeInBytes);
          p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a3->llVal;
          a3->llVal = (LONGLONG)Vector;
          if ( !Vector )
            HvsThrowHResultError(-2147024882);
          a3->vt = 8209;
          SafeArrayAccessData(Vector, &ppvData);
          break;
        case 8:
          ppvData = &v25;
          v8 = 4;
          v19 = 4;
          a3->vt = 11;
          p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a3->llVal;
          break;
        default:
          HvsThrowHResultError(-2147024809);
      }
      goto LABEL_27;
  }
  p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a3->llVal;
  ppvData = &a3->decVal.8;
  v8 = 8;
  v19 = 8;
LABEL_27:
  v16 = v8;
  v17 = v20;
  HyperVStorage::GetValueInternal(v21, v7, (unsigned int)v20, v16, ppvData, &v19);
  if ( v17 == 8 )
  {
    if ( v25 )
      v18 = -1;
    else
      v18 = 0;
    p_llVal->iVal = v18;
  }
  if ( a3->vt == 8209 )
    SafeArrayUnaccessData(p_llVal->parray);
  return 0;
}

```

## disassembly

```asm
0x1401c8ca0  mov     [rsp+arg_18], rsi
0x1401c8ca5  push    rdi
0x1401c8ca6  push    r12
0x1401c8ca8  push    r13
0x1401c8caa  push    r14
0x1401c8cac  push    r15
0x1401c8cae  sub     rsp, 80h
0x1401c8cb5  mov     rax, cs:__security_cookie
0x1401c8cbc  xor     rax, rsp
0x1401c8cbf  mov     [rsp+0A8h+var_30], rax
0x1401c8cc4  mov     r12, r8
0x1401c8cc7  mov     rdi, rdx
0x1401c8cca  mov     rsi, rcx
0x1401c8ccd  mov     [rsp+0A8h+var_58], rcx
0x1401c8cd2  mov     [rsp+0A8h+var_48], r8
0x1401c8cd7  mov     r14, r8
0x1401c8cda  mov     [rsp+0A8h+var_50], r8
0x1401c8cdf  test    rdx, rdx
0x1401c8ce2  jnz     short loc_1401C8CEE
0x1401c8ce4  mov     ecx, 80070057h; int
0x1401c8ce9  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401c8cee  mov     rcx, r12; pvarg
0x1401c8cf1  call    cs:__imp_VariantInit
0x1401c8cf8  nop     dword ptr [rax+rax+00h]
0x1401c8cfd  mov     [rsp+0A8h+var_60], 0
0x1401c8d06  mov     [rsp+0A8h+var_78], 0
0x1401c8d0b  mov     [rsp+0A8h+var_88], 0
0x1401c8d14  lea     r9, [rsp+0A8h+var_60]
0x1401c8d19  xor     r8d, r8d
0x1401c8d1c  mov     rdx, rdi
0x1401c8d1f  mov     rcx, rsi
0x1401c8d22  call    ?GetOrCreateNode@HyperVStorage@@IEAAHPEBGPEAVHyperVStorageOperation@@AEAV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBDPEAVHyperVStorageKeyTableEntry@@@std@@@std@@@std@@@std@@PEAPEAVHyperVStorageKeyTableEntry@@IE@Z; HyperVStorage::GetOrCreateNode(ushort const *,HyperVStorageOperation *,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<char const * const,HyperVStorageKeyTableEntry *>>>> &,HyperVStorageKeyTableEntry * *,uint,uchar)
0x1401c8d27  test    eax, eax
0x1401c8d29  jnz     short loc_1401C8D35
0x1401c8d2b  mov     eax, 80070002h
0x1401c8d30  jmp     loc_1401C8F35
0x1401c8d35  mov     [rsp+0A8h+var_38], 0
0x1401c8d3d  mov     [rsp+0A8h+ppvData], 0
0x1401c8d46  mov     rax, [rsp+0A8h+var_60]
0x1401c8d4b  mov     r13, [rax+28h]
0x1401c8d4f  mov     rax, [r13+0]
0x1401c8d53  movzx   ecx, byte ptr [rax]
0x1401c8d56  mov     dword ptr [rsp+0A8h+var_60], ecx
0x1401c8d5a  sub     ecx, 3
0x1401c8d5d  jz      loc_1401C8E8F
0x1401c8d63  sub     ecx, 1
0x1401c8d66  jz      loc_1401C8E86
0x1401c8d6c  sub     ecx, 1
0x1401c8d6f  jz      loc_1401C8E7D
0x1401c8d75  sub     ecx, 1
0x1401c8d78  jz      loc_1401C8E24
0x1401c8d7e  sub     ecx, 1
0x1401c8d81  jz      short loc_1401C8DBC
0x1401c8d83  cmp     ecx, 1
0x1401c8d86  jz      short loc_1401C8D92
0x1401c8d88  mov     ecx, 80070057h; int
0x1401c8d8d  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401c8d92  lea     rax, [rsp+0A8h+var_38]
0x1401c8d97  mov     [rsp+0A8h+ppvData], rax
0x1401c8d9c  mov     edi, 4
0x1401c8da1  mov     [rsp+0A8h+var_68], edi
0x1401c8da5  mov     word ptr [r12], 0Bh
0x1401c8dac  lea     rsi, [r12+8]
0x1401c8db1  mov     r15d, 8
0x1401c8db7  jmp     loc_1401C8EAE
0x1401c8dbc  mov     rcx, r13; this
0x1401c8dbf  call    ?PointsToFileObject@HyperVStorageKeyTableEntry@@QEBAHXZ; HyperVStorageKeyTableEntry::PointsToFileObject(void)
0x1401c8dc4  test    eax, eax
0x1401c8dc6  jnz     short loc_1401C8DCF
0x1401c8dc8  call    ?GetValueSizeInBytes@HyperVStorageKeyTableEntry@@QEBAIXZ; HyperVStorageKeyTableEntry::GetValueSizeInBytes(void)
0x1401c8dcd  jmp     short loc_1401C8DD4
0x1401c8dcf  call    ?GetFileObjectDataSizeInBytes@HyperVStorageKeyTableEntry@@QEBAIXZ; HyperVStorageKeyTableEntry::GetFileObjectDataSizeInBytes(void)
0x1401c8dd4  mov     edi, eax
0x1401c8dd6  mov     [rsp+0A8h+var_68], eax
0x1401c8dda  mov     ecx, 11h; vt
0x1401c8ddf  mov     r8d, eax; cElements
0x1401c8de2  xor     edx, edx; lLbound
0x1401c8de4  call    cs:__imp_SafeArrayCreateVector
0x1401c8deb  nop     dword ptr [rax+rax+00h]
0x1401c8df0  mov     rcx, rax; psa
0x1401c8df3  lea     rsi, [r12+8]
0x1401c8df8  mov     [rsi], rax
0x1401c8dfb  test    rax, rax
0x1401c8dfe  jnz     short loc_1401C8E0A
0x1401c8e00  mov     ecx, 8007000Eh; int
0x1401c8e05  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401c8e0a  mov     word ptr [r12], 2011h
0x1401c8e11  lea     rdx, [rsp+0A8h+ppvData]; ppvData
0x1401c8e16  call    cs:__imp_SafeArrayAccessData
0x1401c8e1d  nop     dword ptr [rax+rax+00h]
0x1401c8e22  jmp     short loc_1401C8DB1
0x1401c8e24  mov     rcx, r13; this
0x1401c8e27  call    ?PointsToFileObject@HyperVStorageKeyTableEntry@@QEBAHXZ; HyperVStorageKeyTableEntry::PointsToFileObject(void)
0x1401c8e2c  test    eax, eax
0x1401c8e2e  jnz     short loc_1401C8E37
0x1401c8e30  call    ?GetValueSizeInBytes@HyperVStorageKeyTableEntry@@QEBAIXZ; HyperVStorageKeyTableEntry::GetValueSizeInBytes(void)
0x1401c8e35  jmp     short loc_1401C8E3C
0x1401c8e37  call    ?GetFileObjectDataSizeInBytes@HyperVStorageKeyTableEntry@@QEBAIXZ; HyperVStorageKeyTableEntry::GetFileObjectDataSizeInBytes(void)
0x1401c8e3c  mov     edi, eax
0x1401c8e3e  mov     [rsp+0A8h+var_68], eax
0x1401c8e42  mov     edx, eax; len
0x1401c8e44  xor     ecx, ecx; psz
0x1401c8e46  call    cs:__imp_SysAllocStringByteLen
0x1401c8e4d  nop     dword ptr [rax+rax+00h]
0x1401c8e52  lea     rsi, [r12+8]
0x1401c8e57  mov     [rsi], rax
0x1401c8e5a  mov     [rsp+0A8h+ppvData], rax
0x1401c8e5f  mov     r8d, edi
0x1401c8e62  add     r8, 2; Size
0x1401c8e66  xor     edx, edx; Val
0x1401c8e68  mov     rcx, rax; void *
0x1401c8e6b  call    memset_0
0x1401c8e70  mov     r15d, 8
0x1401c8e76  mov     [r12], r15w
0x1401c8e7b  jmp     short loc_1401C8EAE
0x1401c8e7d  mov     word ptr [r12], 5
0x1401c8e84  jmp     short loc_1401C8E96
0x1401c8e86  mov     word ptr [r12], 15h
0x1401c8e8d  jmp     short loc_1401C8E96
0x1401c8e8f  mov     word ptr [r12], 14h
0x1401c8e96  lea     rsi, [r12+8]
0x1401c8e9b  mov     r15d, 8
0x1401c8ea1  mov     [rsp+0A8h+ppvData], rsi
0x1401c8ea6  mov     edi, r15d
0x1401c8ea9  mov     [rsp+0A8h+var_68], r15d
0x1401c8eae  lea     rax, [rsp+0A8h+var_68]
0x1401c8eb3  mov     [rsp+0A8h+var_80], rax
0x1401c8eb8  mov     rax, [rsp+0A8h+ppvData]
0x1401c8ebd  mov     [rsp+0A8h+var_88], rax
0x1401c8ec2  mov     r9d, edi
0x1401c8ec5  mov     edi, dword ptr [rsp+0A8h+var_60]
0x1401c8ec9  mov     r8d, edi
0x1401c8ecc  mov     rdx, r13
0x1401c8ecf  mov     rcx, [rsp+0A8h+var_58]
0x1401c8ed4  call    ?GetValueInternal@HyperVStorage@@IEBAXPEBVHyperVStorageKeyTableEntry@@W4HyperVStorageKeyType@@IPEAEAEAI@Z; HyperVStorage::GetValueInternal(HyperVStorageKeyTableEntry const *,HyperVStorageKeyType,uint,uchar *,uint &)
0x1401c8ed9  cmp     edi, r15d
0x1401c8edc  jnz     short loc_1401C8EEF
0x1401c8ede  cmp     [rsp+0A8h+var_38], 0
0x1401c8ee3  jz      short loc_1401C8EEA
0x1401c8ee5  or      eax, 0FFFFFFFFh
0x1401c8ee8  jmp     short loc_1401C8EEC
0x1401c8eea  xor     eax, eax
0x1401c8eec  mov     [rsi], ax
0x1401c8eef  xor     edi, edi
0x1401c8ef1  jmp     short loc_1401C8F05
0x1401c8ef3  mov     r14, [rsp+0A8h+var_50]
0x1401c8ef8  lea     rsi, [r14+8]
0x1401c8efc  mov     edi, dword ptr [rsp+0A8h+var_60]
0x1401c8f00  mov     r12, [rsp+0A8h+var_48]
0x1401c8f05  mov     eax, 2011h
0x1401c8f0a  cmp     [r12], ax
0x1401c8f0f  jnz     short loc_1401C8F20
0x1401c8f11  mov     rcx, [rsi]; psa
0x1401c8f14  call    cs:__imp_SafeArrayUnaccessData
0x1401c8f1b  nop     dword ptr [rax+rax+00h]
0x1401c8f20  test    edi, edi
0x1401c8f22  jns     short loc_1401C8F33
0x1401c8f24  mov     rcx, r14; pvarg
0x1401c8f27  call    cs:__imp_VariantClear
0x1401c8f2e  nop     dword ptr [rax+rax+00h]
0x1401c8f33  mov     eax, edi
0x1401c8f35  mov     rcx, [rsp+0A8h+var_30]
0x1401c8f3a  xor     rcx, rsp; StackCookie
0x1401c8f3d  call    __security_check_cookie
0x1401c8f42  mov     rsi, [rsp+0A8h+arg_18]
0x1401c8f4a  add     rsp, 80h
0x1401c8f51  pop     r15
0x1401c8f53  pop     r14
0x1401c8f55  pop     r13
0x1401c8f57  pop     r12
0x1401c8f59  pop     rdi
0x1401c8f5a  retn
```
