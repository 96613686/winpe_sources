# ImagingHandler::CalculateTotalSizeOccupiedByImageFrame(IMAGE_PIXELFORMAT const &)

- ea: `0x180010780`
- end: `0x18001089b`
- name: `?CalculateTotalSizeOccupiedByImageFrame@ImagingHandler@@AEAAJAEBW4IMAGE_PIXELFORMAT@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(ImagingHandler *__hidden this, const enum IMAGE_PIXELFORMAT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013b90`

## callees

- `0x180010780`
- `0x180011384`
- `0x180013d4c`
- `0x18001b010`

## string_xrefs

- `0x180010831`: `onecoreuap\base\appmodel\Search\filters\common\imageprocessing\imagingHandler.h`
- `0x18001085e`: `onecoreuap\base\appmodel\Search\filters\common\imageprocessing\imagingHandler.h`
- `0x180010880`: `onecoreuap\base\appmodel\Search\filters\common\imageprocessing\imagingHandler.h`

## pseudocode

```c
__int64 __fastcall ImagingHandler::CalculateTotalSizeOccupiedByImageFrame(
        ImagingHandler *this,
        const enum IMAGE_PIXELFORMAT *a2)
{
  _DWORD *v3; // r14
  _DWORD *v4; // rdi
  unsigned int v5; // ebx
  unsigned __int64 v6; // rdi
  __int64 v7; // rdx
  unsigned int MaxImageBufferSize; // eax
  __int64 result; // rax
  int v10; // [rsp+20h] [rbp-38h]

  v3 = (_DWORD *)((char *)this + 40);
  *((_DWORD *)this + 11) = (*(_DWORD *)a2 != 2) + 3;
  v4 = (_DWORD *)((char *)this + 36);
  (*(void (__fastcall **)(_QWORD, char *, char *))(**((_QWORD **)this + 3) + 24LL))(
    *((_QWORD *)this + 3),
    (char *)this + 36,
    (char *)this + 40);
  if ( *v3 && *v4 )
  {
    if ( *v4 * (*((_DWORD *)this + 11) & 0x1FFFFFFFu) / *v4 == (*((_DWORD *)this + 11) & 0x1FFFFFFF)
      && (v5 = (*v4 * (*((_DWORD *)this + 11) & 0x1FFFFFFF) + 3) & 0xFFFFFFFC) != 0 )
    {
      v6 = (unsigned int)*v3 * (unsigned __int64)v5;
      if ( v6 / (unsigned int)*v3 == v5 )
      {
        MaxImageBufferSize = GetMaxImageBufferSize();
        if ( v6 <= (int)MaxImageBufferSize )
        {
          result = 0;
          *((_DWORD *)this + 8) = *v3 * v5;
          return result;
        }
        v10 = -2147467259;
        SearchIndexerTrace::Error(
          (wchar_t *)L"onecoreuap\\base\\appmodel\\Search\\filters\\common\\imageprocessing\\imagingHandler.h",
          (const wchar_t *)0x149,
          (unsigned int)L"ImagingHandler::CalculateTotalSizeOccupiedByImageFrame : Frame buffer size exceeds the limit of "
                         "%d BYTES, hr(0x%08x)",
          (const wchar_t *)MaxImageBufferSize,
          v10);
        return 2147500037LL;
      }
      v7 = 316;
    }
    else
    {
      v7 = 306;
    }
    SearchIndexerTrace::Error(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\Search\\filters\\common\\imageprocessing\\imagingHandler.h",
      (const wchar_t *)v7,
      (unsigned int)L"ImagingHandler::CalculateTotalSizeOccupiedByImageFrame : Overflow, hr(0x%08x)",
      (const wchar_t *)0x80004005LL);
    return 2147500037LL;
  }
  SearchIndexerTrace::Error(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\Search\\filters\\common\\imageprocessing\\imagingHandler.h",
    (const wchar_t *)0x129,
    (unsigned int)L"ImagingHandler::CalculateTotalSizeOccupiedByImageFrame : Frame height or width is zero, hr(0x%08x)",
    (const wchar_t *)0x80004003LL);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180010780  push    rbx
0x180010782  push    rsi
0x180010783  push    rdi
0x180010784  push    r14
0x180010786  sub     rsp, 38h
0x18001078a  xor     eax, eax
0x18001078c  mov     rsi, rcx
0x18001078f  cmp     dword ptr [rdx], 2
0x180010792  setnz   al
0x180010795  add     eax, 3
0x180010798  lea     r14, [rsi+28h]
0x18001079c  mov     [rcx+2Ch], eax
0x18001079f  lea     rdi, [rsi+24h]
0x1800107a3  mov     rcx, [rcx+18h]
0x1800107a7  mov     r8, r14
0x1800107aa  mov     rdx, rdi
0x1800107ad  mov     rax, [rcx]
0x1800107b0  mov     rax, [rax+18h]
0x1800107b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107b9  cmp     dword ptr [r14], 0
0x1800107bd  jz      loc_18001086E
0x1800107c3  cmp     dword ptr [rdi], 0
0x1800107c6  jz      loc_18001086E
0x1800107cc  mov     ecx, [rsi+2Ch]
0x1800107cf  xor     edx, edx
0x1800107d1  and     ecx, 1FFFFFFFh
0x1800107d7  mov     ebx, ecx
0x1800107d9  imul    ebx, [rdi]
0x1800107dc  mov     eax, ebx
0x1800107de  div     dword ptr [rdi]
0x1800107e0  cmp     eax, ecx
0x1800107e2  jnz     short loc_18001084A
0x1800107e4  add     ebx, 3
0x1800107e7  and     ebx, 0FFFFFFFCh
0x1800107ea  jz      short loc_18001084A
0x1800107ec  mov     ecx, [r14]
0x1800107ef  xor     edx, edx
0x1800107f1  mov     edi, ebx
0x1800107f3  imul    rdi, rcx
0x1800107f7  mov     r8d, ebx
0x1800107fa  mov     rax, rdi
0x1800107fd  div     rcx
0x180010800  cmp     rax, r8
0x180010803  jz      short loc_18001080C
0x180010805  mov     edx, 13Ch
0x18001080a  jmp     short loc_18001084F
0x18001080c  call    ?GetMaxImageBufferSize@@YAHXZ; GetMaxImageBufferSize(void)
0x180010811  movsxd  rcx, eax
0x180010814  cmp     rdi, rcx
0x180010817  jbe     short loc_18001083F
0x180010819  mov     ebx, 80004005h
0x18001081e  lea     r8, aImaginghandler_9; "ImagingHandler::CalculateTotalSizeOccup"...
0x180010825  mov     r9d, eax; wchar_t *
0x180010828  mov     [rsp+58h+var_38], ebx
0x18001082c  mov     edx, 149h; wchar_t *
0x180010831  lea     rcx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\Search\\fil"...
0x180010838  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18001083d  jmp     short loc_18001086A
0x18001083f  imul    ebx, [r14]
0x180010843  xor     eax, eax
0x180010845  mov     [rsi+20h], ebx
0x180010848  jmp     short loc_180010891
0x18001084a  mov     edx, 132h; wchar_t *
0x18001084f  mov     ebx, 80004005h
0x180010854  lea     r8, aImaginghandler_8; "ImagingHandler::CalculateTotalSizeOccup"...
0x18001085b  mov     r9d, ebx; wchar_t *
0x18001085e  lea     rcx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\Search\\fil"...
0x180010865  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18001086a  mov     eax, ebx
0x18001086c  jmp     short loc_180010891
0x18001086e  mov     r9d, 80004003h; wchar_t *
0x180010874  lea     r8, aImaginghandler_0; "ImagingHandler::CalculateTotalSizeOccup"...
0x18001087b  mov     edx, 129h; wchar_t *
0x180010880  lea     rcx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\Search\\fil"...
0x180010887  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18001088c  mov     eax, 80004005h
0x180010891  add     rsp, 38h
0x180010895  pop     r14
0x180010897  pop     rdi
0x180010898  pop     rsi
0x180010899  pop     rbx
0x18001089a  retn
```
