# HyperVStorage::GetVariantValue(ushort const *,tagVARIANT &)

- ea: `0x1401b7fd0`
- end: `0x1401b828c`
- name: `?GetVariantValue@HyperVStorage@@QEBAJPEBGAEAUtagVARIANT@@@Z`
- size: `700`
- prototype: `int(HyperVStorage *__hidden this, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1401d9e70`

## callees

- `0x140029b34`
- `0x14002cae8`
- `0x14002d380`
- `0x1400af904`
- `0x1400e6cec`
- `0x14011ea40`
- `0x14011f6fc`
- `0x1401b7fd0`
- `0x1401c4a24`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1401b8021`
- `OLEAUT32!__imp_VariantInit` at `0x1401b8021`
- `OLEAUT32!__imp_VariantClear` at `0x1401b8257`
- `OLEAUT32!__imp_VariantClear` at `0x1401b8257`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401b8146`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401b8146`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401b8244`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401b8244`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1401b8176`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1401b8176`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1401b8114`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1401b8114`

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
0x1401b7fd0  mov     [rsp+arg_18], rsi
0x1401b7fd5  push    rdi
0x1401b7fd6  push    r12
0x1401b7fd8  push    r13
0x1401b7fda  push    r14
0x1401b7fdc  push    r15
0x1401b7fde  sub     rsp, 80h
0x1401b7fe5  mov     rax, cs:__security_cookie
0x1401b7fec  xor     rax, rsp
0x1401b7fef  mov     [rsp+0A8h+var_30], rax
0x1401b7ff4  mov     r12, r8
0x1401b7ff7  mov     rdi, rdx
0x1401b7ffa  mov     rsi, rcx
0x1401b7ffd  mov     [rsp+0A8h+var_58], rcx
0x1401b8002  mov     [rsp+0A8h+var_48], r8
0x1401b8007  mov     r14, r8
0x1401b800a  mov     [rsp+0A8h+var_50], r8
0x1401b800f  test    rdx, rdx
0x1401b8012  jnz     short loc_1401B801E
0x1401b8014  mov     ecx, 80070057h; int
0x1401b8019  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401b801e  mov     rcx, r12; pvarg
0x1401b8021  call    cs:__imp_VariantInit
0x1401b8028  nop     dword ptr [rax+rax+00h]
0x1401b802d  mov     [rsp+0A8h+var_60], 0
0x1401b8036  mov     [rsp+0A8h+var_78], 0
0x1401b803b  mov     [rsp+0A8h+var_88], 0
0x1401b8044  lea     r9, [rsp+0A8h+var_60]
0x1401b8049  xor     r8d, r8d
0x1401b804c  mov     rdx, rdi
0x1401b804f  mov     rcx, rsi
0x1401b8052  call    ?GetOrCreateNode@HyperVStorage@@IEAAHPEBGPEAVHyperVStorageOperation@@AEAV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBDPEAVHyperVStorageKeyTableEntry@@@std@@@std@@@std@@@std@@PEAPEAVHyperVStorageKeyTableEntry@@IE@Z; HyperVStorage::GetOrCreateNode(ushort const *,HyperVStorageOperation *,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<char const * const,HyperVStorageKeyTableEntry *>>>> &,HyperVStorageKeyTableEntry * *,uint,uchar)
0x1401b8057  test    eax, eax
0x1401b8059  jnz     short loc_1401B8065
0x1401b805b  mov     eax, 80070002h
0x1401b8060  jmp     loc_1401B8265
0x1401b8065  mov     [rsp+0A8h+var_38], 0
0x1401b806d  mov     [rsp+0A8h+ppvData], 0
0x1401b8076  mov     rax, [rsp+0A8h+var_60]
0x1401b807b  mov     r13, [rax+28h]
0x1401b807f  mov     rax, [r13+0]
0x1401b8083  movzx   ecx, byte ptr [rax]
0x1401b8086  mov     dword ptr [rsp+0A8h+var_60], ecx
0x1401b808a  sub     ecx, 3
0x1401b808d  jz      loc_1401B81BF
0x1401b8093  sub     ecx, 1
0x1401b8096  jz      loc_1401B81B6
0x1401b809c  sub     ecx, 1
0x1401b809f  jz      loc_1401B81AD
0x1401b80a5  sub     ecx, 1
0x1401b80a8  jz      loc_1401B8154
0x1401b80ae  sub     ecx, 1
0x1401b80b1  jz      short loc_1401B80EC
0x1401b80b3  cmp     ecx, 1
0x1401b80b6  jz      short loc_1401B80C2
0x1401b80b8  mov     ecx, 80070057h; int
0x1401b80bd  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401b80c2  lea     rax, [rsp+0A8h+var_38]
0x1401b80c7  mov     [rsp+0A8h+ppvData], rax
0x1401b80cc  mov     edi, 4
0x1401b80d1  mov     [rsp+0A8h+var_68], edi
0x1401b80d5  mov     word ptr [r12], 0Bh
0x1401b80dc  lea     rsi, [r12+8]
0x1401b80e1  mov     r15d, 8
0x1401b80e7  jmp     loc_1401B81DE
0x1401b80ec  mov     rcx, r13; this
0x1401b80ef  call    ?PointsToFileObject@HyperVStorageKeyTableEntry@@QEBAHXZ; HyperVStorageKeyTableEntry::PointsToFileObject(void)
0x1401b80f4  test    eax, eax
0x1401b80f6  jnz     short loc_1401B80FF
0x1401b80f8  call    ?GetValueSizeInBytes@HyperVStorageKeyTableEntry@@QEBAIXZ; HyperVStorageKeyTableEntry::GetValueSizeInBytes(void)
0x1401b80fd  jmp     short loc_1401B8104
0x1401b80ff  call    ?GetFileObjectDataSizeInBytes@HyperVStorageKeyTableEntry@@QEBAIXZ; HyperVStorageKeyTableEntry::GetFileObjectDataSizeInBytes(void)
0x1401b8104  mov     edi, eax
0x1401b8106  mov     [rsp+0A8h+var_68], eax
0x1401b810a  mov     ecx, 11h; vt
0x1401b810f  mov     r8d, eax; cElements
0x1401b8112  xor     edx, edx; lLbound
0x1401b8114  call    cs:__imp_SafeArrayCreateVector
0x1401b811b  nop     dword ptr [rax+rax+00h]
0x1401b8120  mov     rcx, rax; psa
0x1401b8123  lea     rsi, [r12+8]
0x1401b8128  mov     [rsi], rax
0x1401b812b  test    rax, rax
0x1401b812e  jnz     short loc_1401B813A
0x1401b8130  mov     ecx, 8007000Eh; int
0x1401b8135  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1401b813a  mov     word ptr [r12], 2011h
0x1401b8141  lea     rdx, [rsp+0A8h+ppvData]; ppvData
0x1401b8146  call    cs:__imp_SafeArrayAccessData
0x1401b814d  nop     dword ptr [rax+rax+00h]
0x1401b8152  jmp     short loc_1401B80E1
0x1401b8154  mov     rcx, r13; this
0x1401b8157  call    ?PointsToFileObject@HyperVStorageKeyTableEntry@@QEBAHXZ; HyperVStorageKeyTableEntry::PointsToFileObject(void)
0x1401b815c  test    eax, eax
0x1401b815e  jnz     short loc_1401B8167
0x1401b8160  call    ?GetValueSizeInBytes@HyperVStorageKeyTableEntry@@QEBAIXZ; HyperVStorageKeyTableEntry::GetValueSizeInBytes(void)
0x1401b8165  jmp     short loc_1401B816C
0x1401b8167  call    ?GetFileObjectDataSizeInBytes@HyperVStorageKeyTableEntry@@QEBAIXZ; HyperVStorageKeyTableEntry::GetFileObjectDataSizeInBytes(void)
0x1401b816c  mov     edi, eax
0x1401b816e  mov     [rsp+0A8h+var_68], eax
0x1401b8172  mov     edx, eax; len
0x1401b8174  xor     ecx, ecx; psz
0x1401b8176  call    cs:__imp_SysAllocStringByteLen
0x1401b817d  nop     dword ptr [rax+rax+00h]
0x1401b8182  lea     rsi, [r12+8]
0x1401b8187  mov     [rsi], rax
0x1401b818a  mov     [rsp+0A8h+ppvData], rax
0x1401b818f  mov     r8d, edi
0x1401b8192  add     r8, 2; Size
0x1401b8196  xor     edx, edx; Val
0x1401b8198  mov     rcx, rax; void *
0x1401b819b  call    memset_0
0x1401b81a0  mov     r15d, 8
0x1401b81a6  mov     [r12], r15w
0x1401b81ab  jmp     short loc_1401B81DE
0x1401b81ad  mov     word ptr [r12], 5
0x1401b81b4  jmp     short loc_1401B81C6
0x1401b81b6  mov     word ptr [r12], 15h
0x1401b81bd  jmp     short loc_1401B81C6
0x1401b81bf  mov     word ptr [r12], 14h
0x1401b81c6  lea     rsi, [r12+8]
0x1401b81cb  mov     r15d, 8
0x1401b81d1  mov     [rsp+0A8h+ppvData], rsi
0x1401b81d6  mov     edi, r15d
0x1401b81d9  mov     [rsp+0A8h+var_68], r15d
0x1401b81de  lea     rax, [rsp+0A8h+var_68]
0x1401b81e3  mov     [rsp+0A8h+var_80], rax
0x1401b81e8  mov     rax, [rsp+0A8h+ppvData]
0x1401b81ed  mov     [rsp+0A8h+var_88], rax
0x1401b81f2  mov     r9d, edi
0x1401b81f5  mov     edi, dword ptr [rsp+0A8h+var_60]
0x1401b81f9  mov     r8d, edi
0x1401b81fc  mov     rdx, r13
0x1401b81ff  mov     rcx, [rsp+0A8h+var_58]
0x1401b8204  call    ?GetValueInternal@HyperVStorage@@IEBAXPEBVHyperVStorageKeyTableEntry@@W4HyperVStorageKeyType@@IPEAEAEAI@Z; HyperVStorage::GetValueInternal(HyperVStorageKeyTableEntry const *,HyperVStorageKeyType,uint,uchar *,uint &)
0x1401b8209  cmp     edi, r15d
0x1401b820c  jnz     short loc_1401B821F
0x1401b820e  cmp     [rsp+0A8h+var_38], 0
0x1401b8213  jz      short loc_1401B821A
0x1401b8215  or      eax, 0FFFFFFFFh
0x1401b8218  jmp     short loc_1401B821C
0x1401b821a  xor     eax, eax
0x1401b821c  mov     [rsi], ax
0x1401b821f  xor     edi, edi
0x1401b8221  jmp     short loc_1401B8235
0x1401b8223  mov     r14, [rsp+0A8h+var_50]
0x1401b8228  lea     rsi, [r14+8]
0x1401b822c  mov     edi, dword ptr [rsp+0A8h+var_60]
0x1401b8230  mov     r12, [rsp+0A8h+var_48]
0x1401b8235  mov     eax, 2011h
0x1401b823a  cmp     [r12], ax
0x1401b823f  jnz     short loc_1401B8250
0x1401b8241  mov     rcx, [rsi]; psa
0x1401b8244  call    cs:__imp_SafeArrayUnaccessData
0x1401b824b  nop     dword ptr [rax+rax+00h]
0x1401b8250  test    edi, edi
0x1401b8252  jns     short loc_1401B8263
0x1401b8254  mov     rcx, r14; pvarg
0x1401b8257  call    cs:__imp_VariantClear
0x1401b825e  nop     dword ptr [rax+rax+00h]
0x1401b8263  mov     eax, edi
0x1401b8265  mov     rcx, [rsp+0A8h+var_30]
0x1401b826a  xor     rcx, rsp; StackCookie
0x1401b826d  call    __security_check_cookie
0x1401b8272  mov     rsi, [rsp+0A8h+arg_18]
0x1401b827a  add     rsp, 80h
0x1401b8281  pop     r15
0x1401b8283  pop     r14
0x1401b8285  pop     r13
0x1401b8287  pop     r12
0x1401b8289  pop     rdi
0x1401b828a  retn
```
