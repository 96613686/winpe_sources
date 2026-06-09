# HyperVStorage::GetVariantValue(ushort const *,tagVARIANT &)

- ea: `0x140274d60`
- end: `0x14027501c`
- name: `?GetVariantValue@HyperVStorage@@QEBAJPEBGAEAUtagVARIANT@@@Z`
- size: `700`
- prototype: `int(HyperVStorage *__hidden this, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140243d00`

## callees

- `0x14003b67c`
- `0x14003cce8`
- `0x14003d82c`
- `0x14003e3d8`
- `0x1400e07d0`
- `0x140106694`
- `0x1401332f0`
- `0x140134048`
- `0x140274d60`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x140274db1`
- `OLEAUT32!__imp_VariantInit` at `0x140274db1`
- `OLEAUT32!__imp_VariantClear` at `0x140274fe7`
- `OLEAUT32!__imp_VariantClear` at `0x140274fe7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140274ed6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140274ed6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140274fd4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140274fd4`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140274f06`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140274f06`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x140274ea4`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x140274ea4`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall HyperVStorage::GetVariantValue(
        HyperVStorage *this,
        const unsigned __int16 *a2,
        struct tagVARIANT *a3)
{
  int v4; // edi
  int v5; // esi
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

  v4 = (int)a2;
  v5 = (int)this;
  v21 = this;
  v23 = a3;
  v22 = a3;
  if ( !a2 )
    HvsThrowHResultError(-2147024809);
  VariantInit(a3);
  v20 = 0;
  if ( !(unsigned int)HyperVStorage::GetOrCreateNode(v5, v4, 0, (unsigned int)&v20, 0) )
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
0x140274d60  mov     [rsp+arg_18], rsi
0x140274d65  push    rdi
0x140274d66  push    r12
0x140274d68  push    r13
0x140274d6a  push    r14
0x140274d6c  push    r15
0x140274d6e  sub     rsp, 80h
0x140274d75  mov     rax, cs:__security_cookie
0x140274d7c  xor     rax, rsp
0x140274d7f  mov     [rsp+0A8h+var_30], rax
0x140274d84  mov     r12, r8
0x140274d87  mov     rdi, rdx
0x140274d8a  mov     rsi, rcx
0x140274d8d  mov     [rsp+0A8h+var_58], rcx
0x140274d92  mov     [rsp+0A8h+var_48], r8
0x140274d97  mov     r14, r8
0x140274d9a  mov     [rsp+0A8h+var_50], r8
0x140274d9f  test    rdx, rdx
0x140274da2  jnz     short loc_140274DAE
0x140274da4  mov     ecx, 80070057h; int
0x140274da9  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x140274dae  mov     rcx, r12; pvarg
0x140274db1  call    cs:__imp_VariantInit
0x140274db8  nop     dword ptr [rax+rax+00h]
0x140274dbd  mov     [rsp+0A8h+var_60], 0
0x140274dc6  mov     [rsp+0A8h+var_78], 0
0x140274dcb  mov     [rsp+0A8h+var_88], 0
0x140274dd4  lea     r9, [rsp+0A8h+var_60]
0x140274dd9  xor     r8d, r8d
0x140274ddc  mov     rdx, rdi
0x140274ddf  mov     rcx, rsi
0x140274de2  call    ?GetOrCreateNode@HyperVStorage@@IEAAHPEBGPEAVHyperVStorageOperation@@AEAV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBDPEAVHyperVStorageKeyTableEntry@@@std@@@std@@@std@@@std@@PEAPEAVHyperVStorageKeyTableEntry@@IE@Z; HyperVStorage::GetOrCreateNode(ushort const *,HyperVStorageOperation *,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<char const * const,HyperVStorageKeyTableEntry *>>>> &,HyperVStorageKeyTableEntry * *,uint,uchar)
0x140274de7  test    eax, eax
0x140274de9  jnz     short loc_140274DF5
0x140274deb  mov     eax, 80070002h
0x140274df0  jmp     loc_140274FF5
0x140274df5  mov     [rsp+0A8h+var_38], 0
0x140274dfd  mov     [rsp+0A8h+ppvData], 0
0x140274e06  mov     rax, [rsp+0A8h+var_60]
0x140274e0b  mov     r13, [rax+28h]
0x140274e0f  mov     rax, [r13+0]
0x140274e13  movzx   ecx, byte ptr [rax]
0x140274e16  mov     dword ptr [rsp+0A8h+var_60], ecx
0x140274e1a  sub     ecx, 3
0x140274e1d  jz      loc_140274F4F
0x140274e23  sub     ecx, 1
0x140274e26  jz      loc_140274F46
0x140274e2c  sub     ecx, 1
0x140274e2f  jz      loc_140274F3D
0x140274e35  sub     ecx, 1
0x140274e38  jz      loc_140274EE4
0x140274e3e  sub     ecx, 1
0x140274e41  jz      short loc_140274E7C
0x140274e43  cmp     ecx, 1
0x140274e46  jz      short loc_140274E52
0x140274e48  mov     ecx, 80070057h; int
0x140274e4d  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x140274e52  lea     rax, [rsp+0A8h+var_38]
0x140274e57  mov     [rsp+0A8h+ppvData], rax
0x140274e5c  mov     edi, 4
0x140274e61  mov     [rsp+0A8h+var_68], edi
0x140274e65  mov     word ptr [r12], 0Bh
0x140274e6c  lea     rsi, [r12+8]
0x140274e71  mov     r15d, 8
0x140274e77  jmp     loc_140274F6E
0x140274e7c  mov     rcx, r13; this
0x140274e7f  call    ?PointsToFileObject@HyperVStorageKeyTableEntry@@QEBAHXZ; HyperVStorageKeyTableEntry::PointsToFileObject(void)
0x140274e84  test    eax, eax
0x140274e86  jnz     short loc_140274E8F
0x140274e88  call    ?GetValueSizeInBytes@HyperVStorageKeyTableEntry@@QEBAIXZ; HyperVStorageKeyTableEntry::GetValueSizeInBytes(void)
0x140274e8d  jmp     short loc_140274E94
0x140274e8f  call    ?GetFileObjectDataSizeInBytes@HyperVStorageKeyTableEntry@@QEBAIXZ; HyperVStorageKeyTableEntry::GetFileObjectDataSizeInBytes(void)
0x140274e94  mov     edi, eax
0x140274e96  mov     [rsp+0A8h+var_68], eax
0x140274e9a  mov     ecx, 11h; vt
0x140274e9f  mov     r8d, eax; cElements
0x140274ea2  xor     edx, edx; lLbound
0x140274ea4  call    cs:__imp_SafeArrayCreateVector
0x140274eab  nop     dword ptr [rax+rax+00h]
0x140274eb0  mov     rcx, rax; psa
0x140274eb3  lea     rsi, [r12+8]
0x140274eb8  mov     [rsi], rax
0x140274ebb  test    rax, rax
0x140274ebe  jnz     short loc_140274ECA
0x140274ec0  mov     ecx, 8007000Eh; int
0x140274ec5  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x140274eca  mov     word ptr [r12], 2011h
0x140274ed1  lea     rdx, [rsp+0A8h+ppvData]; ppvData
0x140274ed6  call    cs:__imp_SafeArrayAccessData
0x140274edd  nop     dword ptr [rax+rax+00h]
0x140274ee2  jmp     short loc_140274E71
0x140274ee4  mov     rcx, r13; this
0x140274ee7  call    ?PointsToFileObject@HyperVStorageKeyTableEntry@@QEBAHXZ; HyperVStorageKeyTableEntry::PointsToFileObject(void)
0x140274eec  test    eax, eax
0x140274eee  jnz     short loc_140274EF7
0x140274ef0  call    ?GetValueSizeInBytes@HyperVStorageKeyTableEntry@@QEBAIXZ; HyperVStorageKeyTableEntry::GetValueSizeInBytes(void)
0x140274ef5  jmp     short loc_140274EFC
0x140274ef7  call    ?GetFileObjectDataSizeInBytes@HyperVStorageKeyTableEntry@@QEBAIXZ; HyperVStorageKeyTableEntry::GetFileObjectDataSizeInBytes(void)
0x140274efc  mov     edi, eax
0x140274efe  mov     [rsp+0A8h+var_68], eax
0x140274f02  mov     edx, eax; len
0x140274f04  xor     ecx, ecx; psz
0x140274f06  call    cs:__imp_SysAllocStringByteLen
0x140274f0d  nop     dword ptr [rax+rax+00h]
0x140274f12  lea     rsi, [r12+8]
0x140274f17  mov     [rsi], rax
0x140274f1a  mov     [rsp+0A8h+ppvData], rax
0x140274f1f  mov     r8d, edi
0x140274f22  add     r8, 2; Size
0x140274f26  xor     edx, edx; Val
0x140274f28  mov     rcx, rax; void *
0x140274f2b  call    memset_0
0x140274f30  mov     r15d, 8
0x140274f36  mov     [r12], r15w
0x140274f3b  jmp     short loc_140274F6E
0x140274f3d  mov     word ptr [r12], 5
0x140274f44  jmp     short loc_140274F56
0x140274f46  mov     word ptr [r12], 15h
0x140274f4d  jmp     short loc_140274F56
0x140274f4f  mov     word ptr [r12], 14h
0x140274f56  lea     rsi, [r12+8]
0x140274f5b  mov     r15d, 8
0x140274f61  mov     [rsp+0A8h+ppvData], rsi
0x140274f66  mov     edi, r15d
0x140274f69  mov     [rsp+0A8h+var_68], r15d
0x140274f6e  lea     rax, [rsp+0A8h+var_68]
0x140274f73  mov     [rsp+0A8h+var_80], rax
0x140274f78  mov     rax, [rsp+0A8h+ppvData]
0x140274f7d  mov     [rsp+0A8h+var_88], rax
0x140274f82  mov     r9d, edi
0x140274f85  mov     edi, dword ptr [rsp+0A8h+var_60]
0x140274f89  mov     r8d, edi
0x140274f8c  mov     rdx, r13
0x140274f8f  mov     rcx, [rsp+0A8h+var_58]
0x140274f94  call    ?GetValueInternal@HyperVStorage@@IEBAXPEBVHyperVStorageKeyTableEntry@@W4HyperVStorageKeyType@@IPEAEAEAI@Z; HyperVStorage::GetValueInternal(HyperVStorageKeyTableEntry const *,HyperVStorageKeyType,uint,uchar *,uint &)
0x140274f99  cmp     edi, r15d
0x140274f9c  jnz     short loc_140274FAF
0x140274f9e  cmp     [rsp+0A8h+var_38], 0
0x140274fa3  jz      short loc_140274FAA
0x140274fa5  or      eax, 0FFFFFFFFh
0x140274fa8  jmp     short loc_140274FAC
0x140274faa  xor     eax, eax
0x140274fac  mov     [rsi], ax
0x140274faf  xor     edi, edi
0x140274fb1  jmp     short loc_140274FC5
0x140274fb3  mov     r14, [rsp+0A8h+var_50]
0x140274fb8  lea     rsi, [r14+8]
0x140274fbc  mov     edi, dword ptr [rsp+0A8h+var_60]
0x140274fc0  mov     r12, [rsp+0A8h+var_48]
0x140274fc5  mov     eax, 2011h
0x140274fca  cmp     [r12], ax
0x140274fcf  jnz     short loc_140274FE0
0x140274fd1  mov     rcx, [rsi]; psa
0x140274fd4  call    cs:__imp_SafeArrayUnaccessData
0x140274fdb  nop     dword ptr [rax+rax+00h]
0x140274fe0  test    edi, edi
0x140274fe2  jns     short loc_140274FF3
0x140274fe4  mov     rcx, r14; pvarg
0x140274fe7  call    cs:__imp_VariantClear
0x140274fee  nop     dword ptr [rax+rax+00h]
0x140274ff3  mov     eax, edi
0x140274ff5  mov     rcx, [rsp+0A8h+var_30]
0x140274ffa  xor     rcx, rsp; StackCookie
0x140274ffd  call    __security_check_cookie
0x140275002  mov     rsi, [rsp+0A8h+arg_18]
0x14027500a  add     rsp, 80h
0x140275011  pop     r15
0x140275013  pop     r14
0x140275015  pop     r13
0x140275017  pop     r12
0x140275019  pop     rdi
0x14027501a  retn
```
