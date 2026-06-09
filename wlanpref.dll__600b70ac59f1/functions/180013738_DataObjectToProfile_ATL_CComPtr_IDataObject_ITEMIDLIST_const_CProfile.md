# DataObjectToProfile(ATL::CComPtr<IDataObject> &,_ITEMIDLIST const *,CProfile &)

- ea: `0x180013738`
- end: `0x1800138c5`
- name: `?DataObjectToProfile@@YAJAEAV?$CComPtr@UIDataObject@@@ATL@@PEFBU_ITEMIDLIST@@AEAVCProfile@@@Z`
- size: `397`
- prototype: `__int64 __fastcall(_QWORD *, const ITEMIDLIST *, CProfile *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800138d0`
- `0x1800139a0`

## callees

- `0x180013554`
- `0x180013738`
- `0x180027594`
- `0x180027648`
- `0x18002868c`
- `0x18002d840`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001381c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001381c`
- `KERNEL32!GlobalLock` at `0x18001380e`
- `KERNEL32!GlobalLock` at `0x18001380e`
- `ole32!ReleaseStgMedium` at `0x180013848`
- `ole32!ReleaseStgMedium` at `0x180013848`
- `SHELL32!__imp_ILIsEqual` at `0x180013880`
- `SHELL32!__imp_ILIsEqual` at `0x180013880`
- `USER32!RegisterClipboardFormatW` at `0x180013776`
- `USER32!RegisterClipboardFormatW` at `0x180013776`

## pseudocode

```c
__int64 __fastcall DataObjectToProfile(_QWORD *a1, const ITEMIDLIST *a2, CProfile *a3)
{
  __int64 result; // rax
  void *v7; // xmm1_8
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  signed int LastError; // eax
  signed int v11; // ebx
  const struct CProfile *v12; // rax
  __int128 v13; // [rsp+20h] [rbp-99h] BYREF
  __int128 v14; // [rsp+30h] [rbp-89h]
  __int128 v15; // [rsp+40h] [rbp-79h] BYREF
  __m128i v16; // [rsp+50h] [rbp-69h] BYREF
  IUnknown *v17; // [rsp+60h] [rbp-59h]
  STGMEDIUM v18; // [rsp+68h] [rbp-51h] BYREF
  _BYTE v19[96]; // [rsp+80h] [rbp-39h] BYREF

  v14 = 0;
  v13 = (unsigned __int16)RegisterClipboardFormatW(L"Shell IDList Array");
  *(_QWORD *)&v14 = 0xFFFFFFFF00000001uLL;
  DWORD2(v14) = 1;
  result = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*a1 + 40LL))(*a1, &v13);
  if ( (int)result >= 0 )
  {
    v16 = 0;
    v17 = 0;
    result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __m128i *))(*(_QWORD *)*a1 + 24LL))(*a1, &v13, &v16);
    if ( (int)result >= 0 )
    {
      *(__m128i *)&v18.tymed = v16;
      v18.pUnkForRelease = v17;
      v15 = 0;
      v7 = (void *)_mm_srli_si128(v16, 8).m128i_u64[0];
      v8 = GlobalLock(v7);
      v9 = v8;
      if ( v8 )
      {
        *(_QWORD *)&v15 = v7;
        *((_QWORD *)&v15 + 1) = v8;
        if ( *v8 == 1 )
        {
          if ( ILIsEqual((LPCITEMIDLIST)((char *)v8 + (unsigned int)v8[1]), a2) )
          {
            v12 = (const struct CProfile *)StructToProfile(v19, (char *)v9 + (unsigned int)v9[2] + 2);
            CProfile::Clone(a3, v12);
            CProfile::~CProfile((CProfile *)v19);
            if ( !*((_BYTE *)a3 + 81) )
            {
              v11 = 0;
              goto LABEL_8;
            }
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        if ( v11 < 0 )
          goto LABEL_8;
      }
      v11 = -2147024809;
LABEL_8:
      CScopedGlobalHandle::~CScopedGlobalHandle((CScopedGlobalHandle *)&v15);
      ReleaseStgMedium(&v18);
      return (unsigned int)v11;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180013738  push    rbp
0x18001373a  push    rbx
0x18001373b  push    rsi
0x18001373c  push    rdi
0x18001373d  push    r14
0x18001373f  lea     rbp, [rsp-37h]
0x180013744  sub     rsp, 0F0h
0x18001374b  mov     rax, cs:__security_cookie
0x180013752  xor     rax, rsp
0x180013755  mov     [rbp+57h+var_30], rax
0x180013759  mov     rsi, r8
0x18001375c  mov     r14, rdx
0x18001375f  mov     rbx, rcx
0x180013762  xorps   xmm0, xmm0
0x180013765  movups  [rsp+110h+var_F0], xmm0
0x18001376a  movups  [rsp+110h+var_E0], xmm0
0x18001376f  lea     rcx, szFormat; "Shell IDList Array"
0x180013776  call    cs:__imp_RegisterClipboardFormatW
0x18001377c  mov     word ptr [rsp+110h+var_F0], ax
0x180013781  mov     qword ptr [rsp+110h+var_F0+8], 0
0x18001378a  mov     dword ptr [rsp+110h+var_E0], 1
0x180013792  mov     dword ptr [rsp+110h+var_E0+4], 0FFFFFFFFh
0x18001379a  mov     dword ptr [rsp+110h+var_E0+8], 1
0x1800137a2  mov     rcx, [rbx]
0x1800137a5  mov     rax, [rcx]
0x1800137a8  lea     rdx, [rsp+110h+var_F0]
0x1800137ad  mov     rax, [rax+28h]
0x1800137b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137b6  test    eax, eax
0x1800137b8  js      loc_180013850
0x1800137be  xorps   xmm0, xmm0
0x1800137c1  xor     eax, eax
0x1800137c3  movups  [rbp+57h+var_C0], xmm0
0x1800137c7  mov     [rbp+57h+var_B0], rax
0x1800137cb  mov     rcx, [rbx]
0x1800137ce  mov     rax, [rcx]
0x1800137d1  lea     r8, [rbp+57h+var_C0]
0x1800137d5  lea     rdx, [rsp+110h+var_F0]
0x1800137da  mov     rax, [rax+18h]
0x1800137de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137e3  test    eax, eax
0x1800137e5  js      short loc_180013850
0x1800137e7  movups  xmm1, [rbp+57h+var_C0]
0x1800137eb  movups  xmmword ptr [rbp+57h+var_A8.tymed], xmm1
0x1800137ef  movsd   xmm0, [rbp+57h+var_B0]
0x1800137f4  movsd   [rbp+57h+var_A8.pUnkForRelease], xmm0
0x1800137f9  xorps   xmm0, xmm0
0x1800137fc  movdqu  [rbp+57h+var_D0], xmm0
0x180013801  psrldq  xmm1, 8
0x180013806  movq    rdi, xmm1
0x18001380b  mov     rcx, rdi; hMem
0x18001380e  call    cs:__imp_GlobalLock
0x180013814  mov     rbx, rax
0x180013817  test    rax, rax
0x18001381a  jnz     short loc_18001386A
0x18001381c  call    cs:__imp_GetLastError
0x180013822  mov     ebx, eax
0x180013824  test    eax, eax
0x180013826  jle     short loc_180013831
0x180013828  movzx   ebx, ax
0x18001382b  or      ebx, 80070000h
0x180013831  test    ebx, ebx
0x180013833  js      short loc_18001383A
0x180013835  mov     ebx, 80070057h
0x18001383a  lea     rcx, [rbp+57h+var_D0]; this
0x18001383e  call    ??1CScopedGlobalHandle@@QEAA@XZ; CScopedGlobalHandle::~CScopedGlobalHandle(void)
0x180013843  nop
0x180013844  lea     rcx, [rbp+57h+var_A8]; LPSTGMEDIUM
0x180013848  call    cs:__imp_ReleaseStgMedium
0x18001384e  mov     eax, ebx
0x180013850  mov     rcx, [rbp+57h+var_30]
0x180013854  xor     rcx, rsp; StackCookie
0x180013857  call    __security_check_cookie
0x18001385c  add     rsp, 0F0h
0x180013863  pop     r14
0x180013865  pop     rdi
0x180013866  pop     rsi
0x180013867  pop     rbx
0x180013868  pop     rbp
0x180013869  retn
0x18001386a  mov     qword ptr [rbp+57h+var_D0], rdi
0x18001386e  mov     qword ptr [rbp+57h+var_D0+8], rbx
0x180013872  cmp     dword ptr [rax], 1
0x180013875  jnz     short loc_180013835
0x180013877  mov     ecx, [rax+4]
0x18001387a  add     rcx, rbx; pidl1
0x18001387d  mov     rdx, r14; pidl2
0x180013880  call    cs:__imp_ILIsEqual
0x180013886  test    eax, eax
0x180013888  jz      short loc_180013835
0x18001388a  mov     edx, [rbx+8]
0x18001388d  add     rdx, 2
0x180013891  add     rdx, rbx
0x180013894  lea     rcx, [rbp+57h+var_90]
0x180013898  call    ?StructToProfile@@YA?AVCProfile@@AEBUWPLDATA@@@Z; StructToProfile(WPLDATA const &)
0x18001389d  nop
0x18001389e  mov     rdx, rax; struct CProfile *
0x1800138a1  mov     rcx, rsi; this
0x1800138a4  call    ?Clone@CProfile@@IEAAXAEBV1@@Z; CProfile::Clone(CProfile const &)
0x1800138a9  nop
0x1800138aa  lea     rcx, [rbp+57h+var_90]; this
0x1800138ae  call    ??1CProfile@@UEAA@XZ; CProfile::~CProfile(void)
0x1800138b3  cmp     byte ptr [rsi+51h], 0
0x1800138b7  jnz     loc_180013835
0x1800138bd  xor     ebx, ebx
0x1800138bf  jmp     loc_18001383A
```
