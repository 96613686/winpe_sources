# DecompressCabFileInternal

- ea: `0x180015dfc`
- end: `0x180015fc0`
- name: `DecompressCabFileInternal`
- size: `452`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, __int64, char **, unsigned int, int, __int64, unsigned int, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b9d0`
- `0x180015fc8`

## callees

- `0x180003950`
- `0x180014cb8`
- `0x180015158`
- `0x180015200`
- `0x180015dfc`
- `0x180016210`
- `0x180016684`
- `0x1800167a4`
- `0x180049260`

## string_xrefs

- `0x180015e3f`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`
- `0x180015f25`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`
- `0x180015f6b`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`

## pseudocode

```c
__int64 __fastcall DecompressCabFileInternal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        char **a6,
        unsigned int a7,
        int a8,
        __int64 a9,
        unsigned int a10,
        __int64 a11,
        _QWORD *a12)
{
  __int64 v14; // rdx
  int v16; // eax
  void *v17; // r9
  struct CCabDecompressor *v18; // rbx
  int v19; // edi
  __int64 v20; // rdx
  __int64 v21; // r8
  int v22; // eax
  const CHAR *v23; // rcx
  int v24; // eax
  __int64 v25; // rax
  unsigned int v26; // [rsp+20h] [rbp-58h]
  struct CCabDecompressor *v27[2]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( !a12 )
  {
    v14 = 1317;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressor.cpp",
      (const char *)0x80070057LL,
      v26);
    return 2147942487LL;
  }
  *a12 = 0;
  if ( !a3 )
  {
    v14 = 1321;
    goto LABEL_3;
  }
  if ( a4 == 1 && !a5 )
  {
    v14 = 1323;
    goto LABEL_3;
  }
  v27[0] = 0;
  v16 = WuSmartPtr::XPtrBase<CCabDecompressor,WuSmartPtr::Policies::STPolicy<CCabDecompressor>>::ReleaseAndAlloc(v27);
  v18 = v27[0];
  v19 = v16;
  if ( v16 >= 0 )
  {
    v19 = CCabDecompressor::Init(v27[0], (const char **)a6, a7, v17, a10);
    if ( v19 >= 0 )
    {
      CCabDecompressorList::AppendNode(v18);
      if ( !a8 || (unsigned int)CCabDecompressor::IsValidCabInternal(v18, 1, v21, a3) )
      {
        v22 = CCabDecompressor::DecompressInternal(v18, a4, a5);
        v19 = v22;
        if ( v22 < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x229,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressor.cpp",
            (const char *)(unsigned int)v22,
            v26);
      }
      else
      {
        v19 = -2147024885;
      }
      v23 = (const CHAR *)*((_QWORD *)v18 + 6);
      v27[0] = 0;
      v24 = CCabDecompressorList::RemoveNode(v23, v27);
      if ( v19 >= 0 )
      {
        if ( v24 >= 0 )
        {
          v25 = *((_QWORD *)v18 + 8);
          v19 = 0;
          *((_QWORD *)v18 + 8) = 0;
          *a12 = v25;
          goto LABEL_24;
        }
        v19 = v24;
        v20 = 1388;
      }
      else
      {
        v20 = 1387;
      }
    }
    else
    {
      v20 = 1329;
    }
  }
  else
  {
    v20 = 1326;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v20,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressor.cpp",
    (const char *)(unsigned int)v19,
    v26);
LABEL_24:
  if ( v18 )
    (**(void (__fastcall ***)(struct CCabDecompressor *, __int64))v18)(v18, 1);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180015dfc  mov     [rsp+arg_0], rbx
0x180015e01  mov     [rsp+arg_8], rbp
0x180015e06  push    rsi
0x180015e07  push    rdi
0x180015e08  push    r12
0x180015e0a  push    r14
0x180015e0c  push    r15
0x180015e0e  sub     rsp, 50h
0x180015e12  mov     r14, [rsp+78h+arg_58]
0x180015e1a  mov     ebp, r9d
0x180015e1d  mov     r15, [rsp+78h+arg_20]
0x180015e25  mov     rsi, r8
0x180015e28  mov     r12, [rsp+78h+arg_28]
0x180015e30  test    r14, r14
0x180015e33  jnz     short loc_180015E5A
0x180015e35  mov     edx, 525h; void *
0x180015e3a  mov     rcx, [rsp+78h]; this
0x180015e3f  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x180015e46  mov     ebx, 80070057h
0x180015e4b  mov     r9d, ebx; char *
0x180015e4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015e53  mov     eax, ebx
0x180015e55  jmp     loc_180015FA7
0x180015e5a  mov     qword ptr [r14], 0
0x180015e61  test    rsi, rsi
0x180015e64  jnz     short loc_180015E6D
0x180015e66  mov     edx, 529h
0x180015e6b  jmp     short loc_180015E3A
0x180015e6d  cmp     ebp, 1
0x180015e70  jnz     short loc_180015E7E
0x180015e72  test    r15, r15
0x180015e75  jnz     short loc_180015E7E
0x180015e77  mov     edx, 52Bh
0x180015e7c  jmp     short loc_180015E3A
0x180015e7e  lea     rcx, [rsp+78h+var_38]
0x180015e83  mov     [rsp+78h+var_38], 0
0x180015e8c  call    ?ReleaseAndAlloc@?$XPtrBase@VCCabDecompressor@@U?$STPolicy@VCCabDecompressor@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAJXZ; WuSmartPtr::XPtrBase<CCabDecompressor,WuSmartPtr::Policies::STPolicy<CCabDecompressor>>::ReleaseAndAlloc(void)
0x180015e91  mov     rbx, [rsp+78h+var_38]
0x180015e96  mov     edi, eax
0x180015e98  test    eax, eax
0x180015e9a  jns     short loc_180015EA6
0x180015e9c  mov     edx, 52Eh
0x180015ea1  jmp     loc_180015F66
0x180015ea6  mov     eax, [rsp+78h+arg_48]
0x180015ead  mov     rdx, r12; char **
0x180015eb0  mov     r8d, [rsp+78h+arg_30]; unsigned int
0x180015eb8  mov     rcx, rbx; this
0x180015ebb  mov     [rsp+78h+var_58], eax; unsigned int
0x180015ebf  call    ?Init@CCabDecompressor@@QEAAJPEAPEBDKPEAXKHH@Z; CCabDecompressor::Init(char const * *,ulong,void *,ulong,int,int)
0x180015ec4  mov     edi, eax
0x180015ec6  test    eax, eax
0x180015ec8  jns     short loc_180015ED4
0x180015eca  mov     edx, 531h
0x180015ecf  jmp     loc_180015F66
0x180015ed4  mov     rcx, rbx; struct CCabDecompressor *
0x180015ed7  call    ?AppendNode@CCabDecompressorList@@SAXPEAVCCabDecompressor@@@Z; CCabDecompressorList::AppendNode(CCabDecompressor *)
0x180015edc  cmp     [rsp+78h+arg_38], 0
0x180015ee4  jz      short loc_180015F01
0x180015ee6  mov     r9, rsi
0x180015ee9  mov     edx, 1
0x180015eee  mov     rcx, rbx
0x180015ef1  call    ?IsValidCabInternal@CCabDecompressor@@AEAAHW4DATA_TYPE@@PEAV?$CSafeBuffer@E@@PEB_W@Z; CCabDecompressor::IsValidCabInternal(DATA_TYPE,CSafeBuffer<uchar> *,wchar_t const *)
0x180015ef6  test    eax, eax
0x180015ef8  jnz     short loc_180015F01
0x180015efa  mov     edi, 8007000Bh
0x180015eff  jmp     short loc_180015F39
0x180015f01  mov     [rsp+78h+var_50], r15; __int64
0x180015f06  mov     r9, rsi
0x180015f09  mov     edx, 1
0x180015f0e  mov     [rsp+78h+var_58], ebp; int
0x180015f12  mov     rcx, rbx; this
0x180015f15  call    ?DecompressInternal@CCabDecompressor@@AEAAJW4DATA_TYPE@@PEAV?$CSafeBuffer@E@@PEB_W02@Z; CCabDecompressor::DecompressInternal(DATA_TYPE,CSafeBuffer<uchar> *,wchar_t const *,DATA_TYPE,wchar_t const *)
0x180015f1a  mov     edi, eax
0x180015f1c  test    eax, eax
0x180015f1e  jns     short loc_180015F39
0x180015f20  mov     rcx, [rsp+78h]; this
0x180015f25  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x180015f2c  mov     r9d, eax; char *
0x180015f2f  mov     edx, 229h; void *
0x180015f34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015f39  mov     rcx, [rbx+30h]; lpString1
0x180015f3d  lea     rdx, [rsp+78h+var_38]; struct CCabDecompressor **
0x180015f42  mov     [rsp+78h+var_38], 0
0x180015f4b  call    ?RemoveNode@CCabDecompressorList@@SAJPEBDPEAPEAVCCabDecompressor@@@Z; CCabDecompressorList::RemoveNode(char const *,CCabDecompressor * *)
0x180015f50  test    edi, edi
0x180015f52  jns     short loc_180015F5B
0x180015f54  mov     edx, 56Bh
0x180015f59  jmp     short loc_180015F66
0x180015f5b  test    eax, eax
0x180015f5d  jns     short loc_180015F7C
0x180015f5f  mov     edi, eax
0x180015f61  mov     edx, 56Ch; void *
0x180015f66  mov     rcx, [rsp+78h]; this
0x180015f6b  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x180015f72  mov     r9d, edi; char *
0x180015f75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015f7a  jmp     short loc_180015F8D
0x180015f7c  mov     rax, [rbx+40h]
0x180015f80  xor     edi, edi
0x180015f82  mov     qword ptr [rbx+40h], 0
0x180015f8a  mov     [r14], rax
0x180015f8d  test    rbx, rbx
0x180015f90  jz      short loc_180015FA5
0x180015f92  mov     r8, [rbx]
0x180015f95  mov     edx, 1
0x180015f9a  mov     rcx, rbx
0x180015f9d  mov     rax, [r8]
0x180015fa0  call    _guard_dispatch_icall
0x180015fa5  mov     eax, edi
0x180015fa7  lea     r11, [rsp+78h+var_28]
0x180015fac  mov     rbx, [r11+30h]
0x180015fb0  mov     rbp, [r11+38h]
0x180015fb4  mov     rsp, r11
0x180015fb7  pop     r15
0x180015fb9  pop     r14
0x180015fbb  pop     r12
0x180015fbd  pop     rdi
0x180015fbe  pop     rsi
0x180015fbf  retn
```
