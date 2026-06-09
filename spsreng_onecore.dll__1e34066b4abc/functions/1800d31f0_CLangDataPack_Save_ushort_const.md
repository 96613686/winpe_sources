# CLangDataPack::Save(ushort const *)

- ea: `0x1800d31f0`
- end: `0x1800d343c`
- name: `?Save@CLangDataPack@@UEAAJPEBG@Z`
- size: `588`
- prototype: `int(CLangDataPack *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x1800034b0`
- `0x180016f48`
- `0x1800d2b3c`
- `0x1800d31f0`
- `0x1800d3444`
- `0x1800d3504`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d3278`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d3278`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d340d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d340d`

## pseudocode

```c
__int64 __fastcall CLangDataPack::Save(unsigned __int64 this, const unsigned __int16 *a2)
{
  unsigned __int64 v2; // r13
  unsigned __int64 v3; // r14
  signed int Error; // edi
  unsigned int v6; // ebx
  __int64 FileW; // rsi
  unsigned __int64 v8; // r15
  unsigned int v9; // r12d
  int v10; // ebx
  __int64 v11; // rax
  int v12; // ecx
  int v13; // eax
  CLangDataPack *v14; // rcx
  CLangDataPack *v15; // rcx
  __int128 *v16; // rax
  __int64 v17; // xmm0_8
  CLangDataPack *v18; // rcx
  unsigned __int64 v19; // r15
  unsigned __int64 i; // rbx
  struct ILangDataPack::PACKDATA_OBJECTINFO *v21; // rax
  CLangDataPack *v22; // rcx
  unsigned __int64 v23; // [rsp+48h] [rbp-41h]
  __int128 v24; // [rsp+50h] [rbp-39h] BYREF
  __int128 v25; // [rsp+60h] [rbp-29h]
  __int128 v26; // [rsp+70h] [rbp-19h]
  GUID v27; // [rsp+80h] [rbp-9h] BYREF
  GUID v28; // [rsp+90h] [rbp+7h]
  __int64 v29; // [rsp+A0h] [rbp+17h]

  v2 = 0;
  v23 = this;
  v3 = this;
  if ( !a2 )
    return 2147942487LL;
  Error = -2147024883;
  v6 = *(_QWORD *)(this + 48) == 0 ? 0x8007000D : 0;
  if ( *(_QWORD *)(this + 16) )
  {
    if ( *(_QWORD *)(this + 48) )
    {
      FileW = (__int64)CreateFileW(a2, 0xC0000000, 1u, 0, 2u, 0x80u, 0);
      if ( FileW == -1 )
        Error = ATL::AtlHresultFromLastError();
      else
        Error = v6;
      goto LABEL_10;
    }
    Error = *(_QWORD *)(this + 48) == 0 ? 0x8007000D : 0;
  }
  FileW = -1;
LABEL_10:
  v8 = *(_QWORD *)(v3 + 16);
  v9 = 0;
  if ( v8 )
  {
    do
    {
      v10 = *(_DWORD *)(ATL::CAtlArray<ILangDataPack::PACKDATA_OBJECTINFO,ATL::CElementTraits<ILangDataPack::PACKDATA_OBJECTINFO>>::operator[](
                          v3 + 8,
                          v2)
                      + 32)
          & 7;
      v11 = ATL::CAtlArray<ILangDataPack::PACKDATA_OBJECTINFO,ATL::CElementTraits<ILangDataPack::PACKDATA_OBJECTINFO>>::operator[](
              v3 + 8,
              v2);
      v12 = 8 - v10;
      v13 = *(_DWORD *)(v11 + 32);
      if ( !v10 )
        v12 = 0;
      ++v2;
      this = (unsigned int)(v12 + 40);
      v9 += this + v13;
    }
    while ( v2 < v8 );
    v3 = v23;
  }
  if ( Error >= 0 )
  {
    v27 = GUID_LangDataFile;
    v29 = v9 + 136LL;
    v28 = GUID_NULL;
    Error = CLangDataPack::SaveObjectHeader(
              (CLangDataPack *)this,
              (void *)FileW,
              (struct ILangDataPack::PACKDATA_OBJECTHEADER *)&v27);
    if ( Error >= 0 )
    {
      v29 = 56;
      v27 = GUID_LangDataFileHeader;
      v28 = GUID_NULL;
      Error = CLangDataPack::SaveObjectHeader(v14, (void *)FileW, (struct ILangDataPack::PACKDATA_OBJECTHEADER *)&v27);
      if ( Error >= 0 )
      {
        v16 = *(__int128 **)(v3 + 48);
        v26 = 0;
        v24 = 0;
        v25 = 0;
        v24 = *v16;
        v25 = v16[1];
        v17 = *((_QWORD *)v16 + 4);
        *((_QWORD *)&v26 + 1) = (char *)v16 + 40;
        *(_QWORD *)&v26 = v17;
        Error = CLangDataPack::SaveObject(v15, (void *)FileW, (struct ILangDataPack::PACKDATA_OBJECTINFO *)&v24);
        if ( Error >= 0 )
        {
          v29 = v9;
          v27 = GUID_LangDataBinaries;
          v28 = GUID_NULL;
          Error = CLangDataPack::SaveObjectHeader(
                    v18,
                    (void *)FileW,
                    (struct ILangDataPack::PACKDATA_OBJECTHEADER *)&v27);
          if ( Error >= 0 )
          {
            v19 = *(_QWORD *)(v3 + 16);
            for ( i = 0; i < v19; ++i )
            {
              v21 = (struct ILangDataPack::PACKDATA_OBJECTINFO *)ATL::CAtlArray<ILangDataPack::PACKDATA_OBJECTINFO,ATL::CElementTraits<ILangDataPack::PACKDATA_OBJECTINFO>>::operator[](
                                                                   v3 + 8,
                                                                   i);
              Error = CLangDataPack::SaveObject(v22, (void *)FileW, v21);
              if ( Error < 0 )
                break;
            }
          }
        }
      }
    }
  }
  if ( FileW )
    CloseHandle((HANDLE)FileW);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800d31f0  mov     [rsp-8+arg_10], rbx
0x1800d31f5  push    rbp
0x1800d31f6  push    rsi
0x1800d31f7  push    rdi
0x1800d31f8  push    r12
0x1800d31fa  push    r13
0x1800d31fc  push    r14
0x1800d31fe  push    r15
0x1800d3200  lea     rbp, [rsp-27h]
0x1800d3205  sub     rsp, 0B0h
0x1800d320c  mov     rax, cs:__security_cookie
0x1800d3213  xor     rax, rsp
0x1800d3216  mov     [rbp+57h+var_38], rax
0x1800d321a  xor     r13d, r13d
0x1800d321d  mov     [rbp+57h+var_98], rcx
0x1800d3221  mov     r10, rdx
0x1800d3224  mov     r14, rcx
0x1800d3227  test    rdx, rdx
0x1800d322a  jnz     short loc_1800D3236
0x1800d322c  mov     eax, 80070057h
0x1800d3231  jmp     loc_1800D3415
0x1800d3236  mov     rax, [rcx+30h]
0x1800d323a  mov     edi, 8007000Dh
0x1800d323f  neg     rax
0x1800d3242  sbb     ebx, ebx
0x1800d3244  not     ebx
0x1800d3246  and     ebx, edi
0x1800d3248  cmp     [rcx+10h], r13
0x1800d324c  jz      short loc_1800D3296
0x1800d324e  cmp     [rcx+30h], r13
0x1800d3252  jz      short loc_1800D3294
0x1800d3254  xor     r9d, r9d; lpSecurityAttributes
0x1800d3257  mov     [rsp+0E0h+hTemplateFile], r13; hTemplateFile
0x1800d325c  mov     [rsp+0E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800d3264  mov     edx, 0C0000000h; dwDesiredAccess
0x1800d3269  mov     rcx, r10; lpFileName
0x1800d326c  mov     [rsp+0E0h+dwCreationDisposition], 2; dwCreationDisposition
0x1800d3274  lea     r8d, [r9+1]; dwShareMode
0x1800d3278  call    cs:__imp_CreateFileW
0x1800d327e  mov     rsi, rax
0x1800d3281  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800d3285  jnz     short loc_1800D3290
0x1800d3287  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800d328c  mov     edi, eax
0x1800d328e  jmp     short loc_1800D329A
0x1800d3290  mov     edi, ebx
0x1800d3292  jmp     short loc_1800D329A
0x1800d3294  mov     edi, ebx
0x1800d3296  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800d329a  mov     r15, [r14+10h]
0x1800d329e  mov     r12d, r13d
0x1800d32a1  test    r15, r15
0x1800d32a4  jz      short loc_1800D32E7
0x1800d32a6  mov     rdx, r13
0x1800d32a9  lea     rcx, [r14+8]
0x1800d32ad  call    ??A?$CAtlArray@UPACKDATA_OBJECTINFO@ILangDataPack@@V?$CElementTraits@UPACKDATA_OBJECTINFO@ILangDataPack@@@ATL@@@ATL@@QEAAAEAUPACKDATA_OBJECTINFO@ILangDataPack@@_K@Z; ATL::CAtlArray<ILangDataPack::PACKDATA_OBJECTINFO,ATL::CElementTraits<ILangDataPack::PACKDATA_OBJECTINFO>>::operator[](unsigned __int64)
0x1800d32b2  mov     rdx, r13
0x1800d32b5  lea     rcx, [r14+8]
0x1800d32b9  mov     ebx, [rax+20h]
0x1800d32bc  and     ebx, 7
0x1800d32bf  call    ??A?$CAtlArray@UPACKDATA_OBJECTINFO@ILangDataPack@@V?$CElementTraits@UPACKDATA_OBJECTINFO@ILangDataPack@@@ATL@@@ATL@@QEAAAEAUPACKDATA_OBJECTINFO@ILangDataPack@@_K@Z; ATL::CAtlArray<ILangDataPack::PACKDATA_OBJECTINFO,ATL::CElementTraits<ILangDataPack::PACKDATA_OBJECTINFO>>::operator[](unsigned __int64)
0x1800d32c4  mov     ecx, 8
0x1800d32c9  sub     ecx, ebx
0x1800d32cb  test    ebx, ebx
0x1800d32cd  mov     eax, [rax+20h]
0x1800d32d0  cmovz   ecx, ebx
0x1800d32d3  inc     r13
0x1800d32d6  add     ecx, 28h ; '('; this
0x1800d32d9  add     eax, ecx
0x1800d32db  add     r12d, eax
0x1800d32de  cmp     r13, r15
0x1800d32e1  jb      short loc_1800D32A6
0x1800d32e3  mov     r14, [rbp+57h+var_98]
0x1800d32e7  test    edi, edi
0x1800d32e9  js      loc_1800D3405
0x1800d32ef  movups  xmm0, xmmword ptr cs:GUID_LangDataFile.Data1
0x1800d32f6  mov     ebx, r12d
0x1800d32f9  lea     r8, [rbp+57h+var_60]; struct ILangDataPack::PACKDATA_OBJECTHEADER *
0x1800d32fd  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x1800d3304  mov     rdx, rsi; void *
0x1800d3307  movdqu  [rbp+57h+var_60], xmm0
0x1800d330c  lea     rax, [rbx+88h]
0x1800d3313  mov     [rbp+57h+var_40], rax
0x1800d3317  movdqu  [rbp+57h+var_50], xmm1
0x1800d331c  call    ?SaveObjectHeader@CLangDataPack@@AEAAJPEAXPEAUPACKDATA_OBJECTHEADER@ILangDataPack@@@Z; CLangDataPack::SaveObjectHeader(void *,ILangDataPack::PACKDATA_OBJECTHEADER *)
0x1800d3321  mov     edi, eax
0x1800d3323  test    eax, eax
0x1800d3325  js      loc_1800D3405
0x1800d332b  movups  xmm0, xmmword ptr cs:GUID_LangDataFileHeader.Data1
0x1800d3332  lea     r8, [rbp+57h+var_60]; struct ILangDataPack::PACKDATA_OBJECTHEADER *
0x1800d3336  mov     rdx, rsi; void *
0x1800d3339  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x1800d3340  mov     [rbp+57h+var_40], 38h ; '8'
0x1800d3348  movdqu  [rbp+57h+var_60], xmm0
0x1800d334d  movdqu  [rbp+57h+var_50], xmm1
0x1800d3352  call    ?SaveObjectHeader@CLangDataPack@@AEAAJPEAXPEAUPACKDATA_OBJECTHEADER@ILangDataPack@@@Z; CLangDataPack::SaveObjectHeader(void *,ILangDataPack::PACKDATA_OBJECTHEADER *)
0x1800d3357  mov     edi, eax
0x1800d3359  test    eax, eax
0x1800d335b  js      loc_1800D3405
0x1800d3361  mov     rax, [r14+30h]
0x1800d3365  lea     r8, [rbp+57h+var_90]; struct ILangDataPack::PACKDATA_OBJECTINFO *
0x1800d3369  xorps   xmm0, xmm0
0x1800d336c  mov     rdx, rsi; void *
0x1800d336f  movups  [rbp+57h+var_70], xmm0
0x1800d3373  movups  [rbp+57h+var_90], xmm0
0x1800d3377  movups  [rbp+57h+var_80], xmm0
0x1800d337b  movups  xmm0, xmmword ptr [rax]
0x1800d337e  movups  [rbp+57h+var_90], xmm0
0x1800d3382  movups  xmm1, xmmword ptr [rax+10h]
0x1800d3386  movups  [rbp+57h+var_80], xmm1
0x1800d338a  movsd   xmm0, qword ptr [rax+20h]
0x1800d338f  add     rax, 28h ; '('
0x1800d3393  mov     qword ptr [rbp+57h+var_70+8], rax
0x1800d3397  movsd   qword ptr [rbp+57h+var_70], xmm0
0x1800d339c  call    ?SaveObject@CLangDataPack@@AEAAJPEAXPEAUPACKDATA_OBJECTINFO@ILangDataPack@@@Z; CLangDataPack::SaveObject(void *,ILangDataPack::PACKDATA_OBJECTINFO *)
0x1800d33a1  mov     edi, eax
0x1800d33a3  test    eax, eax
0x1800d33a5  js      short loc_1800D3405
0x1800d33a7  movups  xmm0, xmmword ptr cs:GUID_LangDataBinaries.Data1
0x1800d33ae  lea     r8, [rbp+57h+var_60]; struct ILangDataPack::PACKDATA_OBJECTHEADER *
0x1800d33b2  mov     rdx, rsi; void *
0x1800d33b5  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x1800d33bc  mov     [rbp+57h+var_40], rbx
0x1800d33c0  movdqu  [rbp+57h+var_60], xmm0
0x1800d33c5  movdqu  [rbp+57h+var_50], xmm1
0x1800d33ca  call    ?SaveObjectHeader@CLangDataPack@@AEAAJPEAXPEAUPACKDATA_OBJECTHEADER@ILangDataPack@@@Z; CLangDataPack::SaveObjectHeader(void *,ILangDataPack::PACKDATA_OBJECTHEADER *)
0x1800d33cf  mov     edi, eax
0x1800d33d1  test    eax, eax
0x1800d33d3  js      short loc_1800D3405
0x1800d33d5  mov     r15, [r14+10h]
0x1800d33d9  xor     ebx, ebx
0x1800d33db  test    r15, r15
0x1800d33de  jz      short loc_1800D3405
0x1800d33e0  mov     rdx, rbx
0x1800d33e3  lea     rcx, [r14+8]
0x1800d33e7  call    ??A?$CAtlArray@UPACKDATA_OBJECTINFO@ILangDataPack@@V?$CElementTraits@UPACKDATA_OBJECTINFO@ILangDataPack@@@ATL@@@ATL@@QEAAAEAUPACKDATA_OBJECTINFO@ILangDataPack@@_K@Z; ATL::CAtlArray<ILangDataPack::PACKDATA_OBJECTINFO,ATL::CElementTraits<ILangDataPack::PACKDATA_OBJECTINFO>>::operator[](unsigned __int64)
0x1800d33ec  mov     r8, rax; struct ILangDataPack::PACKDATA_OBJECTINFO *
0x1800d33ef  mov     rdx, rsi; void *
0x1800d33f2  call    ?SaveObject@CLangDataPack@@AEAAJPEAXPEAUPACKDATA_OBJECTINFO@ILangDataPack@@@Z; CLangDataPack::SaveObject(void *,ILangDataPack::PACKDATA_OBJECTINFO *)
0x1800d33f7  mov     edi, eax
0x1800d33f9  test    eax, eax
0x1800d33fb  js      short loc_1800D3405
0x1800d33fd  inc     rbx
0x1800d3400  cmp     rbx, r15
0x1800d3403  jb      short loc_1800D33E0
0x1800d3405  test    rsi, rsi
0x1800d3408  jz      short loc_1800D3413
0x1800d340a  mov     rcx, rsi; hObject
0x1800d340d  call    cs:__imp_CloseHandle
0x1800d3413  mov     eax, edi
0x1800d3415  mov     rcx, [rbp+57h+var_38]
0x1800d3419  xor     rcx, rsp; StackCookie
0x1800d341c  call    __security_check_cookie
0x1800d3421  mov     rbx, [rsp+0E0h+arg_10]
0x1800d3429  add     rsp, 0B0h
0x1800d3430  pop     r15
0x1800d3432  pop     r14
0x1800d3434  pop     r13
0x1800d3436  pop     r12
0x1800d3438  pop     rdi
0x1800d3439  pop     rsi
0x1800d343a  pop     rbp
0x1800d343b  retn
```
