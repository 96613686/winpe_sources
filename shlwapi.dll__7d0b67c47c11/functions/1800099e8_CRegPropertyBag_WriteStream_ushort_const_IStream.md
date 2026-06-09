# CRegPropertyBag::_WriteStream(ushort const *,IStream *)

- ea: `0x1800099e8`
- end: `0x180009aca`
- name: `?_WriteStream@CRegPropertyBag@@AEAAJPEBGPEAUIStream@@@Z`
- size: `226`
- prototype: `int(CRegPropertyBag *__hidden this, const unsigned __int16 *, struct IStream *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x1800097e0`

## callees

- `0x1800099e8`
- `0x180009ad0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009a3f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009a3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009a9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009a9d`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x180009a8a`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x180009a8a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180009a66`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180009a66`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180009a50`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180009a50`

## pseudocode

```c
__int64 __fastcall CRegPropertyBag::_WriteStream(HKEY *this, const unsigned __int16 *a2, struct IStream *a3)
{
  HRESULT StreamSize; // ebx
  ULONG v7; // edi
  char *pvData; // rsi
  ULONG cb; // [rsp+78h] [rbp+20h] BYREF

  cb = 0;
  StreamSize = CRegPropertyBag::_GetStreamSize((CRegPropertyBag *)this, a3, &cb);
  if ( StreamSize >= 0 )
  {
    v7 = cb;
    if ( cb )
    {
      if ( cb + 16 < cb )
      {
        return (unsigned int)-2147024362;
      }
      else
      {
        pvData = (char *)LocalAlloc(0x40u, cb + 16);
        if ( pvData )
        {
          StreamSize = IStream_Reset(a3);
          if ( StreamSize >= 0 )
            StreamSize = IStream_Read(a3, pvData + 16, v7);
          if ( StreamSize >= 0 && SHSetValueW(this[4], 0, a2, 3u, pvData, v7 + 16) )
            StreamSize = -2147467259;
          LocalFree(pvData);
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
    }
  }
  return (unsigned int)StreamSize;
}

```

## disassembly

```asm
0x1800099e8  mov     rax, rsp
0x1800099eb  mov     [rax+8], rbx
0x1800099ef  mov     [rax+10h], rbp
0x1800099f3  push    rsi
0x1800099f4  push    rdi
0x1800099f5  push    r13
0x1800099f7  push    r14
0x1800099f9  push    r15
0x1800099fb  sub     rsp, 30h
0x1800099ff  mov     r14, r8
0x180009a02  mov     dword ptr [rax+20h], 0
0x180009a09  mov     r15, rdx
0x180009a0c  lea     r8, [rax+20h]; unsigned int *
0x180009a10  mov     rdx, r14; struct IStream *
0x180009a13  mov     r13, rcx
0x180009a16  call    ?_GetStreamSize@CRegPropertyBag@@AEAAJPEAUIStream@@PEAK@Z; CRegPropertyBag::_GetStreamSize(IStream *,ulong *)
0x180009a1b  mov     ebx, eax
0x180009a1d  test    eax, eax
0x180009a1f  js      loc_180009AB1
0x180009a25  mov     edi, [rsp+58h+cb]
0x180009a29  test    edi, edi
0x180009a2b  jz      loc_180009AB1
0x180009a31  lea     ebp, [rdi+10h]
0x180009a34  cmp     ebp, edi
0x180009a36  jb      short loc_180009AAC
0x180009a38  mov     edx, ebp; uBytes
0x180009a3a  mov     ecx, 40h ; '@'; uFlags
0x180009a3f  call    cs:__imp_LocalAlloc
0x180009a45  mov     rsi, rax
0x180009a48  test    rax, rax
0x180009a4b  jz      short loc_180009AA5
0x180009a4d  mov     rcx, r14; pstm
0x180009a50  call    cs:__imp_IStream_Reset
0x180009a56  mov     ebx, eax
0x180009a58  test    eax, eax
0x180009a5a  js      short loc_180009A6E
0x180009a5c  lea     rdx, [rsi+10h]; pv
0x180009a60  mov     r8d, edi; cb
0x180009a63  mov     rcx, r14; pstm
0x180009a66  call    cs:__imp_IStream_Read
0x180009a6c  mov     ebx, eax
0x180009a6e  test    ebx, ebx
0x180009a70  js      short loc_180009A9A
0x180009a72  mov     rcx, [r13+20h]; hkey
0x180009a76  mov     r9d, 3; dwType
0x180009a7c  mov     [rsp+58h+cbData], ebp; cbData
0x180009a80  mov     r8, r15; pszValue
0x180009a83  xor     edx, edx; pszSubKey
0x180009a85  mov     [rsp+58h+pvData], rsi; pvData
0x180009a8a  call    cs:__imp_SHSetValueW
0x180009a90  test    eax, eax
0x180009a92  mov     ecx, 80004005h
0x180009a97  cmovnz  ebx, ecx
0x180009a9a  mov     rcx, rsi; hMem
0x180009a9d  call    cs:__imp_LocalFree
0x180009aa3  jmp     short loc_180009AB1
0x180009aa5  mov     ebx, 8007000Eh
0x180009aaa  jmp     short loc_180009AB1
0x180009aac  mov     ebx, 80070216h
0x180009ab1  mov     rbp, [rsp+58h+arg_8]
0x180009ab6  mov     eax, ebx
0x180009ab8  mov     rbx, [rsp+58h+arg_0]
0x180009abd  add     rsp, 30h
0x180009ac1  pop     r15
0x180009ac3  pop     r14
0x180009ac5  pop     r13
0x180009ac7  pop     rdi
0x180009ac8  pop     rsi
0x180009ac9  retn
```
