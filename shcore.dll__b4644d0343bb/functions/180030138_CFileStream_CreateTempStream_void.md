# CFileStream::_CreateTempStream(void)

- ea: `0x180030138`
- end: `0x180030329`
- name: `?_CreateTempStream@CFileStream@@AEAAJXZ`
- size: `497`
- prototype: `__int64 __fastcall(CFileStream *__hidden this)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x18001a4c0`
- `0x18001a870`
- `0x180030010`
- `0x180080de0`

## callees

- `0x18001a10c`
- `0x18001a270`
- `0x18001a408`
- `0x18001a750`
- `0x180030138`
- `0x180030584`
- `0x180080d10`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18003021c`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180030261`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18003021c`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180030261`

## pseudocode

```c
__int64 __fastcall CFileStream::_CreateTempStream(CFileStream *this)
{
  __int64 *v1; // r14
  const WCHAR *v3; // rcx
  int TempStreamNameAlloc; // edi
  int v5; // r9d
  __int64 v6; // rcx
  __int64 v7; // rcx
  int v8; // eax
  union _LARGE_INTEGER v9; // rsi
  HANDLE v10; // rbp
  LARGE_INTEGER v11; // rdx
  bool v12; // zf
  struct IStream *v13; // rdx
  union _LARGE_INTEGER NewFilePointer; // [rsp+70h] [rbp+8h] BYREF
  HANDLE hFile; // [rsp+78h] [rbp+10h] BYREF
  LARGE_INTEGER liDistanceToMove; // [rsp+80h] [rbp+18h]

  v1 = (__int64 *)((char *)this + 4248);
  Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free((char *)this + 4248);
  v3 = &SourceString;
  v1[1] = -1;
  v1[2] = -1;
  if ( *((_QWORD *)this + 523) )
    v3 = (const WCHAR *)*((_QWORD *)this + 523);
  TempStreamNameAlloc = CreateTempStreamNameAlloc(v3, 0, v1);
  if ( TempStreamNameAlloc < 0 )
    goto LABEL_16;
  v6 = *v1;
  LOBYTE(v5) = 1;
  NewFilePointer.QuadPart = 0;
  TempStreamNameAlloc = CFileStream_Create(v6, 4114, 2, v5);
  if ( TempStreamNameAlloc < 0 )
    goto LABEL_16;
  v7 = *((_QWORD *)this + 529);
  hFile = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v7 + 24LL))(v7, &hFile);
  v9 = NewFilePointer;
  TempStreamNameAlloc = v8;
  if ( v8 >= 0 )
  {
    v10 = hFile;
    v11.QuadPart = *((_DWORD *)this + 19) - *((_DWORD *)this + 20);
    NewFilePointer.QuadPart = 0;
    SetFilePointerEx(hFile, v11, &NewFilePointer, 1u);
    v12 = (*((_DWORD *)this + 17) & 0x10000) == 0;
    *(_QWORD *)((char *)this + 76) = 0;
    if ( v12 || *((_BYTE *)this + 4241) )
    {
      *((union _LARGE_INTEGER *)this + 534) = v9;
      _InterlockedIncrement((volatile signed __int32 *)(v9.QuadPart + 64));
      *(_QWORD *)(*((_QWORD *)this + 534) + 4280LL) = this;
    }
    else
    {
      liDistanceToMove.QuadPart = 0;
      SetFilePointerEx(v10, 0, 0, 0);
      hFile = (HANDLE)-1LL;
      if ( v9.QuadPart )
        v13 = (struct IStream *)(v9.QuadPart + 16);
      else
        v13 = 0;
      TempStreamNameAlloc = CFileStream::CopyTo(
                              (CFileStream *)((char *)this + 16),
                              v13,
                              (union _ULARGE_INTEGER)hFile,
                              0,
                              0);
      if ( TempStreamNameAlloc >= 0 )
      {
        *((union _LARGE_INTEGER *)this + 534) = v9;
        _InterlockedIncrement((volatile signed __int32 *)(v9.QuadPart + 64));
        CFileStream::Seek((CFileStream *)(*((_QWORD *)this + 534) + 16LL), NewFilePointer, 0, 0);
        CFileStream::Seek((CFileStream *)((char *)this + 16), NewFilePointer, 0, 0);
      }
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 529) + 32LL))(*((_QWORD *)this + 529));
  }
  CFileStream::Release((CFileStream *)(v9.QuadPart + 16));
  if ( TempStreamNameAlloc < 0 )
LABEL_16:
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(v1);
  return (unsigned int)TempStreamNameAlloc;
}

```

## disassembly

```asm
0x180030138  push    rbx
0x18003013a  push    rbp
0x18003013b  push    rsi
0x18003013c  push    rdi
0x18003013d  push    r14
0x18003013f  sub     rsp, 40h
0x180030143  lea     r14, [rcx+1098h]
0x18003014a  mov     rbx, rcx
0x18003014d  mov     rcx, r14
0x180030150  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180030155  or      rax, 0FFFFFFFFFFFFFFFFh
0x180030159  lea     rcx, SourceString
0x180030160  mov     [r14+8], rax
0x180030164  mov     r8, r14
0x180030167  mov     [r14+10h], rax
0x18003016b  mov     rax, [rbx+1058h]
0x180030172  test    rax, rax
0x180030175  cmovnz  rcx, rax
0x180030179  xor     edx, edx
0x18003017b  call    ?CreateTempStreamNameAlloc@@YAJPEBGW4CSTN_FILE_EXTENSION_OPTION@@PEAPEAG@Z; CreateTempStreamNameAlloc(ushort const *,CSTN_FILE_EXTENSION_OPTION,ushort * *)
0x180030180  mov     edi, eax
0x180030182  test    eax, eax
0x180030184  js      loc_180030314
0x18003018a  mov     rcx, [r14]
0x18003018d  lea     rax, [rsp+68h+NewFilePointer]
0x180030192  mov     [rsp+68h+var_38], rax
0x180030197  mov     r9b, 1
0x18003019a  mov     eax, [rbx+1080h]
0x1800301a0  mov     edx, 1012h
0x1800301a5  mov     r8d, 2
0x1800301ab  mov     [rsp+68h+var_40], eax
0x1800301af  mov     qword ptr [rsp+68h+NewFilePointer], 0
0x1800301b8  call    CFileStream_Create
0x1800301bd  mov     edi, eax
0x1800301bf  test    eax, eax
0x1800301c1  js      loc_180030314
0x1800301c7  mov     rcx, [rbx+1088h]
0x1800301ce  lea     rdx, [rsp+68h+hFile]
0x1800301d3  mov     [rsp+68h+hFile], 0
0x1800301dc  mov     rax, [rcx]
0x1800301df  mov     rax, [rax+18h]
0x1800301e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301e8  mov     rsi, qword ptr [rsp+68h+NewFilePointer]
0x1800301ed  mov     edi, eax
0x1800301ef  test    eax, eax
0x1800301f1  js      loc_180030307
0x1800301f7  mov     eax, [rbx+4Ch]
0x1800301fa  lea     r8, [rsp+68h+NewFilePointer]; lpNewFilePointer
0x1800301ff  sub     eax, [rbx+50h]
0x180030202  mov     r9d, 1; dwMoveMethod
0x180030208  mov     rbp, [rsp+68h+hFile]
0x18003020d  movsxd  rdx, eax; liDistanceToMove
0x180030210  mov     rcx, rbp; hFile
0x180030213  mov     qword ptr [rsp+68h+NewFilePointer], 0
0x18003021c  call    cs:__imp_SetFilePointerEx
0x180030222  test    dword ptr [rbx+44h], 10000h
0x180030229  mov     qword ptr [rbx+4Ch], 0
0x180030231  jz      loc_1800302DB
0x180030237  cmp     byte ptr [rbx+1091h], 0
0x18003023e  jnz     loc_1800302DB
0x180030244  mov     qword ptr [rsp+68h+liDistanceToMove], 0
0x180030250  xor     r9d, r9d; dwMoveMethod
0x180030253  mov     rdx, qword ptr [rsp+68h+liDistanceToMove]; liDistanceToMove
0x18003025b  xor     r8d, r8d; lpNewFilePointer
0x18003025e  mov     rcx, rbp; hFile
0x180030261  call    cs:__imp_SetFilePointerEx
0x180030267  or      eax, 0FFFFFFFFh
0x18003026a  mov     dword ptr [rsp+68h+hFile], eax
0x18003026e  mov     dword ptr [rsp+68h+hFile+4], eax
0x180030272  test    rsi, rsi
0x180030275  jz      short loc_18003027D
0x180030277  lea     rdx, [rsi+10h]
0x18003027b  jmp     short loc_18003027F
0x18003027d  xor     edx, edx; struct IStream *
0x18003027f  mov     r8, [rsp+68h+hFile]; union _ULARGE_INTEGER
0x180030284  lea     rcx, [rbx+10h]; this
0x180030288  xor     r9d, r9d; union _ULARGE_INTEGER *
0x18003028b  mov     [rsp+68h+var_48], 0; union _ULARGE_INTEGER *
0x180030294  call    ?CopyTo@CFileStream@@UEAAJPEAUIStream@@T_ULARGE_INTEGER@@PEAT3@2@Z; CFileStream::CopyTo(IStream *,_ULARGE_INTEGER,_ULARGE_INTEGER *,_ULARGE_INTEGER *)
0x180030299  mov     edi, eax
0x18003029b  test    eax, eax
0x18003029d  js      short loc_1800302F4
0x18003029f  mov     [rbx+10B0h], rsi
0x1800302a6  lock inc dword ptr [rsi+40h]
0x1800302aa  mov     rcx, [rbx+10B0h]
0x1800302b1  xor     r9d, r9d; union _ULARGE_INTEGER *
0x1800302b4  mov     rdx, qword ptr [rsp+68h+NewFilePointer]; union _LARGE_INTEGER
0x1800302b9  add     rcx, 10h; this
0x1800302bd  xor     r8d, r8d; unsigned int
0x1800302c0  call    ?Seek@CFileStream@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z; CFileStream::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)
0x1800302c5  mov     rdx, qword ptr [rsp+68h+NewFilePointer]; union _LARGE_INTEGER
0x1800302ca  lea     rcx, [rbx+10h]; this
0x1800302ce  xor     r9d, r9d; union _ULARGE_INTEGER *
0x1800302d1  xor     r8d, r8d; unsigned int
0x1800302d4  call    ?Seek@CFileStream@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z; CFileStream::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)
0x1800302d9  jmp     short loc_1800302F4
0x1800302db  mov     [rbx+10B0h], rsi
0x1800302e2  lock inc dword ptr [rsi+40h]
0x1800302e6  mov     rax, [rbx+10B0h]
0x1800302ed  mov     [rax+10B8h], rbx
0x1800302f4  mov     rcx, [rbx+1088h]
0x1800302fb  mov     rax, [rcx]
0x1800302fe  mov     rax, [rax+20h]
0x180030302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030307  lea     rcx, [rsi+10h]; this
0x18003030b  call    ?Release@CFileStream@@UEAAKXZ; CFileStream::Release(void)
0x180030310  test    edi, edi
0x180030312  jns     short loc_18003031C
0x180030314  mov     rcx, r14
0x180030317  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x18003031c  mov     eax, edi
0x18003031e  add     rsp, 40h
0x180030322  pop     r14
0x180030324  pop     rdi
0x180030325  pop     rsi
0x180030326  pop     rbp
0x180030327  pop     rbx
0x180030328  retn
```
